---
description: Descreve como executar trabalhos em computadores remotos.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 93e1d3aba1f4037cc3c5c18386488bf321fc2a64
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598613"
---
# <a name="about-remote-jobs"></a>Sobre trabalhos remotos

## <a name="short-description"></a>Descrição breve
Descreve como executar trabalhos em segundo plano em computadores remotos.

## <a name="detailed-description"></a>Descrição detalhada

O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos. Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.

- `RemoteJob` -Comandos e scripts executados em uma sessão remota.
- `BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local. Para obter mais informações, consulte [about_Jobs](about_Jobs.md).
- `PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local. Para obter mais informações, consulte [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).

Executar scripts remotamente, em um computador separado ou em um processo separado, proporcionar um grande isolamento. Os erros que ocorrem no trabalho remoto não afetam outros trabalhos em execução ou a sessão pai que iniciou o trabalho. No entanto, a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto. Todos os objetos são serializados e desserializados à medida que são passados entre a sessão pai e a sessão remota (trabalho). A serialização de grandes objetos de dados complexos pode consumir grandes quantidades de recursos de computação e memória e transferir grandes quantidades de dados pela rede.

> [!IMPORTANT]
> A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline. O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído. Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.

Há duas maneiras de solucionar essa situação:

1. Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas. Consulte a seção [processos desanexados](#how-to-run-as-a-detached-process) deste artigo.
1. Use `Start-Process` para criar um novo processo em vez de um trabalho. Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

## <a name="remote-jobs"></a>Trabalhos remotos

Você pode executar trabalhos em computadores remotos usando três métodos diferentes.

- Iniciar uma sessão interativa em um computador remoto. Em seguida, inicie um trabalho na sessão interativa. Os procedimentos são os mesmos que executar um trabalho local, embora todas as ações sejam executadas no computador remoto.

- Execute um trabalho em um computador remoto que retorna seus resultados para o computador local. Use esse método quando desejar coletar os resultados dos trabalhos e mantê-los em um local central no computador local.

- Execute um trabalho em um computador remoto que mantém seus resultados no computador remoto. Use esse método quando os dados do trabalho forem mantidos com mais segurança no computador de origem.

### <a name="start-a-job-in-an-interactive-session"></a>Iniciar um trabalho em uma sessão interativa

Você pode iniciar uma sessão interativa com um computador remoto e, em seguida, iniciar um trabalho durante a sessão interativa. Para obter mais informações sobre sessões interativas, consulte about_Remote e ver `Enter-PSSession` .

O procedimento para iniciar um trabalho em uma sessão interativa é quase idêntico ao procedimento para iniciar um trabalho em segundo plano no computador local. No entanto, todas as operações ocorrem no computador remoto, não no computador local.

1. Use o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com um computador remoto. Você pode usar o parâmetro ComputerName do `Enter-PSSession` para estabelecer uma conexão temporária para a sessão interativa. Ou, você pode usar o parâmetro Session para executar a sessão interativa em uma sessão do PowerShell (PSSession).

   O comando a seguir inicia uma sessão interativa no computador Server01.

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   O prompt de comando é alterado para mostrar que agora você está conectado ao computador Server01.

   ```
   Server01\C:>
   ```

1. Para iniciar um trabalho remoto na sessão, use o `Start-Job` cmdlet. O comando a seguir executa um trabalho remoto que obtém os eventos no log de eventos do Windows PowerShell no computador Server01. O `Start-Job` cmdlet retorna um objeto que representa o trabalho.

   Esse comando salva o objeto de trabalho na `$job` variável.

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   Enquanto o trabalho é executado, você pode usar a sessão interativa para executar outros comandos, incluindo outros trabalhos. No entanto, você deve manter a sessão interativa aberta até que o trabalho seja concluído. Se você encerrar a sessão, o trabalho será interrompido e os resultados serão perdidos.

1. Para descobrir se o trabalho foi concluído, exiba o valor da `$job` variável ou use o `Get-Job` cmdlet para obter o trabalho. O comando a seguir usa o `Get-Job` cmdlet para exibir o trabalho.

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   A `Get-Job` saída mostra que o trabalho está em execução no computador "localhost" porque o trabalho foi iniciado no e está em execução no mesmo computador (nesse caso, Server01).

1. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet. Você pode exibir os resultados na sessão interativa ou salvá-los em um arquivo no computador remoto. O comando a seguir obtém os resultados do trabalho na variável $job. O comando usa o operador de redirecionamento ( `>` ) para salvar os resultados do trabalho no arquivo de PsLog.txt no computador Server01.

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. Para encerrar a sessão interativa, use o `Exit-PSSession` cmdlet. O prompt de comando é alterado para mostrar que você está de volta na sessão original no computador local.

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. Para exibir o conteúdo do `PsLog.txt` arquivo no computador Server01 a qualquer momento, inicie outra sessão interativa ou execute um comando remoto. Esse tipo de comando é melhor executado em uma PSSession (uma conexão persistente), caso você queira usar vários comandos para investigar e gerenciar os dados no `PsLog.txt` arquivo. Para obter mais informações sobre PSSessions, consulte [about_PSSessions](about_PSSessions.md).

   Os comandos a seguir usam o `New-PSSession` cmdlet para criar uma **PSSession** que está conectada ao computador Server01 e usam o `Invoke-Command` cmdlet para executar um `Get-Content` comando na PSSession para exibir o conteúdo do arquivo.

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>Iniciar um trabalho remoto que retorna os resultados para o computador local (AsJob)

Para iniciar um trabalho em um computador remoto que retorna os resultados do comando para o computador local, use o parâmetro **AsJob** de um cmdlet, como o `Invoke-Command` cmdlet.

Quando você usa o parâmetro **AsJob** , o objeto de trabalho é realmente criado no computador local, mesmo que o trabalho seja executado no computador remoto. Quando o trabalho é concluído, os resultados são retornados para o computador local.

Você pode usar os cmdlets que contêm o substantivo do trabalho (os cmdlets de trabalho) para gerenciar qualquer trabalho criado por qualquer cmdlet. Muitos dos cmdlets que têm parâmetros **AsJob** não usam a comunicação remota do PowerShell, para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota e que não atendem aos requisitos de comunicação remota.

1. O comando a seguir usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho no computador Server01. O trabalho executa um `Get-Eventlog` comando que obtém os eventos no log do sistema. Você pode usar o parâmetro JobName para atribuir um nome de exibição ao trabalho.

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   Os resultados do comando se assemelham à saída de exemplo a seguir.

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   Quando o parâmetro **AsJob** é usado, `Invoke-Command` retorna o mesmo tipo de objeto de trabalho que `Start-Job` retorna. Você pode salvar o objeto de trabalho em uma variável ou pode usar um `Get-Job` comando para obter o trabalho.

   Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador Server01.

1. Para gerenciar um trabalho iniciado usando o parâmetro **AsJob** do `Invoke-Command` cmdlet, use os cmdlets de trabalho. Como o objeto de trabalho que representa o trabalho remoto está no computador local, não é necessário executar comandos remotos para gerenciar o trabalho.

   Para determinar se o trabalho está concluído, use um `Get-Job` comando. O comando a seguir obtém todos os trabalhos que foram iniciados na sessão atual.

   ```powershell
   Get-Job
   ```

   Como o trabalho remoto foi iniciado na sessão atual, um comando local `Get-Job` Obtém o trabalho. A propriedade State do objeto Job mostra que o comando foi concluído com êxito.

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet. Como os resultados do trabalho são retornados automaticamente para o computador em que o objeto de trabalho reside, você pode obter os resultados com um `Receive-Job` comando local.

   O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho. Ele usa a ID de sessão para identificar o trabalho. Esse comando salva os resultados do trabalho na variável $results. Você também pode redirecionar os resultados para um arquivo.

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>Iniciar um trabalho remoto que mantém os resultados no computador remoto

Para iniciar um trabalho em um computador remoto que mantém os resultados do comando no computador remoto, use o `Invoke-Command` cmdlet para executar um `Start-Job` comando em um computador remoto. Você pode usar esse método para executar trabalhos em vários computadores.

Quando você executa um `Start-Job` comando remotamente, o objeto de trabalho é criado no computador remoto e os resultados do trabalho são mantidos no computador remoto.
Da perspectiva do trabalho, todas as operações são locais. Você está apenas executando comandos remotamente para gerenciar um trabalho local no computador remoto.

1. Use o `Invoke-Command` cmdlet para executar um `Start-Job` comando em um computador remoto.

   Esse comando requer uma PSSession (uma conexão persistente). Se você usar o parâmetro ComputerName de `Invoke-Command` para estabelecer uma conexão temporária, o `Invoke-Command` comando será considerado como concluído quando o objeto de trabalho for retornado. Como resultado, a conexão temporária é fechada e o trabalho é cancelado.

   O comando a seguir usa o `New-PSSession` cmdlet para criar uma PSSession que está conectada ao computador Server01. O comando salva a PSSession na `$s` variável.

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   O comando a seguir usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando na PSSession. O `Start-Job` comando e o `Get-Eventlog` comando são colocados entre chaves.

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   Os resultados se assemelham à saída de exemplo a seguir.

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   Quando você executa um `Start-Job` comando remotamente, `Invoke-Command` o retorna o mesmo tipo de objeto de trabalho que o `Start-Job` retorna. Você pode salvar o objeto de trabalho em uma variável ou pode usar um `Get-Job` comando para obter o trabalho.

   Observe que o valor da propriedade **Location** mostra que o trabalho foi executado no computador local, conhecido como "localhost", embora o trabalho tenha sido executado no computador Server01. Como o objeto de trabalho é criado no computador Server01 e o trabalho é executado no mesmo computador, é considerado um trabalho em segundo plano local.

1. Para gerenciar um trabalho remoto, use os cmdlets de **trabalho** . Como o objeto de trabalho está no computador remoto, você precisa executar comandos remotos para obter, parar, aguardar ou recuperar os resultados do trabalho.

   Para ver se o trabalho está concluído, use um `Invoke-Command` comando para executar um `Get-Job` comando na PSSession que está conectada ao computador Server01.

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   O comando retorna um objeto de trabalho. A propriedade **State** do objeto Job mostra que o comando foi concluído com êxito.

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. Para obter os resultados do trabalho, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na PSSession que está conectada ao computador Server01.

   O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho. Ele usa a ID de sessão para identificar o trabalho. Esse comando salva os resultados do trabalho na `$results` variável. Ele usa o parâmetro Keep de `Receive-Job` para manter o resultado no cache do trabalho no computador remoto.

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   Você também pode redirecionar os resultados para um arquivo no computador local ou remoto.
   O comando a seguir usa um operador de redirecionamento para salvar os resultados em um arquivo no computador Server01.

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a>Como executar como um processo desanexado

Como mencionado anteriormente, quando a sessão pai é encerrada, todos os trabalhos filho em execução são encerrados junto com seus processos filhos. Você pode usar a comunicação remota no computador local para executar trabalhos que não estão anexados à sessão atual do PowerShell.

Crie uma nova sessão do PowerShell no computador local. O uso `Invoke-Command` para iniciar um trabalho nesta sessão. `Invoke-Command` permite que você desconecte uma sessão remota e encerre a sessão pai. Posteriormente, você pode iniciar uma nova sessão do PowerShell e conectar-se à sessão desconectada anteriormente para retomar o monitoramento do trabalho. No entanto, todos os dados retornados para a sessão original do PowerShell são perdidos quando essa sessão é encerrada. Somente novos objetos de dados gerados após a desconexão são retornados quando reconectados.

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

Para este exemplo, os trabalhos ainda estão anexados a uma sessão pai do PowerShell.
No entanto, a sessão pai não é a sessão do PowerShell original em que `Invoke-Command` foi executada.

## <a name="see-also"></a>Consulte também

- [about_Jobs](about_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_Remote_Variables](about_Remote_Variables.md)
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
- [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
- [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
