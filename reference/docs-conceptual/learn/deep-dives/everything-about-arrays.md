---
title: Tudo o que você queria saber sobre matrizes
description: As matrizes são um recurso fundamental de linguagem da maioria das linguagens de programação.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 5cab354a99b122401f8f8119de24e075cf9d21f8
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149599"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a><span data-ttu-id="1178a-103">Tudo o que você queria saber sobre matrizes</span><span class="sxs-lookup"><span data-stu-id="1178a-103">Everything you wanted to know about arrays</span></span>

<span data-ttu-id="1178a-104">As [matrizes][] são um recurso fundamental de linguagem da maioria das linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="1178a-104">[Arrays][] are a fundamental language feature of most programming languages.</span></span> <span data-ttu-id="1178a-105">Elas são uma coleção de valores ou objetos difíceis de evitar.</span><span class="sxs-lookup"><span data-stu-id="1178a-105">They're a collection of values or objects that are difficult to avoid.</span></span> <span data-ttu-id="1178a-106">Vamos examinar as matrizes e tudo o que elas têm a oferecer.</span><span class="sxs-lookup"><span data-stu-id="1178a-106">Let's take a close look at arrays and everything they have to offer.</span></span>

> [!NOTE]
> <span data-ttu-id="1178a-107">A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="1178a-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="1178a-108">A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="1178a-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="1178a-109">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="1178a-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="1178a-110">O que é uma matriz?</span><span class="sxs-lookup"><span data-stu-id="1178a-110">What is an array?</span></span>

<span data-ttu-id="1178a-111">Antes de mudar para as outras formas pelas quais o PowerShell faz uso das matrizes, começarei com uma descrição técnica básica do que são matrizes e como elas são usadas pela maioria das linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="1178a-111">I'm going to start with a basic technical description of what arrays are and how they are used by most programming languages before I shift into the other ways PowerShell makes use of them.</span></span>

<span data-ttu-id="1178a-112">Uma matriz é uma estrutura de dados que serve como uma coleção de vários itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-112">An array is a data structure that serves as a collection of multiple items.</span></span> <span data-ttu-id="1178a-113">Você pode iterar sobre a matriz ou acessar itens individuais usando um índice.</span><span class="sxs-lookup"><span data-stu-id="1178a-113">You can iterate over the array or access individual items using an index.</span></span> <span data-ttu-id="1178a-114">A matriz é criada como uma parte sequencial da memória, em que cada valor é armazenado ao lado do outro.</span><span class="sxs-lookup"><span data-stu-id="1178a-114">The array is created as a sequential chunk of memory where each value is stored right next to the other.</span></span>

<span data-ttu-id="1178a-115">Falarei sobre cada um desses detalhes adiante.</span><span class="sxs-lookup"><span data-stu-id="1178a-115">I'll touch on each of those details as we go.</span></span>

## <a name="basic-usage"></a><span data-ttu-id="1178a-116">Uso básico</span><span class="sxs-lookup"><span data-stu-id="1178a-116">Basic usage</span></span>

<span data-ttu-id="1178a-117">Como as matrizes são um recurso básico do PowerShell, há uma sintaxe simples para trabalhar com elas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1178a-117">Because arrays are such a basic feature of PowerShell, there is a simple syntax for working with them in PowerShell.</span></span>

### <a name="create-an-array"></a><span data-ttu-id="1178a-118">Criar uma matriz</span><span class="sxs-lookup"><span data-stu-id="1178a-118">Create an array</span></span>

<span data-ttu-id="1178a-119">Uma matriz vazia pode ser criada usando `@()`</span><span class="sxs-lookup"><span data-stu-id="1178a-119">An empty array can be created by using `@()`</span></span>

```powershell
PS> $data = @()
PS> $data.count
0
```

<span data-ttu-id="1178a-120">Podemos criar uma matriz e propagá-la com valores apenas colocando-os nos parênteses `@()`.</span><span class="sxs-lookup"><span data-stu-id="1178a-120">We can create an array and seed it with values just by placing them in the `@()` parentheses.</span></span>

```powershell
PS> $data = @('Zero','One','Two','Three')
PS> $data.count
4

PS> $data
Zero
One
Two
Three
```

<span data-ttu-id="1178a-121">Esta matriz tem quatro itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-121">This array has 4 items.</span></span> <span data-ttu-id="1178a-122">Quando chamamos a variável `$data`, vemos a lista de nossos itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-122">When we call the `$data` variable, we see the list of our items.</span></span> <span data-ttu-id="1178a-123">Se for uma matriz de cadeias de caracteres, obteremos uma linha por cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1178a-123">If it's an array of strings, then we get one line per string.</span></span>

<span data-ttu-id="1178a-124">Podemos declarar uma matriz em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="1178a-124">We can declare an array on multiple lines.</span></span> <span data-ttu-id="1178a-125">A vírgula é opcional nesse caso e, geralmente, deixada de fora.</span><span class="sxs-lookup"><span data-stu-id="1178a-125">The comma is optional in this case and generally left out.</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

<span data-ttu-id="1178a-126">Prefiro declarar minhas matrizes em várias linhas como essa.</span><span class="sxs-lookup"><span data-stu-id="1178a-126">I prefer to declare my arrays on multiple lines like that.</span></span> <span data-ttu-id="1178a-127">É mais fácil de ler quando você tem vários itens e também facilita a comparação com versões anteriores ao usar o controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="1178a-127">Not only does it get easier to read when you have multiple items, it also makes it easier to compare to previous versions when using source control.</span></span>

#### <a name="other-syntax"></a><span data-ttu-id="1178a-128">Outra sintaxe</span><span class="sxs-lookup"><span data-stu-id="1178a-128">Other syntax</span></span>

<span data-ttu-id="1178a-129">Normalmente compreende-se que `@()` é a sintaxe para criar uma matriz, mas as listas separadas por vírgulas funcionam na maior parte do tempo.</span><span class="sxs-lookup"><span data-stu-id="1178a-129">It's commonly understood that `@()` is the syntax for creating an array, but comma-separated lists work most of the time.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a><span data-ttu-id="1178a-130">Write-Output para criar matrizes</span><span class="sxs-lookup"><span data-stu-id="1178a-130">Write-Output to create arrays</span></span>

<span data-ttu-id="1178a-131">Um pequeno truque interessante que vale a pena mencionar é que você pode usar `Write-Output` para criar rapidamente cadeias de caracteres no console.</span><span class="sxs-lookup"><span data-stu-id="1178a-131">One cool little trick worth mentioning is that you can use `Write-Output` to quickly create strings at the console.</span></span>

```powershell
$data = Write-Output Zero One Two Three
```

<span data-ttu-id="1178a-132">Isso é útil porque você não precisa colocar aspas em volta das cadeias de caracteres quando o parâmetro aceita cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1178a-132">This is handy because you don't have to put quotes around the strings when the parameter accepts strings.</span></span> <span data-ttu-id="1178a-133">Eu nunca faria isso em um script, mas é um jogo justo no console.</span><span class="sxs-lookup"><span data-stu-id="1178a-133">I would never do this in a script but it's fair game in the console.</span></span>

### <a name="accessing-items"></a><span data-ttu-id="1178a-134">Acessando itens</span><span class="sxs-lookup"><span data-stu-id="1178a-134">Accessing items</span></span>

<span data-ttu-id="1178a-135">Agora que você tem uma matriz com itens, talvez queira acessar e atualizar esses itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-135">Now that you have an array with items in it, you may want to access and update those items.</span></span>

#### <a name="offset"></a><span data-ttu-id="1178a-136">Deslocamento</span><span class="sxs-lookup"><span data-stu-id="1178a-136">Offset</span></span>

<span data-ttu-id="1178a-137">Para acessar itens individuais, usamos os colchetes `[]` com um valor de deslocamento começando em 0.</span><span class="sxs-lookup"><span data-stu-id="1178a-137">To access individual items, we use the brackets `[]` with an offset value starting at 0.</span></span> <span data-ttu-id="1178a-138">É assim que obtemos o primeiro item em nossa matriz:</span><span class="sxs-lookup"><span data-stu-id="1178a-138">This is how we get the first item in our array:</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

<span data-ttu-id="1178a-139">O motivo pelo qual usamos zero aqui é porque o primeiro item está no início da lista; portanto, usamos um deslocamento de 0 item para chegar a ele.</span><span class="sxs-lookup"><span data-stu-id="1178a-139">The reason why we use zero here is because the first item is at the beginning of the list so we use an offset of 0 items to get to it.</span></span> <span data-ttu-id="1178a-140">Para chegar ao segundo item, precisamos usar um deslocamento de 1 para ignorar o primeiro item.</span><span class="sxs-lookup"><span data-stu-id="1178a-140">To get to the second item, we would need to use an offset of 1 to skip the first item.</span></span>

```powershell
PS> $data[1]
One
```

<span data-ttu-id="1178a-141">Isso significa que o último item está no deslocamento 3.</span><span class="sxs-lookup"><span data-stu-id="1178a-141">This would mean that the last item is at offset 3.</span></span>

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a><span data-ttu-id="1178a-142">Índice</span><span class="sxs-lookup"><span data-stu-id="1178a-142">Index</span></span>

<span data-ttu-id="1178a-143">Agora você pode ver por que escolhi os valores usados para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="1178a-143">Now you can see why I picked the values that I did for this example.</span></span> <span data-ttu-id="1178a-144">Apresentei isso como um deslocamento porque isso é o que realmente é, mas esse deslocamento é mais comumente referido como um índice.</span><span class="sxs-lookup"><span data-stu-id="1178a-144">I introduced this as an offset because that is what it really is, but this offset is more commonly referred to as an index.</span></span> <span data-ttu-id="1178a-145">Um índice que começa em `0`.</span><span class="sxs-lookup"><span data-stu-id="1178a-145">An index that starts at `0`.</span></span> <span data-ttu-id="1178a-146">No restante deste artigo, chamarei o deslocamento de um índice.</span><span class="sxs-lookup"><span data-stu-id="1178a-146">For the rest of this article I will call the offset an index.</span></span>

