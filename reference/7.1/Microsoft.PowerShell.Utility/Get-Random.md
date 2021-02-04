---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 842d4ea92f60a92fddcddea11bb8155c708ac192
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495951"
---
# <span data-ttu-id="59b03-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="59b03-102">Get-Random</span></span>

## <span data-ttu-id="59b03-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="59b03-103">SYNOPSIS</span></span>
<span data-ttu-id="59b03-104">Obtém um número aleatório ou seleciona objetos aleatoriamente de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="59b03-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="59b03-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59b03-105">SYNTAX</span></span>

### <span data-ttu-id="59b03-106">RandomNumberParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="59b03-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="59b03-107">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="59b03-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="59b03-108">ShuffleParameterSet</span><span class="sxs-lookup"><span data-stu-id="59b03-108">ShuffleParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## <span data-ttu-id="59b03-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59b03-109">DESCRIPTION</span></span>

<span data-ttu-id="59b03-110">O `Get-Random` cmdlet obtém um número selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="59b03-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="59b03-111">Se você enviar uma coleção de objetos ao `Get-Random` , ele obterá um ou mais objetos selecionados aleatoriamente da coleção.</span><span class="sxs-lookup"><span data-stu-id="59b03-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="59b03-112">Sem parâmetros ou entrada, um `Get-Random` comando retorna um inteiro não assinado de 32 bits selecionado aleatoriamente entre 0 (zero) e **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="59b03-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="59b03-113">Por padrão, o `Get-Random` gera randomização segura criptograficamente usando a classe [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="59b03-113">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="59b03-114">Você pode usar os parâmetros de `Get-Random` para especificar os valores mínimo e máximo, o número de objetos retornados de uma coleção ou um número de semente.</span><span class="sxs-lookup"><span data-stu-id="59b03-114">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="59b03-115">Definir os resultados deliberados de semente em comportamento não aleatório e repetível.</span><span class="sxs-lookup"><span data-stu-id="59b03-115">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="59b03-116">Ele só deve ser usado ao tentar reproduzir o comportamento, como ao depurar ou analisar um script que inclui `Get-Random` comandos.</span><span class="sxs-lookup"><span data-stu-id="59b03-116">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="59b03-117">Esse valor de semente é usado para o comando atual e para todos os comandos subsequentes `Get-Random` na sessão atual até que você use **setsemente** novamente ou feche a sessão.</span><span class="sxs-lookup"><span data-stu-id="59b03-117">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="59b03-118">Não é possível redefinir a semente para seu valor padrão.</span><span class="sxs-lookup"><span data-stu-id="59b03-118">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="59b03-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="59b03-119">EXAMPLES</span></span>

### <span data-ttu-id="59b03-120">Exemplo 1: obter um inteiro aleatório</span><span class="sxs-lookup"><span data-stu-id="59b03-120">Example 1: Get a random integer</span></span>

<span data-ttu-id="59b03-121">Esse comando obtém um inteiro aleatório entre 0 (zero) e **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="59b03-121">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="59b03-122">Exemplo 2: obter um inteiro aleatório entre 0 e 99</span><span class="sxs-lookup"><span data-stu-id="59b03-122">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="59b03-123">Exemplo 3: obter um inteiro aleatório entre-100 e 99</span><span class="sxs-lookup"><span data-stu-id="59b03-123">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="59b03-124">Exemplo 4: obter um número de ponto flutuante aleatório</span><span class="sxs-lookup"><span data-stu-id="59b03-124">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="59b03-125">Esse comando obtém um número de ponto flutuante aleatório maior ou igual a 10.7 e menor que 20.92.</span><span class="sxs-lookup"><span data-stu-id="59b03-125">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="59b03-126">Exemplo 5: obter um inteiro aleatório de uma matriz</span><span class="sxs-lookup"><span data-stu-id="59b03-126">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="59b03-127">Esse comando obtém um número selecionado aleatoriamente da matriz especificada.</span><span class="sxs-lookup"><span data-stu-id="59b03-127">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="59b03-128">Exemplo 6: obter vários inteiros aleatórios de uma matriz</span><span class="sxs-lookup"><span data-stu-id="59b03-128">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="59b03-129">Esse comando obtém três números selecionados aleatoriamente em ordem aleatória de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="59b03-129">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="59b03-130">Exemplo 7: tornar aleatório uma coleção inteira</span><span class="sxs-lookup"><span data-stu-id="59b03-130">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="59b03-131">A partir do PowerShell 7,1, você pode usar o parâmetro de **ordem aleatória** para retornar a coleção inteira em uma ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="59b03-131">Starting in PowerShell 7.1, you can use the **Shuffle** parameter to return the entire collection in a random order.</span></span>

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

