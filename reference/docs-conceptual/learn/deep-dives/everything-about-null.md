---
title: Tudo o que você queria saber sobre o $null
description: Normalmente, o $null do PowerShell parece ser simples, mas tem inúmeras nuances. Vamos examinar o $null para entender o que acontece quando nos deparamos inesperadamente com um valor nulo.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e0553a5e17450d8044f548792649369e99903850
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149469"
---
# <a name="everything-you-wanted-to-know-about-null"></a><span data-ttu-id="e9a51-104">Tudo o que você queria saber sobre o $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-104">Everything you wanted to know about $null</span></span>

<span data-ttu-id="e9a51-105">Normalmente, o `$null` do PowerShell parece ser simples, mas tem inúmeras nuances.</span><span class="sxs-lookup"><span data-stu-id="e9a51-105">The PowerShell `$null` often appears to be simple but it has a lot of nuances.</span></span> <span data-ttu-id="e9a51-106">Vamos examinar o `$null` para entender o que acontece quando nos deparamos inesperadamente com um valor `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-106">Let's take a close look at `$null` so you know what happens when you unexpectedly run into a `$null` value.</span></span>

> [!NOTE]
> <span data-ttu-id="e9a51-107">A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="e9a51-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="e9a51-108">A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="e9a51-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="e9a51-109">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="e9a51-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-null"></a><span data-ttu-id="e9a51-110">O que é NULL?</span><span class="sxs-lookup"><span data-stu-id="e9a51-110">What is NULL?</span></span>

<span data-ttu-id="e9a51-111">Você pode pensar no NULL como um valor desconhecido ou vazio.</span><span class="sxs-lookup"><span data-stu-id="e9a51-111">You can think of NULL as an unknown or empty value.</span></span> <span data-ttu-id="e9a51-112">Uma variável será NULL até que você atribua um valor ou um objeto a ela.</span><span class="sxs-lookup"><span data-stu-id="e9a51-112">A variable is NULL until you assign a value or an object to it.</span></span> <span data-ttu-id="e9a51-113">Isso pode ser importante porque há alguns comandos que exigem um valor e geram erros se o valor for NULL.</span><span class="sxs-lookup"><span data-stu-id="e9a51-113">This can be important because there are some commands that require a value and generate errors if the value is NULL.</span></span>

### <a name="powershell-null"></a><span data-ttu-id="e9a51-114">$null do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9a51-114">PowerShell $null</span></span>

<span data-ttu-id="e9a51-115">O `$null` é uma variável automática do PowerShell usada para representar NULL.</span><span class="sxs-lookup"><span data-stu-id="e9a51-115">`$null` is an automatic variable in PowerShell used to represent NULL.</span></span> <span data-ttu-id="e9a51-116">Você poderá atribui-la a variáveis, usá-la em comparações ou empregá-la como um espaço reservado para NULL em uma coleção.</span><span class="sxs-lookup"><span data-stu-id="e9a51-116">You can assign it to variables, use it in comparisons and use it as a place holder for NULL in a collection.</span></span>

<span data-ttu-id="e9a51-117">O PowerShell trata `$null` como um objeto de valor NULL.</span><span class="sxs-lookup"><span data-stu-id="e9a51-117">PowerShell treats `$null` as an object with a value of NULL.</span></span> <span data-ttu-id="e9a51-118">Isso será diferente do que você pode esperar se estiver acostumado com outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="e9a51-118">This is different than what you may expect if you come from another language.</span></span>

## <a name="examples-of-null"></a><span data-ttu-id="e9a51-119">Exemplos de $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-119">Examples of $null</span></span>

<span data-ttu-id="e9a51-120">Sempre que você tentar usar uma variável que não foi inicializada, o valor será `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-120">Anytime you try to use a variable that you have not initialized, the value is `$null`.</span></span> <span data-ttu-id="e9a51-121">Essa é uma das maneiras mais comuns pelas quais os valores `$null` se infiltram em seu código.</span><span class="sxs-lookup"><span data-stu-id="e9a51-121">This is one of the most common ways that `$null` values sneak into your code.</span></span>

```powershell
PS> $null -eq $undefinedVariable
True
```

<span data-ttu-id="e9a51-122">Se você digitar o nome de uma variável incorretamente por engano, o PowerShell a verá como uma variável diferente e o valor atribuído será `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-122">If you happen to mistype a variable name then PowerShell sees it as a different variable and the value is `$null`.</span></span>

<span data-ttu-id="e9a51-123">A outra maneira de encontrar valores `$null` é quando eles são provenientes de outros comandos que não fornecem nenhum resultado.</span><span class="sxs-lookup"><span data-stu-id="e9a51-123">The other way you find `$null` values is when they come from other commands that don't give you any results.</span></span>

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a><span data-ttu-id="e9a51-124">Impacto do $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-124">Impact of $null</span></span>

<span data-ttu-id="e9a51-125">Os valores `$null` impactam seu código de maneira diferente, dependendo do local em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="e9a51-125">`$null` values impact your code differently depending on where they show up.</span></span>

### <a name="in-strings"></a><span data-ttu-id="e9a51-126">Em cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e9a51-126">In strings</span></span>

<span data-ttu-id="e9a51-127">Se você usar o `$null` em uma cadeia de caracteres, ela será um valor em branco (ou uma cadeia de caracteres vazia).</span><span class="sxs-lookup"><span data-stu-id="e9a51-127">If you use `$null` in a string, then it's a blank value (or empty string).</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

<span data-ttu-id="e9a51-128">Essa é uma das razões pelas quais eu gosto de colocar colchetes ao redor das variáveis ao usá-las nas mensagens de log.</span><span class="sxs-lookup"><span data-stu-id="e9a51-128">This is one of the reasons that I like to place brackets around variables when using them in log messages.</span></span> <span data-ttu-id="e9a51-129">É ainda mais importante identificar os limites dos valores das variáveis quando o valor está ao final da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e9a51-129">It's even more important to identify the edges of your variable values when the value is at the end of the string.</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

<span data-ttu-id="e9a51-130">Isso torna as cadeias de caracteres vazias e os valores `$null` fáceis de identificar.</span><span class="sxs-lookup"><span data-stu-id="e9a51-130">This makes empty strings and `$null` values easy to spot.</span></span>

### <a name="in-numeric-equation"></a><span data-ttu-id="e9a51-131">Em equações numéricas</span><span class="sxs-lookup"><span data-stu-id="e9a51-131">In numeric equation</span></span>

<span data-ttu-id="e9a51-132">Quando um valor `$null` é usado em uma equação numérica, os resultados são inválidos caso não gerem erro.</span><span class="sxs-lookup"><span data-stu-id="e9a51-132">When a `$null` value is used in a numeric equation then your results are invalid if they don't give an error.</span></span> <span data-ttu-id="e9a51-133">Às vezes, o `$null` é avaliado como `0` e outras vezes torna todo o resultado `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-133">Sometimes the `$null` evaluates to `0` and other times it makes the whole result `$null`.</span></span>
<span data-ttu-id="e9a51-134">Aqui está um exemplo com multiplicação que fornece 0 ou `$null`, dependendo da ordem dos valores.</span><span class="sxs-lookup"><span data-stu-id="e9a51-134">Here is an example with multiplication that gives 0 or `$null` depending on the order of the values.</span></span>

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a><span data-ttu-id="e9a51-135">No lugar de uma coleção</span><span class="sxs-lookup"><span data-stu-id="e9a51-135">In place of a collection</span></span>

