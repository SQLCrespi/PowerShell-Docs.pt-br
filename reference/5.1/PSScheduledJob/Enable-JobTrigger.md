---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193677"
---
# Enable-JobTrigger

## SINOPSE
Habilita os disparadores de trabalho dos trabalhos agendados.

## SYNTAX

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Enable-JobTrigger** reabilita os gatilhos de trabalho de trabalhos agendados, como aqueles que foram desabilitados usando o cmdlet Disable-JobTrigger.
Gatilhos de trabalho habilitados e reabilitados podem iniciar trabalhos agendados imediatamente, não é necessário reiniciar o Windows ou o Windows PowerShell.

Para usar esse cmdlet, use o cmdlet Get-JobTrigger para obter os gatilhos de trabalho.
Em seguida, direcione os gatilhos de trabalho para **Enable-JobTrigger** ou use seu parâmetro *InputObject* .

Para habilitar um gatilho de trabalho, o cmdlet **Enable-JobTrigger** define a propriedade Enabled do gatilho de trabalho para $true.

**Enable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: habilitar um gatilho de trabalho

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

Este comando habilita o primeiro gatilho (ID = 1) de trabalho agendado de arquivos de backup no computador local.

O comando usa o cmdlet Get-JobTrigger para obter o gatilho do trabalho.
Um operador de pipeline envia o gatilho de trabalho para o cmdlet **Enable-JobTrigger** , que o habilita.

### Exemplo 2: habilitar todos os gatilhos de trabalho

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.
Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho dos trabalhos agendados.
Outro operador pipeline envia os gatilhos de trabalho para o cmdlet **Enable-JobTrigger** , que os habilita.

### Exemplo 3: habilitar o gatilho de trabalho de um trabalho agendado em um computador remoto

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

Este comando reabilita os gatilhos de trabalho AtLogon no trabalho agendado DeployPackage no computador remoto Server01.

O comando usa o cmdlet Invoke-Command para executar os comandos no computador Server01.
O comando remoto usa o cmdlet Get-JobTrigger para obter os disparadores de trabalho do trabalho agendado DeployPackage.
Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna somente gatilhos de trabalho AtLogon.
Um operador de pipeline envia os gatilhos de trabalho AtLogon para o cmdlet **Enable-JobTrigger** , que os habilita.

### Exemplo 4: Exibir gatilhos de trabalho desabilitados

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Este comando exibe todos os gatilhos de trabalho desabilitados de todos os trabalhos agendados em uma tabela.
Você pode usar um comando como este para descobrir os gatilhos de trabalho que talvez precisem ser habilitados.

O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.
Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho dos trabalhos agendados.
Outro operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna somente gatilhos de trabalho que estão desabilitados, ou seja, onde o valor da propriedade Enabled do gatilho de trabalho não é (!) true.

Outro operador de pipeline envia os gatilhos de trabalho desabilitados para o cmdlet Format-Table, que exibe as propriedades selecionadas dos gatilhos de trabalho em uma tabela.
As propriedades incluem uma nova propriedade JobName que exibe o nome do trabalho agendado na propriedade de JobDefinition do gatilho de trabalho.

## PARAMETERS

### -InputObject
Especifica o gatilho de trabalho a ser habilitado.
Insira uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.
Também é possível canalizar um objeto **ScheduledJobTrigger** para **Enable-JobTrigger** .

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
Você pode canalizar gatilhos de trabalho para **Enable-JobTrigger** .

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* **Enable-JobTrigger** não gerará erros ou avisos se você habilitar um gatilho de trabalho que já esteja habilitado.

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
