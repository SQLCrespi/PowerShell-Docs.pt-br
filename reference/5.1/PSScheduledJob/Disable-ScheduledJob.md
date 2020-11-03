---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193685"
---
# Disable-ScheduledJob

## SINOPSE
Desabilita um trabalho agendado.

## SYNTAX

### Definição (padrão)

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Definitionname

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Disable-ScheduledJob** desabilita temporariamente trabalhos agendados.
Desabilitar preserva todas as propriedades do trabalho e não desabilita os disparadores do trabalho, mas impede que os trabalhos agendados iniciem automaticamente quando disparados.
Você pode iniciar um trabalho agendado desabilitado usando o cmdlet Start-Job ou usar um trabalho agendado desabilitado como um modelo.

Para desabilitar um trabalho agendado, o cmdlet **Disable-ScheduledJob** define a propriedade **Enabled** do trabalho agendado como Falso ($false).
Para reabilitar o trabalho agendado, use o cmdlet Enable-ScheduledJob.

**Disable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: desabilitar um trabalho agendado

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

Este comando desabilita o trabalho agendado com ID 2 presente no computador local.
A saída mostra o efeito do comando.

### Exemplo 2: desabilitar todos os trabalhos agendados

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

Este comando desabilita todos os trabalhos agendados existentes no computador local.
Ele usa o cmdlet Get-ScheduledJob para obter todo o trabalho agendado e o cmdlet **Disable-ScheduledJob** para desabilitá-los.

Você pode reabilitar o trabalho agendado usando o cmdlet Enable-ScheduledJob e executar um trabalho agendado desabilitado usando o cmdlet Start-Job.

**Disable-ScheduledJob** não gera avisos ou erros se você desabilitar um trabalho agendado que já está desabilitado, para que você possa desabilitar todos os trabalhos agendados sem condições.

### Exemplo 3: desabilitar os trabalhos agendados selecionados

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

Este comando desabilita trabalhos agendados que não incluem uma credencial.
Trabalhos sem credenciais são executados com a permissão do usuário que os criou.

O comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador.
Um operador de pipeline envia os trabalhos agendados para o cmdlet Where-Object, que seleciona trabalhos agendados que não têm credenciais.
O comando usa o operador não (!) e referências à propriedade Credential do trabalho agendado.
Outro operador de pipeline envia os trabalhos agendados selecionados para o cmdlet **Disable-ScheduledJob** , que os desabilita.

### Exemplo 4: desabilitar trabalhos agendados em um computador remoto

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

Este comando desabilita o trabalho agendado TestJob em dois computadores remotos, Srv01 e Srv10.

O comando usa o cmdlet Invoke-Command para executar um comando **Disable-ScheduledJob** nos computadores Srv01 e Srv10.
O comando usa o parâmetro *Name* do **Disable-ScheduledJob** para selecionar o trabalho agendado do TestJob em cada computador.

### Exemplo 5: desabilitar um trabalho agendado por sua ID global

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

Este exemplo mostra como desabilitar um trabalho agendado usando seu identificador global.
O valor da propriedade GlobalID de um trabalho agendado é um identificador exclusivo (GUID).
Use o valor GlobalID quando a precisão é necessária, como quando você está desativando trabalhos agendados em vários computadores.

## PARAMETERS

### -Id
Desabilita o trabalho agendado com o número de identificação (ID) especificado.
Insira a ID de um trabalho agendado.

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica o trabalho agendado a ser desabilitado.
Insira uma variável que contenha objetos  **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.
Também é possível canalizar um objeto **ScheduledJobDefinition** para **Disable-ScheduledJob** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Desabilita os trabalhos agendados com os nomes especificados.
Insira o nome de um trabalho agendado.
Há suporte para caracteres curinga.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Você pode direcionar um trabalho agendado para **Disable-ScheduledJob** .

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Se você usar o parâmetro **Passthru** , **Disable-ScheduledJob** retorna o trabalho agendado que foi desabilitado.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* **Disable-ScheduledJob** não gerará avisos ou erros se você usá-lo para desabilitar um trabalho agendado que já está desabilitado.

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