<span data-ttu-id="e9a51-136">Uma coleção permite que você use um índice para acessar os valores.</span><span class="sxs-lookup"><span data-stu-id="e9a51-136">A collection allow you use an index to access values.</span></span> <span data-ttu-id="e9a51-137">Se você tentar indexar uma coleção que corresponde a `null`, receberá o seguinte erro: `Cannot index into a null array`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-137">If you try to index into a collection that is actually `null`, you get this error: `Cannot index into a null array`.</span></span>

```powershell
PS> $value = $null
PS> $value[10]
Cannot index into a null array.
At line:1 char:1
+ $value[10]
+ ~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : NullArray
```

<span data-ttu-id="e9a51-138">Se você tiver uma coleção, mas tentar acessar um elemento que não pertence à coleção, receberá `$null` como resultado.</span><span class="sxs-lookup"><span data-stu-id="e9a51-138">If you have a collection but try to access an element that is not in the collection, you get a `$null` result.</span></span>

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a><span data-ttu-id="e9a51-139">No lugar de um objeto</span><span class="sxs-lookup"><span data-stu-id="e9a51-139">In place of an object</span></span>

<span data-ttu-id="e9a51-140">Se você tentar acessar uma propriedade ou uma subpropriedade de um objeto que não tem aquela propriedade especificada, obterá um valor `$null`, assim como ocorreria para uma variável indefinida.</span><span class="sxs-lookup"><span data-stu-id="e9a51-140">If you try to access a property or sub property of an object that doesn't have the specified property, you get a `$null` value like you would for an undefined variable.</span></span> <span data-ttu-id="e9a51-141">Não importa se a variável é `$null` ou um objeto real nesse caso.</span><span class="sxs-lookup"><span data-stu-id="e9a51-141">It doesn't matter if the variable is `$null` or an actual object in this case.</span></span>

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a><span data-ttu-id="e9a51-142">Método em uma expressão com valor nulo</span><span class="sxs-lookup"><span data-stu-id="e9a51-142">Method on a null-valued expression</span></span>

<span data-ttu-id="e9a51-143">Chamar um método em um objeto `$null` gera um `RuntimeException`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-143">Calling a method on a `$null` object throws a `RuntimeException`.</span></span>

```powershell
PS> $value = $null
PS> $value.toString()
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $value.tostring()
+ ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
```

<span data-ttu-id="e9a51-144">Sempre que vejo a frase `You cannot call a method on a null-valued expression`, a primeira coisa que procuro são locais onde algum método esteja sendo chamado em uma variável sem antes verificar se ele corresponde a `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-144">Whenever I see the phrase `You cannot call a method on a null-valued expression` then the first thing I look for are places where I am calling a method on a variable without first checking it for `$null`.</span></span>

## <a name="checking-for-null"></a><span data-ttu-id="e9a51-145">Verificando se corresponde a $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-145">Checking for $null</span></span>

<span data-ttu-id="e9a51-146">Talvez você tenha notado que eu sempre coloco o `$null` à esquerda ao verificar se corresponde a `$null` em meus exemplos.</span><span class="sxs-lookup"><span data-stu-id="e9a51-146">You may have noticed that I always place the `$null` on the left when checking for `$null` in my examples.</span></span> <span data-ttu-id="e9a51-147">Isso é intencional e aceito como uma melhor prática do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9a51-147">This is intentional and accepted as a PowerShell best practice.</span></span> <span data-ttu-id="e9a51-148">Há alguns cenários em que colocá-lo à direita não gera o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="e9a51-148">There are some scenarios where placing it on the right doesn't give you the expected result.</span></span>

<span data-ttu-id="e9a51-149">Observe o próximo exemplo e tente prever os resultados:</span><span class="sxs-lookup"><span data-stu-id="e9a51-149">Look at this next example and try to predict the results:</span></span>

```powershell
if ( $value -eq $null )
{
    'The array is $null'
}
if ( $value -ne $null )
{
    'The array is not $null'
}
```

<span data-ttu-id="e9a51-150">Se eu não definir `$value`, o primeiro será avaliado como `$true` e a mensagem será `The array is $null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-150">If I do not define `$value`, the first one evaluates to `$true` and our message is `The array is $null`.</span></span> <span data-ttu-id="e9a51-151">A armadilha aqui é que é possível criar um `$value` que permita que ambos sejam `$false`</span><span class="sxs-lookup"><span data-stu-id="e9a51-151">The trap here is that it's possible to create a `$value` that allows both of them to be `$false`</span></span>