### <span data-ttu-id="59b03-132">Exemplo 8: obter um valor não numérico aleatório</span><span class="sxs-lookup"><span data-stu-id="59b03-132">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="59b03-133">Esse comando retorna um valor aleatório de uma coleção não numérica.</span><span class="sxs-lookup"><span data-stu-id="59b03-133">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="59b03-134">Exemplo 9: usar o parâmetro setsemente</span><span class="sxs-lookup"><span data-stu-id="59b03-134">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="59b03-135">Este exemplo mostra o efeito do uso do parâmetro **SetSeed**.</span><span class="sxs-lookup"><span data-stu-id="59b03-135">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="59b03-136">Como **setsemente** produz comportamento não aleatório, ele é normalmente usado apenas para reproduzir resultados, como ao depurar ou analisar um script.</span><span class="sxs-lookup"><span data-stu-id="59b03-136">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="59b03-137">Exemplo 10: obter arquivos aleatórios</span><span class="sxs-lookup"><span data-stu-id="59b03-137">Example 10: Get random files</span></span>

<span data-ttu-id="59b03-138">Esses comandos obtêm um exemplo selecionado aleatoriamente de 50 arquivos da `C:` unidade do computador local.</span><span class="sxs-lookup"><span data-stu-id="59b03-138">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="59b03-139">Exemplo 11: roll Fair</span><span class="sxs-lookup"><span data-stu-id="59b03-139">Example 11: Roll fair dice</span></span>

<span data-ttu-id="59b03-140">Este exemplo acumula um dado justo 1200 vezes e conta os resultados.</span><span class="sxs-lookup"><span data-stu-id="59b03-140">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="59b03-141">O primeiro comando, `ForEach-Object` repete a chamada para `Get-Random` do piped em números (1-6).</span><span class="sxs-lookup"><span data-stu-id="59b03-141">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="59b03-142">Os resultados são agrupados por seu valor com `Group-Object` e formatados como uma tabela com `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="59b03-142">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

### <span data-ttu-id="59b03-143">Exemplo 12: usar o parâmetro de contagem</span><span class="sxs-lookup"><span data-stu-id="59b03-143">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="59b03-144">Agora você pode usar o parâmetro **Count** sem objetos de tubulação para `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="59b03-144">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="59b03-145">O exemplo a seguir obtém três números aleatórios menores que 10.</span><span class="sxs-lookup"><span data-stu-id="59b03-145">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="59b03-146">Exemplo 13: usar o parâmetro InputObject com uma cadeia de caracteres vazia ou $null</span><span class="sxs-lookup"><span data-stu-id="59b03-146">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="59b03-147">Neste exemplo, o parâmetro **InputObject** especifica uma matriz que contém uma cadeia de caracteres vazia ( `''` ) e `$null` .</span><span class="sxs-lookup"><span data-stu-id="59b03-147">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="59b03-148">`Get-Random` retornará uma `a` cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="59b03-148">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="59b03-149">O Stinger vazio é exibido como uma linha em branco e `$null` retorna a um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b03-149">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="59b03-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59b03-150">PARAMETERS</span></span>

### <span data-ttu-id="59b03-151">-Contagem</span><span class="sxs-lookup"><span data-stu-id="59b03-151">-Count</span></span>

<span data-ttu-id="59b03-152">Especifica o número de objetos aleatórios ou números a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="59b03-152">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="59b03-153">O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="59b03-153">The default is 1.</span></span>

<span data-ttu-id="59b03-154">Quando usado com `InputObject` , se o valor de **Count** excede o número de objetos na coleção, `Get-Random` retorna todos os objetos em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="59b03-154">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

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

### <span data-ttu-id="59b03-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="59b03-155">-InputObject</span></span>

