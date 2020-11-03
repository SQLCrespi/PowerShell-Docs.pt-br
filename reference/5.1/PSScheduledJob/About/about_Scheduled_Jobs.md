---
description: Descreve os trabalhos agendados e explica como usar e gerenciar trabalhos agendados no PowerShell e no Agendador de Tarefas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195819"
---
# <a name="about-scheduled-jobs"></a>Sobre os trabalhos agendados

## <a name="short-description"></a>Descrição breve

Descreve os trabalhos agendados e explica como usar e gerenciar trabalhos agendados no PowerShell e no Agendador de Tarefas.

## <a name="long-description"></a>Descrição longa

Os trabalhos agendados do PowerShell são um híbrido útil de trabalhos em segundo plano do PowerShell e tarefas de Agendador de Tarefas.

Como trabalhos em segundo plano do PowerShell, os trabalhos agendados são executados de forma assíncrona em segundo plano As instâncias de trabalhos agendados que têm execução podem ser gerenciadas usando os cmdlets de trabalho, como `Start-Job` ,, `Get-Job` `Stop-Job` e `Receive-Job` .

Assim como Agendador de Tarefas tarefas, os trabalhos agendados são salvos em disco. Você pode exibir e gerenciar os trabalhos no Agendador de Tarefas, habilitá-los e desabilitá-los conforme necessário, executá-los ou usá-los como modelos, estabelecer agendamentos de uso único ou recorrente para iniciar os trabalhos ou definir condições sob as quais os trabalhos são iniciados.

Além disso, os resultados das instâncias de trabalho agendadas são salvos em disco em um formato facilmente acessível, fornecendo um log de saída de trabalho em execução. Os trabalhos agendados são fornecidos com um conjunto personalizado de cmdlets para gerenciá-los. Os cmdlets permitem que você crie, edite, gerencie, desabilite e habilite novamente os trabalhos agendados, gatilhos de trabalho e opções de trabalho.

Esse conjunto abrangente e flexível de ferramentas torna os trabalhos agendados um componente essencial de muitas soluções profissionais de ti do PowerShell.

Os cmdlets de trabalho agendados são incluídos no módulo **PSScheduledJob** que é instalado com o PowerShell. Esse módulo foi introduzido no PowerShell 3,0 e funciona no PowerShell 3,0 e em versões posteriores do PowerShell. Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).

Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

Para obter mais informações sobre Agendador de Tarefas, consulte [Agendador de tarefas](/windows/desktop/TaskSchd/task-scheduler-reference).

> [!NOTE]
> Você pode exibir e gerenciar trabalhos agendados do PowerShell no Agendador de Tarefas. Os cmdlets do PowerShell e trabalhos agendados funcionam apenas em trabalhos agendados que são criados no PowerShell.

## <a name="quick-start"></a>Início rápido

Este exemplo cria um trabalho agendado que é iniciado todos os dias às 3:00 e executa o `Get-Process` cmdlet. O trabalho é iniciado mesmo que o computador esteja sendo executado em baterias.

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

O `Get-ScheduledJob` cmdlet obtém os trabalhos agendados no computador local.

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

`Get-JobTrigger` Obtém os gatilhos de trabalho de **ProcessJob** . Os parâmetros de entrada especificam o trabalho agendado, não o gatilho, porque os gatilhos são salvos em um trabalho agendado.

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

Este exemplo usa o parâmetro **ContinueIfGoingOnBattery** do `Set-ScheduledJob` cmdlet para alterar a propriedade **StopIfGoingOnBatteries** de **ProcessJob** para **false** .

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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

O `Get-ScheduledJob` cmdlet obtém o trabalho agendado do **ProcessJob** .

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

O `Get-Job` cmdlet obtém todas as instâncias do trabalho agendado **ProcessJob** que foram executados até o momento. O `Get-Job` cmdlet obtém trabalhos agendados somente quando o módulo **PSScheduledJob** é importado para a sessão atual.

> [!TIP]
> Observe que você usa os cmdlets de trabalho agendado para gerenciar trabalhos agendados, mas usa os cmdlets de trabalho para gerenciar instâncias de trabalhos agendados.

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

O `Receive-Job` cmdlet obtém os resultados da instância mais recente do trabalho agendado **PROCESSJOB** (ID = 51).

