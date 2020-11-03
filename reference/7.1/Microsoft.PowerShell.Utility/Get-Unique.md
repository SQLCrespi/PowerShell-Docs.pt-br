---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: f0233e24e82ce5f0ef2113f65d19134833d75cb1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193569"
---
# <span data-ttu-id="f5dec-103">Get-Unique</span><span class="sxs-lookup"><span data-stu-id="f5dec-103">Get-Unique</span></span>

## <span data-ttu-id="f5dec-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f5dec-104">SYNOPSIS</span></span>
<span data-ttu-id="f5dec-105">Retorna itens únicos por meio de uma lista classificada.</span><span class="sxs-lookup"><span data-stu-id="f5dec-105">Returns unique items from a sorted list.</span></span>

## <span data-ttu-id="f5dec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5dec-106">SYNTAX</span></span>

### <span data-ttu-id="f5dec-107">AsString (padrão)</span><span class="sxs-lookup"><span data-stu-id="f5dec-107">AsString (Default)</span></span>

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### <span data-ttu-id="f5dec-108">UniqueByType</span><span class="sxs-lookup"><span data-stu-id="f5dec-108">UniqueByType</span></span>

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## <span data-ttu-id="f5dec-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5dec-109">DESCRIPTION</span></span>

<span data-ttu-id="f5dec-110">O `Get-Unique` cmdlet compara cada item em uma lista classificada com o próximo item, elimina duplicatas e retorna apenas uma instância de cada item.</span><span class="sxs-lookup"><span data-stu-id="f5dec-110">The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item.</span></span> <span data-ttu-id="f5dec-111">A lista deve ser classificada para que o cmdlet funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="f5dec-111">The list must be sorted for the cmdlet to work properly.</span></span>

<span data-ttu-id="f5dec-112">`Get-Unique` diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-112">`Get-Unique` is case-sensitive.</span></span> <span data-ttu-id="f5dec-113">Como resultado, cadeias de caracteres que diferem apenas em maiúsculas e minúsculas são consideradas como sendo exclusivas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-113">As a result, strings that differ only in character casing are considered to be unique.</span></span>

## <span data-ttu-id="f5dec-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f5dec-114">EXAMPLES</span></span>

### <span data-ttu-id="f5dec-115">Exemplo 1: obter palavras exclusivas em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="f5dec-115">Example 1: Get unique words in a text file</span></span>

<span data-ttu-id="f5dec-116">Estes comandos localizam o número de palavras exclusivas em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f5dec-116">These commands find the number of unique words in a text file.</span></span>

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

<span data-ttu-id="f5dec-117">O primeiro comando obtém o conteúdo do arquivo Arquivo.txt.</span><span class="sxs-lookup"><span data-stu-id="f5dec-117">The first command gets the content of the File.txt file.</span></span> <span data-ttu-id="f5dec-118">Ele converte cada linha de texto em letras minúsculas e, em seguida, divide cada palavra em uma linha separada por um espaço (" ").</span><span class="sxs-lookup"><span data-stu-id="f5dec-118">It converts each line of text to lowercase letters and then splits each word onto a separate line at the space (" ").</span></span> <span data-ttu-id="f5dec-119">Em seguida, ele classifica a lista resultante em ordem alfabética (o padrão) e usa o `Get-Unique` cmdlet para eliminar quaisquer palavras duplicadas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-119">Then, it sorts the resulting list alphabetically (the default) and uses the `Get-Unique` cmdlet to eliminate any duplicate words.</span></span> <span data-ttu-id="f5dec-120">Os resultados são armazenados na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="f5dec-120">The results are stored in the `$A` variable.</span></span>

<span data-ttu-id="f5dec-121">O segundo comando usa a propriedade **Count** da coleção de cadeias de caracteres no `$A` para determinar a quantidade de itens em `$A` .</span><span class="sxs-lookup"><span data-stu-id="f5dec-121">The second command uses the **Count** property of the collection of strings in `$A` to determine how many items are in `$A`.</span></span>

### <span data-ttu-id="f5dec-122">Exemplo 2: obter inteiros exclusivos em uma matriz</span><span class="sxs-lookup"><span data-stu-id="f5dec-122">Example 2: Get unique integers in an array</span></span>

<span data-ttu-id="f5dec-123">Este comando localiza os membros exclusivos do conjunto de números inteiros.</span><span class="sxs-lookup"><span data-stu-id="f5dec-123">This command finds the unique members of the set of integers.</span></span>

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

