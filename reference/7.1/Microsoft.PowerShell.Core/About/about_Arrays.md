---
description: Descreve matrizes, que são estruturas de dados projetadas para armazenar coleções de itens.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 96e3798d4ff0a737421bb6211b809b192afa96f0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196072"
---
# <a name="about-arrays"></a><span data-ttu-id="d6c22-104">Sobre matrizes</span><span class="sxs-lookup"><span data-stu-id="d6c22-104">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="d6c22-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d6c22-105">Short Description</span></span>
<span data-ttu-id="d6c22-106">Descreve matrizes, que são estruturas de dados projetadas para armazenar coleções de itens.</span><span class="sxs-lookup"><span data-stu-id="d6c22-106">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="d6c22-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="d6c22-107">Long Description</span></span>

<span data-ttu-id="d6c22-108">Uma matriz é uma estrutura de dados que é projetada para armazenar uma coleção de itens.</span><span class="sxs-lookup"><span data-stu-id="d6c22-108">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="d6c22-109">Os itens podem ser do mesmo tipo ou tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-109">The items can be the same type or different types.</span></span>

<span data-ttu-id="d6c22-110">A partir do Windows PowerShell 3,0, uma coleção de zero ou um objeto tem algumas propriedades de matrizes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-110">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="d6c22-111">Criando e inicializando uma matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-111">Creating and initializing an array</span></span>

<span data-ttu-id="d6c22-112">Para criar e inicializar uma matriz, atribua vários valores a uma variável.</span><span class="sxs-lookup"><span data-stu-id="d6c22-112">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="d6c22-113">Os valores armazenados na matriz são delimitados por uma vírgula e separados do nome da variável pelo operador de atribuição ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="d6c22-113">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="d6c22-114">Por exemplo, para criar uma matriz chamada `$A` que contenha os sete valores numéricos (int) de 22, 5, 10, 8, 12, 9 e 80, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-114">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="d6c22-115">A vírgula também pode ser usada para inicializar uma única matriz de item colocando a vírgula antes do único item.</span><span class="sxs-lookup"><span data-stu-id="d6c22-115">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="d6c22-116">Por exemplo, para criar uma única matriz de item denominada `$B` contendo o único valor de 7, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-116">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="d6c22-117">Você também pode criar e inicializar uma matriz usando o operador de intervalo ( `..` ).</span><span class="sxs-lookup"><span data-stu-id="d6c22-117">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="d6c22-118">O exemplo a seguir cria uma matriz que contém os valores de 5 a 8.</span><span class="sxs-lookup"><span data-stu-id="d6c22-118">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="d6c22-119">Como resultado, `$C` contém quatro valores: 5, 6, 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="d6c22-119">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="d6c22-120">Quando nenhum tipo de dados é especificado, o PowerShell cria cada matriz como uma matriz de objetos ( **System. Object []** ).</span><span class="sxs-lookup"><span data-stu-id="d6c22-120">When no data type is specified, PowerShell creates each array as an object array ( **System.Object[]** ).</span></span> <span data-ttu-id="d6c22-121">Para determinar o tipo de dados de uma matriz, use o método **GetType ()** .</span><span class="sxs-lookup"><span data-stu-id="d6c22-121">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="d6c22-122">Por exemplo, para determinar o tipo de dados da `$A` matriz, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-122">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="d6c22-123">Para criar uma matriz fortemente tipada, ou seja, uma matriz que possa conter apenas valores de um tipo específico, converta a variável como um tipo de matriz, como **String []** , **Long []** ou **Int32 []** .</span><span class="sxs-lookup"><span data-stu-id="d6c22-123">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]** , **long[]** , or **int32[]** .</span></span> <span data-ttu-id="d6c22-124">Para converter uma matriz, preceda o nome da variável com um tipo de matriz entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-124">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="d6c22-125">Por exemplo, para criar uma matriz de inteiros de 32 bits chamada `$ia` contendo quatro inteiros (1500, 2230, 3350 e 4000), digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-125">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="d6c22-126">Como resultado, a `$ia` matriz pode conter apenas números inteiros.</span><span class="sxs-lookup"><span data-stu-id="d6c22-126">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="d6c22-127">Você pode criar matrizes que são convertidas para qualquer tipo com suporte na estrutura de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="d6c22-127">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="d6c22-128">Por exemplo, os objetos `Get-Process` recuperados para representar processos são do tipo **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="d6c22-128">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="d6c22-129">Para criar uma matriz fortemente tipada de objetos de processo, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d6c22-129">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="d6c22-130">O operador de subexpressão de matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-130">The array sub-expression operator</span></span>

