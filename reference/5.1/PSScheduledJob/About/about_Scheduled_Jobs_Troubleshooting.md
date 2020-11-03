---
description: Explica como resolver problemas com trabalhos agendados
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Troubleshooting
ms.openlocfilehash: 924205edb9d44724cfef201d84baa304ecde67ad
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195814"
---
# <a name="about-scheduled-jobs-troubleshooting"></a>Sobre a solução de problemas de trabalhos agendados

## <a name="short-description"></a>Descrição breve

Explica como resolver problemas com trabalhos agendados

## <a name="long-description"></a>Descrição longa

Este documento descreve alguns dos problemas que você pode enfrentar ao usar os recursos de trabalho agendado do PowerShell e ele sugere soluções para esses problemas.

Antes de usar os trabalhos agendados do PowerShell, consulte [about_Scheduled_Jobs](about_Scheduled_Jobs.md) e os trabalhos agendados relacionados sobre tópicos.

Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).

## <a name="cant-find-job-results"></a>Não é possível localizar os resultados do trabalho

### <a name="basic-method-for-getting-job-results-in-powershell"></a>Método básico para obter resultados de trabalho no PowerShell

Quando um trabalho agendado é executado, ele cria uma instância do trabalho agendado. Para exibir, gerenciar e obter os resultados das instâncias de trabalho agendadas, use os cmdlets de trabalho.

> [!NOTE]
> Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão. Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .

Para obter uma lista de todas as instâncias de um trabalho agendado, use o `Get-Job` cmdlet.

```powershell
Import-Module PSScheduledJob
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State         HasMoreData     Location
--     ----         -------------   -----         -----------     --------
43     ProcessJob   PSScheduledJob  Completed     False           localhost
44     ProcessJob   PSScheduledJob  Completed     False           localhost
45     ProcessJob   PSScheduledJob  Completed     False           localhost
46     ProcessJob   PSScheduledJob  Completed     False           localhost
47     ProcessJob   PSScheduledJob  Completed     False           localhost
48     ProcessJob   PSScheduledJob  Completed     False           localhost
49     ProcessJob   PSScheduledJob  Completed     False           localhost
50     ProcessJob   PSScheduledJob  Completed     False           localhost
```

O `Get-Job` cmdlet envia objetos **ProcessJob** para baixo do pipeline. O `Format-Table` cmdlet exibe as propriedades **Name** , **ID** e **PSBeginTime** de uma instância de trabalho agendada em uma tabela.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, PSBeginTime -Auto
```

```Output
Name       Id PSBeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

Para obter os resultados de uma instância de um trabalho agendado, use o `Receive-Job` cmdlet. O comando a seguir obtém os resultados da instância mais recente do ProcessJob (ID = 50).

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a>Método básico para localizar resultados de trabalho em disco

Para gerenciar trabalhos agendados, use os cmdlets de trabalho, como `Get-Job` e `Receive-Job` .

Se o não `Get-Job` obtiver a instância de trabalho ou não `Receive-Job` obtiver os resultados do trabalho, você poderá pesquisar os arquivos de histórico de execução do trabalho em disco.
O histórico de execução contém um registro de todas as instâncias de trabalho disparadas.

Verifique se há um diretório nomeado com carimbo de data/hora no diretório para um trabalho agendado no seguinte caminho:

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Por exemplo:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Por exemplo, o `Get-ChildItem` cmdlet obtém o histórico de execução em disco do trabalho agendado do **ProcessJob** .

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

Cada diretório nomeado por carimbo de data/hora representa uma instância de trabalho. Os resultados de cada instância de trabalho são salvos em um arquivo de **Results.xml** no diretório nomeado por carimbo de data/hora.

Por exemplo, o comando a seguir obtém os arquivos de **Results.xml** para cada instância salva do trabalho agendado **ProcessJob** . Se o arquivo de **Results.xml** estiver ausente, o PowerShell não poderá retornar ou exibir os resultados do trabalho.

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