<span data-ttu-id="f5dec-124">O primeiro comando usa uma matriz de inteiros digitados na linha de comando, canaliza-os para o `Sort-Object` cmdlet a ser classificado e, em seguida, os canaliza para `Get-Unique` , o que elimina as entradas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-124">The first command takes an array of integers typed at the command line, pipes them to the `Sort-Object` cmdlet to be sorted, and then pipes them to `Get-Unique`, which eliminates duplicate entries.</span></span>

### <span data-ttu-id="f5dec-125">Exemplo 3: obter tipos de objeto exclusivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="f5dec-125">Example 3: Get unique object types in a directory</span></span>

<span data-ttu-id="f5dec-126">Esse comando usa o `Get-ChildItem` cmdlet para recuperar o conteúdo do diretório local, que inclui arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="f5dec-126">This command uses the `Get-ChildItem` cmdlet to retrieve the contents of the local directory, which includes files and directories.</span></span>

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

<span data-ttu-id="f5dec-127">O operador de pipeline (|) envia os resultados para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f5dec-127">The pipeline operator (|) sends the results to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="f5dec-128">A `$_.GetType()` instrução aplica o método **GetType** a cada arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="f5dec-128">The `$_.GetType()` statement applies the **GetType** method to each file or directory.</span></span> <span data-ttu-id="f5dec-129">Em seguida, `Sort-Object` o classifica os itens por tipo.</span><span class="sxs-lookup"><span data-stu-id="f5dec-129">Then, `Sort-Object` sorts the items by type.</span></span> <span data-ttu-id="f5dec-130">Outro operador de pipeline envia os resultados para `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="f5dec-130">Another pipeline operator sends the results to `Get-Unique`.</span></span> <span data-ttu-id="f5dec-131">O parâmetro **OnType** direciona `Get-Unique` para retornar apenas um objeto de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="f5dec-131">The **OnType** parameter directs `Get-Unique` to return only one object of each type.</span></span>

### <span data-ttu-id="f5dec-132">Exemplo 4: obter processos exclusivos</span><span class="sxs-lookup"><span data-stu-id="f5dec-132">Example 4: Get unique processes</span></span>

<span data-ttu-id="f5dec-133">Este comando obtém os nomes dos processos em execução no computador com as duplicatas já eliminadas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-133">This command gets the names of processes running on the computer with duplicates eliminated.</span></span>

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

<span data-ttu-id="f5dec-134">O `Get-Process` comando obtém todos os processos no computador.</span><span class="sxs-lookup"><span data-stu-id="f5dec-134">The `Get-Process` command gets all of the processes on the computer.</span></span> <span data-ttu-id="f5dec-135">O operador de pipeline (|) passa o resultado para `Sort-Object` , que, por padrão, classifica os processos alfabeticamente por ProcessName.</span><span class="sxs-lookup"><span data-stu-id="f5dec-135">The pipeline operator (|) passes the result to `Sort-Object`, which, by default, sorts the processes alphabetically by ProcessName.</span></span> <span data-ttu-id="f5dec-136">Os resultados são canalizados para o `Select-Object` cmdlet, que seleciona apenas os valores da propriedade ProcessName de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="f5dec-136">The results are piped to the `Select-Object` cmdlet, which selects only the values of the ProcessName property of each object.</span></span> <span data-ttu-id="f5dec-137">Os resultados são então canalizados para `Get-Unique` para eliminar duplicatas.</span><span class="sxs-lookup"><span data-stu-id="f5dec-137">The results are then piped to `Get-Unique` to eliminate duplicates.</span></span>

<span data-ttu-id="f5dec-138">O parâmetro **AsString** diz `Get-Unique` para tratar os valores **ProcessName** como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f5dec-138">The **AsString** parameter tells `Get-Unique` to treat the **ProcessName** values as strings.</span></span>
<span data-ttu-id="f5dec-139">Sem esse parâmetro, `Get-Unique` o trata os valores de **ProcessName** como objetos e retorna apenas uma instância do objeto, ou seja, o primeiro nome do processo na lista.</span><span class="sxs-lookup"><span data-stu-id="f5dec-139">Without this parameter, `Get-Unique` treats the **ProcessName** values as objects and returns only one instance of the object, that is, the first process name in the list.</span></span>

