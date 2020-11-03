---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: bf3934ed711eac30573b173f2c3fac3378ca2f3a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195349"
---
# Get-Clipboard

## SINOPSE
Obtém o conteúdo da área de transferência.

[!NOTE]
> No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Clipboard` cmdlet obtém o conteúdo da área de transferência como texto. Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .

## EXEMPLOS

### Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando

Neste exemplo, copiamos o texto "Olá" para a área de transferência.

```powershell
Get-Clipboard
```

```Output
hello
```

## PARAMETERS

### -RAW

Obtém todo o conteúdo da área de transferência. O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### System.String

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Set-Clipboard](Set-Clipboard.md)