```powershell
$value = @( $null )
```

<span data-ttu-id="e9a51-152">Nesse caso, o `$value` é uma matriz que contém um `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-152">In this case, the `$value` is an array that contains a `$null`.</span></span> <span data-ttu-id="e9a51-153">O `-eq` verifica cada valor da matriz e retorna o `$null` com correspondência.</span><span class="sxs-lookup"><span data-stu-id="e9a51-153">The `-eq` checks every value in the array and returns the `$null` that is matched.</span></span> <span data-ttu-id="e9a51-154">Isso é avaliado como `$false`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-154">This evaluates to `$false`.</span></span> <span data-ttu-id="e9a51-155">O `-ne` retorna tudo que não corresponde a `$null` e, nesse caso, não há resultados (isso também é avaliado como `$false`).</span><span class="sxs-lookup"><span data-stu-id="e9a51-155">The `-ne` returns everything that doesn't match `$null` and in this case there are no results (This also evaluates to `$false`).</span></span> <span data-ttu-id="e9a51-156">Nenhuma delas é `$true`, embora pareça que uma delas deveria ser.</span><span class="sxs-lookup"><span data-stu-id="e9a51-156">Neither one is `$true` even though it looks like one of them should be.</span></span>

<span data-ttu-id="e9a51-157">Não só podemos criar um valor que faça com que ambos sejam avaliados como `$false`, também é possível criar um valor em que ambos sejam avaliados como `$true`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-157">Not only can we create a value that makes both of them evaluate to `$false`, it's possible to create a value where they both evaluate to `$true`.</span></span> <span data-ttu-id="e9a51-158">Mathias Jessen (@IISResetMe) tem uma [excelente postagem][] que explora esse cenário.</span><span class="sxs-lookup"><span data-stu-id="e9a51-158">Mathias Jessen (@IISResetMe) has a [good post][] that dives into that scenario.</span></span>

### <a name="psscriptanalyzer-and-vscode"></a><span data-ttu-id="e9a51-159">PSScriptAnalyzer e VSCode</span><span class="sxs-lookup"><span data-stu-id="e9a51-159">PSScriptAnalyzer and VSCode</span></span>

<span data-ttu-id="e9a51-160">O módulo do [PSScriptAnalyzer][] tem uma regra que verifica a ocorrência desse problema chamado `PSPossibleIncorrectComparisonWithNull`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-160">The [PSScriptAnalyzer][] module has a rule that checks for this issue called `PSPossibleIncorrectComparisonWithNull`.</span></span>

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

<span data-ttu-id="e9a51-161">Como o VS Code também usa as regras do PSScriptAnalyser, ele realça ou identifica isso como um problema em seu script.</span><span class="sxs-lookup"><span data-stu-id="e9a51-161">Because VS Code uses the PSScriptAnalyser rules too, it also highlights or identifies this as a problem in your script.</span></span>

### <a name="simple-if-check"></a><span data-ttu-id="e9a51-162">Verificação simples</span><span class="sxs-lookup"><span data-stu-id="e9a51-162">Simple if check</span></span>

<span data-ttu-id="e9a51-163">Uma forma comum pela qual as pessoas verificam um valor não $null é usando uma instrução `if()` simples sem a comparação.</span><span class="sxs-lookup"><span data-stu-id="e9a51-163">A common way that people check for a non-$null value is to use a simple `if()` statement without the comparison.</span></span>

```powershell
if ( $value )
{
    Do-Something
}
```

<span data-ttu-id="e9a51-164">Se o valor for `$null`, isso será avaliado como `$false`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-164">If the value is `$null`, this evaluates to `$false`.</span></span> <span data-ttu-id="e9a51-165">Isso é fácil de ler, mas tenha cuidado para que ele esteja procurando exatamente o que você espera que ele procure.</span><span class="sxs-lookup"><span data-stu-id="e9a51-165">This is easy to read, but be careful that it's looking for exactly what you're expecting it to look for.</span></span> <span data-ttu-id="e9a51-166">Eu li essa linha de código como:</span><span class="sxs-lookup"><span data-stu-id="e9a51-166">I read that line of code as:</span></span>

> <span data-ttu-id="e9a51-167">Se `$value` tiver um valor.</span><span class="sxs-lookup"><span data-stu-id="e9a51-167">If `$value` has a value.</span></span>

<span data-ttu-id="e9a51-168">Mas essa não é a realidade.</span><span class="sxs-lookup"><span data-stu-id="e9a51-168">But that's not the whole story.</span></span> <span data-ttu-id="e9a51-169">Na verdade, a linha está dizendo:</span><span class="sxs-lookup"><span data-stu-id="e9a51-169">That line is actually saying:</span></span>

> <span data-ttu-id="e9a51-170">Se `$value` não for `$null` ou `0` ou `$false` ou um `empty string`</span><span class="sxs-lookup"><span data-stu-id="e9a51-170">If `$value` is not `$null` or `0` or `$false` or an `empty string`</span></span>

<span data-ttu-id="e9a51-171">Aqui está um exemplo mais completo dessa instrução.</span><span class="sxs-lookup"><span data-stu-id="e9a51-171">Here is a more complete sample of that statement.</span></span>

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

<span data-ttu-id="e9a51-172">É perfeitamente possível usar uma verificação básica de `if`, contanto que você se lembre de que esses outros valores contam como `$false` e não apenas que uma variável tem um valor.</span><span class="sxs-lookup"><span data-stu-id="e9a51-172">It's perfectly OK to use a basic `if` check as long as you remember those other values count as `$false` and not just that a variable has a value.</span></span>

<span data-ttu-id="e9a51-173">Eu tive esse problema ao refatorar alguns códigos há alguns dias.</span><span class="sxs-lookup"><span data-stu-id="e9a51-173">I ran into this issue when refactoring some code a few days ago.</span></span> <span data-ttu-id="e9a51-174">Ele tinha uma verificação de propriedade básica como esta.</span><span class="sxs-lookup"><span data-stu-id="e9a51-174">It had a basic property check like this.</span></span>

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="e9a51-175">Eu queria atribuir um valor à propriedade dos objetos somente se ele existisse.</span><span class="sxs-lookup"><span data-stu-id="e9a51-175">I wanted to assign a value to the object property only if it existed.</span></span> <span data-ttu-id="e9a51-176">Na maioria dos casos, o objeto original tinha um valor que seria avaliado como `$true` na instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-176">In most cases, the original object had a value that would evaluate to `$true` in the `if` statement.</span></span> <span data-ttu-id="e9a51-177">Mas eu encontrei um problema em que o valor, ocasionalmente, não era definido.</span><span class="sxs-lookup"><span data-stu-id="e9a51-177">But I ran into an issue where the value was occasionally not getting set.</span></span> <span data-ttu-id="e9a51-178">Eu depurei o código e descobri que o objeto tinha a propriedade, mas ela era um valor de cadeia de caracteres em branco.</span><span class="sxs-lookup"><span data-stu-id="e9a51-178">I debugged the code and found that the object had the property but it was a blank string value.</span></span> <span data-ttu-id="e9a51-179">Isso impedia que ela fosse atualizada com a lógica anterior.</span><span class="sxs-lookup"><span data-stu-id="e9a51-179">This prevented it from ever getting updated with the previous logic.</span></span> <span data-ttu-id="e9a51-180">Então, adicionei uma verificação de `$null` adequada e tudo funcionou.</span><span class="sxs-lookup"><span data-stu-id="e9a51-180">So I added a proper `$null` check and everything worked.</span></span>

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="e9a51-181">São pequenos bugs como esses que são difíceis de identificar e fazem com que eu verifique de maneira agressiva se os valores correspondem a `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-181">It's little bugs like these that are hard to spot and make me aggressively check values for `$null`.</span></span>

