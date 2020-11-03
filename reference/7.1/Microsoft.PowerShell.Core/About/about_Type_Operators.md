---
description: Descreve os operadores que funcionam com tipos de Microsoft .NET.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 829dfbbf2cd02c1bf4f1616b49f01f8f079d7d0e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196441"
---
# <a name="about-type-operators"></a><span data-ttu-id="3dd26-104">Sobre operadores de tipo</span><span class="sxs-lookup"><span data-stu-id="3dd26-104">About Type Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="3dd26-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="3dd26-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3dd26-106">Descreve os operadores que funcionam com tipos de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="3dd26-106">Describes the operators that work with Microsoft .NET types.</span></span>

## <a name="long-description"></a><span data-ttu-id="3dd26-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="3dd26-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3dd26-108">Os operadores de tipo booliano ( `-is` e `-isNot` ) informam se um objeto é uma instância de um tipo .net especificado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-108">The Boolean type operators (`-is` and `-isNot`) tell whether an object is an instance of a specified .NET type.</span></span> <span data-ttu-id="3dd26-109">O `-is` operador retornará um valor **true** se o tipo corresponder e um valor de **false** , caso contrário.</span><span class="sxs-lookup"><span data-stu-id="3dd26-109">The `-is` operator returns a value of **TRUE** if the type matches and a value of **FALSE** otherwise.</span></span> <span data-ttu-id="3dd26-110">O `-isNot` operador retornará um valor **false** se o tipo corresponder e um valor de **verdadeiro** caso contrário.</span><span class="sxs-lookup"><span data-stu-id="3dd26-110">The `-isNot` operator returns a value of **FALSE** if the type matches and a value of **TRUE** otherwise.</span></span>

<span data-ttu-id="3dd26-111">O `-as` operador tenta converter o objeto de entrada para o tipo .net especificado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-111">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="3dd26-112">Se tiver sucesso, ele retornará o objeto convertido.</span><span class="sxs-lookup"><span data-stu-id="3dd26-112">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="3dd26-113">Se falhar, ele retornará `$null` .</span><span class="sxs-lookup"><span data-stu-id="3dd26-113">If it fails, it returns `$null`.</span></span> <span data-ttu-id="3dd26-114">Ele não retorna um erro.</span><span class="sxs-lookup"><span data-stu-id="3dd26-114">It does not return an error.</span></span>

<span data-ttu-id="3dd26-115">A tabela a seguir lista os operadores de tipo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dd26-115">The following table lists the type operators in PowerShell.</span></span>

|<span data-ttu-id="3dd26-116">Operador</span><span class="sxs-lookup"><span data-stu-id="3dd26-116">Operator</span></span>|<span data-ttu-id="3dd26-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="3dd26-117">Description</span></span>                |<span data-ttu-id="3dd26-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3dd26-118">Example</span></span>                          |
|--------|---------------------------|---------------------------------|
|`-is`   |<span data-ttu-id="3dd26-119">Retorna TRUE quando a entrada</span><span class="sxs-lookup"><span data-stu-id="3dd26-119">Returns TRUE when the input</span></span>|`(get-date) -is [DateTime]`      |
|        |<span data-ttu-id="3dd26-120">é uma instância do</span><span class="sxs-lookup"><span data-stu-id="3dd26-120">is an instance of the</span></span>      |`True`                           |
|        |<span data-ttu-id="3dd26-121">tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-121">specified .NET type.</span></span>       |                                 |
|`-isNot`|<span data-ttu-id="3dd26-122">Retorna TRUE quando a entrada</span><span class="sxs-lookup"><span data-stu-id="3dd26-122">Returns TRUE when the input</span></span>|`(get-date) -isNot [DateTime]`   |
|        |<span data-ttu-id="3dd26-123">Não é uma instância do</span><span class="sxs-lookup"><span data-stu-id="3dd26-123">not an instance of the</span></span>     |`False`                          |
|        |<span data-ttu-id="3dd26-124">tipo de specified.NET.</span><span class="sxs-lookup"><span data-stu-id="3dd26-124">specified.NET type.</span></span>        |                                 |
|`-as`   |<span data-ttu-id="3dd26-125">Converte a entrada para o</span><span class="sxs-lookup"><span data-stu-id="3dd26-125">Converts the input to the</span></span>  |`"5/7/07" -as [DateTime]`        |
|        |<span data-ttu-id="3dd26-126">tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-126">specified .NET type.</span></span>       |`Monday, May 7, 2007 12:00:00 AM`|

<span data-ttu-id="3dd26-127">A sintaxe dos operadores de tipo é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="3dd26-127">The syntax of the type operators is as follows:</span></span>

