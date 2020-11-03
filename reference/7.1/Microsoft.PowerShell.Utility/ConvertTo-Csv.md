---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: e4cc40e7a9a5fdcd12b6a787607e4979ddbb3273
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194292"
---
# <span data-ttu-id="fb7fb-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="fb7fb-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="fb7fb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fb7fb-104">SYNOPSIS</span></span>
<span data-ttu-id="fb7fb-105">Converte objetos .NET em uma série de cadeias de caracteres CSV (valores separados por caractere).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="fb7fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb7fb-106">SYNTAX</span></span>

### <span data-ttu-id="fb7fb-107">Delimitador</span><span class="sxs-lookup"><span data-stu-id="fb7fb-107">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

### <span data-ttu-id="fb7fb-108">parâmetro</span><span class="sxs-lookup"><span data-stu-id="fb7fb-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

## <span data-ttu-id="fb7fb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fb7fb-109">DESCRIPTION</span></span>

<span data-ttu-id="fb7fb-110">O `ConvertTo-CSV` cmdlet retorna uma série de cadeias de caracteres CSV (valores separados por vírgula) que representam os objetos que você envia.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="fb7fb-111">Você pode usar o `ConvertFrom-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="fb7fb-112">Os objetos convertidos de CSV são valores de cadeia de caracteres dos objetos originais que contêm valores de propriedade e nenhum método.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="fb7fb-113">Você pode usar o `Export-Csv` cmdlet para converter objetos em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="fb7fb-114">`Export-CSV` é semelhante a `ConvertTo-CSV` , exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="fb7fb-115">O `ConvertTo-CSV` cmdlet tem parâmetros para especificar um delimitador diferente de uma vírgula ou usar a cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="fb7fb-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fb7fb-116">EXAMPLES</span></span>

### <span data-ttu-id="fb7fb-117">Exemplo 1: converter um objeto em CSV</span><span class="sxs-lookup"><span data-stu-id="fb7fb-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="fb7fb-118">Este exemplo converte um objeto de **processo** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="fb7fb-119">O `Get-Process` cmdlet obtém o objeto de **processo** e usa o parâmetro **Name** para especificar o processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="fb7fb-120">O objeto de processo é enviado pelo pipeline para o `ConvertTo-CSV` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="fb7fb-121">O `ConvertTo-CSV` cmdlet converte o objeto em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="fb7fb-122">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="fb7fb-123">Exemplo 2: converter um objeto DateTime em CSV</span><span class="sxs-lookup"><span data-stu-id="fb7fb-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="fb7fb-124">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="fb7fb-125">O `Get-Date` cmdlet obtém o objeto **DateTime** e o salva na `$Date` variável.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="fb7fb-126">O `ConvertTo-Csv` cmdlet converte o objeto **DateTime** em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="fb7fb-127">O parâmetro **InputObject** usa o objeto **DateTime** armazenado na `$Date` variável.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="fb7fb-128">O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="fb7fb-129">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="fb7fb-130">Exemplo 3: converter o log de eventos do PowerShell em CSV</span><span class="sxs-lookup"><span data-stu-id="fb7fb-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="fb7fb-131">Este exemplo converte o log de eventos do Windows para o PowerShell em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="fb7fb-132">O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="fb7fb-133">O `Get-WinEvent` cmdlet obtém os objetos de log de eventos e usa o parâmetro **LogName** para especificar o nome do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="fb7fb-134">Os objetos de log de eventos são enviados pelo pipeline para o `ConvertTo-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="fb7fb-135">O `ConvertTo-Csv` cmdlet converte os objetos de log de eventos em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="fb7fb-136">O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="fb7fb-137">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="fb7fb-138">Exemplo 4: converter em CSV com aspas em volta de duas colunas</span><span class="sxs-lookup"><span data-stu-id="fb7fb-138">Example 4: Convert to CSV with quotes around two columns</span></span>

<span data-ttu-id="fb7fb-139">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-139">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -QuoteFields "DateTime","Date"
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="fb7fb-140">Exemplo 4: converter em CSV com aspas somente quando necessário</span><span class="sxs-lookup"><span data-stu-id="fb7fb-140">Example 4: Convert to CSV with quotes only when needed</span></span>

<span data-ttu-id="fb7fb-141">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-141">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -UseQuotes AsNeeded
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="fb7fb-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb7fb-142">PARAMETERS</span></span>

### <span data-ttu-id="fb7fb-143">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="fb7fb-143">-Delimiter</span></span>

<span data-ttu-id="fb7fb-144">Especifica o delimitador para separar os valores de propriedade em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-144">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="fb7fb-145">O padrão é uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-145">The default is a comma (`,`).</span></span> <span data-ttu-id="fb7fb-146">Insira um caractere, como dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-146">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="fb7fb-147">Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-147">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="fb7fb-148">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="fb7fb-148">-IncludeTypeInformation</span></span>

