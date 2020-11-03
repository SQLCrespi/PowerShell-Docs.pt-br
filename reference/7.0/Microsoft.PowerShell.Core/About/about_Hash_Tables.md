---
description: Descreve como criar, usar e classificar tabelas de hash no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: 2d7b886a8d36a72f789395650d1f2dd17123258c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195902"
---
# <a name="about-hash-tables"></a><span data-ttu-id="e57c5-104">Sobre tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="e57c5-104">About Hash Tables</span></span>

## <a name="short-description"></a><span data-ttu-id="e57c5-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="e57c5-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e57c5-106">Descreve como criar, usar e classificar tabelas de hash no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57c5-106">Describes how to create, use, and sort hash tables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e57c5-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="e57c5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e57c5-108">Uma tabela de hash, também conhecida como um dicionário ou uma matriz associativa, é uma estrutura de dados compacta que armazena um ou mais pares chave/valor.</span><span class="sxs-lookup"><span data-stu-id="e57c5-108">A hash table, also known as a dictionary or associative array, is a compact data structure that stores one or more key/value pairs.</span></span> <span data-ttu-id="e57c5-109">Por exemplo, uma tabela de hash pode conter uma série de endereços IP e nomes de computador, onde os endereços IP são as chaves e os nomes dos computadores são os valores, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e57c5-109">For example, a hash table might contain a series of IP addresses and computer names, where the IP addresses are the keys and the computer names are the values, or vice versa.</span></span>

<span data-ttu-id="e57c5-110">No PowerShell, cada tabela de hash é um objeto Hashtable (System. Collections. Hashtable).</span><span class="sxs-lookup"><span data-stu-id="e57c5-110">In PowerShell, each hash table is a Hashtable (System.Collections.Hashtable) object.</span></span> <span data-ttu-id="e57c5-111">Você pode usar as propriedades e métodos de objetos de tabela de hash no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57c5-111">You can use the properties and methods of Hashtable objects in PowerShell.</span></span>

<span data-ttu-id="e57c5-112">A partir do PowerShell 3,0, você pode usar o atributo [ordenado] para criar um dicionário ordenado (System. Collections. especializada. OrderedDictionary) no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57c5-112">Beginning in PowerShell 3.0, you can use the [ordered] attribute to create an ordered dictionary (System.Collections.Specialized.OrderedDictionary) in PowerShell.</span></span>

<span data-ttu-id="e57c5-113">Os dicionários ordenados diferem das tabelas de hash, pois as chaves sempre aparecem na ordem em que são listadas.</span><span class="sxs-lookup"><span data-stu-id="e57c5-113">Ordered dictionaries differ from hash tables in that the keys always appear in the order in which you list them.</span></span> <span data-ttu-id="e57c5-114">A ordem das chaves em uma tabela de hash não é determinada.</span><span class="sxs-lookup"><span data-stu-id="e57c5-114">The order of keys in a hash table is not determined.</span></span>

<span data-ttu-id="e57c5-115">As chaves e o valor em tabelas de hash também são objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="e57c5-115">The keys and value in hash tables are also .NET objects.</span></span> <span data-ttu-id="e57c5-116">Eles são geralmente cadeias de caracteres ou inteiros, mas podem ter qualquer tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e57c5-116">They are most often strings or integers, but they can have any object type.</span></span> <span data-ttu-id="e57c5-117">Você também pode criar tabelas de hash aninhadas, nas quais o valor de uma chave é outra tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-117">You can also create nested hash tables, in which the value of a key is another hash table.</span></span>

<span data-ttu-id="e57c5-118">As tabelas de hash são frequentemente usadas porque são muito eficientes para localizar e recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="e57c5-118">Hash tables are frequently used because they are very efficient for finding and retrieving data.</span></span> <span data-ttu-id="e57c5-119">Você pode usar tabelas de hash para armazenar listas e criar propriedades calculadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57c5-119">You can use hash tables to store lists and to create calculated properties in PowerShell.</span></span> <span data-ttu-id="e57c5-120">E o PowerShell tem um cmdlet, ConvertFrom-StringData, que converte cadeias de caracteres em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-120">And, PowerShell has a cmdlet, ConvertFrom-StringData, that converts strings to a hash table.</span></span>

