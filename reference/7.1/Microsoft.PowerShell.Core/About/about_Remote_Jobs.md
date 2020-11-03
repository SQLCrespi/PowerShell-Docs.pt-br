---
description: Descreve como executar trabalhos em segundo plano em computadores remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: fb2270ea5c0acdcf2c506e687787d22c73e2cb2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196056"
---
# <a name="about-remote-jobs"></a>Sobre trabalhos remotos

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como executar trabalhos em segundo plano em computadores remotos.

## <a name="detailed-description"></a>DESCRIÇÃO DETALHADA

Um trabalho em segundo plano é um comando que é executado de forma assíncrona sem interagir com a sessão atual. O prompt de comando retorna imediatamente e você pode continuar a usar a sessão enquanto o trabalho é executado.

Por padrão, os trabalhos em segundo plano são executados no computador local. No entanto, você pode usar vários procedimentos diferentes para executar trabalhos em segundo plano em computadores remotos.

Este tópico explica como executar um trabalho em segundo plano em um computador remoto. Para obter informações sobre como executar trabalhos em segundo plano em um computador local, consulte [about_Jobs](about_Jobs.md). Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Job_Details](about_Job_Details.md).

## <a name="remote-background-jobs"></a>TRABALHOS EM SEGUNDO PLANO REMOTOS

Você pode executar trabalhos em segundo plano em computadores remotos usando três métodos diferentes.

- Inicie uma sessão interativa com um computador remoto e inicie um trabalho na sessão interativa. Os procedimentos são os mesmos que executar um trabalho local, embora todas as ações sejam executadas no computador remoto.

- Execute um trabalho em segundo plano em um computador remoto que retorna seus resultados para o computador local. Use esse método quando desejar coletar os resultados de trabalhos em segundo plano e mantê-los em um local central no computador local.

- Execute um trabalho em segundo plano em um computador remoto que mantém seus resultados no computador remoto. Use esse método quando os dados do trabalho forem mantidos com mais segurança no computador de origem.

### <a name="start-a-background-job-in-an-interactive-session"></a>INICIAR UM TRABALHO EM SEGUNDO PLANO EM UMA SESSÃO INTERATIVA

Você pode iniciar uma sessão interativa com um computador remoto e iniciar um trabalho em segundo plano durante a sessão interativa. Para obter mais informações sobre sessões interativas, consulte about_Remote e consulte Enter-PSSession.

O procedimento para iniciar um trabalho em segundo plano em uma sessão interativa é quase idêntico ao procedimento para iniciar um trabalho em segundo plano no computador local. No entanto, todas as operações ocorrem no computador remoto, não no computador local.

#### <a name="step-1-enter-pssession"></a>ETAPA 1: ENTER-PSSESSION

Use o cmdlet Enter-PSSession para iniciar uma sessão interativa com um computador remoto. Você pode usar o parâmetro ComputerName de Enter-PSSession para estabelecer uma conexão temporária para a sessão interativa. Ou, você pode usar o parâmetro Session para executar a sessão interativa em uma sessão do PowerShell (PSSession).

O comando a seguir inicia uma sessão interativa no computador Server01.

```powershell
C:\PS> Enter-PSSession -computername Server01
```

O prompt de comando é alterado para mostrar que agora você está conectado ao computador Server01.

```
Server01\C:>
```

#### <a name="step-2-start-job"></a>ETAPA 2: INICIAR-TRABALHO

Para iniciar um trabalho em segundo plano na sessão, use o cmdlet Start-Job.

O comando a seguir executa um trabalho em segundo plano que obtém os eventos no log de eventos do Windows PowerShell no computador Server01. O cmdlet Start-Job retorna um objeto que representa o trabalho.

Esse comando salva o objeto de trabalho na \$ variável de trabalho.

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

Enquanto o trabalho é executado, você pode usar a sessão interativa para executar outros comandos, incluindo outros trabalhos em segundo plano. No entanto, você deve manter a sessão interativa aberta até que o trabalho seja concluído. Se você encerrar a sessão, o trabalho será interrompido e os resultados serão perdidos.

#### <a name="step-3-get-job"></a>ETAPA 3: GET-JOB

