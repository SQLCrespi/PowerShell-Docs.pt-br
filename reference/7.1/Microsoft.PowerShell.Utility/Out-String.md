---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 16dc25e3468eaf3126b3286cfd71bfea9627c015
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "93195366"
---
# <span data-ttu-id="06932-103">Out-String</span><span class="sxs-lookup"><span data-stu-id="06932-103">Out-String</span></span>

## <span data-ttu-id="06932-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="06932-104">SYNOPSIS</span></span>
<span data-ttu-id="06932-105">Gera objetos de entrada como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-105">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="06932-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06932-106">SYNTAX</span></span>

### <span data-ttu-id="06932-107">NoNewLineFormatting (padrão)</span><span class="sxs-lookup"><span data-stu-id="06932-107">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="06932-108">StreamFormatting</span><span class="sxs-lookup"><span data-stu-id="06932-108">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="06932-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06932-109">DESCRIPTION</span></span>

<span data-ttu-id="06932-110">O `Out-String` cmdlet converte objetos de entrada em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-110">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="06932-111">Por padrão, `Out-String` o acumula as cadeias de caracteres e as retorna como uma única cadeia de caracteres, mas você pode usar o parâmetro **Stream** para direcionar `Out-String` para retornar uma linha de cada vez ou criar e matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-111">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="06932-112">Esse cmdlet permite pesquisar e manipular a saída da cadeia de caracteres como faria em shells tradicionais quando a manipulação de objetos for menos conveniente.</span><span class="sxs-lookup"><span data-stu-id="06932-112">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="06932-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="06932-113">EXAMPLES</span></span>

### <span data-ttu-id="06932-114">Exemplo 1: obter a cultura atual e converter os dados em cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="06932-114">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="06932-115">Este exemplo obtém as configurações regionais para o usuário atual e converte os dados do objeto em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-115">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

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

<span data-ttu-id="06932-116">A `$C` variável armazena um **Selected.System. Objeto Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="06932-116">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="06932-117">O objeto é o resultado do `Get-Culture` envio da saída para baixo do pipeline para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="06932-117">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="06932-118">O parâmetro **Property** usa um curinga asterisco ( `*` ) para especificar que todas as propriedades estão contidas no objeto.</span><span class="sxs-lookup"><span data-stu-id="06932-118">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="06932-119">`Out-String` usa o parâmetro **InputObject** para especificar o objeto **CultureInfo** armazenado na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="06932-119">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="06932-120">Os objetos no `$C` são convertidos em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-120">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="06932-121">Para exibir a `Out-String` matriz, armazene a saída em uma variável e use um índice de matriz para exibir os elementos.</span><span class="sxs-lookup"><span data-stu-id="06932-121">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="06932-122">Para obter mais informações sobre o índice de matriz, consulte [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="06932-122">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="06932-123">Exemplo 2: trabalhando com objetos</span><span class="sxs-lookup"><span data-stu-id="06932-123">Example 2: Working with objects</span></span>

<span data-ttu-id="06932-124">Este exemplo demonstra a diferença entre trabalhar com objetos e trabalhar com cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-124">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="06932-125">O comando exibe um alias que inclui o texto **GCM** , o alias para `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="06932-125">The command displays an alias that includes the text **gcm** , the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="06932-126">`Get-Alias` Obtém os objetos **System. Management. Automation. AliasInfo** , um para cada alias e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="06932-126">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="06932-127">`Out-String` usa o parâmetro **Stream** para converter cada objeto em uma cadeia de caracteres, em vez de concatenar todos os objetos em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-127">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="06932-128">Os objetos **System. String** são enviados pelo pipeline e `Select-String` usam o parâmetro **Pattern** para localizar correspondências para o texto **GCM** .</span><span class="sxs-lookup"><span data-stu-id="06932-128">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm** .</span></span>