```powershell
<input> <operator> [.NET type]
```

<span data-ttu-id="3dd26-128">Você também pode usar a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3dd26-128">You can also use the following syntax:</span></span>

```powershell
<input> <operator> ".NET type"
```

<span data-ttu-id="3dd26-129">O tipo .NET pode ser escrito como um nome de tipo entre colchetes ou uma cadeia de caracteres, como `[DateTime]` ou `"DateTime"` para **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="3dd26-129">The .NET type can be written as a type name in brackets or a string, such as `[DateTime]` or `"DateTime"` for **System.DateTime** .</span></span> <span data-ttu-id="3dd26-130">Se o tipo não estiver na raiz do namespace do sistema, especifique o nome completo do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="3dd26-130">If the type is not at the root of the system namespace, specify the full name of the object type.</span></span> <span data-ttu-id="3dd26-131">Você pode omitir "System.".</span><span class="sxs-lookup"><span data-stu-id="3dd26-131">You can omit "System.".</span></span> <span data-ttu-id="3dd26-132">Por exemplo, para especificar **System. Diagnostics. Process** , digite `[System.Diagnostics.Process]` , `[Diagnostics.Process]` ou `"Diagnostics.Process"` .</span><span class="sxs-lookup"><span data-stu-id="3dd26-132">For example, to specify **System.Diagnostics.Process** , enter `[System.Diagnostics.Process]`, `[Diagnostics.Process]`, or `"Diagnostics.Process"`.</span></span>

<span data-ttu-id="3dd26-133">Os operadores de tipo sempre operam no objeto de entrada como um todo.</span><span class="sxs-lookup"><span data-stu-id="3dd26-133">The type operators always operate on the input object as a whole.</span></span> <span data-ttu-id="3dd26-134">Ou seja, se o objeto de entrada for uma coleção, ele será o tipo de _coleção_ que é testado, não os tipos dos _elementos_ da coleção.</span><span class="sxs-lookup"><span data-stu-id="3dd26-134">That is, if the input object is a collection, it is the _collection_ type that is tested, not the types of the collection's _elements_ .</span></span>

### <a name="-isisnot-operators"></a><span data-ttu-id="3dd26-135">-operadores is/isNot</span><span class="sxs-lookup"><span data-stu-id="3dd26-135">-is/isNot operators</span></span>

<span data-ttu-id="3dd26-136">Os operadores de tipo **booliano** ( `-is` e `-isNot` ) sempre retornam um valor **booliano** , mesmo que a entrada seja uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="3dd26-136">The **Boolean** type operators (`-is` and `-isNot`) always return a **Boolean** value, even if the input is a collection of objects.</span></span>

<span data-ttu-id="3dd26-137">Se `<input>` é um tipo que é igual a ou é _derivado_ do tipo .net, o `-is` operador retorna `$True` .</span><span class="sxs-lookup"><span data-stu-id="3dd26-137">If `<input>` is a type that is the same as or is _derived_ from the .NET Type, the `-is` operator returns `$True`.</span></span>

<span data-ttu-id="3dd26-138">Por exemplo, o tipo **DirectoryInfo** é derivado do tipo **FileSystemInfo** .</span><span class="sxs-lookup"><span data-stu-id="3dd26-138">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="3dd26-139">Portanto, ambos os exemplos retornam **true** .</span><span class="sxs-lookup"><span data-stu-id="3dd26-139">Therefore, both of these examples return **True** .</span></span>

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

<span data-ttu-id="3dd26-140">O `-is` operador também pode corresponder a interfaces se o `<input>` implementar a interface na comparação.</span><span class="sxs-lookup"><span data-stu-id="3dd26-140">The `-is` operator can also match interfaces if the `<input>` implements the interface in the comparison.</span></span> <span data-ttu-id="3dd26-141">Neste exemplo, a entrada é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="3dd26-141">In this example, the input is an array.</span></span> <span data-ttu-id="3dd26-142">As matrizes implementam a interface **System. Collections. IList** .</span><span class="sxs-lookup"><span data-stu-id="3dd26-142">Arrays implement the **System.Collections.IList** interface.</span></span>

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a><span data-ttu-id="3dd26-143">operador-as</span><span class="sxs-lookup"><span data-stu-id="3dd26-143">-as operator</span></span>