## <a name="nullcount"></a><span data-ttu-id="e9a51-182">$null.Count</span><span class="sxs-lookup"><span data-stu-id="e9a51-182">$null.Count</span></span>

<span data-ttu-id="e9a51-183">Se você tentar acessar uma propriedade em um valor `$null`, a propriedade também será `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-183">If you try to access a property on a `$null` value, that the property is also `$null`.</span></span> <span data-ttu-id="e9a51-184">A propriedade `count` é a exceção a essa regra.</span><span class="sxs-lookup"><span data-stu-id="e9a51-184">The `count` property is the exception to this rule.</span></span>

```powershell
PS> $value = $null
PS> $value.count
0
```

<span data-ttu-id="e9a51-185">Quando você tem um valor `$null`, então o `count` é `0`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-185">When you have a `$null` value, then the `count` is `0`.</span></span> <span data-ttu-id="e9a51-186">Essa propriedade especial é adicionada pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9a51-186">This special property is added by PowerShell.</span></span>

### <a name="pscustomobject-count"></a><span data-ttu-id="e9a51-187">[PSCustomObject] Count</span><span class="sxs-lookup"><span data-stu-id="e9a51-187">[PSCustomObject] Count</span></span>

<span data-ttu-id="e9a51-188">Quase todos os objetos do PowerShell têm essa propriedade Count.</span><span class="sxs-lookup"><span data-stu-id="e9a51-188">Almost all objects in PowerShell have that count property.</span></span> <span data-ttu-id="e9a51-189">Uma exceção importante é o `[PSCustomObject]`, no Windows PowerShell 5.1 (isso é corrigido no PowerShell 6.0).</span><span class="sxs-lookup"><span data-stu-id="e9a51-189">One important exception is the `[PSCustomObject]` in Windows PowerShell 5.1 (This is fixed in PowerShell 6.0).</span></span> <span data-ttu-id="e9a51-190">Ele não tem a propriedade Count, então você receberá o valor `$null` se tentar usá-la.</span><span class="sxs-lookup"><span data-stu-id="e9a51-190">It doesn't have a count property so you get a `$null` value if you try to use it.</span></span> <span data-ttu-id="e9a51-191">Eu chamo a atenção para isso aqui a fim de que você não tente usar `.Count` em vez de uma verificação `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-191">I call this out here so that you don't try to use `.Count` instead of a `$null` check.</span></span>

<span data-ttu-id="e9a51-192">A execução deste exemplo no Windows PowerShell 5.1 e no PowerShell 6.0 vai gerar resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="e9a51-192">Running this example on Windows PowerShell 5.1 and PowerShell 6.0 gives you different results.</span></span>

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a><span data-ttu-id="e9a51-193">Nulo vazio</span><span class="sxs-lookup"><span data-stu-id="e9a51-193">Empty null</span></span>

<span data-ttu-id="e9a51-194">Há um tipo especial de `$null` que funciona de maneira diferente dos demais.</span><span class="sxs-lookup"><span data-stu-id="e9a51-194">There is one special type of `$null` that acts differently than the others.</span></span> <span data-ttu-id="e9a51-195">Vou chamá-lo de `$null` vazio, mas, na verdade, trata-se de um [System.Management.Automation.Internal.AutomationNull][].</span><span class="sxs-lookup"><span data-stu-id="e9a51-195">I am going to call it the empty `$null` but it's really a [System.Management.Automation.Internal.AutomationNull][].</span></span> <span data-ttu-id="e9a51-196">Esse `$null` vazio é o que você recebe como resultado de uma função ou bloco de script que não retorna nada (um resultado nulo).</span><span class="sxs-lookup"><span data-stu-id="e9a51-196">This empty `$null` is the one you get as the result of a function or script block that returns nothing (a void result).</span></span>

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

<span data-ttu-id="e9a51-197">Se você o comparar com `$null`, receberá o valor `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-197">If you compare it with `$null`, you get a `$null` value.</span></span> <span data-ttu-id="e9a51-198">Quando usado em uma avaliação em que um valor seja obrigatório, o valor será sempre `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-198">When used in an evaluation where a value is required, the value is always `$null`.</span></span> <span data-ttu-id="e9a51-199">Mas se você o colocar dentro de uma matriz, ele será tratado da mesma forma que uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="e9a51-199">But if you place it inside an array, it's treated the same as an empty array.</span></span>

