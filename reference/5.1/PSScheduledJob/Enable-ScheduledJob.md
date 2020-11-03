---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193678"
---
# Enable-ScheduledJob

## SINOPSE
Habilita um trabalho agendado.

## SYNTAX

### Definição (padrão)

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Definitionname

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Enable-ScheduledJob** habilita novamente os trabalhos agendados que estão desabilitados, como aqueles que estão desabilitados usando o cmdlet Disable-ScheduledJob.
Trabalhos habilitados são executados automaticamente quando disparados.

Para habilitar um trabalho agendado, o cmdlet **Enable-ScheduledJob** define a propriedade Enabled do trabalho agendado para $true.

**Enabled-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: habilitar um trabalho agendado

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

Este comando habilita o trabalho agendado com ID 2 no computador local.
A saída mostra o efeito do comando.

### Exemplo 2: habilitar todos os trabalhos agendados

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

Este comando habilita todos os trabalhos agendados no computador local.
Ele usa o cmdlet Get-ScheduledJob para obter todo o trabalho agendado e o cmdlet **Enable-ScheduledJob** para habilitá-los.

O **Enable-ScheduledJob** não gera avisos ou erros se você habilitar um trabalho agendado que já está habilitado, para que você possa habilitar todos os trabalhos agendados sem condições.

### Exemplo 3: habilitar os trabalhos agendados selecionados

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

Este comando habilita os trabalhos agendados que não exigem uma conexão de rede.

O comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador.
Um operador de pipeline envia os trabalhos agendados para o cmdlet Get-ScheduledJobOption, que obtém as opções de trabalho de cada trabalho agendado.
Cada objeto de opções de trabalho tem uma propriedade JobDefinition que contém o trabalho agendado associado.
A propriedade JobDefinition é usada para concluir o comando.

O comando usa um operador de pipeline (|) para enviar as opções de trabalho para o cmdlet Where-Object, que seleciona objetos de opção de trabalho agendado nos quais a propriedade **RunWithoutNetwork** tem um valor de True ($true).
Outro operador de pipeline envia os objetos de opções de trabalho agendado selecionados para o cmdlet ForEach-Object, que executa um comando **Enable-ScheduledJob** no trabalho agendado no valor da propriedade JobDefinition de cada objeto de opções de trabalho.

### Exemplo 4: habilitar trabalhos agendados em um computador remoto

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

Este comando habilita os trabalhos agendados que possuem "teste" em seus nomes em dois computadores remotos, Srv01 e Srv10.

O comando usa o cmdlet Invoke-Command para executar um comando **Enable-ScheduledJob** nos computadores Srv01 e Srv10.
O comando usa o parâmetro *Name* do **Enable-ScheduledJob** para habilitar o trabalho agendado Inventory em cada computador.

## PARAMETERS

### -Id
Habilita o trabalho agendado com o número de identificação (ID) especificado.
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
Especifica o trabalho agendado a ser habilitado.
Insira uma variável que contenha objetos **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.
Também é possível canalizar um objeto **ScheduledJobDefinition** para **Enable-ScheduledJob** .

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
Habilita os trabalhos agendados com os nomes especificados.
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
É possível canalizar um trabalho agendado para **Enable-ScheduledJob** .

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Se você usar o parâmetro **Passthru** , **Enable-ScheduledJob** retorna o trabalho agendado que foi habilitado.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* O **Enable-ScheduledJob** não gera avisos ou erros se você usá-lo para habilitar um trabalho agendado que já está habilitado.

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
