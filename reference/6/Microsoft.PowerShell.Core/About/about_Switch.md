---
description: Explica como usar uma opção para manipular várias `If` instruções.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 2b39f8e0ad49c9e5f6cab06eea34e8f27b37186b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195615"
---
# <a name="about-switch"></a><span data-ttu-id="dd571-104">Sobre o comutador</span><span class="sxs-lookup"><span data-stu-id="dd571-104">About Switch</span></span>

## <a name="short-description"></a><span data-ttu-id="dd571-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="dd571-105">Short description</span></span>
<span data-ttu-id="dd571-106">Explica como usar uma opção para manipular várias `If` instruções.</span><span class="sxs-lookup"><span data-stu-id="dd571-106">Explains how to use a switch to handle multiple `If` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="dd571-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="dd571-107">Long description</span></span>

<span data-ttu-id="dd571-108">Para verificar uma condição em um script ou uma função, use uma `If` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-108">To check a condition in a script or function, use an `If` statement.</span></span> <span data-ttu-id="dd571-109">A `If` instrução pode verificar muitos tipos de condições, incluindo o valor de variáveis e as propriedades de objetos.</span><span class="sxs-lookup"><span data-stu-id="dd571-109">The `If` statement can check many types of conditions, including the value of variables and the properties of objects.</span></span>

<span data-ttu-id="dd571-110">Para verificar várias condições, use uma `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-110">To check multiple conditions, use a `Switch` statement.</span></span> <span data-ttu-id="dd571-111">A `Switch` instrução é equivalente a uma série de `If` instruções, mas é mais simples.</span><span class="sxs-lookup"><span data-stu-id="dd571-111">The `Switch` statement is equivalent to a series of `If` statements, but it is simpler.</span></span> <span data-ttu-id="dd571-112">A `Switch` instrução lista cada condição e uma ação opcional.</span><span class="sxs-lookup"><span data-stu-id="dd571-112">The `Switch` statement lists each condition and an optional action.</span></span> <span data-ttu-id="dd571-113">Se uma condição for obtida, a ação será executada.</span><span class="sxs-lookup"><span data-stu-id="dd571-113">If a condition obtains, the action is performed.</span></span>

<span data-ttu-id="dd571-114">A `Switch` instrução pode usar as `$_` `$switch` variáveis and automáticas.</span><span class="sxs-lookup"><span data-stu-id="dd571-114">The `Switch` statement can use the `$_` and `$switch` automatic variables.</span></span> <span data-ttu-id="dd571-115">Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="dd571-115">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="dd571-116">Uma `Switch` instrução básica tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="dd571-116">A basic `Switch` statement has the following format:</span></span>

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

<span data-ttu-id="dd571-117">Por exemplo, a instrução a seguir `Switch` compara o valor de teste, 3, para cada uma das condições.</span><span class="sxs-lookup"><span data-stu-id="dd571-117">For example, the following `Switch` statement compares the test value, 3, to each of the conditions.</span></span> <span data-ttu-id="dd571-118">Quando o valor de teste corresponde à condição, a ação é executada.</span><span class="sxs-lookup"><span data-stu-id="dd571-118">When the test value matches the condition, the action is performed.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

<span data-ttu-id="dd571-119">Neste exemplo simples, o valor é comparado a cada condição na lista, mesmo que haja uma correspondência para o valor 3.</span><span class="sxs-lookup"><span data-stu-id="dd571-119">In this simple example, the value is compared to each condition in the list, even though there is a match for the value 3.</span></span> <span data-ttu-id="dd571-120">A instrução a seguir `Switch` tem duas condições para um valor de 3.</span><span class="sxs-lookup"><span data-stu-id="dd571-120">The following `Switch` statement has two conditions for a value of 3.</span></span> <span data-ttu-id="dd571-121">Ele demonstra que, por padrão, todas as condições são testadas.</span><span class="sxs-lookup"><span data-stu-id="dd571-121">It demonstrates that, by default, all conditions are tested.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

<span data-ttu-id="dd571-122">Para direcionar o `Switch` para parar de comparar após uma correspondência, use a `Break` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-122">To direct the `Switch` to stop comparing after a match, use the `Break` statement.</span></span> <span data-ttu-id="dd571-123">A `Break` instrução encerra a `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-123">The `Break` statement terminates the `Switch` statement.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

