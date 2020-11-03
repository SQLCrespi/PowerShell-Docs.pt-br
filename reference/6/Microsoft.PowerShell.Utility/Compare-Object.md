---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: c72cde8e626993726ae1a52206c88e20c3a7c588
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "93196630"
---
# <span data-ttu-id="61ac1-103">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-103">Compare-Object</span></span>

## <span data-ttu-id="61ac1-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="61ac1-104">Synopsis</span></span>
<span data-ttu-id="61ac1-105">Compara dois conjuntos de objetos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-105">Compares two sets of objects.</span></span>

## <span data-ttu-id="61ac1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="61ac1-106">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="61ac1-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="61ac1-107">Description</span></span>

<span data-ttu-id="61ac1-108">O `Compare-Object` cmdlet compara dois conjuntos de objetos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-108">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="61ac1-109">Um conjunto de objetos é a **referência** e o outro conjunto de objetos é a **diferença** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-109">One set of objects is the **reference** , and the other set of objects is the **difference** .</span></span>

<span data-ttu-id="61ac1-110">`Compare-Object` verifica se há métodos disponíveis para comparar um objeto inteiro.</span><span class="sxs-lookup"><span data-stu-id="61ac1-110">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="61ac1-111">Se não for possível encontrar um método adequado, ele chamará os métodos **ToString ()** dos objetos de entrada e comparará os resultados da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="61ac1-111">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="61ac1-112">Você pode fornecer uma ou mais propriedades a serem usadas para comparação.</span><span class="sxs-lookup"><span data-stu-id="61ac1-112">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="61ac1-113">Quando as propriedades são fornecidas, o cmdlet compara os valores dessas propriedades apenas.</span><span class="sxs-lookup"><span data-stu-id="61ac1-113">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="61ac1-114">O resultado da comparação indica se um valor de propriedade apareceu somente no objeto de **referência** ( `<=` ) ou somente no objeto de **diferença** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="61ac1-114">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="61ac1-115">Se o parâmetro **includeequal** for usado, ( `==` ) indicará que o valor está em ambos os objetos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-115">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="61ac1-116">Se a **referência** ou os objetos de **diferença** forem nulos ( `$null` ), o `Compare-Object` gerará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="61ac1-116">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="61ac1-117">Alguns exemplos usam nivelamento para reduzir o tamanho da linha dos exemplos de código.</span><span class="sxs-lookup"><span data-stu-id="61ac1-117">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="61ac1-118">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="61ac1-118">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="61ac1-119">Exemplos</span><span class="sxs-lookup"><span data-stu-id="61ac1-119">Examples</span></span>

### <span data-ttu-id="61ac1-120">Exemplo 1 – comparar o conteúdo de dois arquivos de texto</span><span class="sxs-lookup"><span data-stu-id="61ac1-120">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="61ac1-121">Este exemplo compara o conteúdo de dois arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="61ac1-121">This example compares the contents of two text files.</span></span> <span data-ttu-id="61ac1-122">O exemplo usa os dois arquivos de texto a seguir, com cada valor em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="61ac1-122">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="61ac1-123">`Testfile1.txt` contém os valores: Dog, Squirrel e pássaro.</span><span class="sxs-lookup"><span data-stu-id="61ac1-123">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="61ac1-124">`Testfile2.txt` contém os valores: Cat, pássaro e racoon.</span><span class="sxs-lookup"><span data-stu-id="61ac1-124">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="61ac1-125">A saída exibe apenas as linhas que são diferentes entre os arquivos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-125">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="61ac1-126">`Testfile1.txt` é o objeto de **referência** ( `<=` ) e `Testfile2.txt` é o objeto de **diferença** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="61ac1-126">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="61ac1-127">Linhas com conteúdo que aparecem em ambos os arquivos não são exibidas.</span><span class="sxs-lookup"><span data-stu-id="61ac1-127">Lines with content that appear in both files aren't displayed.</span></span>

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### <span data-ttu-id="61ac1-128">Exemplo 2 – comparar cada linha de conteúdo e excluir as diferenças</span><span class="sxs-lookup"><span data-stu-id="61ac1-128">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="61ac1-129">Este exemplo usa os parâmetros **includeequal** e **ExcludeDifferent** para comparar cada linha de conteúdo em dois arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="61ac1-129">This example uses the **IncludeEqual** and **ExcludeDifferent** parameters to compare each line of content in two text files.</span></span>