#### <a name="special-index-tricks"></a><span data-ttu-id="1178a-147">Truques de índice especial</span><span class="sxs-lookup"><span data-stu-id="1178a-147">Special index tricks</span></span>

<span data-ttu-id="1178a-148">Na maioria das linguagens, você só pode especificar um número como o índice e obter um só item de volta.</span><span class="sxs-lookup"><span data-stu-id="1178a-148">In most languages, you can only specify a single number as the index and you get a single item back.</span></span>
<span data-ttu-id="1178a-149">O PowerShell é muito mais flexível.</span><span class="sxs-lookup"><span data-stu-id="1178a-149">PowerShell is much more flexible.</span></span> <span data-ttu-id="1178a-150">Você pode usar vários índices ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1178a-150">You can use multiple indexes at once.</span></span> <span data-ttu-id="1178a-151">Ao fornecer uma lista de índices, podemos selecionar diversos itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-151">By providing a list of indexes, we can select several items.</span></span>

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

<span data-ttu-id="1178a-152">Os itens são retornados com base na ordem dos índices fornecidos.</span><span class="sxs-lookup"><span data-stu-id="1178a-152">The items are returned based on the order of the indexes provided.</span></span> <span data-ttu-id="1178a-153">Se você duplicar um índice, obterá esse item duas vezes.</span><span class="sxs-lookup"><span data-stu-id="1178a-153">If you duplicate an index, you get that item both times.</span></span>

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

<span data-ttu-id="1178a-154">Podemos especificar uma sequência de números com o operador `..` interno.</span><span class="sxs-lookup"><span data-stu-id="1178a-154">We can specify a sequence of numbers with the built-in `..` operator.</span></span>

```powershell
PS> $data[1..3]
One
Two
Three
```

<span data-ttu-id="1178a-155">Isso também funciona em ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="1178a-155">This works in reverse too.</span></span>

```powershell
PS> $data[3..1]
Three
Two
One
```

<span data-ttu-id="1178a-156">Você pode usar valores de índice negativos para compensar do final.</span><span class="sxs-lookup"><span data-stu-id="1178a-156">You can use negative index values to offset from the end.</span></span> <span data-ttu-id="1178a-157">Portanto, se você precisar do último item da lista, poderá usar `-1`.</span><span class="sxs-lookup"><span data-stu-id="1178a-157">So if you need the last item in the list, you can use `-1`.</span></span>

```powershell
PS> $data[-1]
Three
```

<span data-ttu-id="1178a-158">Uma palavra de prudência aqui com o operador `..`.</span><span class="sxs-lookup"><span data-stu-id="1178a-158">One word of caution here with the `..` operator.</span></span> <span data-ttu-id="1178a-159">A sequência `0..-1` e `-1..0` avalia os valores `0,-1` e `-1,0`.</span><span class="sxs-lookup"><span data-stu-id="1178a-159">The sequence `0..-1` and `-1..0` evaluate to the values `0,-1` and `-1,0`.</span></span> <span data-ttu-id="1178a-160">É fácil ver `$data[0..-1]` e pensar que ele enumerará todos os itens se você esquecer esse detalhe.</span><span class="sxs-lookup"><span data-stu-id="1178a-160">It's easy to see `$data[0..-1]` and think it would enumerate all items if you forget this detail.</span></span> <span data-ttu-id="1178a-161">`$data[0..-1]` fornece o mesmo valor que `$data[0,-1]` fornecendo o primeiro e o último item na matriz (e nenhum dos outros valores).</span><span class="sxs-lookup"><span data-stu-id="1178a-161">`$data[0..-1]` gives you the same value as `$data[0,-1]` by giving you the first and last item in the array (and none of the other values).</span></span>

#### <a name="out-of-bounds"></a><span data-ttu-id="1178a-162">Fora dos limites</span><span class="sxs-lookup"><span data-stu-id="1178a-162">Out of bounds</span></span>

<span data-ttu-id="1178a-163">Na maioria das linguagens, se você tentar acessar um índice de um item que ultrapassa o fim da matriz, obteria algum tipo de erro ou exceção.</span><span class="sxs-lookup"><span data-stu-id="1178a-163">In most languages, if you try to access an index of an item that is past the end of the array, you would get some type of error or an exception.</span></span> <span data-ttu-id="1178a-164">O PowerShell silenciosamente não retorna nada.</span><span class="sxs-lookup"><span data-stu-id="1178a-164">PowerShell silently returns nothing.</span></span>

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a><span data-ttu-id="1178a-165">Não é possível indexar em uma matriz nula</span><span class="sxs-lookup"><span data-stu-id="1178a-165">Cannot index into a null array</span></span>

<span data-ttu-id="1178a-166">Se a variável for `$null` e você tentar indexá-la como uma matriz, você receberá uma exceção `System.Management.Automation.RuntimeException` com a mensagem `Cannot index into a null array`.</span><span class="sxs-lookup"><span data-stu-id="1178a-166">If your variable is `$null` and you try to index it like an array, you get a `System.Management.Automation.RuntimeException` exception with the message `Cannot index into a null array`.</span></span>

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

<span data-ttu-id="1178a-167">Portanto, verifique se suas matrizes não são `$null` antes de tentar acessar elementos dentro delas.</span><span class="sxs-lookup"><span data-stu-id="1178a-167">So make sure your arrays are not `$null` before you try to access elements inside them.</span></span>

#### <a name="count"></a><span data-ttu-id="1178a-168">Contagem</span><span class="sxs-lookup"><span data-stu-id="1178a-168">Count</span></span>

<span data-ttu-id="1178a-169">Matrizes e outras coleções têm uma propriedade de contagem que informa quantos itens estão na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-169">Arrays and other collections have a count property that tells you how many items are in the array.</span></span>

```powershell
PS> $data.count
4
```

<span data-ttu-id="1178a-170">O PowerShell 3.0 adicionou uma propriedade de contagem à maioria dos objetos.</span><span class="sxs-lookup"><span data-stu-id="1178a-170">PowerShell 3.0 added a count property to most objects.</span></span> <span data-ttu-id="1178a-171">Você pode ter um só objeto e ele deve fornecer uma contagem de `1`.</span><span class="sxs-lookup"><span data-stu-id="1178a-171">you can have a single object and it should give you a count of `1`.</span></span>

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

<span data-ttu-id="1178a-172">Até mesmo `$null` tem uma propriedade de contagem, exceto que retorna `0`.</span><span class="sxs-lookup"><span data-stu-id="1178a-172">Even `$null` has a count property except it returns `0`.</span></span>

```powershell
PS> $null.count
0
```

<span data-ttu-id="1178a-173">Há algumas armadilhas aqui que vou revisitar quando eu abordar a verificação de `$null` ou de matrizes vazias posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="1178a-173">There are some traps here that I will revisit when I cover checking for `$null` or empty arrays later on in this article.</span></span>

#### <a name="off-by-one-errors"></a><span data-ttu-id="1178a-174">Erros por falta de uma repetição</span><span class="sxs-lookup"><span data-stu-id="1178a-174">Off-by-one errors</span></span>

<span data-ttu-id="1178a-175">Um erro de programação comum é criado porque as matrizes começam no índice 0.</span><span class="sxs-lookup"><span data-stu-id="1178a-175">A common programming error is created because arrays start at index 0.</span></span> <span data-ttu-id="1178a-176">Os erros por falta de uma repetição podem ser introduzidos de duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="1178a-176">Off-by-one errors can be introduced in two ways.</span></span>

<span data-ttu-id="1178a-177">A primeira é pensando que você deseja o segundo item e usando um índice de `2` e realmente obter o terceiro item.</span><span class="sxs-lookup"><span data-stu-id="1178a-177">The first is by mentally thinking you want the second item and using an index of `2` and really getting the third item.</span></span> <span data-ttu-id="1178a-178">Ou, pensando que você tem quatro itens e deseja o último item, você usa a contagem para acessar o último item.</span><span class="sxs-lookup"><span data-stu-id="1178a-178">Or by thinking that you have four items and you want last item, so you use the count to access the last item.</span></span>

```powershell
$data[ $data.count ]
```

<span data-ttu-id="1178a-179">O PowerShell está perfeitamente satisfeito em permitir que você faça isso e dá a você exatamente o item existente no índice 4: `$null`.</span><span class="sxs-lookup"><span data-stu-id="1178a-179">PowerShell is perfectly happy to let you do that and give you exactly what item exists at index 4: `$null`.</span></span> <span data-ttu-id="1178a-180">Você deve estar usando `$data.count - 1` ou o `-1` que aprendemos acima.</span><span class="sxs-lookup"><span data-stu-id="1178a-180">You should be using `$data.count - 1` or the `-1` that we learned about above.</span></span>

```powershell
PS> $data[ $data.count - 1 ]
Three
```

<span data-ttu-id="1178a-181">É aqui que você pode usar o índice `-1` para obter o último elemento.</span><span class="sxs-lookup"><span data-stu-id="1178a-181">This is where you can use the `-1` index to get the last element.</span></span>

```powershell
PS> $data[ -1 ]
Three
```

<span data-ttu-id="1178a-182">Lee Dailey também apontou para mim que podemos usar `$data.GetUpperBound(0)` para obter o número de índice máximo.</span><span class="sxs-lookup"><span data-stu-id="1178a-182">Lee Dailey also pointed out to me that we can use `$data.GetUpperBound(0)` to get the max index number.</span></span>

```powershell
PS> $data.GetUpperBound(0)
Three
```

