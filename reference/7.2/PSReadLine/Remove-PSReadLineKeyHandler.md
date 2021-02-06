---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596172"
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

