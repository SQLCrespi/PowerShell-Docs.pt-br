---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193675"
---
# Get-ScheduledJob

## SINOPSE
Obtém os trabalhos agendados no computador local.

## SYNTAX

### DefinitionId (padrão)

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### Definitionname

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-ScheduledJob** obtém os trabalhos agendados no computador local.
**Get-ScheduledJob** obtém apenas os trabalhos agendados que são criados pelo usuário atual usando o cmdlet Register-ScheduledJob.

Embora trabalhos que são criados usando o cmdlet **Register-ScheduledJob** apareçam no Agendador de tarefas, o **Get-ScheduledJob** obtém apenas os trabalhos agendados.
Ele não obtém os trabalhos agendados que são criados no Agendador de tarefas.

Sem parâmetros, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.
Você pode usar os parâmetros de **Get-ScheduledJob** para obter os trabalhos agendados pelo nome ou ID e examiná-los ou direcioná-los para outros cmdlets.

**Get-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: obter todos os trabalhos agendados

```
PS C:\> Get-ScheduledJob
```

Este comando obtém todos os trabalhos agendados no computador local.

### Exemplo 2: obter trabalhos agendados por nome

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

Esse comando obtém todos os trabalhos agendados no computador que têm nomes que incluem backup ou arquivo morto.
Esse formato de comando permite pesquisar trabalhos específicos.

### Exemplo 3: obter trabalhos agendados em computadores remotos

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

Esse comando obtém todos os trabalhos agendados nos computadores que estão listados no arquivo txt.
O comando usa o cmdlet Invoke-Command para executar um comando **Get-ScheduleJob** em cada computador.

### Exemplo 4: direcionar trabalhos agendados para outros cmdlets

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

Esse comando obtém os disparadores de trabalho dos trabalhos agendados DailyBackup e WeeklyBackup.
Ele usa o cmdlet **Get-ScheduledJob** para obter os trabalhos agendados e o cmdlet Get-JobTrigger para obter os disparadores de trabalho dos trabalhos agendados.

## PARAMETERS

### -Id
Obtém somente os trabalhos agendados com o número de identificação especificado (ID).
Insira um ou mais IDs dos trabalhos agendados no computador.
Por padrão, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Obtém somente os trabalhos agendados com os nomes especificados.
Insira um ou mais nomes dos trabalhos agendados no computador.
Há suporte para caracteres curinga.
Por padrão, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível canalizar a entrada para **Get-ScheduledJob** .

## SAÍDAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition

## OBSERVAÇÕES

* Cada trabalho agendado é salvo em um subdiretório do diretório $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs no computador local. O subdiretório é nomeado de acordo com o trabalho agendado e contém o arquivo XML para o trabalho agendado e registros do histórico de execução. Para obter mais informações sobre trabalhos agendados no disco, consulte about_Scheduled_Jobs_Advanced.
* Trabalhos agendados que você cria no Windows PowerShell aparecem no Agendador de tarefas na pasta Library\Microsoft\Windows\PowerShell\ScheduledJobs do Agendador de tarefas. Você pode usar o Agendador de tarefas para exibir e editar o trabalho agendado.
* Você pode usar o Agendador de tarefas, a ferramenta de linha de comando SchTasks.exe e os cmdlets do Agendador de tarefas para gerenciar trabalhos agendados criados por você com os cmdlets do Trabalho agendado. No entanto, você não pode usar os cmdlets do Trabalho agendado para gerenciar tarefas que você cria no Agendador de tarefas.

## LINKS RELACIONADOS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
