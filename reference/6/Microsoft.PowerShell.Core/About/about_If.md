---
description: Descreve um comando de linguagem que você pode usar para executar listas de instruções com base nos resultados de um ou mais testes condicionais.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 7f63b6f12743390608e0da72adb4098ce0583751
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195724"
---
# <a name="about-if"></a><span data-ttu-id="c34a3-104">Sobre se</span><span class="sxs-lookup"><span data-stu-id="c34a3-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="c34a3-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="c34a3-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c34a3-106">Descreve um comando de linguagem que você pode usar para executar listas de instruções com base nos resultados de um ou mais testes condicionais.</span><span class="sxs-lookup"><span data-stu-id="c34a3-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="c34a3-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="c34a3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c34a3-108">Você pode usar a `If` instrução para executar blocos de código se um teste condicional especificado for avaliado como true.</span><span class="sxs-lookup"><span data-stu-id="c34a3-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="c34a3-109">Você também pode especificar um ou mais testes condicionais adicionais a serem executados se todos os testes anteriores forem avaliados como false.</span><span class="sxs-lookup"><span data-stu-id="c34a3-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="c34a3-110">Por fim, você pode especificar um bloco de código adicional que será executado se nenhum outro teste condicional anterior for avaliado como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="c34a3-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="c34a3-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c34a3-111">Syntax</span></span>

<span data-ttu-id="c34a3-112">O exemplo a seguir mostra a `If` sintaxe da instrução:</span><span class="sxs-lookup"><span data-stu-id="c34a3-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="c34a3-113">Quando você executa uma `If` instrução, o PowerShell avalia a `<test1>` expressão condicional como true ou false.</span><span class="sxs-lookup"><span data-stu-id="c34a3-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="c34a3-114">Se `<test1>` é verdadeiro, `<statement list 1>` é executado e o PowerShell sai da `If` instrução.</span><span class="sxs-lookup"><span data-stu-id="c34a3-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="c34a3-115">Se `<test1>` for false, o PowerShell avaliará a condição especificada pela `<test2>` instrução condicional.</span><span class="sxs-lookup"><span data-stu-id="c34a3-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="c34a3-116">Se `<test2>` é verdadeiro, `<statement list 2>` é executado e o PowerShell sai da `If` instrução.</span><span class="sxs-lookup"><span data-stu-id="c34a3-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="c34a3-117">Se `<test1>` e `<test2>` for avaliado como false, o `<statement list 3` bloco de código> será executado e o PowerShell sairá da instrução If.</span><span class="sxs-lookup"><span data-stu-id="c34a3-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="c34a3-118">Você pode usar várias instruções Elseif para encadear uma série de testes condicionais.</span><span class="sxs-lookup"><span data-stu-id="c34a3-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="c34a3-119">Portanto, cada teste será executado somente se todos os testes anteriores forem falsos.</span><span class="sxs-lookup"><span data-stu-id="c34a3-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="c34a3-120">Se você precisar criar uma `If` instrução que contém muitas instruções ElseIf, considere usar uma instrução switch em vez disso.</span><span class="sxs-lookup"><span data-stu-id="c34a3-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="c34a3-121">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="c34a3-121">Examples:</span></span>

<span data-ttu-id="c34a3-122">A instrução mais simples `If` contém um único comando e não contém nenhuma instrução ElseIf ou nenhuma instrução else.</span><span class="sxs-lookup"><span data-stu-id="c34a3-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="c34a3-123">O exemplo a seguir mostra a forma mais simples da `If` instrução:</span><span class="sxs-lookup"><span data-stu-id="c34a3-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="c34a3-124">Neste exemplo, se a variável $a for maior que 2, a condição será avaliada como true e a lista de instruções será executada.</span><span class="sxs-lookup"><span data-stu-id="c34a3-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="c34a3-125">No entanto, se $a for menor ou igual a 2 ou não for uma variável existente, a `If` instrução não exibirá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="c34a3-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="c34a3-126">Ao adicionar uma instrução else, uma mensagem é exibida quando $a é menor ou igual a 2.</span><span class="sxs-lookup"><span data-stu-id="c34a3-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="c34a3-127">Como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c34a3-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="c34a3-128">Para refinar ainda mais este exemplo, você pode usar a instrução Elseif para exibir uma mensagem quando o valor de $a for igual a 2.</span><span class="sxs-lookup"><span data-stu-id="c34a3-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="c34a3-129">Como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c34a3-129">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

## <a name="see-also"></a><span data-ttu-id="c34a3-130">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="c34a3-130">SEE ALSO</span></span>

[<span data-ttu-id="c34a3-131">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="c34a3-131">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="c34a3-132">about_Switch</span><span class="sxs-lookup"><span data-stu-id="c34a3-132">about_Switch</span></span>](about_Switch.md)
