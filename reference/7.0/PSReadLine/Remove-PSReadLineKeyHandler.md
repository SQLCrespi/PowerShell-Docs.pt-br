---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 1c6a21880bba0f074388c6e32baa8e1c7e93413d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196600"
---
# Remove-PSReadLineKeyHandler

## SINOPSE
Remove uma associação de chave.

## SYNTAX

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-PSReadLineKeyHandler` cmdlet Remove uma associação de chave especificada.

## EXEMPLOS

### Exemplo 1: remover uma associação

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

Esse comando Remove a associação da combinação de teclas, ou corda, `Ctrl+B` . A `Ctrl+B` corda é criada no `Set-PSReadLineKeyHandler` artigo.

## PARAMETERS

### -Corda

Especifica uma matriz de chaves ou sequências de chaves a serem removidas. Uma única associação é especificada usando uma única cadeia de caracteres. Se a associação for uma sequência de chaves, separe as chaves por uma vírgula, como no exemplo a seguir:

`Ctrl+x,Ctrl+l`

Esse parâmetro aceita uma matriz de cadeias de caracteres. Cada cadeia de caracteres é uma associação separada, não uma sequência de chaves para uma única associação.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViMode

Especifique a qual modo vi a associação se aplica. Os valores possíveis são: inserir, comando.

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Set-PSReadLineOption](Set-PSReadLineOption.md)

[Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