### <a name="syntax"></a><span data-ttu-id="e57c5-121">Syntax</span><span class="sxs-lookup"><span data-stu-id="e57c5-121">Syntax</span></span>

<span data-ttu-id="e57c5-122">A sintaxe de uma tabela de hash é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="e57c5-122">The syntax of a hash table is as follows:</span></span>

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="e57c5-123">A sintaxe de um dicionário ordenado é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="e57c5-123">The syntax of an ordered dictionary is as follows:</span></span>

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="e57c5-124">O atributo [ordered] foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e57c5-124">The [ordered] attribute was introduced in PowerShell 3.0.</span></span>

### <a name="creating-hash-tables"></a><span data-ttu-id="e57c5-125">Criando tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="e57c5-125">Creating Hash Tables</span></span>

<span data-ttu-id="e57c5-126">Para criar uma tabela de hash, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="e57c5-126">To create a hash table, follow these guidelines:</span></span>

- <span data-ttu-id="e57c5-127">Inicie a tabela de hash com um sinal de arroba (@).</span><span class="sxs-lookup"><span data-stu-id="e57c5-127">Begin the hash table with an at sign (@).</span></span>
- <span data-ttu-id="e57c5-128">Coloque a tabela de hash entre chaves ( {} ).</span><span class="sxs-lookup"><span data-stu-id="e57c5-128">Enclose the hash table in braces ({}).</span></span>
- <span data-ttu-id="e57c5-129">Insira um ou mais pares de chave/valor para o conteúdo da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-129">Enter one or more key/value pairs for the content of the hash table.</span></span>
- <span data-ttu-id="e57c5-130">Use um sinal de igual (=) para separar cada chave de seu valor.</span><span class="sxs-lookup"><span data-stu-id="e57c5-130">Use an equal sign (=) to separate each key from its value.</span></span>
- <span data-ttu-id="e57c5-131">Use um ponto e vírgula (;) ou uma quebra de linha para separar os pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="e57c5-131">Use a semicolon (;) or a line break to separate the key/value pairs.</span></span>
- <span data-ttu-id="e57c5-132">As chaves que contêm espaços devem ser colocadas entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e57c5-132">Keys that contains spaces must be enclosed in quotation marks.</span></span> <span data-ttu-id="e57c5-133">Os valores devem ser expressões válidas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57c5-133">Values must be valid PowerShell expressions.</span></span> <span data-ttu-id="e57c5-134">As cadeias de caracteres devem aparecer entre aspas, mesmo que não incluam espaços.</span><span class="sxs-lookup"><span data-stu-id="e57c5-134">Strings must appear in quotation marks, even if they do not include spaces.</span></span>
- <span data-ttu-id="e57c5-135">Para gerenciar a tabela de hash, salve-a em uma variável.</span><span class="sxs-lookup"><span data-stu-id="e57c5-135">To manage the hash table, save it in a variable.</span></span>
- <span data-ttu-id="e57c5-136">Ao atribuir uma tabela de hash ordenada a uma variável, coloque o atributo [ordenado] antes do símbolo "@".</span><span class="sxs-lookup"><span data-stu-id="e57c5-136">When assigning an ordered hash table to a variable, place the [ordered] attribute before the "@" symbol.</span></span> <span data-ttu-id="e57c5-137">Se você o posicionar antes do nome da variável, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="e57c5-137">If you place it before the variable name, the command fails.</span></span>

<span data-ttu-id="e57c5-138">Para criar uma tabela de hash vazia no valor de $hash, digite:</span><span class="sxs-lookup"><span data-stu-id="e57c5-138">To create an empty hash table in the value of $hash, type:</span></span>

