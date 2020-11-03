---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193690"
---
# Add-JobTrigger

## SINOPSE
Adiciona disparadores de trabalho a trabalhos agendados.

## SYNTAX

### JobDefinition (padrão)

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### JobDefinitionId

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Add-JobTrigger** adiciona gatilhos de trabalho a trabalhos agendados.
Você pode usá-lo para adicionar vários gatilhos a vários trabalhos agendados.

Um gatilho de trabalho inicia um trabalho agendado em um agendamento de uso único ou recorrente ou quando ocorre um evento.

Use o parâmetro *Trigger* de **Add-JobTrigger** para identificar os gatilhos de trabalho a serem adicionados.
Use os parâmetros *Name* , *ID* ou *InputObject* de **Add-JobTrigger** para identificar o trabalho agendado ao qual os gatilhos são adicionados.

Para criar gatilhos de trabalho para o valor do parâmetro *Trigger* , use o cmdlet New-JobTrigger ou use uma tabela de hash para especificar o gatilho do trabalho.

**Add-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: adicionar um gatilho de trabalho a um trabalho agendado

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

Estes comandos adicionam o gatilho de trabalho Daily ao trabalho agendado TestJob.

O primeiro comando usa o cmdlet New-JobTrigger para criar um gatilho de trabalho que inicia um trabalho agendado todos os dias às 3:00 a.m.
O comando salva o gatilho de trabalho na variável $Daily.

O segundo comando usa o cmdlet **Add-JobTrigger** para adicionar o gatilho de trabalho na variável $Startup ao trabalho agendado TestJob.

### Exemplo 2: adicionar um gatilho de trabalho a vários trabalhos agendados

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

Este comando adiciona um gatilho de trabalho AtStartup a todos os trabalhos agendados no computador local.
Ele usa o Get-ScheduledJob para obter todos os trabalhos agendados no computador.
Ele usa um operador de pipeline (|) para enviar os trabalhos para o cmdlet **Add-JobTrigger** , que adiciona o gatilho de trabalho a cada um dos trabalhos agendados.
O valor do parâmetro *Trigger* é um comando New-JobTrigger que cria o gatilho de trabalho AtStartup.

### Exemplo 3: copiar um gatilho de trabalho

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

Estes comandos copiam o gatilho de trabalho do trabalho agendado BackupArchives e adicionam-no aos trabalhos agendados TestBackup e BackupLogs.

O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado trabalho.
O comando salva o gatilho na variável $t.

O segundo comando usa o cmdlet **Add-JobTrigger** para adicionar o gatilho de trabalho em $t aos trabalhos agendados TestBackup e BackupLogs.

## PARAMETERS

### -Id
Especifica os números de identificação dos trabalhos agendados.
**Add-JobTrigger** adiciona o gatilho de trabalho a trabalhos agendados especificados.

Para obter o número de identificação de trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica os trabalhos agendados.
Insira uma variável que contenha objetos **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.
Você também pode canalizar objetos **ScheduledJob** para **Add-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
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
**Add-JobTrigger** adiciona os gatilhos de trabalho a trabalhos agendados especificados.
Há suporte para caracteres curinga.

Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gatilho
Especifica os gatilhos de trabalho a serem adicionados.
Insira uma tabela de hash que especifique gatilhos de trabalho ou uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.
Você também pode canalizar objetos **ScheduledJobTrigger** para **Add-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger, Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
É possível redirecionar gatilhos de trabalho ou trabalhos agendados para **Add-JobTrigger** .

## SAÍDAS

### Nenhum
Este cmdlet não retorna nenhuma saída.

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
