---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: 01d045a6254b40161462bf36976fdbf57f205705
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596793"
---
# <span data-ttu-id="a2acf-102">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a2acf-102">Write-Host</span></span>

## <span data-ttu-id="a2acf-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a2acf-103">SYNOPSIS</span></span>

<span data-ttu-id="a2acf-104">Grava a saída personalizada em um host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-104">Writes customized output to a host.</span></span>

## <span data-ttu-id="a2acf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2acf-105">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="a2acf-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2acf-106">DESCRIPTION</span></span>

<span data-ttu-id="a2acf-107">A `Write-Host` principal finalidade do cmdlet é produzir uma saída de-(host)-somente exibição, como a impressão de texto colorido, como ao solicitar a entrada do usuário em conjunto com o [Read-Host](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="a2acf-107">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="a2acf-108">`Write-Host` usa o método [ToString ()](/dotnet/api/system.object.tostring) para gravar a saída.</span><span class="sxs-lookup"><span data-stu-id="a2acf-108">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="a2acf-109">Por outro lado, para gerar dados de saída para o pipeline, use [Write-Output](Write-Output.md) ou saída implícita.</span><span class="sxs-lookup"><span data-stu-id="a2acf-109">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="a2acf-110">Você pode especificar a cor do texto usando o `ForegroundColor` parâmetro e pode especificar a cor do plano de fundo usando o `BackgroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a2acf-110">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="a2acf-111">O parâmetro separador permite que você especifique uma cadeia de caracteres a ser usada para separar os objetos exibidos.</span><span class="sxs-lookup"><span data-stu-id="a2acf-111">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="a2acf-112">O resultado específico depende do programa que está hospedando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2acf-112">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="a2acf-113">A partir do Windows PowerShell 5,0, `Write-Host` é um wrapper para `Write-Information` isso permite que você use `Write-Host` para emitir a saída para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="a2acf-113">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="a2acf-114">Isso permite a **captura** ou **supressão** de dados gravados usando `Write-Host` enquanto preserva a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="a2acf-114">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="a2acf-115">A `$InformationPreference` variável de preferência e o `InformationAction` parâmetro comum não afetam `Write-Host` as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a2acf-115">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="a2acf-116">A exceção a essa regra é `-InformationAction Ignore` , que suprime efetivamente a `Write-Host` saída.</span><span class="sxs-lookup"><span data-stu-id="a2acf-116">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="a2acf-117">(consulte o "exemplo 5")</span><span class="sxs-lookup"><span data-stu-id="a2acf-117">(see "Example 5")</span></span>

## <span data-ttu-id="a2acf-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a2acf-118">EXAMPLES</span></span>

### <span data-ttu-id="a2acf-119">Exemplo 1: gravar no console sem adicionar uma nova linha</span><span class="sxs-lookup"><span data-stu-id="a2acf-119">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="a2acf-120">Este comando exibe a cadeia de caracteres "nenhum teste de nova linha" com o `NoNewline` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a2acf-120">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="a2acf-121">Uma segunda cadeia de caracteres é gravada, mas termina na mesma linha que a primeira, devido à ausência de uma linhagem separando as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2acf-121">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="a2acf-122">Exemplo 2: gravar no console e incluir um separador</span><span class="sxs-lookup"><span data-stu-id="a2acf-122">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Esse comando exibe os números pares de dois a doze. <span data-ttu-id="a2acf-124">O parâmetro **Separator** é usado para adicionar a cadeia de caracteres `, +2= ` (vírgula, espaço,,, `+` `2` `=` , espaço).</span><span class="sxs-lookup"><span data-stu-id="a2acf-124">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="a2acf-125">Exemplo 3: escrever com cores de texto e de plano de fundo diferentes</span><span class="sxs-lookup"><span data-stu-id="a2acf-125">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="a2acf-126">Esse comando exibe os números pares de dois a doze.</span><span class="sxs-lookup"><span data-stu-id="a2acf-126">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="a2acf-127">Ele usa o `ForegroundColor` parâmetro para gerar texto verde escuro e o `BackgroundColor` parâmetro para exibir um plano de fundo branco.</span><span class="sxs-lookup"><span data-stu-id="a2acf-127">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="a2acf-128">Exemplo 4: escrever com cores de texto e de plano de fundo diferentes</span><span class="sxs-lookup"><span data-stu-id="a2acf-128">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="a2acf-129">Este comando exibe a cadeia de caracteres "Texto vermelho sobre branco".</span><span class="sxs-lookup"><span data-stu-id="a2acf-129">This command displays the string "Red on white text."</span></span> <span data-ttu-id="a2acf-130">O texto é vermelho, conforme definido pelo `ForegroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a2acf-130">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="a2acf-131">O plano de fundo é branco, conforme definido pelo `BackgroundColor` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a2acf-131">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="a2acf-132">Exemplo 5: suprimir a saída de Write-Host</span><span class="sxs-lookup"><span data-stu-id="a2acf-132">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="a2acf-133">Esses comandos suprimim efetivamente a saída do `Write-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2acf-133">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="a2acf-134">A primeira usa o `InformationAction` parâmetro com o `Ignore` valor para suprimir a saída para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="a2acf-134">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="a2acf-135">O segundo exemplo redireciona o fluxo de informações do comando para a `$null` variável e, portanto, a suprime.</span><span class="sxs-lookup"><span data-stu-id="a2acf-135">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="a2acf-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2acf-136">PARAMETERS</span></span>

### <span data-ttu-id="a2acf-137">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="a2acf-137">-BackgroundColor</span></span>

<span data-ttu-id="a2acf-138">Especifica a cor do plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="a2acf-138">Specifies the background color.</span></span> <span data-ttu-id="a2acf-139">Não há nenhum padrão.</span><span class="sxs-lookup"><span data-stu-id="a2acf-139">There is no default.</span></span> <span data-ttu-id="a2acf-140">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a2acf-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a2acf-141">Preto</span><span class="sxs-lookup"><span data-stu-id="a2acf-141">Black</span></span>
- <span data-ttu-id="a2acf-142">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="a2acf-142">DarkBlue</span></span>
- <span data-ttu-id="a2acf-143">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="a2acf-143">DarkGreen</span></span>
- <span data-ttu-id="a2acf-144">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="a2acf-144">DarkCyan</span></span>
- <span data-ttu-id="a2acf-145">DarkRed</span><span class="sxs-lookup"><span data-stu-id="a2acf-145">DarkRed</span></span>
- <span data-ttu-id="a2acf-146">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="a2acf-146">DarkMagenta</span></span>
- <span data-ttu-id="a2acf-147">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="a2acf-147">DarkYellow</span></span>
- <span data-ttu-id="a2acf-148">Cinza</span><span class="sxs-lookup"><span data-stu-id="a2acf-148">Gray</span></span>
- <span data-ttu-id="a2acf-149">DarkGray</span><span class="sxs-lookup"><span data-stu-id="a2acf-149">DarkGray</span></span>
- <span data-ttu-id="a2acf-150">Azul</span><span class="sxs-lookup"><span data-stu-id="a2acf-150">Blue</span></span>
- <span data-ttu-id="a2acf-151">Verde</span><span class="sxs-lookup"><span data-stu-id="a2acf-151">Green</span></span>
- <span data-ttu-id="a2acf-152">Cores</span><span class="sxs-lookup"><span data-stu-id="a2acf-152">Cyan</span></span>
- <span data-ttu-id="a2acf-153">Vermelho</span><span class="sxs-lookup"><span data-stu-id="a2acf-153">Red</span></span>
- <span data-ttu-id="a2acf-154">Magenta</span><span class="sxs-lookup"><span data-stu-id="a2acf-154">Magenta</span></span>
- <span data-ttu-id="a2acf-155">Amarelo</span><span class="sxs-lookup"><span data-stu-id="a2acf-155">Yellow</span></span>
- <span data-ttu-id="a2acf-156">Branca</span><span class="sxs-lookup"><span data-stu-id="a2acf-156">White</span></span>

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

### <span data-ttu-id="a2acf-157">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="a2acf-157">-ForegroundColor</span></span>

<span data-ttu-id="a2acf-158">Especifica a cor do texto.</span><span class="sxs-lookup"><span data-stu-id="a2acf-158">Specifies the text color.</span></span> <span data-ttu-id="a2acf-159">Não há nenhum padrão.</span><span class="sxs-lookup"><span data-stu-id="a2acf-159">There is no default.</span></span> <span data-ttu-id="a2acf-160">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a2acf-160">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a2acf-161">Preto</span><span class="sxs-lookup"><span data-stu-id="a2acf-161">Black</span></span>
- <span data-ttu-id="a2acf-162">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="a2acf-162">DarkBlue</span></span>
- <span data-ttu-id="a2acf-163">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="a2acf-163">DarkGreen</span></span>
- <span data-ttu-id="a2acf-164">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="a2acf-164">DarkCyan</span></span>
- <span data-ttu-id="a2acf-165">DarkRed</span><span class="sxs-lookup"><span data-stu-id="a2acf-165">DarkRed</span></span>
- <span data-ttu-id="a2acf-166">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="a2acf-166">DarkMagenta</span></span>
- <span data-ttu-id="a2acf-167">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="a2acf-167">DarkYellow</span></span>
- <span data-ttu-id="a2acf-168">Cinza</span><span class="sxs-lookup"><span data-stu-id="a2acf-168">Gray</span></span>
- <span data-ttu-id="a2acf-169">DarkGray</span><span class="sxs-lookup"><span data-stu-id="a2acf-169">DarkGray</span></span>
- <span data-ttu-id="a2acf-170">Azul</span><span class="sxs-lookup"><span data-stu-id="a2acf-170">Blue</span></span>
- <span data-ttu-id="a2acf-171">Verde</span><span class="sxs-lookup"><span data-stu-id="a2acf-171">Green</span></span>
- <span data-ttu-id="a2acf-172">Cores</span><span class="sxs-lookup"><span data-stu-id="a2acf-172">Cyan</span></span>
- <span data-ttu-id="a2acf-173">Vermelho</span><span class="sxs-lookup"><span data-stu-id="a2acf-173">Red</span></span>
- <span data-ttu-id="a2acf-174">Magenta</span><span class="sxs-lookup"><span data-stu-id="a2acf-174">Magenta</span></span>
- <span data-ttu-id="a2acf-175">Amarelo</span><span class="sxs-lookup"><span data-stu-id="a2acf-175">Yellow</span></span>
- <span data-ttu-id="a2acf-176">Branca</span><span class="sxs-lookup"><span data-stu-id="a2acf-176">White</span></span>

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

### <span data-ttu-id="a2acf-177">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="a2acf-177">-NoNewline</span></span>

<span data-ttu-id="a2acf-178">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="a2acf-178">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="a2acf-179">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="a2acf-179">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="a2acf-180">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="a2acf-180">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="a2acf-181">-Objeto</span><span class="sxs-lookup"><span data-stu-id="a2acf-181">-Object</span></span>

<span data-ttu-id="a2acf-182">Objetos a serem exibidos no host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-182">Objects to display in the host.</span></span>

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

### <span data-ttu-id="a2acf-183">-Separador</span><span class="sxs-lookup"><span data-stu-id="a2acf-183">-Separator</span></span>

<span data-ttu-id="a2acf-184">Especifica uma cadeia de caracteres separadora a ser inserida entre os objetos exibidos pelo host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-184">Specifies a separator string to insert between objects displayed by the host.</span></span>

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

### <span data-ttu-id="a2acf-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2acf-185">CommonParameters</span></span>
<span data-ttu-id="a2acf-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2acf-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2acf-187">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2acf-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2acf-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a2acf-188">INPUTS</span></span>

### <span data-ttu-id="a2acf-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="a2acf-189">System.Object</span></span>

<span data-ttu-id="a2acf-190">É possível redirecionar objetos a serem gravados no host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-190">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="a2acf-191">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a2acf-191">OUTPUTS</span></span>

### <span data-ttu-id="a2acf-192">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a2acf-192">None</span></span>

<span data-ttu-id="a2acf-193">`Write-Host` envia os objetos para o host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-193">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="a2acf-194">Ele não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="a2acf-194">It does not return any objects.</span></span> <span data-ttu-id="a2acf-195">No entanto, o host exibe os objetos que `Write-Host` enviam a ele.</span><span class="sxs-lookup"><span data-stu-id="a2acf-195">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="a2acf-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a2acf-196">NOTES</span></span>

- <span data-ttu-id="a2acf-197">Ao gravar uma coleção no host, os elementos da coleção são impressos na mesma linha separada por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="a2acf-197">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="a2acf-198">Isso pode ser substituído pelo parâmetro **Separator** .</span><span class="sxs-lookup"><span data-stu-id="a2acf-198">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="a2acf-199">Tipos de dados não primitivos, como objetos com propriedades, podem causar resultados inesperados e não fornecem uma saída significativa.</span><span class="sxs-lookup"><span data-stu-id="a2acf-199">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="a2acf-200">Por exemplo, `Write-Host @{a = 1; b = 2}` será impresso no `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` host.</span><span class="sxs-lookup"><span data-stu-id="a2acf-200">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="a2acf-201">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a2acf-201">RELATED LINKS</span></span>

[<span data-ttu-id="a2acf-202">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="a2acf-202">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="a2acf-203">Out-Host</span><span class="sxs-lookup"><span data-stu-id="a2acf-203">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="a2acf-204">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a2acf-204">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="a2acf-205">Write-Error</span><span class="sxs-lookup"><span data-stu-id="a2acf-205">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="a2acf-206">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a2acf-206">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="a2acf-207">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a2acf-207">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="a2acf-208">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a2acf-208">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="a2acf-209">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a2acf-209">Write-Warning</span></span>](Write-Warning.md)