<span data-ttu-id="dd571-124">Se o valor de teste for uma coleção, como uma matriz, cada item na coleção será avaliado na ordem em que aparece.</span><span class="sxs-lookup"><span data-stu-id="dd571-124">If the test value is a collection, such as an array, each item in the collection is evaluated in the order in which it appears.</span></span> <span data-ttu-id="dd571-125">Os exemplos a seguir avaliam 4 e depois 2.</span><span class="sxs-lookup"><span data-stu-id="dd571-125">The following examples evaluates 4 and then 2.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

<span data-ttu-id="dd571-126">Todas as `Break` instruções se aplicam à coleção, não a cada valor, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd571-126">Any `Break` statements apply to the collection, not to each value, as shown in the following example.</span></span> <span data-ttu-id="dd571-127">A `Switch` instrução é encerrada pela `Break` instrução na condição do valor 4.</span><span class="sxs-lookup"><span data-stu-id="dd571-127">The `Switch` statement is terminated by the `Break` statement in the condition of value 4.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a><span data-ttu-id="dd571-128">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd571-128">Syntax</span></span>

<span data-ttu-id="dd571-129">A `Switch` sintaxe de instrução completa é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd571-129">The complete `Switch` statement syntax is as follows:</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="dd571-130">ou</span><span class="sxs-lookup"><span data-stu-id="dd571-130">or</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="dd571-131">Se nenhum parâmetro for usado, `Switch` o terá o mesmo que usar o parâmetro **exato** .</span><span class="sxs-lookup"><span data-stu-id="dd571-131">If no parameters are used, `Switch` behaves the same as using the **Exact** parameter.</span></span> <span data-ttu-id="dd571-132">Ele executa uma correspondência que não diferencia maiúsculas de minúsculas para o valor.</span><span class="sxs-lookup"><span data-stu-id="dd571-132">It performs a case-insensitive match for the value.</span></span> <span data-ttu-id="dd571-133">Se o valor for uma coleção, cada elemento será avaliado na ordem em que ele aparece.</span><span class="sxs-lookup"><span data-stu-id="dd571-133">If the value is a collection, each element is evaluated in the order in which it appears.</span></span>

<span data-ttu-id="dd571-134">A `Switch` instrução deve incluir pelo menos uma instrução de condição.</span><span class="sxs-lookup"><span data-stu-id="dd571-134">The `Switch` statement must include at least one condition statement.</span></span>

<span data-ttu-id="dd571-135">A `Default` cláusula é disparada quando o valor não corresponde a nenhuma das condições.</span><span class="sxs-lookup"><span data-stu-id="dd571-135">The `Default` clause is triggered when the value does not match any of the conditions.</span></span> <span data-ttu-id="dd571-136">É equivalente a uma `Else` cláusula em uma `If` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-136">It is equivalent to an `Else` clause in an `If` statement.</span></span> <span data-ttu-id="dd571-137">Somente uma `Default` cláusula é permitida em cada `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-137">Only one `Default` clause is permitted in each `Switch` statement.</span></span>

<span data-ttu-id="dd571-138">`Switch` tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="dd571-138">`Switch` has the following parameters:</span></span>

