---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 59e5b728604ce37f27b56ebe62e1a22d6af8a966
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "99597003"
---
# <span data-ttu-id="1d5b6-102">Out-String</span><span class="sxs-lookup"><span data-stu-id="1d5b6-102">Out-String</span></span>

## <span data-ttu-id="1d5b6-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="1d5b6-103">Synopsis</span></span>
<span data-ttu-id="1d5b6-104">Gera objetos de entrada como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-104">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="1d5b6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d5b6-105">Syntax</span></span>

### <span data-ttu-id="1d5b6-106">NoNewLineFormatting (padrão)</span><span class="sxs-lookup"><span data-stu-id="1d5b6-106">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="1d5b6-107">StreamFormatting</span><span class="sxs-lookup"><span data-stu-id="1d5b6-107">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="1d5b6-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d5b6-108">Description</span></span>

<span data-ttu-id="1d5b6-109">O `Out-String` cmdlet converte objetos de entrada em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-109">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="1d5b6-110">Por padrão, `Out-String` o acumula as cadeias de caracteres e as retorna como uma única cadeia de caracteres, mas você pode usar o parâmetro **Stream** para direcionar `Out-String` para retornar uma linha de cada vez ou criar e matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-110">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="1d5b6-111">Esse cmdlet permite pesquisar e manipular a saída da cadeia de caracteres como faria em shells tradicionais quando a manipulação de objetos for menos conveniente.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-111">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="1d5b6-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1d5b6-112">Examples</span></span>

### <span data-ttu-id="1d5b6-113">Exemplo 1: obter a cultura atual e converter os dados em cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="1d5b6-113">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="1d5b6-114">Este exemplo obtém as configurações regionais para o usuário atual e converte os dados do objeto em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-114">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