```powershell
$hash = @{}
```

<span data-ttu-id="e57c5-139">Você também pode adicionar chaves e valores a uma tabela de hash ao criá-la.</span><span class="sxs-lookup"><span data-stu-id="e57c5-139">You can also add keys and values to a hash table when you create it.</span></span> <span data-ttu-id="e57c5-140">Por exemplo, a instrução a seguir cria uma tabela de hash com três chaves.</span><span class="sxs-lookup"><span data-stu-id="e57c5-140">For example, the following statement creates a hash table with three keys.</span></span>

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a><span data-ttu-id="e57c5-141">Criando dicionários ordenados</span><span class="sxs-lookup"><span data-stu-id="e57c5-141">Creating Ordered Dictionaries</span></span>

<span data-ttu-id="e57c5-142">Você pode criar um dicionário ordenado adicionando um objeto do tipo OrderedDictionary, mas a maneira mais fácil de criar um dicionário ordenado é usar o atributo [ordered].</span><span class="sxs-lookup"><span data-stu-id="e57c5-142">You can create an ordered dictionary by adding an object of the OrderedDictionary type, but the easiest way to create an ordered dictionary is use the [Ordered] attribute.</span></span>

<span data-ttu-id="e57c5-143">O atributo [ordered] é introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e57c5-143">The [ordered] attribute is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="e57c5-144">Coloque o atributo imediatamente antes do símbolo "@".</span><span class="sxs-lookup"><span data-stu-id="e57c5-144">Place the attribute immediately before the "@" symbol.</span></span>

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

<span data-ttu-id="e57c5-145">Você pode usar dicionários ordenados da mesma maneira que usa tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-145">You can use ordered dictionaries in the same way that you use hash tables.</span></span>
<span data-ttu-id="e57c5-146">Qualquer um dos tipos pode ser usado como o valor dos parâmetros que usam uma tabela de hash ou um dicionário (iDictionary).</span><span class="sxs-lookup"><span data-stu-id="e57c5-146">Either type can be used as the value of parameters that take a hash table or dictionary (iDictionary).</span></span>

<span data-ttu-id="e57c5-147">Você não pode usar o atributo [ordenado] para converter ou transmitir uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-147">You cannot use the [ordered] attribute to convert or cast a hash table.</span></span> <span data-ttu-id="e57c5-148">Se você posicionar o atributo ordenado antes do nome da variável, o comando falhará com a seguinte mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e57c5-148">If you place the ordered attribute before the variable name, the command fails with the following error message.</span></span>

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

<span data-ttu-id="e57c5-149">Para corrigir a expressão, mova o atributo [ordenado].</span><span class="sxs-lookup"><span data-stu-id="e57c5-149">To correct the expression, move the [ordered] attribute.</span></span>

```powershell
PS C:\> $hash = [ordered]@{}
```

<span data-ttu-id="e57c5-150">Você pode converter um dicionário ordenado em uma tabela de hash, mas não pode recuperar o atributo ordenado, mesmo se você limpar a variável e inserir novos valores.</span><span class="sxs-lookup"><span data-stu-id="e57c5-150">You can cast an ordered dictionary to a hash table, but you cannot recover the ordered attribute, even if you clear the variable and enter new values.</span></span> <span data-ttu-id="e57c5-151">Para restabelecer o pedido, você deve remover e recriar a variável.</span><span class="sxs-lookup"><span data-stu-id="e57c5-151">To re-establish the order, you must remove and recreate the variable.</span></span>

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a><span data-ttu-id="e57c5-152">Exibindo tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="e57c5-152">Displaying Hash Tables</span></span>

<span data-ttu-id="e57c5-153">Para exibir uma tabela de hash que é salva em uma variável, digite o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="e57c5-153">To display a hash table that is saved in a variable, type the variable name.</span></span>
<span data-ttu-id="e57c5-154">Por padrão, as tabelas de hash são exibidas como uma tabela com uma coluna para chaves e outra para valores.</span><span class="sxs-lookup"><span data-stu-id="e57c5-154">By default, a hash tables is displayed as a table with one column for keys and one for values.</span></span>

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

