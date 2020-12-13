---
title: Tudo o que você queria saber sobre a instrução if
description: Como muitas outras linguagens, o PowerShell tem instruções para executar código condicionalmente em seus scripts.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: b6bafb99bfb8ecd0152bae841e5c58d4c27ccd3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "86469745"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a><span data-ttu-id="0f6ce-103">Tudo o que você queria saber sobre a instrução `if`</span><span class="sxs-lookup"><span data-stu-id="0f6ce-103">Everything you wanted to know about the `if` statement</span></span>

<span data-ttu-id="0f6ce-104">Como muitas outras linguagens, o PowerShell tem instruções para executar código condicionalmente em seus scripts.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-104">Like many other languages, PowerShell has statements for conditionally executing code in your scripts.</span></span> <span data-ttu-id="0f6ce-105">Uma dessas instruções é a instrução [If][].</span><span class="sxs-lookup"><span data-stu-id="0f6ce-105">One of those statements is the [If][] statement.</span></span> <span data-ttu-id="0f6ce-106">Hoje, vamos nos aprofundar em um dos comandos mais fundamentais no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-106">Today we will take a deep dive into one of the most fundamental commands in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="0f6ce-107">A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="0f6ce-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="0f6ce-108">A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="0f6ce-109">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="0f6ce-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="conditional-execution"></a><span data-ttu-id="0f6ce-110">Execução condicional</span><span class="sxs-lookup"><span data-stu-id="0f6ce-110">Conditional execution</span></span>

<span data-ttu-id="0f6ce-111">Os scripts geralmente precisam tomar decisões e executar diferentes lógicas com base nessas decisões.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-111">Your scripts often need to make decisions and perform different logic based on those decisions.</span></span>
<span data-ttu-id="0f6ce-112">Isso é o que quero dizer pela execução condicional.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-112">This is what I mean by conditional execution.</span></span> <span data-ttu-id="0f6ce-113">Você tem uma instrução ou valor a ser avaliado e executa uma seção diferente do código com base nessa avaliação.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-113">You have one statement or value to evaluate, then execute a different section of code based on that evaluation.</span></span> <span data-ttu-id="0f6ce-114">Isso é exatamente o que a instrução `if` faz.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-114">This is exactly what the `if` statement does.</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="0f6ce-115">A instrução `if`</span><span class="sxs-lookup"><span data-stu-id="0f6ce-115">The `if` statement</span></span>

<span data-ttu-id="0f6ce-116">Aqui está um exemplo básico da instrução `if`:</span><span class="sxs-lookup"><span data-stu-id="0f6ce-116">Here is a basic example of the `if` statement:</span></span>

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

<span data-ttu-id="0f6ce-117">A primeira coisa que a instrução `if` faz é avaliar a expressão entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-117">The first thing the `if` statement does is evaluate the expression in parentheses.</span></span> <span data-ttu-id="0f6ce-118">Se for avaliada como `$true`, executará o `scriptblock` nas chaves.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-118">If it evaluates to `$true`, then it executes the `scriptblock` in the braces.</span></span> <span data-ttu-id="0f6ce-119">Se o valor fosse `$false`, esse scriptblock seria ignorado.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-119">If the value was `$false`, then it would skip over that scriptblock.</span></span>

<span data-ttu-id="0f6ce-120">No exemplo anterior, a instrução `if` estava apenas avaliando a variável `$condition`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-120">In the previous example, the `if` statement was just evaluating the `$condition` variable.</span></span> <span data-ttu-id="0f6ce-121">Foi `$true` e teria executado o comando `Write-Output` dentro do scriptblock.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-121">It was `$true` and would have executed the `Write-Output` command inside the scriptblock.</span></span>

<span data-ttu-id="0f6ce-122">Em algumas linguagens, você pode posicionar uma única linha de código após a instrução `if` e esta é executada.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-122">In some languages, you can place a single line of code after the `if` statement and it gets executed.</span></span> <span data-ttu-id="0f6ce-123">Não é o caso no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-123">That isn't the case in PowerShell.</span></span> <span data-ttu-id="0f6ce-124">Você deverá fornecer um `scriptblock` completo com chaves para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-124">You must provide a full `scriptblock` with braces for it to work correctly.</span></span>

## <a name="comparison-operators"></a><span data-ttu-id="0f6ce-125">Operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="0f6ce-125">Comparison operators</span></span>

<span data-ttu-id="0f6ce-126">O uso mais comum da instrução `if` é comparar dois itens entre si.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-126">The most common use of the `if` statement for is comparing two items with each other.</span></span> <span data-ttu-id="0f6ce-127">O PowerShell tem operadores especiais para cenários de comparação diferentes.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-127">PowerShell has special operators for different comparison scenarios.</span></span> <span data-ttu-id="0f6ce-128">Quando você usa um operador de comparação, o valor no lado esquerdo é comparado ao valor no lado direito.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-128">When you use a comparison operator, the value on the left-hand side is compared to the value on the right-hand side.</span></span>

### <a name="-eq-for-equality"></a><span data-ttu-id="0f6ce-129">-eq para igualdade</span><span class="sxs-lookup"><span data-stu-id="0f6ce-129">-eq for equality</span></span>

<span data-ttu-id="0f6ce-130">O `-eq` faz uma verificação de igualdade entre dois valores para garantir que eles sejam iguais.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-130">The `-eq` does an equality check between two values to make sure they're equal to each other.</span></span>

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

<span data-ttu-id="0f6ce-131">Neste exemplo, estou assumindo um valor conhecido de `5` e comparando com meu `$value` para ver se correspondem.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-131">In this example, I'm taking a known value of `5` and comparing it to my `$value` to see if they match.</span></span>

<span data-ttu-id="0f6ce-132">Um possível caso de uso é verificar o status de um valor antes de executar uma ação.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-132">One possible use case is to check the status of a value before you take an action on it.</span></span> <span data-ttu-id="0f6ce-133">Você pode obter um serviço e verificar se o status estava definido como em execução antes de chamar `Restart-Service`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-133">You could get a service and check that the status was running before you called `Restart-Service` on it.</span></span>

<span data-ttu-id="0f6ce-134">É comum em outras linguagens, como C#, usar `==` para igualdade (por exemplo, `5 == $value`). Mas isso não funciona com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-134">It's common in other languages like C# to use `==` for equality (ex: `5 == $value`) but that doesn't work with PowerShell.</span></span> <span data-ttu-id="0f6ce-135">Outro erro comum é usar o sinal de igual (por exemplo, `5 = $value`) que é reservado para atribuir valores para variáveis.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-135">Another common mistake that people make is to use the equals sign (ex: `5 = $value`) that is reserved for assigning values to variables.</span></span> <span data-ttu-id="0f6ce-136">Colocar seu valor conhecido à esquerda torna o erro mais embaraçoso.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-136">By placing your known value on the left, it makes that mistake more awkward to make.</span></span>