<span data-ttu-id="61ac1-130">Como o comando usa o parâmetro **ExcludeDifferent** , a saída contém apenas as linhas contidas em ambos os arquivos, conforme mostrado pelo **SideIndicator** ( `==` ).</span><span class="sxs-lookup"><span data-stu-id="61ac1-130">Because the command uses the **ExcludeDifferent** parameter, the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="61ac1-131">Exemplo 3-mostrar a diferença ao usar o parâmetro PassThru</span><span class="sxs-lookup"><span data-stu-id="61ac1-131">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="61ac1-132">Normalmente, `Compare-Object` retorna um tipo **PSCustomObject** com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="61ac1-132">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="61ac1-133">O **InputObject** que está sendo comparado</span><span class="sxs-lookup"><span data-stu-id="61ac1-133">The **InputObject** being compared</span></span>
- <span data-ttu-id="61ac1-134">A propriedade **SideIndicator** que mostra a qual objeto de entrada a saída pertence</span><span class="sxs-lookup"><span data-stu-id="61ac1-134">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="61ac1-135">Quando você usa o parâmetro **PassThru** , o **tipo** do objeto não é alterado, mas a instância do objeto retornado tem uma **observaçãoproperty** adicionada chamada **SideIndicator** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-135">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator** .</span></span> <span data-ttu-id="61ac1-136">**SideIndicator** mostra a qual objeto de entrada a saída pertence.</span><span class="sxs-lookup"><span data-stu-id="61ac1-136">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="61ac1-137">Os exemplos a seguir mostram os diferentes tipos de saída.</span><span class="sxs-lookup"><span data-stu-id="61ac1-137">The following examples shows the different output types.</span></span>

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

<span data-ttu-id="61ac1-138">Ao usar **PassThru** , o tipo de objeto original ( **System. Boolean** ) é retornado.</span><span class="sxs-lookup"><span data-stu-id="61ac1-138">When using **PassThru** , the original object type ( **System.Boolean** ) is returned.</span></span> <span data-ttu-id="61ac1-139">Observe como a saída exibida pelo formato padrão para objetos **System. Boolean** não exibia a propriedade **SideIndicator** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-139">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="61ac1-140">No entanto, o objeto **System. Boolean** retornado tem a **observaçãoproperty** adicionada.</span><span class="sxs-lookup"><span data-stu-id="61ac1-140">However, the returned **System.Boolean** object has the added **NoteProperty** .</span></span>

### <span data-ttu-id="61ac1-141">Exemplo 4 – comparar dois objetos simples usando propriedades</span><span class="sxs-lookup"><span data-stu-id="61ac1-141">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="61ac1-142">Neste exemplo, comparamos duas cadeias de caracteres diferentes que têm o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="61ac1-142">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="61ac1-143">Exemplo 5-comparando objetos complexos usando propriedades</span><span class="sxs-lookup"><span data-stu-id="61ac1-143">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="61ac1-144">Este exemplo mostra o comportamento ao comparar objetos complexos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-144">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="61ac1-145">Neste exemplo, armazenamos dois objetos de processo diferentes para diferentes instâncias do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61ac1-145">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="61ac1-146">Ambas as variáveis contêm objetos de processo com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="61ac1-146">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="61ac1-147">Quando os objetos são comparados sem especificar o parâmetro **Property** , o cmdlet considera os objetos como iguais.</span><span class="sxs-lookup"><span data-stu-id="61ac1-147">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="61ac1-148">Observe que o valor de **InputObject** é o mesmo que o resultado do método **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-148">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="61ac1-149">Como a classe **System. Diagnostics. Process** não tem a interface **IComparable** , o cmdlet converte os objetos em cadeias de caracteres e, em seguida, compara os resultados.</span><span class="sxs-lookup"><span data-stu-id="61ac1-149">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