O cmdlet Job pode não ser capaz de obter instâncias de trabalho agendadas ou seus resultados porque o módulo **PSScheduledJob** não é importado para a sessão.

> [!NOTE]
> Antes de usar um cmdlet de trabalho em instâncias de trabalho agendadas, verifique se o módulo **PSScheduledJob** está incluído na sessão. Sem o módulo **PSScheduledJob** , os cmdlets de trabalho não podem obter instâncias de trabalho agendadas ou seus resultados.

Para importar o módulo **PSScheduledJob** :

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a>Receive-Job cmdlet já pode ter retornado os resultados

Se o `Receive-Job` não retornar resultados da instância de trabalho, pode ser porque um `Receive-Job` comando foi executado para essa instância de trabalho na sessão atual sem o parâmetro **Keep** .

Quando você usa `Receive-Job` sem o parâmetro **Keep** , `Receive-Job` o retorna os resultados do trabalho e define a propriedade **HasMoreData** da instância do trabalho como **false** . O valor **false** significa que `Receive-Job` retornou os resultados do trabalho e a instância não tem mais resultados a serem retornados. Essa configuração é apropriada para trabalhos em segundo plano padrão, mas não para instâncias de trabalhos agendados, que são salvos em disco.

Para obter os resultados da instância de trabalho novamente, inicie uma nova sessão do PowerShell digitando `PowerShell` . Importe o módulo **PSScheduledJob** e tente o `Receive-Job` comando novamente.

```powershell
Receive-Job -ID 50
```

```Output
#No results
```

```powershell
PowerShell.exe
```

```Output
Windows PowerShell
Copyright (C) 2012 Microsoft Corporation. All rights reserved.
```

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a>Usando o parâmetro Keep para obter resultados mais de uma vez em uma sessão

Para obter o resultado de uma instância de trabalho mais de uma vez em uma sessão, use o parâmetro **Keep** do `Receive-Job` cmdlet.

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

```powershell
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="the-scheduled-job-might-be-corrupted"></a>O trabalho agendado pode estar corrompido

Se um trabalho agendado for corrompido, o PowerShell excluirá o trabalho agendado corrompido e seus resultados. Você não pode recuperar os resultados de um trabalho agendado corrompido.

Para determinar se um trabalho agendado ainda existe, use o `Get-ScheduledJob` cmdlet.

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a>O número de resultados pode ter excedido o ExecutionHistoryLength

A propriedade **ExecutionHistoryLength** de um trabalho agendado determina quantas instâncias de trabalho e seus resultados são salvos em disco. O valor padrão é 32.
Quando o número de instâncias de um trabalho agendado exceder esse valor, o PowerShell excluirá a instância de trabalho mais antiga para liberar espaço para cada nova instância de trabalho.

Para obter o valor da propriedade **ExecutionHistoryLength** de um trabalho agendado, use o seguinte formato de comando:

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

Por exemplo, o comando a seguir obtém o valor da propriedade **ExecutionHistoryLength** do trabalho agendado **ProcessJob** .

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

Para definir ou alterar o valor da propriedade **ExecutionHistoryLength** , use o parâmetro **MaxResultCount** dos `Register-ScheduledJob` `Set-ScheduledJob` cmdlets e.

O comando a seguir aumenta o valor da propriedade **ExecutionHistoryLength** para 50.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a>Os resultados da instância de trabalho podem ter sido excluídos

O parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet exclui o histórico de execução de um trabalho. Você pode usar esse recurso para liberar espaço em disco ou excluir resultados que não são necessários, ou já usados, analisados ou salvos em um local diferente.

Para excluir o histórico de execução de um trabalho agendado, use o parâmetro **ClearExecutionHistory** do trabalho agendado.

O comando a seguir exclui o histórico de execução do trabalho agendado do **ProcessJob** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

Além disso, o `Remove-Job` cmdlet exclui os resultados do trabalho. Quando você usa `Remove-Job` o para excluir um trabalho agendado, ele exclui todas as instâncias do trabalho em disco, incluindo o histórico de execução e todos os resultados do trabalho.

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a>Os trabalhos iniciados usando o cmdlet Start-Job não são salvos em disco

Quando você usa o `Start-Job` para iniciar um trabalho agendado, em vez de usar um gatilho de trabalho, `Start-Job` o inicia um trabalho em segundo plano padrão. O trabalho em segundo plano e seus resultados não são armazenados no histórico de execução do trabalho em disco.

Você pode usar o `Get-Job` cmdlet para obter o trabalho e o `Receive-Job` cmdlet para obter os resultados do trabalho, mas os resultados estarão disponíveis somente até você recebê-los, a menos que você use o parâmetro Keep do `Receive-Job` cmdlet.

Além disso, os trabalhos em segundo plano e seus resultados são específicos da sessão; elas existem somente na sessão em que são criadas. Se você excluir o trabalho com `Remove-Job` , feche a sessão ou feche o PowerShell, a instância de trabalho e seus resultados serão excluídos.

## <a name="scheduled-job-doesnt-run"></a>O trabalho agendado não é executado

Os trabalhos agendados não serão executados automaticamente se o trabalho for disparado ou se o trabalho agendado estiver desabilitado.

Use o `Get-ScheduledJob` cmdlet para obter o trabalho agendado. Verifique se o valor da propriedade **habilitado** do trabalho agendado é **true** .

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command         Enabled
--         ----            --------        -------         -------
4          ProcessJob      {1, 2}          Get-Process     True
```