<span data-ttu-id="1178a-183">A segunda maneira mais comum é ao iterar a lista e não parar no momento certo.</span><span class="sxs-lookup"><span data-stu-id="1178a-183">The second most common way is when iterating the list and not stopping at the right time.</span></span> <span data-ttu-id="1178a-184">Revisitarei isso quando falarmos sobre o uso do loop `for`.</span><span class="sxs-lookup"><span data-stu-id="1178a-184">I'll revisit this when we talk about using the `for` loop.</span></span>

### <a name="updating-items"></a><span data-ttu-id="1178a-185">Atualizando itens</span><span class="sxs-lookup"><span data-stu-id="1178a-185">Updating items</span></span>

<span data-ttu-id="1178a-186">Podemos usar o mesmo índice para atualizar itens existentes na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-186">We can use the same index to update existing items in the array.</span></span> <span data-ttu-id="1178a-187">Isso nos dá acesso direto para atualizar itens individuais.</span><span class="sxs-lookup"><span data-stu-id="1178a-187">This gives us direct access to update individual items.</span></span>

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

<span data-ttu-id="1178a-188">Se tentarmos atualizar um item que está além do último elemento, obteremos um erro `Index was outside the bounds of the array.`.</span><span class="sxs-lookup"><span data-stu-id="1178a-188">If we try to update an item that is past the last element, then we get an `Index was outside the bounds of the array.` error.</span></span>

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

<span data-ttu-id="1178a-189">Revisitarei isso mais tarde quando falar sobre como aumentar uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-189">I'll revisit this later when I talk about how to make an array larger.</span></span>

### <a name="iteration"></a><span data-ttu-id="1178a-190">Iteração</span><span class="sxs-lookup"><span data-stu-id="1178a-190">Iteration</span></span>

<span data-ttu-id="1178a-191">Em algum momento, talvez seja necessário percorrer ou iterar toda a lista e executar alguma ação para cada item na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-191">At some point, you might need to walk or iterate the entire list and perform some action for each item in the array.</span></span>

#### <a name="pipeline"></a><span data-ttu-id="1178a-192">Pipeline</span><span class="sxs-lookup"><span data-stu-id="1178a-192">Pipeline</span></span>

<span data-ttu-id="1178a-193">As matrizes e o pipeline do PowerShell são destinados para si.</span><span class="sxs-lookup"><span data-stu-id="1178a-193">Arrays and the PowerShell pipeline are meant for each other.</span></span> <span data-ttu-id="1178a-194">Essa é uma das maneiras mais simples de processar esses valores.</span><span class="sxs-lookup"><span data-stu-id="1178a-194">This is one of the simplest ways to process over those values.</span></span> <span data-ttu-id="1178a-195">Quando você passa uma matriz para um pipeline, cada item dentro da matriz é processado individualmente.</span><span class="sxs-lookup"><span data-stu-id="1178a-195">When you pass an array to a pipeline, each item inside the array is processed individually.</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

<span data-ttu-id="1178a-196">Se você ainda não viu `$PSItem` antes, apenas saiba que ele é o mesmo que `$_`.</span><span class="sxs-lookup"><span data-stu-id="1178a-196">If you have not seen `$PSItem` before, just know that it's the same thing as `$_`.</span></span> <span data-ttu-id="1178a-197">Você pode usar um deles porque ambos representam o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="1178a-197">You can use either one because they both represent the current object in the pipeline.</span></span>

#### <a name="foreach-loop"></a><span data-ttu-id="1178a-198">Loop ForEach</span><span class="sxs-lookup"><span data-stu-id="1178a-198">ForEach loop</span></span>

<span data-ttu-id="1178a-199">O loop `ForEach` funciona bem com coleções.</span><span class="sxs-lookup"><span data-stu-id="1178a-199">The `ForEach` loop works well with collections.</span></span> <span data-ttu-id="1178a-200">Usando a sintaxe: `foreach ( <variable> in <collection> )`</span><span class="sxs-lookup"><span data-stu-id="1178a-200">Using the syntax: `foreach ( <variable> in <collection> )`</span></span>

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a><span data-ttu-id="1178a-201">Método ForEach</span><span class="sxs-lookup"><span data-stu-id="1178a-201">ForEach method</span></span>

<span data-ttu-id="1178a-202">Eu tenho a tendência de esquecer deste, mas ele funciona bem para operações simples.</span><span class="sxs-lookup"><span data-stu-id="1178a-202">I tend to forget about this one but it works well for simple operations.</span></span> <span data-ttu-id="1178a-203">O PowerShell permite que você chame `.ForEach()` em uma coleção.</span><span class="sxs-lookup"><span data-stu-id="1178a-203">PowerShell allows you to call `.ForEach()` on a collection.</span></span>

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

<span data-ttu-id="1178a-204">O `.foreach()` usa um parâmetro que é um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="1178a-204">The `.foreach()` takes a parameter that is a script block.</span></span> <span data-ttu-id="1178a-205">Você pode descartar os parênteses e apenas fornecer o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="1178a-205">You can drop the parentheses and just provide the script block.</span></span>

```powershell
$data.foreach{"Item [$PSItem]"}
```

<span data-ttu-id="1178a-206">Essa é uma sintaxe menos conhecida, mas funciona exatamente da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="1178a-206">This is a lesser known syntax but it works just the same.</span></span> <span data-ttu-id="1178a-207">Este método `foreach` foi adicionado no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="1178a-207">This `foreach` method was added in PowerShell 4.0.</span></span>

#### <a name="for-loop"></a><span data-ttu-id="1178a-208">Loop for</span><span class="sxs-lookup"><span data-stu-id="1178a-208">For loop</span></span>

<span data-ttu-id="1178a-209">O loop `for` é muito usado na maioria das outras linguagens, mas você não o vê muito no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1178a-209">The `for` loop is used heavily in most other languages but you don’t see it much in PowerShell.</span></span> <span data-ttu-id="1178a-210">Quando você o vê, geralmente está no contexto da movimentação de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-210">When you do see it, it's often in the context of walking an array.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="1178a-211">A primeira ação é inicializar um `$index` para `0`.</span><span class="sxs-lookup"><span data-stu-id="1178a-211">The first thing we do is initialize an `$index` to `0`.</span></span> <span data-ttu-id="1178a-212">Em seguida, adicionamos a condição de que `$index` deve ser menor que `$data.count`.</span><span class="sxs-lookup"><span data-stu-id="1178a-212">Then we add the condition that `$index` must be less than `$data.count`.</span></span> <span data-ttu-id="1178a-213">Por fim, especificamos que, toda vez que executamos um loop, o índice precisa ser aumentado em `1`.</span><span class="sxs-lookup"><span data-stu-id="1178a-213">Finally, we specify that every time we loop that me must increase the index by `1`.</span></span> <span data-ttu-id="1178a-214">Nesse caso, `$index++` é a abreviação de `$index = $index + 1`.</span><span class="sxs-lookup"><span data-stu-id="1178a-214">In this case `$index++` is short for `$index = $index + 1`.</span></span>

<span data-ttu-id="1178a-215">Sempre que você estiver usando um loop `for`, preste atenção especial à condição.</span><span class="sxs-lookup"><span data-stu-id="1178a-215">Whenever you're using a `for` loop, pay special attention to the condition.</span></span> <span data-ttu-id="1178a-216">Usei `$index -lt $data.count` aqui.</span><span class="sxs-lookup"><span data-stu-id="1178a-216">I used `$index -lt $data.count` here.</span></span> <span data-ttu-id="1178a-217">É fácil obter uma condição um pouco errada para obter um erro por falta de uma repetição em sua lógica.</span><span class="sxs-lookup"><span data-stu-id="1178a-217">It's easy to get the condition slightly wrong to get an off-by-one error in your logic.</span></span> <span data-ttu-id="1178a-218">É errado usar `$index -le $data.count` ou `$index -lt ($data.count - 1)`.</span><span class="sxs-lookup"><span data-stu-id="1178a-218">Using `$index -le $data.count` or `$index -lt ($data.count - 1)` are ever so slightly wrong.</span></span> <span data-ttu-id="1178a-219">Isso faria com que o resultado processasse muitos ou poucos itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-219">That would cause your result to process too many or too few items.</span></span> <span data-ttu-id="1178a-220">Este é o clássico erro por falta de uma repetição.</span><span class="sxs-lookup"><span data-stu-id="1178a-220">This is the classic off-by-one error.</span></span>

#### <a name="switch-loop"></a><span data-ttu-id="1178a-221">Loop switch</span><span class="sxs-lookup"><span data-stu-id="1178a-221">Switch loop</span></span>