```powershell
PS> $containempty = @( @() )
PS> $containnothing = @($nothing)
PS> $containnull = @($null)

PS> $containempty.count
0
PS> $containnothing.count
0
PS> $containnull.count
1
```

<span data-ttu-id="e9a51-200">Você pode ter uma matriz que contém um valor `$null` e sua `count` será `1`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-200">You can have an array that contains one `$null` value and its `count` is `1`.</span></span> <span data-ttu-id="e9a51-201">Mas se você inserir um resultado vazio dentro de uma matriz, ele não será contado como um item.</span><span class="sxs-lookup"><span data-stu-id="e9a51-201">But if you place an empty result inside an array then it's not counted as an item.</span></span> <span data-ttu-id="e9a51-202">A contagem será `0`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-202">The count is `0`.</span></span>

<span data-ttu-id="e9a51-203">Se você tratar o `$null` vazio como uma coleção, ela estará vazia.</span><span class="sxs-lookup"><span data-stu-id="e9a51-203">If you treat the empty `$null` like a collection, then it's empty.</span></span>

### <a name="pipeline"></a><span data-ttu-id="e9a51-204">Pipeline</span><span class="sxs-lookup"><span data-stu-id="e9a51-204">Pipeline</span></span>

<span data-ttu-id="e9a51-205">O principal local em que você vê a diferença é ao usar o pipeline.</span><span class="sxs-lookup"><span data-stu-id="e9a51-205">The primary place you see the difference is when using the pipeline.</span></span> <span data-ttu-id="e9a51-206">É possível armazenar em pipe um valor `$null`, mas não um valor `$null` vazio.</span><span class="sxs-lookup"><span data-stu-id="e9a51-206">You can pipe a `$null` value but not an empty `$null` value.</span></span>

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

<span data-ttu-id="e9a51-207">Dependendo do seu código, você deve considerar o `$null` em sua lógica.</span><span class="sxs-lookup"><span data-stu-id="e9a51-207">Depending on your code, you should account for the `$null` in your logic.</span></span>

<span data-ttu-id="e9a51-208">Verifique se corresponde a `$null`, primeiro</span><span class="sxs-lookup"><span data-stu-id="e9a51-208">Either check for `$null` first</span></span>

- <span data-ttu-id="e9a51-209">Filtrar nulo no pipeline (`... | Where {$null -ne $_} | ...`)</span><span class="sxs-lookup"><span data-stu-id="e9a51-209">Filter out null on the pipeline (`... | Where {$null -ne $_} | ...`)</span></span>
- <span data-ttu-id="e9a51-210">Gerenciá-lo na função do pipeline</span><span class="sxs-lookup"><span data-stu-id="e9a51-210">Handle it in the pipeline function</span></span>

## <a name="foreach"></a><span data-ttu-id="e9a51-211">foreach</span><span class="sxs-lookup"><span data-stu-id="e9a51-211">foreach</span></span>

<span data-ttu-id="e9a51-212">Um dos meus recursos favoritos do `foreach` é que ele não enumera em uma coleção `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-212">One of my favorite features of `foreach` is that it doesn't enumerate over a `$null` collection.</span></span>

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

<span data-ttu-id="e9a51-213">Isso evita que eu precise verificar se a coleção corresponde a `$null` antes de enumerá-la.</span><span class="sxs-lookup"><span data-stu-id="e9a51-213">This saves me from having to `$null` check the collection before I enumerate it.</span></span> <span data-ttu-id="e9a51-214">Se você tiver uma coleção de valores de `$null`, o `$node` ainda poderá ser `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-214">If you have a collection of `$null` values, the `$node` can still be `$null`.</span></span>

<span data-ttu-id="e9a51-215">O foreach começou a funcionar dessa forma no PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e9a51-215">The foreach started working this way with PowerShell 3.0.</span></span> <span data-ttu-id="e9a51-216">Se você estiver em uma versão mais antiga, então não será assim.</span><span class="sxs-lookup"><span data-stu-id="e9a51-216">If you happen to be on an older version, then this is not the case.</span></span> <span data-ttu-id="e9a51-217">Essa é uma das alterações importantes a serem observadas ao realizar a portabilidade do código para a compatibilidade com a versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="e9a51-217">This is one of the important changes to be aware of when back-porting code for 2.0 compatibility.</span></span>

## <a name="value-types"></a><span data-ttu-id="e9a51-218">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="e9a51-218">Value types</span></span>

<span data-ttu-id="e9a51-219">Tecnicamente, apenas tipos de referência podem ser `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-219">Technically, only reference types can be `$null`.</span></span> <span data-ttu-id="e9a51-220">Mas o PowerShell é muito generosa e permite que variáveis sejam de qualquer tipo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-220">But PowerShell is very generous and allows for variables to be any type.</span></span> <span data-ttu-id="e9a51-221">Se você decidir forçar a conversão de um tipo de valor, ele não poderá ser `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-221">If you decide to strongly type a value type, it cannot be `$null`.</span></span>
<span data-ttu-id="e9a51-222">O PowerShell converte `$null` em um valor padrão para muitos tipos.</span><span class="sxs-lookup"><span data-stu-id="e9a51-222">PowerShell converts `$null` to a default value for many types.</span></span>

```powershell
PS> [int]$number = $null
PS> $number
0

PS> [bool]$boolean = $null
PS> $boolean
False

PS> [string]$string = $null
PS> $string -eq ''
True
```