<span data-ttu-id="fb7fb-149">Quando esse parâmetro é usado, a primeira linha da saída contém **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-149">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="fb7fb-150">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="fb7fb-150">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="fb7fb-151">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-151">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb7fb-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fb7fb-152">-InputObject</span></span>

<span data-ttu-id="fb7fb-153">Especifica os objetos que são convertidos em cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-153">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="fb7fb-154">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-154">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="fb7fb-155">Você também pode canalizar objetos para `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="fb7fb-155">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="fb7fb-156">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="fb7fb-156">-NoTypeInformation</span></span>

<span data-ttu-id="fb7fb-157">Remove o cabeçalho de informações **#TYPE** da saída.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-157">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="fb7fb-158">Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-158">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="fb7fb-159">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="fb7fb-159">-UseCulture</span></span>

<span data-ttu-id="fb7fb-160">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-160">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="fb7fb-161">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="fb7fb-161">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="fb7fb-162">-QuoteFields</span><span class="sxs-lookup"><span data-stu-id="fb7fb-162">-QuoteFields</span></span>

<span data-ttu-id="fb7fb-163">Especifica os nomes das colunas que devem ser entre aspas.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-163">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="fb7fb-164">Quando esse parâmetro é usado, somente as colunas especificadas são citadas.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-164">When this parameter is used only the specified columns are quoted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb7fb-165">-UseQuotes</span><span class="sxs-lookup"><span data-stu-id="fb7fb-165">-UseQuotes</span></span>

<span data-ttu-id="fb7fb-166">Especifica quando as aspas são usadas nos arquivos CSV.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-166">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="fb7fb-167">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="fb7fb-167">Possible values are:</span></span>

- <span data-ttu-id="fb7fb-168">Nunca-não citar nada</span><span class="sxs-lookup"><span data-stu-id="fb7fb-168">Never - don't quote anything</span></span>
- <span data-ttu-id="fb7fb-169">Sempre-cotação de tudo (comportamento padrão)</span><span class="sxs-lookup"><span data-stu-id="fb7fb-169">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="fb7fb-170">Apenas campos de cotação necessários que contêm um caractere delimitador</span><span class="sxs-lookup"><span data-stu-id="fb7fb-170">AsNeeded - only quote fields that contain a delimiter character</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fb7fb-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb7fb-171">CommonParameters</span></span>

<span data-ttu-id="fb7fb-172">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb7fb-173">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fb7fb-174">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fb7fb-174">INPUTS</span></span>

### <span data-ttu-id="fb7fb-175">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="fb7fb-175">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fb7fb-176">É possível canalizar qualquer objeto que tenha um adaptador de sistema de tipo estendido (ETS) para o `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="fb7fb-176">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="fb7fb-177">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fb7fb-177">OUTPUTS</span></span>

### <span data-ttu-id="fb7fb-178">System.String</span><span class="sxs-lookup"><span data-stu-id="fb7fb-178">System.String</span></span>

<span data-ttu-id="fb7fb-179">A saída CSV é retornada como uma coleção de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-179">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="fb7fb-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fb7fb-180">NOTES</span></span>

<span data-ttu-id="fb7fb-181">No formato CSV, cada objeto é representado por uma lista separada por vírgulas de seu valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-181">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="fb7fb-182">Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** do objeto.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-182">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="fb7fb-183">As cadeias de caracteres são representadas pelo nome do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-183">The strings are represented by the property value name.</span></span> <span data-ttu-id="fb7fb-184">`ConvertTo-CSV` não exporta os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-184">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="fb7fb-185">As cadeias de caracteres CSV são saídas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fb7fb-185">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="fb7fb-186">Se **IncludeTypeInformation** for usado, a primeira cadeia de caracteres consiste em **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-186">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="fb7fb-187">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="fb7fb-187">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="fb7fb-188">Se **IncludeTypeInformation** não for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-188">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="fb7fb-189">Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-189">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="fb7fb-190">As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-190">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="fb7fb-191">A partir do PowerShell 6,0, o comportamento padrão de `ConvertTo-CSV` é não incluir as informações de **#TYPE** no CSV e **NoTypeInformation** é implícito.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-191">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="fb7fb-192">**IncludeTypeInformation** pode ser usado para incluir as informações de **#TYPE** e emular o comportamento padrão de `ConvertTo-CSV` antes do PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-192">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="fb7fb-193">Quando você envia vários objetos ao `ConvertTo-CSV` , `ConvertTo-CSV` o ordena as cadeias de caracteres com base nas propriedades do primeiro objeto que você envia.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-193">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="fb7fb-194">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse objeto será nulo, conforme representado por duas vírgulas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-194">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="fb7fb-195">Se os objetos restantes têm propriedades adicionais, esses valores das propriedades serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-195">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="fb7fb-196">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fb7fb-196">RELATED LINKS</span></span>

[<span data-ttu-id="fb7fb-197">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="fb7fb-197">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="fb7fb-198">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="fb7fb-198">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="fb7fb-199">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="fb7fb-199">Import-Csv</span></span>](Import-Csv.md)

