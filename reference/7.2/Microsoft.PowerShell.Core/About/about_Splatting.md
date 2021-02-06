---
description: Descreve como usar nivelamento para passar parâmetros para comandos no PowerShell.
Locale: en-US
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: e028f43828afd69d645591ab20795689cb115e12
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595379"
---
# <a name="about-splatting"></a><span data-ttu-id="760f6-103">Sobre o nivelamento</span><span class="sxs-lookup"><span data-stu-id="760f6-103">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="760f6-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="760f6-104">Short description</span></span>

<span data-ttu-id="760f6-105">Descreve como usar nivelamento para passar parâmetros para comandos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="760f6-105">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="760f6-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="760f6-106">Long description</span></span>

<span data-ttu-id="760f6-107">Nivelamento é um método para passar uma coleção de valores de parâmetro para um comando como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="760f6-107">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="760f6-108">O PowerShell associa cada valor na coleção a um parâmetro de comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-108">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="760f6-109">Os valores de parâmetro Splatted são armazenados em variáveis nomeadas nivelamento, que se parecem com variáveis padrão, mas começam com um símbolo de arroba ( `@` ) em vez de um cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="760f6-109">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="760f6-110">O símbolo at informa ao PowerShell que você está passando uma coleção de valores, em vez de um único valor.</span><span class="sxs-lookup"><span data-stu-id="760f6-110">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="760f6-111">O nivelamento torna seus comandos mais curtos e fáceis de ler.</span><span class="sxs-lookup"><span data-stu-id="760f6-111">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="760f6-112">Você pode reutilizar os valores de nivelamento em chamadas de comando diferentes e usar nivelamento para passar valores de parâmetro da `$PSBoundParameters` variável automática para outros scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="760f6-112">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="760f6-113">A partir do Windows PowerShell 3,0, você também pode usar nivelamento para representar todos os parâmetros de um comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-113">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="760f6-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="760f6-114">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="760f6-115">Para fornecer valores de parâmetro para parâmetros posicionais, nos quais os nomes de parâmetro não são necessários, use a sintaxe de matriz.</span><span class="sxs-lookup"><span data-stu-id="760f6-115">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="760f6-116">Para fornecer pares de nome de parâmetro e valor, use a sintaxe da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="760f6-116">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="760f6-117">O valor de splatted pode aparecer em qualquer lugar na lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="760f6-117">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="760f6-118">Quando nivelamento, você não precisa usar uma tabela de hash ou uma matriz para passar todos os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="760f6-118">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="760f6-119">Você pode passar alguns parâmetros usando nivelamento e passar outros por posição ou por nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="760f6-119">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="760f6-120">Além disso, você pode fragmentação vários objetos em um único comando para não passar mais de um valor para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="760f6-120">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

<span data-ttu-id="760f6-121">A partir do PowerShell 7,1, você pode substituir um parâmetro splatted definindo explicitamente um parâmetro em um comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-121">As of PowerShell 7.1, you can override a splatted parameter by explicitly defining a parameter in a command.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="760f6-122">Nivelamento com tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="760f6-122">Splatting with hash tables</span></span>

<span data-ttu-id="760f6-123">Use uma tabela de hash para fragmentação pares de nome e valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="760f6-123">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="760f6-124">Você pode usar esse formato para todos os tipos de parâmetro, incluindo parâmetros posicionais e de switch.</span><span class="sxs-lookup"><span data-stu-id="760f6-124">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="760f6-125">Os parâmetros posicionais devem ser atribuídos por nome.</span><span class="sxs-lookup"><span data-stu-id="760f6-125">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="760f6-126">Os exemplos a seguir comparam dois `Copy-Item` comandos que copiam o arquivo de Test.txt para o arquivo de Test2.txt no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="760f6-126">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="760f6-127">O primeiro exemplo usa o formato tradicional no qual os nomes de parâmetro são incluídos.</span><span class="sxs-lookup"><span data-stu-id="760f6-127">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="760f6-128">O segundo exemplo usa a tabela de hash nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-128">The second example uses hash table splatting.</span></span> <span data-ttu-id="760f6-129">O primeiro comando cria uma tabela de hash de pares parâmetro-nome e parâmetro-valor e o armazena na `$HashArguments` variável.</span><span class="sxs-lookup"><span data-stu-id="760f6-129">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="760f6-130">O segundo comando usa a `$HashArguments` variável em um comando com nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-130">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="760f6-131">O símbolo de arroba ( `@HashArguments` ) substitui o sinal de dólar ( `$HashArguments` ) no comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-131">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="760f6-132">Para fornecer um valor para o parâmetro de opção **WhatIf** , use `$True` ou `$False` .</span><span class="sxs-lookup"><span data-stu-id="760f6-132">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="760f6-133">No primeiro comando, o símbolo de arroba ( `@` ) indica uma tabela de hash, não um valor splatted.</span><span class="sxs-lookup"><span data-stu-id="760f6-133">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="760f6-134">A sintaxe para tabelas de hash no PowerShell é: `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="760f6-134">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="760f6-135">Nivelamento com matrizes</span><span class="sxs-lookup"><span data-stu-id="760f6-135">Splatting with arrays</span></span>

