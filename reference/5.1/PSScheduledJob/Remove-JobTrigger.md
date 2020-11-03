---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193669"
---
# Remove-JobTrigger

## SINOPSE
Excluir gatilhos de trabalho de trabalhos agendados.

## SYNTAX

### JobDefinition (padrão)

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### JobDefinitionId

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Remove-JobTrigger** exclui os gatilhos de trabalho dos trabalhos agendados.

Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.
Para gerenciar gatilhos de trabalho, use os cmdlets New-JobTrigger, Add-JobTrigger, Set-JobTrigger e Set-ScheduledJob.

Use os parâmetros *Name* , *ID* ou *InputObject* de **Remove-JobTrigger** para identificar os trabalhos agendados dos quais os gatilhos são removidos.
Use o parâmetro *triggerid* para identificar os gatilhos de trabalho a serem excluídos.
Por padrão, o **Remove-JobTrigger** exclui todos os gatilhos de trabalho de um trabalho agendado.

**Remove-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: excluir todos os gatilhos de trabalho

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

Este comando exclui todos os gatilhos de trabalho agendados que têm nomes que começam com teste.

### Exemplo 2: excluir gatilhos de trabalho selecionados

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

Esse comando exclui somente o terceiro gatilho (ID = 3) do trabalho agendado BackupArchive.

### Exemplo 3: excluir gatilhos de trabalho AtStartup de todos os trabalhos agendados

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

Esta função exclui todos os gatilhos de trabalho AtStartup de todos os trabalhos no computador local.
Para usar a função, execute a função em sua sessão e digite `Delete-AtStartup` .

A função Delete-AtStartup contém um único comando.
O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.
Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho de cada um dos trabalhos agendados.
Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que seleciona os gatilhos de trabalho em que o valor da propriedade Frequency do gatilho do trabalho é igual a AtStartup.

Os objetos **JobTrigger** têm uma propriedade **JobDefinition** que contém o trabalho agendado que eles disparam.
O restante do comando usa esse recurso valioso.

Um operador de pipeline envia os gatilhos de trabalho AtStartup para o cmdlet ForEach-Object, que executa um comando **Remove-JobTrigger** em cada gatilho AtStartup.
O valor do parâmetro *InputObject***Remove-JobTrigger** é o trabalho agendado na propriedade JobDefinition do gatilho de trabalho.
O valor do parâmetro *TriggerID* é o identificador na propriedade ID do gatilho de trabalho.

### Exemplo 4: excluir um gatilho de trabalho de um trabalho agendado remoto

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

Esse comando exclui o primeiro gatilho de trabalho do trabalho Inventory no computador Server01.

O comando usa o cmdlet **Invoke-Command** para executar o cmdlet **Remove-JobTrigger** no computador Server01.
O cmdlet **Remove-JobTrigger** usa o parâmetro *ID* para identificar o trabalho agendado de inventário e o parâmetro *triggerid* para especificar o primeiro gatilho.
O parâmetro *ID* é especialmente útil quando vários trabalhos agendados têm nomes iguais ou semelhantes.

## PARAMETERS

### -Id
Especifica os números de identificação dos trabalhos agendados.
O **Remove-JobTrigger** exclui os gatilhos dos trabalhos agendados especificados.

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
Você também pode canalizar objetos **ScheduledJob** para **Remove-JobTrigger** .

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
O **Remove-JobTrigger** exclui os gatilhos dos trabalhos agendados especificados.
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

### -Triggerid
Exclui somente os gatilhos de trabalho especificados.
Por padrão, o **Remove-JobTrigger** exclui todos os gatilhos de trabalhos agendados.
Use esse parâmetro quando os trabalhos agendados tiverem vários gatilhos de trabalho.

Insira as IDs de gatilho de um ou mais gatilhos de trabalho de uma tarefa agendada.
Se você especificar vários trabalhos agendados, **Remove-JobTrigger** excluirá o gatilho de trabalho com a ID especificada de todos os trabalhos agendados.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
É possível redirecionar os trabalhos agendados para o cmdlet **Remove-JobTrigger** .

## SAÍDAS

### Nenhum
O cmdlet não gera nenhuma saída.

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