<span data-ttu-id="e9a51-223">Mas há alguns tipos que não têm uma conversão válida do `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-223">There are some types that do not have a valid conversion from `$null`.</span></span> <span data-ttu-id="e9a51-224">Esses tipos geram um erro de `Cannot convert null to type`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-224">These types generate a `Cannot convert null to type` error.</span></span>

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a><span data-ttu-id="e9a51-225">Parâmetros de função</span><span class="sxs-lookup"><span data-stu-id="e9a51-225">Function parameters</span></span>

<span data-ttu-id="e9a51-226">Forçar a conversão de valores em parâmetros de função é algo muito comum.</span><span class="sxs-lookup"><span data-stu-id="e9a51-226">Using a strongly typed values in function parameters is very common.</span></span> <span data-ttu-id="e9a51-227">Em geral, aprenderemos a definir os tipos dos parâmetros, mesmo se estivermos acostumados a não definir os tipos das outras variáveis do script.</span><span class="sxs-lookup"><span data-stu-id="e9a51-227">We generally learn to define the types of our parameters even if we tend not to define the types of other variables in our scripts.</span></span> <span data-ttu-id="e9a51-228">Talvez você já tenha algumas variáveis com a conversão de tipo forçada em suas funções e sequer tenha percebido.</span><span class="sxs-lookup"><span data-stu-id="e9a51-228">You may already have some strongly typed variables in your functions and not even realize it.</span></span>

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

<span data-ttu-id="e9a51-229">Assim que você definir o tipo do parâmetro como `string`, o valor nunca mais poderá ser `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-229">As soon as you set the type of the parameter as a `string`, the value can never be `$null`.</span></span> <span data-ttu-id="e9a51-230">É comum verificar se um valor é `$null` para ver se o usuário forneceu algum valor ou não.</span><span class="sxs-lookup"><span data-stu-id="e9a51-230">It's common to check if a value is `$null` to see if the user provided a value or not.</span></span>

```powershell
if ( $null -ne $Value ){...}
```

<span data-ttu-id="e9a51-231">`$Value` é uma cadeia de caracteres `''` vazia quando nenhum valor é fornecido.</span><span class="sxs-lookup"><span data-stu-id="e9a51-231">`$Value` is an empty string `''` when no value is provided.</span></span> <span data-ttu-id="e9a51-232">Em vez disso, use a variável automática `$PSBoundParameters.Value`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-232">Use the automatic variable `$PSBoundParameters.Value` instead.</span></span>

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

<span data-ttu-id="e9a51-233">`$PSBoundParameters` contém apenas os parâmetros que foram especificados quando a função foi chamada.</span><span class="sxs-lookup"><span data-stu-id="e9a51-233">`$PSBoundParameters` only contains the parameters that were specified when the function was called.</span></span>
<span data-ttu-id="e9a51-234">Você também pode usar o método `ContainsKey` para verificar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="e9a51-234">You can also use the `ContainsKey` method to check for the property.</span></span>

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a><span data-ttu-id="e9a51-235">IsNotNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="e9a51-235">IsNotNullOrEmpty</span></span>

<span data-ttu-id="e9a51-236">Se o valor for uma cadeia de caracteres, você poderá usar uma função de cadeia de caracteres estática para verificar se o valor é `$null` ou uma cadeia de caracteres vazia ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-236">If the value is a string, you can use a static string function to check if the value is `$null` or an empty string at the same time.</span></span>

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

<span data-ttu-id="e9a51-237">Eu me pego usando isso com frequência quando sei que o tipo de valor deve ser uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e9a51-237">I find myself using this often when I know the value type should be a string.</span></span>

## <a name="when-i-null-check"></a><span data-ttu-id="e9a51-238">Quando eu verifico se corresponde a $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-238">When I $null check</span></span>

