---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: c45b234445a7bc2b54aefb080d2d3da65433d412
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193006"
---
# <span data-ttu-id="b316f-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="b316f-103">Get-Random</span></span>

## <span data-ttu-id="b316f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b316f-104">SYNOPSIS</span></span>
<span data-ttu-id="b316f-105">Obtém um número aleatório ou seleciona objetos aleatoriamente de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="b316f-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="b316f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b316f-106">SYNTAX</span></span>

### <span data-ttu-id="b316f-107">RandomNumberParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="b316f-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="b316f-108">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="b316f-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="b316f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b316f-109">DESCRIPTION</span></span>

<span data-ttu-id="b316f-110">O `Get-Random` cmdlet obtém um número selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="b316f-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="b316f-111">Se você enviar uma coleção de objetos ao `Get-Random` , ele obterá um ou mais objetos selecionados aleatoriamente da coleção.</span><span class="sxs-lookup"><span data-stu-id="b316f-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="b316f-112">Sem parâmetros ou entrada, um `Get-Random` comando retorna um inteiro não assinado de 32 bits selecionado aleatoriamente entre 0 (zero) e **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="b316f-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="b316f-113">Você pode usar os parâmetros de `Get-Random` para especificar um número de semente, os valores mínimo e máximo e o número de objetos retornados de uma coleção enviada.</span><span class="sxs-lookup"><span data-stu-id="b316f-113">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, and the number of objects returned from a submitted collection.</span></span>

## <span data-ttu-id="b316f-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b316f-114">EXAMPLES</span></span>

### <span data-ttu-id="b316f-115">Exemplo 1: obter um inteiro aleatório</span><span class="sxs-lookup"><span data-stu-id="b316f-115">Example 1: Get a random integer</span></span>

<span data-ttu-id="b316f-116">Esse comando obtém um inteiro aleatório entre 0 (zero) e **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="b316f-116">This command gets a random integer between 0 (zero) and **Int32.MaxValue** .</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="b316f-117">Exemplo 2: obter um inteiro aleatório entre 0 e 99</span><span class="sxs-lookup"><span data-stu-id="b316f-117">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="b316f-118">Exemplo 3: obter um inteiro aleatório entre-100 e 99</span><span class="sxs-lookup"><span data-stu-id="b316f-118">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="b316f-119">Exemplo 4: obter um número de ponto flutuante aleatório</span><span class="sxs-lookup"><span data-stu-id="b316f-119">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="b316f-120">Esse comando obtém um número de ponto flutuante aleatório maior ou igual a 10.7 e menor que 20.92.</span><span class="sxs-lookup"><span data-stu-id="b316f-120">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="b316f-121">Exemplo 5: obter um inteiro aleatório de uma matriz</span><span class="sxs-lookup"><span data-stu-id="b316f-121">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="b316f-122">Esse comando obtém um número selecionado aleatoriamente da matriz especificada.</span><span class="sxs-lookup"><span data-stu-id="b316f-122">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="b316f-123">Exemplo 6: obter vários inteiros aleatórios de uma matriz</span><span class="sxs-lookup"><span data-stu-id="b316f-123">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="b316f-124">Esse comando obtém três números selecionados aleatoriamente em ordem aleatória de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="b316f-124">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="b316f-125">Exemplo 7: tornar aleatório uma coleção inteira</span><span class="sxs-lookup"><span data-stu-id="b316f-125">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="b316f-126">Esse comando retorna toda a coleção em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="b316f-126">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="b316f-127">O valor do parâmetro de **contagem** é a propriedade de valores estáticos **MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="b316f-127">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="b316f-128">Para retornar uma coleção inteira em ordem aleatória, insira qualquer número maior que ou igual ao número de objetos da coleção.</span><span class="sxs-lookup"><span data-stu-id="b316f-128">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="b316f-129">Exemplo 8: obter um valor não numérico aleatório</span><span class="sxs-lookup"><span data-stu-id="b316f-129">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="b316f-130">Esse comando retorna um valor aleatório de uma coleção não numérica.</span><span class="sxs-lookup"><span data-stu-id="b316f-130">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="b316f-131">Exemplo 9: usar o parâmetro setsemente</span><span class="sxs-lookup"><span data-stu-id="b316f-131">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="b316f-132">Este exemplo mostra o efeito do uso do parâmetro **SetSeed** .</span><span class="sxs-lookup"><span data-stu-id="b316f-132">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="b316f-133">Como **setsemente** produz comportamento não aleatório, ele é normalmente usado apenas para reproduzir resultados, como ao depurar ou analisar um script.</span><span class="sxs-lookup"><span data-stu-id="b316f-133">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="b316f-134">Exemplo 10: obter arquivos aleatórios</span><span class="sxs-lookup"><span data-stu-id="b316f-134">Example 10: Get random files</span></span>