<span data-ttu-id="59b03-156">Especifica uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="59b03-156">Specifies a collection of objects.</span></span> <span data-ttu-id="59b03-157">`Get-Random` Obtém objetos aleatoriamente selecionados em ordem aleatória da coleção até o número especificado por **contagem**.</span><span class="sxs-lookup"><span data-stu-id="59b03-157">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="59b03-158">Insira os objetos, uma variável que contenha os objetos ou um comando ou expressão que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="59b03-158">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="59b03-159">Também é possível canalizar uma coleção de objetos para o `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="59b03-159">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="59b03-160">A partir do PowerShell 7, o parâmetro **InputObject** aceita matrizes que podem conter uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="59b03-160">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="59b03-161">A matriz pode ser enviada ao pipeline ou como um valor de parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="59b03-161">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

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

### <span data-ttu-id="59b03-162">-Máximo</span><span class="sxs-lookup"><span data-stu-id="59b03-162">-Maximum</span></span>

<span data-ttu-id="59b03-163">Especifica um valor máximo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="59b03-163">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="59b03-164">`Get-Random` Retorna um valor menor que o máximo (não igual).</span><span class="sxs-lookup"><span data-stu-id="59b03-164">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="59b03-165">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="59b03-165">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="59b03-166">O valor de **Maximum** deve ser maior que (diferente de) o valor de **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="59b03-166">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="59b03-167">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="59b03-167">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="59b03-168">Em um computador de 64 bits, se o valor **mínimo** for um inteiro de 32 bits, o valor padrão de **máximo** será **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="59b03-168">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="59b03-169">Se o valor **mínimo** for um Double (um número de ponto flutuante), o valor padrão de **Maximum** será **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="59b03-169">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="59b03-170">Caso contrário, o valor padrão é **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="59b03-170">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="59b03-171">-Mínimo</span><span class="sxs-lookup"><span data-stu-id="59b03-171">-Minimum</span></span>

<span data-ttu-id="59b03-172">Especifica um valor mínimo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="59b03-172">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="59b03-173">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="59b03-173">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="59b03-174">O valor padrão é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="59b03-174">The default value is 0 (zero).</span></span>

<span data-ttu-id="59b03-175">O valor de **Minimum** deve ser menor que (diferente de) o valor de **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="59b03-175">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="59b03-176">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="59b03-176">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="59b03-177">-Setsemente</span><span class="sxs-lookup"><span data-stu-id="59b03-177">-SetSeed</span></span>

<span data-ttu-id="59b03-178">Especifica um valor de semente para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="59b03-178">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="59b03-179">Quando você usa **setsemente**, o cmdlet usa o método [System. Random](/dotnet/api/system.random) para gerar números de pseudoaleatória, que não é criptograficamente seguro.</span><span class="sxs-lookup"><span data-stu-id="59b03-179">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="59b03-180">Definir os resultados da semente no comportamento não aleatório.</span><span class="sxs-lookup"><span data-stu-id="59b03-180">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="59b03-181">Ele só deve ser usado ao tentar reproduzir o comportamento, como ao depurar ou analisar um script que inclui `Get-Random` comandos.</span><span class="sxs-lookup"><span data-stu-id="59b03-181">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="59b03-182">Esse valor de semente é usado para o comando atual e para todos os comandos subsequentes `Get-Random` na sessão atual até que você use **setsemente** novamente ou feche a sessão.</span><span class="sxs-lookup"><span data-stu-id="59b03-182">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="59b03-183">Não é possível redefinir a semente para seu valor padrão.</span><span class="sxs-lookup"><span data-stu-id="59b03-183">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="59b03-184">-Ordem aleatória</span><span class="sxs-lookup"><span data-stu-id="59b03-184">-Shuffle</span></span>

<span data-ttu-id="59b03-185">Retorna a coleção inteira em uma ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="59b03-185">Returns the entire collection in a randomized order.</span></span>

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

### <span data-ttu-id="59b03-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59b03-186">CommonParameters</span></span>

<span data-ttu-id="59b03-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59b03-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59b03-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59b03-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59b03-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="59b03-189">INPUTS</span></span>

### <span data-ttu-id="59b03-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="59b03-190">System.Object</span></span>

<span data-ttu-id="59b03-191">É possível canalizar um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="59b03-191">You can pipe one or more objects.</span></span> <span data-ttu-id="59b03-192">`Get-Random` seleciona valores aleatoriamente dos objetos canalizados.</span><span class="sxs-lookup"><span data-stu-id="59b03-192">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="59b03-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="59b03-193">OUTPUTS</span></span>

### <span data-ttu-id="59b03-194">System. Int32, System. Int64, sistema. Double</span><span class="sxs-lookup"><span data-stu-id="59b03-194">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="59b03-195">`Get-Random` Retorna um número inteiro ou de ponto flutuante ou um objeto selecionado aleatoriamente de uma coleção enviada.</span><span class="sxs-lookup"><span data-stu-id="59b03-195">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="59b03-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="59b03-196">NOTES</span></span>

<span data-ttu-id="59b03-197">Por padrão, o `Get-Random` gera randomização segura criptograficamente usando a classe [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="59b03-197">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="59b03-198">`Get-Random` Nem sempre retorna o mesmo tipo de dados que o valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="59b03-198">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="59b03-199">A tabela a seguir mostra o tipo de saída para cada um dos tipos de entrada numéricos.</span><span class="sxs-lookup"><span data-stu-id="59b03-199">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="59b03-200">Tipo de entrada</span><span class="sxs-lookup"><span data-stu-id="59b03-200">Input Type</span></span> | <span data-ttu-id="59b03-201">Tipo de saída</span><span class="sxs-lookup"><span data-stu-id="59b03-201">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="59b03-202">SByte</span><span class="sxs-lookup"><span data-stu-id="59b03-202">SByte</span></span>    |   <span data-ttu-id="59b03-203">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-203">Double</span></span>    |
|    <span data-ttu-id="59b03-204">Byte</span><span class="sxs-lookup"><span data-stu-id="59b03-204">Byte</span></span>    |   <span data-ttu-id="59b03-205">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-205">Double</span></span>    |
|   <span data-ttu-id="59b03-206">Int16</span><span class="sxs-lookup"><span data-stu-id="59b03-206">Int16</span></span>    |   <span data-ttu-id="59b03-207">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-207">Double</span></span>    |
|   <span data-ttu-id="59b03-208">UInt16</span><span class="sxs-lookup"><span data-stu-id="59b03-208">UInt16</span></span>   |   <span data-ttu-id="59b03-209">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-209">Double</span></span>    |
|   <span data-ttu-id="59b03-210">Int32</span><span class="sxs-lookup"><span data-stu-id="59b03-210">Int32</span></span>    |    <span data-ttu-id="59b03-211">Int32</span><span class="sxs-lookup"><span data-stu-id="59b03-211">Int32</span></span>    |
|   <span data-ttu-id="59b03-212">UInt32</span><span class="sxs-lookup"><span data-stu-id="59b03-212">UInt32</span></span>   |   <span data-ttu-id="59b03-213">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-213">Double</span></span>    |
|   <span data-ttu-id="59b03-214">Int64</span><span class="sxs-lookup"><span data-stu-id="59b03-214">Int64</span></span>    |    <span data-ttu-id="59b03-215">Int64</span><span class="sxs-lookup"><span data-stu-id="59b03-215">Int64</span></span>    |
|   <span data-ttu-id="59b03-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="59b03-216">UInt64</span></span>   |   <span data-ttu-id="59b03-217">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-217">Double</span></span>    |
|   <span data-ttu-id="59b03-218">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-218">Double</span></span>   |   <span data-ttu-id="59b03-219">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-219">Double</span></span>    |
|   <span data-ttu-id="59b03-220">Single</span><span class="sxs-lookup"><span data-stu-id="59b03-220">Single</span></span>   |   <span data-ttu-id="59b03-221">Double</span><span class="sxs-lookup"><span data-stu-id="59b03-221">Double</span></span>    |

<span data-ttu-id="59b03-222">A partir do Windows PowerShell 3,0, `Get-Random` dá suporte a inteiros de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="59b03-222">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="59b03-223">No Windows PowerShell 2,0, todos os valores são convertidos em **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="59b03-223">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="59b03-224">A partir do PowerShell 7, o parâmetro **InputObject** no conjunto de parâmetros **RandomListItemParameterSet** aceita matrizes que contêm uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="59b03-224">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="59b03-225">Nas versões anteriores do PowerShell, apenas o parâmetro **máximo** no conjunto de parâmetros **RandomNumberParameterSet** aceitou uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="59b03-225">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="59b03-226">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="59b03-226">RELATED LINKS</span></span>

[<span data-ttu-id="59b03-227">System. Security. Cryptography. RandomNumberGenerator ()</span><span class="sxs-lookup"><span data-stu-id="59b03-227">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="59b03-228">Sistema. aleatório</span><span class="sxs-lookup"><span data-stu-id="59b03-228">Sytem.Random</span></span>](/dotnet/api/system.random)