<span data-ttu-id="e57c5-155">As tabelas de hash têm propriedades de chaves e valores.</span><span class="sxs-lookup"><span data-stu-id="e57c5-155">Hash tables have Keys and Values properties.</span></span> <span data-ttu-id="e57c5-156">Use a notação de ponto para exibir todas as chaves ou todos os valores.</span><span class="sxs-lookup"><span data-stu-id="e57c5-156">Use dot notation to display all of the keys or all of the values.</span></span>

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

<span data-ttu-id="e57c5-157">Cada nome de chave também é uma propriedade da tabela de hash e seu valor é o valor da propriedade Key-Name.</span><span class="sxs-lookup"><span data-stu-id="e57c5-157">Each key name is also a property of the hash table, and its value is the value of the key-name property.</span></span> <span data-ttu-id="e57c5-158">Use o formato a seguir para exibir os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e57c5-158">Use the following format to display the property values.</span></span>

```powershell
$hashtable.<key>
<value>
```

<span data-ttu-id="e57c5-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e57c5-159">For example:</span></span>

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

<span data-ttu-id="e57c5-160">Se o nome da chave colidir com um dos nomes de Propriedade do tipo de tabela de hash, você poderá usar `PSBase` para acessar essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e57c5-160">If the key name collides with one of the property names of the HashTable type, you can use `PSBase` to access those properties.</span></span> <span data-ttu-id="e57c5-161">Por exemplo, se o nome da chave for `keys` e você quiser retornar a coleção de chaves, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e57c5-161">For example, if the key name is `keys` and you want to return the collection of Keys, use this syntax:</span></span>

```powershell
$hashtable.PSBase.Keys
```

<span data-ttu-id="e57c5-162">As tabelas de hash têm uma propriedade Count que indica o número de pares chave-valor na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-162">Hash tables have a Count property that indicates the number of key-value pairs in the hash table.</span></span>

```powershell
C:\PS> $hash.count
3
```

<span data-ttu-id="e57c5-163">As tabelas de tabela de hash não são matrizes, portanto, você não pode usar um inteiro como um índice na tabela de hash, mas pode usar um nome de chave para indexar a tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-163">Hash table tables are not arrays, so you cannot use an integer as an index into the hash table, but you can use a key name to index into the hash table.</span></span>
<span data-ttu-id="e57c5-164">Se a chave for um valor de cadeia de caracteres, coloque o nome da chave entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e57c5-164">If the key is a string value, enclose the key name in quotation marks.</span></span>

<span data-ttu-id="e57c5-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e57c5-165">For example:</span></span>

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a><span data-ttu-id="e57c5-166">Adicionando e removendo chaves e valores</span><span class="sxs-lookup"><span data-stu-id="e57c5-166">Adding and Removing Keys and Values</span></span>

<span data-ttu-id="e57c5-167">Para adicionar chaves e valores a uma tabela de hash, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="e57c5-167">To add keys and values to a hash table, use the following command format.</span></span>

```powershell
$hash["<key>"] = "<value>"
```

<span data-ttu-id="e57c5-168">Por exemplo, para adicionar uma chave "Time" com um valor de "Now" à tabela de hash, use o formato de instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="e57c5-168">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash["Time"] = "Now"
```

<span data-ttu-id="e57c5-169">Você também pode adicionar chaves e valores a uma tabela de hash usando o método Add do objeto System. Collections. Hashtable.</span><span class="sxs-lookup"><span data-stu-id="e57c5-169">You can also add keys and values to a hash table by using the Add method of the System.Collections.Hashtable object.</span></span> <span data-ttu-id="e57c5-170">O método Add tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e57c5-170">The Add method has the following syntax:</span></span>

```powershell
Add(Key, Value)
```

<span data-ttu-id="e57c5-171">Por exemplo, para adicionar uma chave "Time" com um valor de "Now" à tabela de hash, use o formato de instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="e57c5-171">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash.Add("Time", "Now")
```