Para descobrir se o trabalho foi concluído, exiba o valor da variável de \$ trabalho ou use o cmdlet Get-Job para obter o trabalho. O comando a seguir usa o cmdlet Get-Job para exibir o trabalho.

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

A saída Get-Job mostra que o trabalho está em execução no computador "localhost" porque o trabalho foi iniciado no e está em execução no mesmo computador (neste caso, Server01).

#### <a name="step-4-receive-job"></a>ETAPA 4: RECEBER-TRABALHO

Para obter os resultados do trabalho, use o cmdlet Receive-Job. Você pode exibir os resultados na sessão interativa ou salvá-los em um arquivo no computador remoto. O comando a seguir obtém os resultados do trabalho na variável $job. O comando usa o operador de redirecionamento (>) para salvar os resultados do trabalho no arquivo de PsLog.txt no computador Server01.

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a>ETAPA 5: SAIR-PSSESSION

Para encerrar a sessão interativa, use o cmdlet Exit-PSSession. O prompt de comando é alterado para mostrar que você está de volta na sessão original no computador local.

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a>ETAPA 6: INVOKE-COMMAND: GET-CONTENT

Para exibir o conteúdo do arquivo de PsLog.txt no computador Server01 a qualquer momento, inicie outra sessão interativa ou execute um comando remoto. Esse tipo de comando é melhor executado em uma PSSession (uma conexão persistente), caso você queira usar vários comandos para investigar e gerenciar os dados no arquivo de PsLog.txt. Para obter mais informações sobre PSSessions, consulte about_PSSessions.

Os comandos a seguir usam o cmdlet New-PSSession para criar uma PSSession que está conectada ao computador Server01 e usam o cmdlet Invoke-Command para executar um comando Get-Content na PSSession para exibir o conteúdo do arquivo.

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>INICIAR um trabalho remoto que retorna os resultados para o computador LOCAL \( AsJob\)

Para iniciar um trabalho em segundo plano em um computador remoto que retorna os resultados do comando para o computador local, use o parâmetro AsJob de um cmdlet, como o cmdlet Invoke-Command.

Quando você usa o parâmetro AsJob, o objeto de trabalho é realmente criado no computador local, mesmo que o trabalho seja executado no computador remoto. Quando o trabalho é concluído, os resultados são retornados para o computador local.

Você pode usar os cmdlets que contêm o substantivo do trabalho (os cmdlets de trabalho) para gerenciar qualquer trabalho criado por qualquer cmdlet. Muitos dos cmdlets que têm parâmetros AsJob não usam a comunicação remota do PowerShell, para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota e que não atendem aos requisitos de comunicação remota.

#### <a name="step-1-invoke-command--asjob"></a>ETAPA 1: INVOKE-COMMAND-ASJOB

O comando a seguir usa o parâmetro AsJob de Invoke-Command para iniciar um trabalho em segundo plano no computador Server01. O trabalho executa um comando Get-Eventlog que obtém os eventos no log do sistema. Você pode usar o parâmetro JobName para atribuir um nome de exibição ao trabalho.

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

Os resultados do comando se assemelham à saída de exemplo a seguir.

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

Quando o parâmetro AsJob é usado, Invoke-Command retorna o mesmo tipo de objeto de trabalho que Start-Job retorna. Você pode salvar o objeto de trabalho em uma variável ou pode usar um comando Get-Job para obter o trabalho.

Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador Server01.

#### <a name="step-2-get-job"></a>ETAPA 2: GET-JOB

Para gerenciar um trabalho iniciado usando o parâmetro AsJob do cmdlet Invoke-Command, use os cmdlets de trabalho. Como o objeto de trabalho que representa o trabalho remoto está no computador local, não é necessário executar comandos remotos para gerenciar o trabalho.

Para determinar se o trabalho está concluído, use um comando Get-Job. O comando a seguir obtém todos os trabalhos que foram iniciados na sessão atual.

```powershell
get-job
```

Como o trabalho remoto foi iniciado na sessão atual, um comando Get-Job local Obtém o trabalho. A propriedade State do objeto Job mostra que o comando foi concluído com êxito.

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a>ETAPA 3: RECEBER-TRABALHO

