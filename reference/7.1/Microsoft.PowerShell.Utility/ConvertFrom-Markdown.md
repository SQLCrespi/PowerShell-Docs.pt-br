---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, cmdlet, redução
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: 9f070819491b87b02868dffdfbe25bf5d72ecab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194555"
---
# ConvertFrom-Markdown

## SINOPSE
Converta o conteúdo de uma cadeia de caracteres ou um arquivo em um objeto **MarkdownInfo** .

## SYNTAX

### PathParamSet (padrão)

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### LiteralParamSet

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### InputObjParamSet

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet converte o conteúdo especificado em um **MarkdownInfo** . Quando um caminho de arquivo é especificado para o parâmetro **path** , o conteúdo no arquivo é convertido. O objeto de saída tem três propriedades:

- A propriedade **token** tem a AST (árvore de sintaxe abstrata) do objeto convertido
- A propriedade **HTML** tem a conversão HTML da entrada especificada
- A propriedade **VT100EncodedString** tem a cadeia de caracteres convertida com sequências de escape ANSI (vt100) se o parâmetro **AsVT100EncodedString** foi especificado

Esse cmdlet foi introduzido no PowerShell 6,1.

## EXEMPLOS

### Exemplo 1: converter um arquivo que contém conteúdo de redução para HTML

```powershell
ConvertFrom-Markdown -Path .\README.md
```

O objeto **MarkdownInfo** é retornado. A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo. A propriedade **HTML** tem o conteúdo convertido em HTML do `README.md` arquivo.

### Exemplo 2: converter um arquivo que contém conteúdo de redução para uma cadeia de caracteres codificada em VT100

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

O objeto **MarkdownInfo** é retornado. A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo. A propriedade **VT100EncodedString** tem o conteúdo da cadeia de caracteres codificada em vt100 convertido do `README.md` arquivo.

### Exemplo 3: converter o objeto de entrada que contém o conteúdo de redução em uma cadeia de caracteres codificada em VT100

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

O objeto **MarkdownInfo** é retornado. O objeto **FileInfo** de `Get-Item` é convertido em uma cadeia de caracteres codificada em VT100. A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo. A propriedade **VT100EncodedString** tem o conteúdo da cadeia de caracteres codificada em vt100 convertido do `README.md` arquivo.

### Exemplo 4: converter uma cadeia de caracteres que contém conteúdo de redução para uma cadeia de caracteres codificada em VT100

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

O objeto **MarkdownInfo** é retornado. A cadeia de caracteres especificada `**Bold text**` é convertida em uma cadeia de caracteres codificada em VT100 e disponível na propriedade **VT100EncodedString** .

## PARAMETERS

### -AsVT100EncodedString

Especifica se a saída deve ser codificada como uma cadeia de caracteres com códigos de escape VT100.

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

### -InputObject

Especifica o objeto a ser convertido. Quando um objeto do tipo **System. String** é especificado, a cadeia de caracteres é convertida. Quando um objeto do tipo **System. IO. FileInfo** é especificado, o conteúdo do arquivo especificado pelo objeto é convertido. Os objetos de qualquer outro tipo resultam em um erro.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica um caminho para o arquivo a ser convertido.

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica um caminho para o arquivo a ser convertido.

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

## SAÍDAS

### Microsoft. PowerShell. MarkdownRender. MarkdownInfo

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Analisador de redução](https://github.com/lunet-io/markdig)

[Código de escape ANSI](https://wikipedia.org/wiki/ANSI_escape_code)

