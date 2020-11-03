---
description: Explica como adicionar parâmetros a funções avançadas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 4123d71392f8b32df8d04033d85476cb18b39736
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "93196647"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="5d9a7-104">Sobre os parâmetros avançados do Functions</span><span class="sxs-lookup"><span data-stu-id="5d9a7-104">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="5d9a7-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="5d9a7-105">Short description</span></span>

<span data-ttu-id="5d9a7-106">Explica como adicionar parâmetros a funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-106">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="5d9a7-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="5d9a7-107">Long description</span></span>

<span data-ttu-id="5d9a7-108">Você pode adicionar parâmetros às funções avançadas que escreve e usar atributos de parâmetro e argumentos para limitar os valores de parâmetro que os usuários de função enviam com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-108">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="5d9a7-109">Os parâmetros que você adiciona à função estão disponíveis para os usuários além dos parâmetros comuns que o PowerShell adiciona automaticamente a todos os cmdlets e funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-109">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="5d9a7-110">Para obter mais informações sobre os parâmetros comuns do PowerShell, consulte [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-110">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="5d9a7-111">A partir do PowerShell 3,0, você pode usar nivelamento com `@Args` para representar os parâmetros em um comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-111">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="5d9a7-112">Nivelamento é válido em funções simples e avançadas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-112">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="5d9a7-113">Para obter mais informações, consulte [about_Functions](about_Functions.md) e [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-113">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="5d9a7-114">Conversão de tipo de valores de parâmetro</span><span class="sxs-lookup"><span data-stu-id="5d9a7-114">Type conversion of parameter values</span></span>

<span data-ttu-id="5d9a7-115">Quando você fornece cadeias de caracteres como argumentos para parâmetros que esperam um tipo diferente, o PowerShell converte implicitamente as cadeias de caracteres no tipo de destino do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-115">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="5d9a7-116">As funções avançadas executam a análise invariável de cultura de valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-116">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="5d9a7-117">Por outro lado, uma conversão sensível à cultura é executada durante a associação de parâmetro para cmdlets compilados.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-117">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="5d9a7-118">Neste exemplo, criamos um cmdlet e uma função de script que usam um `[datetime]` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-118">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="5d9a7-119">A cultura atual é alterada para usar as configurações de alemão.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-119">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="5d9a7-120">Uma data formatada em alemão é passada para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-120">A German-formatted date is passed to the parameter.</span></span>

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

<span data-ttu-id="5d9a7-121">Como mostrado acima, os cmdlets usam a análise sensível à cultura para converter a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-121">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

<span data-ttu-id="5d9a7-122">As funções avançadas usam a análise de cultura invariável, o que resulta no erro a seguir.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-122">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a><span data-ttu-id="5d9a7-123">Parâmetros estáticos</span><span class="sxs-lookup"><span data-stu-id="5d9a7-123">Static parameters</span></span>

<span data-ttu-id="5d9a7-124">Parâmetros estáticos são parâmetros que estão sempre disponíveis na função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-124">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="5d9a7-125">A maioria dos parâmetros nos cmdlets e scripts do PowerShell são parâmetros estáticos.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-125">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="5d9a7-126">O exemplo a seguir mostra a declaração de um parâmetro **ComputerName** que tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-126">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="5d9a7-127">É obrigatório (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-127">It's mandatory (required).</span></span>
- <span data-ttu-id="5d9a7-128">Ele usa a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-128">It takes input from the pipeline.</span></span>
- <span data-ttu-id="5d9a7-129">Ele usa uma matriz de cadeias de caracteres como entrada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-129">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="5d9a7-130">Atributos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="5d9a7-130">Attributes of parameters</span></span>

<span data-ttu-id="5d9a7-131">Esta seção descreve os atributos que você pode adicionar a parâmetros de função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-131">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="5d9a7-132">Todos os atributos são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-132">All attributes are optional.</span></span> <span data-ttu-id="5d9a7-133">No entanto, se você omitir o atributo **CmdletBinding** , para ser reconhecido como uma função avançada, a função deverá incluir o atributo **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-133">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="5d9a7-134">Você pode adicionar um ou vários atributos em cada declaração de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-134">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="5d9a7-135">Não há limite para o número de atributos que você pode adicionar a uma declaração de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-135">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="5d9a7-136">Atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="5d9a7-136">Parameter attribute</span></span>

<span data-ttu-id="5d9a7-137">O atributo de **parâmetro** é usado para declarar os atributos dos parâmetros de função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-137">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="5d9a7-138">O atributo de **parâmetro** é opcional e você pode omiti-lo se nenhum dos parâmetros de suas funções precisarem de atributos.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-138">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="5d9a7-139">Mas, para ser reconhecido como uma função avançada, em vez de uma função simples, uma função deve ter o atributo **CmdletBinding** ou o atributo de **parâmetro** , ou ambos.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-139">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="5d9a7-140">O atributo **Parameter** tem argumentos que definem as características do parâmetro, como se o parâmetro é obrigatório ou opcional.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-140">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="5d9a7-141">Use a sintaxe a seguir para declarar o atributo de **parâmetro** , um argumento e um valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-141">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="5d9a7-142">Os parênteses que delimitam o argumento e seu valor devem seguir o **parâmetro** sem nenhum espaço intermediário.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-142">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="5d9a7-143">Use vírgulas para separar os argumentos entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-143">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="5d9a7-144">Use a sintaxe a seguir para declarar dois argumentos do atributo **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-144">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="5d9a7-145">Os tipos de argumento boolianos do atributo de **parâmetro** são padrão como **false** quando omitidos do atributo de **parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-145">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="5d9a7-146">Defina o valor do argumento como `$true` ou apenas liste o argumento por nome.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-146">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="5d9a7-147">Por exemplo, os atributos de **parâmetro** a seguir são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-147">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="5d9a7-148">Se você usar o atributo **Parameter** sem argumentos, como uma alternativa ao uso do atributo **CmdletBinding** , os parênteses que seguem o nome do atributo ainda serão necessários.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-148">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="5d9a7-149">Argumento obrigatório</span><span class="sxs-lookup"><span data-stu-id="5d9a7-149">Mandatory argument</span></span>

<span data-ttu-id="5d9a7-150">O `Mandatory` argumento indica que o parâmetro é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-150">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="5d9a7-151">Se esse argumento não for especificado, o parâmetro será opcional.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-151">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="5d9a7-152">O exemplo a seguir declara o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-152">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="5d9a7-153">Ele usa o `Mandatory` argumento para tornar o parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-153">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="5d9a7-154">Argumento de posição</span><span class="sxs-lookup"><span data-stu-id="5d9a7-154">Position argument</span></span>

<span data-ttu-id="5d9a7-155">O `Position` argumento determina se o nome do parâmetro é necessário quando o parâmetro é usado em um comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-155">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="5d9a7-156">Quando uma declaração de parâmetro inclui o `Position` argumento, o nome do parâmetro pode ser omitido e o PowerShell identifica o valor do parâmetro sem nome por sua posição, ou ordem, na lista de valores de parâmetro não nomeados no comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-156">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="5d9a7-157">Se o `Position` argumento não for especificado, o nome do parâmetro ou um alias de nome de parâmetro ou abreviatura, deverá preceder o valor do parâmetro sempre que o parâmetro for usado em um comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-157">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="5d9a7-158">Por padrão, todos os parâmetros de função são posicionais.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-158">By default, all function parameters are positional.</span></span> <span data-ttu-id="5d9a7-159">O PowerShell atribui números de posição a parâmetros na ordem em que os parâmetros são declarados na função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-159">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="5d9a7-160">Para desabilitar esse recurso, defina o valor do `PositionalBinding` argumento do atributo **CmdletBinding** como `$False` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-160">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="5d9a7-161">O `Position` argumento tem precedência sobre o valor do `PositionalBinding` argumento do atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-161">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="5d9a7-162">Para obter mais informações, consulte `PositionalBinding` em [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-162">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="5d9a7-163">O valor do `Position` argumento é especificado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-163">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="5d9a7-164">Um valor de posição de **0** representa a primeira posição no comando, um valor de posição **1** representa a segunda posição no comando e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-164">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="5d9a7-165">Se uma função não tiver parâmetros posicionais, o PowerShell atribuirá posições a cada parâmetro com base na ordem em que os parâmetros são declarados.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-165">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="5d9a7-166">No entanto, como prática recomendada, não confie nessa atribuição.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-166">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="5d9a7-167">Quando desejar que os parâmetros sejam posicionais, use o `Position` argumento.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-167">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="5d9a7-168">O exemplo a seguir declara o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-168">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="5d9a7-169">Ele usa o `Position` argumento com um valor de **0** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-169">It uses the `Position` argument with a value of **0** .</span></span> <span data-ttu-id="5d9a7-170">Como resultado, quando `-ComputerName` é omitido do comando, seu valor deve ser o primeiro ou apenas o valor de parâmetro não nomeado no comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-170">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="5d9a7-171">Argumento ParameterSetName</span><span class="sxs-lookup"><span data-stu-id="5d9a7-171">ParameterSetName argument</span></span>

<span data-ttu-id="5d9a7-172">O `ParameterSetName` argumento especifica o conjunto de parâmetros ao qual um parâmetro pertence.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-172">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="5d9a7-173">Se nenhum conjunto de parâmetros for especificado, o parâmetro pertencerá a todos os conjuntos de parâmetros definidos pela função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-173">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="5d9a7-174">Portanto, para ser exclusivo, cada conjunto de parâmetros deve ter pelo menos um parâmetro que não seja membro de nenhum outro conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-174">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="5d9a7-175">Para um cmdlet ou uma função, há um limite de conjuntos de parâmetros 32.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-175">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="5d9a7-176">O exemplo a seguir declara um parâmetro **ComputerName** no conjunto de `Computer` parâmetros, um parâmetro **username** no conjunto de `User` parâmetros e um parâmetro **Summary** em ambos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-176">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

<span data-ttu-id="5d9a7-177">Você pode especificar apenas um `ParameterSetName` valor em cada argumento e apenas um `ParameterSetName` argumento em cada atributo de **parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-177">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="5d9a7-178">Para indicar que um parâmetro aparece em mais de um conjunto de parâmetros, adicione atributos de **parâmetro** adicionais.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-178">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="5d9a7-179">O exemplo a seguir adiciona explicitamente o parâmetro **Summary** aos `Computer` `User` conjuntos de parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-179">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="5d9a7-180">O parâmetro **Summary** é opcional no `Computer` conjunto de parâmetros e obrigatório no `User` conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-180">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

<span data-ttu-id="5d9a7-181">Para obter mais informações sobre conjuntos de parâmetros, consulte [sobre conjuntos de parâmetros](about_parameter_sets.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-181">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="5d9a7-182">Argumento ValueFromPipeline</span><span class="sxs-lookup"><span data-stu-id="5d9a7-182">ValueFromPipeline argument</span></span>

<span data-ttu-id="5d9a7-183">O `ValueFromPipeline` argumento indica que o parâmetro aceita entrada de um objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-183">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="5d9a7-184">Especifique esse argumento se a função aceitar o objeto inteiro, não apenas uma propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-184">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="5d9a7-185">O exemplo a seguir declara um parâmetro **ComputerName** que é obrigatório e aceita um objeto que é passado para a função do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-185">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="5d9a7-186">Argumento ValueFromPipelineByPropertyName</span><span class="sxs-lookup"><span data-stu-id="5d9a7-186">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="5d9a7-187">O `ValueFromPipelineByPropertyName` argumento indica que o parâmetro aceita entrada de uma propriedade de um objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-187">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="5d9a7-188">A propriedade do objeto deve ter o mesmo nome ou alias que o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-188">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="5d9a7-189">Por exemplo, se a função tiver um parâmetro **ComputerName** e o objeto piped tiver uma propriedade **ComputerName** , o valor da propriedade **ComputerName** será atribuído ao parâmetro **ComputerName** da função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-189">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="5d9a7-190">O exemplo a seguir declara um parâmetro **ComputerName** que é obrigatório e aceita a entrada da propriedade **ComputerName** do objeto que é passada para a função por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-190">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="5d9a7-191">Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de _ligação de atraso_ no parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-191">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="5d9a7-192">O bloco de script de _ligação de atraso_ é executado automaticamente durante o **parâmetrobinding** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-192">The _delay-bind_ script block is run automatically during **ParameterBinding** .</span></span> <span data-ttu-id="5d9a7-193">O resultado é associado ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-193">The result is bound to the parameter.</span></span> <span data-ttu-id="5d9a7-194">A associação de atraso não funciona para parâmetros definidos como tipo `ScriptBlock` ou `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-194">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="5d9a7-195">O bloco de script é passado _sem_ ser invocado.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-195">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="5d9a7-196">Você pode ler sobre blocos _de script de ligação de atraso_ aqui [about_Script_Blocks. MD](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-196">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="5d9a7-197">Argumento ValueFromRemainingArguments</span><span class="sxs-lookup"><span data-stu-id="5d9a7-197">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="5d9a7-198">O `ValueFromRemainingArguments` argumento indica que o parâmetro aceita todos os valores do parâmetro no comando que não estão atribuídos a outros parâmetros da função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-198">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="5d9a7-199">Há um problema conhecido para usar coleções com **ValueFromRemainingArguments** , em que a coleção passada é tratada como um único elemento.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-199">There's a known issue for using collections with **ValueFromRemainingArguments** where the passed-in collection is treated as a single element.</span></span>

<span data-ttu-id="5d9a7-200">O exemplo a seguir demonstra esse problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-200">The following example demonstrates this known issue.</span></span> <span data-ttu-id="5d9a7-201">O parâmetro **restante** deve conter **um** no **índice 0** e **dois** no **índice 1** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-201">The **Remaining** parameter should contain **one** at **index 0** and **two** at **index 1** .</span></span>
<span data-ttu-id="5d9a7-202">Em vez disso, ambos os elementos são combinados em uma única entidade.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-202">Instead, both elements are combined into a single entity.</span></span>

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 1 elements
0: one two
```

> [!NOTE]
> <span data-ttu-id="5d9a7-203">Esse problema foi resolvido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-203">This issue is resolved in PowerShell 6.2.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="5d9a7-204">Argumento HelpMessage</span><span class="sxs-lookup"><span data-stu-id="5d9a7-204">HelpMessage argument</span></span>

<span data-ttu-id="5d9a7-205">O `HelpMessage` argumento especifica uma cadeia de caracteres que contém uma breve descrição do parâmetro ou seu valor.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-205">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="5d9a7-206">O PowerShell exibe essa mensagem no prompt que aparece quando um valor de parâmetro obrigatório está ausente em um comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-206">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="5d9a7-207">Esse argumento não tem nenhum efeito nos parâmetros opcionais.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-207">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="5d9a7-208">O exemplo a seguir declara um parâmetro **ComputerName** obrigatório e uma mensagem de ajuda que explica o valor do parâmetro esperado.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-208">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="5d9a7-209">Se não houver outra sintaxe de [Ajuda baseada em comentários](./about_comment_based_help.md) para a função (por exemplo, `.SYNOPSIS` ), essa mensagem também aparecerá na `Get-Help` saída.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-209">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="5d9a7-210">Atributo de alias</span><span class="sxs-lookup"><span data-stu-id="5d9a7-210">Alias attribute</span></span>

<span data-ttu-id="5d9a7-211">O atributo **alias** estabelece um nome alternativo para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-211">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="5d9a7-212">Não há limite para o número de aliases que você pode atribuir a um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-212">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="5d9a7-213">O exemplo a seguir mostra uma declaração de parâmetro que adiciona os aliases **CN** e **MachineName** ao parâmetro **ComputerName** obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-213">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="5d9a7-214">Atributo SupportsWildcards</span><span class="sxs-lookup"><span data-stu-id="5d9a7-214">SupportsWildcards attribute</span></span>

<span data-ttu-id="5d9a7-215">O atributo **SupportsWildcards** é usado para indicar que o parâmetro aceita valores curinga.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-215">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="5d9a7-216">O exemplo a seguir mostra uma declaração de parâmetro para um parâmetro de **caminho** obrigatório que dá suporte a valores curinga.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-216">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="5d9a7-217">O uso desse atributo não habilita automaticamente o suporte a curingas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-217">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="5d9a7-218">O desenvolvedor do cmdlet deve implementar o código para manipular a entrada curinga.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-218">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="5d9a7-219">Os curingas com suporte podem variar de acordo com a API subjacente ou o provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-219">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="5d9a7-220">Para obter mais informações, consulte [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-220">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="5d9a7-221">Atributos de validação de parâmetro e variável</span><span class="sxs-lookup"><span data-stu-id="5d9a7-221">Parameter and variable validation attributes</span></span>

<span data-ttu-id="5d9a7-222">Atributos de validação direcionam o PowerShell para testar os valores de parâmetro que os usuários enviam quando chamam a função avançada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-222">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="5d9a7-223">Se os valores de parâmetro falharem no teste, um erro será gerado e a função não será chamada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-223">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="5d9a7-224">A validação de parâmetro é aplicada somente à entrada fornecida e quaisquer outros valores como valores padrão não são validados.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-224">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="5d9a7-225">Você também pode usar os atributos de validação para restringir os valores que os usuários podem especificar para variáveis.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-225">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="5d9a7-226">Quando você usa um conversor de tipo junto com um atributo de validação, o conversor de tipo precisa ser definido antes do atributo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-226">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="5d9a7-227">Atributo de validação AllowNull</span><span class="sxs-lookup"><span data-stu-id="5d9a7-227">AllowNull validation attribute</span></span>

<span data-ttu-id="5d9a7-228">O atributo **AllowNull** permite que o valor de um parâmetro obrigatório seja `$null` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-228">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="5d9a7-229">O exemplo a seguir declara um parâmetro **ComputerInfo** de Hashtable que pode ter um valor **nulo** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-229">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="5d9a7-230">O atributo **AllowNull** não funcionará se o conversor de tipo estiver definido como cadeia de caracteres, pois o tipo de cadeia de caracteres não aceitará um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-230">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="5d9a7-231">Você pode usar o atributo **AllowEmptyString** para este cenário.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-231">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="5d9a7-232">Atributo de validação AllowEmptyString</span><span class="sxs-lookup"><span data-stu-id="5d9a7-232">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="5d9a7-233">O atributo **AllowEmptyString** permite que o valor de um parâmetro obrigatório seja uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-233">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="5d9a7-234">O exemplo a seguir declara um parâmetro **ComputerName** que pode ter um valor de cadeia de caracteres vazio.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-234">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="5d9a7-235">Atributo de validação AllowEmptyCollection</span><span class="sxs-lookup"><span data-stu-id="5d9a7-235">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="5d9a7-236">O atributo **AllowEmptyCollection** permite que o valor de um parâmetro obrigatório seja uma coleção vazia `@()` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-236">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="5d9a7-237">O exemplo a seguir declara um parâmetro **ComputerName** que pode ter um valor de coleção Vazio.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-237">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="5d9a7-238">Atributo de validação ValidateCount</span><span class="sxs-lookup"><span data-stu-id="5d9a7-238">ValidateCount validation attribute</span></span>

<span data-ttu-id="5d9a7-239">O atributo **ValidateCount** especifica o número mínimo e máximo de valores de parâmetro que um parâmetro aceita.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-239">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="5d9a7-240">O PowerShell gerará um erro se o número de valores de parâmetro no comando que chama a função estiver fora desse intervalo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-240">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="5d9a7-241">A declaração de parâmetro a seguir cria um parâmetro **ComputerName** que usa um para cinco valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-241">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="5d9a7-242">Atributo de validação ValidateLength</span><span class="sxs-lookup"><span data-stu-id="5d9a7-242">ValidateLength validation attribute</span></span>

<span data-ttu-id="5d9a7-243">O atributo **ValidateLength** especifica o número mínimo e máximo de caracteres em um parâmetro ou valor de variável.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-243">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="5d9a7-244">O PowerShell gerará um erro se o comprimento de um valor especificado para um parâmetro ou uma variável estiver fora do intervalo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-244">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="5d9a7-245">No exemplo a seguir, cada nome de computador deve ter de um a dez caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-245">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="5d9a7-246">No exemplo a seguir, o valor da variável `$number` deve ter no mínimo um caractere de comprimento e no máximo dez caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-246">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="5d9a7-247">Neste exemplo, o valor de `01` é encapsulado entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-247">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="5d9a7-248">O atributo **ValidateLength** não aceitará um número sem ser quebrado entre aspas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-248">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="5d9a7-249">Atributo de validação ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="5d9a7-249">ValidatePattern validation attribute</span></span>

<span data-ttu-id="5d9a7-250">O atributo **ValidatePattern** especifica uma expressão regular que é comparada ao parâmetro ou ao valor da variável.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-250">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="5d9a7-251">O PowerShell gerará um erro se o valor não corresponder ao padrão de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-251">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="5d9a7-252">No exemplo a seguir, o valor do parâmetro deve conter um número de quatro dígitos e cada dígito deve ser um número zero a nove.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-252">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="5d9a7-253">No exemplo a seguir, o valor da variável `$number` deve ser exatamente um número de quatro dígitos e cada dígito deve ser um número zero a nove.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-253">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="5d9a7-254">Atributo de validação ValidateRange</span><span class="sxs-lookup"><span data-stu-id="5d9a7-254">ValidateRange validation attribute</span></span>

<span data-ttu-id="5d9a7-255">O atributo **ValidateRange** especifica um intervalo numérico para cada parâmetro ou valor de variável.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-255">The **ValidateRange** attribute specifies a numeric range for each parameter or variable value.</span></span> <span data-ttu-id="5d9a7-256">O PowerShell gerará um erro se qualquer valor estiver fora desse intervalo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-256">PowerShell generates an error if any value is outside that range.</span></span> <span data-ttu-id="5d9a7-257">No exemplo a seguir, o valor do parâmetro de **tentativas** deve estar entre zero e dez.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-257">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="5d9a7-258">No exemplo a seguir, o valor da variável `$number` deve estar entre zero e dez.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-258">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="5d9a7-259">Atributo de validação ValidateScript</span><span class="sxs-lookup"><span data-stu-id="5d9a7-259">ValidateScript validation attribute</span></span>

<span data-ttu-id="5d9a7-260">O atributo **ValidateScript** especifica um script que é usado para validar um parâmetro ou valor de variável.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-260">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="5d9a7-261">O PowerShell canaliza o valor para o script e gera um erro se o script retorna `$false` ou se o script gera uma exceção.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-261">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="5d9a7-262">Quando você usa o atributo **ValidateScript** , o valor que está sendo validado é mapeado para a `$_` variável.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-262">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="5d9a7-263">Você pode usar a `$_` variável para fazer referência ao valor no script.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-263">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="5d9a7-264">No exemplo a seguir, o valor do parâmetro **EventDate** deve ser maior ou igual à data atual.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-264">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="5d9a7-265">No exemplo a seguir, o valor da variável `$date` deve ser maior ou igual à data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-265">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="5d9a7-266">Se você usar **ValidateScript** , não será possível passar um `$null` valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-266">If you use **ValidateScript** , you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="5d9a7-267">Quando você passa um valor nulo, **ValidateScript** não pode validar o argumento.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-267">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="5d9a7-268">Atributo ValidateSet</span><span class="sxs-lookup"><span data-stu-id="5d9a7-268">ValidateSet attribute</span></span>

<span data-ttu-id="5d9a7-269">O atributo **ValidateSet** especifica um conjunto de valores válidos para um parâmetro ou variável e habilita o preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-269">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="5d9a7-270">O PowerShell gerará um erro se um parâmetro ou valor de variável não corresponder a um valor no conjunto.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-270">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="5d9a7-271">No exemplo a seguir, o valor do parâmetro **Detail** só pode ser baixo, Average ou High.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-271">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="5d9a7-272">No exemplo a seguir, o valor da variável `$flavor` deve ser chocolate, morango ou baunilha.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-272">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="5d9a7-273">A validação ocorre sempre que essa variável é atribuída mesmo dentro do script.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-273">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="5d9a7-274">Por exemplo, os resultados a seguir resultam em um erro em tempo de execução:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-274">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="5d9a7-275">Atributo de validação ValidateNotNull</span><span class="sxs-lookup"><span data-stu-id="5d9a7-275">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="5d9a7-276">O atributo **ValidateNotNull** especifica que o valor do parâmetro não pode ser `$null` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-276">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="5d9a7-277">O PowerShell gerará um erro se o valor do parâmetro for `$null` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-277">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="5d9a7-278">O atributo **ValidateNotNull** é projetado para ser usado quando o parâmetro é opcional e o tipo é indefinido ou tem um conversor de tipo que não pode converter implicitamente um valor nulo como **objeto** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-278">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object** .</span></span> <span data-ttu-id="5d9a7-279">Se você especificar um tipo que irá converter implicitamente um valor nulo, como uma **cadeia de caracteres** , o valor nulo será convertido em uma cadeia de caracteres vazia mesmo ao usar o atributo **ValidateNotNull** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-279">If you specify a type that that will implicitly convert a null value such as a **string** , the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="5d9a7-280">Para este cenário, use o **ValidateNotNullOrEmpty**</span><span class="sxs-lookup"><span data-stu-id="5d9a7-280">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="5d9a7-281">No exemplo a seguir, o valor do parâmetro **ID** não pode ser `$null` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-281">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="5d9a7-282">Atributo de validação ValidateNotNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="5d9a7-282">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="5d9a7-283">O atributo **ValidateNotNullOrEmpty** especifica que o valor do parâmetro não pode ser `$null` e não pode ser uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-283">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="5d9a7-284">O PowerShell gerará um erro se o parâmetro for usado em uma chamada de função, mas seu valor for `$null` , uma cadeia de caracteres vazia ( `""` ) ou uma matriz vazia `@()` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-284">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="5d9a7-285">Atributo de validação ValidateDrive</span><span class="sxs-lookup"><span data-stu-id="5d9a7-285">ValidateDrive validation attribute</span></span>

<span data-ttu-id="5d9a7-286">O atributo **ValidateDrive** especifica que o valor do parâmetro deve representar o caminho, que está se referindo apenas a unidades permitidas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-286">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="5d9a7-287">O PowerShell gerará um erro se o valor do parâmetro se referir a unidades diferentes das permitidas.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-287">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="5d9a7-288">A existência do caminho, exceto para a própria unidade, não é verificada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-288">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="5d9a7-289">Se você usar o caminho relativo, a unidade atual deverá estar na lista unidade permitida.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-289">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="5d9a7-290">Atributo de validação ValidateUserDrive</span><span class="sxs-lookup"><span data-stu-id="5d9a7-290">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="5d9a7-291">O atributo **ValidateUserDrive** especifica que o valor do parâmetro deve representar o caminho, que está se referindo à `User` unidade.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-291">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="5d9a7-292">O PowerShell gerará um erro se o caminho se referir a uma unidade diferente.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-292">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="5d9a7-293">O atributo de validação só testa a existência da parte da unidade do caminho.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-293">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="5d9a7-294">Se você usar o caminho relativo, a unidade atual deverá ser `User` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-294">If you use relative path, the current drive must be `User`.</span></span>

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

<span data-ttu-id="5d9a7-295">Você pode definir a `User` unidade em configurações de sessão Jea (administração suficiente).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-295">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="5d9a7-296">Para este exemplo, criamos a unidade User:.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-296">For this example, we create the User: drive.</span></span>

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="5d9a7-297">Atributo de validação ValidateTrustedData</span><span class="sxs-lookup"><span data-stu-id="5d9a7-297">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="5d9a7-298">Esse atributo foi adicionado no PowerShell 6.1.1.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-298">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="5d9a7-299">Neste momento, o atributo é usado internamente pelo próprio PowerShell e não se destina ao uso externo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-299">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="5d9a7-300">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="5d9a7-300">Dynamic parameters</span></span>

<span data-ttu-id="5d9a7-301">Parâmetros dinâmicos são parâmetros de um cmdlet, uma função ou um script que estão disponíveis somente sob determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-301">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="5d9a7-302">Por exemplo, vários cmdlets de provedor têm parâmetros que estão disponíveis somente quando o cmdlet é usado na unidade do provedor ou em um caminho específico da unidade do provedor.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-302">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="5d9a7-303">Por exemplo, o parâmetro de **codificação** está disponível nos `Add-Content` `Get-Content` `Set-Content` cmdlets, e somente quando ele é usado em uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-303">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="5d9a7-304">Você também pode criar um parâmetro que aparece somente quando outro parâmetro é usado no comando Function ou quando outro parâmetro tem um determinado valor.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-304">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="5d9a7-305">Os parâmetros dinâmicos podem ser úteis, mas são usados somente quando necessário, pois podem ser difíceis para os usuários descobrirem.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-305">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="5d9a7-306">Para localizar um parâmetro dinâmico, o usuário deve estar no caminho do provedor, usar o parâmetro **ArgumentList** do `Get-Command` cmdlet ou usar o parâmetro **Path** de `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-306">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="5d9a7-307">Para criar um parâmetro dinâmico para uma função ou script, use a `DynamicParam` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-307">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="5d9a7-308">A sintaxe dela é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-308">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="5d9a7-309">Na lista de instruções, use uma `If` instrução para especificar as condições sob as quais o parâmetro está disponível na função.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-309">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="5d9a7-310">Use o `New-Object` cmdlet para criar um objeto **System. Management. Automation. RuntimeDefinedParameter** para representar o parâmetro e especificar seu nome.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-310">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="5d9a7-311">Você pode usar um `New-Object` comando para criar um objeto **System. Management. Automation. ParameterAttribute** para representar atributos do parâmetro, como **obrigatório** , **posição** ou **ValueFromPipeline** ou seu conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-311">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory** , **Position** , or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="5d9a7-312">O exemplo a seguir mostra uma função de exemplo com parâmetros padrão nomeados **Name** e **Path** , e um parâmetro dinâmico opcional chamado **DP1** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-312">The following example shows a sample function with standard parameters named **Name** and **Path** , and an optional dynamic parameter named **DP1** .</span></span> <span data-ttu-id="5d9a7-313">O parâmetro **DP1** está no `PSet1` conjunto de parâmetros e tem um tipo de `Int32` .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-313">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="5d9a7-314">O parâmetro **DP1** está disponível na `Get-Sample` função somente quando o valor do parâmetro **Path** começa com `HKLM:` , indicando que ele está sendo usado na `HKEY_LOCAL_MACHINE` unidade do registro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-314">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

<span data-ttu-id="5d9a7-315">Para obter mais informações, consulte [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-315">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="5d9a7-316">Parâmetros de opção</span><span class="sxs-lookup"><span data-stu-id="5d9a7-316">Switch parameters</span></span>

<span data-ttu-id="5d9a7-317">Parâmetros de switch são parâmetros sem valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-317">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="5d9a7-318">Eles são eficazes somente quando são usados e têm apenas um efeito.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-318">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="5d9a7-319">Por exemplo, o parâmetro **NoProfile** de **powershell.exe** é um parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-319">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="5d9a7-320">Para criar um parâmetro de opção em uma função, especifique o `Switch` tipo na definição de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-320">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="5d9a7-321">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-321">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="5d9a7-322">Ou você pode usar um outro método:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-322">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="5d9a7-323">Parâmetros de comutação são fáceis de usar e são preferenciais sobre parâmetros boolianos, que têm uma sintaxe mais difícil.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-323">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="5d9a7-324">Por exemplo, para usar um parâmetro de opção, o usuário digita o parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-324">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="5d9a7-325">Para usar um parâmetro booliano, o usuário digita o parâmetro e um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-325">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="5d9a7-326">Ao criar parâmetros de opção, escolha o nome do parâmetro com cuidado.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-326">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="5d9a7-327">Certifique-se de que o nome do parâmetro comunique o efeito do parâmetro para o usuário.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-327">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="5d9a7-328">Evite termos ambíguos, como **filtro** ou **máximo** , que podem implicar que um valor é necessário.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-328">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="5d9a7-329">Atributo ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="5d9a7-329">ArgumentCompleter attribute</span></span>

<span data-ttu-id="5d9a7-330">O atributo **ArgumentCompleter** permite adicionar valores de preenchimento de guia a um parâmetro específico.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-330">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="5d9a7-331">Um atributo **ArgumentCompleter** deve ser definido para cada parâmetro que precisa de preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-331">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="5d9a7-332">Semelhante a **DynamicParameters** , os valores disponíveis são calculados em tempo de execução quando o usuário pressiona <kbd>Tab</kbd> após o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-332">Similar to **DynamicParameters** , the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="5d9a7-333">Para adicionar um atributo **ArgumentCompleter** , você precisa definir um bloco de script que determina os valores.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-333">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="5d9a7-334">O bloco de script deve usar os seguintes parâmetros na ordem especificada abaixo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-334">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="5d9a7-335">Os nomes dos parâmetros não são importantes, pois os valores são fornecidos de forma posicionada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-335">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="5d9a7-336">A sintaxe dela é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-336">The syntax is as follows:</span></span>

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="5d9a7-337">Bloco de script ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="5d9a7-337">ArgumentCompleter script block</span></span>

<span data-ttu-id="5d9a7-338">Os parâmetros de bloco de script são definidos com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5d9a7-338">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="5d9a7-339">`$commandName` (Posição 0)-esse parâmetro é definido como o nome do comando para o qual o bloco de script está fornecendo preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-339">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="5d9a7-340">`$parameterName` (Posição 1)-esse parâmetro é definido como o parâmetro cujo valor requer preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-340">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="5d9a7-341">`$wordToComplete` (Posição 2)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-341">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="5d9a7-342">`$commandAst` (Posição 3)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-342">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="5d9a7-343">Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-343">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="5d9a7-344">`$fakeBoundParameters` (Posição 4)-esse parâmetro é definido como uma tabela de hash que contém o `$PSBoundParameters` para o cmdlet, antes da <kbd>guia</kbd>ser pressionada pelo usuário. Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5d9a7-344">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="5d9a7-345">O bloco de script **ArgumentCompleter** deve desdistribuir os valores usando o pipeline, como `ForEach-Object` , `Where-Object` ou outro método adequado.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-345">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="5d9a7-346">Retornar uma matriz de valores faz com que o PowerShell trate toda a matriz como **um** valor de conclusão de tabulação.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-346">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="5d9a7-347">O exemplo a seguir adiciona a conclusão de Tab ao parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="5d9a7-347">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="5d9a7-348">Se apenas o parâmetro **Value** for especificado, todos os valores possíveis, ou argumentos, para **Value** serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-348">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="5d9a7-349">Quando o parâmetro de **tipo** é especificado, o parâmetro **Value** exibe apenas os valores possíveis para esse tipo.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-349">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="5d9a7-350">Além disso, o `-like` operador garante que, se o usuário digitar o comando a seguir e usar a conclusão de <kbd>Tabulação</kbd> , somente a **Apple** será retornada.</span><span class="sxs-lookup"><span data-stu-id="5d9a7-350">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a><span data-ttu-id="5d9a7-351">Confira também</span><span class="sxs-lookup"><span data-stu-id="5d9a7-351">See also</span></span>

[<span data-ttu-id="5d9a7-352">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="5d9a7-352">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="5d9a7-353">about_Functions</span><span class="sxs-lookup"><span data-stu-id="5d9a7-353">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="5d9a7-354">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="5d9a7-354">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="5d9a7-355">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="5d9a7-355">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="5d9a7-356">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="5d9a7-356">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="5d9a7-357">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="5d9a7-357">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