<span data-ttu-id="b316f-135">Esses comandos obtêm um exemplo selecionado aleatoriamente de 50 arquivos da `C:` unidade do computador local.</span><span class="sxs-lookup"><span data-stu-id="b316f-135">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="b316f-136">Exemplo 11: roll Fair</span><span class="sxs-lookup"><span data-stu-id="b316f-136">Example 11: Roll fair dice</span></span>

<span data-ttu-id="b316f-137">Este exemplo acumula um dado justo 1200 vezes e conta os resultados.</span><span class="sxs-lookup"><span data-stu-id="b316f-137">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="b316f-138">O primeiro comando, `For-EachObject` repete a chamada para `Get-Random` do piped em números (1-6).</span><span class="sxs-lookup"><span data-stu-id="b316f-138">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="b316f-139">Os resultados são agrupados por seu valor com `Group-Object` e formatados como uma tabela com `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b316f-139">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

### <span data-ttu-id="b316f-140">Exemplo 12: usar o parâmetro de contagem</span><span class="sxs-lookup"><span data-stu-id="b316f-140">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="b316f-141">Agora você pode usar o parâmetro **Count** sem objetos de tubulação para `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="b316f-141">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="b316f-142">O exemplo a seguir obtém três números aleatórios menores que 10.</span><span class="sxs-lookup"><span data-stu-id="b316f-142">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="b316f-143">Exemplo 13: usar o parâmetro InputObject com uma cadeia de caracteres vazia ou $null</span><span class="sxs-lookup"><span data-stu-id="b316f-143">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="b316f-144">Neste exemplo, o parâmetro **InputObject** especifica uma matriz que contém uma cadeia de caracteres vazia ( `''` ) e `$null` .</span><span class="sxs-lookup"><span data-stu-id="b316f-144">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="b316f-145">`Get-Random` retornará uma `a` cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="b316f-145">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="b316f-146">O Stinger vazio é exibido como uma linha em branco e `$null` retorna a um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b316f-146">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="b316f-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b316f-147">PARAMETERS</span></span>

### <span data-ttu-id="b316f-148">-Contagem</span><span class="sxs-lookup"><span data-stu-id="b316f-148">-Count</span></span>

<span data-ttu-id="b316f-149">Especifica o número de objetos aleatórios ou números a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="b316f-149">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="b316f-150">O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="b316f-150">The default is 1.</span></span>

<span data-ttu-id="b316f-151">Quando usado com `InputObject` , se o valor de **Count** excede o número de objetos na coleção, `Get-Random` retorna todos os objetos em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="b316f-151">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b316f-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b316f-152">-InputObject</span></span>