```powershell
(Get-ScheduledJob ProcessJob).Enabled
```

```Output
True
```

Use o `Get-JobTrigger` cmdlet para obter os gatilhos de trabalho do trabalho agendado.
Verifique se o valor da propriedade **Enabled** do gatilho do trabalho é **true** .

```powershell
Get-ScheduledJob ProcessJob | Get-JobTrigger
```

```Output
Id      Frequency    Time                   DaysOfWeek            Enabled
--      ---------    ----                   ----------            -------
1       Weekly       11/7/2011 5:00:00 AM   {Monday, Thursday}    True
2       Daily        11/7/2011 3:00:00 PM                         True
```

```powershell
Get-ScheduledJob ProcessJob|Get-JobTrigger|Format-Table ID, Enabled -Auto
```

```Output
Id Enabled
-- -------
1    True
2    True
```

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a>Os trabalhos agendados não serão executados automaticamente se os gatilhos de trabalho forem inválidos

Por exemplo, um gatilho de trabalho pode especificar uma data no passado ou uma data que não ocorre, como a quinta segunda-feira do mês.

Os trabalhos agendados não serão executados automaticamente se as condições do gatilho de trabalho ou as opções de trabalho não forem satisfeitas.

Por exemplo, um trabalho agendado que é executado somente quando um usuário específico faz logon no computador não será executado se esse usuário não fizer logon ou se conectar somente remotamente.

Examine as opções do trabalho agendado e verifique se eles estão satisfeitos.
Por exemplo, um trabalho agendado que exige que o computador fique ocioso ou exija uma conexão de rede, ou tem um longo **IdleDuration** ou um breve **IdleTimeout** pode nunca ser executado.

Use o `Get-ScheduledJobOption` cmdlet para examinar as opções de trabalho e seus valores.