- <span data-ttu-id="dd571-139">**Curinga** – indica que a condição é uma cadeia de caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="dd571-139">**Wildcard** - Indicates that the condition is a wildcard string.</span></span> <span data-ttu-id="dd571-140">Se a cláusula match não for uma cadeia de caracteres, o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="dd571-140">If the match clause is not a string, the parameter is ignored.</span></span> <span data-ttu-id="dd571-141">A comparação não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd571-141">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="dd571-142">**Exact** -indica que a cláusula Match, se for uma cadeia de caracteres, deve corresponder exatamente.</span><span class="sxs-lookup"><span data-stu-id="dd571-142">**Exact** - Indicates that the match clause, if it is a string, must match exactly.</span></span> <span data-ttu-id="dd571-143">Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="dd571-143">If the match clause is not a string, this parameter is ignored.</span></span> <span data-ttu-id="dd571-144">A comparação não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd571-144">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="dd571-145">**CaseSensitive** -executa uma correspondência que diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd571-145">**CaseSensitive** - Performs a case-sensitive match.</span></span> <span data-ttu-id="dd571-146">Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="dd571-146">If the match clause is not a string, this parameter is ignored.</span></span>
- <span data-ttu-id="dd571-147">**Arquivo** -obtém entrada de um arquivo em vez de uma instrução Value.</span><span class="sxs-lookup"><span data-stu-id="dd571-147">**File** - Takes input from a file rather than a value statement.</span></span> <span data-ttu-id="dd571-148">Se vários parâmetros de **arquivo** forem incluídos, somente o último será usado.</span><span class="sxs-lookup"><span data-stu-id="dd571-148">If multiple **File** parameters are included, only the last one is used.</span></span> <span data-ttu-id="dd571-149">Cada linha do arquivo é lida e avaliada pela `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-149">Each line of the file is read and evaluated by the `Switch` statement.</span></span> <span data-ttu-id="dd571-150">A comparação não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd571-150">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="dd571-151">**Regex** -executa a correspondência de expressão regular do valor para a condição.</span><span class="sxs-lookup"><span data-stu-id="dd571-151">**Regex** - Performs regular expression matching of the value to the condition.</span></span> <span data-ttu-id="dd571-152">Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="dd571-152">If the match clause is not a string, this parameter is ignored.</span></span>
  <span data-ttu-id="dd571-153">A comparação não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd571-153">The comparison is case-insensitive.</span></span> <span data-ttu-id="dd571-154">A `$matches` variável automática está disponível para uso dentro do bloco de instrução correspondente.</span><span class="sxs-lookup"><span data-stu-id="dd571-154">The `$matches` automatic variable is available for use within the matching statement block.</span></span>

> [!NOTE]
> <span data-ttu-id="dd571-155">Ao especificar valores conflitantes, como **Regex** e **wildcard** , o último parâmetro especificado tem precedência e todos os parâmetros conflitantes são ignorados.</span><span class="sxs-lookup"><span data-stu-id="dd571-155">When specifying conflicting values, like **Regex** and **Wildcard** , the last parameter specified takes precedence, and all conflicting parameters are ignored.</span></span> <span data-ttu-id="dd571-156">Também são permitidas várias instâncias de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="dd571-156">Multiple instances of parameters are also permitted.</span></span> <span data-ttu-id="dd571-157">No entanto, apenas o último parâmetro usado é efetivo.</span><span class="sxs-lookup"><span data-stu-id="dd571-157">However, only the last parameter used is effective.</span></span>

<span data-ttu-id="dd571-158">Neste exemplo, um objeto que não é uma cadeia de caracteres ou dados numéricos é passado para o `Switch` .</span><span class="sxs-lookup"><span data-stu-id="dd571-158">In this example, an object that's not a string or numerical data is passed to the `Switch`.</span></span> <span data-ttu-id="dd571-159">O `Switch` executa uma coerção de cadeia de caracteres no objeto e avalia o resultado.</span><span class="sxs-lookup"><span data-stu-id="dd571-159">The `Switch` performs a string coercion on the object and evaluates the outcome.</span></span>

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

<span data-ttu-id="dd571-160">Neste exemplo, não há nenhum caso correspondente, portanto, não há nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="dd571-160">In this example, there is no matching case so there is no output.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

<span data-ttu-id="dd571-161">Ao adicionar a `Default` cláusula, você pode executar uma ação quando nenhuma outra condição for realizada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="dd571-161">By adding the `Default` clause, you can perform an action when no other conditions succeed.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

<span data-ttu-id="dd571-162">Para a palavra "quatorze" corresponder a um caso, você deve usar `-Wildcard` o `-Regex` parâmetro ou.</span><span class="sxs-lookup"><span data-stu-id="dd571-162">For the word "fourteen" to match a case you must use the `-Wildcard` or `-Regex` parameter.</span></span>

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

<span data-ttu-id="dd571-163">O exemplo a seguir usa o `-Regex` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dd571-163">The following example uses the `-Regex` parameter.</span></span>

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

<span data-ttu-id="dd571-164">Uma condição de instrução switch pode ser:</span><span class="sxs-lookup"><span data-stu-id="dd571-164">A Switch statement condition may be either:</span></span>

- <span data-ttu-id="dd571-165">Uma expressão cujo valor é comparado ao valor de entrada</span><span class="sxs-lookup"><span data-stu-id="dd571-165">An expression whose value is compared to the input value</span></span>
- <span data-ttu-id="dd571-166">Um bloco de script que deve retornar `$true` se uma condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="dd571-166">A script block which should return `$true` if a condition is met.</span></span>

<span data-ttu-id="dd571-167">A `$_` variável automática contém o valor passado para a instrução switch e está disponível para avaliação e uso dentro do escopo das instruções Condition.</span><span class="sxs-lookup"><span data-stu-id="dd571-167">The `$_` automatic variable contains the value passed to the switch statement and is available for evaluation and use within the scope of the condition statements.</span></span>

<span data-ttu-id="dd571-168">A ação para cada condição é independente das ações em outras condições.</span><span class="sxs-lookup"><span data-stu-id="dd571-168">The action for each condition is independent of the actions in other conditions.</span></span>

<span data-ttu-id="dd571-169">O exemplo a seguir demonstra o uso de blocos de script como `Switch` condições de instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-169">The following example demonstrates the use of script blocks as `Switch` statement conditions.</span></span>

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

<span data-ttu-id="dd571-170">Se o valor corresponder a várias condições, a ação para cada condição será executada.</span><span class="sxs-lookup"><span data-stu-id="dd571-170">If the value matches multiple conditions, the action for each condition is executed.</span></span> <span data-ttu-id="dd571-171">Para alterar esse comportamento, use as `Break` `Continue` palavras-chave ou.</span><span class="sxs-lookup"><span data-stu-id="dd571-171">To change this behavior, use the `Break` or `Continue` keywords.</span></span>

<span data-ttu-id="dd571-172">A `Break` palavra-chave interrompe o processamento e sai da `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="dd571-172">The `Break` keyword stops processing and exits the `Switch` statement.</span></span>