```powershell
Receive-Job -ID 51
```

Embora o `Receive-Job` comando não tenha incluído o parâmetro **Keep** , os resultados do trabalho são salvos no disco até que você os exclua ou o número máximo de resultados seja excedido.

Os resultados do trabalho não estão mais disponíveis nesta sessão, mas se você iniciar uma nova sessão ou abrir uma nova janela do PowerShell, os resultados do trabalho estarão disponíveis novamente.

O comando a seguir usa o parâmetro **definitionname** do `Start-Job` cmdlet para iniciar o trabalho agendado do **ProcessJob** .

Os trabalhos que são iniciados usando o `Start-Job` cmdlet são trabalhos em segundo plano padrão do PowerShell, não instâncias do trabalho agendado. Como todos os trabalhos em segundo plano, esses trabalhos são iniciados imediatamente, eles não estão sujeitos a opções de trabalho ou afetados por gatilhos de trabalho, e sua saída não é salva no diretório de saída do diretório de trabalho agendado.

```powershell
Start-Job -DefinitionName ProcessJob
```

O `Unregister-ScheduledJob` cmdlet exclui o trabalho agendado **ProcessJob** e todos os resultados salvos de suas instâncias de trabalho.

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a>Conceitos de trabalhos agendados

Um trabalho agendado executa comandos ou um script. Um trabalho agendado pode incluir gatilhos de trabalho que iniciam as opções de trabalho e trabalho que definem condições para executar o trabalho.

Um gatilho de trabalho inicia automaticamente um trabalho agendado. Um gatilho de trabalho pode incluir uma agenda única ou recorrente ou especificar um evento, como quando um usuário faz logon ou o Windows é iniciado. Um trabalho agendado pode ter um ou mais gatilhos de trabalho, e você pode criar, adicionar, habilitar, desabilitar e obter gatilhos de trabalho.

Disparadores de trabalho são opcionais. Você pode iniciar trabalhos agendados imediatamente usando o `Start-Job cmdlet` , ou adicionando o parâmetro **RunNow** ao `Register-ScheduledJob` comando.

As opções de trabalho definem as condições para executar um trabalho agendado. Cada trabalho agendado tem um objeto de opções de trabalho. Você pode criar e editar objetos de opções de trabalho e adicioná-los a um ou mais trabalhos agendados.

Cada vez que um trabalho agendado é iniciado, uma instância de trabalho é criada. Use os cmdlets de trabalho do PowerShell para exibir e gerenciar a instância de trabalho.

Os trabalhos agendados são salvos em disco e usam o verbo do cmdlet, `Register` em vez de `New` . Os arquivos XML estão localizados no computador local no diretório `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .

O PowerShell cria um diretório para cada trabalho agendado e salva os comandos do trabalho, os gatilhos de trabalho, as opções de trabalho e os resultados do trabalho no diretório de trabalho agendado. Os gatilhos de trabalho e as opções de trabalho não são salvos em disco de forma independente.
Eles são salvos no XML do trabalho agendado de cada trabalho agendado ao qual estão associados.

Os trabalhos agendados, os gatilhos de trabalho e as opções de trabalho aparecem no PowerShell como objetos.
Os objetos são interligados, o que os torna fácil de descobrir e usar em comandos e scripts.

Os trabalhos agendados aparecem como objetos **ScheduledJobDefinition** . O objeto **ScheduledJobDefinition** tem uma propriedade **JobTriggers** que contém os gatilhos de trabalho do trabalho agendado e uma propriedade **Options** que contém as opções de trabalho. Os objetos **ScheduledJobTriggers** e **ScheduledJobOptions** que representam gatilhos de trabalho e opções de trabalho, respectivamente, têm uma propriedade **JobDefinition** que contém o trabalho agendado ao qual estão associados. Essa interconexão recursiva facilita a localização dos gatilhos e das opções de um trabalho agendado, bem como a localização, o script e a exibição do trabalho agendado ao qual qualquer opção de trabalho ou gatilho de trabalho está associada.

## <a name="see-also"></a>Confira também

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)

[Agendador de Tarefas](/windows/desktop/TaskSchd/task-scheduler-reference)
