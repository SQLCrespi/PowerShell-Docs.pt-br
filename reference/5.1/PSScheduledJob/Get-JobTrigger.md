---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193676"
---
# Get-JobTrigger

## SINOPSE
Habilita os gatilhos de trabalhos agendados.

## SYNTAX

### JobDefinition (padrão)

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-JobTrigger** obtém os gatilhos de trabalho dos trabalhos agendados.
Você pode usar este comando para examinar os gatilhos de trabalho ou para direcionar os gatilhos de trabalho para outros cmdlets.

Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.
Gatilhos de trabalho não são salvas em disco de modo independente; elas fazem parte de um trabalho agendado.
Para obter um gatilho de trabalho, especifique o trabalho agendado que o gatilho inicia.

Use os parâmetros do cmdlet **Get-JobTrigger** para identificar os trabalhos agendado.
Você pode identificar os trabalhos agendados por seus nomes ou números de identificação, ou inserindo ou canalizando objetos **ScheduledJob** , como os que são retornados pelo cmdlet Get-ScheduledJob, para **Get-JobTrigger** .

**Get-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: obter um gatilho de trabalho por nome de trabalho agendado

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

O comando usa o parâmetro *Name* de **Get-JobTrigger** para obter os gatilhos de trabalho do trabalho agendado BackupJob.

### Exemplo 2: obter um gatilho de trabalho por ID

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

O exemplo usa o parâmetro *ID* de **Get-JobTrigger** para obter os gatilhos de trabalho de um trabalho agendado.

### Exemplo 3: obter gatilhos de trabalho ao canalizar um trabalho

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

Esse comando obtém os gatilhos de trabalho de todos os trabalhos que têm backup ou arquivamento em seus nomes.

### Exemplo 4: obter o gatilho de trabalho de um trabalho em um computador remoto

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

Esse comando obtém um dos dois gatilhos trabalhos de um trabalho agendado em um computador remoto.

O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.
Ele usa o cmdlet Get-ScheduledJob para obter o trabalho agendado de backup, que ele canaliza para o cmdlet **Get-JobTrigger** .
Ele usa o parâmetro *triggerid* para obter apenas o segundo gatilho.

### Exemplo 5: obter todos os gatilhos de trabalho

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

Este comando obtém todos os gatilhos de trabalho de todos os trabalhos agendados no computador local.

O comando usa o Get-ScheduledJob para obter os trabalhos agendados no computador local e os canaliza para **Get-JobTrigger** , que obtém o gatilho de trabalho de cada trabalho agendado (se houver).

Para adicionar o nome do trabalho agendado à exibição do gatilho de trabalho, o comando usa o recurso de propriedade calculada do cmdlet Format-Table.
Além das propriedades do gatilho de trabalho que são exibidas por padrão, o comando cria uma nova propriedade ScheduledJob que exibe o nome do trabalho agendado.

### Exemplo 6: obter a propriedade de gatilho de trabalho de um trabalho agendado

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

Os gatilhos de trabalho de uma tarefa agendada são armazenados na propriedade JobTriggers do trabalho.
Este exemplo mostra alternativas ao uso do cmdlet **Get-JobTrigger** para obter gatilhos de trabalho.
Os resultados são idênticos a usar o cmdlet **Get-JobTrigger** e as técnicas podem ser usadas intercambiavelmente.

### Exemplo 7: comparar gatilhos de trabalho

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

Este exemplo mostra como comparar os gatilhos de trabalho de dois trabalhos agendados.

## PARAMETERS

### -Id
Especifica o número de identificação de um trabalho agendado.
O **Get-JobTrigger** obtém o gatilho de trabalho do trabalho agendado especificado.

Para obter o número de identificação de trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

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
Insira uma variável que contenha objetos  **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.
Você também pode canalizar objetos **ScheduledJob** para **Get-JobTrigger** .

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
Especifique o nome de um trabalho agendado.
O **Get-JobTrigger** obtém o gatilho de trabalho do trabalho agendado especificado.
Há suporte para caracteres curinga.

Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Triggerid
Obtém os gatilhos de trabalho especificado.
Insira as IDs de gatilho de um ou mais gatilhos de trabalho de uma tarefa agendada.
Use esse parâmetro quando o trabalho agendado especificado pelos parâmetros *Name* , *ID* ou *InputObject* tiverem vários gatilhos de trabalho.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
É possível canalizar um trabalho agendado de Get-ScheduledJob para **Get-JobTrigger** .

## SAÍDAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger

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
