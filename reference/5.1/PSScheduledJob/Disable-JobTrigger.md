---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193689"
---
# Disable-JobTrigger

## SINOPSE
Desabilita os disparadores de trabalho dos trabalhos agendados.

## SYNTAX

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Disable-JobTrigger** desabilita temporariamente os gatilhos dos trabalhos agendados.
A desabilitação preserva todas as propriedades de gatilho de trabalho, mas impede que o gatilho de trabalho inicie o trabalho agendado.

Para usar esse cmdlet, use o cmdlet Get-JobTrigger para obter os gatilhos de trabalho.
Em seguida, redirecione os gatilhos de trabalho para **Disable-JobTrigger** ou utilize seu parâmetro *InputObject* .

Para desabilitar um gatilho de trabalho, o cmdlet **Disable-JobTrigger** define a propriedade Enabled do gatilho de trabalho para $false.
Para reabilitar o gatilho de trabalho, use o cmdlet Enable-JobTrigger, que define a propriedade **Enabled** do gatilho de trabalho para $true.
Desabilitar um gatilho de trabalho não desabilita o trabalho agendado, como é feito pelo cmdlet Disable-ScheduledJob, mas se você desabilitar todos os gatilhos de trabalho, o efeito será o mesmo que desabilitar o trabalho agendado.

Se você desabilitar um trabalho agendado ou desabilitar todos os gatilhos de trabalho de um trabalho agendado, ainda poderá iniciar o trabalho usando o cmdlet Start-Job ou usar o trabalho agendado desabilitado como um modelo.

**Disable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: desabilitar um gatilho de trabalho

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

Este comando desabilita o primeiro gatilho (ID = 1) de trabalho agendado de arquivos de backup no computador local.

O comando usa o cmdlet Get-JobTrigger para obter o gatilho do trabalho.
Um operador de pipeline envia o gatilho de trabalho para o cmdlet **Disable-JobTrigger** , que o desabilita.

### Exemplo 2: desabilitar todos os gatilhos de trabalho

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Esses comandos desabilitam todos os gatilhos de trabalho nos dois trabalhos agendados e exibem os resultados.

### Exemplo 3: desabilitar o gatilho de trabalho de um trabalho agendado em um computador remoto

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

Este comando desabilita os gatilhos de trabalho diários no trabalho agendado DeployPackage no computador remoto Server01.

O comando usa o cmdlet Invoke-Command para executar os comandos no computador Server01.
O comando remoto usa o cmdlet Get-JobTrigger para obter os disparadores de trabalho do trabalho agendado DeployPackage.
Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna apenas gatilhos de trabalho diários.
Um operador de pipeline envia os gatilhos de trabalho diários para o cmdlet **Disable-JobTrigger** , que os desabilita.

## PARAMETERS

### -InputObject
Especifica o gatilho de trabalho a ser desabilitado.
Insira uma variável que contenha objetos  **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.
Também é possível canalizar um objeto **ScheduledJobTrigger** para **Disable-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger
É possível redirecionar gatilhos de trabalho para **Disable-JobTrigger** .

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* **Disable-JobTrigger** não gerará erros ou avisos se você desabilitar um gatilho de trabalho que já esteja desabilitado.

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
