---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193850"
---
# <span data-ttu-id="6e045-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="6e045-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="6e045-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6e045-104">SYNOPSIS</span></span>
<span data-ttu-id="6e045-105">Converte objetos .NET em uma série de cadeias de caracteres CSV (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="6e045-105">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="6e045-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e045-106">SYNTAX</span></span>

### <span data-ttu-id="6e045-107">Delimitador (padrão)</span><span class="sxs-lookup"><span data-stu-id="6e045-107">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="6e045-108">parâmetro</span><span class="sxs-lookup"><span data-stu-id="6e045-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="6e045-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e045-109">DESCRIPTION</span></span>

<span data-ttu-id="6e045-110">O `ConvertTo-CSV` cmdlet retorna uma série de cadeias de caracteres CSV (valores separados por vírgula) que representam os objetos que você envia.</span><span class="sxs-lookup"><span data-stu-id="6e045-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="6e045-111">Você pode usar o `ConvertFrom-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="6e045-112">Os objetos convertidos de CSV são valores de cadeia de caracteres dos objetos originais que contêm valores de propriedade e nenhum método.</span><span class="sxs-lookup"><span data-stu-id="6e045-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="6e045-113">Você pode usar o `Export-Csv` cmdlet para converter objetos em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="6e045-114">`Export-CSV` é semelhante a `ConvertTo-CSV` , exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6e045-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="6e045-115">O `ConvertTo-CSV` cmdlet tem parâmetros para especificar um delimitador diferente de uma vírgula ou usar a cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="6e045-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="6e045-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6e045-116">EXAMPLES</span></span>

### <span data-ttu-id="6e045-117">Exemplo 1: converter um objeto em CSV</span><span class="sxs-lookup"><span data-stu-id="6e045-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="6e045-118">Este exemplo converte um objeto de **processo** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="6e045-119">O `Get-Process` cmdlet obtém o objeto de **processo** e usa o parâmetro **Name** para especificar o processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e045-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="6e045-120">O objeto de processo é enviado pelo pipeline para o `ConvertTo-CSV` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e045-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="6e045-121">O `ConvertTo-CSV` cmdlet converte o objeto em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="6e045-122">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="6e045-123">Exemplo 2: converter um objeto DateTime em CSV</span><span class="sxs-lookup"><span data-stu-id="6e045-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="6e045-124">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="6e045-125">O `Get-Date` cmdlet obtém o objeto **DateTime** e o salva na `$Date` variável.</span><span class="sxs-lookup"><span data-stu-id="6e045-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="6e045-126">O `ConvertTo-Csv` cmdlet converte o objeto **DateTime** em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6e045-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="6e045-127">O parâmetro **InputObject** usa o objeto **DateTime** armazenado na `$Date` variável.</span><span class="sxs-lookup"><span data-stu-id="6e045-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="6e045-128">O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6e045-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="6e045-129">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="6e045-130">Exemplo 3: converter o log de eventos do PowerShell em CSV</span><span class="sxs-lookup"><span data-stu-id="6e045-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="6e045-131">Este exemplo converte o log de eventos do Windows para o PowerShell em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="6e045-132">O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="6e045-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="6e045-133">O `Get-WinEvent` cmdlet obtém os objetos de log de eventos e usa o parâmetro **LogName** para especificar o nome do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="6e045-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="6e045-134">Os objetos de log de eventos são enviados pelo pipeline para o `ConvertTo-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e045-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="6e045-135">O `ConvertTo-Csv` cmdlet converte os objetos de log de eventos em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="6e045-136">O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="6e045-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="6e045-137">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="6e045-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e045-138">PARAMETERS</span></span>

### <span data-ttu-id="6e045-139">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="6e045-139">-Delimiter</span></span>

<span data-ttu-id="6e045-140">Especifica o delimitador para separar os valores de propriedade em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-140">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="6e045-141">O padrão é uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="6e045-141">The default is a comma (`,`).</span></span> <span data-ttu-id="6e045-142">Insira um caractere, como dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="6e045-142">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="6e045-143">Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="6e045-143">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e045-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6e045-144">-InputObject</span></span>

<span data-ttu-id="6e045-145">Especifica os objetos que são convertidos em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6e045-145">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="6e045-146">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="6e045-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="6e045-147">Você também pode canalizar objetos para `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="6e045-147">You can also pipe objects to `ConvertTo-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6e045-148">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="6e045-148">-NoTypeInformation</span></span>

<span data-ttu-id="6e045-149">Remove o cabeçalho de informações **#TYPE** da saída.</span><span class="sxs-lookup"><span data-stu-id="6e045-149">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="6e045-150">Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6e045-150">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e045-151">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="6e045-151">-UseCulture</span></span>

<span data-ttu-id="6e045-152">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="6e045-152">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="6e045-153">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="6e045-153">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e045-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e045-154">CommonParameters</span></span>

<span data-ttu-id="6e045-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e045-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e045-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e045-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e045-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6e045-157">INPUTS</span></span>

### <span data-ttu-id="6e045-158">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="6e045-158">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="6e045-159">É possível canalizar qualquer objeto que tenha um adaptador de sistema de tipo estendido (ETS) para o `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="6e045-159">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="6e045-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6e045-160">OUTPUTS</span></span>

### <span data-ttu-id="6e045-161">System.String</span><span class="sxs-lookup"><span data-stu-id="6e045-161">System.String</span></span>

<span data-ttu-id="6e045-162">A saída CSV é retornada como uma coleção de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6e045-162">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="6e045-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6e045-163">NOTES</span></span>

<span data-ttu-id="6e045-164">No formato CSV, cada objeto é representado por uma lista separada por vírgulas de seu valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="6e045-164">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="6e045-165">Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** do objeto.</span><span class="sxs-lookup"><span data-stu-id="6e045-165">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="6e045-166">As cadeias de caracteres são representadas pelo nome do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6e045-166">The strings are represented by the property value name.</span></span> <span data-ttu-id="6e045-167">`ConvertTo-CSV` não exporta os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="6e045-167">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="6e045-168">As cadeias de caracteres CSV são saídas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6e045-168">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="6e045-169">Por padrão, a primeira cadeia de caracteres contém o cabeçalho de informações **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="6e045-169">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="6e045-170">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="6e045-170">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="6e045-171">Se **NoTypeInformation** for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="6e045-171">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="6e045-172">Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="6e045-172">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="6e045-173">As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="6e045-173">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="6e045-174">Quando você envia vários objetos ao `ConvertTo-CSV` , `ConvertTo-CSV` o ordena as cadeias de caracteres com base nas propriedades do primeiro objeto que você envia.</span><span class="sxs-lookup"><span data-stu-id="6e045-174">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="6e045-175">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse objeto será nulo, conforme representado por duas vírgulas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="6e045-175">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="6e045-176">Se os objetos restantes têm propriedades adicionais, esses valores das propriedades serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="6e045-176">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="6e045-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6e045-177">RELATED LINKS</span></span>

[<span data-ttu-id="6e045-178">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="6e045-178">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="6e045-179">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="6e045-179">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="6e045-180">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="6e045-180">Import-Csv</span></span>](Import-Csv.md)