<span data-ttu-id="1d5b6-115">A `$C` variável armazena um **Selected.System. Objeto Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-115">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="1d5b6-116">O objeto é o resultado do `Get-Culture` envio da saída para baixo do pipeline para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-116">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="1d5b6-117">O parâmetro **Property** usa um curinga asterisco ( `*` ) para especificar que todas as propriedades estão contidas no objeto.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-117">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="1d5b6-118">`Out-String` usa o parâmetro **InputObject** para especificar o objeto **CultureInfo** armazenado na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-118">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="1d5b6-119">Os objetos no `$C` são convertidos em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-119">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="1d5b6-120">Para exibir a `Out-String` matriz, armazene a saída em uma variável e use um índice de matriz para exibir os elementos.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-120">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="1d5b6-121">Para obter mais informações sobre o índice de matriz, consulte [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="1d5b6-121">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="1d5b6-122">Exemplo 2: trabalhando com objetos</span><span class="sxs-lookup"><span data-stu-id="1d5b6-122">Example 2: Working with objects</span></span>

<span data-ttu-id="1d5b6-123">Este exemplo demonstra a diferença entre trabalhar com objetos e trabalhar com cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-123">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="1d5b6-124">O comando exibe um alias que inclui o texto **GCM**, o alias para `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-124">The command displays an alias that includes the text **gcm**, the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="1d5b6-125">`Get-Alias` Obtém os objetos **System. Management. Automation. AliasInfo** , um para cada alias e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-125">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="1d5b6-126">`Out-String` usa o parâmetro **Stream** para converter cada objeto em uma cadeia de caracteres, em vez de concatenar todos os objetos em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-126">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="1d5b6-127">Os objetos **System. String** são enviados pelo pipeline e `Select-String` usam o parâmetro **Pattern** para localizar correspondências para o texto **GCM**.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-127">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d5b6-128">Se você omitir o parâmetro de **fluxo** , o comando exibirá todos os aliases, pois `Select-String` localiza o texto **GCM** na cadeia de caracteres única que `Out-String` retorna.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-128">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="1d5b6-129">Exemplo 3: Use o parâmetro Width para evitar truncamento.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-129">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="1d5b6-130">Embora a maior parte da saída `Out-String` seja encapsulada na próxima linha, há cenários em que a saída é truncada pelo sistema de formatação antes de ser passada para `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-130">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="1d5b6-131">Você pode evitar o truncamento usando o parâmetro **Width** .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-131">You can avoid truncation using the **Width** parameter.</span></span>

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## <span data-ttu-id="1d5b6-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d5b6-132">PARAMETERS</span></span>

### <span data-ttu-id="1d5b6-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1d5b6-133">-InputObject</span></span>

<span data-ttu-id="1d5b6-134">Especifica os objetos a serem gravados em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-134">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="1d5b6-135">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-135">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1d5b6-136">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="1d5b6-136">-NoNewline</span></span>

<span data-ttu-id="1d5b6-137">Remove todas as novas linhas da saída geradas pelo formatador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-137">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="1d5b6-138">Novas linhas que fazem parte dos objetos de cadeia de caracteres são preservadas.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-138">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="1d5b6-139">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-139">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5b6-140">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="1d5b6-140">-Stream</span></span>

<span data-ttu-id="1d5b6-141">Por padrão, `Out-String` o gera uma única cadeia de caracteres formatada como você a veria no console, incluindo todos os cabeçalhos em branco ou novas linhas à direita.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-141">By default, `Out-String` outputs a single string formatted as you would see it in the console including any blank headers or trailing newlines.</span></span> <span data-ttu-id="1d5b6-142">O parâmetro de **fluxo** permite `Out-String` a saída de cada linha uma a uma.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-142">The **Stream** parameter enables `Out-String` to output each line one by one.</span></span> <span data-ttu-id="1d5b6-143">A única exceção a isso são as cadeias de caracteres multilinha.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-143">The only exception to this are multiline strings.</span></span> <span data-ttu-id="1d5b6-144">Nesse caso, `Out-String` o ainda produzirá a cadeia de caracteres como uma única cadeia de caracteres de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-144">In that case, `Out-String` will still output the string as a single, multiline string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5b6-145">-Largura</span><span class="sxs-lookup"><span data-stu-id="1d5b6-145">-Width</span></span>

<span data-ttu-id="1d5b6-146">Especifica o número de caracteres em cada linha de saída.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-146">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="1d5b6-147">Quaisquer caracteres adicionais são encapsulados na próxima linha ou truncados, dependendo do cmdlet do formatador usado.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-147">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="1d5b6-148">O parâmetro **Width** aplica-se somente a objetos que estão sendo formatados.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-148">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="1d5b6-149">Se você omitir esse parâmetro, a largura será determinada pelas características do programa host.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-149">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="1d5b6-150">Em janelas de terminal (console), a largura da janela atual é usada como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-150">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="1d5b6-151">O console do PowerShell Windows tem como padrão uma largura de 80 caracteres na instalação.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-151">PowerShell console windows default to a width of 80 characters on installation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5b6-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1d5b6-152">CommonParameters</span></span>

<span data-ttu-id="1d5b6-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d5b6-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d5b6-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d5b6-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1d5b6-155">INPUTS</span></span>

### <span data-ttu-id="1d5b6-156">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="1d5b6-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1d5b6-157">Você pode enviar objetos pelo pipeline para o `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="1d5b6-157">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="1d5b6-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1d5b6-158">OUTPUTS</span></span>

### <span data-ttu-id="1d5b6-159">System.String</span><span class="sxs-lookup"><span data-stu-id="1d5b6-159">System.String</span></span>

<span data-ttu-id="1d5b6-160">`Out-String` Retorna a cadeia de caracteres que ele cria do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-160">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="1d5b6-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1d5b6-161">NOTES</span></span>

<span data-ttu-id="1d5b6-162">Os cmdlets que contêm o `Out` verbo não formatam objetos.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-162">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="1d5b6-163">Os `Out` cmdlets enviam objetos para o formatador para o destino de exibição especificado.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-163">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="1d5b6-164">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1d5b6-164">RELATED LINKS</span></span>

[<span data-ttu-id="1d5b6-165">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="1d5b6-165">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="1d5b6-166">Out-Default</span><span class="sxs-lookup"><span data-stu-id="1d5b6-166">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="1d5b6-167">Out-File</span><span class="sxs-lookup"><span data-stu-id="1d5b6-167">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="1d5b6-168">Out-Host</span><span class="sxs-lookup"><span data-stu-id="1d5b6-168">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="1d5b6-169">Out-Null</span><span class="sxs-lookup"><span data-stu-id="1d5b6-169">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="1d5b6-170">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="1d5b6-170">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="1d5b6-171">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="1d5b6-171">Out-Printer</span></span>](Out-Printer.md)