<span data-ttu-id="e9a51-239">Eu sou um criador de scripts conservador.</span><span class="sxs-lookup"><span data-stu-id="e9a51-239">I am a defensive scripter.</span></span> <span data-ttu-id="e9a51-240">Sempre que eu chamo uma função e atribuo seu resultado a uma variável, eu a verifico se corresponde a `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-240">Anytime I call a function and assign it to a variable, I check it for `$null`.</span></span>

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

<span data-ttu-id="e9a51-241">Eu prefiro usar `if` ou `foreach` do que `try/catch`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-241">I much prefer using `if` or `foreach` over using `try/catch`.</span></span> <span data-ttu-id="e9a51-242">Não me entenda mal, eu também uso `try/catch` com frequência.</span><span class="sxs-lookup"><span data-stu-id="e9a51-242">Don't get me wrong, I still use `try/catch` a lot.</span></span> <span data-ttu-id="e9a51-243">Mas se eu posso testar uma condição de erro ou um conjunto de resultados vazio, posso permitir que meu tratamento de exceção seja para exceções verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="e9a51-243">But if I can test for an error condition or an empty set of results, I can allow my exception handling be for true exceptions.</span></span>

<span data-ttu-id="e9a51-244">Também costumo verificar se corresponde a `$null` antes de indexar um valor ou chamar métodos em um objeto.</span><span class="sxs-lookup"><span data-stu-id="e9a51-244">I also tend to check for `$null` before I index into a value or call methods on an object.</span></span> <span data-ttu-id="e9a51-245">Essas duas ações falham em caso de objeto `$null`, portanto, acho importante validá-las primeiro.</span><span class="sxs-lookup"><span data-stu-id="e9a51-245">These two actions fail for a `$null` object so I find it important to validate them first.</span></span> <span data-ttu-id="e9a51-246">Já abordei esses cenários anteriormente nesta postagem.</span><span class="sxs-lookup"><span data-stu-id="e9a51-246">I already covered those scenarios earlier in this post.</span></span>

### <a name="no-results-scenario"></a><span data-ttu-id="e9a51-247">Cenário sem resultados</span><span class="sxs-lookup"><span data-stu-id="e9a51-247">No results scenario</span></span>

<span data-ttu-id="e9a51-248">É importante saber que funções e comandos diferentes gerenciam o cenário sem resultados de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="e9a51-248">It's important to know that different functions and commands handle the no results scenario differently.</span></span> <span data-ttu-id="e9a51-249">Muitos comandos do PowerShell retornam o `$null` vazio e um erro no fluxo de erros.</span><span class="sxs-lookup"><span data-stu-id="e9a51-249">Many PowerShell commands return the empty `$null` and an error in the error stream.</span></span> <span data-ttu-id="e9a51-250">Mas outros geram exceções ou fornecem um objeto de status.</span><span class="sxs-lookup"><span data-stu-id="e9a51-250">But others throw exceptions or give you a status object.</span></span> <span data-ttu-id="e9a51-251">É sua responsabilidade saber como os comandos que você usa gerenciam os cenários sem resultados e os cenários de erro.</span><span class="sxs-lookup"><span data-stu-id="e9a51-251">It's still up to you to know how the commands you use deal with the no results and error scenarios.</span></span>

## <a name="initializing-to-null"></a><span data-ttu-id="e9a51-252">Inicializando com $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-252">Initializing to $null</span></span>

<span data-ttu-id="e9a51-253">Um hábito que eu adquiri foi o de inicializar todas as minhas variáveis antes de usá-las.</span><span class="sxs-lookup"><span data-stu-id="e9a51-253">One habit that I have picked up is initializing all my variables before I use them.</span></span> <span data-ttu-id="e9a51-254">Isso é algo obrigatório em outras linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="e9a51-254">You are required to do this in other languages.</span></span> <span data-ttu-id="e9a51-255">Na parte superior da função ou sempre no início do loop de um foreach, eu defino todos os valores que estou usando.</span><span class="sxs-lookup"><span data-stu-id="e9a51-255">At the top of my function or as I enter a foreach loop, I define all the values that I'm using.</span></span>

<span data-ttu-id="e9a51-256">Aqui está um cenário que desejo examinar mais de perto contigo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-256">Here is a scenario that I want you to take a close look at.</span></span> <span data-ttu-id="e9a51-257">É um exemplo de bug que já precisei enfrentar anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e9a51-257">It's an example of a bug I had to chase down before.</span></span>

```powershell
function Do-Something
{
    foreach ( $node in 1..6 )
    {
        try
        {
            $result = Get-Something -ID $node
        }
        catch
        {
            Write-Verbose "[$result] not valid"
        }

        if ( $null -ne $result )
        {
            Update-Something $result
        }
    }
}
```

<span data-ttu-id="e9a51-258">A expectativa aqui é que `Get-Something` retorne um resultado ou um `$null` vazio.</span><span class="sxs-lookup"><span data-stu-id="e9a51-258">The expectation here is that `Get-Something` returns either a result or an empty `$null`.</span></span> <span data-ttu-id="e9a51-259">Se houver um erro, nós o registramos em um log.</span><span class="sxs-lookup"><span data-stu-id="e9a51-259">If there is an error, we log it.</span></span> <span data-ttu-id="e9a51-260">Em seguida, verificamos se recebemos um resultado válido antes de processá-lo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-260">Then we check to make sure we got a valid result before processing it.</span></span>

<span data-ttu-id="e9a51-261">O bug que se oculta nesse código é quando `Get-Something` gera uma exceção e não atribui um valor a `$result`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-261">The bug hiding in this code is when `Get-Something` throws an exception and doesn't assign a value to `$result`.</span></span> <span data-ttu-id="e9a51-262">Ela falha antes da atribuição, portanto, nem chegamos a atribuir `$null` à variável `$result`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-262">It fails before the assignment so we don't even assign `$null` to the `$result` variable.</span></span> <span data-ttu-id="e9a51-263">`$result` ainda contém a `$result` anterior válida, obtida em outras iterações.</span><span class="sxs-lookup"><span data-stu-id="e9a51-263">`$result` still contains the previous valid `$result` from other iterations.</span></span>
<span data-ttu-id="e9a51-264">`Update-Something` vai executar várias vezes no mesmo objeto neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-264">`Update-Something` to execute multiple times on the same object in this example.</span></span>

<span data-ttu-id="e9a51-265">Passei a definir `$result` como `$null` dentro do loop do foreach antes de usá-la para contornar esse problema.</span><span class="sxs-lookup"><span data-stu-id="e9a51-265">I set `$result` to `$null` right inside the foreach loop before I use it to mitigate this issue.</span></span>

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a><span data-ttu-id="e9a51-266">Problemas de escopo</span><span class="sxs-lookup"><span data-stu-id="e9a51-266">Scope issues</span></span>

<span data-ttu-id="e9a51-267">Isso também ajuda a atenuar problemas de escopo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-267">This also helps mitigate scoping issues.</span></span> <span data-ttu-id="e9a51-268">Nesse exemplo, atribuímos valores a `$result` repetidamente em um loop.</span><span class="sxs-lookup"><span data-stu-id="e9a51-268">In that example, we assign values to `$result` over and over in a loop.</span></span> <span data-ttu-id="e9a51-269">Mas como o PowerShell permite que valores variáveis de fora da função sejam acessados no escopo da função atual, inicializá-los dentro da função atenua os bugs que podem ser introduzidos dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="e9a51-269">But because PowerShell allows variable values from outside the function to bleed into the scope of the current function, initializing them inside your function mitigates bugs that can be introduced that way.</span></span>

<span data-ttu-id="e9a51-270">Uma variável não inicializada em sua função não será `$null` se ela estiver definida como um valor em um escopo superior.</span><span class="sxs-lookup"><span data-stu-id="e9a51-270">An uninitialized variable in your function is not `$null` if it's set to a value in a parent scope.</span></span>
<span data-ttu-id="e9a51-271">O escopo superior pode ser outra função que chama sua função e usa os mesmos nomes de variáveis, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-271">The parent scope could be another function that calls your function and uses the same variable names.</span></span>

<span data-ttu-id="e9a51-272">Se eu pegar o mesmo exemplo de `Do-something` e remover o loop, acabarei com algo parecido com este exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9a51-272">If I take that same `Do-something` example and remove the loop, I would end up with something that looks like this example:</span></span>

```powershell
function Invoke-Something
{
    $result = 'ParentScope'
    Do-Something
}