<span data-ttu-id="1178a-222">Este é fácil de ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="1178a-222">This is one that is easy to overlook.</span></span> <span data-ttu-id="1178a-223">Se você fornecer uma matriz a uma [instrução switch][], ela verificará cada item na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-223">If you provide an array to a [switch statement][], it checks each item in the array.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
switch( $data )
{
    'One'
    {
        'Tock'
    }
    'Three'
    {
        'Tock'
    }
    Default
    {
        'Tick'
    }
}
```

```Output
Tick
Tock
Tick
Tock
```

<span data-ttu-id="1178a-224">Há muitas ações legais que podemos fazer com a instrução switch.</span><span class="sxs-lookup"><span data-stu-id="1178a-224">There are a lot of cool things that we can do with the switch statement.</span></span> <span data-ttu-id="1178a-225">Tenho outro artigo dedicado a isso.</span><span class="sxs-lookup"><span data-stu-id="1178a-225">I have another article dedicated to this.</span></span>

- <span data-ttu-id="1178a-226">[Tudo o que você queria saber sobre a instrução switch][instrução switch]</span><span class="sxs-lookup"><span data-stu-id="1178a-226">[Everything you ever wanted to know about the switch statement][switch statement]</span></span>

#### <a name="updating-values"></a><span data-ttu-id="1178a-227">Atualizando valores</span><span class="sxs-lookup"><span data-stu-id="1178a-227">Updating values</span></span>

<span data-ttu-id="1178a-228">Quando a matriz é uma coleção de cadeia de caracteres ou inteiros (tipos de valor), às vezes, convém atualizar os valores na matriz conforme você faz um loop sobre eles.</span><span class="sxs-lookup"><span data-stu-id="1178a-228">When your array is a collection of string or integers (value types), sometimes you may want to update the values in the array as you loop over them.</span></span> <span data-ttu-id="1178a-229">A maioria dos loops acima usa uma variável no loop que contém uma cópia do valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-229">Most of the loops above use a variable in the loop that holds a copy of the value.</span></span> <span data-ttu-id="1178a-230">Se você atualizar essa variável, o valor original na matriz não será atualizado.</span><span class="sxs-lookup"><span data-stu-id="1178a-230">If you update that variable, the original value in the array is not updated.</span></span>

<span data-ttu-id="1178a-231">A exceção a essa instrução é o loop `for`.</span><span class="sxs-lookup"><span data-stu-id="1178a-231">The exception to that statement is the `for` loop.</span></span> <span data-ttu-id="1178a-232">Se você quiser percorrer uma matriz e atualizar valores dentro dela, o loop `for` será o que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="1178a-232">If you want to walk an array and update values inside it, then the `for` loop is what you're looking for.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="1178a-233">Este exemplo usa um valor por índice, faz algumas alterações e usa esse mesmo índice para atribuí-lo de volta.</span><span class="sxs-lookup"><span data-stu-id="1178a-233">This example takes a value by index, makes a few changes, and then uses that same index to assign it back.</span></span>

## <a name="arrays-of-objects"></a><span data-ttu-id="1178a-234">Matrizes de objetos</span><span class="sxs-lookup"><span data-stu-id="1178a-234">Arrays of Objects</span></span>

<span data-ttu-id="1178a-235">Até agora, o único item que colocamos em uma matriz é um tipo de valor, mas as matrizes também podem conter objetos.</span><span class="sxs-lookup"><span data-stu-id="1178a-235">So far, the only thing we've placed in an array is a value type, but arrays can also contain objects.</span></span>

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

<span data-ttu-id="1178a-236">Muitos cmdlets retornam coleções de objetos como matrizes quando você os atribui a uma variável.</span><span class="sxs-lookup"><span data-stu-id="1178a-236">Many cmdlets return collections of objects as arrays when you assign them to a variable.</span></span>

```powershell
$processList = Get-Process
```

<span data-ttu-id="1178a-237">Todos os recursos básicos dos quais já falamos ainda se aplicam a matrizes de objetos com alguns detalhes que valem a pena destacar.</span><span class="sxs-lookup"><span data-stu-id="1178a-237">All of the basic features we already talked about still apply to arrays of objects with a few details worth pointing out.</span></span>

### <a name="accessing-properties"></a><span data-ttu-id="1178a-238">Acessando propriedades</span><span class="sxs-lookup"><span data-stu-id="1178a-238">Accessing properties</span></span>

<span data-ttu-id="1178a-239">Podemos usar um índice para acessar um item individual em uma coleção, assim como ocorre com tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-239">We can use an index to access an individual item in a collection just like with value types.</span></span>

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="1178a-240">Podemos acessar e atualizar as propriedades diretamente.</span><span class="sxs-lookup"><span data-stu-id="1178a-240">We can access and update properties directly.</span></span>

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a><span data-ttu-id="1178a-241">Propriedades da matriz</span><span class="sxs-lookup"><span data-stu-id="1178a-241">Array properties</span></span>

<span data-ttu-id="1178a-242">Normalmente, você teria que enumerar a lista inteira como esta para acessar todas as propriedades:</span><span class="sxs-lookup"><span data-stu-id="1178a-242">Normally you would have to enumerate the whole list like this to access all the properties:</span></span>

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

<span data-ttu-id="1178a-243">Ou usar o cmdlet `Select-Object -ExpandProperty`.</span><span class="sxs-lookup"><span data-stu-id="1178a-243">Or by using the `Select-Object -ExpandProperty` cmdlet.</span></span>

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

<span data-ttu-id="1178a-244">Mas o PowerShell permite solicitar `LastName` diretamente.</span><span class="sxs-lookup"><span data-stu-id="1178a-244">But PowerShell offers us the ability to request `LastName` directly.</span></span> <span data-ttu-id="1178a-245">O PowerShell enumera todas elas para nós e retorna uma lista limpa.</span><span class="sxs-lookup"><span data-stu-id="1178a-245">PowerShell enumerates them all for us and returns a clean list.</span></span>

```powershell
PS> $data.LastName