> [!NOTE]
> <span data-ttu-id="06932-129">Se você omitir o parâmetro de **fluxo** , o comando exibirá todos os aliases, pois `Select-String` localiza o texto **GCM** na cadeia de caracteres única que `Out-String` retorna.</span><span class="sxs-lookup"><span data-stu-id="06932-129">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="06932-130">Exemplo 3: Use o parâmetro Width para evitar truncamento.</span><span class="sxs-lookup"><span data-stu-id="06932-130">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="06932-131">Embora a maior parte da saída `Out-String` seja encapsulada na próxima linha, há cenários em que a saída é truncada pelo sistema de formatação antes de ser passada para `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="06932-131">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="06932-132">Você pode evitar o truncamento usando o parâmetro **Width** .</span><span class="sxs-lookup"><span data-stu-id="06932-132">You can avoid truncation using the **Width** parameter.</span></span>

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

## <span data-ttu-id="06932-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06932-133">PARAMETERS</span></span>

### <span data-ttu-id="06932-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="06932-134">-InputObject</span></span>

<span data-ttu-id="06932-135">Especifica os objetos a serem gravados em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-135">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="06932-136">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="06932-136">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="06932-137">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="06932-137">-NoNewline</span></span>

<span data-ttu-id="06932-138">Remove todas as novas linhas da saída geradas pelo formatador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06932-138">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="06932-139">Novas linhas que fazem parte dos objetos de cadeia de caracteres são preservadas.</span><span class="sxs-lookup"><span data-stu-id="06932-139">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="06932-140">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="06932-140">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="06932-141">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="06932-141">-Stream</span></span>

<span data-ttu-id="06932-142">Indica que o cmdlet envia uma cadeia de caracteres separada para cada linha de um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="06932-142">Indicates that the cmdlet sends a separate string for each line of an input object.</span></span> <span data-ttu-id="06932-143">Por padrão, as cadeias de caracteres para cada objeto são acumuladas e enviadas como uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="06932-143">By default, the strings for each object are accumulated and sent as a single string.</span></span>

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

### <span data-ttu-id="06932-144">-Largura</span><span class="sxs-lookup"><span data-stu-id="06932-144">-Width</span></span>

<span data-ttu-id="06932-145">Especifica o número de caracteres em cada linha de saída.</span><span class="sxs-lookup"><span data-stu-id="06932-145">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="06932-146">Quaisquer caracteres adicionais são encapsulados na próxima linha ou truncados, dependendo do cmdlet do formatador usado.</span><span class="sxs-lookup"><span data-stu-id="06932-146">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="06932-147">O parâmetro **Width** aplica-se somente a objetos que estão sendo formatados.</span><span class="sxs-lookup"><span data-stu-id="06932-147">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="06932-148">Se você omitir esse parâmetro, a largura será determinada pelas características do programa host.</span><span class="sxs-lookup"><span data-stu-id="06932-148">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="06932-149">Em janelas de terminal (console), a largura da janela atual é usada como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="06932-149">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="06932-150">O console do PowerShell Windows tem como padrão uma largura de 80 caracteres na instalação.</span><span class="sxs-lookup"><span data-stu-id="06932-150">PowerShell console windows default to a width of 80 characters on installation.</span></span>

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

### <span data-ttu-id="06932-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="06932-151">CommonParameters</span></span>

<span data-ttu-id="06932-152">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06932-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06932-153">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06932-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06932-154">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="06932-154">INPUTS</span></span>

### <span data-ttu-id="06932-155">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="06932-155">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="06932-156">Você pode enviar objetos pelo pipeline para o `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="06932-156">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="06932-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="06932-157">OUTPUTS</span></span>

### <span data-ttu-id="06932-158">System.String</span><span class="sxs-lookup"><span data-stu-id="06932-158">System.String</span></span>

<span data-ttu-id="06932-159">`Out-String` Retorna a cadeia de caracteres que ele cria do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="06932-159">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="06932-160">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="06932-160">NOTES</span></span>

<span data-ttu-id="06932-161">Os cmdlets que contêm o `Out` verbo não formatam objetos.</span><span class="sxs-lookup"><span data-stu-id="06932-161">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="06932-162">Os `Out` cmdlets enviam objetos para o formatador para o destino de exibição especificado.</span><span class="sxs-lookup"><span data-stu-id="06932-162">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="06932-163">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="06932-163">RELATED LINKS</span></span>

[<span data-ttu-id="06932-164">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="06932-164">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="06932-165">Out-Default</span><span class="sxs-lookup"><span data-stu-id="06932-165">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="06932-166">Out-File</span><span class="sxs-lookup"><span data-stu-id="06932-166">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="06932-167">Out-Host</span><span class="sxs-lookup"><span data-stu-id="06932-167">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="06932-168">Out-Null</span><span class="sxs-lookup"><span data-stu-id="06932-168">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="06932-169">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="06932-169">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="06932-170">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="06932-170">Out-Printer</span></span>](Out-Printer.md)