<span data-ttu-id="0f6ce-137">Este operador (e outros) tem algumas variações.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-137">This operator (and others) has a few variations.</span></span>

- <span data-ttu-id="0f6ce-138">`-eq` igualdade que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-138">`-eq` case-insensitive equality</span></span>
- <span data-ttu-id="0f6ce-139">`-ieq` igualdade que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-139">`-ieq` case-insensitive equality</span></span>
- <span data-ttu-id="0f6ce-140">`-ceq` igualdade que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-140">`-ceq` case-sensitive equality</span></span>

### <a name="-ne-not-equal"></a><span data-ttu-id="0f6ce-141">-ne diferente de</span><span class="sxs-lookup"><span data-stu-id="0f6ce-141">-ne not equal</span></span>

<span data-ttu-id="0f6ce-142">Muitos operadores têm um operador relacionado que está verificando o resultado oposto.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-142">Many operators have a related operator that is checking for the opposite result.</span></span> <span data-ttu-id="0f6ce-143">`-ne` verifica se os valores não são iguais.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-143">`-ne` verifies that the values don't equal each other.</span></span>

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

<span data-ttu-id="0f6ce-144">Use para garantir que a ação seja executada somente se o valor não for `5`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-144">Use this to make sure that the action only executes if the value isn't `5`.</span></span> <span data-ttu-id="0f6ce-145">Um bom caso de uso seria verificar se um serviço está em estado de execução antes de tentar iniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-145">A good use-cases where would be to check if a service was in the running state before you try to start it.</span></span>

<span data-ttu-id="0f6ce-146">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-146">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-147">`-ne` não igual que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-147">`-ne` case-insensitive not equal</span></span>
- <span data-ttu-id="0f6ce-148">`-ine` não igual que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-148">`-ine` case-insensitive not equal</span></span>
- <span data-ttu-id="0f6ce-149">`-cne` não igual que diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-149">`-cne` case-sensitive not equal</span></span>

<span data-ttu-id="0f6ce-150">São variações inversas de `-eq`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-150">These are inverse variations of `-eq`.</span></span> <span data-ttu-id="0f6ce-151">Agruparei esses tipos quando listar as variações para outros operadores.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-151">I'll group these types together when I list variations for other operators.</span></span>

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a><span data-ttu-id="0f6ce-152">-gt -ge -lt -le para maior que ou menor que</span><span class="sxs-lookup"><span data-stu-id="0f6ce-152">-gt -ge -lt -le for greater than or less than</span></span>

<span data-ttu-id="0f6ce-153">Esses operadores são usados durante a verificação para ver se um valor é maior ou menor que outro valor.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-153">These operators are used when checking to see if a value is larger or smaller than another value.</span></span>
<span data-ttu-id="0f6ce-154">Os `-gt -ge -lt -le` são GreaterThan, GreaterThanOrEqual, LessThan e LessThanOrEqual.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-154">The `-gt -ge -lt -le` stand for GreaterThan, GreaterThanOrEqual, LessThan, and LessThanOrEqual.</span></span>

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

<span data-ttu-id="0f6ce-155">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-155">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-156">`-gt` maior que</span><span class="sxs-lookup"><span data-stu-id="0f6ce-156">`-gt` greater than</span></span>
- <span data-ttu-id="0f6ce-157">`-igt` maior que, não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-157">`-igt` greater than, case-insensitive</span></span>
- <span data-ttu-id="0f6ce-158">`-cgt` maior que, diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-158">`-cgt` greater than, case-sensitive</span></span>
- <span data-ttu-id="0f6ce-159">`-ge` maior que ou igual a</span><span class="sxs-lookup"><span data-stu-id="0f6ce-159">`-ge` greater than or equal</span></span>
- <span data-ttu-id="0f6ce-160">`-ige` maior que ou igual a, não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-160">`-ige` greater than or equal, case-insensitive</span></span>
- <span data-ttu-id="0f6ce-161">`-cge` maior que ou igual a, diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-161">`-cge` greater than or equal, case-sensitive</span></span>
- <span data-ttu-id="0f6ce-162">`-lt` menor que</span><span class="sxs-lookup"><span data-stu-id="0f6ce-162">`-lt` less than</span></span>
- <span data-ttu-id="0f6ce-163">`-ilt` menor que, não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-163">`-ilt` less than, case-insensitive</span></span>
- <span data-ttu-id="0f6ce-164">`-clt` menor que, diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-164">`-clt` less than, case-sensitive</span></span>
- <span data-ttu-id="0f6ce-165">`-le` menor que ou igual a</span><span class="sxs-lookup"><span data-stu-id="0f6ce-165">`-le` less than or equal</span></span>
- <span data-ttu-id="0f6ce-166">`-ile` menor que ou igual a, não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-166">`-ile` less than or equal, case-insensitive</span></span>
- <span data-ttu-id="0f6ce-167">`-cle` menor que ou igual a, diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-167">`-cle` less than or equal, case-sensitive</span></span>

<span data-ttu-id="0f6ce-168">Não sei por que você usaria opções que diferenciam e não diferenciam maiúsculas de minúsculas para esses operadores.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-168">I don't know why you would use case-sensitive and insensitive options for these operators.</span></span>

### <a name="-like-wildcard-matches"></a><span data-ttu-id="0f6ce-169">-like correspondências de caractere curinga</span><span class="sxs-lookup"><span data-stu-id="0f6ce-169">-like wildcard matches</span></span>

<span data-ttu-id="0f6ce-170">O PowerShell tem sua própria sintaxe de correspondência de padrões baseada em caractere curinga e você pode usá-la com o operador `-like`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-170">PowerShell has its own wildcard-based pattern matching syntax and you can use it with the `-like` operator.</span></span> <span data-ttu-id="0f6ce-171">Esses padrões de caractere curinga são bastante básicos.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-171">These wildcard patterns are fairly basic.</span></span>

- <span data-ttu-id="0f6ce-172">`?` corresponde a qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="0f6ce-172">`?` matches any single character</span></span>
- <span data-ttu-id="0f6ce-173">`*` corresponde a qualquer número de caracteres</span><span class="sxs-lookup"><span data-stu-id="0f6ce-173">`*` matches any number of characters</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

<span data-ttu-id="0f6ce-174">É importante ressaltar que o padrão corresponde à cadeia de caracteres inteira.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-174">It's important to point out that the pattern matches the whole string.</span></span> <span data-ttu-id="0f6ce-175">Se você precisar corresponder algo no meio da cadeia de caracteres, você precisará posicionar `*` em ambas as extremidades da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-175">If you need to match something in the middle of the string, you need to place the `*` on both ends of the string.</span></span>

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