function Do-Something
{
    try
    {
        $result = Get-Something -ID $node
    }
    catch
    {
        Write-Verbose "[$result] not valid"
    }

    if ( $null -ne $result )
    {
        Update-Something $result
    }
}
```

<span data-ttu-id="e9a51-273">Se a chamada à `Get-Something` gerar uma exceção, então minha verificação se corresponde a `$null` encontrará a `$result` de `Invoke-Something`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-273">If the call to `Get-Something` throws an exception, then my `$null` check finds the `$result` from `Invoke-Something`.</span></span> <span data-ttu-id="e9a51-274">A inicialização do valor dentro da sua função atenua esse problema.</span><span class="sxs-lookup"><span data-stu-id="e9a51-274">Initializing the value inside your function mitigates this issue.</span></span>

<span data-ttu-id="e9a51-275">Dar nomes às variáveis é algo difícil, de modo que é comum um autor usar os mesmos nomes de variáveis em diferentes funções.</span><span class="sxs-lookup"><span data-stu-id="e9a51-275">Naming variables is hard and it's common for an author to use the same variable names in multiple functions.</span></span> <span data-ttu-id="e9a51-276">Eu, por exemplo, uso `$node`, `$result` e `$data` o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-276">I know I use `$node`,`$result`,`$data` all the time.</span></span> <span data-ttu-id="e9a51-277">Portanto, é muito comum que valores de escopos diferentes acabem aparecendo em locais onde não deveriam.</span><span class="sxs-lookup"><span data-stu-id="e9a51-277">So it would be very easy for values from different scopes to show up in places where they should not be.</span></span>

## <a name="redirect-output-to-null"></a><span data-ttu-id="e9a51-278">Redirecionar a saída para $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-278">Redirect output to $null</span></span>

<span data-ttu-id="e9a51-279">Tenho falado sobre valores `$null` ao longo de todo este artigo, mas o tópico não estaria completo se eu não mencionasse o redirecionamento da saída para `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-279">I have been talking about `$null` values for this entire article but the topic is not complete if I didn't mention redirecting output to `$null`.</span></span> <span data-ttu-id="e9a51-280">Há ocasiões em que determinados comandos geram informações ou objetos que você deseja suprimir.</span><span class="sxs-lookup"><span data-stu-id="e9a51-280">There are times when you have commands that output information or objects that you want to suppress.</span></span> <span data-ttu-id="e9a51-281">O redirecionamento da saída para `$null` faz exatamente isso.</span><span class="sxs-lookup"><span data-stu-id="e9a51-281">Redirecting output to `$null` does that.</span></span>

### <a name="out-null"></a><span data-ttu-id="e9a51-282">Out-Null</span><span class="sxs-lookup"><span data-stu-id="e9a51-282">Out-Null</span></span>

<span data-ttu-id="e9a51-283">O comando Out-Null é a maneira interna de redirecionar os dados do pipeline para `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-283">The Out-Null command is the built-in way to redirect pipeline data to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a><span data-ttu-id="e9a51-284">Atribuir $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-284">Assign to $null</span></span>

<span data-ttu-id="e9a51-285">Você pode atribuir `$null` aos resultados de um comando para alcançar o mesmo efeito do uso de `Out-Null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-285">You can assign the results of a command to `$null` for the same effect as using `Out-Null`.</span></span>

```powershell
$null = New-Item -Type Directory -Path $path
```

<span data-ttu-id="e9a51-286">Como `$null` é um valor constante, você jamais poderá substituí-lo.</span><span class="sxs-lookup"><span data-stu-id="e9a51-286">Because `$null` is a constant value, you can never overwrite it.</span></span> <span data-ttu-id="e9a51-287">Não gosto da aparência dele em meus códigos, mas geralmente é executado mais rápido do que `Out-Null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-287">I don't like the way it looks in my code but it often performs faster than `Out-Null`.</span></span>

### <a name="redirect-to-null"></a><span data-ttu-id="e9a51-288">Redirecionar para $null</span><span class="sxs-lookup"><span data-stu-id="e9a51-288">Redirect to $null</span></span>

<span data-ttu-id="e9a51-289">Você também pode usar o operador de redirecionamento para enviar a saída para `$null`.</span><span class="sxs-lookup"><span data-stu-id="e9a51-289">You can also use the redirection operator to send output to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path > $null
```

<span data-ttu-id="e9a51-290">Se você estiver lidando com executáveis de linha de comando que geram saída em diferentes fluxos.</span><span class="sxs-lookup"><span data-stu-id="e9a51-290">If you're dealing with command-line executables that output on the different streams.</span></span> <span data-ttu-id="e9a51-291">Você poderá redirecionar todos os fluxos de saída para `$null` da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e9a51-291">You can redirect all output streams to `$null` like this:</span></span>

```powershell
git status *> $null
```

## <a name="summary"></a><span data-ttu-id="e9a51-292">Resumo</span><span class="sxs-lookup"><span data-stu-id="e9a51-292">Summary</span></span>

<span data-ttu-id="e9a51-293">Eu abordei muitos aspectos sobre este assunto e estou ciente de que este artigo ficou mais fragmentado do que a maior parte dos meus estudos de aprofundamento.</span><span class="sxs-lookup"><span data-stu-id="e9a51-293">I covered a lot of ground on this one and I know this article is more fragmented than most of my deep dives.</span></span> <span data-ttu-id="e9a51-294">Isso ocorre porque valores `$null` podem aparecer em vários locais diferentes no PowerShell e todas as nuances são específicas ao local em que você os encontra.</span><span class="sxs-lookup"><span data-stu-id="e9a51-294">That is because `$null` values can pop up in many different places in PowerShell and all the nuances are specific to where you find it.</span></span> <span data-ttu-id="e9a51-295">Espero que você saia com uma compreensão melhor do `$null` e com uma boa noção dos cenários mais obscuros que pode encontrar pela frente.</span><span class="sxs-lookup"><span data-stu-id="e9a51-295">I hope you walk away from this with a better understanding of `$null` and an awareness of the more obscure scenarios you may run into.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[excelente postagem]: https://blog.iisreset.me/schrodingers-argumentlist
[good post]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
