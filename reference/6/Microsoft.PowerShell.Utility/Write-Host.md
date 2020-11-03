---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: f0b7542d551fa0dbbdec186980dcdb7ac600b60c
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "93195318"
---
# <span data-ttu-id="b67be-103">Write-Host</span><span class="sxs-lookup"><span data-stu-id="b67be-103">Write-Host</span></span>

## <span data-ttu-id="b67be-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b67be-104">SYNOPSIS</span></span>

<span data-ttu-id="b67be-105">Grava a saída personalizada em um host.</span><span class="sxs-lookup"><span data-stu-id="b67be-105">Writes customized output to a host.</span></span>

## <span data-ttu-id="b67be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b67be-106">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="b67be-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b67be-107">DESCRIPTION</span></span>

<span data-ttu-id="b67be-108">A `Write-Host` principal finalidade do cmdlet é produzir uma saída de-(host)-somente exibição, como a impressão de texto colorido, como ao solicitar a entrada do usuário em conjunto com o [Read-Host](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="b67be-108">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="b67be-109">`Write-Host` usa o método [ToString ()](/dotnet/api/system.object.tostring) para gravar a saída.</span><span class="sxs-lookup"><span data-stu-id="b67be-109">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="b67be-110">Por outro lado, para gerar dados de saída para o pipeline, use [Write-Output](Write-Output.md) ou saída implícita.</span><span class="sxs-lookup"><span data-stu-id="b67be-110">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="b67be-111">Você pode especificar a cor do texto usando o `ForegroundColor` parâmetro e pode especificar a cor do plano de fundo usando o `BackgroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b67be-111">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="b67be-112">O parâmetro separador permite que você especifique uma cadeia de caracteres a ser usada para separar os objetos exibidos.</span><span class="sxs-lookup"><span data-stu-id="b67be-112">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="b67be-113">O resultado específico depende do programa que está hospedando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b67be-113">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b67be-114">A partir do Windows PowerShell 5,0, `Write-Host` é um wrapper para `Write-Information` isso permite que você use `Write-Host` para emitir a saída para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="b67be-114">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="b67be-115">Isso permite a **captura** ou **supressão** de dados gravados usando `Write-Host` enquanto preserva a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b67be-115">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="b67be-116">A `$InformationPreference` variável de preferência e o `InformationAction` parâmetro comum não afetam `Write-Host` as mensagens.</span><span class="sxs-lookup"><span data-stu-id="b67be-116">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="b67be-117">A exceção a essa regra é `-InformationAction Ignore` , que suprime efetivamente a `Write-Host` saída.</span><span class="sxs-lookup"><span data-stu-id="b67be-117">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="b67be-118">(consulte o "exemplo 5")</span><span class="sxs-lookup"><span data-stu-id="b67be-118">(see "Example 5")</span></span>

## <span data-ttu-id="b67be-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b67be-119">EXAMPLES</span></span>

### <span data-ttu-id="b67be-120">Exemplo 1: gravar no console sem adicionar uma nova linha</span><span class="sxs-lookup"><span data-stu-id="b67be-120">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="b67be-121">Este comando exibe a cadeia de caracteres "nenhum teste de nova linha" com o `NoNewline` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b67be-121">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="b67be-122">Uma segunda cadeia de caracteres é gravada, mas termina na mesma linha que a primeira, devido à ausência de uma linhagem separando as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b67be-122">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="b67be-123">Exemplo 2: gravar no console e incluir um separador</span><span class="sxs-lookup"><span data-stu-id="b67be-123">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Esse comando exibe os números pares de dois a doze. <span data-ttu-id="b67be-125">O parâmetro **Separator** é usado para adicionar a cadeia de caracteres `, +2= ` (vírgula, espaço,,, `+` `2` `=` , espaço).</span><span class="sxs-lookup"><span data-stu-id="b67be-125">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="b67be-126">Exemplo 3: escrever com cores de texto e de plano de fundo diferentes</span><span class="sxs-lookup"><span data-stu-id="b67be-126">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="b67be-127">Esse comando exibe os números pares de dois a doze.</span><span class="sxs-lookup"><span data-stu-id="b67be-127">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="b67be-128">Ele usa o `ForegroundColor` parâmetro para gerar texto verde escuro e o `BackgroundColor` parâmetro para exibir um plano de fundo branco.</span><span class="sxs-lookup"><span data-stu-id="b67be-128">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="b67be-129">Exemplo 4: escrever com cores de texto e de plano de fundo diferentes</span><span class="sxs-lookup"><span data-stu-id="b67be-129">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="b67be-130">Este comando exibe a cadeia de caracteres "Texto vermelho sobre branco".</span><span class="sxs-lookup"><span data-stu-id="b67be-130">This command displays the string "Red on white text."</span></span> <span data-ttu-id="b67be-131">O texto é vermelho, conforme definido pelo `ForegroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b67be-131">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="b67be-132">O plano de fundo é branco, conforme definido pelo `BackgroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b67be-132">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="b67be-133">Exemplo 5: suprimir a saída de Write-Host</span><span class="sxs-lookup"><span data-stu-id="b67be-133">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="b67be-134">Esses comandos suprimim efetivamente a saída do `Write-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b67be-134">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="b67be-135">A primeira usa o `InformationAction` parâmetro com o `Ignore` valor para suprimir a saída para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="b67be-135">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="b67be-136">O segundo exemplo redireciona o fluxo de informações do comando para a `$null` variável e, portanto, a suprime.</span><span class="sxs-lookup"><span data-stu-id="b67be-136">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="b67be-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b67be-137">PARAMETERS</span></span>

### <span data-ttu-id="b67be-138">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="b67be-138">-BackgroundColor</span></span>

<span data-ttu-id="b67be-139">Especifica a cor do plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="b67be-139">Specifies the background color.</span></span> <span data-ttu-id="b67be-140">Não há nenhum padrão.</span><span class="sxs-lookup"><span data-stu-id="b67be-140">There is no default.</span></span> <span data-ttu-id="b67be-141">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b67be-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b67be-142">Preto</span><span class="sxs-lookup"><span data-stu-id="b67be-142">Black</span></span>
- <span data-ttu-id="b67be-143">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="b67be-143">DarkBlue</span></span>
- <span data-ttu-id="b67be-144">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="b67be-144">DarkGreen</span></span>
- <span data-ttu-id="b67be-145">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="b67be-145">DarkCyan</span></span>
- <span data-ttu-id="b67be-146">DarkRed</span><span class="sxs-lookup"><span data-stu-id="b67be-146">DarkRed</span></span>
- <span data-ttu-id="b67be-147">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="b67be-147">DarkMagenta</span></span>
- <span data-ttu-id="b67be-148">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="b67be-148">DarkYellow</span></span>
- <span data-ttu-id="b67be-149">Cinza</span><span class="sxs-lookup"><span data-stu-id="b67be-149">Gray</span></span>
- <span data-ttu-id="b67be-150">DarkGray</span><span class="sxs-lookup"><span data-stu-id="b67be-150">DarkGray</span></span>
- <span data-ttu-id="b67be-151">Azul</span><span class="sxs-lookup"><span data-stu-id="b67be-151">Blue</span></span>
- <span data-ttu-id="b67be-152">Verde</span><span class="sxs-lookup"><span data-stu-id="b67be-152">Green</span></span>
- <span data-ttu-id="b67be-153">Cores</span><span class="sxs-lookup"><span data-stu-id="b67be-153">Cyan</span></span>
- <span data-ttu-id="b67be-154">Vermelho</span><span class="sxs-lookup"><span data-stu-id="b67be-154">Red</span></span>
- <span data-ttu-id="b67be-155">Magenta</span><span class="sxs-lookup"><span data-stu-id="b67be-155">Magenta</span></span>
- <span data-ttu-id="b67be-156">Amarelo</span><span class="sxs-lookup"><span data-stu-id="b67be-156">Yellow</span></span>
- <span data-ttu-id="b67be-157">Branco</span><span class="sxs-lookup"><span data-stu-id="b67be-157">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b67be-158">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="b67be-158">-ForegroundColor</span></span>

<span data-ttu-id="b67be-159">Especifica a cor do texto.</span><span class="sxs-lookup"><span data-stu-id="b67be-159">Specifies the text color.</span></span> <span data-ttu-id="b67be-160">Não há nenhum padrão.</span><span class="sxs-lookup"><span data-stu-id="b67be-160">There is no default.</span></span> <span data-ttu-id="b67be-161">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b67be-161">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b67be-162">Preto</span><span class="sxs-lookup"><span data-stu-id="b67be-162">Black</span></span>
- <span data-ttu-id="b67be-163">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="b67be-163">DarkBlue</span></span>
- <span data-ttu-id="b67be-164">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="b67be-164">DarkGreen</span></span>
- <span data-ttu-id="b67be-165">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="b67be-165">DarkCyan</span></span>
- <span data-ttu-id="b67be-166">DarkRed</span><span class="sxs-lookup"><span data-stu-id="b67be-166">DarkRed</span></span>
- <span data-ttu-id="b67be-167">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="b67be-167">DarkMagenta</span></span>
- <span data-ttu-id="b67be-168">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="b67be-168">DarkYellow</span></span>
- <span data-ttu-id="b67be-169">Cinza</span><span class="sxs-lookup"><span data-stu-id="b67be-169">Gray</span></span>
- <span data-ttu-id="b67be-170">DarkGray</span><span class="sxs-lookup"><span data-stu-id="b67be-170">DarkGray</span></span>
- <span data-ttu-id="b67be-171">Azul</span><span class="sxs-lookup"><span data-stu-id="b67be-171">Blue</span></span>
- <span data-ttu-id="b67be-172">Verde</span><span class="sxs-lookup"><span data-stu-id="b67be-172">Green</span></span>
- <span data-ttu-id="b67be-173">Cores</span><span class="sxs-lookup"><span data-stu-id="b67be-173">Cyan</span></span>
- <span data-ttu-id="b67be-174">Vermelho</span><span class="sxs-lookup"><span data-stu-id="b67be-174">Red</span></span>
- <span data-ttu-id="b67be-175">Magenta</span><span class="sxs-lookup"><span data-stu-id="b67be-175">Magenta</span></span>
- <span data-ttu-id="b67be-176">Amarelo</span><span class="sxs-lookup"><span data-stu-id="b67be-176">Yellow</span></span>
- <span data-ttu-id="b67be-177">Branco</span><span class="sxs-lookup"><span data-stu-id="b67be-177">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b67be-178">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="b67be-178">-NoNewline</span></span>

<span data-ttu-id="b67be-179">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="b67be-179">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="b67be-180">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="b67be-180">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="b67be-181">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="b67be-181">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="b67be-182">-Objeto</span><span class="sxs-lookup"><span data-stu-id="b67be-182">-Object</span></span>

<span data-ttu-id="b67be-183">Objetos a serem exibidos no host.</span><span class="sxs-lookup"><span data-stu-id="b67be-183">Objects to display in the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b67be-184">-Separador</span><span class="sxs-lookup"><span data-stu-id="b67be-184">-Separator</span></span>

<span data-ttu-id="b67be-185">Especifica uma cadeia de caracteres separadora a ser inserida entre os objetos exibidos pelo host.</span><span class="sxs-lookup"><span data-stu-id="b67be-185">Specifies a separator string to insert between objects displayed by the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b67be-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b67be-186">CommonParameters</span></span>
<span data-ttu-id="b67be-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b67be-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b67be-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b67be-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b67be-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b67be-189">INPUTS</span></span>

### <span data-ttu-id="b67be-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="b67be-190">System.Object</span></span>

<span data-ttu-id="b67be-191">É possível redirecionar objetos a serem gravados no host.</span><span class="sxs-lookup"><span data-stu-id="b67be-191">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="b67be-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b67be-192">OUTPUTS</span></span>

### <span data-ttu-id="b67be-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b67be-193">None</span></span>

<span data-ttu-id="b67be-194">`Write-Host` envia os objetos para o host.</span><span class="sxs-lookup"><span data-stu-id="b67be-194">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="b67be-195">Ele não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="b67be-195">It does not return any objects.</span></span> <span data-ttu-id="b67be-196">No entanto, o host exibe os objetos que `Write-Host` enviam a ele.</span><span class="sxs-lookup"><span data-stu-id="b67be-196">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="b67be-197">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b67be-197">NOTES</span></span>

- <span data-ttu-id="b67be-198">Ao gravar uma coleção no host, os elementos da coleção são impressos na mesma linha separada por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="b67be-198">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="b67be-199">Isso pode ser substituído pelo parâmetro **Separator** .</span><span class="sxs-lookup"><span data-stu-id="b67be-199">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="b67be-200">Tipos de dados não primitivos, como objetos com propriedades, podem causar resultados inesperados e não fornecem uma saída significativa.</span><span class="sxs-lookup"><span data-stu-id="b67be-200">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="b67be-201">Por exemplo, `Write-Host @{a = 1; b = 2}` será impresso no `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` host.</span><span class="sxs-lookup"><span data-stu-id="b67be-201">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="b67be-202">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b67be-202">RELATED LINKS</span></span>

[<span data-ttu-id="b67be-203">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="b67be-203">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="b67be-204">Out-Host</span><span class="sxs-lookup"><span data-stu-id="b67be-204">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="b67be-205">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="b67be-205">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="b67be-206">Erro de gravação</span><span class="sxs-lookup"><span data-stu-id="b67be-206">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="b67be-207">Write-Output</span><span class="sxs-lookup"><span data-stu-id="b67be-207">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="b67be-208">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="b67be-208">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="b67be-209">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="b67be-209">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="b67be-210">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="b67be-210">Write-Warning</span></span>](Write-Warning.md)
