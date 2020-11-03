---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e7e70637afcf53f84c719b489575f5267f9048b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193270"
---
# <span data-ttu-id="b03cc-101">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="b03cc-101">Set-MarkdownOption</span></span>

## <span data-ttu-id="b03cc-102">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b03cc-102">SYNOPSIS</span></span>
<span data-ttu-id="b03cc-103">Define as cores e os estilos usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="b03cc-103">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="b03cc-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b03cc-104">SYNTAX</span></span>

### <span data-ttu-id="b03cc-105">IndividualSetting (padrão)</span><span class="sxs-lookup"><span data-stu-id="b03cc-105">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="b03cc-106">Tema</span><span class="sxs-lookup"><span data-stu-id="b03cc-106">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="b03cc-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="b03cc-107">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="b03cc-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b03cc-108">DESCRIPTION</span></span>

<span data-ttu-id="b03cc-109">Define as cores e os estilos usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="b03cc-109">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="b03cc-110">Esses estilos são definidos usando códigos de escape ANSI que alteram a cor e o estilo do texto de redução que está sendo renderizado.</span><span class="sxs-lookup"><span data-stu-id="b03cc-110">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="b03cc-111">Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="b03cc-111">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="b03cc-112">Os valores de cadeia de caracteres usados nas configurações são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="b03cc-112">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="b03cc-113">Não inclua o caractere de **escape** na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b03cc-113">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="b03cc-114">Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="b03cc-114">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="b03cc-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b03cc-115">EXAMPLES</span></span>

### <span data-ttu-id="b03cc-116">Exemplo 1-alternar para o tema claro</span><span class="sxs-lookup"><span data-stu-id="b03cc-116">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="b03cc-117">Este exemplo seleciona o tema **claro** e exibe a nova configuração usando o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="b03cc-117">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

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

### <span data-ttu-id="b03cc-118">Exemplo 2 – personalizar as configurações de cor e estilo</span><span class="sxs-lookup"><span data-stu-id="b03cc-118">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="b03cc-119">Este exemplo altera o código de escape para os cabeçalhos de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-119">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="b03cc-120">A configuração padrão dos cabeçalhos os renderiza como texto sublinhado de várias cores.</span><span class="sxs-lookup"><span data-stu-id="b03cc-120">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="b03cc-121">Essa alteração remove o estilo sublinhado.</span><span class="sxs-lookup"><span data-stu-id="b03cc-121">This change removes the underline style.</span></span>

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

## <span data-ttu-id="b03cc-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b03cc-122">PARAMETERS</span></span>

### <span data-ttu-id="b03cc-123">-BoldForegroundColor</span><span class="sxs-lookup"><span data-stu-id="b03cc-123">-BoldForegroundColor</span></span>

<span data-ttu-id="b03cc-124">Define a cor de primeiro plano para renderizar o texto de redução em negrito.</span><span class="sxs-lookup"><span data-stu-id="b03cc-124">Sets the foreground color for rendering bold Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-125">-Código</span><span class="sxs-lookup"><span data-stu-id="b03cc-125">-Code</span></span>

<span data-ttu-id="b03cc-126">Define a cor para renderizar blocos de código e abrange em texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-126">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-127">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-127">-Header1Color</span></span>

<span data-ttu-id="b03cc-128">Define a cor para renderização de blocos header1 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-128">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-129">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-129">-Header2Color</span></span>

<span data-ttu-id="b03cc-130">Define a cor para renderização de blocos Header2 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-130">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-131">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-131">-Header3Color</span></span>

<span data-ttu-id="b03cc-132">Define a cor para renderização de blocos Header3 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-132">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-133">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-133">-Header4Color</span></span>

<span data-ttu-id="b03cc-134">Define a cor para renderização de blocos Header4 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-134">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-135">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-135">-Header5Color</span></span>

<span data-ttu-id="b03cc-136">Define a cor para renderização de blocos Header5 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-136">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-137">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="b03cc-137">-Header6Color</span></span>

<span data-ttu-id="b03cc-138">Define a cor para renderização de blocos Header6 no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-138">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-139">-ImageAltTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="b03cc-139">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="b03cc-140">Define a cor de primeiro plano para renderizar o texto alternativo de um elemento Image no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-140">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b03cc-141">-InputObject</span></span>

<span data-ttu-id="b03cc-142">Um objeto **PSMarkdownOptionInfo** que contém a configuração a ser definida.</span><span class="sxs-lookup"><span data-stu-id="b03cc-142">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

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

### <span data-ttu-id="b03cc-143">-ItalicsForegroundColor</span><span class="sxs-lookup"><span data-stu-id="b03cc-143">-ItalicsForegroundColor</span></span>

<span data-ttu-id="b03cc-144">Define a cor de primeiro plano para renderizar os itálicos no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-144">Sets the foreground color for rendering the italics in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-145">-LinkForegroundColor</span><span class="sxs-lookup"><span data-stu-id="b03cc-145">-LinkForegroundColor</span></span>

<span data-ttu-id="b03cc-146">Define a cor de primeiro plano para renderizar hiperlinks no texto de redução.</span><span class="sxs-lookup"><span data-stu-id="b03cc-146">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

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

### <span data-ttu-id="b03cc-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b03cc-147">-PassThru</span></span>

<span data-ttu-id="b03cc-148">Faz com que o cmdlet gere um objeto **PSMarkdownOptionInfo** contendo a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="b03cc-148">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="b03cc-149">-Tema</span><span class="sxs-lookup"><span data-stu-id="b03cc-149">-Theme</span></span>

<span data-ttu-id="b03cc-150">Seleciona um tema que contém configurações de cores predefinidas.</span><span class="sxs-lookup"><span data-stu-id="b03cc-150">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="b03cc-151">Os valores possíveis são **escuro** e **claro** .</span><span class="sxs-lookup"><span data-stu-id="b03cc-151">The possible values are **Dark** and **Light** .</span></span>

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

### <span data-ttu-id="b03cc-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b03cc-152">CommonParameters</span></span>

<span data-ttu-id="b03cc-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b03cc-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b03cc-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b03cc-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b03cc-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b03cc-155">INPUTS</span></span>

### <span data-ttu-id="b03cc-156">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="b03cc-156">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="b03cc-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b03cc-157">OUTPUTS</span></span>

### <span data-ttu-id="b03cc-158">Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="b03cc-158">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="b03cc-159">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b03cc-159">NOTES</span></span>

<span data-ttu-id="b03cc-160">Os valores de cadeia de caracteres usados para definir a cor e o estilo devem corresponder à expressão regular `^\[*[0-9;]*?m{1}` .</span><span class="sxs-lookup"><span data-stu-id="b03cc-160">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="b03cc-161">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b03cc-161">RELATED LINKS</span></span>

[<span data-ttu-id="b03cc-162">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="b03cc-162">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="b03cc-163">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="b03cc-163">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="b03cc-164">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="b03cc-164">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="b03cc-165">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="b03cc-165">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="b03cc-166">CommonMark</span><span class="sxs-lookup"><span data-stu-id="b03cc-166">CommonMark</span></span>](https://commonmark.org/)

