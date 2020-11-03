---
description: Explica como criar e gerenciar trabalhos agendados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195816"
---
# <a name="about-scheduled-jobs-basics"></a>Sobre noções básicas de trabalhos agendados

## <a name="short-description"></a>Descrição breve

Explica como criar e gerenciar trabalhos agendados.

## <a name="long-description"></a>Descrição longa

Este documento mostra como executar tarefas básicas de criação e gerenciamento de trabalhos agendados. Para obter informações sobre tarefas mais avançadas, consulte [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).

Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).

## <a name="how-to-create-a-scheduled-job"></a>Como criar um trabalho agendado

Para criar um trabalho agendado, use o `Register-ScheduledJob` cmdlet. O cmdlet requer um nome e os comandos ou o script que o trabalho executa. Você pode executar o trabalho imediatamente adicionando o parâmetro **RunNow** ou criar um gatilho de trabalho e definir opções de trabalho ao criar o trabalho ou editar um trabalho existente.

Para criar um trabalho que executa um script, use o parâmetro **FilePath** para especificar o caminho para o arquivo de script. Para criar um trabalho que executa comandos, use o parâmetro **scriptblock** .

O `Register-ScheduledJob` cmdlet cria o **ProcessJob** , que executa um `Get-Process` comando. Este trabalho agendado tem as opções de trabalho padrão e nenhum gatilho de trabalho.

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a>Como criar um gatilho de trabalho

Os gatilhos de trabalho iniciam automaticamente um trabalho agendado. Um gatilho de trabalho pode ser agendamento único ou recorrente ou um evento, como quando um usuário faz logon ou o Windows é iniciado. Cada trabalho pode ter zero, um ou vários gatilhos de trabalho.

Para criar um gatilho de trabalho, use o `New-JobTrigger` cmdlet. O comando a seguir cria um gatilho de trabalho que inicia um trabalho todas as segundas e quintas-feiras às 5:00.
O comando salva o gatilho de trabalho na `$T` variável.

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

Disparadores de trabalho são opcionais. Você pode iniciar um trabalho agendado a qualquer momento adicionando o parâmetro **RunNow** ao `Register-ScheduledJob` comando ou usando os `Start-Job` cmdlets.

## <a name="how-to-add-a-job-trigger"></a>Como adicionar um gatilho de trabalho

Quando você adiciona um gatilho de trabalho a um trabalho agendado, o gatilho de trabalho é adicionado ao arquivo XML de trabalho agendado para o trabalho agendado e torna-se parte do trabalho agendado.

Você pode adicionar um gatilho de trabalho a um trabalho agendado ao criar o trabalho agendado ou editar um trabalho existente. Você pode alterar o gatilho de trabalho de um trabalho agendado a qualquer momento.

O PowerShell usa alguns dos mesmos gatilhos de trabalho que Agendador de Tarefas usa. Para obter informações detalhadas sobre gatilhos de trabalho, consulte o tópico de ajuda para o cmdlet [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) .

