---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 644663c8871233bae84288f83492b518405d14ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193575"
---
# <span data-ttu-id="43025-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="43025-103">Get-Random</span></span>

## <span data-ttu-id="43025-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="43025-104">SYNOPSIS</span></span>
<span data-ttu-id="43025-105">Obtém um número aleatório ou seleciona objetos aleatoriamente de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="43025-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="43025-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43025-106">SYNTAX</span></span>

### <span data-ttu-id="43025-107">RandomNumberParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="43025-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="43025-108">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="43025-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="43025-109">ShuffleParameterSet</span><span class="sxs-lookup"><span data-stu-id="43025-109">ShuffleParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## <span data-ttu-id="43025-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43025-110">DESCRIPTION</span></span>

<span data-ttu-id="43025-111">O `Get-Random` cmdlet obtém um número selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="43025-111">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="43025-112">Se você enviar uma coleção de objetos ao `Get-Random` , ele obterá um ou mais objetos selecionados aleatoriamente da coleção.</span><span class="sxs-lookup"><span data-stu-id="43025-112">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="43025-113">Sem parâmetros ou entrada, um `Get-Random` comando retorna um inteiro não assinado de 32 bits selecionado aleatoriamente entre 0 (zero) e **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="43025-113">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="43025-114">Você pode usar os parâmetros de `Get-Random` para especificar um número de semente, os valores mínimo e máximo, o número de objetos retornados de uma coleção enviada e a coleção inteira em uma ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="43025-114">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, the number of objects returned from a submitted collection, and the entire collection in a random order.</span></span>

## <span data-ttu-id="43025-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="43025-115">EXAMPLES</span></span>

### <span data-ttu-id="43025-116">Exemplo 1: obter um inteiro aleatório</span><span class="sxs-lookup"><span data-stu-id="43025-116">Example 1: Get a random integer</span></span>

<span data-ttu-id="43025-117">Esse comando obtém um inteiro aleatório entre 0 (zero) e **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="43025-117">This command gets a random integer between 0 (zero) and **Int32.MaxValue** .</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="43025-118">Exemplo 2: obter um inteiro aleatório entre 0 e 99</span><span class="sxs-lookup"><span data-stu-id="43025-118">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="43025-119">Exemplo 3: obter um inteiro aleatório entre-100 e 99</span><span class="sxs-lookup"><span data-stu-id="43025-119">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="43025-120">Exemplo 4: obter um número de ponto flutuante aleatório</span><span class="sxs-lookup"><span data-stu-id="43025-120">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="43025-121">Esse comando obtém um número de ponto flutuante aleatório maior ou igual a 10.7 e menor que 20.92.</span><span class="sxs-lookup"><span data-stu-id="43025-121">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="43025-122">Exemplo 5: obter um inteiro aleatório de uma matriz</span><span class="sxs-lookup"><span data-stu-id="43025-122">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="43025-123">Esse comando obtém um número selecionado aleatoriamente da matriz especificada.</span><span class="sxs-lookup"><span data-stu-id="43025-123">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="43025-124">Exemplo 6: obter vários inteiros aleatórios de uma matriz</span><span class="sxs-lookup"><span data-stu-id="43025-124">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="43025-125">Esse comando obtém três números selecionados aleatoriamente em ordem aleatória de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="43025-125">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="43025-126">Exemplo 7: tornar aleatório uma coleção inteira</span><span class="sxs-lookup"><span data-stu-id="43025-126">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="43025-127">A partir do PowerShell 7,1, você pode usar o parâmetro de **ordem aleatória** para retornar a coleção inteira em uma ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="43025-127">Starting in PowerShell 7.1, you can use the **Shuffle** parameter to return the entire collection in a random order.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Shuffle
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="43025-128">Exemplo 8: obter um valor não numérico aleatório</span><span class="sxs-lookup"><span data-stu-id="43025-128">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="43025-129">Esse comando retorna um valor aleatório de uma coleção não numérica.</span><span class="sxs-lookup"><span data-stu-id="43025-129">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="43025-130">Exemplo 9: usar o parâmetro setsemente</span><span class="sxs-lookup"><span data-stu-id="43025-130">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="43025-131">Este exemplo mostra o efeito do uso do parâmetro **SetSeed** .</span><span class="sxs-lookup"><span data-stu-id="43025-131">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="43025-132">Como **setsemente** produz comportamento não aleatório, ele é normalmente usado apenas para reproduzir resultados, como ao depurar ou analisar um script.</span><span class="sxs-lookup"><span data-stu-id="43025-132">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### <span data-ttu-id="43025-133">Exemplo 10: obter arquivos aleatórios</span><span class="sxs-lookup"><span data-stu-id="43025-133">Example 10: Get random files</span></span>