<span data-ttu-id="b316f-153">Especifica uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="b316f-153">Specifies a collection of objects.</span></span> <span data-ttu-id="b316f-154">`Get-Random` Obtém objetos aleatoriamente selecionados em ordem aleatória da coleção até o número especificado por **contagem** .</span><span class="sxs-lookup"><span data-stu-id="b316f-154">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count** .</span></span> <span data-ttu-id="b316f-155">Insira os objetos, uma variável que contenha os objetos ou um comando ou expressão que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="b316f-155">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="b316f-156">Também é possível canalizar uma coleção de objetos para o `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="b316f-156">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="b316f-157">A partir do PowerShell 7, o parâmetro **InputObject** aceita matrizes que podem conter uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="b316f-157">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="b316f-158">A matriz pode ser enviada ao pipeline ou como um valor de parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="b316f-158">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b316f-159">-Máximo</span><span class="sxs-lookup"><span data-stu-id="b316f-159">-Maximum</span></span>

<span data-ttu-id="b316f-160">Especifica um valor máximo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="b316f-160">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="b316f-161">`Get-Random` Retorna um valor menor que o máximo (não igual).</span><span class="sxs-lookup"><span data-stu-id="b316f-161">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="b316f-162">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="b316f-162">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="b316f-163">O valor de **Maximum** deve ser maior que (diferente de) o valor de **Minimum** .</span><span class="sxs-lookup"><span data-stu-id="b316f-163">The value of **Maximum** must be greater than (not equal to) the value of **Minimum** .</span></span> <span data-ttu-id="b316f-164">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="b316f-164">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="b316f-165">Em um computador de 64 bits, se o valor **mínimo** for um inteiro de 32 bits, o valor padrão de **máximo** será **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="b316f-165">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue** .</span></span>

<span data-ttu-id="b316f-166">Se o valor **mínimo** for um Double (um número de ponto flutuante), o valor padrão de **Maximum** será **Double. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="b316f-166">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue** .</span></span> <span data-ttu-id="b316f-167">Caso contrário, o valor padrão é **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="b316f-167">Otherwise, the default value is **Int32.MaxValue** .</span></span>

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

### <span data-ttu-id="b316f-168">-Mínimo</span><span class="sxs-lookup"><span data-stu-id="b316f-168">-Minimum</span></span>

<span data-ttu-id="b316f-169">Especifica um valor mínimo para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="b316f-169">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="b316f-170">Insira um inteiro, um número de ponto flutuante de precisão dupla ou um objeto que possa ser convertido em um número inteiro ou duplo, como uma cadeia de caracteres numérica ("100").</span><span class="sxs-lookup"><span data-stu-id="b316f-170">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="b316f-171">O valor padrão é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b316f-171">The default value is 0 (zero).</span></span>

<span data-ttu-id="b316f-172">O valor de **Minimum** deve ser menor que (diferente de) o valor de **Maximum** .</span><span class="sxs-lookup"><span data-stu-id="b316f-172">The value of **Minimum** must be less than (not equal to) the value of **Maximum** .</span></span> <span data-ttu-id="b316f-173">Se o valor **máximo** ou **mínimo** for um número de ponto flutuante, o `Get-Random` retornará um número de ponto flutuante selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="b316f-173">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="b316f-174">-Setsemente</span><span class="sxs-lookup"><span data-stu-id="b316f-174">-SetSeed</span></span>

<span data-ttu-id="b316f-175">Especifica um valor de semente para o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="b316f-175">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="b316f-176">Esse valor de semente é usado para o comando atual e para todos os comandos subsequentes `Get-Random` na sessão atual até que você use **setsemente** novamente ou feche a sessão.</span><span class="sxs-lookup"><span data-stu-id="b316f-176">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="b316f-177">Não é possível redefinir a semente para seu valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b316f-177">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="b316f-178">O parâmetro **setsemente** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="b316f-178">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="b316f-179">Por padrão, `Get-Random` o usa o método [RandomNumberGenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) para gerar um valor de semente.</span><span class="sxs-lookup"><span data-stu-id="b316f-179">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="b316f-180">Como o **setsemente** resulta em comportamento não aleatório, ele é normalmente usado apenas ao tentar reproduzir o comportamento, como ao depurar ou analisar um script que inclui `Get-Random` comandos.</span><span class="sxs-lookup"><span data-stu-id="b316f-180">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

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

### <span data-ttu-id="b316f-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b316f-181">CommonParameters</span></span>

<span data-ttu-id="b316f-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b316f-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b316f-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b316f-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b316f-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b316f-184">INPUTS</span></span>

### <span data-ttu-id="b316f-185">System.Object</span><span class="sxs-lookup"><span data-stu-id="b316f-185">System.Object</span></span>

<span data-ttu-id="b316f-186">É possível canalizar um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="b316f-186">You can pipe one or more objects.</span></span> <span data-ttu-id="b316f-187">`Get-Random` seleciona valores aleatoriamente dos objetos canalizados.</span><span class="sxs-lookup"><span data-stu-id="b316f-187">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="b316f-188">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b316f-188">OUTPUTS</span></span>

### <span data-ttu-id="b316f-189">System. Int32, System. Int64, sistema. Double</span><span class="sxs-lookup"><span data-stu-id="b316f-189">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="b316f-190">`Get-Random` Retorna um número inteiro ou de ponto flutuante ou um objeto selecionado aleatoriamente de uma coleção enviada.</span><span class="sxs-lookup"><span data-stu-id="b316f-190">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="b316f-191">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b316f-191">NOTES</span></span>

<span data-ttu-id="b316f-192">`Get-Random` define uma semente padrão para cada sessão com base no relógio de tempo do sistema quando a sessão é iniciada.</span><span class="sxs-lookup"><span data-stu-id="b316f-192">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="b316f-193">`Get-Random` Nem sempre retorna o mesmo tipo de dados que o valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="b316f-193">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="b316f-194">A tabela a seguir mostra o tipo de saída para cada um dos tipos de entrada numéricos.</span><span class="sxs-lookup"><span data-stu-id="b316f-194">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="b316f-195">Tipo de entrada</span><span class="sxs-lookup"><span data-stu-id="b316f-195">Input Type</span></span> | <span data-ttu-id="b316f-196">Tipo de saída</span><span class="sxs-lookup"><span data-stu-id="b316f-196">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="b316f-197">SByte</span><span class="sxs-lookup"><span data-stu-id="b316f-197">SByte</span></span>    |   <span data-ttu-id="b316f-198">Duplo</span><span class="sxs-lookup"><span data-stu-id="b316f-198">Double</span></span>    |
|    <span data-ttu-id="b316f-199">Byte</span><span class="sxs-lookup"><span data-stu-id="b316f-199">Byte</span></span>    |   <span data-ttu-id="b316f-200">Duplo</span><span class="sxs-lookup"><span data-stu-id="b316f-200">Double</span></span>    |
|   <span data-ttu-id="b316f-201">Int16</span><span class="sxs-lookup"><span data-stu-id="b316f-201">Int16</span></span>    |   <span data-ttu-id="b316f-202">Duplo</span><span class="sxs-lookup"><span data-stu-id="b316f-202">Double</span></span>    |
|   <span data-ttu-id="b316f-203">UInt16</span><span class="sxs-lookup"><span data-stu-id="b316f-203">UInt16</span></span>   |   <span data-ttu-id="b316f-204">Duplo</span><span class="sxs-lookup"><span data-stu-id="b316f-204">Double</span></span>    |
|   <span data-ttu-id="b316f-205">Int32</span><span class="sxs-lookup"><span data-stu-id="b316f-205">Int32</span></span>    |    <span data-ttu-id="b316f-206">Int32</span><span class="sxs-lookup"><span data-stu-id="b316f-206">Int32</span></span>    |
|   <span data-ttu-id="b316f-207">UInt32</span><span class="sxs-lookup"><span data-stu-id="b316f-207">UInt32</span></span>   |   <span data-ttu-id="b316f-208">Double</span><span class="sxs-lookup"><span data-stu-id="b316f-208">Double</span></span>    |
|   <span data-ttu-id="b316f-209">Int64</span><span class="sxs-lookup"><span data-stu-id="b316f-209">Int64</span></span>    |    <span data-ttu-id="b316f-210">Int64</span><span class="sxs-lookup"><span data-stu-id="b316f-210">Int64</span></span>    |
|   <span data-ttu-id="b316f-211">UInt64</span><span class="sxs-lookup"><span data-stu-id="b316f-211">UInt64</span></span>   |   <span data-ttu-id="b316f-212">Double</span><span class="sxs-lookup"><span data-stu-id="b316f-212">Double</span></span>    |
|   <span data-ttu-id="b316f-213">Double</span><span class="sxs-lookup"><span data-stu-id="b316f-213">Double</span></span>   |   <span data-ttu-id="b316f-214">Double</span><span class="sxs-lookup"><span data-stu-id="b316f-214">Double</span></span>    |
|   <span data-ttu-id="b316f-215">Simples</span><span class="sxs-lookup"><span data-stu-id="b316f-215">Single</span></span>   |   <span data-ttu-id="b316f-216">Duplo</span><span class="sxs-lookup"><span data-stu-id="b316f-216">Double</span></span>    |

<span data-ttu-id="b316f-217">A partir do Windows PowerShell 3,0, `Get-Random` dá suporte a inteiros de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b316f-217">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="b316f-218">No Windows PowerShell 2,0, todos os valores são convertidos em **System. Int32** .</span><span class="sxs-lookup"><span data-stu-id="b316f-218">In Windows PowerShell 2.0, all values are cast to **System.Int32** .</span></span>

<span data-ttu-id="b316f-219">A partir do PowerShell 7, o parâmetro **InputObject** no conjunto de parâmetros **RandomListItemParameterSet** aceita matrizes que contêm uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="b316f-219">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="b316f-220">Nas versões anteriores do PowerShell, apenas o parâmetro **máximo** no conjunto de parâmetros **RandomNumberParameterSet** aceitou uma cadeia de caracteres vazia ou `$null` .</span><span class="sxs-lookup"><span data-stu-id="b316f-220">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="b316f-221">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b316f-221">RELATED LINKS</span></span>
