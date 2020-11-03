---
description: Descreve um comando de linguagem que você pode usar para executar instruções com base em um teste condicional.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 3/4/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 07037b73a5507bb0ef420ad39271be8832f7500b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195564"
---
# <a name="about-for"></a><span data-ttu-id="95c71-104">Sobre o para</span><span class="sxs-lookup"><span data-stu-id="95c71-104">About For</span></span>

## <a name="short-description"></a><span data-ttu-id="95c71-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="95c71-105">Short description</span></span>
<span data-ttu-id="95c71-106">Descreve um comando de linguagem que você pode usar para executar instruções com base em um teste condicional.</span><span class="sxs-lookup"><span data-stu-id="95c71-106">Describes a language command you can use to run statements based on a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="95c71-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="95c71-107">Long description</span></span>

<span data-ttu-id="95c71-108">A `For` instrução (também conhecida como `For` loop) é uma construção de linguagem que você pode usar para criar um loop que executa comandos em um bloco de comando enquanto uma condição especificada é avaliada como `$true` .</span><span class="sxs-lookup"><span data-stu-id="95c71-108">The `For` statement (also known as a `For` loop) is a language construct you can use to create a loop that runs commands in a command block while a specified condition evaluates to `$true`.</span></span>

<span data-ttu-id="95c71-109">Um uso típico do `For` loop é iterar uma matriz de valores e operar em um subconjunto desses valores.</span><span class="sxs-lookup"><span data-stu-id="95c71-109">A typical use of the `For` loop is to iterate an array of values and to operate on a subset of these values.</span></span> <span data-ttu-id="95c71-110">Na maioria dos casos, se você quiser iterar todos os valores em uma matriz, considere usar uma `Foreach` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-110">In most cases, if you want to iterate all the values in an array, consider using a `Foreach` statement.</span></span>

### <a name="syntax"></a><span data-ttu-id="95c71-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="95c71-111">Syntax</span></span>

<span data-ttu-id="95c71-112">O seguinte mostra a `For` sintaxe da instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-112">The following shows the `For` statement syntax.</span></span>

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

<span data-ttu-id="95c71-113">O espaço reservado de **inicialização** representa um ou mais comandos que são executados antes do início do loop.</span><span class="sxs-lookup"><span data-stu-id="95c71-113">The **Init** placeholder represents one or more commands that are run before the loop begins.</span></span> <span data-ttu-id="95c71-114">Normalmente, você usa a parte **init** da instrução para criar e inicializar uma variável com um valor inicial.</span><span class="sxs-lookup"><span data-stu-id="95c71-114">You typically use the **Init** portion of the statement to create and initialize a variable with a starting value.</span></span>

<span data-ttu-id="95c71-115">Essa variável será então a base para a condição a ser testada na próxima parte da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-115">This variable will then be the basis for the condition to be tested in the next portion of the `For` statement.</span></span>

<span data-ttu-id="95c71-116">O espaço reservado da **condição** representa a parte da `For` instrução que é resolvida para `$true` um `$false` valor ou **booliano** .</span><span class="sxs-lookup"><span data-stu-id="95c71-116">The **Condition** placeholder represents the portion of the `For` statement that resolves to a `$true` or `$false` **Boolean** value.</span></span> <span data-ttu-id="95c71-117">O PowerShell avalia a condição toda vez que o `For` loop é executado.</span><span class="sxs-lookup"><span data-stu-id="95c71-117">PowerShell evaluates the condition each time the `For` loop runs.</span></span> <span data-ttu-id="95c71-118">Se a instrução for `$true` , os comandos no bloco de comando serão executados e a instrução será avaliada novamente.</span><span class="sxs-lookup"><span data-stu-id="95c71-118">If the statement is `$true`, the commands in the command block run, and the statement is evaluated again.</span></span> <span data-ttu-id="95c71-119">Se a condição ainda for `$true` , os comandos na **lista de instruções** serão executados novamente.</span><span class="sxs-lookup"><span data-stu-id="95c71-119">If the condition is still `$true`, the commands in the **Statement list** run again.</span></span> <span data-ttu-id="95c71-120">O loop é repetido até que a condição se torne `$false` .</span><span class="sxs-lookup"><span data-stu-id="95c71-120">The loop is repeated until the condition becomes `$false`.</span></span>