O exemplo a seguir usa nivelamento para criar `$JobParms` que são valores de parâmetro que são passados para o `Register-ScheduledJob` cmdlet. Para obter mais informações, consulte [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
O `Register-ScheduledJob` usa `@JobParms` para criar um trabalho agendado. Ele usa o parâmetro **Trigger** para especificar o gatilho do trabalho na `$T` variável.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

Você também pode adicionar um gatilho de trabalho a um trabalho agendado existente a qualquer momento. O `Add-JobTrigger` cmdlet adiciona o gatilho de trabalho na `$T` variável ao trabalho agendado **ProcessJob** .

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

Como resultado, o gatilho de trabalho inicia o **ProcessJob** automaticamente todas as segundas e quintas-feiras às 5:00.

## <a name="how-to-get-a-job-trigger"></a>Como obter um gatilho de trabalho

Para obter o gatilho de trabalho de um trabalho agendado, use o `Get-JobTrigger` cmdlet. Use os parâmetros **Name** , **ID** e **InputObject** para especificar o trabalho agendado, não o gatilho do trabalho.

`Get-JobTrigger` Obtém o gatilho de trabalho do **ProcessJob** .

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a>Como criar opções de trabalho

As opções de trabalho estabelecem condições para iniciar e executar o trabalho. Cada trabalho tem as opções de trabalho padrão, a menos que você as altere. Como as opções de trabalho podem impedir que um trabalho seja executado no horário agendado, é importante entender as opções de trabalho e usá-las com cuidado.

O PowerShell usa as mesmas opções de trabalho que o Agendador de Tarefas usa. Para obter informações detalhadas sobre as opções de trabalho, consulte o tópico da ajuda para [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).

As opções de trabalho são armazenadas no arquivo XML de trabalho agendado. Você pode definir opções de trabalho ao criar um trabalho agendado ou alterá-los a qualquer momento.

O `New-ScheduledJobOption` cmdlet cria uma opção de trabalho agendado na qual a opção de trabalho agendado **WakeToRun** é definida como true. A opção **WakeToRun** executa o trabalho agendado mesmo que o computador esteja no estado de suspensão ou hibernação na hora de início agendada. O comando salva as opções de trabalho na `$O` variável.

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a>Como obter opções de trabalho

Para obter as opções de trabalho de um trabalho agendado, use o `Get-ScheduledJobOption` cmdlet. Use os parâmetros **Name** , **ID** e **InputObject** para especificar o trabalho agendado, não as opções de trabalho.

`Get-ScheduledJobOption` Obtém as opções de trabalho do **ProcessJob** .

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a>Como alterar as opções de trabalho

Você pode alterar as opções de trabalho de um trabalho agendado ao criar um trabalho agendado ou editar um trabalho existente.

Os splatted `$JobParms` são passados para o `Add-JobTrigger` cmdlet para criar o trabalho de processo. Ele usa o parâmetro **ScheduledJobOption** para especificar as opções de trabalho na `$O` variável.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

Você também pode alterar as opções de trabalho para um trabalho agendado existente a qualquer momento.
O comando a seguir usa o `Set-ScheduledJobOption` cmdlet para alterar o valor da opção **WakeToRun** de **ProcessJob** scheduledJob para **true** .

Os `Set` cmdlets no módulo **PSScheduledJob** , como o `Set-ScheduledJobOption` cmdlet, não têm parâmetros **Name** ou **ID** . Você pode usar o parâmetro **InputObject** para especificar as opções de trabalho agendado ou canalizar um trabalho agendado de um `Get-ScheduledJobOption` cmdlet para `Set-ScheduledJobOption` .

Este exemplo usa o `Get-ScheduledJob` cmdlet para obter o ProcessJob. Ele usa o `Get-ScheduledJobOption` cmdlet para obter as opções de trabalho no **ProcessJob** e o `Set-ScheduledJobOption` cmdlet para alterar a opção de trabalho **WakeToRun** no ProcessJob para true.

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a>Como obter instâncias de trabalho agendadas

Quando um trabalho agendado é iniciado, o PowerShell cria uma instância de trabalho semelhante a um trabalho em segundo plano padrão do PowerShell. Você pode usar os cmdlets de trabalho, como `Get-Job` `Stop-Job` e `Receive-Job` para gerenciar as instâncias de trabalho.

> [!NOTE]
> Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão. Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .

Para obter todas as instâncias de trabalhos agendados do PowerShell e todos os trabalhos padrão ativos, use o `Get-Job` cmdlet. O `Import-Module` cmdlet importa o módulo **PSScheduledJob** e `Get-Job` Obtém os trabalhos no computador local.

```powershell
Import-Module PSScheduledJob
Get-Job
```

`Get-Job` Obtém as instâncias de **ProcessJob** no computador local.

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

A exibição padrão não mostra a hora de início, que normalmente distingue instâncias do mesmo trabalho agendado.

O `Get-Job` cmdlet envia objetos por meio do pipeline. O `Format-Table` cmdlet exibe as propriedades **Name** , **ID** e **BeginTime** do trabalho agendado.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
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

## <a name="get-scheduled-job-results"></a>Obter resultados do trabalho agendado

Para obter os resultados de uma instância de um trabalho agendado, use o `Receive-Job` cmdlet.

> [!NOTE]
> Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão. Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .

Este exemplo obtém os resultados da instância mais recente do trabalho agendado **ProcessJob** (ID = 51).

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

Os resultados de trabalhos agendados são salvos em disco, portanto, o parâmetro **Keep** de `Receive-Job` não é necessário. No entanto, sem o parâmetro **Keep** , você pode obter os resultados de um trabalho agendado apenas uma vez em cada sessão do PowerShell. Para iniciar uma nova sessão do PowerShell, digite `PowerShell` ou abra uma nova janela do PowerShell.

## <a name="see-also"></a>Confira também

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)

[Agendador de Tarefas](/windows/desktop/TaskSchd/task-scheduler-reference)
