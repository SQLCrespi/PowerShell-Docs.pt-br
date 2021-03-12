---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2b6bbc6e3e0c535d777509a545edfe10fed7d727
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194938"
---
# Get-ExperimentalFeature

## SINOPSE
Obtém recursos experimentais.

## SYNTAX

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-ExperimentalFeature` cmdlet retorna todos os recursos experimentais descobertos pelo PowerShell.
Os recursos experimentais podem vir de módulos ou do mecanismo do PowerShell. Os recursos experimentais permitem que os usuários testem novos recursos com segurança e forneçam comentários (normalmente por meio do GitHub) antes que o design seja considerado concluído e quaisquer alterações possam se tornar uma alteração significativa.

## EXEMPLOS

### Exemplo 1

Obtém a lista de recursos experimentais registrados no momento e seu estado atual.

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## PARAMETERS

### -Name

Nome ou nomes de recursos experimentais específicos a serem retornados.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

Nome ou nomes dos recursos experimentais a serem retornados.

## SAÍDAS

### System. Management. Automation. ExperimentalFeature

Retorna instâncias que correspondem aos nomes solicitados ou a todos os recursos experimentais se nenhum nome for especificado.

## LINKS RELACIONADOS

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)
