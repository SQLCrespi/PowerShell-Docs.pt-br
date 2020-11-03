---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193673"
---
# Get-ScheduledJobOption

## SINOPSE
Obtém as opções de trabalho de trabalhos agendados.

## SYNTAX

### JobDefinition (padrão)

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-ScheduledJobOption** Obtém as opções de trabalho dos trabalhos agendados.
Você pode usar este comando para examinar as opções de trabalho ou para direcionar as opções de trabalho para outros cmdlets.

As opções de trabalho não são salvas em disco de modo independente; elas são parte de um trabalho agendado.
Para obter as opções de trabalho de um trabalho agendado, especifique esse trabalho.

Use os parâmetros do cmdlet **Get-ScheduledJobOption** para identificar o trabalho agendado.
Você pode identificar os trabalhos agendados por seus nomes ou números de identificação ou inserindo ou canalizando objetos **ScheduledJob** , como os que são retornados pelo cmdlet Get-ScheduledJob, para **Get-ScheduledJobOption** .

**Get-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: obter opções de trabalho

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Esse comando obtém as opções de trabalho dos trabalhos agendados que têm BackUp em seus nomes.
Os resultados mostram o objeto de opções de trabalho retornado pelo **Get-ScheduledJobOption** .

### Exemplo 2: obter todas as opções de trabalho

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

Este comando obtém as opções de trabalho de todos os trabalhos agendados no computador local.

Ele usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.
Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet **Get-ScheduledJobOption** , que obtém as opções de trabalho de cada trabalho agendado.

### Exemplo 3: obter opções de trabalho selecionadas

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

Este exemplo mostra como localizar um objeto de opções de trabalho com valores específicos.

O primeiro comando obtém as opções de trabalho nas quais a propriedade RunElevated tem um valor de $True e a propriedade RunWithoutNetwork tem um valor de $False.
A saída mostra o objeto **JobOptions** que foi selecionado.

### Exemplo 4: usar as opções de trabalho para criar um novo trabalho

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

Este exemplo mostra como usar as opções de trabalho que Get-ScheduledJobOption obtém em um novo trabalho agendado.

O primeiro comando usa **Get-ScheduledJobOption** para obter as opções de trabalhos do trabalho agendado BackupTestLogs.
O comando salva as opções na variável $Opts.

O segundo comando usa Register-ScheduledJob cmdlet para criar um novo trabalho agendado.
O valor do parâmetro *ScheduledJobOption* é o objeto de opções na variável $Opts.

### Exemplo 5: obter opções de trabalho de um computador remoto

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

Esse comando usa o cmdlet Invoke-Command para obter as opções de trabalho agendado do trabalho datademon no computador Srv01.
O comando salva as opções na variável $O.

## PARAMETERS

### -Id
Especifica o número de identificação de um trabalho agendado.
O **Get-ScheduledJobOption** obtém as opções de trabalho do trabalho agendado especificado.

Para obter os números de identificação dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica um trabalho agendado.
Insira uma variável que contenha um objeto **ScheduledJob** ou digite um comando ou uma expressão que obtenha um objeto **ScheduledJob** , como um comando Get-ScheduledJob.
Você também pode redirecionar um objeto **ScheduledJob** para **Get-ScheduledJobOption** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Especifica os nomes dos trabalhos agendados.
O **Get-ScheduledJobOption** obtém as opções de trabalho do trabalho agendado especificado.
Há suporte para caracteres curinga.

Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
É possível canalizar um trabalho agendado de Get-ScheduledJob para **Get-ScheduledJobOption** .

## SAÍDAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions

## OBSERVAÇÕES

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
