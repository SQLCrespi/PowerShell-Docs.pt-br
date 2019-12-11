---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Rastreamento e registro de scripts
ms.openlocfilehash: 6b7e5022cb4c974da5ddb3d670b5808dc9fb7bdc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71147796"
---
# <a name="script-tracing-and-logging"></a>Rastreamento e registro de scripts

Embora o PowerShell já tenha a configuração **LogPipelineExecutionDetails** da Política de Grupo para registrar em log a chamada de cmdlets, a linguagem de scripts do PowerShell traz vários recursos que talvez você queira registrar em log e auditar. O novo recurso de Rastreamento de Script Detalhado permite habilitar o acompanhamento e a análise detalhados ao usar scripts do PowerShell em um sistema. Depois de habilitar o rastreamento detalhado de scripts, o PowerShell registra em log todos os blocos de script no log de eventos do ETW, **Microsoft-Windows-PowerShell/Operational**. Se um bloco de script criar outro bloco de script, por exemplo, chamando `Invoke-Expression`, o bloco de script chamado também será registrado em log.

O registro em log é habilitado pela configuração **Ativar Registro de Bloco de Script do PowerShell** da Política de Grupo em **Modelos Administrativos** -> **Componentes do Windows** -> **Windows PowerShell**.

Os eventos são:

| Canal |                               Operacional                               |
| ------- | ----------------------------------------------------------------------- |
| Nível   | Verbose                                                                 |
| Opcode  | Criar                                                                  |
| Tarefa    | CommandStart                                                            |
| Palavra-chave | Runspace                                                                |
| EventId | Engine_ScriptBlockCompiled (0x1008 = 4104)                              |
| Mensagem | Criando texto Scriptblock (%1 de %2): </br> %3 </br> ID de ScriptBlock: %4 |


O texto inserido na mensagem é a extensão do bloco de script compilado. A ID é um GUID que é retido durante o ciclo de vida do bloco de script.

Ao habilitar o registro detalhado, o recurso escreve marcadores de início e de fim:

| Canal |                                 Operacional                                |
| ------- | -------------------------------------------------------------------------- |
| Nível   | Verbose                                                                    |
| Opcode  | Abrir/Fechar                                                               |
| Tarefa    | CommandStart/CommandStop                                                 |
| Palavra-chave | Runspace                                                                   |
| EventId | ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) / </br> ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106) |
| Mensagem | Chamada da ID do ScriptBlock: %1 iniciada/concluída </br> Runspace ID: %2 |

A ID é o GUID que representa o bloco de script (que pode ser correlacionado com a ID de evento 0x1008), e a ID do Runspace representa o runspace no qual este bloco de script foi executado.

Sinais de porcentagem na mensagem de invocação representam propriedades estruturadas do ETW. Embora eles sejam substituídos pelos valores reais no texto da mensagem, uma maneira mais robusta de acessá-los é recuperar a mensagem com o cmdlet Get-WinEvent e depois usar a matriz **Properties** da mensagem.

Aqui está um exemplo de como essa funcionalidade pode ajudar a descodificar uma tentativa mal-intencionada de criptografar e ocultar um script:

```powershell
## Malware
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)

    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)
}

$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
Invoke-Expression $decrypted
```

A execução disso gera as seguintes entradas de log:

```Output
Compiling Scriptblock text (1 of 1):
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)
    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)

}
ScriptBlock ID: ad8ae740-1f33-42aa-8dfc-1314411877e3

Compiling Scriptblock text (1 of 1):
$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
ScriptBlock ID: ba11c155-d34c-4004-88e3-6502ecb50f52

Compiling Scriptblock text (1 of 1):
Invoke-Expression $decrypted
ScriptBlock ID: 856c01ca-85d7-4989-b47f-e6a09ee4eeb3

Compiling Scriptblock text (1 of 1):
Write-Host 'Pwnd'
ScriptBlock ID: 5e618414-4e77-48e3-8f65-9a863f54b4c8
```

Caso o tamanho do bloco de script exceda a capacidade de um único evento, o PowerShell dividirá o script em várias partes. Aqui está o código de exemplo para recombinar um script desde suas mensagens de log:

```powershell
$created = Get-WinEvent -FilterHashtable @{ ProviderName="Microsoft-Windows-PowerShell"; Id = 4104 } |
  Where-Object { $_.<...> }
$sortedScripts = $created | sort { $_.Properties[0].Value }
$mergedScript = -join ($sortedScripts | % { $_.Properties[2].Value })
```

Assim como acontece com todos os sistemas de registro em log que têm um buffer de retenção limitado, uma forma de atacar essa infraestrutura seria inundar o log com eventos diferentes para ocultar a evidência anterior. Para se proteger contra esse ataque, verifique se você tem alguma forma de coletar logs de eventos configurada (Encaminhamento de Eventos do Windows). Saiba mais em [Identificar o adversário com o monitoramento de logs de eventos do Windows](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm).