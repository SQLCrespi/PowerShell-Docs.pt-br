---
description: Descreve como executar comandos remotos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: 04c297f849a30ddabecec98a5a2250b8d9b3fbfa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195658"
---
# <a name="about-remote"></a>Sobre o remoto

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como executar comandos remotos no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Você pode executar comandos remotos em um único computador ou em vários computadores usando uma conexão temporária ou persistente. Você também pode iniciar uma sessão interativa com um único computador remoto.

Este tópico fornece uma série de exemplos para mostrar como executar diferentes tipos de comando remoto. Depois de tentar esses comandos básicos, leia os tópicos da ajuda que descrevem cada cmdlet que é usado nesses comandos. Os tópicos fornecem os detalhes e explicam como você pode modificar os comandos para atender às suas necessidades.

Observação: para usar a comunicação remota do PowerShell, os computadores locais e remotos devem ser configurados para comunicação remota. Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

## <a name="how-to-start-an-interactive-session-enter-pssession"></a>COMO INICIAR UMA SESSÃO INTERATIVA (ENTER-PSSESSION)

A maneira mais fácil de executar comandos remotos é iniciar uma sessão interativa com um computador remoto.

Quando a sessão é iniciada, os comandos digitados são executados no computador remoto, assim como se você os digitou diretamente no computador remoto. Você pode se conectar a apenas um computador em cada sessão interativa.

Para iniciar uma sessão interativa, use o cmdlet Enter-PSSession. O comando a seguir inicia uma sessão interativa com o computador Server01:

```powershell
Enter-PSSession Server01
```

O prompt de comando é alterado para indicar que você está conectado ao computador Server01.

```
Server01\PS>
```

Agora, você pode digitar comandos no computador Server01.

Para encerrar a sessão interativa, digite:

```powershell
Exit-PSSession
```

Para obter mais informações, consulte Enter-PSSession.

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a>COMO USAR CMDLETS QUE TÊM UM PARÂMETRO COMPUTERNAME PARA OBTER DADOS REMOTOS

Vários cmdlets têm um parâmetro ComputerName que permite que você obtenha objetos de computadores remotos.

Como esses cmdlets não usam a comunicação remota do PowerShell baseada no WS-Management, você pode usar o parâmetro ComputerName desses cmdlets em qualquer computador que esteja executando o PowerShell. Os computadores não precisam ser configurados para comunicação remota do PowerShell e os computadores não precisam atender aos requisitos do sistema para comunicação remota.

Os cmdlets a seguir têm um parâmetro ComputerName:

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

Por exemplo, o comando a seguir obtém os serviços no computador remoto Server01:

```powershell
Get-Service -ComputerName Server01
```

Normalmente, os cmdlets que oferecem suporte a comunicação remota sem configuração especial têm um parâmetro **ComputerName** e não têm um parâmetro **Session** . Para localizar esses cmdlets em sua sessão, digite:

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a>COMO EXECUTAR UM COMANDO REMOTO

Para executar outros comandos em computadores remotos, use o cmdlet Invoke-Command.

Para executar um único comando ou alguns comandos não relacionados, use o parâmetro ComputerName de Invoke-Command para especificar os computadores remotos. Use o parâmetro ScriptBlock para especificar o comando.

Por exemplo, o comando a seguir executa um comando Get-Culture no computador Server01.

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

O parâmetro ComputerName foi projetado para a situação em que você executa um único comando ou vários comandos não relacionados em um ou vários computadores. Para estabelecer uma conexão persistente com um computador remoto, use o parâmetro Session.

## <a name="how-to-create-a-persistent-connection-pssession"></a>COMO CRIAR UMA CONEXÃO PERSISTENTE (PSSESSION)

Quando você usa o parâmetro ComputerName do cmdlet Invoke-Command, o Windows PowerShell estabelece uma conexão apenas para o comando. Em seguida, fecha a conexão quando o comando for concluído. Todas as variáveis ou funções definidas no comando são perdidas.

Para criar uma conexão persistente com um computador remoto, use o cmdlet New-PSSession. Por exemplo, o comando a seguir cria PSSessions nos computadores Server01 e Server02 e, em seguida, salva as PSSessions na variável $s.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a>COMO EXECUTAR COMANDOS EM UMA PSSESSION

Com uma PSSession, você pode executar uma série de comandos remotos que compartilham dados, como funções, aliases e os valores de variáveis. Para executar comandos em uma PSSession, use o parâmetro Session do cmdlet Invoke-Command.

Por exemplo, o comando a seguir usa o cmdlet Invoke-Command para executar um comando Get-Process em PSSessions nos computadores Server01 e Server02.
O comando salva os processos em uma variável $p em cada PSSession.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

Como a PSSession usa uma conexão persistente, você pode executar outro comando na mesma PSSession que usa a variável $p. O comando a seguir conta o número de processos salvos em $p.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a>COMO EXECUTAR UM COMANDO REMOTO EM VÁRIOS COMPUTADORES

Para executar um comando remoto em vários computadores, digite todos os nomes de computador no valor do parâmetro ComputerName de Invoke-Command. Separe os nomes com vírgulas.

Por exemplo, o comando a seguir executa um comando Get-Culture em três computadores:

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

Você também pode executar um comando em várias PSSessions. Os comandos a seguir criam PSSessions nos computadores Server01, Server02 e Server03 e, em seguida, executam um comando Get-Culture em cada uma das PSSessions.

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

Para incluir a lista de computadores do computador local, digite o nome do computador local, digite um ponto (.) ou digite "localhost".

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a>COMO EXECUTAR UM SCRIPT EM COMPUTADORES REMOTOS

Para executar um script local em computadores remotos, use o parâmetro FilePath de Invoke-Command.

Por exemplo, o comando a seguir executa o script Sample.ps1 nos computadores S1 e S2:

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

Os resultados do script são retornados para o computador local. Você não precisa copiar nenhum arquivo.

## <a name="how-to-stop-a-remote-command"></a>COMO INTERROMPER UM COMANDO REMOTO

Para interromper um comando, pressione CTRL + C. A solicitação de interrupção é passada para o computador remoto onde ele termina o comando remoto.

## <a name="for-more-information"></a>PARA OBTER MAIS INFORMAÇÕES

- Para obter informações sobre os requisitos de sistema para comunicação remota, consulte [about_Remote_Requirements](about_Remote_Requirements.md).

- Para obter ajuda na formatação da saída remota, consulte [about_Remote_Output](about_Remote_Output.md).

- Para obter informações sobre como funciona a comunicação remota, como gerenciar dados remotos, configurações especiais, problemas de segurança e outras perguntas frequentes, consulte [about_Remote_FAQ](about_Remote_FAQ.md).

- Para obter ajuda na resolução de erros de comunicação remota, consulte about_Remote_Troubleshooting.

- Para obter informações sobre PSSessions e conexões persistentes, consulte [about_PSSessions](about_PSSessions.md).

- Para obter informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](about_Jobs.md).

## <a name="keywords"></a>Palavras-chave

about_Remoting

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_PSSessions](about_PSSessions.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_FAQ](about_Remote_FAQ.md)

[about_Remote_TroubleShooting](about_Remote_TroubleShooting.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