<span data-ttu-id="0f6ce-176">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-176">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-177">`-like` caractere curinga que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-177">`-like` case-insensitive wildcard</span></span>
- <span data-ttu-id="0f6ce-178">`-ilike` caractere curinga que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-178">`-ilike` case-insensitive wildcard</span></span>
- <span data-ttu-id="0f6ce-179">`-clike` caractere curinga que diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-179">`-clike` case-sensitive wildcard</span></span>
- <span data-ttu-id="0f6ce-180">`-notlike` caractere curinga que não diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-180">`-notlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="0f6ce-181">`-inotlike` caractere curinga que não diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-181">`-inotlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="0f6ce-182">`-cnotlike` caractere curinga que diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-182">`-cnotlike` case-sensitive wildcard not matched</span></span>

### <a name="-match-regular-expression"></a><span data-ttu-id="0f6ce-183">-match expressão regular</span><span class="sxs-lookup"><span data-stu-id="0f6ce-183">-match regular expression</span></span>

<span data-ttu-id="0f6ce-184">O operador `-match` permite que você procure uma correspondência baseada em expressão regular numa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-184">The `-match` operator allows you to check a string for a regular-expression-based match.</span></span> <span data-ttu-id="0f6ce-185">Use quando os padrões de caractere curinga não são flexíveis o suficiente.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-185">Use this when the wildcard patterns aren't flexible enough for you.</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

<span data-ttu-id="0f6ce-186">Um padrão regex corresponde a qualquer local na cadeia de caracteres por padrão.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-186">A regex pattern matches anywhere in the string by default.</span></span> <span data-ttu-id="0f6ce-187">Portanto, você pode especificar uma substring de caracteres que você deseja corresponder, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0f6ce-187">So you can specify a substring that you want matched like this:</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

<span data-ttu-id="0f6ce-188">Regex é uma linguagem complexa e vale a pena analisar.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-188">Regex is a complex language of its own and worth looking into.</span></span> <span data-ttu-id="0f6ce-189">Falarei mais sobre `-match` e [, as várias maneiras de usar regex][] em outro artigo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-189">I talk more about `-match` and [the many ways to use regex][] in another article.</span></span>

<span data-ttu-id="0f6ce-190">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-190">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-191">`-match` regex que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-191">`-match` case-insensitive regex</span></span>
- <span data-ttu-id="0f6ce-192">`-imatch` regex que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-192">`-imatch` case-insensitive regex</span></span>
- <span data-ttu-id="0f6ce-193">`-cmatch` regex que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-193">`-cmatch` case-sensitive regex</span></span>
- <span data-ttu-id="0f6ce-194">`-notmatch` regex que não diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-194">`-notmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="0f6ce-195">`-inotmatch` regex que não diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-195">`-inotmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="0f6ce-196">`-cnotmatch` regex que diferencia maiúsculas e minúsculas não correspondente</span><span class="sxs-lookup"><span data-stu-id="0f6ce-196">`-cnotmatch` case-sensitive regex not matched</span></span>

### <a name="-is-of-type"></a><span data-ttu-id="0f6ce-197">-is é tipo</span><span class="sxs-lookup"><span data-stu-id="0f6ce-197">-is of type</span></span>

<span data-ttu-id="0f6ce-198">Você pode verificar o tipo de um valor com o operador `-is`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-198">You can check a value's type with the `-is` operator.</span></span>

```powershell
if ( $value -is [string] )
{
    # do something
}
```

<span data-ttu-id="0f6ce-199">Você pode usá-lo se estiver trabalhando com classes ou aceitando vários objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-199">You may use this if you're working with classes or accepting various objects over the pipeline.</span></span> <span data-ttu-id="0f6ce-200">É possível ter um serviço ou um nome de serviço como sua entrada.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-200">You could have either a service or a service name as your input.</span></span> <span data-ttu-id="0f6ce-201">Verifique se você tem um serviço e busque-o apenas com o nome.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-201">Then check to see if you have a service and fetch the service if you only have the name.</span></span>

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

<span data-ttu-id="0f6ce-202">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-202">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-203">`-is` do tipo</span><span class="sxs-lookup"><span data-stu-id="0f6ce-203">`-is` of type</span></span>
- <span data-ttu-id="0f6ce-204">`-isnot` não é do tipo</span><span class="sxs-lookup"><span data-stu-id="0f6ce-204">`-isnot` not of type</span></span>

## <a name="collection-operators"></a><span data-ttu-id="0f6ce-205">Operadores de coleção</span><span class="sxs-lookup"><span data-stu-id="0f6ce-205">Collection operators</span></span>

<span data-ttu-id="0f6ce-206">Quando você usa os operadores anteriores com um único valor, o resultado é `$true` ou `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-206">When you use the previous operators with a single value, the result is `$true` or `$false`.</span></span> <span data-ttu-id="0f6ce-207">Isso é tratado de forma levemente diferente ao trabalhar com uma coleção.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-207">This is handled slightly differently when working with a collection.</span></span> <span data-ttu-id="0f6ce-208">Cada item na coleção é avaliado e o operador retorna todos os valores avaliados como `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-208">Each item in the collection gets evaluated and the operator returns every value that evaluates to `$true`.</span></span>

```powershell
PS> 1,2,3,4 -eq 3
3
```

<span data-ttu-id="0f6ce-209">Isso ainda funciona corretamente em uma instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-209">This still works correctly in a `if` statement.</span></span> <span data-ttu-id="0f6ce-210">Portanto, um valor é retornado pelo operador e a instrução inteira é `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-210">So a value is returned by your operator, then the whole statement is `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

<span data-ttu-id="0f6ce-211">Há uma pequena armadilha ocultada nos detalhes que preciso destacar. Quando você usa o operador `-ne` dessa forma, é fácil analisar incorretamente a lógica de forma invertida.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-211">There's one small trap hiding in the details here that I need to point out. When using the `-ne` operator this way, it's easy to mistakenly look at the logic backwards.</span></span> <span data-ttu-id="0f6ce-212">Usar `-ne` com uma coleção retornará `$true` se qualquer item na coleção não corresponder ao seu valor.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-212">Using `-ne` with a collection returns `$true` if any item in the collection doesn't match your value.</span></span>

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

<span data-ttu-id="0f6ce-213">Pode parecer um truque inteligente, mas temos operadores `-contains` e `-in` que lidam com isso com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-213">This may look like a clever trick, but we have operators `-contains` and `-in` that handle this more efficiently.</span></span> <span data-ttu-id="0f6ce-214">E `-notcontains` faz o que você espera.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-214">And `-notcontains` does what you expect.</span></span>

### <a name="-contains"></a><span data-ttu-id="0f6ce-215">-contains</span><span class="sxs-lookup"><span data-stu-id="0f6ce-215">-contains</span></span>

<span data-ttu-id="0f6ce-216">O operador `-contains` procura seu valor na coleção.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-216">The `-contains` operator checks the collection for your value.</span></span> <span data-ttu-id="0f6ce-217">Assim que encontra uma correspondência, retorna `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-217">As soon as it finds a match, it returns `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

