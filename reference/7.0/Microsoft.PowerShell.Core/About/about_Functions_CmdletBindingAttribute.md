---
description: Descreve o atributo que faz uma função funcionar como um cmdlet compilado.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: 816bee647702fca4a2b9196491b2525f0338ab31
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195906"
---
# <a name="about-functions-cmdletbindingattribute"></a><span data-ttu-id="10983-104">Sobre o Functions CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="10983-104">About Functions CmdletBindingAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="10983-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="10983-105">Short description</span></span>
<span data-ttu-id="10983-106">Descreve o atributo que faz uma função funcionar como um cmdlet compilado.</span><span class="sxs-lookup"><span data-stu-id="10983-106">Describes the attribute that makes a function work like a compiled cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="10983-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="10983-107">Long description</span></span>

<span data-ttu-id="10983-108">O `CmdletBinding` atributo é um atributo de funções que os torna operar como cmdlets compilados escritos em C#.</span><span class="sxs-lookup"><span data-stu-id="10983-108">The `CmdletBinding` attribute is an attribute of functions that makes them operate like compiled cmdlets written in C#.</span></span> <span data-ttu-id="10983-109">Ele fornece acesso aos recursos de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="10983-109">It provides access to the features of cmdlets.</span></span>

<span data-ttu-id="10983-110">O PowerShell associa os parâmetros das funções que têm o `CmdletBinding` atributo da mesma forma que vincula os parâmetros dos cmdlets compilados.</span><span class="sxs-lookup"><span data-stu-id="10983-110">PowerShell binds the parameters of functions that have the `CmdletBinding` attribute in the same way that it binds the parameters of compiled cmdlets.</span></span> <span data-ttu-id="10983-111">A `$PSCmdlet` variável automática está disponível para funções com o `CmdletBinding` atributo, mas a `$Args` variável não está disponível.</span><span class="sxs-lookup"><span data-stu-id="10983-111">The `$PSCmdlet` automatic variable is available to functions with the `CmdletBinding` attribute, but the `$Args` variable is not available.</span></span>

<span data-ttu-id="10983-112">Em funções que têm o `CmdletBinding` atributo, parâmetros desconhecidos e argumentos posicionais que não têm parâmetros posicionais correspondentes causam a falha da Associação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="10983-112">In functions that have the `CmdletBinding` attribute, unknown parameters and positional arguments that have no matching positional parameters cause parameter binding to fail.</span></span>

> [!NOTE]
> <span data-ttu-id="10983-113">Os cmdlets compilados usam o `Cmdlet` Atributo Required, que é semelhante ao `CmdletBinding` atributo descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="10983-113">Compiled cmdlets use the required `Cmdlet` attribute, which is similar to the `CmdletBinding` attribute that is described in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="10983-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="10983-114">Syntax</span></span>

<span data-ttu-id="10983-115">O exemplo a seguir mostra o formato de uma função que especifica todos os argumentos opcionais do `CmdletBinding` atributo.</span><span class="sxs-lookup"><span data-stu-id="10983-115">The following example shows the format of a function that specifies all the optional arguments of the `CmdletBinding` attribute.</span></span> <span data-ttu-id="10983-116">Uma breve descrição de cada argumento segue este exemplo.</span><span class="sxs-lookup"><span data-stu-id="10983-116">A brief description of each argument follows this example.</span></span>

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a><span data-ttu-id="10983-117">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="10983-117">ConfirmImpact</span></span>