<span data-ttu-id="95c71-121">O espaço reservado de **repetição** representa um ou mais comandos, separados por vírgulas, que são executados cada vez que o loop se repete.</span><span class="sxs-lookup"><span data-stu-id="95c71-121">The **Repeat** placeholder represents one or more commands, separated by commas, that are executed each time the loop repeats.</span></span> <span data-ttu-id="95c71-122">Normalmente, isso é usado para modificar uma variável que é testada dentro da parte da **condição** da instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-122">Typically, this is used to modify a variable that is tested inside the **Condition** part of the statement.</span></span>

<span data-ttu-id="95c71-123">O espaço reservado da **lista de instruções** representa um conjunto de um ou mais comandos que são executados cada vez que o loop é inserido ou repetido.</span><span class="sxs-lookup"><span data-stu-id="95c71-123">The **Statement list** placeholder represents a set of one or more commands that are run each time the loop is entered or repeated.</span></span> <span data-ttu-id="95c71-124">O conteúdo da **lista de instruções** está entre chaves.</span><span class="sxs-lookup"><span data-stu-id="95c71-124">The contents of the **Statement list** are surrounded by braces.</span></span>

### <a name="support-for-multiple-operations"></a><span data-ttu-id="95c71-125">Suporte para várias operações</span><span class="sxs-lookup"><span data-stu-id="95c71-125">Support for multiple operations</span></span>

<span data-ttu-id="95c71-126">As sintaxes a seguir têm suporte para várias operações de atribuição na instrução **init** :</span><span class="sxs-lookup"><span data-stu-id="95c71-126">The following syntaxes are supported for multiple assignment operations in the **Init** statement:</span></span>

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="95c71-127">As sintaxes a seguir têm suporte para várias operações de atribuição na instrução **REPEAT** :</span><span class="sxs-lookup"><span data-stu-id="95c71-127">The following syntaxes are supported for multiple assignment operations in the **Repeat** statement:</span></span>

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> <span data-ttu-id="95c71-128">Operações diferentes de pré ou pós-incremento podem não funcionar com todas as sintaxes.</span><span class="sxs-lookup"><span data-stu-id="95c71-128">Operations other than pre or post increment may not work with all syntaxes.</span></span>