<span data-ttu-id="0f6ce-218">Essa é a melhor maneira de ver se uma coleção contém seu valor.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-218">This is the preferred way to see if a collection contains your value.</span></span> <span data-ttu-id="0f6ce-219">O uso de `Where-Object` (ou `-eq`) percorre a lista inteira toda vez e é significativamente mais lento.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-219">Using `Where-Object` (or `-eq`) walks the entire list every time and is significantly slower.</span></span>

<span data-ttu-id="0f6ce-220">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-220">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-221">`-contains` correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-221">`-contains` case-insensitive match</span></span>
- <span data-ttu-id="0f6ce-222">`-icontains` correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-222">`-icontains` case-insensitive match</span></span>
- <span data-ttu-id="0f6ce-223">`-ccontains` correspondência que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-223">`-ccontains` case-sensitive match</span></span>
- <span data-ttu-id="0f6ce-224">`-notcontains` não correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-224">`-notcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="0f6ce-225">`-inotcontains` não correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-225">`-inotcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="0f6ce-226">`-cnotcontains` não correspondência que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-226">`-cnotcontains` case-sensitive not matched</span></span>

### <a name="-in"></a><span data-ttu-id="0f6ce-227">-in</span><span class="sxs-lookup"><span data-stu-id="0f6ce-227">-in</span></span>

<span data-ttu-id="0f6ce-228">O operador `-in` é exatamente como o operador `-contains`, exceto que a coleção está no lado direito.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-228">The `-in` operator is just like the `-contains` operator except the collection is on the right-hand side.</span></span>

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

<span data-ttu-id="0f6ce-229">**Variações:**</span><span class="sxs-lookup"><span data-stu-id="0f6ce-229">**Variations:**</span></span>

- <span data-ttu-id="0f6ce-230">`-in` correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-230">`-in` case-insensitive match</span></span>
- <span data-ttu-id="0f6ce-231">`-iin` correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-231">`-iin` case-insensitive match</span></span>
- <span data-ttu-id="0f6ce-232">`-cin` correspondência que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-232">`-cin` case-sensitive match</span></span>
- <span data-ttu-id="0f6ce-233">`-notin` não correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-233">`-notin` case-insensitive not matched</span></span>
- <span data-ttu-id="0f6ce-234">`-inotin` não correspondência que não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-234">`-inotin` case-insensitive not matched</span></span>
- <span data-ttu-id="0f6ce-235">`-cnotin` não correspondência que diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-235">`-cnotin` case-sensitive not matched</span></span>

## <a name="logical-operators"></a><span data-ttu-id="0f6ce-236">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="0f6ce-236">Logical operators</span></span>

<span data-ttu-id="0f6ce-237">Os operadores lógicos são usados para inverter ou combinar outras expressões.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-237">Logical operators are used to invert or combine other expressions.</span></span>

### <a name="-not"></a><span data-ttu-id="0f6ce-238">-not</span><span class="sxs-lookup"><span data-stu-id="0f6ce-238">-not</span></span>

<span data-ttu-id="0f6ce-239">O operador `-not` inverte uma expressão de `$false` para `$true` ou de `$true` para `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-239">The `-not` operator flips an expression from `$false` to `$true` or from `$true` to `$false`.</span></span> <span data-ttu-id="0f6ce-240">Aqui está um exemplo em que queremos executar uma ação quando `Test-Path` é `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-240">Here is an example where we want to perform an action when `Test-Path` is `$false`.</span></span>

```powershell
if ( -not ( Test-Path -Path $path ) )
```

<span data-ttu-id="0f6ce-241">A maioria dos operadores nos quais falamos tem uma variação em que você não precisa usar o operador `-not`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-241">Most of the operators we talked about do have a variation where you do not need to use the `-not` operator.</span></span> <span data-ttu-id="0f6ce-242">Mas ainda há momentos em que é útil.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-242">But there are still times it is useful.</span></span>

### <a name="-operator"></a><span data-ttu-id="0f6ce-243">!</span><span class="sxs-lookup"><span data-stu-id="0f6ce-243">!</span></span> <span data-ttu-id="0f6ce-244">operador</span><span class="sxs-lookup"><span data-stu-id="0f6ce-244">operator</span></span>

<span data-ttu-id="0f6ce-245">Você pode usar `!` como um alias para `-not`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-245">You can use `!` as an alias for `-not`.</span></span>

```powershell
if ( -not $value ){}
if ( !$value ){}
```

<span data-ttu-id="0f6ce-246">Você pode ver `!` usados mais por pessoas acostumadas com outras linguagens, como C#.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-246">You may see `!` used more by people that come from another languages like C#.</span></span> <span data-ttu-id="0f6ce-247">Prefiro digitar, pois acho difícil encontrar ao analisar rapidamente meus scripts.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-247">I prefer to type it out because I find it hard to see when quickly looking at my scripts.</span></span>

### <a name="-and"></a><span data-ttu-id="0f6ce-248">-and</span><span class="sxs-lookup"><span data-stu-id="0f6ce-248">-and</span></span>

<span data-ttu-id="0f6ce-249">Você pode combinar expressões com o operador `-and`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-249">You can combine expressions with the `-and` operator.</span></span> <span data-ttu-id="0f6ce-250">Quando você faz isso, ambos os lados precisam ser `$true` para que toda a expressão seja `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-250">When you do that, both sides need to be `$true` for the whole expression to be `$true`.</span></span>

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

<span data-ttu-id="0f6ce-251">Nesse exemplo, `$age` deve ser 13 ou mais velho no lado esquerdo e menor que 55 no lado direito.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-251">In that example, `$age` must be 13 or older for the left side and less than 55 for the right side.</span></span> <span data-ttu-id="0f6ce-252">Adicionei parênteses extras para deixar mais claro nesse exemplo, mas são opcionais, desde que a expressão seja simples.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-252">I added extra parentheses to make it clearer in that example but they're optional as long as the expression is simple.</span></span> <span data-ttu-id="0f6ce-253">Aqui está o mesmo exemplo sem eles.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-253">Here is the same example without them.</span></span>

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

<span data-ttu-id="0f6ce-254">A avaliação ocorre da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-254">Evaluation happens from left to right.</span></span> <span data-ttu-id="0f6ce-255">Se o primeiro item for avaliado como `$false`, sairá antes e não executará a comparação correta.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-255">If the first item evaluates to `$false`, it exits early and doesn't perform the right comparison.</span></span> <span data-ttu-id="0f6ce-256">Isso é útil quando você precisa ter certeza de que um valor existe antes de usá-lo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-256">This is handy when you need to make sure a value exists before you use it.</span></span> <span data-ttu-id="0f6ce-257">Por exemplo, `Test-Path` gera um erro se você der a ele um caminho `$null`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-257">For example, `Test-Path` throws an error if you give it a `$null` path.</span></span>

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a><span data-ttu-id="0f6ce-258">-or</span><span class="sxs-lookup"><span data-stu-id="0f6ce-258">-or</span></span>