Para obter os resultados do trabalho, use o cmdlet Receive-Job. Como os resultados do trabalho são retornados automaticamente para o computador em que o objeto de trabalho reside, você pode obter os resultados com um comando de Receive-Job local.

O comando a seguir usa o cmdlet Receive-Job para obter os resultados do trabalho. Ele usa a ID de sessão para identificar o trabalho. Esse comando salva os resultados do trabalho na variável $results. Você também pode redirecionar os resultados para um arquivo.

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>INICIAR UM TRABALHO REMOTO QUE MANTÉM OS RESULTADOS NO COMPUTADOR REMOTO

Para iniciar um trabalho em segundo plano em um computador remoto que mantém os resultados do comando no computador remoto, use o cmdlet Invoke-Command para executar um comando Start-Job em um computador remoto. Você pode usar esse método para executar trabalhos em segundo plano em vários computadores.

Quando você executa um comando Start-Job remotamente, o objeto de trabalho é criado no computador remoto e os resultados do trabalho são mantidos no computador remoto.
Da perspectiva do trabalho, todas as operações são locais. Você está apenas executando comandos remotamente para gerenciar um trabalho local no computador remoto.

#### <a name="step-1-invoke-command-start-job"></a>ETAPA 1: INVOKE-COMANDO START-JOB

Use o cmdlet Invoke-Command para executar um comando Start-Job em um computador remoto.

Esse comando requer uma PSSession (uma conexão persistente). Se você usar o parâmetro ComputerName de Invoke-Command para estabelecer uma conexão temporária, o comando Invoke-Command será considerado como concluído quando o objeto de trabalho for retornado. Como resultado, a conexão temporária é fechada e o trabalho é cancelado.

O comando a seguir usa o cmdlet New-PSSession para criar uma PSSession que está conectada ao computador Server01. O comando salva a PSSession na \$ variável s.

```powershell
$s = new-pssession -computername Server01
```

O comando a seguir usa o cmdlet Invoke-Command para executar um comando Start-Job na PSSession. O comando Start-Job e o comando Get-Eventlog são colocados entre chaves.

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

Os resultados se assemelham à saída de exemplo a seguir.

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

Quando você executa um comando Start-Job remotamente, Invoke-Command retorna o mesmo tipo de objeto de trabalho que Start-Job retorna. Você pode salvar o objeto de trabalho em uma variável ou pode usar um comando Get-Job para obter o trabalho.

Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador local, conhecido como "LocalHost", embora o trabalho tenha sido executado no computador Server01. Como o objeto de trabalho é criado no computador Server01 e o trabalho é executado no mesmo computador, é considerado um trabalho em segundo plano local.

#### <a name="step-2-invoke-command-get-job"></a>ETAPA 2: INVOKE-COMMAND GET-JOB

Para gerenciar um trabalho de segundo plano remoto, use os cmdlets de trabalho. Como o objeto de trabalho está no computador remoto, você precisa executar comandos remotos para obter, parar, aguardar ou recuperar os resultados do trabalho.

Para ver se o trabalho está concluído, use um comando Invoke-Command para executar um comando Get-Job na PSSession que está conectada ao computador Server01.

```powershell
invoke-command -session $s -scriptblock {get-job}
```

O comando retorna um objeto de trabalho. A propriedade State do objeto Job mostra que o comando foi concluído com êxito.

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a>ETAPA 3: INVOKE-COMANDO RECEIVE-JOB

Para obter os resultados do trabalho, use o cmdlet Invoke-Command para executar um comando Receive-Job na PSSession que está conectada ao computador Server01.

O comando a seguir usa o cmdlet Receive-Job para obter os resultados do trabalho. Ele usa a ID de sessão para identificar o trabalho. Esse comando salva os resultados do trabalho na \$ variável Results. Ele usa o parâmetro Keep de Receive-Job para manter o resultado no cache do trabalho no computador remoto.

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

Você também pode redirecionar os resultados para um arquivo no computador local ou remoto.
O comando a seguir usa um operador de redirecionamento para salvar os resultados em um arquivo no computador Server01.

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Jobs](about_Jobs.md)

[about_Job_Details](about_Job_Details.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)

[Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)

[Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)

[Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)

[Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