<span data-ttu-id="e57c5-172">Além disso, você pode adicionar chaves e valores a uma tabela de hash usando o operador de adição (+) para adicionar uma tabela de hash a uma tabela de hash existente.</span><span class="sxs-lookup"><span data-stu-id="e57c5-172">And, you can add keys and values to a hash table by using the addition operator (+) to add a hash table to an existing hash table.</span></span> <span data-ttu-id="e57c5-173">Por exemplo, a instrução a seguir adiciona uma chave "Time" com um valor de "Now" à tabela de hash na variável $hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-173">For example, the following statement adds a "Time" key with a value of "Now" to the hash table in the $hash variable.</span></span>

```powershell
$hash = $hash + @{Time="Now"}
```

<span data-ttu-id="e57c5-174">Você também pode adicionar valores que são armazenados em variáveis.</span><span class="sxs-lookup"><span data-stu-id="e57c5-174">You can also add values that are stored in variables.</span></span>

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

<span data-ttu-id="e57c5-175">Não é possível usar um operador de subtração para remover um par de chave/valor de uma tabela de hash, mas você pode usar o método remove do objeto Hashtable.</span><span class="sxs-lookup"><span data-stu-id="e57c5-175">You cannot use a subtraction operator to remove a key/value pair from a hash table, but you can use the Remove method of the Hashtable object.</span></span> <span data-ttu-id="e57c5-176">O método remove usa a chave como seu valor.</span><span class="sxs-lookup"><span data-stu-id="e57c5-176">The Remove method takes the key as its value.</span></span>

<span data-ttu-id="e57c5-177">O método remove tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e57c5-177">The Remove method has the following syntax:</span></span>

```
Remove(Key)
```

<span data-ttu-id="e57c5-178">Por exemplo, para remover o par de chave/valor time = Now da tabela de hash no valor da variável $hash, digite:</span><span class="sxs-lookup"><span data-stu-id="e57c5-178">For example, to remove the Time=Now key/value pair from the hash table in the value of the $hash variable, type:</span></span>

```powershell
$hash.Remove("Time")
```

<span data-ttu-id="e57c5-179">Você pode usar todas as propriedades e métodos de objetos de tabela de hash no PowerShell, incluindo contém, Clear, clone e CopyTo.</span><span class="sxs-lookup"><span data-stu-id="e57c5-179">You can use all of the properties and methods of Hashtable objects in PowerShell, including Contains, Clear, Clone, and CopyTo.</span></span> <span data-ttu-id="e57c5-180">Para obter mais informações sobre objetos de tabela de hash, consulte "System. Collections. Hashtable" no MSDN.</span><span class="sxs-lookup"><span data-stu-id="e57c5-180">For more information about Hashtable objects, see "System.Collections.Hashtable" on MSDN.</span></span>

### <a name="object-types-in-hashtables"></a><span data-ttu-id="e57c5-181">Tipos de objeto em HashTables</span><span class="sxs-lookup"><span data-stu-id="e57c5-181">Object Types in HashTables</span></span>

<span data-ttu-id="e57c5-182">As chaves e os valores em uma tabela de hash podem ter qualquer tipo de objeto .NET, e uma única tabela de hash pode ter chaves e valores de vários tipos.</span><span class="sxs-lookup"><span data-stu-id="e57c5-182">The keys and values in a hash table can have any .NET object type, and a single hash table can have keys and values of multiple types.</span></span>

<span data-ttu-id="e57c5-183">A instrução a seguir cria uma tabela de hash de cadeias de caracteres de nome do processo e valores de objeto de processo e salva-o na \$ variável p.</span><span class="sxs-lookup"><span data-stu-id="e57c5-183">The following statement creates a hash table of process name strings and process object values and saves it in the \$p variable.</span></span>

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