<span data-ttu-id="0f6ce-259">O `-or` permite que você especifique duas expressões e retorna `$true` se uma delas for `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-259">The `-or` allows for you to specify two expressions and returns `$true` if either one of them is `$true`.</span></span>

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

<span data-ttu-id="0f6ce-260">Assim como com o operador `-and`, a avaliação ocorre da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-260">Just like with the `-and` operator, the evaluation happens from left to right.</span></span> <span data-ttu-id="0f6ce-261">Exceto que, se a primeira parte for `$true`, a instrução inteira será `$true` e não processará o restante da expressão.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-261">Except that if the first part is `$true`, then the whole statement is `$true` and it doesn't process the rest of the expression.</span></span>

<span data-ttu-id="0f6ce-262">Além disso, observe como a sintaxe funciona para esses operadores.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-262">Also make note of how the syntax works for these operators.</span></span> <span data-ttu-id="0f6ce-263">Você precisa de duas expressões separadas.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-263">You need two separate expressions.</span></span> <span data-ttu-id="0f6ce-264">Já vi usuários tentarem fazer algo como isso `$value -eq 5 -or 6` sem perceber o erro.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-264">I have seen users try to do something like this `$value -eq 5 -or 6` without realizing their mistake.</span></span>

### <a name="-xor-exclusive-or"></a><span data-ttu-id="0f6ce-265">-xor ou exclusivo</span><span class="sxs-lookup"><span data-stu-id="0f6ce-265">-xor exclusive or</span></span>

<span data-ttu-id="0f6ce-266">Esse é um pouco incomum.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-266">This one is a little unusual.</span></span> <span data-ttu-id="0f6ce-267">`-xor` permite que apenas uma expressão seja avaliada como `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-267">`-xor` allows only one expression to evaluate to `$true`.</span></span> <span data-ttu-id="0f6ce-268">Portanto, se ambos os itens forem `$false` ou `$true`, a expressão inteira será `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-268">So if both items are `$false` or both items are `$true`, then the whole expression is `$false`.</span></span> <span data-ttu-id="0f6ce-269">Outra maneira de analisar é que a expressão só será `$true` quando os resultados da expressão forem diferentes.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-269">Another way to look at this is the expression is only `$true` when the results of the expression are different.</span></span>

<span data-ttu-id="0f6ce-270">O uso desse operador lógico é raro e não consigo pensar em um bom exemplo em que o usaria.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-270">It's rare that anyone would ever use this logical operator and I can't think up a good example as to why I would ever use it.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="0f6ce-271">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="0f6ce-271">Bitwise operators</span></span>

<span data-ttu-id="0f6ce-272">Os operadores bit a bit executam cálculos nos bits dentro dos valores e produzem um novo valor como resultado.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-272">Bitwise operators perform calculations on the bits within the values and produce a new value as the result.</span></span> <span data-ttu-id="0f6ce-273">Ensinar [operadores bit a bit][] está além do escopo deste artigo. Mas aqui está a lista deles.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-273">Teaching [bitwise operators][] is beyond the scope of this article, but here is the list the them.</span></span>

- <span data-ttu-id="0f6ce-274">`-band` binário AND</span><span class="sxs-lookup"><span data-stu-id="0f6ce-274">`-band` binary AND</span></span>
- <span data-ttu-id="0f6ce-275">`-bor` binário OR</span><span class="sxs-lookup"><span data-stu-id="0f6ce-275">`-bor` binary OR</span></span>
- <span data-ttu-id="0f6ce-276">`-bxor` binário OR exclusivo</span><span class="sxs-lookup"><span data-stu-id="0f6ce-276">`-bxor` binary exclusive OR</span></span>
- <span data-ttu-id="0f6ce-277">`-bnot` binário NOT</span><span class="sxs-lookup"><span data-stu-id="0f6ce-277">`-bnot` binary NOT</span></span>
- <span data-ttu-id="0f6ce-278">`-shl` shift left</span><span class="sxs-lookup"><span data-stu-id="0f6ce-278">`-shl` shift left</span></span>
- <span data-ttu-id="0f6ce-279">`-shr` shift right</span><span class="sxs-lookup"><span data-stu-id="0f6ce-279">`-shr` shift right</span></span>

## <a name="powershell-expressions"></a><span data-ttu-id="0f6ce-280">Expressões do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f6ce-280">PowerShell expressions</span></span>

<span data-ttu-id="0f6ce-281">Podemos usar o PowerShell normal dentro da instrução de condição.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-281">We can use normal PowerShell inside the condition statement.</span></span>

```powershell
if ( Test-Path -Path $Path )
```

<span data-ttu-id="0f6ce-282">`Test-Path` retorna `$true` ou `$false` quando é executado.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-282">`Test-Path` returns `$true` or `$false` when it executes.</span></span> <span data-ttu-id="0f6ce-283">Isso também se aplica a comandos que retornam outros valores.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-283">This also applies to commands that return other values.</span></span>

```powershell
if ( Get-Process Notepad* )
```

<span data-ttu-id="0f6ce-284">Será avaliado como `$true` se houver um processo retornado e `$false` se não houver nada.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-284">It evaluates to `$true` if there's a returned process and `$false` if there'sn'thing.</span></span> <span data-ttu-id="0f6ce-285">É perfeitamente válido usar expressões de pipeline ou outras instruções do PowerShell, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0f6ce-285">It's perfectly valid to use pipeline expressions or other PowerShell statements like this:</span></span>

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

<span data-ttu-id="0f6ce-286">As expressões podem ser combinadas entre si com os operadores `-and` e `-or`, mas talvez você precise usar parênteses para dividi-las em subexpressões.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-286">These expressions can be combined with each other with the `-and` and `-or` operators, but you may have to use parenthesis to break them into subexpressions.</span></span>

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a><span data-ttu-id="0f6ce-287">Verificação por $null</span><span class="sxs-lookup"><span data-stu-id="0f6ce-287">Checking for $null</span></span>

<span data-ttu-id="0f6ce-288">Obter "sem resultados" ou um valor de `$null` é avaliado como `$false` na instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-288">Having a no result or a `$null` value evaluates to `$false` in the `if` statement.</span></span> <span data-ttu-id="0f6ce-289">Quando você verifica especificamente por `$null`, é uma melhor prática adicionar `$null` no lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-289">When checking specifically for `$null`, it's a best practice to place the `$null` on the left-hand side.</span></span>

```powershell
if ( $null -eq $value )
```

<span data-ttu-id="0f6ce-290">Há algumas nuances para lidar com valores de `$null` no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-290">There are quite a few nuances when dealing with `$null` values in PowerShell.</span></span> <span data-ttu-id="0f6ce-291">Se você estiver interessado em se aprofundar, tenho um artigo sobre [tudo o que você precisa saber sobre $null][].</span><span class="sxs-lookup"><span data-stu-id="0f6ce-291">If you're interested in diving deeper, I have an article about [everything you wanted to know about $null][].</span></span>

