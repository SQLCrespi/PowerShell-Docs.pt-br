---
description: Explica os tópicos avançados de trabalho agendado, incluindo a estrutura de arquivos que é subjacente aos trabalhos agendados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195818"
---
# <a name="about-scheduled-jobs-advanced"></a>Sobre os trabalhos agendados avançado

## <a name="short-description"></a>Descrição breve

Explica os tópicos avançados de trabalho agendado, incluindo a estrutura de arquivos que é subjacente aos trabalhos agendados.

## <a name="long-description"></a>Descrição longa

Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).

## <a name="scheduled-job-directories-and-files"></a>Diretórios e arquivos de trabalho agendados

Os trabalhos agendados do PowerShell são trabalhos do PowerShell e tarefas de Agendador de Tarefas.
Cada trabalho agendado é registrado no Agendador de Tarefas e salvo em disco no formato XML de serialização Microsoft .NET Framework.

Quando você cria um trabalho agendado, o PowerShell cria um diretório para o trabalho agendado no `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` diretório no computador local. O nome do diretório é o mesmo que o nome do trabalho.

A seguir está um exemplo de diretório **ScheduledJobs** .

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

Cada trabalho agendado tem seu próprio diretório. O diretório contém o arquivo XML de trabalho agendado e um subdiretório de **saída** .

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

O diretório de **saída** para um trabalho agendado contém seu histórico de execução.
Cada vez que um gatilho de trabalho inicia um trabalho agendado, o PowerShell cria um diretório nomeado com carimbo de data/hora no diretório de saída. O diretório timestamp contém os resultados do trabalho em um arquivo de **Results.xml** e o status do trabalho em um arquivo **Status.xml** .

O comando a seguir mostra os diretórios de histórico de execução para o trabalho agendado do **ProcessJob** .

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

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

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

Você pode abrir e examinar os arquivos de **ScheduledJobDefinition.xml** , **Results.xml** e **Status.xml** ou usar o `Select-XML` cmdlet para analisar os arquivos.

> [!WARNING]
> Não edite os arquivos XML. Se qualquer arquivo XML contiver XML inválido, o PowerShell excluirá o trabalho agendado e seu histórico de execução, incluindo os resultados do trabalho.

## <a name="start-a-scheduled-job-immediately"></a>Iniciar um trabalho agendado imediatamente

Você pode iniciar um trabalho agendado imediatamente de uma das duas maneiras:

- Execute o `Start-Job` cmdlet para iniciar qualquer trabalho agendado.
- Adicione o parâmetro **RunNow** ao `Register-ScheduledJob` comando para iniciar o trabalho assim que o comando for executado.

Os trabalhos que são iniciados usando o `Start-Job` cmdlet são trabalhos em segundo plano padrão do PowerShell, não instâncias do trabalho agendado. Como todos os trabalhos em segundo plano, esses trabalhos são iniciados imediatamente, eles não estão sujeitos a opções de trabalho ou afetados por gatilhos de trabalho. A saída do trabalho não é salva no diretório de **saída** do diretório de trabalho agendado.

O comando a seguir usa o parâmetro **definitionname** do `Start-Job` cmdlet para iniciar o trabalho agendado do ProcessJob.

```powershell
Start-Job -DefinitionName ProcessJob
```

Para gerenciar o trabalho e obter os resultados do trabalho, use os cmdlets do trabalho. Para obter mais informações sobre os cmdlets de trabalho, consulte [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

> [!NOTE]
> Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão. Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .

## <a name="rename-a-scheduled-job"></a>Renomear um trabalho agendado

Para renomear um trabalho agendado, use o parâmetro Name do `Set-ScheduledJob` cmdlet. Quando você renomeia um trabalho agendado, o PowerShell altera o nome do trabalho agendado e o diretório de trabalho agendado. No entanto, ele não altera os nomes de instâncias do trabalho agendado que já foram executados.

## <a name="get-start-and-end-times"></a>Obter horários de início e término

Para obter as datas e as horas em que as instâncias de trabalho foram iniciadas e encerradas, use as propriedades **PSBeginTime** e **PSEndTime** do objeto ScheduledJob que `Get-Job` retorna para trabalhos agendados.

O exemplo a seguir usa o parâmetro **Property** do `Format-Table` cmdlet para exibir as propriedades **PSBeginTime** e **PSEndTime** de cada instância de trabalho em uma tabela. Uma propriedade calculada denominada **Label** exibe o tempo decorrido de cada instância de trabalho.

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a>Gerenciar histórico de execução

Você pode determinar o número de resultados da instância de trabalho que são salvos para cada trabalho agendado e excluir o histórico de execução e os resultados de trabalho salvos de qualquer trabalho agendado.

A propriedade **ExecutionHistoryLength** de um trabalho agendado determina quantos resultados da instância de trabalho são salvos para o trabalho agendado. Quando o número de resultados salvos excede o valor da propriedade **ExecutionHistoryLength** , o PowerShell exclui os resultados da instância mais antiga para liberar espaço para os resultados da instância mais recente.

Por padrão, o PowerShell salva o histórico de execução e os resultados de 32 instâncias de cada trabalho agendado. Para alterar esse valor, use os parâmetros **MaxResultCount** dos `Register-ScheduledJob` `Set-ScheduledJob` cmdlets ou.

Para excluir o histórico de execução e todos os resultados de um trabalho agendado, use o parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet. Excluir esse histórico de execução não impede que o PowerShell salve os resultados de novas instâncias do trabalho agendado.

O exemplo a seguir usa nivelamento para criar `$JobParms` que são valores de parâmetro que são passados para o `Register-ScheduledJob` cmdlet. Para obter mais informações, consulte [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
O `Register-ScheduledJob` usa `@JobParms` para criar um trabalho agendado. O comando usa o parâmetro **MaxResultCount** com um valor de 12 para salvar apenas os 12 resultados mais recentes da instância de trabalho do trabalho agendado.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

O comando a seguir usa o parâmetro **MaxResultCount** do `Set-ScheduledJob` cmdlet para aumentar o número de resultados da instância salva para
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

O comando a seguir exclui o histórico de execução e os resultados salvos atuais do trabalho agendado do **ProcessJob** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

O comando a seguir obtém os valores das propriedades Name e **ExecutionHistoryLength** de todos os trabalhos agendados no computador e os exibe em uma tabela.

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a>Confira também

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)

[Agendador de Tarefas](/windows/desktop/TaskSchd/task-scheduler-reference)