<span data-ttu-id="61ac1-150">Quando você especifica Propriedades a serem comparadas, o cmdlet mostra as diferenças.</span><span class="sxs-lookup"><span data-stu-id="61ac1-150">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="61ac1-151">Exemplo 6 – comparando objetos complexos que implementam IComparable</span><span class="sxs-lookup"><span data-stu-id="61ac1-151">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="61ac1-152">Se o objeto implementar **IComparable** , o cmdlet pesquisará maneiras de comparar os objetos. Se os objetos forem de tipos diferentes, o objeto de **diferença** será convertido no tipo de **referenceobject** , em comparação.</span><span class="sxs-lookup"><span data-stu-id="61ac1-152">If the object implements **IComparable** , the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="61ac1-153">Neste exemplo, estamos comparando uma cadeia de caracteres a um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-153">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="61ac1-154">No primeiro caso, a cadeia de caracteres é convertida em um **TimeSpan** para que os objetos sejam iguais.</span><span class="sxs-lookup"><span data-stu-id="61ac1-154">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

<span data-ttu-id="61ac1-155">No segundo caso, o **TimeSpan** é convertido em uma cadeia de caracteres para que o objeto seja diferente.</span><span class="sxs-lookup"><span data-stu-id="61ac1-155">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="61ac1-156">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="61ac1-156">Parameters</span></span>

### <span data-ttu-id="61ac1-157">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="61ac1-157">-CaseSensitive</span></span>

<span data-ttu-id="61ac1-158">Indica que as comparações devem diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="61ac1-158">Indicates that comparisons should be case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-159">-Culture</span><span class="sxs-lookup"><span data-stu-id="61ac1-159">-Culture</span></span>

<span data-ttu-id="61ac1-160">Especifica a cultura a ser usada para as comparações.</span><span class="sxs-lookup"><span data-stu-id="61ac1-160">Specifies the culture to use for comparisons.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-161">-Differenceobject</span><span class="sxs-lookup"><span data-stu-id="61ac1-161">-DifferenceObject</span></span>

<span data-ttu-id="61ac1-162">Especifica os objetos que são comparados aos objetos de **referência** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-162">Specifies the objects that are compared to the **reference** objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-163">-ExcludeDifferent</span><span class="sxs-lookup"><span data-stu-id="61ac1-163">-ExcludeDifferent</span></span>

<span data-ttu-id="61ac1-164">Indica que esse cmdlet exibe apenas as características dos objetos comparados que são iguais.</span><span class="sxs-lookup"><span data-stu-id="61ac1-164">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="61ac1-165">As diferenças entre os objetos são descartadas.</span><span class="sxs-lookup"><span data-stu-id="61ac1-165">The differences between the objects are discarded.</span></span>

<span data-ttu-id="61ac1-166">Use **ExcludeDifferent** com **includeequal** para exibir apenas as linhas que correspondem entre os objetos de **referência** e **diferença** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-166">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="61ac1-167">Se **ExcludeDifferent** for especificado sem **includeequal** , não haverá nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="61ac1-167">If **ExcludeDifferent** is specified without **IncludeEqual** , there's no output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-168">-IncludeEqual</span><span class="sxs-lookup"><span data-stu-id="61ac1-168">-IncludeEqual</span></span>

<span data-ttu-id="61ac1-169">**Includeequal** exibe as correspondências entre os objetos de **referência** e **diferença** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-169">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="61ac1-170">Por padrão, a saída também inclui as diferenças entre os objetos de **referência** e **diferença** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-170">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-171">-PassThru</span><span class="sxs-lookup"><span data-stu-id="61ac1-171">-PassThru</span></span>

<span data-ttu-id="61ac1-172">Quando você usa o parâmetro **PassThru** , `Compare-Object` o omite o wrapper **PSCustomObject** em volta dos objetos comparados e retorna os objetos diferentes, inalterados.</span><span class="sxs-lookup"><span data-stu-id="61ac1-172">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-173">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="61ac1-173">-Property</span></span>