<span data-ttu-id="d6c22-131">O operador de subexpressão de matriz cria uma matriz das instruções dentro dela.</span><span class="sxs-lookup"><span data-stu-id="d6c22-131">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="d6c22-132">Qualquer que seja a instrução dentro do operador, o operador a coloca em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-132">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="d6c22-133">Mesmo que haja zero ou um objeto.</span><span class="sxs-lookup"><span data-stu-id="d6c22-133">Even if there is zero or one object.</span></span>

<span data-ttu-id="d6c22-134">A sintaxe do operador de matriz é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6c22-134">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="d6c22-135">Você pode usar o operador de matriz para criar uma matriz de zero ou um objeto.</span><span class="sxs-lookup"><span data-stu-id="d6c22-135">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="d6c22-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6c22-136">For example:</span></span>

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

<span data-ttu-id="d6c22-137">O operador de matriz é útil em scripts quando você está obtendo objetos, mas não sabe quantos objetos você obtém.</span><span class="sxs-lookup"><span data-stu-id="d6c22-137">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="d6c22-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6c22-138">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="d6c22-139">Para obter mais informações sobre o operador de subexpressão de matriz, consulte [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d6c22-139">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="d6c22-140">Acessando e usando elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-140">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="d6c22-141">Lendo uma matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-141">Reading an array</span></span>

<span data-ttu-id="d6c22-142">Você pode fazer referência a uma matriz usando seu nome de variável.</span><span class="sxs-lookup"><span data-stu-id="d6c22-142">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="d6c22-143">Para exibir todos os elementos na matriz, digite o nome da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-143">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="d6c22-144">Por exemplo, supondo que `$a` seja uma matriz contendo inteiros 0, 1, 2, até 9; digitando:</span><span class="sxs-lookup"><span data-stu-id="d6c22-144">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="d6c22-145">Você pode consultar os elementos em uma matriz usando um índice, começando na posição 0.</span><span class="sxs-lookup"><span data-stu-id="d6c22-145">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="d6c22-146">Coloque o número de índice entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-146">Enclose the index number in brackets.</span></span> <span data-ttu-id="d6c22-147">Por exemplo, para exibir o primeiro elemento na `$a` matriz, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-147">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="d6c22-148">Para exibir o terceiro elemento na `$a` matriz, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-148">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="d6c22-149">Você pode recuperar parte da matriz usando um operador de intervalo para o índice.</span><span class="sxs-lookup"><span data-stu-id="d6c22-149">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="d6c22-150">Por exemplo, para recuperar o segundo para o quinto elementos da matriz, você digitaria:</span><span class="sxs-lookup"><span data-stu-id="d6c22-150">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="d6c22-151">Contagem de números negativos do final da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-151">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="d6c22-152">Por exemplo, "-1" refere-se ao último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-152">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="d6c22-153">Para exibir os três últimos elementos da matriz, em ordem crescente de índice, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-153">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="d6c22-154">Se você digitar índices negativos em ordem decrescente, sua saída será alterada.</span><span class="sxs-lookup"><span data-stu-id="d6c22-154">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="d6c22-155">No entanto, tenha cuidado ao usar essa notação.</span><span class="sxs-lookup"><span data-stu-id="d6c22-155">However, be cautious when using this notation.</span></span> <span data-ttu-id="d6c22-156">A notação percorre o limite final até o início da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-156">The notation cycles from the end boundary to the beginning of the array.</span></span>

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

<span data-ttu-id="d6c22-157">Além disso, um erro comum é assumir a `$a[0..-2]` referência a todos os elementos da matriz, exceto para o último.</span><span class="sxs-lookup"><span data-stu-id="d6c22-157">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="d6c22-158">Refere-se ao primeiro, ao último e ao último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-158">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="d6c22-159">Você pode usar o operador de adição ( `+` ) para combinar intervalos com uma lista de elementos em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-159">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="d6c22-160">Por exemplo, para exibir os elementos nas posições de índice 0, 2 e 4 a 6, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-160">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

<span data-ttu-id="d6c22-161">Além disso, para listar vários intervalos e elementos individuais, você pode usar o operador de adição.</span><span class="sxs-lookup"><span data-stu-id="d6c22-161">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="d6c22-162">Por exemplo, para listar os elementos de zero a dois, quatro a seis e o elemento em um oitavo tipo posicional:</span><span class="sxs-lookup"><span data-stu-id="d6c22-162">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a><span data-ttu-id="d6c22-163">Iterações sobre elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-163">Iterations over array elements</span></span>

<span data-ttu-id="d6c22-164">Você também pode usar constructos de loop, como ForEach, for e loops while, para se referir aos elementos em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-164">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="d6c22-165">Por exemplo, para usar um loop ForEach para exibir os elementos na `$a` matriz, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-165">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="d6c22-166">O loop foreach itera na matriz e retorna cada valor na matriz até chegar ao final da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-166">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="d6c22-167">O loop for é útil quando você está incrementando contadores ao examinar os elementos em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-167">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="d6c22-168">Por exemplo, para usar um loop for para retornar todos os outros valores em uma matriz, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-168">For example, to use a For loop to return every other value in an array, type:</span></span>

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

<span data-ttu-id="d6c22-169">Você pode usar um loop while para exibir os elementos em uma matriz até que uma condição definida não seja mais verdadeira.</span><span class="sxs-lookup"><span data-stu-id="d6c22-169">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="d6c22-170">Por exemplo, para exibir os elementos na `$a` matriz enquanto o índice de matriz é menor que 4, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-170">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a><span data-ttu-id="d6c22-171">Propriedades de matrizes</span><span class="sxs-lookup"><span data-stu-id="d6c22-171">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="d6c22-172">Contagem ou comprimento ou LongLength</span><span class="sxs-lookup"><span data-stu-id="d6c22-172">Count or Length or LongLength</span></span>

<span data-ttu-id="d6c22-173">Para determinar quantos itens estão em uma matriz, use a `Length` propriedade ou seu `Count` alias.</span><span class="sxs-lookup"><span data-stu-id="d6c22-173">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="d6c22-174">`Longlength` será útil se a matriz contiver mais de 2.147.483.647 elementos.</span><span class="sxs-lookup"><span data-stu-id="d6c22-174">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="d6c22-175">Rank</span><span class="sxs-lookup"><span data-stu-id="d6c22-175">Rank</span></span>

<span data-ttu-id="d6c22-176">Retorna o número de dimensões na matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-176">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="d6c22-177">A maioria das matrizes no PowerShell tem apenas uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="d6c22-177">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="d6c22-178">Mesmo quando você acredita que está criando uma matriz multidimensional; semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d6c22-178">Even when you think you are building a multidimensional array; like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

<span data-ttu-id="d6c22-179">O exemplo a seguir mostra como criar uma matriz verdadeiramente multidimensional usando o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6c22-179">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="d6c22-180">Métodos de matrizes</span><span class="sxs-lookup"><span data-stu-id="d6c22-180">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="d6c22-181">Limpar</span><span class="sxs-lookup"><span data-stu-id="d6c22-181">Clear</span></span>

<span data-ttu-id="d6c22-182">Define todos os valores de elemento como o _valor padrão_ do tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-182">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="d6c22-183">O método Clear () não redefine o tamanho da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-183">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="d6c22-184">No exemplo a seguir, `$a` há uma matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="d6c22-184">In the following example `$a` is an array of objects.</span></span>

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

<span data-ttu-id="d6c22-185">Neste exemplo, `$intA` é digitado explicitamente para conter inteiros.</span><span class="sxs-lookup"><span data-stu-id="d6c22-185">In this example, `$intA` is explicitly typed to contain integers.</span></span>

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a><span data-ttu-id="d6c22-186">ForEach</span><span class="sxs-lookup"><span data-stu-id="d6c22-186">ForEach</span></span>

<span data-ttu-id="d6c22-187">Permite iterar em todos os elementos na matriz e executar uma determinada operação para cada elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-187">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="d6c22-188">O método ForEach tem várias sobrecargas que executam operações diferentes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-188">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="d6c22-189">ForEach (expressão scriptblock)</span><span class="sxs-lookup"><span data-stu-id="d6c22-189">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="d6c22-190">ForEach (expressão scriptblock, argumentos Object [])</span><span class="sxs-lookup"><span data-stu-id="d6c22-190">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="d6c22-191">Esse método foi adicionado no PowerShell v4.</span><span class="sxs-lookup"><span data-stu-id="d6c22-191">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c22-192">A sintaxe requer o uso de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d6c22-192">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="d6c22-193">Os parênteses serão opcionais se o scriptblock for o único parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d6c22-193">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="d6c22-194">Além disso, não deve haver um espaço entre o método e o parêntese de abertura ou a chave.</span><span class="sxs-lookup"><span data-stu-id="d6c22-194">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="d6c22-195">O exemplo a seguir mostra como usar o método ForEach.</span><span class="sxs-lookup"><span data-stu-id="d6c22-195">The following example shows how use the foreach method.</span></span> <span data-ttu-id="d6c22-196">Nesse caso, a intenção é gerar o valor quadrado dos elementos na matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-196">In this case the intent is to generate the square value of the elements in the array.</span></span>

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

<span data-ttu-id="d6c22-197">Assim como o `-ArgumentList` parâmetro de `ForEach-Object` , o `arguments` parâmetro permite a passagem de uma matriz de argumentos para um bloco de script configurado para aceitá-los.</span><span class="sxs-lookup"><span data-stu-id="d6c22-197">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="d6c22-198">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="d6c22-198">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="d6c22-199">ForEach (tipo convertTotype)</span><span class="sxs-lookup"><span data-stu-id="d6c22-199">ForEach(type convertToType)</span></span>

<span data-ttu-id="d6c22-200">O `ForEach` método pode ser usado para converter rapidamente os elementos em um tipo diferente; o exemplo a seguir mostra como converter uma lista de datas de cadeia de caracteres para `[DateTime]` tipo.</span><span class="sxs-lookup"><span data-stu-id="d6c22-200">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="d6c22-201">ForEach (cadeia de caracteres propertyName)</span><span class="sxs-lookup"><span data-stu-id="d6c22-201">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="d6c22-202">ForEach (String propertyName, Object [] newValue)</span><span class="sxs-lookup"><span data-stu-id="d6c22-202">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="d6c22-203">O `ForEach` método também pode ser usado para recuperar rapidamente ou definir valores de propriedade para cada item na coleção.</span><span class="sxs-lookup"><span data-stu-id="d6c22-203">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="d6c22-204">ForEach (cadeia de caracteres methodName)</span><span class="sxs-lookup"><span data-stu-id="d6c22-204">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="d6c22-205">ForEach (cadeia de caracteres methodName, argumentos Object [])</span><span class="sxs-lookup"><span data-stu-id="d6c22-205">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="d6c22-206">Por fim, os `ForEach` métodos podem ser usados para executar um método em cada item da coleção.</span><span class="sxs-lookup"><span data-stu-id="d6c22-206">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="d6c22-207">Assim como o `-ArgumentList` parâmetro de `ForEach-Object` , o `arguments` parâmetro permite a passagem de uma matriz de argumentos para um bloco de script configurado para aceitá-los.</span><span class="sxs-lookup"><span data-stu-id="d6c22-207">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c22-208">A partir do Windows PowerShell 3,0 a recuperação de propriedades e execução de métodos para cada item em uma coleção também pode ser realizada usando "métodos de coleções e objetos escalares". você pode ler mais sobre isso aqui [about_methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="d6c22-208">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="d6c22-209">Where</span><span class="sxs-lookup"><span data-stu-id="d6c22-209">Where</span></span>

<span data-ttu-id="d6c22-210">Permite filtrar ou selecionar os elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-210">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="d6c22-211">O script deve ser avaliado como algo diferente de: zero (0), Cadeia de caracteres vazia `$false` ou `$null` para o elemento a ser mostrado após o `Where`</span><span class="sxs-lookup"><span data-stu-id="d6c22-211">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="d6c22-212">Há uma definição para o `Where` método.</span><span class="sxs-lookup"><span data-stu-id="d6c22-212">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="d6c22-213">A sintaxe requer o uso de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d6c22-213">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="d6c22-214">Os parênteses serão opcionais se o scriptblock for o único parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d6c22-214">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="d6c22-215">Além disso, não deve haver um espaço entre o método e o parêntese de abertura ou a chave.</span><span class="sxs-lookup"><span data-stu-id="d6c22-215">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="d6c22-216">O `Expression` scriptblock is é necessário para a filtragem, o `mode` argumento opcional permite recursos de seleção adicionais e o `numberToReturn` argumento opcional permite limitar quantos itens são retornados do filtro.</span><span class="sxs-lookup"><span data-stu-id="d6c22-216">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="d6c22-217">Os valores aceitáveis para `mode` são:</span><span class="sxs-lookup"><span data-stu-id="d6c22-217">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="d6c22-218">Padrão (0)-retornar todos os itens</span><span class="sxs-lookup"><span data-stu-id="d6c22-218">Default (0) - Return all items</span></span>
- <span data-ttu-id="d6c22-219">Primeiro (1)-retornar o primeiro item</span><span class="sxs-lookup"><span data-stu-id="d6c22-219">First (1) - Return the first item</span></span>
- <span data-ttu-id="d6c22-220">Último (2) – retornar o último item</span><span class="sxs-lookup"><span data-stu-id="d6c22-220">Last (2) - Return the last item</span></span>
- <span data-ttu-id="d6c22-221">SkipUntil (3) – ignorar itens até a condição ser verdadeira, retornar os itens restantes</span><span class="sxs-lookup"><span data-stu-id="d6c22-221">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="d6c22-222">Até (4) – retornar todos os itens até que a condição seja verdadeira</span><span class="sxs-lookup"><span data-stu-id="d6c22-222">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="d6c22-223">Split (5) – retornar uma matriz de dois elementos</span><span class="sxs-lookup"><span data-stu-id="d6c22-223">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="d6c22-224">O primeiro elemento contém itens correspondentes</span><span class="sxs-lookup"><span data-stu-id="d6c22-224">The first element contains matching items</span></span>
  - <span data-ttu-id="d6c22-225">O segundo elemento contém os itens restantes</span><span class="sxs-lookup"><span data-stu-id="d6c22-225">The second element contains the remaining items</span></span>

<span data-ttu-id="d6c22-226">O exemplo a seguir mostra como selecionar todos os números ímpares da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-226">The following example shows how to select all odd numbers from the array.</span></span>

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

<span data-ttu-id="d6c22-227">Este exemplo mostra como selecionar as cadeias de caracteres que não estão vazias.</span><span class="sxs-lookup"><span data-stu-id="d6c22-227">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="d6c22-228">Padrão</span><span class="sxs-lookup"><span data-stu-id="d6c22-228">Default</span></span>

<span data-ttu-id="d6c22-229">O `Default` modo filtra itens usando o `Expression` scriptblock.</span><span class="sxs-lookup"><span data-stu-id="d6c22-229">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="d6c22-230">Se um `numberToReturn` for fornecido, ele especificará o número máximo de itens a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="d6c22-230">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="d6c22-231">O `Default` modo e o `First` modo retornam os primeiros ( `numberToReturn` ) itens e podem ser usados de forma intercambiável.</span><span class="sxs-lookup"><span data-stu-id="d6c22-231">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="d6c22-232">Último</span><span class="sxs-lookup"><span data-stu-id="d6c22-232">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="d6c22-233">SkipUntil</span><span class="sxs-lookup"><span data-stu-id="d6c22-233">SkipUntil</span></span>

<span data-ttu-id="d6c22-234">O `SkipUntil` modo ignora todos os objetos em uma coleção até que um objeto passe o filtro de expressão de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d6c22-234">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="d6c22-235">Em seguida, ele retorna **todos os** itens de coleta restantes sem testá-los.</span><span class="sxs-lookup"><span data-stu-id="d6c22-235">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="d6c22-236">_Apenas um item de passagem é testado_ .</span><span class="sxs-lookup"><span data-stu-id="d6c22-236">_Only one passing item is tested_ .</span></span>

<span data-ttu-id="d6c22-237">Isso significa que a coleção retornada contém itens de _passagem_ e _não APROVADOs_ que não foram testados.</span><span class="sxs-lookup"><span data-stu-id="d6c22-237">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="d6c22-238">O número de itens retornados pode ser limitado passando um valor para o `numberToReturn` argumento.</span><span class="sxs-lookup"><span data-stu-id="d6c22-238">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="d6c22-239">Haja</span><span class="sxs-lookup"><span data-stu-id="d6c22-239">Until</span></span>

<span data-ttu-id="d6c22-240">O `Until` modo inverte o `SkipUntil` modo.</span><span class="sxs-lookup"><span data-stu-id="d6c22-240">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="d6c22-241">Ele retorna **todos os** itens em uma coleção até que um item passe a expressão de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d6c22-241">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="d6c22-242">Depois que um item _passa_ a expressão scriptblock, o `Where` método interrompe o processamento de itens.</span><span class="sxs-lookup"><span data-stu-id="d6c22-242">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="d6c22-243">Isso significa que você recebe o primeiro conjunto de itens _não aprovados_ do `Where` método.</span><span class="sxs-lookup"><span data-stu-id="d6c22-243">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="d6c22-244">_Depois_ que um item passa, o restante não é testado ou retornado.</span><span class="sxs-lookup"><span data-stu-id="d6c22-244">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="d6c22-245">O número de itens retornados pode ser limitado passando um valor para o `numberToReturn` argumento.</span><span class="sxs-lookup"><span data-stu-id="d6c22-245">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> <span data-ttu-id="d6c22-246">`Until`E `SkipUntil` operar com a premissa de não testar um lote de itens.</span><span class="sxs-lookup"><span data-stu-id="d6c22-246">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="d6c22-247">`Until` Retorna os itens **antes** da primeira _passagem_ .</span><span class="sxs-lookup"><span data-stu-id="d6c22-247">`Until` returns the items **BEFORE** the first _pass_ .</span></span>
>
> <span data-ttu-id="d6c22-248">`SkipUntil` Retorna todos os itens **após** a primeira _passagem_ , incluindo o primeiro item de passagem.</span><span class="sxs-lookup"><span data-stu-id="d6c22-248">`SkipUntil` returns all the items **AFTER** the first _pass_ , including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="d6c22-249">Divisão</span><span class="sxs-lookup"><span data-stu-id="d6c22-249">Split</span></span>

<span data-ttu-id="d6c22-250">O `Split` modo divide ou agrupa itens de coleção em duas coleções separadas.</span><span class="sxs-lookup"><span data-stu-id="d6c22-250">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="d6c22-251">Aqueles que passam a expressão scriptblock e os que não fazem.</span><span class="sxs-lookup"><span data-stu-id="d6c22-251">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="d6c22-252">Se um `numberToReturn` for especificado, a primeira coleção conterá os itens _aprovados_ , não para exceder o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="d6c22-252">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="d6c22-253">Os objetos restantes, até aqueles que **passam** o filtro de expressão, são retornados na segunda coleção.</span><span class="sxs-lookup"><span data-stu-id="d6c22-253">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="d6c22-254">Obter os membros de uma matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-254">Get the members of an array</span></span>

<span data-ttu-id="d6c22-255">Para obter as propriedades e os métodos de uma matriz, como a propriedade Length e o método **SetValue** , use o parâmetro **InputObject** do `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6c22-255">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="d6c22-256">Quando você canaliza uma matriz para `Get-Member` o, o PowerShell envia os itens um de cada vez e `Get-Member` retorna o tipo de cada item na matriz (ignorando duplicatas).</span><span class="sxs-lookup"><span data-stu-id="d6c22-256">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="d6c22-257">Quando você usa o parâmetro **InputObject** , `Get-Member` o retorna os membros da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-257">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="d6c22-258">Por exemplo, o comando a seguir obtém os membros da `$a` variável de matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-258">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="d6c22-259">Você também pode obter os membros de uma matriz digitando uma vírgula (,) antes do valor que é canalizado para o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6c22-259">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="d6c22-260">A vírgula torna a matriz o segundo item em uma matriz de matrizes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-260">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="d6c22-261">O PowerShell canaliza as matrizes uma de cada vez e `Get-Member` retorna os membros da matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-261">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="d6c22-262">Como os dois exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6c22-262">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="d6c22-263">Manipulando uma matriz</span><span class="sxs-lookup"><span data-stu-id="d6c22-263">Manipulating an array</span></span>

<span data-ttu-id="d6c22-264">Você pode alterar os elementos em uma matriz, adicionar um elemento a uma matriz e combinar os valores de duas matrizes em uma terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-264">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="d6c22-265">Para alterar o valor de um elemento específico em uma matriz, especifique o nome da matriz e o índice do elemento que você deseja alterar e, em seguida, use o operador de atribuição ( `=` ) para especificar um novo valor para o elemento.</span><span class="sxs-lookup"><span data-stu-id="d6c22-265">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="d6c22-266">Por exemplo, para alterar o valor do segundo item na `$a` matriz (posição de índice 1) para 10, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-266">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="d6c22-267">Você também pode usar o método **SetValue** de uma matriz para alterar um valor.</span><span class="sxs-lookup"><span data-stu-id="d6c22-267">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="d6c22-268">O exemplo a seguir altera o segundo valor (posição de índice 1) da `$a` matriz para 500:</span><span class="sxs-lookup"><span data-stu-id="d6c22-268">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="d6c22-269">Você pode usar o `+=` operador para adicionar um elemento a uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-269">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="d6c22-270">O exemplo a seguir mostra como adicionar um elemento à `$a` matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-270">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="d6c22-271">Quando você usa o `+=` operador, o PowerShell realmente cria uma nova matriz com os valores da matriz original e o valor adicionado.</span><span class="sxs-lookup"><span data-stu-id="d6c22-271">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="d6c22-272">Isso pode causar problemas de desempenho se a operação for repetida várias vezes ou o tamanho da matriz for muito grande.</span><span class="sxs-lookup"><span data-stu-id="d6c22-272">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="d6c22-273">Não é fácil excluir elementos de uma matriz, mas você pode criar uma nova matriz que contém apenas os elementos selecionados de uma matriz existente.</span><span class="sxs-lookup"><span data-stu-id="d6c22-273">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="d6c22-274">Por exemplo, para criar a `$t` matriz com todos os elementos na `$a` matriz, exceto para o valor na posição do índice 2, digite:</span><span class="sxs-lookup"><span data-stu-id="d6c22-274">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="d6c22-275">Para combinar duas matrizes em uma única matriz, use o operador de adição ( `+` ).</span><span class="sxs-lookup"><span data-stu-id="d6c22-275">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="d6c22-276">O exemplo a seguir cria duas matrizes, combina-as e, em seguida, exibe a matriz combinada resultante.</span><span class="sxs-lookup"><span data-stu-id="d6c22-276">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="d6c22-277">Como resultado, a `$z` matriz contém 1, 3, 5 e 9.</span><span class="sxs-lookup"><span data-stu-id="d6c22-277">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="d6c22-278">Para excluir uma matriz, atribua um valor de `$null` à matriz.</span><span class="sxs-lookup"><span data-stu-id="d6c22-278">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="d6c22-279">O comando a seguir exclui a matriz na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="d6c22-279">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="d6c22-280">Você também pode usar o `Remove-Item` cmdlet, mas atribuir um valor `$null` é mais rápido, especialmente para matrizes grandes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-280">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="d6c22-281">Matrizes de zero ou uma</span><span class="sxs-lookup"><span data-stu-id="d6c22-281">Arrays of zero or one</span></span>

<span data-ttu-id="d6c22-282">A partir do Windows PowerShell 3,0, uma coleção de zero ou um objeto tem a propriedade Count e length.</span><span class="sxs-lookup"><span data-stu-id="d6c22-282">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="d6c22-283">Além disso, você pode indexar em uma matriz de um objeto.</span><span class="sxs-lookup"><span data-stu-id="d6c22-283">Also, you can index into an array of one object.</span></span> <span data-ttu-id="d6c22-284">Esse recurso ajuda a evitar erros de script que ocorrem quando um comando que espera uma coleção tem menos de dois itens.</span><span class="sxs-lookup"><span data-stu-id="d6c22-284">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="d6c22-285">Os exemplos a seguir demonstram esse recurso.</span><span class="sxs-lookup"><span data-stu-id="d6c22-285">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="d6c22-286">Zero objetos</span><span class="sxs-lookup"><span data-stu-id="d6c22-286">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="d6c22-287">Um objeto</span><span class="sxs-lookup"><span data-stu-id="d6c22-287">One object</span></span>

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="d6c22-288">Suporte de indexação para objetos System. tupla</span><span class="sxs-lookup"><span data-stu-id="d6c22-288">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="d6c22-289">O PowerShell 6,1 adicionou o suporte para acesso indexado de objetos de **tupla** , semelhante a matrizes.</span><span class="sxs-lookup"><span data-stu-id="d6c22-289">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="d6c22-290">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6c22-290">For example:</span></span>

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

<span data-ttu-id="d6c22-291">Ao contrário de matrizes e outros objetos de coleção, os objetos de **tupla** são tratados como um único objeto quando passam pelo pipeline ou por parâmetros que dão suporte a matrizes de objetos.</span><span class="sxs-lookup"><span data-stu-id="d6c22-291">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="d6c22-292">Para obter mais informações, consulte [System. tupla](/dotnet/api/system.tuple).</span><span class="sxs-lookup"><span data-stu-id="d6c22-292">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6c22-293">Confira também</span><span class="sxs-lookup"><span data-stu-id="d6c22-293">See also</span></span>

- [<span data-ttu-id="d6c22-294">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="d6c22-294">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="d6c22-295">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="d6c22-295">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="d6c22-296">about_Operators</span><span class="sxs-lookup"><span data-stu-id="d6c22-296">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="d6c22-297">about_For</span><span class="sxs-lookup"><span data-stu-id="d6c22-297">about_For</span></span>](about_For.md)
- [<span data-ttu-id="d6c22-298">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="d6c22-298">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="d6c22-299">about_While</span><span class="sxs-lookup"><span data-stu-id="d6c22-299">about_While</span></span>](about_While.md)

