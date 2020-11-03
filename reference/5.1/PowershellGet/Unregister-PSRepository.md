---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0d98d7bbb26d5a50542f0e125e912ea6333714c1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194111"
---
# Unregister-PSRepository

## SINOPSE
Cancela o registro de um repositório.

## SYNTAX

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION

O `Unregister-PSRepository` cmdlet cancela o registro de um repositório para o usuário atual.

## EXEMPLOS

### Exemplo 1: cancelar o registro de um repositório

Este exemplo cancela o registro do repositório chamado myNuGetSource.

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### Exemplo 2: cancelar o registro de todos os repositórios

Este exemplo usa `Get-PSRepository` para obter todos os repositórios registrados e usa o operador de pipeline para passá-los para `Unregister-PSRepository` o cancelamento do registro.

```powershell
Get-PSRepository | Unregister-PSRepository
```

## PARAMETERS

### -Name

Especifica uma matriz de nomes dos repositórios a serem removidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
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

### System.String[]

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)