```powershell
Get-ScheduledJob -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Para obter descrições das opções de trabalho agendado, consulte [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).

### <a name="the-scheduled-job-instance-might-have-failed"></a>A instância do trabalho agendado pode ter falhado

Se um comando de trabalho agendado falhar, o PowerShell o relatará imediatamente gerando uma mensagem de erro. No entanto, se o trabalho falhar quando Agendador de Tarefas tentar executá-lo, o erro não estará disponível para o PowerShell.

Use os métodos a seguir para detectar e corrigir falhas de trabalho:

Verifique se há erros na Agendador de Tarefas log de eventos. Para verificar o log, use Visualizador de Eventos ou um comando do PowerShell, como o seguinte:

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

Verifique o registro de trabalho em Agendador de Tarefas. Os trabalhos agendados do PowerShell são armazenados na seguinte pasta agendada de tarefas:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a>O trabalho agendado pode não ser executado por causa de permissão insuficiente

Os trabalhos agendados são executados com as permissões do usuário que criou o trabalho ou as permissões do usuário que é especificado pelo parâmetro de **credencial** no `Register-ScheduledJob` `Set-ScheduledJob` comando ou.

Se esse usuário não tiver permissão para executar os comandos ou scripts, o trabalho falhará.

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a>Não é possível obter o trabalho agendado ou o trabalho agendado está corrompido

Em raras ocasiões, os trabalhos agendados podem se tornar corrompidos ou conter contradição internas que não podem ser resolvidas. Normalmente, isso ocorre quando os arquivos XML para o trabalho agendado são editados manualmente, resultando em XML inválido.

Quando um trabalho agendado está corrompido, o PowerShell tenta excluir o trabalho agendado, seu histórico de execução e seus resultados do disco.

Se não for possível remover o trabalho agendado, você receberá uma mensagem de erro de trabalho corrompida toda vez que executar o `Get-ScheduledJob` cmdlet.

Para remover um trabalho agendado corrompido, use um dos seguintes métodos:

Exclua o `<ScheduledJobName>` diretório para o trabalho agendado. Não exclua o diretório **ScheduledJob** .

O local do diretório:

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

Por exemplo:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

Use Agendador de Tarefas para excluir o trabalho agendado. As tarefas agendadas do PowerShell aparecem no seguinte caminho de Agendador de Tarefas:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a>Os cmdlets de trabalho não podem encontrar trabalhos agendados de forma consistente

Quando o módulo **PSScheduledJob** não está na sessão atual, os cmdlets de trabalho não podem obter trabalhos agendados, iniciá-los ou obter seus resultados.

Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou execute ou obtenha qualquer cmdlet no módulo, como o `Get-ScheduledJob` cmdlet.
A partir do PowerShell 3,0, os módulos são importados automaticamente quando você obtém ou usa qualquer cmdlet no módulo.

Quando o módulo **PSScheduledJob** não está na sessão atual, a sequência de comandos a seguir é possível.

```powershell
Get-Job ProcessJob
```

```Output
Get-Job : The command cannot find the job because the job name
ProcessJob was not found.
Verify the value of the Name parameter, and then try the command again.
+ CategoryInfo          : ObjectNotFound: (ProcessJob:String) [Get-Job],
PSArgumentException
+ FullyQualifiedErrorId : JobWithSpecifiedNameNotFound,Microsoft.PowerShell.
Commands.GetJobCommand
```

```powershell
Get-Job
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command      Enabled
--         ----            --------        -------      -------
4          ProcessJob      {1}             Get-Process  True
```

```powershell
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State       HasMoreData     Location
--     ----         -------------   -----       -----------     --------
43     ProcessJob   PSScheduledJob  Completed   True            localhost
44     ProcessJob   PSScheduledJob  Completed   True            localhost
45     ProcessJob   PSScheduledJob  Completed   True            localhost
46     ProcessJob   PSScheduledJob  Completed   True            localhost
47     ProcessJob   PSScheduledJob  Completed   True            localhost
48     ProcessJob   PSScheduledJob  Completed   True            localhost
49     ProcessJob   PSScheduledJob  Completed   True            localhost
50     ProcessJob   PSScheduledJob  Completed   True            localhost
```

Esse comportamento ocorre porque o `Get-ScheduledJob` comando importa automaticamente o módulo **PSScheduledJob** e executa o comando.

## <a name="see-also"></a>Confira também

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)

[Agendador de Tarefas](/windows/desktop/TaskSchd/task-scheduler-reference)