<span data-ttu-id="760f6-136">Use uma matriz para fragmentação valores de parâmetros posicionais, que não exigem nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="760f6-136">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="760f6-137">Os valores devem estar na ordem de número de posição na matriz.</span><span class="sxs-lookup"><span data-stu-id="760f6-137">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="760f6-138">Os exemplos a seguir comparam dois `Copy-Item` comandos que copiam o arquivo de Test.txt para o arquivo de Test2.txt no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="760f6-138">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="760f6-139">O primeiro exemplo usa o formato tradicional no qual os nomes de parâmetro são omitidos.</span><span class="sxs-lookup"><span data-stu-id="760f6-139">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="760f6-140">Os valores de parâmetro aparecem na ordem de posição no comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-140">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="760f6-141">O segundo exemplo usa a matriz nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-141">The second example uses array splatting.</span></span> <span data-ttu-id="760f6-142">O primeiro comando cria uma matriz dos valores de parâmetro e armazena-o na `$ArrayArguments` variável.</span><span class="sxs-lookup"><span data-stu-id="760f6-142">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="760f6-143">Os valores estão na ordem de posição na matriz.</span><span class="sxs-lookup"><span data-stu-id="760f6-143">The values are in position order in the array.</span></span> <span data-ttu-id="760f6-144">O segundo comando usa a `$ArrayArguments` variável em um comando em nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-144">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="760f6-145">O símbolo de arroba ( `@ArrayArguments` ) substitui o sinal de dólar ( `$ArrayArguments` ) no comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-145">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="760f6-146">Usando o parâmetro ArgumentList</span><span class="sxs-lookup"><span data-stu-id="760f6-146">Using the ArgumentList parameter</span></span>