<span data-ttu-id="95c71-129">Para várias **condições** , use operadores lógicos, conforme demonstrado pelo exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="95c71-129">For multiple **Conditions** use logical operators as demonstrated by the following example.</span></span>

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="95c71-130">Para obter mais informações, consulte [about_Logical_Operators](about_Logical_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="95c71-130">For more information, see [about_Logical_Operators](about_Logical_Operators.md).</span></span>

### <a name="examples"></a><span data-ttu-id="95c71-131">Exemplos</span><span class="sxs-lookup"><span data-stu-id="95c71-131">Examples</span></span>

<span data-ttu-id="95c71-132">No mínimo, uma `For` instrução requer o parêntese em torno da parte de **init** , da **condição** e da **repetição** da instrução e de um comando entre chaves na parte da **lista de instruções** da instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-132">At a minimum, a `For` statement requires the parenthesis surrounding the **Init** , **Condition** , and **Repeat** part of the statement and a command surrounded by braces in the **Statement list** part of the statement.</span></span>

<span data-ttu-id="95c71-133">Observe que os exemplos futuros mostram intencionalmente o código fora da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-133">Note that the upcoming examples intentionally show code outside the `For` statement.</span></span> <span data-ttu-id="95c71-134">Em exemplos posteriores, o código é integrado à `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-134">In later examples, code is integrated into the `For` statement.</span></span>

<span data-ttu-id="95c71-135">Por exemplo, a instrução a seguir `For` exibe continuamente o valor da `$i` variável até que você interrompa manualmente o comando pressionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="95c71-135">For example, the following `For` statement continually displays the value of the `$i` variable until you manually break out of the command by pressing CTRL+C.</span></span>

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

<span data-ttu-id="95c71-136">Você pode adicionar outros comandos à lista de instruções para que o valor de `$i` seja incrementado em 1 cada vez que o loop for executado, como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="95c71-136">You can add additional commands to the statement list so that the value of `$i` is incremented by 1 each time the loop is run, as the following example shows.</span></span>

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

<span data-ttu-id="95c71-137">Até que você saia do comando pressionando CTRL + C, essa instrução exibirá continuamente o valor da `$i` variável à medida que ela for incrementada em 1 cada vez que o loop for executado.</span><span class="sxs-lookup"><span data-stu-id="95c71-137">Until you break out of the command by pressing CTRL+C, this statement will continually display the value of the `$i` variable as it is incremented by 1 each time the loop is run.</span></span>

<span data-ttu-id="95c71-138">Em vez de alterar o valor da variável na lista de instruções, parte da `For` instrução, você pode usar a parte de **repetição** da `For` instrução, como a seguir.</span><span class="sxs-lookup"><span data-stu-id="95c71-138">Rather than change the value of the variable in the statement list part of the `For` statement, you can use the **Repeat** portion of the `For` statement instead, as follows.</span></span>

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="95c71-139">Essa instrução ainda será repetida indefinidamente até que você se divida do comando pressionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="95c71-139">This statement will still repeat indefinitely until you break out of the command by pressing CTRL+C.</span></span>

<span data-ttu-id="95c71-140">Você pode encerrar o `For` loop usando uma *condição* .</span><span class="sxs-lookup"><span data-stu-id="95c71-140">You can terminate the `For` loop using a *condition* .</span></span> <span data-ttu-id="95c71-141">Você pode inserir uma condição usando a parte da **condição** da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-141">You can place a condition using the **Condition** portion of the `For` statement.</span></span> <span data-ttu-id="95c71-142">O `For` loop é encerrado quando a condição é avaliada como `$false` .</span><span class="sxs-lookup"><span data-stu-id="95c71-142">The `For` loop terminates when the condition evaluates to `$false`.</span></span>

<span data-ttu-id="95c71-143">No exemplo a seguir, o `For` loop é executado enquanto o valor de `$i` é menor ou igual a 10.</span><span class="sxs-lookup"><span data-stu-id="95c71-143">In the following example, the `For` loop runs while the value of `$i` is less than or equal to 10.</span></span>

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="95c71-144">Em vez de criar e inicializar a variável fora da `For` instrução, você pode executar essa tarefa dentro do `For` loop usando a parte **init** da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-144">Instead of creating and initializing the variable outside the `For` statement, you can perform this task inside the `For` loop by using the **Init** portion of the `For` statement.</span></span>

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

<span data-ttu-id="95c71-145">Você pode usar retornos de carro em vez de ponto e vírgula para delimitar as partes de **inicialização** , **condição** e **repetição** da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-145">You can use carriage returns instead of semicolons to delimit the **Init** , **Condition** , and **Repeat** portions of the `For` statement.</span></span> <span data-ttu-id="95c71-146">O exemplo a seguir mostra um `For` que usa essa sintaxe alternativa.</span><span class="sxs-lookup"><span data-stu-id="95c71-146">The following example shows a `For` that uses this alternative syntax.</span></span>

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

<span data-ttu-id="95c71-147">Essa forma alternativa da `For` instrução funciona nos arquivos de script do PowerShell e no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95c71-147">This alternative form of the `For` statement works in PowerShell script files and at the PowerShell command prompt.</span></span> <span data-ttu-id="95c71-148">No entanto, é mais fácil usar a `For` sintaxe da instrução com ponto e vírgula quando você insere comandos interativos no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="95c71-148">However, it is easier to use the `For` statement syntax with semicolons when you enter interactive commands at the command prompt.</span></span>

<span data-ttu-id="95c71-149">O `For` loop é mais flexível do que o `Foreach` loop porque permite incrementar valores em uma matriz ou coleção usando padrões.</span><span class="sxs-lookup"><span data-stu-id="95c71-149">The `For` loop is more flexible than the `Foreach` loop because it allows you to increment values in an array or collection by using patterns.</span></span> <span data-ttu-id="95c71-150">No exemplo a seguir, a `$i` variável é incrementada por 2 na parte de **repetição** da `For` instrução.</span><span class="sxs-lookup"><span data-stu-id="95c71-150">In the following example, the `$i` variable is incremented by 2 in the **Repeat** portion of the `For` statement.</span></span>

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

<span data-ttu-id="95c71-151">O `For` loop também pode ser gravado em uma linha como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="95c71-151">The `For` loop can also be written on one line as in the following example.</span></span>

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a><span data-ttu-id="95c71-152">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="95c71-152">SEE ALSO</span></span>

[<span data-ttu-id="95c71-153">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="95c71-153">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="95c71-154">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="95c71-154">about_Foreach</span></span>](about_Foreach.md)

