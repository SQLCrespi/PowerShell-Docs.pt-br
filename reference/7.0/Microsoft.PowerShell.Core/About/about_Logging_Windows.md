---
description: O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_windows?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging-Windows
ms.openlocfilehash: 62fa0592d931f5f675661f4d41ee01df6b89dc06
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195882"
---
# <a name="about-logging-windows"></a>Sobre o registro em log do Windows

## <a name="short-description"></a>Descrição breve

O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.

## <a name="long-description"></a>Descrição longa

O PowerShell registra detalhes sobre as operações do PowerShell, como iniciar e interromper o mecanismo e os provedores e executar comandos do PowerShell.

> [!NOTE]
> As versões 3,0, 4,0, 5,0 e 5,1 do Windows PowerShell incluem cmdlets do **EventLog** para os logs de eventos do Windows. Nessas versões, para exibir a lista de cmdlets do **EventLog** , digite: `Get-Command -Noun EventLog` . Para obter mais informações, consulte a documentação do cmdlet e about_EventLogs para sua versão do Windows PowerShell.

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a>Exibindo as entradas do log de eventos do PowerShell no Windows

Os logs do PowerShell podem ser exibidos usando o Windows Visualizador de Eventos. O log de eventos está localizado no grupo logs de aplicativos e serviços e é nomeado `PowerShellCore` . O provedor de ETW associado `GUID` é `{f90714a8-5509-434a-bf6d-b1624c8a19a2}` .

Quando o log de bloco de script estiver habilitado, o PowerShell registrará os seguintes eventos no `PowerShellCore/Operational` log:

|Campo| Valor|
|-|-|
|EventId|`4104` / `0x1008`|
|Canal|`Operational`|
|Nível|`Verbose`|
|Opcode|`Create`|
|Tarefa|`CommandStart`|
|Palavra-chave|`Runspace`|

### <a name="registering-the-powershell-event-provider-on-windows"></a>Registrando o provedor de eventos do PowerShell no Windows

Ao contrário do Linux ou do macOS, o Windows exige que o provedor de eventos seja registrado antes que os eventos possam ser gravados no log de eventos. Para habilitar o provedor de eventos do PowerShell, execute o seguinte comando em um prompt do PowerShell com privilégios elevados.

```powershell
$PSHOME\RegisterManifest.ps1
```

### <a name="unregistering-the-powershell-event-provider-on-windows"></a>Cancelando o registro do provedor de eventos do PowerShell no Windows

O registro do provedor de eventos coloca um bloqueio na biblioteca binária usada para decodificar eventos. Para atualizar essa biblioteca, o provedor deve ter o registro cancelado para liberar esse bloqueio.

Para cancelar o registro do provedor do PowerShell, execute o seguinte comando em um prompt do PowerShell com privilégios elevados.

```powershell
$PSHOME\RegisterManifest.ps1 -Unregister
```

Depois de atualizar o PowerShell, execute `$PSHOME\RegisterManifest.ps1` para registrar o provedor de eventos atualizado.

## <a name="enabling-script-block-logging"></a>Habilitando o log de bloco de script

Quando você habilita o log de bloco de script, o PowerShell registra o conteúdo de todos os blocos de script que ele processa. Uma vez habilitada, qualquer sessão do PowerShell nova registra essas informações.

> [!NOTE]
> É recomendável habilitar o log de eventos protegidos, conforme descrito abaixo, ao usar o log de bloco de script para algo diferente de fins de diagnóstico.

O log de bloco de script pode ser habilitado via Política de Grupo ou uma configuração de registro.

### <a name="using-group-policy"></a>Como usar a Política de Grupo

Para habilitar a transcrição automática, habilite o `Turn on PowerShell Script Block
Logging` recurso no política de grupo por meio do `Administrative Templates -> Windows
Components -> Windows PowerShell` .

### <a name="using-the-registry"></a>Usando o registro

Execute a seguinte função:

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a>Log de eventos protegidos

Aumentar o nível de log em um sistema aumenta a possibilidade de que o conteúdo registrado possa conter dados confidenciais. Por exemplo, com o log de script habilitado, as credenciais ou outros dados confidenciais usados por um script podem ser gravados no log de eventos. Quando um computador que tem dados confidenciais registrados em log é comprometido, os logs podem fornecer a um invasor as informações necessárias para estender seu alcance.

Para proteger essas informações, o Windows 10 apresenta o registro em log de eventos protegido.
O log de eventos protegido permite que os aplicativos participantes criptografem os dados confidenciais gravados no log de eventos. Posteriormente, você pode descriptografar e processar esses logs em um coletor de logs mais seguro e centralizado.

O conteúdo do log de eventos é protegido usando o padrão de CMS (sintaxe de mensagem criptográfica) da IETF. O CMS usa criptografia de chave pública. As chaves usadas para criptografar conteúdo e descriptografar conteúdo são mantidas separadas.

A chave pública pode ser compartilhada amplamente e não dados confidenciais. Qualquer conteúdo criptografado com essa chave pública só pode ser descriptografado pela chave privada. Para obter mais informações sobre criptografia de chave pública, consulte [Wikipédia-criptografia de chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).

Para habilitar uma política de log de eventos protegida, implante uma chave pública em todos os computadores que têm dados de log de eventos a serem protegidos. A chave privada correspondente é usada para processar os logs de eventos em um local mais seguro, como um coletor de log de eventos central ou um agregador [Siem][] . Você pode configurar o SIEM no Azure. Para obter mais informações, consulte [integração de Siem genérico](/cloud-app-security/siem).

### <a name="enabling-protected-event-logging-via-group-policy"></a>Habilitando o log de eventos protegidos via Política de Grupo

Para habilitar o log de eventos protegidos, habilite o `Enable Protected Event Logging` recurso no política de grupo por meio do `Administrative Templates -> Windows Components
-> Event Logging` . Essa configuração requer um certificado de criptografia, que você pode fornecer em uma das várias formas:

- O conteúdo de um certificado X. 509 codificado em base-64 (por exemplo, conforme oferecido pela `Export` opção no Gerenciador de certificados).
- A impressão digital de um certificado que pode ser encontrado no repositório de certificados do computador local (pode ser implantado pela infraestrutura PKI).
- O caminho completo de um certificado (pode ser local ou um compartilhamento remoto).
- O caminho para um diretório que contém um certificado ou certificados (pode ser local ou um compartilhamento remoto).
- O nome da entidade de um certificado que pode ser encontrado no repositório de certificados do computador local (pode ser implantado pela infraestrutura PKI).

O certificado resultante deve ter `Document Encryption` como um uso avançado de chave ( `1.3.6.1.4.1.311.80.1` ) e um `Data Encipherment` ou mais `Key
Encipherment` usos de chave habilitados.

> [!WARNING]
> A chave privada não deve ser implantada nos eventos de log de máquinas. Ele deve ser mantido em um local seguro onde você descriptografa as mensagens.

### <a name="decrypting-protected-event-logging-messages"></a>Descriptografando mensagens de log de eventos protegidas

O script a seguir irá recuperar e descriptografar, supondo que você tenha a chave privada:

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a>Confira também

[about_Logging_Non-Windows](about_Logging_Non-Windows.md)

[PowerShell para a equipe azul](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[Integração genérica ao SIEM](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