<span data-ttu-id="760f6-147">Vários cmdlets têm um parâmetro **ArgumentList** que é usado para passar valores de parâmetro para um bloco de script que é executado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="760f6-147">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="760f6-148">O parâmetro **ArgumentList** usa uma matriz de valores que é passada para o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="760f6-148">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="760f6-149">O PowerShell está efetivamente usando array nivelamento para associar os valores aos parâmetros do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="760f6-149">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="760f6-150">Ao usar **ArgumentList**, se você precisar passar uma matriz como um único objeto associado a um único parâmetro, deverá encapsular a matriz como o único elemento de outra matriz.</span><span class="sxs-lookup"><span data-stu-id="760f6-150">When using **ArgumentList**, if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="760f6-151">O exemplo a seguir tem um bloco de script que usa um único parâmetro que é uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="760f6-151">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```
<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
<span data-ttu-id="760f6-152">Neste exemplo, somente o primeiro item em `$array` é passado para o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="760f6-152">In this example, only the first item in `$array` is passed to the script block.</span></span>

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

<span data-ttu-id="760f6-153">Neste exemplo, `$array` é encapsulado em uma matriz para que toda a matriz seja passada para o bloco de script como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="760f6-153">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="760f6-154">Exemplos</span><span class="sxs-lookup"><span data-stu-id="760f6-154">Examples</span></span>

### <a name="example-1-reuse-splatted-parameters-in-different-commands"></a><span data-ttu-id="760f6-155">Exemplo 1: reutilizar parâmetros splatted em comandos diferentes</span><span class="sxs-lookup"><span data-stu-id="760f6-155">Example 1: Reuse splatted parameters in different commands</span></span>

<span data-ttu-id="760f6-156">Este exemplo mostra como reutilizar valores splatted em comandos diferentes.</span><span class="sxs-lookup"><span data-stu-id="760f6-156">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="760f6-157">Os comandos neste exemplo usam o `Write-Host` cmdlet para gravar mensagens no console do programa host.</span><span class="sxs-lookup"><span data-stu-id="760f6-157">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="760f6-158">Ele usa nivelamento para especificar as cores de primeiro e segundo plano.</span><span class="sxs-lookup"><span data-stu-id="760f6-158">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="760f6-159">Para alterar as cores de todos os comandos, basta alterar o valor da `$Colors` variável.</span><span class="sxs-lookup"><span data-stu-id="760f6-159">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="760f6-160">O primeiro comando cria uma tabela de hash de nomes e valores de parâmetro e armazena a tabela de hash na `$Colors` variável.</span><span class="sxs-lookup"><span data-stu-id="760f6-160">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="760f6-161">O segundo e o terceiro comandos usam a `$Colors` variável para nivelamento em um `Write-Host` comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-161">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="760f6-162">Para usar o `$Colors variable` , substitua o cifrão ( `$Colors` ) por um símbolo de arroba ( `@Colors` ).</span><span class="sxs-lookup"><span data-stu-id="760f6-162">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

### <a name="example-2-forward-parameters-using-psboundparameters"></a><span data-ttu-id="760f6-163">Exemplo 2: encaminhar parâmetros usando $PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="760f6-163">Example 2: Forward parameters using $PSBoundParameters</span></span>

<span data-ttu-id="760f6-164">Este exemplo mostra como encaminhar seus parâmetros para outros comandos usando nivelamento e a `$PSBoundParameters` variável automática.</span><span class="sxs-lookup"><span data-stu-id="760f6-164">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="760f6-165">A `$PSBoundParameters` variável automática é um objeto de dicionário (System. Collections. Generic. Dictionary) que contém todos os nomes de parâmetro e valores que são usados quando um script ou uma função é executada.</span><span class="sxs-lookup"><span data-stu-id="760f6-165">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="760f6-166">No exemplo a seguir, usamos a `$PSBoundParameters` variável para encaminhar os valores de parâmetros passados para um script ou função da `Test2` função para a `Test1` função.</span><span class="sxs-lookup"><span data-stu-id="760f6-166">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="760f6-167">Ambas as chamadas para a `Test1` função de `Test2` usam nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-167">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

### <a name="example-3-override-splatted-parameters-with-explicitly-defined-parameters"></a><span data-ttu-id="760f6-168">Exemplo 3: Substituir parâmetros splatted por parâmetros definidos explicitamente</span><span class="sxs-lookup"><span data-stu-id="760f6-168">Example 3: Override splatted parameters with explicitly defined parameters</span></span>

<span data-ttu-id="760f6-169">Este exemplo mostra como substituir um parâmetro splatted usando parâmetros definidos explicitamente.</span><span class="sxs-lookup"><span data-stu-id="760f6-169">This example shows how to override a splatted parameter using explicitly defined parameters.</span></span> <span data-ttu-id="760f6-170">Isso é útil quando você não deseja criar uma nova tabela de hash ou alterar um valor na tabela de hash que você está usando para fragmentação.</span><span class="sxs-lookup"><span data-stu-id="760f6-170">This is useful when you don't want to build a new hashtable or change a value in the hashtable you are using to splat.</span></span>

<span data-ttu-id="760f6-171">A `$commonParams` variável armazena os parâmetros para criar máquinas virtuais no `East US` local.</span><span class="sxs-lookup"><span data-stu-id="760f6-171">The `$commonParams` variable stores the parameters to create virtual machines in the `East US` location.</span></span> <span data-ttu-id="760f6-172">A `$allVms` variável é uma lista de máquinas virtuais a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="760f6-172">The `$allVms` variable is a list of virtual machines to create.</span></span> <span data-ttu-id="760f6-173">Vamos fazer um loop pela lista e usar `$commonParams` para fragmentação os parâmetros para criar cada máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="760f6-173">We loop through the list and use `$commonParams` to splat the parameters to create each virtual machine.</span></span> <span data-ttu-id="760f6-174">No entanto, queremos `myVM2` ser criados em uma região diferente das outras máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="760f6-174">However, we want `myVM2` to be created in a different region than the other virtual machines.</span></span> <span data-ttu-id="760f6-175">Em vez de ajustar a `$commonParams` Hashtable, você pode definir explicitamente o parâmetro **Location** no `New-AzVm` para substituir o valor da `Location` chave em `$commonParams` .</span><span class="sxs-lookup"><span data-stu-id="760f6-175">Instead of adjusting the `$commonParams` hashtable, you can explicitly define the **Location** parameter in `New-AzVm` to supersede the value of the `Location` key in `$commonParams`.</span></span>

```powershell
$commonParams = @{
    ResourceGroupName = "myResourceGroup"
    Location = "East US"
    VirtualNetworkName = "myVnet"
    SubnetName = "mySubnet"
    SecurityGroupName = "myNetworkSecurityGroup"
    PublicIpAddressName = "myPublicIpAddress"
}

