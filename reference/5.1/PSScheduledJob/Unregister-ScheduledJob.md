---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193659"
---
# Unregister-ScheduledJob

## SINOPSE
Exclui os trabalhos agendados no computador local.

## SYNTAX

### Definição (padrão)

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Definitionname

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Unregister-ScheduledJob** exclui os trabalhos agendados do computador local.

Quando ele exclui ou cancela o registro de um trabalho agendado, **o cancelamento do registro-ScheduledJob** exclui o diretório do trabalho agendado (no diretório $home \appdata\local\microsoft\windows\powershell\scheduledjobs), que contém o arquivo XML que define o trabalho agendado, o histórico de execução do trabalho e todos os resultados do trabalho.
Essa ação também exclui o trabalho do Agendador de tarefas.

**Unregister-ScheduledJob** exclui somente os trabalhos agendados que são criados usando o cmdlet Register-ScheduledJob.
Ele não exclui os trabalhos agendados que são criados no Agendador de tarefas.

Você pode usar os parâmetros de **Unregister-ScheduledJob** para excluir trabalhos agendados por ID ou nome ou trabalhos agendados de pipe de Get-ScheduledJob para **cancelar o registro-ScheduledJob** .

**Unregister-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: excluir um trabalho agendado

```
PS C:\> Unregister-ScheduledJob TestJob
```

Esse comando exclui o trabalho agendado TestJob no computador local.

### Exemplo 2: excluir todos os trabalhos agendados

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

Este exemplo mostra dois comandos diferentes que excluem todos os trabalhos agendados no computador local.

O primeiro comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador local.
Um operador de pipeline (|) envia os trabalhos agendados para **Unregister-ScheduleJob** , que os exclui.

O segundo comando usa o parâmetro *Name* do **Unregister-ScheduledJob** com um valor de todos (*) para excluir todos os trabalhos agendados.

Os dois comandos utilizam o parâmetro *Force* , que exclui um trabalho agendado, mesmo que uma instância do trabalho esteja em execução.

### Exemplo 3: excluir um trabalho agendado em um computador remoto

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

Esse comando exclui os trabalhos agendados com nomes que começam com Test no computador remoto Server01.
O comando usa o cmdlet Invoke-Command para executar o comando **Unregister-ScheduledJob** no computador Server02.

## PARAMETERS

### -Force
Excluir o trabalho agendado, mesmo que uma instância do trabalho esteja em execução.
Por padrão, o **Unregister-ScheduledJob** não interrompe os trabalhos em execução.

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

### -Id
Excluir os trabalhos agendados com os números de identificação especificado (ID).
Insira as IDs dos trabalhos agendados no computador.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica um trabalho agendado.
Insira uma variável que contenha objetos **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.
Você também pode canalizar os objetos **ScheduledJob** para **cancelar o registro-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Excluir os trabalhos agendados com os nomes especificados.
Digite os nomes de um ou mais trabalhos agendados no computador.
Há suporte para caracteres curinga.

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
É possível redirecionar os trabalhos agendados para Unregister-ScheduledJob

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

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