<span data-ttu-id="61ac1-174">Especifica uma matriz de propriedades dos objetos de **referência** e **diferença** a serem comparados.</span><span class="sxs-lookup"><span data-stu-id="61ac1-174">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="61ac1-175">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="61ac1-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="61ac1-176">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="61ac1-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="61ac1-177">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="61ac1-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="61ac1-178">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="61ac1-178">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="61ac1-179">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="61ac1-179">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-180">-Referenceobject</span><span class="sxs-lookup"><span data-stu-id="61ac1-180">-ReferenceObject</span></span>

<span data-ttu-id="61ac1-181">Especifica uma matriz de objetos usada como referência para comparação.</span><span class="sxs-lookup"><span data-stu-id="61ac1-181">Specifies an array of objects used as a reference for comparison.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-182">-SyncWindow</span><span class="sxs-lookup"><span data-stu-id="61ac1-182">-SyncWindow</span></span>

<span data-ttu-id="61ac1-183">Especifica o número de objetos adjacentes que `Compare-Object` inspeciona ao procurar uma correspondência em uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-183">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="61ac1-184">`Compare-Object` examina objetos adjacentes quando não encontra o objeto na mesma posição em uma coleção.</span><span class="sxs-lookup"><span data-stu-id="61ac1-184">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="61ac1-185">O valor padrão é `[Int32]::MaxValue` , que significa que `Compare-Object` o examina toda a coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="61ac1-185">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61ac1-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="61ac1-186">CommonParameters</span></span>

<span data-ttu-id="61ac1-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61ac1-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61ac1-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="61ac1-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61ac1-189">Entradas</span><span class="sxs-lookup"><span data-stu-id="61ac1-189">Inputs</span></span>

### <span data-ttu-id="61ac1-190">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="61ac1-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="61ac1-191">Você pode enviar um objeto para baixo do pipeline para o parâmetro **differenceobject** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-191">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="61ac1-192">Saídas</span><span class="sxs-lookup"><span data-stu-id="61ac1-192">Outputs</span></span>

### <span data-ttu-id="61ac1-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="61ac1-193">None</span></span>

<span data-ttu-id="61ac1-194">Se o objeto de **referência** e o objeto de **diferença** forem os mesmos, não haverá nenhuma saída, a menos que você use o parâmetro **includeequal** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-194">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="61ac1-195">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="61ac1-195">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="61ac1-196">Se os objetos forem diferentes, o `Compare-Object` encapsulará os objetos diferentes em um `PSCustomObject` wrapper com uma propriedade **SideIndicator** para fazer referência às diferenças.</span><span class="sxs-lookup"><span data-stu-id="61ac1-196">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="61ac1-197">Quando você usa o parâmetro **PassThru** , o **tipo** do objeto não é alterado, mas a instância do objeto retornado tem uma **observaçãoproperty** adicionada chamada **SideIndicator** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-197">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator** .</span></span> <span data-ttu-id="61ac1-198">**SideIndicator** mostra a qual objeto de entrada a saída pertence.</span><span class="sxs-lookup"><span data-stu-id="61ac1-198">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="61ac1-199">Observações</span><span class="sxs-lookup"><span data-stu-id="61ac1-199">Notes</span></span>

<span data-ttu-id="61ac1-200">Ao usar o parâmetro **PassThru** , a saída exibida no console pode não incluir a propriedade **SideIndicator** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-200">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="61ac1-201">A exibição de formato padrão do para a saída do tipo de objeto por não `Compare-Object` inclui a propriedade **SideIndicator** .</span><span class="sxs-lookup"><span data-stu-id="61ac1-201">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="61ac1-202">Para obter mais informações, consulte o [exemplo 3](#ex3) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="61ac1-202">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="61ac1-203">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="61ac1-203">Related links</span></span>

[<span data-ttu-id="61ac1-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="61ac1-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="61ac1-205">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-205">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="61ac1-206">Group-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-206">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="61ac1-207">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-207">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="61ac1-208">New-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-208">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="61ac1-209">Select-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-209">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="61ac1-210">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-210">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="61ac1-211">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-211">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="61ac1-212">Where-Object</span><span class="sxs-lookup"><span data-stu-id="61ac1-212">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="61ac1-213">Get-Process</span><span class="sxs-lookup"><span data-stu-id="61ac1-213">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