Marquette
Doe
```

<span data-ttu-id="1178a-246">A enumeração ainda acontece, mas não vemos a complexidade por trás dela.</span><span class="sxs-lookup"><span data-stu-id="1178a-246">The enumeration still happens but we don't see the complexity behind it.</span></span>

### <a name="where-object-filtering"></a><span data-ttu-id="1178a-247">Filtragem Where-Object</span><span class="sxs-lookup"><span data-stu-id="1178a-247">Where-Object filtering</span></span>

<span data-ttu-id="1178a-248">É aí que `Where-Object` entra em ação para que possamos filtrar e selecionar o que desejamos para fora da matriz com base nas propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="1178a-248">This is where `Where-Object` comes in so we can filter and select what we want out of the array based on the properties of the object.</span></span>

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="1178a-249">Podemos gravar essa mesma consulta para obter o `FirstName` que estamos procurando.</span><span class="sxs-lookup"><span data-stu-id="1178a-249">We can write that same query to get the `FirstName` we are looking for.</span></span>

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a><span data-ttu-id="1178a-250">Where()</span><span class="sxs-lookup"><span data-stu-id="1178a-250">Where()</span></span>

<span data-ttu-id="1178a-251">As matrizes têm um método `Where()` que permite especificar um `scriptblock` para o filtro.</span><span class="sxs-lookup"><span data-stu-id="1178a-251">Arrays have a `Where()` method on them that allows you to specify a `scriptblock` for the filter.</span></span>

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

<span data-ttu-id="1178a-252">Este recurso foi adicionado no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="1178a-252">This feature was added in PowerShell 4.0.</span></span>

### <a name="updating-objects-in-loops"></a><span data-ttu-id="1178a-253">Atualizando objetos em loops</span><span class="sxs-lookup"><span data-stu-id="1178a-253">Updating objects in loops</span></span>

<span data-ttu-id="1178a-254">Com tipos de valor, a única maneira de atualizar a matriz é usando um loop for, pois precisamos saber o índice para substituir o valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-254">With value types, the only way to update the array is to use a for loop because we need to know the index to replace the value.</span></span> <span data-ttu-id="1178a-255">Temos mais opções com objetos porque são tipos de referência.</span><span class="sxs-lookup"><span data-stu-id="1178a-255">We have more options with objects because they are reference types.</span></span> <span data-ttu-id="1178a-256">Aqui está um exemplo rápido:</span><span class="sxs-lookup"><span data-stu-id="1178a-256">Here is a quick example:</span></span>

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

<span data-ttu-id="1178a-257">Este loop está examinando cada objeto na matriz `$data`.</span><span class="sxs-lookup"><span data-stu-id="1178a-257">This loop is walking every object in the `$data` array.</span></span> <span data-ttu-id="1178a-258">Como os objetos são tipos de referência, a variável `$person` referencia exatamente o mesmo objeto que está na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-258">Because objects are reference types, the `$person` variable references the exact same object that is in the array.</span></span> <span data-ttu-id="1178a-259">Portanto, as atualizações para suas propriedades atualizam o original.</span><span class="sxs-lookup"><span data-stu-id="1178a-259">So updates to its properties do update the original.</span></span>

<span data-ttu-id="1178a-260">Você ainda não pode substituir o objeto inteiro dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="1178a-260">You still can't replace the whole object this way.</span></span> <span data-ttu-id="1178a-261">Se você tentar atribuir um novo objeto à variável `$person`, estará atualizando a referência de variável para algo que não aponta mais para o objeto original na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-261">If you try to assign a new object to the `$person` variable, you're updating the variable reference to something else that no longer points to the original object in the array.</span></span> <span data-ttu-id="1178a-262">Isso não funciona como você esperaria:</span><span class="sxs-lookup"><span data-stu-id="1178a-262">This doesn't work like you would expect:</span></span>

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a><span data-ttu-id="1178a-263">Operadores</span><span class="sxs-lookup"><span data-stu-id="1178a-263">Operators</span></span>

<span data-ttu-id="1178a-264">Os operadores no PowerShell também funcionam em matrizes.</span><span class="sxs-lookup"><span data-stu-id="1178a-264">The operators in PowerShell also work on arrays.</span></span> <span data-ttu-id="1178a-265">Alguns deles funcionam de modo ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="1178a-265">Some of them work slightly differently.</span></span>

### <a name="-join"></a><span data-ttu-id="1178a-266">-join</span><span class="sxs-lookup"><span data-stu-id="1178a-266">-join</span></span>

<span data-ttu-id="1178a-267">O operador `-join` é o mais óbvio. Portanto, vamos dar uma olhada nele primeiro.</span><span class="sxs-lookup"><span data-stu-id="1178a-267">The `-join` operator is the most obvious one so let's look at it first.</span></span> <span data-ttu-id="1178a-268">Gosto do operador `-join` e o uso com frequência.</span><span class="sxs-lookup"><span data-stu-id="1178a-268">I like the `-join` operator and use it often.</span></span> <span data-ttu-id="1178a-269">Ele une todos os elementos na matriz com o caractere ou a cadeia de caracteres que você especificar.</span><span class="sxs-lookup"><span data-stu-id="1178a-269">It joins all elements in the array with the character or string that you specify.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

<span data-ttu-id="1178a-270">Um dos recursos que gosto sobre o operador `-join` é que ele lida com itens únicos.</span><span class="sxs-lookup"><span data-stu-id="1178a-270">One of the features that I like about the `-join` operator is that it handles single items.</span></span>

```powershell
PS> 1 -join '-'
1
```

<span data-ttu-id="1178a-271">Uso isso dentro de mensagens de registro em log e detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1178a-271">I use this inside logging and verbose messages.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a><span data-ttu-id="1178a-272">-join $array</span><span class="sxs-lookup"><span data-stu-id="1178a-272">-join $array</span></span>

<span data-ttu-id="1178a-273">Aqui está um truque inteligente que Lee Dailey destacou para mim.</span><span class="sxs-lookup"><span data-stu-id="1178a-273">Here is a clever trick that Lee Dailey pointed out to me.</span></span> <span data-ttu-id="1178a-274">Se você quiser unir tudo sem um delimitador, em vez de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="1178a-274">If you ever want to join everything without a delimiter, instead of doing this:</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

<span data-ttu-id="1178a-275">Você pode usar `-join` com a matriz como o parâmetro sem prefixo.</span><span class="sxs-lookup"><span data-stu-id="1178a-275">You can use `-join` with the array as the parameter with no prefix.</span></span> <span data-ttu-id="1178a-276">Dê uma olhada neste exemplo para ver do que estou falando.</span><span class="sxs-lookup"><span data-stu-id="1178a-276">Take a look at this example to see that I'm talking about.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a><span data-ttu-id="1178a-277">-replace e -split</span><span class="sxs-lookup"><span data-stu-id="1178a-277">-replace and -split</span></span>

<span data-ttu-id="1178a-278">Os outros operadores, como `-replace` e `-split` são executados em cada item da matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-278">The other operators like `-replace` and `-split` execute on each item in the array.</span></span> <span data-ttu-id="1178a-279">Não posso dizer que já os usei dessa forma, mas aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1178a-279">I can't say that I have ever used them this way but here is an example.</span></span>

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a><span data-ttu-id="1178a-280">-contains</span><span class="sxs-lookup"><span data-stu-id="1178a-280">-contains</span></span>

<span data-ttu-id="1178a-281">O operador `-contains` permite que você verifique uma matriz de valores para ver se ela contém um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="1178a-281">The `-contains` operator allows you to check an array of values to see if it contains a specified value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a><span data-ttu-id="1178a-282">-in</span><span class="sxs-lookup"><span data-stu-id="1178a-282">-in</span></span>

<span data-ttu-id="1178a-283">Quando você tem um só valor que deseja verificar correspondências a um de vários valores, pode usar o operador `-in`.</span><span class="sxs-lookup"><span data-stu-id="1178a-283">When you have a single value that you would like to verify matches one of several values, you can use the `-in` operator.</span></span> <span data-ttu-id="1178a-284">O valor estaria à esquerda e a matriz no lado direito da operação.</span><span class="sxs-lookup"><span data-stu-id="1178a-284">The value would be on the left and the array on the right-hand side of the operation.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

<span data-ttu-id="1178a-285">Isso pode ser caro se a lista for grande.</span><span class="sxs-lookup"><span data-stu-id="1178a-285">This can get expensive if the list is large.</span></span> <span data-ttu-id="1178a-286">Geralmente uso um padrão regex se eu estiver verificando mais do que alguns valores.</span><span class="sxs-lookup"><span data-stu-id="1178a-286">I often use a regex pattern if I'm checking more than a few values.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a><span data-ttu-id="1178a-287">-eq e -ne</span><span class="sxs-lookup"><span data-stu-id="1178a-287">-eq and -ne</span></span>

<span data-ttu-id="1178a-288">Igualdade e matrizes podem ficar complicadas.</span><span class="sxs-lookup"><span data-stu-id="1178a-288">Equality and arrays can get complicated.</span></span> <span data-ttu-id="1178a-289">Quando a matriz está no lado esquerdo, cada item é comparado.</span><span class="sxs-lookup"><span data-stu-id="1178a-289">When the array is on the left side, every item gets compared.</span></span> <span data-ttu-id="1178a-290">Em vez de retornar `True`, ela retorna o objeto correspondente.</span><span class="sxs-lookup"><span data-stu-id="1178a-290">Instead of returning `True`, it returns the object that matches.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

<span data-ttu-id="1178a-291">Quando usamos o operador `-ne`, obtemos todos os valores que não são iguais ao nosso valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-291">When you use the `-ne` operator, we get all the values that are not equal to our value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

<span data-ttu-id="1178a-292">Quando você usa isso em uma instrução `if()`, um valor retornado é um valor `True`.</span><span class="sxs-lookup"><span data-stu-id="1178a-292">When you use this in an `if()` statement, a value that is returned is a `True` value.</span></span> <span data-ttu-id="1178a-293">Se nenhum valor for retornado, será um valor `False`.</span><span class="sxs-lookup"><span data-stu-id="1178a-293">If no value is returned, then it's a `False` value.</span></span> <span data-ttu-id="1178a-294">Ambas as próximas instruções são avaliadas como `True`.</span><span class="sxs-lookup"><span data-stu-id="1178a-294">Both of these next statements evaluate to `True`.</span></span>

```powershell
$data = @('red','green','blue')
if ( $data -eq 'green' )
{
    'Green was found'
}
if ( $data -ne 'green' )
{
    'And green was not found'
}
```

<span data-ttu-id="1178a-295">Revisitarei isso daqui a pouco quando falarmos sobre testes para `$null`.</span><span class="sxs-lookup"><span data-stu-id="1178a-295">I'll revisit this in a moment when we talk about testing for `$null`.</span></span>

### <a name="-match"></a><span data-ttu-id="1178a-296">-match</span><span class="sxs-lookup"><span data-stu-id="1178a-296">-match</span></span>

<span data-ttu-id="1178a-297">O operador `-match` tenta corresponder a cada item na coleção.</span><span class="sxs-lookup"><span data-stu-id="1178a-297">The `-match` operator tries to match each item in the collection.</span></span>

```powershell
PS> $servers = @(
    'LAX-SQL-01'
    'LAX-API-01'
    'ATX-SQL-01'
    'ATX-API-01'
)
PS> $servers -match 'SQL'
LAX-SQL-01
ATX-SQL-01
```

<span data-ttu-id="1178a-298">Quando você usa `-match` com um só valor, uma variável especial `$Matches` é populada com informações de correspondência.</span><span class="sxs-lookup"><span data-stu-id="1178a-298">When you use `-match` with a single value, a special variable `$Matches` gets populated with match info.</span></span> <span data-ttu-id="1178a-299">Esse não é o caso quando uma matriz é processada dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="1178a-299">This isn't the case when an array is processed this way.</span></span>

<span data-ttu-id="1178a-300">Podemos usar a mesma abordagem com `Select-String`.</span><span class="sxs-lookup"><span data-stu-id="1178a-300">We can take the same approach with `Select-String`.</span></span>

```powershell
$servers | Select-String SQL
```

<span data-ttu-id="1178a-301">Considero mais atentamente `Select-String`,`-match` e a variável `$matches` em outra postagem chamada [As várias maneiras de usar regex][] (As várias maneiras de usar regex).</span><span class="sxs-lookup"><span data-stu-id="1178a-301">I take a closer look at `Select-String`,`-match` and the `$matches` variable in another post called [The many ways to use regex][].</span></span>

### <a name="null-or-empty"></a><span data-ttu-id="1178a-302">$null ou vazio</span><span class="sxs-lookup"><span data-stu-id="1178a-302">$null or empty</span></span>

<span data-ttu-id="1178a-303">O teste para `$null` ou matrizes vazias pode ser complicado.</span><span class="sxs-lookup"><span data-stu-id="1178a-303">Testing for `$null` or empty arrays can be tricky.</span></span> <span data-ttu-id="1178a-304">Aqui estão as armadilhas comuns com matrizes.</span><span class="sxs-lookup"><span data-stu-id="1178a-304">Here are the common traps with arrays.</span></span>

<span data-ttu-id="1178a-305">À primeira vista, essa instrução parece funcionar.</span><span class="sxs-lookup"><span data-stu-id="1178a-305">At a glance, this statement looks like it should work.</span></span>

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

<span data-ttu-id="1178a-306">Mas acabei de saber como `-eq` verifica cada item na matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-306">But I just went over how `-eq` checks each item in the array.</span></span> <span data-ttu-id="1178a-307">Então, podemos ter uma matriz de vários itens com um só valor $null e ele será avaliado como `$true`</span><span class="sxs-lookup"><span data-stu-id="1178a-307">So we can have an array of several items with a single $null value and it would evaluate to `$true`</span></span>

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

<span data-ttu-id="1178a-308">Por esse motivo, a melhor prática é posicionar `$null` no lado esquerdo do operador.</span><span class="sxs-lookup"><span data-stu-id="1178a-308">This is why it's a best practice to place the `$null` on the left side of the operator.</span></span> <span data-ttu-id="1178a-309">Isso faz com que esse cenário não seja um problema.</span><span class="sxs-lookup"><span data-stu-id="1178a-309">This makes this scenario a non-issue.</span></span>

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

<span data-ttu-id="1178a-310">Uma matriz `$null` não é o mesmo que uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="1178a-310">A `$null` array isn't the same thing as an empty array.</span></span> <span data-ttu-id="1178a-311">Se você souber que tem uma matriz, verifique a contagem de objetos nela.</span><span class="sxs-lookup"><span data-stu-id="1178a-311">If you know you have an array, check the count of objects in it.</span></span> <span data-ttu-id="1178a-312">Se a matriz for `$null`, a contagem será `0`.</span><span class="sxs-lookup"><span data-stu-id="1178a-312">If the array is `$null`, the count is `0`.</span></span>

```powershell
if ( $array.count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="1178a-313">Há mais uma armadilha a ser observada aqui.</span><span class="sxs-lookup"><span data-stu-id="1178a-313">There is one more trap to watch out for here.</span></span> <span data-ttu-id="1178a-314">Você pode usar o `count` mesmo que tenha um só objeto, a menos que esse objeto seja um `PSCustomObject`.</span><span class="sxs-lookup"><span data-stu-id="1178a-314">You can use the `count` even if you have a single object, unless that object is a `PSCustomObject`.</span></span> <span data-ttu-id="1178a-315">Esse é um bug que foi corrigido no PowerShell 6.1.</span><span class="sxs-lookup"><span data-stu-id="1178a-315">This is a bug that is fixed in PowerShell 6.1.</span></span>
<span data-ttu-id="1178a-316">Essa é uma boa notícia, mas muitas pessoas ainda usam a versão 5.1 e precisam prestar atenção nisso.</span><span class="sxs-lookup"><span data-stu-id="1178a-316">That's good news, but a lot of people are still on 5.1 and need to watch out for it.</span></span>

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

<span data-ttu-id="1178a-317">Se ainda estiver no PowerShell 5.1, você poderá encapsular o objeto em uma matriz antes de verificar a contagem para obter uma contagem precisa.</span><span class="sxs-lookup"><span data-stu-id="1178a-317">If you're still on PowerShell 5.1, you can wrap the object in an array before checking the count to get an accurate count.</span></span>

```powershell
if ( @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="1178a-318">Para reproduzi-lo de maneira completa, verifique `$null` e, em seguida, verifique a contagem.</span><span class="sxs-lookup"><span data-stu-id="1178a-318">To fully play it safe, check for `$null`, then check the count.</span></span>

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

### <a name="all--eq"></a><span data-ttu-id="1178a-319">Tudo -eq</span><span class="sxs-lookup"><span data-stu-id="1178a-319">All -eq</span></span>

<span data-ttu-id="1178a-320">Vi recentemente alguém perguntar [como verificar se cada valor em uma matriz corresponde a um determinado valor][].</span><span class="sxs-lookup"><span data-stu-id="1178a-320">I recently saw someone ask [how to verify that every value in an array matches a given value][].</span></span>
<span data-ttu-id="1178a-321">O usuário do Reddit **/u/bis** tinha essa [solução inteligente][] que verifica se há valores incorretos e inverte o resultado.</span><span class="sxs-lookup"><span data-stu-id="1178a-321">Reddit user **/u/bis** had this clever [solution][] that checks for any incorrect values and then flips the result.</span></span>

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a><span data-ttu-id="1178a-322">Adicionando a matrizes</span><span class="sxs-lookup"><span data-stu-id="1178a-322">Adding to arrays</span></span>

<span data-ttu-id="1178a-323">Neste ponto, você está começando a imaginar como adicionar itens a uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-323">At this point, you're starting to wonder how to add items to an array.</span></span> <span data-ttu-id="1178a-324">A resposta rápida é que você não pode.</span><span class="sxs-lookup"><span data-stu-id="1178a-324">The quick answer is that you can't.</span></span> <span data-ttu-id="1178a-325">Uma matriz é um tamanho fixo na memória.</span><span class="sxs-lookup"><span data-stu-id="1178a-325">An array is a fixed size in memory.</span></span> <span data-ttu-id="1178a-326">Se você precisar aumentá-la ou adicionar um item a ela, precisará criar uma matriz e copiar todos os valores da matriz antiga.</span><span class="sxs-lookup"><span data-stu-id="1178a-326">If you need to grow it or add a single item to it, then you need to create a new array and copy all the values over from the old array.</span></span> <span data-ttu-id="1178a-327">Isso soa caro e trabalhoso. No entanto, o PowerShell oculta a complexidade da criação da matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-327">This sounds expensive and like a lot of work, however, PowerShell hides the complexity of creating the new array.</span></span>

### <a name="array-addition"></a><span data-ttu-id="1178a-328">Adição de matriz</span><span class="sxs-lookup"><span data-stu-id="1178a-328">Array addition</span></span>

<span data-ttu-id="1178a-329">Podemos usar o operador de adição com matrizes para criar uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-329">We can use the addition operator with arrays to create a new array.</span></span> <span data-ttu-id="1178a-330">Portanto, dadas estas duas matrizes:</span><span class="sxs-lookup"><span data-stu-id="1178a-330">So given these two arrays:</span></span>

```powershell
$first = @(
    'Zero'
    'One'
)
$second = @(
    'Two'
    'Three'
)
```

<span data-ttu-id="1178a-331">Podemos adicioná-las juntas para obter uma nova matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-331">We can add them together to get a new array.</span></span>

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a><span data-ttu-id="1178a-332">Mais igual +=</span><span class="sxs-lookup"><span data-stu-id="1178a-332">Plus equals +=</span></span>

<span data-ttu-id="1178a-333">Podemos criar uma matriz no local e adicionar um item a ela da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1178a-333">We can create a new array in place and add an item to it like this:</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

<span data-ttu-id="1178a-334">Lembre-se de que sempre que usar `+=` você estará duplicando e criando uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-334">Just remember that every time you use `+=` that you're duplicating and creating a new array.</span></span> <span data-ttu-id="1178a-335">Isso não é um problema para pequenos conjuntos de dados, mas escala de maneira muito ruim.</span><span class="sxs-lookup"><span data-stu-id="1178a-335">This is a not an issue for small datasets but it scales extremely poorly.</span></span>

### <a name="pipeline-assignment"></a><span data-ttu-id="1178a-336">Atribuição de pipeline</span><span class="sxs-lookup"><span data-stu-id="1178a-336">Pipeline assignment</span></span>

<span data-ttu-id="1178a-337">Você pode atribuir os resultados de qualquer pipeline em uma variável.</span><span class="sxs-lookup"><span data-stu-id="1178a-337">You can assign the results of any pipeline into a variable.</span></span> <span data-ttu-id="1178a-338">Será uma matriz se contiver vários itens.</span><span class="sxs-lookup"><span data-stu-id="1178a-338">It's an array if it contains multiple items.</span></span>

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

<span data-ttu-id="1178a-339">Normalmente, quando pensamos em usar o pipeline, consideramos os one-liners típicos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1178a-339">Normally when we think of using the pipeline, we think of the typical PowerShell one-liners.</span></span> <span data-ttu-id="1178a-340">Podemos aproveitar o pipeline com instruções `foreach()` e outros loops.</span><span class="sxs-lookup"><span data-stu-id="1178a-340">We can leverage the pipeline with `foreach()` statements and other loops.</span></span> <span data-ttu-id="1178a-341">Então, em vez de adicionar itens a uma matriz em um loop, podemos soltar itens no pipeline.</span><span class="sxs-lookup"><span data-stu-id="1178a-341">So instead of adding items to an array in a loop, we can drop items onto the pipeline.</span></span>

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

<span data-ttu-id="1178a-342">Ao atribuir os resultados da `foreach` a uma variável, capturamos todos os objetos e criamos uma só matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-342">By assigning the results of the `foreach` to a variable, we capture all the objects and create a single array.</span></span>

## <a name="array-types"></a><span data-ttu-id="1178a-343">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="1178a-343">Array Types</span></span>

<span data-ttu-id="1178a-344">Por padrão, uma matriz no PowerShell é criada como um tipo `[PSObject[]]`.</span><span class="sxs-lookup"><span data-stu-id="1178a-344">By default, an array in PowerShell is created as a `[PSObject[]]` type.</span></span> <span data-ttu-id="1178a-345">Isso permite que ela contenha qualquer tipo de objeto ou valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-345">This allows it to contain any type of object or value.</span></span> <span data-ttu-id="1178a-346">Isso funciona porque tudo é herdado do tipo `PSObject`.</span><span class="sxs-lookup"><span data-stu-id="1178a-346">This works because everything is inherited from the `PSObject` type.</span></span>

### <a name="strongly-typed-arrays"></a><span data-ttu-id="1178a-347">Matrizes fortemente tipadas</span><span class="sxs-lookup"><span data-stu-id="1178a-347">Strongly typed arrays</span></span>

<span data-ttu-id="1178a-348">Você pode criar uma matriz de qualquer tipo usando uma sintaxe semelhante.</span><span class="sxs-lookup"><span data-stu-id="1178a-348">You can create an array of any type using a similar syntax.</span></span> <span data-ttu-id="1178a-349">Quando você cria uma matriz fortemente tipada, ela só pode conter valores ou objetos do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1178a-349">When you create a strongly typed array, it can only contain values or objects the specified type.</span></span>

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a><span data-ttu-id="1178a-350">ArrayList</span><span class="sxs-lookup"><span data-stu-id="1178a-350">ArrayList</span></span>

<span data-ttu-id="1178a-351">Adicionar itens a uma matriz é uma das suas maiores limitações, mas há algumas outras coleções às quais podemos recorrer para resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="1178a-351">Adding items to an array is one of its biggest limitations, but there are a few other collections that we can turn to that solve this problem.</span></span>

<span data-ttu-id="1178a-352">A `ArrayList` é normalmente uma das primeiras coisas em que pensamos quando precisamos de uma matriz mais rápida para trabalhar.</span><span class="sxs-lookup"><span data-stu-id="1178a-352">The `ArrayList` is commonly one of the first things that we think of when we need an array that is faster to work with.</span></span> <span data-ttu-id="1178a-353">Ela atua como uma matriz de objetos em todos os lugares necessários, mas lida com a adição de itens rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1178a-353">It acts like an object array every place that we need it, but it handles adding items quickly.</span></span>

<span data-ttu-id="1178a-354">Veja como criamos uma `ArrayList` e adicionamos itens a ela.</span><span class="sxs-lookup"><span data-stu-id="1178a-354">Here is how we create an `ArrayList` and add items to it.</span></span>

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

<span data-ttu-id="1178a-355">Estamos chamando o .NET para obter este tipo.</span><span class="sxs-lookup"><span data-stu-id="1178a-355">We are calling into .NET to get this type.</span></span> <span data-ttu-id="1178a-356">Nesse caso, estamos usando o construtor padrão para criá-la.</span><span class="sxs-lookup"><span data-stu-id="1178a-356">In this case, we are using the default constructor to create it.</span></span> <span data-ttu-id="1178a-357">Em seguida, chamamos o método `Add` para adicionar um item a ela.</span><span class="sxs-lookup"><span data-stu-id="1178a-357">Then we call the `Add` method to add an item to it.</span></span>

<span data-ttu-id="1178a-358">O motivo pelo qual estou usando `[void]` no início da linha é suprimir o código de retorno.</span><span class="sxs-lookup"><span data-stu-id="1178a-358">The reason I'm using `[void]` at the beginning of the line is to suppress the return code.</span></span> <span data-ttu-id="1178a-359">Algumas chamadas .NET fazem isso e podem criar uma saída inesperada.</span><span class="sxs-lookup"><span data-stu-id="1178a-359">Some .NET calls do this and can create unexpected output.</span></span>

<span data-ttu-id="1178a-360">Se os únicos dados que você tem em sua matriz forem cadeias de caracteres, veja também como usar [StringBuilder][].</span><span class="sxs-lookup"><span data-stu-id="1178a-360">If the only data that you have in your array is strings, then also take a look at using [StringBuilder][].</span></span> <span data-ttu-id="1178a-361">É quase a mesma coisa, mas tem alguns métodos que são apenas para lidar com cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1178a-361">It's almost the same thing but has some methods that are just for dealing with strings.</span></span> <span data-ttu-id="1178a-362">A `StringBuilder` é especialmente projetada para o desempenho.</span><span class="sxs-lookup"><span data-stu-id="1178a-362">The `StringBuilder` is specially designed for performance.</span></span>

<span data-ttu-id="1178a-363">É comum ver as pessoas migrarem para `ArrayList` de matrizes.</span><span class="sxs-lookup"><span data-stu-id="1178a-363">It's common to see people move to `ArrayList` from arrays.</span></span> <span data-ttu-id="1178a-364">Mas ela vem de um momento em que C# não tinha suporte genérico.</span><span class="sxs-lookup"><span data-stu-id="1178a-364">But it comes from a time where C# didn't have generic support.</span></span> <span data-ttu-id="1178a-365">A `ArrayList` é depreciada em suporte para a `List[]` genérica</span><span class="sxs-lookup"><span data-stu-id="1178a-365">The `ArrayList` is depreciated in support for the generic `List[]`</span></span>

### <a name="generic-list"></a><span data-ttu-id="1178a-366">Lista genérica</span><span class="sxs-lookup"><span data-stu-id="1178a-366">Generic List</span></span>

<span data-ttu-id="1178a-367">Um tipo genérico é um tipo especial no C# que define uma classe generalizada e o usuário especifica os tipos de dados que ele usa quando criado.</span><span class="sxs-lookup"><span data-stu-id="1178a-367">A generic type is a special type in C# that defines a generalized class and the user specifies the data types it uses when created.</span></span> <span data-ttu-id="1178a-368">Portanto, se você quiser uma lista de números ou cadeias de caracteres, definirá que deseja uma lista de tipos `int` ou `string`.</span><span class="sxs-lookup"><span data-stu-id="1178a-368">So if you want a list of numbers or strings, you would define that you want list of `int` or `string` types.</span></span>

<span data-ttu-id="1178a-369">Veja como criar uma lista para cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1178a-369">Here is how you create a List for strings.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

<span data-ttu-id="1178a-370">Ou uma lista de números.</span><span class="sxs-lookup"><span data-stu-id="1178a-370">Or a list for numbers.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

<span data-ttu-id="1178a-371">Podemos converter uma matriz existente em uma lista como esta, sem criar o objeto primeiro:</span><span class="sxs-lookup"><span data-stu-id="1178a-371">We can cast an existing array to a list like this without creating the object first:</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

<span data-ttu-id="1178a-372">Podemos reduzir a sintaxe com a instrução `using namespace` no PowerShell 5 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="1178a-372">We can shorten the syntax with the `using namespace` statement in PowerShell 5 and newer.</span></span> <span data-ttu-id="1178a-373">A instrução `using` precisa ser a primeira linha do seu script.</span><span class="sxs-lookup"><span data-stu-id="1178a-373">The `using` statement needs to be the first line of your script.</span></span> <span data-ttu-id="1178a-374">Ao declarar um namespace, o PowerShell permite deixá-lo fora dos tipos de dados ao referenciá-los.</span><span class="sxs-lookup"><span data-stu-id="1178a-374">By declaring a namespace, PowerShell lets you leave it off of the data types when you reference them.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

<span data-ttu-id="1178a-375">Isso torna o `List` muito mais utilizável.</span><span class="sxs-lookup"><span data-stu-id="1178a-375">This makes the `List` much more usable.</span></span>

<span data-ttu-id="1178a-376">Você tem um método `Add` semelhante disponível para você.</span><span class="sxs-lookup"><span data-stu-id="1178a-376">You have a similar `Add` method available to you.</span></span> <span data-ttu-id="1178a-377">Diferentemente de ArrayList, não há nenhum valor retornado no método `Add`. Portanto, não precisamos usar `void` para anulá-lo.</span><span class="sxs-lookup"><span data-stu-id="1178a-377">Unlike the ArrayList, there is no return value on the `Add` method so we don't have to `void` it.</span></span>

```powershell
$myList.Add(10)
```

<span data-ttu-id="1178a-378">E ainda podemos acessar os elementos como outras matrizes.</span><span class="sxs-lookup"><span data-stu-id="1178a-378">And we can still access the elements like other arrays.</span></span>

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a><span data-ttu-id="1178a-379">List[PSObject]</span><span class="sxs-lookup"><span data-stu-id="1178a-379">List[PSObject]</span></span>

<span data-ttu-id="1178a-380">Você pode ter uma lista de qualquer tipo, mas quando não conhece o tipo de objetos, pode usar `[List[PSObject]]` para contê-los.</span><span class="sxs-lookup"><span data-stu-id="1178a-380">You can have a list of any type, but when you don’t know the type of objects, you can use `[List[PSObject]]` to contain them.</span></span>

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a><span data-ttu-id="1178a-381">Remove()</span><span class="sxs-lookup"><span data-stu-id="1178a-381">Remove()</span></span>

<span data-ttu-id="1178a-382">O `ArrayList` e o `List[]` genérico dão suporte à remoção de itens da coleção.</span><span class="sxs-lookup"><span data-stu-id="1178a-382">The `ArrayList` and the generic `List[]` both support removing items from the collection.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

<span data-ttu-id="1178a-383">Ao trabalhar com tipos de valor, ele remove o primeiro da lista.</span><span class="sxs-lookup"><span data-stu-id="1178a-383">When working with value types, it removes the first one from the list.</span></span> <span data-ttu-id="1178a-384">Você pode chamá-lo repetidamente para continuar a remover esse valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-384">You can call it over and over again to keep removing that value.</span></span> <span data-ttu-id="1178a-385">Se você tiver tipos de referência, será necessário fornecer o objeto que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="1178a-385">If you have reference types, you have to provide the object that you want removed.</span></span>

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

<span data-ttu-id="1178a-386">O método remove retorna `true` se foi possível localizar e remover o item da coleção.</span><span class="sxs-lookup"><span data-stu-id="1178a-386">The remove method returns `true` if it was able to find and remove the item from the collection.</span></span>

### <a name="more-collections"></a><span data-ttu-id="1178a-387">Mais coleções</span><span class="sxs-lookup"><span data-stu-id="1178a-387">More collections</span></span>

<span data-ttu-id="1178a-388">Há muitas outras coleções que podem ser usadas, mas essas são as boas substituições de matriz genéricas.</span><span class="sxs-lookup"><span data-stu-id="1178a-388">There are many other collections that can be used but these are the good generic array replacements.</span></span>
<span data-ttu-id="1178a-389">Se você tiver interesse em saber mais sobre essas opções, dê uma olhada neste [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) que [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) reuniu.</span><span class="sxs-lookup"><span data-stu-id="1178a-389">If you're interested in learning about more of these options, take a look at this [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) that [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) put together.</span></span>

## <a name="other-nuances"></a><span data-ttu-id="1178a-390">Outras nuances</span><span class="sxs-lookup"><span data-stu-id="1178a-390">Other nuances</span></span>

<span data-ttu-id="1178a-391">Agora que já abordei todas as principais funcionalidades, aqui estão alguns aspectos que eu queria mencionar antes de encerrar.</span><span class="sxs-lookup"><span data-stu-id="1178a-391">Now that I have covered all the major functionality, here are a few more things that I wanted to mention before I wrap this up.</span></span>

### <a name="pre-sized-arrays"></a><span data-ttu-id="1178a-392">Matrizes pré-dimensionadas</span><span class="sxs-lookup"><span data-stu-id="1178a-392">Pre-sized arrays</span></span>

<span data-ttu-id="1178a-393">Mencionei que não é possível alterar o tamanho de uma matriz depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="1178a-393">I mentioned that you can't change the size of an array once it's created.</span></span> <span data-ttu-id="1178a-394">Podemos criar uma matriz de um tamanho predeterminado chamando-a com o construtor `new($size)`.</span><span class="sxs-lookup"><span data-stu-id="1178a-394">We can create an array of a pre-determined size by calling it with the `new($size)` constructor.</span></span>

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a><span data-ttu-id="1178a-395">Multiplicando matrizes</span><span class="sxs-lookup"><span data-stu-id="1178a-395">Multiplying arrays</span></span>

<span data-ttu-id="1178a-396">Um pequeno truque interessante é que você pode multiplicar uma matriz por um inteiro.</span><span class="sxs-lookup"><span data-stu-id="1178a-396">An interesting little trick is that you can multiply an array by an integer.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data * 3
red
green
blue
red
green
blue
red
green
blue
```

### <a name="initialize-with-0"></a><span data-ttu-id="1178a-397">Inicializar com 0</span><span class="sxs-lookup"><span data-stu-id="1178a-397">Initialize with 0</span></span>

<span data-ttu-id="1178a-398">Um cenário comum é que você deseja criar uma matriz com todos os zeros.</span><span class="sxs-lookup"><span data-stu-id="1178a-398">A common scenario is that you want to create an array with all zeros.</span></span> <span data-ttu-id="1178a-399">Se você for ter apenas inteiros, uma matriz fortemente tipada de inteiros assume como padrão todos os zeros.</span><span class="sxs-lookup"><span data-stu-id="1178a-399">If you're only going to have integers, a strongly typed array of integers defaults to all zeros.</span></span>

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

<span data-ttu-id="1178a-400">Podemos usar o truque de multiplicação para fazer isso também.</span><span class="sxs-lookup"><span data-stu-id="1178a-400">We can use the multiplying trick to do this too.</span></span>

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

<span data-ttu-id="1178a-401">O interessante sobre o truque de multiplicação é que você pode usar qualquer valor.</span><span class="sxs-lookup"><span data-stu-id="1178a-401">The nice thing about the multiplying trick is that you can use any value.</span></span> <span data-ttu-id="1178a-402">Portanto, se você preferir ter `255` como valor padrão, essa seria uma boa maneira de fazer isso.</span><span class="sxs-lookup"><span data-stu-id="1178a-402">So if you would rather have `255` as your default value, this would be a good way to do it.</span></span>

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a><span data-ttu-id="1178a-403">Matrizes aninhadas</span><span class="sxs-lookup"><span data-stu-id="1178a-403">Nested arrays</span></span>

<span data-ttu-id="1178a-404">Uma matriz dentro de uma matriz é chamada de matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="1178a-404">An array inside an array is called a nested array.</span></span> <span data-ttu-id="1178a-405">Não uso muito no PowerShell, mas as usei mais em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="1178a-405">I don't use these much in PowerShell but I have used them more in other languages.</span></span> <span data-ttu-id="1178a-406">Considere o uso de uma matriz de matrizes quando seus dados couberem em um padrão tipo grade.</span><span class="sxs-lookup"><span data-stu-id="1178a-406">Consider using an array of arrays when your data fits in a grid like pattern.</span></span>

<span data-ttu-id="1178a-407">Aqui estão duas maneiras de criar uma matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="1178a-407">Here are two ways we can create a two-dimensional array.</span></span>

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

<span data-ttu-id="1178a-408">A vírgula é muito importante nesses exemplos.</span><span class="sxs-lookup"><span data-stu-id="1178a-408">The comma is very important in those examples.</span></span> <span data-ttu-id="1178a-409">Forneci um exemplo anterior de uma matriz normal em várias linhas em que a vírgula era opcional.</span><span class="sxs-lookup"><span data-stu-id="1178a-409">I gave an earlier example of a normal array on multiple lines where the comma was optional.</span></span> <span data-ttu-id="1178a-410">Esse não é o caso com uma matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="1178a-410">That isn't the case with a multi-dimensional array.</span></span>

<span data-ttu-id="1178a-411">A maneira como usamos a notação de índice muda um pouco agora que temos uma matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="1178a-411">The way we use the index notation changes slightly now that we've a nested array.</span></span> <span data-ttu-id="1178a-412">Acessaremos o valor 3 usando o `$data` acima.</span><span class="sxs-lookup"><span data-stu-id="1178a-412">Using the `$data` above, this is how we would access the value 3.</span></span>

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

<span data-ttu-id="1178a-413">Adicione um conjunto de colchetes para cada nível de aninhamento de matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-413">Add a set of bracket for each level of array nesting.</span></span> <span data-ttu-id="1178a-414">O primeiro conjunto de colchetes é para a matriz mais externa e, em seguida, você trabalha de lá.</span><span class="sxs-lookup"><span data-stu-id="1178a-414">The first set of brackets is for the outer most array and then you work your way in from there.</span></span>

### <a name="write-output--noenumerate"></a><span data-ttu-id="1178a-415">Write-Output -NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="1178a-415">Write-Output -NoEnumerate</span></span>

<span data-ttu-id="1178a-416">O PowerShell gosta de desencapsular ou enumerar matrizes.</span><span class="sxs-lookup"><span data-stu-id="1178a-416">PowerShell likes to unwrap or enumerate arrays.</span></span> <span data-ttu-id="1178a-417">Esse é um aspecto fundamental do modo como o PowerShell usa o pipeline, mas há ocasiões em que você não quer que isso aconteça.</span><span class="sxs-lookup"><span data-stu-id="1178a-417">This is a core aspect of the way PowerShell uses the pipeline but there are times that you don't want that to happen.</span></span>

<span data-ttu-id="1178a-418">Eu normalmente redireciono objetos para `Get-Member` a fim de saber mais sobre eles.</span><span class="sxs-lookup"><span data-stu-id="1178a-418">I commonly pipe objects to `Get-Member` to learn more about them.</span></span> <span data-ttu-id="1178a-419">Quando redireciono uma matriz para ele, ela é desencapsulada e Get-Member vê os membros da matriz e não a matriz real.</span><span class="sxs-lookup"><span data-stu-id="1178a-419">When I pipe an array to it, it gets unwrapped and Get-Member sees the members of the array and not the actual array.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

<span data-ttu-id="1178a-420">Para evitar o desencapsulamento da matriz, você pode usar `Write-Object -NoEnumerate`.</span><span class="sxs-lookup"><span data-stu-id="1178a-420">To prevent that unwrap of the array, you can use `Write-Object -NoEnumerate`.</span></span>

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

<span data-ttu-id="1178a-421">Tenho uma segunda forma que parece mais um ataque (e tento evitar ataques como esse).</span><span class="sxs-lookup"><span data-stu-id="1178a-421">I have a second way that's more of a hack (and I try to avoid hacks like this).</span></span> <span data-ttu-id="1178a-422">Você pode inserir uma vírgula na frente da matriz antes de direcioná-la.</span><span class="sxs-lookup"><span data-stu-id="1178a-422">You can place a comma in front of the array before you pipe it.</span></span>

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a><span data-ttu-id="1178a-423">Retornar uma matriz</span><span class="sxs-lookup"><span data-stu-id="1178a-423">Return an array</span></span>

<span data-ttu-id="1178a-424">Esse desencapsulamento de matrizes também acontece quando você gera ou retorna valores de uma função.</span><span class="sxs-lookup"><span data-stu-id="1178a-424">This unwrapping of arrays also happens when you output or return values from a function.</span></span> <span data-ttu-id="1178a-425">Você ainda poderá obter uma matriz se atribuir a saída a uma variável. Portanto, isso não é normalmente um problema.</span><span class="sxs-lookup"><span data-stu-id="1178a-425">You can still get an array if you assign the output to a variable so this isn't commonly an issue.</span></span>

<span data-ttu-id="1178a-426">O problema é que você tem uma nova matriz.</span><span class="sxs-lookup"><span data-stu-id="1178a-426">The catch is that you have a new array.</span></span> <span data-ttu-id="1178a-427">Se isso nunca for um problema, você poderá usar `Write-Output -NoEnumerate $array` ou `return ,$array` para contornar isso.</span><span class="sxs-lookup"><span data-stu-id="1178a-427">If that is ever a problem, you can use `Write-Output -NoEnumerate $array` or `return ,$array` to work around it.</span></span>

## <a name="anything-else"></a><span data-ttu-id="1178a-428">Algo mais?</span><span class="sxs-lookup"><span data-stu-id="1178a-428">Anything else?</span></span>

<span data-ttu-id="1178a-429">Sei que é muita informação a ser assimilada.</span><span class="sxs-lookup"><span data-stu-id="1178a-429">I know this is all a lot to take in.</span></span> <span data-ttu-id="1178a-430">Espero que você aprenda algo com este artigo toda vez que lê-lo e que ele se torne uma boa referência por um bom tempo.</span><span class="sxs-lookup"><span data-stu-id="1178a-430">My hope is that you learn something from this article every time you read it and that it turns out to be a good reference for you for a long time to come.</span></span> <span data-ttu-id="1178a-431">Se você achou que este conteúdo é útil, compartilhe-o com outras pessoas para que elas possam aproveitá-lo.</span><span class="sxs-lookup"><span data-stu-id="1178a-431">If you found this to be helpful, please share it with others you think may get value out of it.</span></span>

<span data-ttu-id="1178a-432">Daqui em diante, recomendo que você confira uma postagem semelhante que escrevi sobre [tabelas de hash][].</span><span class="sxs-lookup"><span data-stu-id="1178a-432">From here, I would recommend you check out a similar post that I wrote about [hashtables][].</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Matrizes]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[instrução switch]: everything-about-switch.md
[switch statement]: everything-about-switch.md
[tabelas de hash]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
[As várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[como verificar se cada valor em uma matriz corresponde a um determinado valor]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[how to verify that every value in an array matches a given value]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[solução inteligente]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[solution]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