## <span data-ttu-id="f5dec-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5dec-140">PARAMETERS</span></span>

### <span data-ttu-id="f5dec-141">-AsString</span><span class="sxs-lookup"><span data-stu-id="f5dec-141">-AsString</span></span>

<span data-ttu-id="f5dec-142">Indica que este cmdlet usa os dados como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f5dec-142">Indicates that this cmdlet uses the data as a string.</span></span> <span data-ttu-id="f5dec-143">Sem esse parâmetro, os dados são tratados como um objeto, portanto, quando você envia uma coleção de objetos do mesmo tipo para `Get-Unique` , como uma coleção de arquivos, ele retorna apenas um (o primeiro).</span><span class="sxs-lookup"><span data-stu-id="f5dec-143">Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a collection of files, it returns just one (the first).</span></span> <span data-ttu-id="f5dec-144">Você pode usar esse parâmetro para localizar os valores exclusivos das propriedades do objeto, como os nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5dec-144">You can use this parameter to find the unique values of object properties, such as the file names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f5dec-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f5dec-145">-InputObject</span></span>

<span data-ttu-id="f5dec-146">Especifica a entrada para `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="f5dec-146">Specifies input for `Get-Unique`.</span></span> <span data-ttu-id="f5dec-147">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="f5dec-147">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="f5dec-148">Esse cmdlet trata a entrada enviada usando **InputObject** como uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f5dec-148">This cmdlet treats the input submitted by using **InputObject** as a collection.</span></span> <span data-ttu-id="f5dec-149">Ele não enumera itens individuais na coleção.</span><span class="sxs-lookup"><span data-stu-id="f5dec-149">it does not enumerate individual items in the collection.</span></span> <span data-ttu-id="f5dec-150">Como a coleção é um único item, a entrada enviada usando **InputObject** é sempre retornada inalterada.</span><span class="sxs-lookup"><span data-stu-id="f5dec-150">Because the collection is a single item, input submitted by using **InputObject** is always returned unchanged.</span></span>

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

### <span data-ttu-id="f5dec-151">-OnType</span><span class="sxs-lookup"><span data-stu-id="f5dec-151">-OnType</span></span>

<span data-ttu-id="f5dec-152">Indica que esse cmdlet retorna apenas um objeto de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="f5dec-152">Indicates that this cmdlet returns only one object of each type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f5dec-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f5dec-153">CommonParameters</span></span>

<span data-ttu-id="f5dec-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f5dec-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5dec-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f5dec-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5dec-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f5dec-156">INPUTS</span></span>

### <span data-ttu-id="f5dec-157">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="f5dec-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f5dec-158">É possível canalizar qualquer tipo de objeto para `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="f5dec-158">You can pipe any type of object to `Get-Unique`.</span></span>

## <span data-ttu-id="f5dec-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f5dec-159">OUTPUTS</span></span>

### <span data-ttu-id="f5dec-160">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="f5dec-160">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f5dec-161">O tipo de objeto que `Get-Unique` retorna é determinado pela entrada.</span><span class="sxs-lookup"><span data-stu-id="f5dec-161">The type of object that `Get-Unique` returns is determined by the input.</span></span>

## <span data-ttu-id="f5dec-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f5dec-162">NOTES</span></span>

<span data-ttu-id="f5dec-163">Você também pode consultar `Get-Unique` por seu alias interno, `gu` .</span><span class="sxs-lookup"><span data-stu-id="f5dec-163">You can also refer to `Get-Unique` by its built-in alias, `gu`.</span></span> <span data-ttu-id="f5dec-164">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="f5dec-164">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="f5dec-165">Para classificar uma lista, utilize o Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="f5dec-165">To sort a list, use Sort-Object.</span></span> <span data-ttu-id="f5dec-166">Você também pode usar o parâmetro **exclusivo** de `Sort-Object` para localizar os itens exclusivos em uma lista.</span><span class="sxs-lookup"><span data-stu-id="f5dec-166">You can also use the **Unique** parameter of `Sort-Object` to find the unique items in a list.</span></span>

## <span data-ttu-id="f5dec-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f5dec-167">RELATED LINKS</span></span>

[<span data-ttu-id="f5dec-168">Select-Object</span><span class="sxs-lookup"><span data-stu-id="f5dec-168">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="f5dec-169">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="f5dec-169">Sort-Object</span></span>](Sort-Object.md)

