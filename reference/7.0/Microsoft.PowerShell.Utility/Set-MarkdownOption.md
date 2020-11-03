---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e18cc8e0f5e547c4418f59b6f55109052b69c220
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "93194823"
---
# Set-MarkdownOption

## SINOPSE
Define as cores e os estilos usados para renderizar o conteúdo de redução no console.

## SYNTAX

### IndividualSetting (padrão)

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### Tema

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### InputObject

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## DESCRIPTION

Define as cores e os estilos usados para renderizar o conteúdo de redução no console. Esses estilos são definidos usando códigos de escape ANSI que alteram a cor e o estilo do texto de redução que está sendo renderizado.

Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .

> [!NOTE]
> Os valores de cadeia de caracteres usados nas configurações são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI. Não inclua o caractere de **escape** na cadeia de caracteres. Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

## EXEMPLOS

### Exemplo 1-alternar para o tema claro

Este exemplo seleciona o tema **claro** e exibe a nova configuração usando o parâmetro **PassThru** .

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### Exemplo 2 – personalizar as configurações de cor e estilo

Este exemplo altera o código de escape para os cabeçalhos de redução. A configuração padrão dos cabeçalhos os renderiza como texto sublinhado de várias cores. Essa alteração remove o estilo sublinhado.

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## PARAMETERS

### -BoldForegroundColor

Define a cor de primeiro plano para renderizar o texto de redução em negrito.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Código

Define a cor para renderizar blocos de código e abrange em texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header1Color

Define a cor para renderização de blocos header1 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header2Color

Define a cor para renderização de blocos Header2 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header3Color

Define a cor para renderização de blocos Header3 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header4Color

Define a cor para renderização de blocos Header4 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header5Color

Define a cor para renderização de blocos Header5 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header6Color

Define a cor para renderização de blocos Header6 no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageAltTextForegroundColor

Define a cor de primeiro plano para renderizar o texto alternativo de um elemento Image no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Um objeto **PSMarkdownOptionInfo** que contém a configuração a ser definida.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ItalicsForegroundColor

Define a cor de primeiro plano para renderizar os itálicos no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkForegroundColor

Define a cor de primeiro plano para renderizar hiperlinks no texto de redução.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Faz com que o cmdlet gere um objeto **PSMarkdownOptionInfo** contendo a nova configuração.

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

### -Tema

Seleciona um tema que contém configurações de cores predefinidas. Os valores possíveis são **escuro** e **claro** .

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

## SAÍDAS

### Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo

## OBSERVAÇÕES

Os valores de cadeia de caracteres usados para definir a cor e o estilo devem corresponder à expressão regular `^\[*[0-9;]*?m{1}` .

## LINKS RELACIONADOS

[Get-MarkdownOption](Get-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)