<span data-ttu-id="43025-134">Esses comandos obtêm um exemplo selecionado aleatoriamente de 50 arquivos da `C:` unidade do computador local.</span><span class="sxs-lookup"><span data-stu-id="43025-134">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="43025-135">Exemplo 11: roll Fair</span><span class="sxs-lookup"><span data-stu-id="43025-135">Example 11: Roll fair dice</span></span>

<span data-ttu-id="43025-136">Este exemplo acumula um dado justo 1200 vezes e conta os resultados.</span><span class="sxs-lookup"><span data-stu-id="43025-136">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="43025-137">O primeiro comando, `For-EachObject` repete a chamada para `Get-Random` do piped em números (1-6).</span><span class="sxs-lookup"><span data-stu-id="43025-137">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="43025-138">Os resultados são agrupados por seu valor com `Group-Object` e formatados como uma tabela com `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="43025-138">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### <span data-ttu-id="43025-139">Exemplo 12: usar o parâmetro de contagem</span><span class="sxs-lookup"><span data-stu-id="43025-139">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="43025-140">Agora você pode usar o parâmetro **Count** sem objetos de tubulação para `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="43025-140">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="43025-141">O exemplo a seguir obtém três números aleatórios menores que 10.</span><span class="sxs-lookup"><span data-stu-id="43025-141">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="43025-142">Exemplo 13: usar o parâmetro InputObject com uma cadeia de caracteres vazia ou $null</span><span class="sxs-lookup"><span data-stu-id="43025-142">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="43025-143">Neste exemplo, o parâmetro **InputObject** especifica uma matriz que contém uma cadeia de caracteres vazia ( `''` ) e `$null` .</span><span class="sxs-lookup"><span data-stu-id="43025-143">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="43025-144">`Get-Random` retornará uma `a` cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="43025-144">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="43025-145">O Stinger vazio é exibido como uma linha em branco e `$null` retorna a um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43025-145">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="43025-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43025-146">PARAMETERS</span></span>

### <span data-ttu-id="43025-147">-Contagem</span><span class="sxs-lookup"><span data-stu-id="43025-147">-Count</span></span>

<span data-ttu-id="43025-148">Especifica o número de objetos aleatórios ou números a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="43025-148">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="43025-149">O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="43025-149">The default is 1.</span></span>

<span data-ttu-id="43025-150">Quando usado com `InputObject` , se o valor de **Count** excede o número de objetos na coleção, `Get-Random` retorna todos os objetos em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="43025-150">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomNumberParameterSet, RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43025-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43025-151">-InputObject</span></span>