### <a name="variable-assignment"></a><span data-ttu-id="0f6ce-292">Atribuição de variável</span><span class="sxs-lookup"><span data-stu-id="0f6ce-292">Variable assignment</span></span>

<span data-ttu-id="0f6ce-293">[Prasoon Karunan V][] me lembrou de adicionar, pois havia esquecido.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-293">I almost forgot to add this one until [Prasoon Karunan V][] reminded me of it.</span></span>

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

<span data-ttu-id="0f6ce-294">Normalmente, quando você atribui um valor a uma variável, o valor não é transmitido para o pipeline ou console.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-294">Normally when you assign a value to a variable, the value isn't passed onto the pipeline or console.</span></span> <span data-ttu-id="0f6ce-295">Quando você faz uma atribuição de variável em uma subexpressão, ela é transmitida para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-295">When you do a variable assignment in a sub expression, it does get passed on to the pipeline.</span></span>

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

<span data-ttu-id="0f6ce-296">Confira como a atribuição de `$first` não tem saída e a atribuição de `$second` tem.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-296">See how the `$first` assignment has no output and the `$second` assignment does?</span></span> <span data-ttu-id="0f6ce-297">Quando uma atribuição é feita em uma instrução `if`, é executada exatamente como a atribuição de `$second` acima.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-297">When an assignment is done in an `if` statement, it executes just like the `$second` assignment above.</span></span> <span data-ttu-id="0f6ce-298">Aqui está um exemplo claro de como você pode usá-la:</span><span class="sxs-lookup"><span data-stu-id="0f6ce-298">Here is a clean example on how you could use it:</span></span>

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

<span data-ttu-id="0f6ce-299">Se `$process` for atribuído com um valor, a instrução será `$true` e `$process` será interrompido.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-299">If `$process` gets assigned a value, then the statement is `$true` and `$process` gets stopped.</span></span>

<span data-ttu-id="0f6ce-300">Certifique-se de não confundir isso com `-eq` porque não é uma verificação de igualdade.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-300">Make sure you don't confuse this with `-eq` because this isn't an equality check.</span></span> <span data-ttu-id="0f6ce-301">Este é um recurso mais obscuro que a maioria das pessoas não percebe como funciona.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-301">This is a more obscure feature that most people don't realize works this way.</span></span>

## <a name="alternate-execution-path"></a><span data-ttu-id="0f6ce-302">Alterar o caminho da execução</span><span class="sxs-lookup"><span data-stu-id="0f6ce-302">Alternate execution path</span></span>

