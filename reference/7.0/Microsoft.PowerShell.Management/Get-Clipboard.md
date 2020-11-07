---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: ed56dc5655f640dae1d80c66850581ff12dbb7ee
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347594"
---
# Get-Clipboard

## SINOPSE
Obtém o conteúdo da área de transferência.

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Clipboard` cmdlet obtém o conteúdo da área de transferência como texto. Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .

> [!NOTE]
> No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho. Não há suporte para esse cmdlet no macOS.

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