<span data-ttu-id="3dd26-144">O `-as` operador tenta converter o objeto de entrada para o tipo .net especificado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-144">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="3dd26-145">Se tiver sucesso, ele retornará o objeto convertido.</span><span class="sxs-lookup"><span data-stu-id="3dd26-145">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="3dd26-146">Se falhar, ele retornará `$null` .</span><span class="sxs-lookup"><span data-stu-id="3dd26-146">It if fails, it returns `$null`.</span></span> <span data-ttu-id="3dd26-147">Ele não retorna um erro.</span><span class="sxs-lookup"><span data-stu-id="3dd26-147">It does not return an error.</span></span>

<span data-ttu-id="3dd26-148">Se o `<input>` for um tipo que é _derivado_ do tipo .NET `-as` _passa por_ retornar objeto de entrada inalterado.</span><span class="sxs-lookup"><span data-stu-id="3dd26-148">If the `<input>` is a type that is _derived_ from the .NET Type `-as` _passes through_ returns input object unchanged.</span></span> <span data-ttu-id="3dd26-149">Por exemplo, o tipo **DirectoryInfo** é derivado do tipo **FileSystemInfo** .</span><span class="sxs-lookup"><span data-stu-id="3dd26-149">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="3dd26-150">Portanto, o tipo de objeto não é alterado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="3dd26-150">Therefore, the object type is unchanged in the following example:</span></span>

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a><span data-ttu-id="3dd26-151">Converter o tipo DateTime é sensível à cultura</span><span class="sxs-lookup"><span data-stu-id="3dd26-151">Converting the DateTime type is culture-sensitive</span></span>

<span data-ttu-id="3dd26-152">Diferentemente da conversão de tipo, a conversão para `[DateTime]` o tipo usando o `-as` operador só funciona com cadeias de caracteres formatadas de acordo com as regras da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="3dd26-152">Unlike type casting, converting to `[DateTime]` type using the `-as` operator only works with strings that are formatted according to the rules of the current culture.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

<span data-ttu-id="3dd26-153">Para localizar o tipo .NET de um objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dd26-153">To find the .NET type of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="3dd26-154">Ou use o método **GetType** de todos os objetos junto com a propriedade **FullName** desse método.</span><span class="sxs-lookup"><span data-stu-id="3dd26-154">Or, use the **GetType** method of all the objects together with the **FullName** property of this method.</span></span> <span data-ttu-id="3dd26-155">Por exemplo, a instrução a seguir obtém o tipo de valor de retorno de um `Get-Culture` comando:</span><span class="sxs-lookup"><span data-stu-id="3dd26-155">For example, the following statement gets the type of the return value of a `Get-Culture` command:</span></span>

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a><span data-ttu-id="3dd26-156">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3dd26-156">EXAMPLES</span></span>

<span data-ttu-id="3dd26-157">Os exemplos a seguir mostram alguns usos dos operadores de tipo:</span><span class="sxs-lookup"><span data-stu-id="3dd26-157">The following examples show some uses of the Type operators:</span></span>

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

<span data-ttu-id="3dd26-158">O exemplo a seguir mostra que quando a entrada é uma coleção de objetos, o tipo de correspondência é o tipo .NET da coleção, não o tipo dos objetos individuais na coleção.</span><span class="sxs-lookup"><span data-stu-id="3dd26-158">The following example shows that when the input is a collection of objects, the matching type is the .NET type of the collection, not the type of the individual objects in the collection.</span></span>

<span data-ttu-id="3dd26-159">Neste exemplo, embora os `Get-Culture` `Get-UICulture` cmdlets e retornem objetos **System. Globalization. CultureInfo** , uma coleção desses objetos é uma matriz System. Object.</span><span class="sxs-lookup"><span data-stu-id="3dd26-159">In this example, although both the `Get-Culture` and `Get-UICulture` cmdlets return **System.Globalization.CultureInfo** objects, a collection of these objects is a System.Object array.</span></span>

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

<span data-ttu-id="3dd26-160">Os exemplos a seguir mostram como usar o `-as` operador.</span><span class="sxs-lookup"><span data-stu-id="3dd26-160">The following examples show how to use the `-as` operator.</span></span>

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

<span data-ttu-id="3dd26-161">O exemplo a seguir mostra que quando o `-as` operador não pode converter o objeto de entrada para o tipo .net, ele retorna `$null` .</span><span class="sxs-lookup"><span data-stu-id="3dd26-161">The following example shows that when the `-as` operator cannot convert the input object to the .NET type, it returns `$null`.</span></span>

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a><span data-ttu-id="3dd26-162">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="3dd26-162">SEE ALSO</span></span>

[<span data-ttu-id="3dd26-163">about_Operators</span><span class="sxs-lookup"><span data-stu-id="3dd26-163">about_Operators</span></span>](about_Operators.md)