<span data-ttu-id="dd571-173">A `Continue` palavra-chave para o processamento do valor atual, mas continua processando quaisquer valores subsequentes.</span><span class="sxs-lookup"><span data-stu-id="dd571-173">The `Continue` keyword stops processing the current value, but continues processing any subsequent values.</span></span>

<span data-ttu-id="dd571-174">O exemplo a seguir processa uma matriz de números e exibe se eles são ímpares ou até mesmo.</span><span class="sxs-lookup"><span data-stu-id="dd571-174">The following example processes an array of numbers and displays if they are odd or even.</span></span> <span data-ttu-id="dd571-175">Números negativos são ignorados com a `Continue` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="dd571-175">Negative numbers are skipped with the `Continue` keyword.</span></span> <span data-ttu-id="dd571-176">Se um número não-numérico for encontrado, a execução será encerrada com a `Break` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="dd571-176">If a non-number is encountered, execution is terminated with the `Break` keyword.</span></span>

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a><span data-ttu-id="dd571-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="dd571-177">See also</span></span>

[<span data-ttu-id="dd571-178">about_Break</span><span class="sxs-lookup"><span data-stu-id="dd571-178">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="dd571-179">about_Continue</span><span class="sxs-lookup"><span data-stu-id="dd571-179">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="dd571-180">about_If</span><span class="sxs-lookup"><span data-stu-id="dd571-180">about_If</span></span>](about_If.md)

[<span data-ttu-id="dd571-181">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="dd571-181">about_Script_Blocks</span></span>](about_Script_Blocks.md)
