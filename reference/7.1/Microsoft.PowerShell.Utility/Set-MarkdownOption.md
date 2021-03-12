---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MarkdownOption
ms.openlocfilehash: 5e19dc25d0b10888f6ce2f915926610f0780daf6
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195318"
---
# <span data-ttu-id="4b803-102">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="4b803-102">Set-MarkdownOption</span></span>

## <span data-ttu-id="4b803-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4b803-103">SYNOPSIS</span></span>
<span data-ttu-id="4b803-104">Define as cores e os estilos usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="4b803-104">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="4b803-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b803-105">SYNTAX</span></span>

### <span data-ttu-id="4b803-106">IndividualSetting (padrão)</span><span class="sxs-lookup"><span data-stu-id="4b803-106">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="4b803-107">Tema</span><span class="sxs-lookup"><span data-stu-id="4b803-107">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="4b803-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="4b803-108">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="4b803-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b803-109">DESCRIPTION</span></span>

<span data-ttu-id="4b803-110">Define as cores e os estilos usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="4b803-110">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="4b803-111">Esses estilos são definidos usando códigos de escape ANSI que alteram a cor e o estilo do texto de redução que está sendo renderizado.</span><span class="sxs-lookup"><span data-stu-id="4b803-111">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="4b803-112">Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="4b803-112">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="4b803-113">Os valores de cadeia de caracteres usados nas configurações são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="4b803-113">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="4b803-114">Não inclua o caractere de **escape** na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4b803-114">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="4b803-115">Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="4b803-115">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="4b803-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4b803-116">EXAMPLES</span></span>

### <span data-ttu-id="4b803-117">Exemplo 1-alternar para o tema claro</span><span class="sxs-lookup"><span data-stu-id="4b803-117">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="4b803-118">Este exemplo seleciona o tema **claro** e exibe a nova configuração usando o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="4b803-118">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

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

### <span data-ttu-id="4b803-119">Exemplo 2 – personalizar as configurações de cor e estilo</span><span class="sxs-lookup"><span data-stu-id="4b803-119">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="4b803-120">Este exemplo altera o código de escape para os cabeçalhos de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-120">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="4b803-121">A configuração padrão dos cabeçalhos os renderiza como texto sublinhado de várias cores.</span><span class="sxs-lookup"><span data-stu-id="4b803-121">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="4b803-122">Essa alteração remove o estilo sublinhado.</span><span class="sxs-lookup"><span data-stu-id="4b803-122">This change removes the underline style.</span></span>

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

## <span data-ttu-id="4b803-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b803-123">PARAMETERS</span></span>

### <span data-ttu-id="4b803-124">-BoldForegroundColor</span><span class="sxs-lookup"><span data-stu-id="4b803-124">-BoldForegroundColor</span></span>

<span data-ttu-id="4b803-125">Define a cor de primeiro plano para renderizar o texto de redução em negrito.</span><span class="sxs-lookup"><span data-stu-id="4b803-125">Sets the foreground color for rendering bold Markdown text.</span></span>

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

### <span data-ttu-id="4b803-126">-Código</span><span class="sxs-lookup"><span data-stu-id="4b803-126">-Code</span></span>

<span data-ttu-id="4b803-127">Define a cor para renderizar blocos de código e abrange em texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-127">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-128">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="4b803-128">-Header1Color</span></span>

<span data-ttu-id="4b803-129">Define a cor para renderização de blocos header1 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-129">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-130">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="4b803-130">-Header2Color</span></span>

<span data-ttu-id="4b803-131">Define a cor para renderização de blocos Header2 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-131">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-132">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="4b803-132">-Header3Color</span></span>

<span data-ttu-id="4b803-133">Define a cor para renderização de blocos Header3 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-133">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-134">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="4b803-134">-Header4Color</span></span>

<span data-ttu-id="4b803-135">Define a cor para renderização de blocos Header4 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-135">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-136">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="4b803-136">-Header5Color</span></span>

<span data-ttu-id="4b803-137">Define a cor para renderização de blocos Header5 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-137">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-138">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="4b803-138">-Header6Color</span></span>

<span data-ttu-id="4b803-139">Define a cor para renderização de blocos Header6 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-139">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-140">-ImageAltTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="4b803-140">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="4b803-141">Define a cor de primeiro plano para renderizar o texto alternativo de um elemento Image no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-141">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4b803-142">-InputObject</span></span>

<span data-ttu-id="4b803-143">Um objeto **PSMarkdownOptionInfo** que contém a configuração a ser definida.</span><span class="sxs-lookup"><span data-stu-id="4b803-143">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

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

### <span data-ttu-id="4b803-144">-ItalicsForegroundColor</span><span class="sxs-lookup"><span data-stu-id="4b803-144">-ItalicsForegroundColor</span></span>

<span data-ttu-id="4b803-145">Define a cor de primeiro plano para renderizar os itálicos no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-145">Sets the foreground color for rendering the italics in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-146">-LinkForegroundColor</span><span class="sxs-lookup"><span data-stu-id="4b803-146">-LinkForegroundColor</span></span>

<span data-ttu-id="4b803-147">Define a cor de primeiro plano para renderizar hiperlinks no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="4b803-147">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

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

### <span data-ttu-id="4b803-148">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4b803-148">-PassThru</span></span>

<span data-ttu-id="4b803-149">Faz com que o cmdlet gere um objeto **PSMarkdownOptionInfo** contendo a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="4b803-149">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="4b803-150">-Tema</span><span class="sxs-lookup"><span data-stu-id="4b803-150">-Theme</span></span>

<span data-ttu-id="4b803-151">Seleciona um tema que contém configurações de cores predefinidas.</span><span class="sxs-lookup"><span data-stu-id="4b803-151">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="4b803-152">Os valores possíveis são **escuro** e **claro**.</span><span class="sxs-lookup"><span data-stu-id="4b803-152">The possible values are **Dark** and **Light**.</span></span>

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

### <span data-ttu-id="4b803-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4b803-153">CommonParameters</span></span>

<span data-ttu-id="4b803-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b803-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b803-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b803-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b803-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4b803-156">INPUTS</span></span>

### <span data-ttu-id="4b803-157">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="4b803-157">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="4b803-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4b803-158">OUTPUTS</span></span>

### <span data-ttu-id="4b803-159">Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="4b803-159">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="4b803-160">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4b803-160">NOTES</span></span>

<span data-ttu-id="4b803-161">Os valores de cadeia de caracteres usados para definir a cor e o estilo devem corresponder à expressão regular `^\[*[0-9;]*?m{1}` .</span><span class="sxs-lookup"><span data-stu-id="4b803-161">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="4b803-162">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4b803-162">RELATED LINKS</span></span>

[<span data-ttu-id="4b803-163">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="4b803-163">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="4b803-164">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="4b803-164">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="4b803-165">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="4b803-165">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="4b803-166">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="4b803-166">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="4b803-167">CommonMark</span><span class="sxs-lookup"><span data-stu-id="4b803-167">CommonMark</span></span>](https://commonmark.org/)