<span data-ttu-id="10983-118">O argumento **ConfirmImpact** especifica quando a ação da função deve ser confirmada por uma chamada para o método **ShouldProcess** .</span><span class="sxs-lookup"><span data-stu-id="10983-118">The **ConfirmImpact** argument specifies when the action of the function should be confirmed by a call to the **ShouldProcess** method.</span></span> <span data-ttu-id="10983-119">A chamada para o método **ShouldProcess** exibe um prompt de confirmação somente quando o argumento **ConfirmImpact** é igual ou maior que o valor da `$ConfirmPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="10983-119">The call to the **ShouldProcess** method displays a confirmation prompt only when the **ConfirmImpact** argument is equal to or greater than the value of the `$ConfirmPreference` preference variable.</span></span> <span data-ttu-id="10983-120">(O valor padrão do argumento é **médio** .) Especifique esse argumento somente quando o argumento **SupportsShouldProcess** também for especificado.</span><span class="sxs-lookup"><span data-stu-id="10983-120">(The default value of the argument is **Medium** .) Specify this argument only when the **SupportsShouldProcess** argument is also specified.</span></span>

<span data-ttu-id="10983-121">Para obter mais informações sobre solicitações de confirmação, consulte [solicitando confirmação](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="10983-121">For more information about confirmation requests, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

## <a name="defaultparametersetname"></a><span data-ttu-id="10983-122">DefaultParameterSetName</span><span class="sxs-lookup"><span data-stu-id="10983-122">DefaultParameterSetName</span></span>

<span data-ttu-id="10983-123">O argumento **DefaultParameterSetName** especifica o nome do conjunto de parâmetros que o PowerShell tentará usar quando não puder determinar qual conjunto de parâmetros usar.</span><span class="sxs-lookup"><span data-stu-id="10983-123">The **DefaultParameterSetName** argument specifies the name of the parameter set that PowerShell will attempt to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="10983-124">Você pode evitar esse problema fazendo com que o parâmetro exclusivo de cada parâmetro defina um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="10983-124">You can avoid this issue by making the unique parameter of each parameter set a mandatory parameter.</span></span>

## <a name="helpuri"></a><span data-ttu-id="10983-125">HelpURI</span><span class="sxs-lookup"><span data-stu-id="10983-125">HelpURI</span></span>

<span data-ttu-id="10983-126">O argumento **HelpURI** especifica o endereço de Internet da versão online do tópico da ajuda que descreve a função.</span><span class="sxs-lookup"><span data-stu-id="10983-126">The **HelpURI** argument specifies the internet address of the online version of the help topic that describes the function.</span></span> <span data-ttu-id="10983-127">O valor do argumento **HelpURI** deve começar com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="10983-127">The value of the **HelpURI** argument must begin with "http" or "https".</span></span>

<span data-ttu-id="10983-128">O valor do argumento **HelpURI** é usado para o valor da propriedade **HelpURI** do objeto **CommandInfo** que `Get-Command` retorna para a função.</span><span class="sxs-lookup"><span data-stu-id="10983-128">The **HelpURI** argument value is used for the value of the **HelpURI** property of the **CommandInfo** object that `Get-Command` returns for the function.</span></span>

<span data-ttu-id="10983-129">No entanto, quando os arquivos de ajuda são instalados no computador e o valor do primeiro link na seção **RelatedLinks** do arquivo de ajuda é um URI ou o valor da primeira `.Link` diretiva na Ajuda baseada em comentários é um URI, o URI no arquivo de ajuda é usado como o valor da propriedade **HelpUri** da função.</span><span class="sxs-lookup"><span data-stu-id="10983-129">However, when help files are installed on the computer and the value of the first link in the **RelatedLinks** section of the help file is a URI, or the value of the first `.Link` directive in comment-based help is a URI, the URI in the help file is used as the value of the **HelpUri** property of the function.</span></span>

<span data-ttu-id="10983-130">O `Get-Help` cmdlet usa o valor da propriedade **HelpURI** para localizar a versão online do tópico da ajuda da função quando o parâmetro **online** do `Get-Help` é especificado em um comando.</span><span class="sxs-lookup"><span data-stu-id="10983-130">The `Get-Help` cmdlet uses the value of the **HelpURI** property to locate the online version of the function help topic when the **Online** parameter of `Get-Help` is specified in a command.</span></span>

## <a name="supportspaging"></a><span data-ttu-id="10983-131">Suporteparapaginação</span><span class="sxs-lookup"><span data-stu-id="10983-131">SupportsPaging</span></span>

<span data-ttu-id="10983-132">O argumento **suporteparapaginação** adiciona os parâmetros **First** , **Skip** e **IncludeTotalCount** à função.</span><span class="sxs-lookup"><span data-stu-id="10983-132">The **SupportsPaging** argument adds the **First** , **Skip** , and **IncludeTotalCount** parameters to the function.</span></span> <span data-ttu-id="10983-133">Esses parâmetros permitem que os usuários selecionem a saída de um conjunto de resultados muito grande.</span><span class="sxs-lookup"><span data-stu-id="10983-133">These parameters allow users to select output from a very large result set.</span></span> <span data-ttu-id="10983-134">Esse argumento é projetado para cmdlets e funções que retornam dados de repositórios de dados grandes que dão suporte à seleção de dados, como um banco de dado SQL.</span><span class="sxs-lookup"><span data-stu-id="10983-134">This argument is designed for cmdlets and functions that return data from large data stores that support data selection, such as an SQL database.</span></span>

<span data-ttu-id="10983-135">Esse argumento foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="10983-135">This argument was introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="10983-136">**Primeiro** : obtém somente os primeiros ' n' objetos.</span><span class="sxs-lookup"><span data-stu-id="10983-136">**First** : Gets only the first 'n' objects.</span></span>
- <span data-ttu-id="10983-137">**Ignorar** : ignora os primeiros ' n' objetos e, em seguida, obtém os objetos restantes.</span><span class="sxs-lookup"><span data-stu-id="10983-137">**Skip** :  Ignores the first 'n' objects and then gets the remaining objects.</span></span>
- <span data-ttu-id="10983-138">**IncludeTotalCount** : relata o número de objetos no conjunto de dados (um inteiro) seguido pelos objetos.</span><span class="sxs-lookup"><span data-stu-id="10983-138">**IncludeTotalCount** : Reports the number of objects in the data set (an integer) followed by the objects.</span></span> <span data-ttu-id="10983-139">Se o cmdlet não puder determinar a contagem total, ele retornará "contagem total desconhecida".</span><span class="sxs-lookup"><span data-stu-id="10983-139">If the cmdlet cannot determine the total count, it returns "Unknown total count".</span></span>

<span data-ttu-id="10983-140">O PowerShell inclui **NewTotalCount** , um método auxiliar que obtém o valor total da contagem para retornar e inclui uma estimativa da precisão do valor total da contagem.</span><span class="sxs-lookup"><span data-stu-id="10983-140">PowerShell includes **NewTotalCount** , a helper method that gets the total count value to return and includes an estimate of the accuracy of the total count value.</span></span>

<span data-ttu-id="10983-141">A função de exemplo a seguir mostra como adicionar suporte para os parâmetros de paginação a uma função avançada.</span><span class="sxs-lookup"><span data-stu-id="10983-141">The following sample function shows how to add support for the paging parameters to an advanced function.</span></span>

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="10983-142">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="10983-142">SupportsShouldProcess</span></span>

<span data-ttu-id="10983-143">O argumento **SupportsShouldProcess** adiciona os parâmetros **Confirm** e **WhatIf** à função.</span><span class="sxs-lookup"><span data-stu-id="10983-143">The **SupportsShouldProcess** argument adds **Confirm** and **WhatIf** parameters to the function.</span></span> <span data-ttu-id="10983-144">O parâmetro **Confirm** solicita o usuário antes de executar o comando em cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="10983-144">The **Confirm** parameter prompts the user before it runs the command on each object in the pipeline.</span></span> <span data-ttu-id="10983-145">O parâmetro **WhatIf** lista as alterações que o comando faria, em vez de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="10983-145">The **WhatIf** parameter lists the changes that the command would make, instead of running the command.</span></span>

## <a name="positionalbinding"></a><span data-ttu-id="10983-146">PositionalBinding</span><span class="sxs-lookup"><span data-stu-id="10983-146">PositionalBinding</span></span>

<span data-ttu-id="10983-147">O argumento **PositionalBinding** determina se os parâmetros na função são posicionais por padrão.</span><span class="sxs-lookup"><span data-stu-id="10983-147">The **PositionalBinding** argument determines whether parameters in the function are positional by default.</span></span> <span data-ttu-id="10983-148">O valor padrão é `$True`.</span><span class="sxs-lookup"><span data-stu-id="10983-148">The default value is `$True`.</span></span> <span data-ttu-id="10983-149">Você pode usar o argumento **PositionalBinding** com um valor de `$False` para desabilitar a associação posicional.</span><span class="sxs-lookup"><span data-stu-id="10983-149">You can use the **PositionalBinding** argument with a value of `$False` to disable positional binding.</span></span>

<span data-ttu-id="10983-150">O argumento **PositionalBinding** é introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="10983-150">The **PositionalBinding** argument is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="10983-151">Quando os parâmetros são posicionais, o nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="10983-151">When parameters are positional, the parameter name is optional.</span></span>
<span data-ttu-id="10983-152">O PowerShell associa valores de parâmetro não nomeados aos parâmetros de função de acordo com a ordem ou a posição dos valores de parâmetro não nomeados no comando Function.</span><span class="sxs-lookup"><span data-stu-id="10983-152">PowerShell associates unnamed parameter values with the function parameters according to the order or position of the unnamed parameter values in the function command.</span></span>

<span data-ttu-id="10983-153">Quando os parâmetros não são posicionais (eles são "nomeados"), o nome do parâmetro (ou uma abreviação ou alias do nome) é necessário no comando.</span><span class="sxs-lookup"><span data-stu-id="10983-153">When parameters are not positional (they are "named"), the parameter name (or an abbreviation or alias of the name) is required in the command.</span></span>

<span data-ttu-id="10983-154">Quando **PositionalBinding** é `$True` , os parâmetros de função são posicionais por padrão.</span><span class="sxs-lookup"><span data-stu-id="10983-154">When **PositionalBinding** is `$True`, function parameters are positional by default.</span></span> <span data-ttu-id="10983-155">O PowerShell atribui o número da posição aos parâmetros na ordem em que eles são declarados na função.</span><span class="sxs-lookup"><span data-stu-id="10983-155">PowerShell assigns position number to the parameters in the order in which they are declared in the function.</span></span>

<span data-ttu-id="10983-156">Quando **PositionalBinding** é `$False` , os parâmetros de função não são posicionais por padrão.</span><span class="sxs-lookup"><span data-stu-id="10983-156">When **PositionalBinding** is `$False`, function parameters are not positional by default.</span></span> <span data-ttu-id="10983-157">A menos que o argumento de **posição** do atributo de **parâmetro** seja declarado no parâmetro, o nome do parâmetro (ou um alias ou uma abreviação) deve ser incluído quando o parâmetro é usado em uma função.</span><span class="sxs-lookup"><span data-stu-id="10983-157">Unless the **Position** argument of the **Parameter** attribute is declared on the parameter, the parameter name (or an alias or abbreviation) must be included when the parameter is used in a function.</span></span>

<span data-ttu-id="10983-158">O argumento **Position** do atributo de **parâmetro** tem precedência sobre o valor padrão **PositionalBinding** .</span><span class="sxs-lookup"><span data-stu-id="10983-158">The **Position** argument of the **Parameter** attribute takes precedence over the **PositionalBinding** default value.</span></span> <span data-ttu-id="10983-159">Você pode usar o argumento **Position** para especificar um valor de posição para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="10983-159">You can use the **Position** argument to specify a position value for a parameter.</span></span> <span data-ttu-id="10983-160">Para obter mais informações sobre o argumento **Position** , consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="10983-160">For more information about the **Position** argument, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="notes"></a><span data-ttu-id="10983-161">Observações</span><span class="sxs-lookup"><span data-stu-id="10983-161">Notes</span></span>

<span data-ttu-id="10983-162">Não há suporte para o argumento **SupportsTransactions** em funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="10983-162">The **SupportsTransactions** argument is not supported in advanced functions.</span></span>

## <a name="keywords"></a><span data-ttu-id="10983-163">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="10983-163">Keywords</span></span>

<span data-ttu-id="10983-164">about_Functions_CmdletBinding_Attribute</span><span class="sxs-lookup"><span data-stu-id="10983-164">about_Functions_CmdletBinding_Attribute</span></span>

## <a name="see-also"></a><span data-ttu-id="10983-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="10983-165">See also</span></span>

[<span data-ttu-id="10983-166">about_Functions</span><span class="sxs-lookup"><span data-stu-id="10983-166">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="10983-167">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="10983-167">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="10983-168">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="10983-168">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="10983-169">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="10983-169">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="10983-170">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="10983-170">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