<span data-ttu-id="0f6ce-303">A instrução `if` permite que você especifique uma ação para não apenas quando a instrução é `$true`, mas também para quando é `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-303">The `if` statement allows you to specify an action for not only when the statement is `$true`, but also for when it's `$false`.</span></span> <span data-ttu-id="0f6ce-304">É aí que a instrução `else` entra em cena.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-304">This is where the `else` statement comes into play.</span></span>

### <a name="else"></a><span data-ttu-id="0f6ce-305">else</span><span class="sxs-lookup"><span data-stu-id="0f6ce-305">else</span></span>

<span data-ttu-id="0f6ce-306">A instrução `else` é sempre a última parte da instrução `if`, quando usada.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-306">The `else` statement is always the last part of the `if` statement when used.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

<span data-ttu-id="0f6ce-307">Neste exemplo, verificamos o `$path` para garantir que é um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-307">In this example, we check the `$path` to make sure it's a file.</span></span> <span data-ttu-id="0f6ce-308">Se encontrarmos o arquivo, nós o moveremos.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-308">If we find the file, we move it.</span></span> <span data-ttu-id="0f6ce-309">Caso contrário, devemos escrever um aviso.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-309">If not, we write a warning.</span></span> <span data-ttu-id="0f6ce-310">Esse tipo de lógica de ramificação é muito comum.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-310">This type of branching logic is very common.</span></span>

### <a name="nested-if"></a><span data-ttu-id="0f6ce-311">if aninhado</span><span class="sxs-lookup"><span data-stu-id="0f6ce-311">Nested if</span></span>

<span data-ttu-id="0f6ce-312">As instruções `if` e `else` usam um scriptblock. Portanto, podemos adicionar qualquer comando do PowerShell, incluindo outra instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-312">The `if` and `else` statements take a script block, so we can place any PowerShell command inside them, including another `if` statement.</span></span> <span data-ttu-id="0f6ce-313">Isso permite que você use uma lógica muito mais complicada.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-313">This allows you to make use of much more complicated logic.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

<span data-ttu-id="0f6ce-314">Neste exemplo, testamos primeiro o caminho feliz e depois executamos uma ação nele.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-314">In this example, we test the happy path first and then take action on it.</span></span> <span data-ttu-id="0f6ce-315">Se falhar, faremos outra verificação e forneceremos informações mais detalhadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-315">If that fails, we do another check and to provide more detailed information to the user.</span></span>

### <a name="elseif"></a><span data-ttu-id="0f6ce-316">elseif</span><span class="sxs-lookup"><span data-stu-id="0f6ce-316">elseif</span></span>

<span data-ttu-id="0f6ce-317">Não estamos limitados a apenas uma única verificação condicional.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-317">We aren't limited to just a single conditional check.</span></span> <span data-ttu-id="0f6ce-318">Podemos encadear instruções `if` e `else` juntas em vez de aninhar usando a instrução `elseif`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-318">We can chain `if` and `else` statements together instead of nesting them by using the `elseif` statement.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

<span data-ttu-id="0f6ce-319">A execução ocorre de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-319">The execution happens from the top to the bottom.</span></span> <span data-ttu-id="0f6ce-320">A instrução `if` superior é avaliada primeiro.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-320">The top `if` statement is evaluated first.</span></span> <span data-ttu-id="0f6ce-321">Se for `$false`, passará para a próxima `elseif` ou `else` na lista.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-321">If that is `$false`, then it moves down to the next `elseif` or `else` in the list.</span></span> <span data-ttu-id="0f6ce-322">A última `else` será a ação padrão a ser tomada se nenhuma das outras retornar `$true`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-322">That last `else` is the default action to take if none of the others return `$true`.</span></span>

### <a name="switch"></a><span data-ttu-id="0f6ce-323">switch</span><span class="sxs-lookup"><span data-stu-id="0f6ce-323">switch</span></span>

<span data-ttu-id="0f6ce-324">Neste ponto, preciso mencionar a instrução `switch`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-324">At this point, I need to mention the `switch` statement.</span></span> <span data-ttu-id="0f6ce-325">Fornece uma sintaxe alternativa para fazer várias comparações com um valor.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-325">It provides an alternate syntax for doing multiple comparisons with a value.</span></span> <span data-ttu-id="0f6ce-326">Com `switch`, você especifica uma expressão, e esse resultado é comparado com vários valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-326">With the `switch`, you specify an expression and that result gets compared with several different values.</span></span> <span data-ttu-id="0f6ce-327">Se um dos valores corresponder, o bloco de código correspondente será executado.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-327">If one of those values match, the matching code block is executed.</span></span> <span data-ttu-id="0f6ce-328">Veja este exemplo:</span><span class="sxs-lookup"><span data-stu-id="0f6ce-328">Take a look at this example:</span></span>

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

<span data-ttu-id="0f6ce-329">Há três valores possíveis que podem corresponder à `$itemType`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-329">There three possible values that can match the `$itemType`.</span></span> <span data-ttu-id="0f6ce-330">Nesse caso, corresponde com `Role`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-330">In this case, it matches with `Role`.</span></span> <span data-ttu-id="0f6ce-331">Usei um exemplo simples apenas para mostrar a você um pouco do operador `switch`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-331">I used a simple example just to give you some exposure to the `switch` operator.</span></span> <span data-ttu-id="0f6ce-332">Falarei mais sobre [tudo o que você queria saber sobre a instrução switch][] em outro artigo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-332">I talk more about [everything you ever wanted to know about the switch statement][] in another article.</span></span>

## <a name="pipeline"></a><span data-ttu-id="0f6ce-333">Pipeline</span><span class="sxs-lookup"><span data-stu-id="0f6ce-333">Pipeline</span></span>

<span data-ttu-id="0f6ce-334">O pipeline é um recurso exclusivo e importante do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-334">The pipeline is a unique and important feature of PowerShell.</span></span> <span data-ttu-id="0f6ce-335">Qualquer valor que não seja suprimido ou atribuído a uma variável será colocado no pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-335">Any value that isn't suppressed or assigned to a variable gets placed in the pipeline.</span></span> <span data-ttu-id="0f6ce-336">O `if` fornece uma maneira de aproveitar o pipeline de uma forma que nem sempre é óbvia.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-336">The `if` provides us a way to take advantage of the pipeline in a way that isn't always obvious.</span></span>

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

<span data-ttu-id="0f6ce-337">Cada scriptblock está colocando os resultados dos comandos ou do valor no pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-337">Each script block is placing the results the commands or the value into the pipeline.</span></span> <span data-ttu-id="0f6ce-338">Em seguida, atribuímos o resultado da instrução `if` à variável `$discount`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-338">Then we assign the result of the `if` statement to the `$discount` variable.</span></span> <span data-ttu-id="0f6ce-339">Esse exemplo poderia ser tão facilmente atribuído aos valores para a variável `$discount` diretamente em cada scriptblock.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-339">That example could have just as easily assigned those values to the `$discount` variable directly in each scriptblock.</span></span> <span data-ttu-id="0f6ce-340">Não posso dizer que uso com a instrução `if` com frequência, mas tenho um exemplo onde usei recentemente.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-340">I can't say that I use this with the `if` statement often, but I do have an example where I used this recently.</span></span>

### <a name="array-inline"></a><span data-ttu-id="0f6ce-341">Matriz embutida</span><span class="sxs-lookup"><span data-stu-id="0f6ce-341">Array inline</span></span>

<span data-ttu-id="0f6ce-342">Tenho uma função chamada [Invoke-SnowSql][] que inicia um executável com vários argumentos de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-342">I have a function called [Invoke-SnowSql][] that launches an executable with several command-line arguments.</span></span> <span data-ttu-id="0f6ce-343">Aqui está um clipe da função em que crio a matriz de argumentos.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-343">Here is a clip from that function where I build the array of arguments.</span></span>

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

<span data-ttu-id="0f6ce-344">As variáveis `$Debug` e `$Path` são parâmetros na função fornecida pelo usuário final.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-344">The `$Debug` and `$Path` variables are parameters on the function that are provided by the end user.</span></span>
<span data-ttu-id="0f6ce-345">Posso avaliar embutidos dentro da inicialização da minha matriz.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-345">I evaluate them inline inside the initialization of my array.</span></span> <span data-ttu-id="0f6ce-346">Se `$Debug` for true, os valores estarão no `$snowSqlParam` no local correto.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-346">If `$Debug` is true, then those values fall into the `$snowSqlParam` in the correct place.</span></span> <span data-ttu-id="0f6ce-347">O mesmo se aplica à variável `$Path`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-347">Same holds true for the `$Path` variable.</span></span>

## <a name="simplify-complex-operations"></a><span data-ttu-id="0f6ce-348">Simplificar operações complexas</span><span class="sxs-lookup"><span data-stu-id="0f6ce-348">Simplify complex operations</span></span>

<span data-ttu-id="0f6ce-349">É inevitável enfrentar situações em que haja muitas comparações a serem verificadas e a instrução `If` fique na extremidade direita da tela.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-349">It's inevitable that you run into a situation that has way too many comparisons to check and your `If` statement scrolls way off the right side of the screen.</span></span>

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

<span data-ttu-id="0f6ce-350">Podem ser difíceis de ler e que o tornam mais propenso a cometer erros.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-350">They can be hard to read and that make you more prone to make mistakes.</span></span> <span data-ttu-id="0f6ce-351">Há algumas coisas que podemos fazer sobre isso.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-351">There are a few things we can do about that.</span></span>

### <a name="line-continuation"></a><span data-ttu-id="0f6ce-352">Continuação de linha</span><span class="sxs-lookup"><span data-stu-id="0f6ce-352">Line continuation</span></span>

<span data-ttu-id="0f6ce-353">Há alguns operadores no PowerShell que permitem encapsular o comando na próxima linha.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-353">There some operators in PowerShell that let you wrap you command to the next line.</span></span> <span data-ttu-id="0f6ce-354">Os operadores lógicos `-and` e `-or` serão bons operadores para serem usados se você quiser dividir a expressão em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-354">The logical operators `-and` and `-or` are good operators to use if you want to break your expression into multiple lines.</span></span>

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

<span data-ttu-id="0f6ce-355">Ainda há muita coisa acontecendo, mas colocar cada peça em sua própria linha faz uma grande diferença.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-355">There's still a lot going on there, but placing each piece on its own line makes a big difference.</span></span>
<span data-ttu-id="0f6ce-356">Geralmente uso quando obtenho mais de duas comparações ou se preciso rolar para a direita para ler qualquer uma das lógicas.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-356">I generally use this when I get more than two comparisons or if I have to scroll to the right to read any of the logic.</span></span>

### <a name="pre-calculating-results"></a><span data-ttu-id="0f6ce-357">Pré-calcular resultados</span><span class="sxs-lookup"><span data-stu-id="0f6ce-357">Pre-calculating results</span></span>

<span data-ttu-id="0f6ce-358">Podemos retirar essa instrução da instrução `if` e verificar apenas o resultado.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-358">We can take that statement out of the `if` statement and only check the result.</span></span>

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

<span data-ttu-id="0f6ce-359">Isso parecerá muito mais limpo que o exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-359">This just feels much cleaner than the previous example.</span></span> <span data-ttu-id="0f6ce-360">Você também terá a oportunidade de usar um nome de variável que explica o que você está realmente verificando.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-360">You also are given an opportunity to use a variable name that explains what it's that you're really checking.</span></span> <span data-ttu-id="0f6ce-361">Também é um exemplo de código de autodocumentação que evita comentários desnecessários.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-361">This is also and example of self-documenting code that saves unnecessary comments.</span></span>

### <a name="multiple-if-statements"></a><span data-ttu-id="0f6ce-362">Várias instruções if</span><span class="sxs-lookup"><span data-stu-id="0f6ce-362">Multiple if statements</span></span>

<span data-ttu-id="0f6ce-363">Podemos dividir em várias instruções e verificar uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-363">We can break this up into multiple statements and check them one at a time.</span></span> <span data-ttu-id="0f6ce-364">Neste caso, usamos um sinalizador ou uma variável de rastreamento para combinar os resultados.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-364">In this case, we use a flag or a tracking variable to combine the results.</span></span>

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

<span data-ttu-id="0f6ce-365">Precisei inverter a lógica para fazer com que a lógica do sinalizador funcionasse corretamente.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-365">I did have to invert the logic to make the flag logic work correctly.</span></span> <span data-ttu-id="0f6ce-366">Cada avaliação é uma instrução `if` individual.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-366">Each evaluation is an individual `if` statement.</span></span> <span data-ttu-id="0f6ce-367">A vantagem disso é que, quando você estiver depurando, poderá dizer exatamente o que a lógica está fazendo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-367">The advantage of this is that when you're debugging, you can tell exactly what the logic is doing.</span></span> <span data-ttu-id="0f6ce-368">Ao mesmo tempo, consegui adicionar um detalhamento muito melhor.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-368">I was able to add much better verbosity at the same time.</span></span>

<span data-ttu-id="0f6ce-369">A desvantagem óbvia é que há muito mais código a ser escrito.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-369">The obvious downside is that it's so much more code to write.</span></span> <span data-ttu-id="0f6ce-370">O código é mais complexo de examinar, pois usa uma única linha de lógica e a detalha em 25 ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-370">The code is more complex to look at as it takes a single line of logic and explodes it into 25 or more lines.</span></span>

### <a name="using-functions"></a><span data-ttu-id="0f6ce-371">Usar funções</span><span class="sxs-lookup"><span data-stu-id="0f6ce-371">Using functions</span></span>

<span data-ttu-id="0f6ce-372">Também podemos mover toda a lógica de validação para uma função.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-372">We can also move all that validation logic into a function.</span></span> <span data-ttu-id="0f6ce-373">Veja rapidamente como parece limpo.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-373">Look at how clean this looks at a glance.</span></span>

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

<span data-ttu-id="0f6ce-374">Você ainda precisará criar a função para fazer a validação, mas torna o código muito mais fácil para trabalhar.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-374">You still have to create the function to do the validation, but it makes this code much easier to work with.</span></span> <span data-ttu-id="0f6ce-375">Torna o teste do código mais fácil.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-375">It makes this code easier to test.</span></span> <span data-ttu-id="0f6ce-376">Em seus testes, você pode simular a chamada para `Test-ADDriveConfiguration` e só precisa de dois testes para essa função.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-376">In your tests, you can mock the call to `Test-ADDriveConfiguration` and you only need two tests for this function.</span></span> <span data-ttu-id="0f6ce-377">Um onde retorna `$true` e outro onde retorna `$false`.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-377">One where it returns `$true` and one where it returns `$false`.</span></span> <span data-ttu-id="0f6ce-378">Testar a outra função é mais simples porque é muito pequena.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-378">Testing the other function is simpler because it's so small.</span></span>

<span data-ttu-id="0f6ce-379">O corpo dessa função ainda pode ser aquele de uma linha que começamos ou a lógica explodida que usamos na última seção.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-379">The body of that function could still be that one-liner we started with or the exploded logic that we used in the last section.</span></span> <span data-ttu-id="0f6ce-380">Isso funciona bem para ambos os cenários e permite que você altere facilmente a implementação posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-380">This works well for both scenarios and allows you to easily change that implementation later.</span></span>

## <a name="error-handling"></a><span data-ttu-id="0f6ce-381">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="0f6ce-381">Error handling</span></span>

<span data-ttu-id="0f6ce-382">Um uso importante da instrução `if` é verificar as condições de erro antes de encontrar erros.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-382">One important use of the `if` statement is to check for error conditions before you run into errors.</span></span> <span data-ttu-id="0f6ce-383">Um bom exemplo é verificar se já existe uma pasta antes de tentar criá-la.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-383">A good example is to check if a folder already exists before you try to create it.</span></span>

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

<span data-ttu-id="0f6ce-384">Se você espera que uma exceção aconteça, não é realmente uma exceção.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-384">I like to say that if you expect an exception to happen, then it's not really an exception.</span></span> <span data-ttu-id="0f6ce-385">Portanto, verifique os valores e valide as condições quando possível.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-385">So check your values and validate your conditions where you can.</span></span>

<span data-ttu-id="0f6ce-386">Se você quiser se aprofundar mais no tratamento de exceções, tenho um artigo sobre [tudo o que você quis saber sobre exceções][].</span><span class="sxs-lookup"><span data-stu-id="0f6ce-386">If you want to dive a little more into actual exception handling, I have an article on [everything you ever wanted to know about exceptions][].</span></span>

## <a name="final-words"></a><span data-ttu-id="0f6ce-387">Conclusão</span><span class="sxs-lookup"><span data-stu-id="0f6ce-387">Final words</span></span>

<span data-ttu-id="0f6ce-388">A instrução `if` é uma instrução simples, mas é uma parte fundamental do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-388">The `if` statement is such a simple statement but is a fundamental piece of PowerShell.</span></span> <span data-ttu-id="0f6ce-389">Você se encontrará usando-a várias vezes em quase todos os scripts que escrever.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-389">You will find yourself using this multiple times in almost every script you write.</span></span> <span data-ttu-id="0f6ce-390">Espero que você tenha um entendimento melhor do que antes.</span><span class="sxs-lookup"><span data-stu-id="0f6ce-390">I hope you have a better understanding than you had before.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2019-08-11-Powershell-if-then-else-equals-operator/
[original version]: https://powershellexplained.com/2019-08-11-Powershell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if
[operadores bit a bit]: /powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[bitwise operators]: /powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[, as várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[the many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[tudo o que você quis saber sobre exceções]: everything-about-exceptions.md
[everything you ever wanted to know about exceptions]: everything-about-exceptions.md
[tudo o que você precisa saber sobre $null]: everything-about-null.md
[everything you wanted to know about $null]: everything-about-null.md
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[tudo o que você queria saber sobre a instrução switch]: everything-about-switch.md
[everything you ever wanted to know about the switch statement]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