<span data-ttu-id="e57c5-184">Você pode exibir a tabela de hash em \$ p e usar as propriedades de nome de chave para exibir os valores.</span><span class="sxs-lookup"><span data-stu-id="e57c5-184">You can display the hash table in \$p and use the key-name properties to display the values.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

<span data-ttu-id="e57c5-185">As chaves em uma tabela de hash também podem ser de qualquer tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="e57c5-185">The keys in a hash table can also be any .NET type.</span></span> <span data-ttu-id="e57c5-186">A instrução a seguir adiciona um par chave/valor à tabela de hash na \$ variável p.</span><span class="sxs-lookup"><span data-stu-id="e57c5-186">The following statement adds a key/value pair to the hash table in the \$p variable.</span></span> <span data-ttu-id="e57c5-187">A chave é um objeto de serviço que representa o serviço WinRM e o valor é o status atual do serviço.</span><span class="sxs-lookup"><span data-stu-id="e57c5-187">The key is a Service object that represents the WinRM service, and the value is the current status of the service.</span></span>

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

<span data-ttu-id="e57c5-188">Você pode exibir e acessar o novo par chave/valor usando os mesmos métodos que você usa para outros pares na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-188">You can display and access the new key/value pair by using the same methods that you use for other pairs in the hash table.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

<span data-ttu-id="e57c5-189">As chaves e os valores em uma tabela de hash também podem ser objetos de Hashtable.</span><span class="sxs-lookup"><span data-stu-id="e57c5-189">The keys and values in a hash table can also be Hashtable objects.</span></span> <span data-ttu-id="e57c5-190">A instrução a seguir adiciona o par chave/valor à tabela de hash na \$ variável p na qual a chave é uma cadeia de caracteres, Hash2, e o valor é uma tabela de hash com três pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="e57c5-190">The following statement adds key/value pair to the hash table in the \$p variable in which the key is a string, Hash2, and the value is a hash table with three key/value pairs.</span></span>

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

<span data-ttu-id="e57c5-191">Você pode exibir e acessar os novos valores usando os mesmos métodos.</span><span class="sxs-lookup"><span data-stu-id="e57c5-191">You can display and access the new values by using the same methods.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a><span data-ttu-id="e57c5-192">Classificando chaves e valores</span><span class="sxs-lookup"><span data-stu-id="e57c5-192">Sorting Keys and Values</span></span>

<span data-ttu-id="e57c5-193">Os itens em uma tabela de hash são intrinsecamente desordenados.</span><span class="sxs-lookup"><span data-stu-id="e57c5-193">The items in a hash table are intrinsically unordered.</span></span> <span data-ttu-id="e57c5-194">Os pares de chave/valor podem aparecer em uma ordem diferente cada vez que você os exibir.</span><span class="sxs-lookup"><span data-stu-id="e57c5-194">The key/value pairs might appear in a different order each time that you display them.</span></span>

<span data-ttu-id="e57c5-195">Embora não seja possível classificar uma tabela de hash, você pode usar o método GetEnumerator de tabelas de hash para enumerar as chaves e os valores e, em seguida, usar o cmdlet Sort-Object para classificar os valores enumerados para exibição.</span><span class="sxs-lookup"><span data-stu-id="e57c5-195">Although you cannot sort a hash table, you can use the GetEnumerator method of hash tables to enumerate the keys and values, and then use the Sort-Object cmdlet to sort the enumerated values for display.</span></span>

<span data-ttu-id="e57c5-196">Por exemplo, os comandos a seguir enumeram as chaves e os valores na tabela de hash na \$ variável p e, em seguida, classificam as chaves em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="e57c5-196">For example, the following commands enumerate the keys and values in the hash table in the \$p variable and then sort the keys in alphabetical order.</span></span>

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

<span data-ttu-id="e57c5-197">O comando a seguir usa o mesmo procedimento para classificar os valores de hash em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="e57c5-197">The following command uses the same procedure to sort the hash values in descending order.</span></span>

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a><span data-ttu-id="e57c5-198">Criando objetos a partir de tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="e57c5-198">Creating Objects from Hash Tables</span></span>