$allVms = @('myVM1','myVM2','myVM3',)

foreach ($vm in $allVms)
{
    if ($vm -eq 'myVM2')
    {
        New-AzVm @commonParams -Name $vm -Location "West US"
    }
    else
    {
        New-AzVm @commonParams -Name $vm
    }
}
```

## <a name="splatting-command-parameters"></a><span data-ttu-id="760f6-176">Parâmetros do comando nivelamento</span><span class="sxs-lookup"><span data-stu-id="760f6-176">Splatting command parameters</span></span>

<span data-ttu-id="760f6-177">Você pode usar nivelamento para representar os parâmetros de um comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-177">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="760f6-178">Essa técnica é útil quando você está criando uma função de proxy, ou seja, uma função que chama outro comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-178">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="760f6-179">Esse recurso é introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="760f6-179">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="760f6-180">Para fragmentação os parâmetros de um comando, use `@Args` para representar os parâmetros de comando.</span><span class="sxs-lookup"><span data-stu-id="760f6-180">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="760f6-181">Essa técnica é mais fácil do que enumerar parâmetros de comando e funciona sem revisão, mesmo que os parâmetros do comando chamado sejam alterados.</span><span class="sxs-lookup"><span data-stu-id="760f6-181">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="760f6-182">O recurso usa a `$Args` variável automática, que contém todos os valores de parâmetro não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="760f6-182">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="760f6-183">Por exemplo, a função a seguir chama o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="760f6-183">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="760f6-184">Nessa função, `@Args` representa todos os parâmetros do `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="760f6-184">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="760f6-185">Quando você usa a `Get-MyProcess` função, todos os parâmetros e valores de parâmetros não atribuídos são passados para `@Args` , conforme mostrado nos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="760f6-185">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

<span data-ttu-id="760f6-186">Você pode usar `@Args` o em uma função que tenha parâmetros explicitamente declarados.</span><span class="sxs-lookup"><span data-stu-id="760f6-186">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="760f6-187">Você pode usá-lo mais de uma vez em uma função, mas todos os parâmetros inseridos são passados para todas as instâncias do `@Args` , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="760f6-187">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a><span data-ttu-id="760f6-188">Observações</span><span class="sxs-lookup"><span data-stu-id="760f6-188">Notes</span></span>

<span data-ttu-id="760f6-189">Se você fizer uma função em uma função avançada usando os atributos **CmdletBinding** ou **parâmetro** , a `$args` variável automática não estará mais disponível na função.</span><span class="sxs-lookup"><span data-stu-id="760f6-189">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="760f6-190">As funções avançadas exigem definição de parâmetro explícita.</span><span class="sxs-lookup"><span data-stu-id="760f6-190">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="760f6-191">A DSC (configuração de estado desejado) do PowerShell não foi projetada para usar nivelamento.</span><span class="sxs-lookup"><span data-stu-id="760f6-191">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="760f6-192">Você não pode usar nivelamento para passar valores para um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="760f6-192">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="760f6-193">Para obter mais informações, consulte o artigo Gael colas " [Getnivelamento DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span><span class="sxs-lookup"><span data-stu-id="760f6-193">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="760f6-194">Consulte também</span><span class="sxs-lookup"><span data-stu-id="760f6-194">See also</span></span>

[<span data-ttu-id="760f6-195">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="760f6-195">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="760f6-196">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="760f6-196">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="760f6-197">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="760f6-197">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="760f6-198">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="760f6-198">about_Parameters</span></span>](about_Parameters.md)