<span data-ttu-id="43025-152">Especifica uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="43025-152">Specifies a collection of objects.</span></span> <span data-ttu-id="43025-153">`Get-Random` Obtém objetos aleatoriamente selecionados em ordem aleatória da coleção até o número especificado por **contagem** .</span><span class="sxs-lookup"><span data-stu-id="43025-153">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count** .</span></span> <span data-ttu-id="43025-154">Insira os objetos, uma variável que contenha os objetos ou um comando ou expressão que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="43025-154">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="43025-155">Também é possível canalizar uma coleção de objetos para o `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="43025-155">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="43025-156">A partir do PowerShell 7, o parâmetro **InputObject** aceita matrizes que podem conter uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="43025-156">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="43025-157">A matriz pode ser enviada ao pipeline ou como um valor de parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="43025-157">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet, ShuffleParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43025-158">-Máximo</span><span class="sxs-lookup"><span data-stu-id="43025-158">-Maximum</span></span>

<span data-ttu-id="43025-159">Especifica um valor máximo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="43025-159">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="43025-160">`Get-Random` Retorna um valor menor que o máximo (não igual).</span><span class="sxs-lookup"><span data-stu-id="43025-160">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="43025-161">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="43025-161">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="43025-162">O valor de **Maximum** deve ser maior que (diferente de) o valor de **Minimum** .</span><span class="sxs-lookup"><span data-stu-id="43025-162">The value of **Maximum** must be greater than (not equal to) the value of **Minimum** .</span></span> <span data-ttu-id="43025-163">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="43025-163">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="43025-164">Em um computador de 64 bits, se o valor **mínimo** for um inteiro de 32 bits, o valor padrão de **máximo** será **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="43025-164">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue** .</span></span>

<span data-ttu-id="43025-165">Se o valor **mínimo** for um Double (um número de ponto flutuante), o valor padrão de **Maximum** será **Double. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="43025-165">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue** .</span></span> <span data-ttu-id="43025-166">Caso contrário, o valor padrão é **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="43025-166">Otherwise, the default value is **Int32.MaxValue** .</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43025-167">-Mínimo</span><span class="sxs-lookup"><span data-stu-id="43025-167">-Minimum</span></span>

<span data-ttu-id="43025-168">Especifica um valor mínimo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="43025-168">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="43025-169">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="43025-169">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="43025-170">O valor padrão é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="43025-170">The default value is 0 (zero).</span></span>

<span data-ttu-id="43025-171">O valor de **Minimum** deve ser menor que (diferente de) o valor de **Maximum** .</span><span class="sxs-lookup"><span data-stu-id="43025-171">The value of **Minimum** must be less than (not equal to) the value of **Maximum** .</span></span> <span data-ttu-id="43025-172">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="43025-172">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43025-173">-Setsemente</span><span class="sxs-lookup"><span data-stu-id="43025-173">-SetSeed</span></span>

<span data-ttu-id="43025-174">Especifica um valor de semente para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="43025-174">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="43025-175">Esse valor de semente é usado para o comando atual e para todos os comandos subsequentes `Get-Random` na sessão atual até que você use **setsemente** novamente ou feche a sessão.</span><span class="sxs-lookup"><span data-stu-id="43025-175">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="43025-176">Não é possível redefinir a semente para seu valor padrão.</span><span class="sxs-lookup"><span data-stu-id="43025-176">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="43025-177">O parâmetro **setsemente** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="43025-177">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="43025-178">Por padrão, `Get-Random` o usa o método [RandomNumberGenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) para gerar um valor de semente.</span><span class="sxs-lookup"><span data-stu-id="43025-178">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="43025-179">Como o **setsemente** resulta em comportamento não aleatório, ele é normalmente usado apenas ao tentar reproduzir o comportamento, como ao depurar ou analisar um script que inclui `Get-Random` comandos.</span><span class="sxs-lookup"><span data-stu-id="43025-179">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43025-180">-Ordem aleatória</span><span class="sxs-lookup"><span data-stu-id="43025-180">-Shuffle</span></span>

<span data-ttu-id="43025-181">Retorna a coleção inteira em uma ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="43025-181">Returns the entire collection in a randomized order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShuffleParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43025-182">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43025-182">CommonParameters</span></span>

<span data-ttu-id="43025-183">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43025-183">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43025-184">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43025-184">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43025-185">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="43025-185">INPUTS</span></span>

### <span data-ttu-id="43025-186">System.Object</span><span class="sxs-lookup"><span data-stu-id="43025-186">System.Object</span></span>

<span data-ttu-id="43025-187">É possível canalizar um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="43025-187">You can pipe one or more objects.</span></span> <span data-ttu-id="43025-188">`Get-Random` seleciona valores aleatoriamente dos objetos canalizados.</span><span class="sxs-lookup"><span data-stu-id="43025-188">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="43025-189">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="43025-189">OUTPUTS</span></span>

### <span data-ttu-id="43025-190">System. Int32, System. Int64, sistema. Double</span><span class="sxs-lookup"><span data-stu-id="43025-190">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="43025-191">`Get-Random` Retorna um número inteiro ou de ponto flutuante ou um objeto selecionado aleatoriamente de uma coleção enviada.</span><span class="sxs-lookup"><span data-stu-id="43025-191">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="43025-192">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="43025-192">NOTES</span></span>

<span data-ttu-id="43025-193">`Get-Random` define uma semente padrão para cada sessão com base no relógio de tempo do sistema quando a sessão é iniciada.</span><span class="sxs-lookup"><span data-stu-id="43025-193">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="43025-194">`Get-Random` Nem sempre retorna o mesmo tipo de dados que o valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="43025-194">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="43025-195">A tabela a seguir mostra o tipo de saída para cada um dos tipos de entrada numéricos.</span><span class="sxs-lookup"><span data-stu-id="43025-195">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="43025-196">Tipo de entrada</span><span class="sxs-lookup"><span data-stu-id="43025-196">Input Type</span></span> | <span data-ttu-id="43025-197">Tipo de saída</span><span class="sxs-lookup"><span data-stu-id="43025-197">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="43025-198">SByte</span><span class="sxs-lookup"><span data-stu-id="43025-198">SByte</span></span>    |   <span data-ttu-id="43025-199">Duplo</span><span class="sxs-lookup"><span data-stu-id="43025-199">Double</span></span>    |
|    <span data-ttu-id="43025-200">Byte</span><span class="sxs-lookup"><span data-stu-id="43025-200">Byte</span></span>    |   <span data-ttu-id="43025-201">Duplo</span><span class="sxs-lookup"><span data-stu-id="43025-201">Double</span></span>    |
|   <span data-ttu-id="43025-202">Int16</span><span class="sxs-lookup"><span data-stu-id="43025-202">Int16</span></span>    |   <span data-ttu-id="43025-203">Duplo</span><span class="sxs-lookup"><span data-stu-id="43025-203">Double</span></span>    |
|   <span data-ttu-id="43025-204">UInt16</span><span class="sxs-lookup"><span data-stu-id="43025-204">UInt16</span></span>   |   <span data-ttu-id="43025-205">Duplo</span><span class="sxs-lookup"><span data-stu-id="43025-205">Double</span></span>    |
|   <span data-ttu-id="43025-206">Int32</span><span class="sxs-lookup"><span data-stu-id="43025-206">Int32</span></span>    |    <span data-ttu-id="43025-207">Int32</span><span class="sxs-lookup"><span data-stu-id="43025-207">Int32</span></span>    |
|   <span data-ttu-id="43025-208">UInt32</span><span class="sxs-lookup"><span data-stu-id="43025-208">UInt32</span></span>   |   <span data-ttu-id="43025-209">Double</span><span class="sxs-lookup"><span data-stu-id="43025-209">Double</span></span>    |
|   <span data-ttu-id="43025-210">Int64</span><span class="sxs-lookup"><span data-stu-id="43025-210">Int64</span></span>    |    <span data-ttu-id="43025-211">Int64</span><span class="sxs-lookup"><span data-stu-id="43025-211">Int64</span></span>    |
|   <span data-ttu-id="43025-212">UInt64</span><span class="sxs-lookup"><span data-stu-id="43025-212">UInt64</span></span>   |   <span data-ttu-id="43025-213">Double</span><span class="sxs-lookup"><span data-stu-id="43025-213">Double</span></span>    |
|   <span data-ttu-id="43025-214">Double</span><span class="sxs-lookup"><span data-stu-id="43025-214">Double</span></span>   |   <span data-ttu-id="43025-215">Double</span><span class="sxs-lookup"><span data-stu-id="43025-215">Double</span></span>    |
|   <span data-ttu-id="43025-216">Simples</span><span class="sxs-lookup"><span data-stu-id="43025-216">Single</span></span>   |   <span data-ttu-id="43025-217">Duplo</span><span class="sxs-lookup"><span data-stu-id="43025-217">Double</span></span>    |

<span data-ttu-id="43025-218">A partir do Windows PowerShell 3,0, `Get-Random` dá suporte a inteiros de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="43025-218">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="43025-219">No Windows PowerShell 2,0, todos os valores são convertidos em **System. Int32** .</span><span class="sxs-lookup"><span data-stu-id="43025-219">In Windows PowerShell 2.0, all values are cast to **System.Int32** .</span></span>

<span data-ttu-id="43025-220">A partir do PowerShell 7, o parâmetro **InputObject** no conjunto de parâmetros **RandomListItemParameterSet** aceita matrizes que contêm uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="43025-220">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="43025-221">Nas versões anteriores do PowerShell, apenas o parâmetro **máximo** no conjunto de parâmetros **RandomNumberParameterSet** aceitou uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="43025-221">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="43025-222">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="43025-222">RELATED LINKS</span></span>