<span data-ttu-id="e57c5-199">A partir do PowerShell 3,0, você pode criar um objeto de uma tabela de hash de propriedades e valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e57c5-199">Beginning in PowerShell 3.0, you can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="e57c5-200">A sintaxe dela é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="e57c5-200">The syntax is as follows:</span></span>

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="e57c5-201">Esse método funciona somente para classes que têm um Construtor nulo, ou seja, um construtor que não tem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e57c5-201">This method works only for classes that have a null constructor, that is, a constructor that has no parameters.</span></span> <span data-ttu-id="e57c5-202">As propriedades do objeto devem ser públicas e configurável.</span><span class="sxs-lookup"><span data-stu-id="e57c5-202">The object properties must be public and settable.</span></span>

<span data-ttu-id="e57c5-203">Para obter mais informações, consulte [about_Object_Creation](about_Object_Creation.md).</span><span class="sxs-lookup"><span data-stu-id="e57c5-203">For more information, see [about_Object_Creation](about_Object_Creation.md).</span></span>

### <a name="convertfrom-stringdata"></a><span data-ttu-id="e57c5-204">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="e57c5-204">ConvertFrom-StringData</span></span>

<span data-ttu-id="e57c5-205">O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres ou uma cadeia de caracteres here de pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-205">The `ConvertFrom-StringData` cmdlet converts a string or a here-string of key/value pairs into a hash table.</span></span> <span data-ttu-id="e57c5-206">Você pode usar o `ConvertFrom-StringData` cmdlet com segurança na seção de dados de um script e pode usá-lo com o `Import-LocalizedData` cmdlet para exibir mensagens de usuário na cultura da interface do usuário do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="e57c5-206">You can use the `ConvertFrom-StringData` cmdlet safely in the Data section of a script, and you can use it with the `Import-LocalizedData` cmdlet to display user messages in the user-interface (UI) culture of the current user.</span></span>

<span data-ttu-id="e57c5-207">Aqui-as cadeias de caracteres são especialmente úteis quando os valores na tabela de hash incluem aspas.</span><span class="sxs-lookup"><span data-stu-id="e57c5-207">Here-strings are especially useful when the values in the hash table include quotation marks.</span></span> <span data-ttu-id="e57c5-208">Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e57c5-208">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="e57c5-209">O exemplo a seguir mostra como criar uma cadeia de caracteres here das mensagens de usuário no exemplo anterior e como usar `ConvertFrom-StringData` para convertê-las de uma cadeia de caracteres em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-209">The following example shows how to create a here-string of the user messages in the previous example and how to use `ConvertFrom-StringData` to convert them from a string into a hash table.</span></span>

<span data-ttu-id="e57c5-210">O comando a seguir cria uma cadeia de caracteres here dos pares de chave/valor e, em seguida, salva-o na \$ variável de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e57c5-210">The following command creates a here-string of the key/value pairs and then saves it in the \$string variable.</span></span>

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

<span data-ttu-id="e57c5-211">Esse comando usa o cmdlet ConvertFrom-StringData para converter a cadeia de caracteres here em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="e57c5-211">This command uses the ConvertFrom-StringData cmdlet to convert the here-string into a hash table.</span></span>

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

<span data-ttu-id="e57c5-212">Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e57c5-212">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e57c5-213">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="e57c5-213">SEE ALSO</span></span>

[<span data-ttu-id="e57c5-214">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="e57c5-214">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="e57c5-215">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="e57c5-215">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="e57c5-216">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e57c5-216">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="e57c5-217">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="e57c5-217">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="e57c5-218">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="e57c5-218">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="e57c5-219">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="e57c5-219">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[<span data-ttu-id="e57c5-220">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="e57c5-220">System.Collections.Hashtable</span></span>](/dotnet/api/system.collections.hashtable)
