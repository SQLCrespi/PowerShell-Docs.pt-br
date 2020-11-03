---
description: Descreve como trabalhar com parâmetros de comando no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: 7cc5c071116df8d3326a4ea13802227d350bfac3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196179"
---
# <a name="about-parameters"></a><span data-ttu-id="8e471-104">Sobre parâmetros</span><span class="sxs-lookup"><span data-stu-id="8e471-104">About Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="8e471-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="8e471-105">Short description</span></span>
<span data-ttu-id="8e471-106">Descreve como trabalhar com parâmetros de comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e471-106">Describes how to work with command parameters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="8e471-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="8e471-107">Long description</span></span>

<span data-ttu-id="8e471-108">A maioria dos comandos do PowerShell, como cmdlets, funções e scripts, depende de parâmetros para permitir que os usuários selecionem opções ou forneçam entradas.</span><span class="sxs-lookup"><span data-stu-id="8e471-108">Most PowerShell commands, such as cmdlets, functions, and scripts, rely on parameters to allow users to select options or provide input.</span></span> <span data-ttu-id="8e471-109">Os parâmetros seguem o nome do comando e têm o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="8e471-109">The parameters follow the command name and have the following form:</span></span>

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

<span data-ttu-id="8e471-110">O nome do parâmetro é precedido por um hífen (-), que sinaliza ao PowerShell que a palavra que segue o hífen é um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-110">The name of the parameter is preceded by a hyphen (-), which signals to PowerShell that the word following the hyphen is a parameter name.</span></span> <span data-ttu-id="8e471-111">O nome e o valor do parâmetro podem ser separados por um espaço ou um caractere de dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="8e471-111">The parameter name and value can be separated by a space or a colon character.</span></span> <span data-ttu-id="8e471-112">Alguns parâmetros não exigem ou aceitam um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-112">Some parameters do not require or accept a parameter value.</span></span> <span data-ttu-id="8e471-113">Outros parâmetros exigem um valor, mas não exigem o nome do parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-113">Other parameters require a value, but do not require the parameter name in the command.</span></span>

<span data-ttu-id="8e471-114">O tipo de parâmetros e os requisitos para esses parâmetros variam.</span><span class="sxs-lookup"><span data-stu-id="8e471-114">The type of parameters and the requirements for those parameters vary.</span></span> <span data-ttu-id="8e471-115">Para localizar informações sobre os parâmetros de um comando, use o `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e471-115">To find information about the parameters of a command, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="8e471-116">Por exemplo, para encontrar informações sobre os parâmetros do `Get-ChildItem` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="8e471-116">For example, to find information about the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="8e471-117">Para encontrar informações sobre os parâmetros de um script, use o caminho completo para o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8e471-117">To find information about the parameters of a script, use the full path to the script file.</span></span> <span data-ttu-id="8e471-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8e471-118">For example:</span></span>

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

<span data-ttu-id="8e471-119">O `Get-Help` cmdlet retorna vários detalhes sobre o comando, incluindo uma descrição, a sintaxe do comando, informações sobre os parâmetros e exemplos que mostram como usar os parâmetros em um comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-119">The `Get-Help` cmdlet returns various details about the command, including a description, the command syntax, information about the parameters, and examples showing how to use the parameters in a command.</span></span>

<span data-ttu-id="8e471-120">Você também pode usar o parâmetro Parameter do `Get-Help` cmdlet para encontrar informações sobre um determinado parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-120">You can also use the Parameter parameter of the `Get-Help` cmdlet to find information about a particular parameter.</span></span> <span data-ttu-id="8e471-121">Ou, você pode usar o parâmetro **Parameter** com o valor Character curinga ( `*` ) para encontrar informações sobre todos os parâmetros do comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-121">Or, you can use the **Parameter** parameter with the wildcard character ( `*` ) value to find information about all parameters of the command.</span></span> <span data-ttu-id="8e471-122">Por exemplo, o comando a seguir obtém informações sobre todos os parâmetros do `Get-Member` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8e471-122">For example, the following command gets information about all parameters of the `Get-Member` cmdlet:</span></span>

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a><span data-ttu-id="8e471-123">Valores do parâmetro padrão</span><span class="sxs-lookup"><span data-stu-id="8e471-123">Default parameter values</span></span>

<span data-ttu-id="8e471-124">Os parâmetros opcionais têm um valor padrão, que é o valor que é usado ou assumido quando o parâmetro não é especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-124">Optional parameters have a default value, which is the value that is used or assumed when the parameter is not specified in the command.</span></span>

<span data-ttu-id="8e471-125">Por exemplo, o valor padrão do parâmetro **ComputerName** de muitos cmdlets é o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="8e471-125">For example, the default value of the **ComputerName** parameter of many cmdlets is the name of the local computer.</span></span> <span data-ttu-id="8e471-126">Como resultado, o nome do computador local é usado no comando, a menos que o parâmetro **ComputerName** seja especificado.</span><span class="sxs-lookup"><span data-stu-id="8e471-126">As a result, the local computer name is used in the command unless the **ComputerName** parameter is specified.</span></span>

<span data-ttu-id="8e471-127">Para localizar o valor do parâmetro padrão, consulte o tópico da ajuda para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e471-127">To find the default parameter value, see help topic for the cmdlet.</span></span> <span data-ttu-id="8e471-128">A descrição do parâmetro deve incluir o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="8e471-128">The parameter description should include the default value.</span></span>

<span data-ttu-id="8e471-129">Você também pode definir um valor padrão personalizado para qualquer parâmetro de um cmdlet ou função avançada.</span><span class="sxs-lookup"><span data-stu-id="8e471-129">You can also set a custom default value for any parameter of a cmdlet or advanced function.</span></span> <span data-ttu-id="8e471-130">Para obter informações sobre como definir valores padrão personalizados, consulte [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="8e471-130">For information about setting custom default values, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="8e471-131">Tabela de atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="8e471-131">Parameter attribute table</span></span>

<span data-ttu-id="8e471-132">Quando você usa os parâmetros **completo** , **parâmetro** ou **online** do `Get-Help` cmdlet, `Get-Help` o exibe uma tabela de atributos de parâmetro com informações detalhadas sobre o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-132">When you use the **Full** , **Parameter** , or **Online** parameters of the `Get-Help` cmdlet, `Get-Help` displays a parameter attribute table with detailed information about the parameter.</span></span>

<span data-ttu-id="8e471-133">Essas informações incluem os detalhes que você precisa saber para usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-133">This information includes the details you need to know to use the parameter.</span></span>
<span data-ttu-id="8e471-134">Por exemplo, o tópico da ajuda para o `Get-ChildItem` cmdlet inclui os seguintes detalhes sobre seu parâmetro de caminho:</span><span class="sxs-lookup"><span data-stu-id="8e471-134">For example, the help topic for the `Get-ChildItem` cmdlet includes the following details about its Path parameter:</span></span>

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

<span data-ttu-id="8e471-135">As informações de parâmetro incluem a sintaxe do parâmetro, uma descrição do parâmetro e os atributos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-135">The parameter information includes the parameter syntax, a description of the parameter, and the parameter attributes.</span></span> <span data-ttu-id="8e471-136">As seções a seguir descrevem os atributos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-136">The following sections describe the parameter attributes.</span></span>

#### <a name="parameter-required"></a><span data-ttu-id="8e471-137">Parâmetro necessário</span><span class="sxs-lookup"><span data-stu-id="8e471-137">Parameter Required</span></span>

<span data-ttu-id="8e471-138">Essa configuração indica se o parâmetro é obrigatório, ou seja, se todos os comandos que usam esse cmdlet devem incluir esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-138">This setting indicates whether the parameter is mandatory, that is, whether all commands that use this cmdlet must include this parameter.</span></span> <span data-ttu-id="8e471-139">Quando o valor for **true** e o parâmetro estiver ausente no comando, o PowerShell solicitará um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-139">When the value is **True** and the parameter is missing from the command, PowerShell prompts you for a value for the parameter.</span></span>

#### <a name="parameter-position"></a><span data-ttu-id="8e471-140">Posição do parâmetro</span><span class="sxs-lookup"><span data-stu-id="8e471-140">Parameter Position</span></span>

<span data-ttu-id="8e471-141">Se a `Position` configuração for definida como um inteiro positivo, o nome do parâmetro não será necessário.</span><span class="sxs-lookup"><span data-stu-id="8e471-141">If the `Position` setting is set to a positive integer, the parameter name is not required.</span></span> <span data-ttu-id="8e471-142">Esse tipo de parâmetro é conhecido como um parâmetro posicional e o número indica a posição em que o parâmetro deve aparecer em relação a outros parâmetros de posição.</span><span class="sxs-lookup"><span data-stu-id="8e471-142">This type of parameter is referred to as a positional parameter, and the number indicates the position in which the parameter must appear in relation to other positional parameters.</span></span> <span data-ttu-id="8e471-143">Um parâmetro nomeado pode ser listado em qualquer posição após o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e471-143">A named parameter can be listed in any position after the cmdlet name.</span></span> <span data-ttu-id="8e471-144">Se você incluir o nome do parâmetro para um parâmetro posicional, o parâmetro poderá ser listado em qualquer posição após o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e471-144">If you include the parameter name for a positional parameter, the parameter can be listed in any position after the cmdlet name.</span></span>

<span data-ttu-id="8e471-145">Por exemplo, o `Get-ChildItem` cmdlet tem parâmetros Path e exclude.</span><span class="sxs-lookup"><span data-stu-id="8e471-145">For example, the `Get-ChildItem` cmdlet has Path and Exclude parameters.</span></span> <span data-ttu-id="8e471-146">A `Position` configuração para **Path** é **0** , o que significa que ele é um parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="8e471-146">The `Position` setting for **Path** is **0** , which means that it is a positional parameter.</span></span> <span data-ttu-id="8e471-147">A `Position` configuração para **excluir** é **denominada** .</span><span class="sxs-lookup"><span data-stu-id="8e471-147">The `Position` setting for **Exclude** is **named** .</span></span>

<span data-ttu-id="8e471-148">Isso significa que o **caminho** não requer o nome do parâmetro, mas seu valor de parâmetro deve ser o primeiro ou apenas o valor do parâmetro não nomeado no comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-148">This means that **Path** does not require the parameter name, but its parameter value must be the first or only unnamed parameter value in the command.</span></span>
<span data-ttu-id="8e471-149">No entanto, como o parâmetro Exclude é um parâmetro nomeado, você pode colocá-lo em qualquer posição no comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-149">However, because the Exclude parameter is a named parameter, you can place it in any position in the command.</span></span>

<span data-ttu-id="8e471-150">Como resultado das `Position` configurações para esses dois parâmetros, você pode usar qualquer um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="8e471-150">As a result of the `Position` settings for these two parameters, you can use any of the following commands:</span></span>

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

<span data-ttu-id="8e471-151">Se você tiver que incluir outro parâmetro posicional sem incluir o nome do parâmetro, esse parâmetro deverá ser colocado na ordem especificada pela `Position` configuração.</span><span class="sxs-lookup"><span data-stu-id="8e471-151">If you were to include another positional parameter without including the parameter name, that parameter must be placed in the order specified by the `Position` setting.</span></span>

#### <a name="parameter-type"></a><span data-ttu-id="8e471-152">Tipo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="8e471-152">Parameter Type</span></span>

<span data-ttu-id="8e471-153">Essa configuração especifica o tipo de Microsoft .NET Framework do valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-153">This setting specifies the Microsoft .NET Framework type of the parameter value.</span></span> <span data-ttu-id="8e471-154">Por exemplo, se o tipo for **Int32** , o valor do parâmetro deverá ser um inteiro.</span><span class="sxs-lookup"><span data-stu-id="8e471-154">For example, if the type is **Int32** , the parameter value must be an integer.</span></span> <span data-ttu-id="8e471-155">Se o tipo for String, o valor do parâmetro deverá ser uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8e471-155">If the type is string, the parameter value must be a character string.</span></span> <span data-ttu-id="8e471-156">Se a cadeia de caracteres contiver espaços, o valor deverá ser colocado entre aspas ou os espaços devem ser precedidos pelo caractere de escape (').</span><span class="sxs-lookup"><span data-stu-id="8e471-156">If the string contains spaces, the value must be enclosed in quotation marks, or the spaces must be preceded by the escape character ( \` ).</span></span>

#### <a name="default-value"></a><span data-ttu-id="8e471-157">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="8e471-157">Default Value</span></span>

<span data-ttu-id="8e471-158">Essa configuração especifica o valor que o parâmetro assumirá se nenhum outro valor for fornecido.</span><span class="sxs-lookup"><span data-stu-id="8e471-158">This setting specifies the value that the parameter will assume if no other value is provided.</span></span> <span data-ttu-id="8e471-159">Por exemplo, o valor padrão do parâmetro Path é geralmente o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8e471-159">For example, the default value of the Path parameter is often the current directory.</span></span> <span data-ttu-id="8e471-160">Os parâmetros necessários nunca têm um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="8e471-160">Required parameters never have a default value.</span></span>
<span data-ttu-id="8e471-161">Para muitos parâmetros opcionais, não há nenhum padrão porque o parâmetro não tem efeito se não for usado.</span><span class="sxs-lookup"><span data-stu-id="8e471-161">For many optional parameters, there is no default because the parameter has no effect if it is not used.</span></span>

#### <a name="accepts-multiple-values"></a><span data-ttu-id="8e471-162">Aceita vários valores</span><span class="sxs-lookup"><span data-stu-id="8e471-162">Accepts Multiple Values</span></span>

<span data-ttu-id="8e471-163">Essa configuração indica se um parâmetro aceita vários valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-163">This setting indicates whether a parameter accepts multiple parameter values.</span></span>
<span data-ttu-id="8e471-164">Quando um parâmetro aceita vários valores, você pode digitar uma lista separada por vírgulas como o valor do parâmetro no comando ou salvar uma lista separada por vírgulas (uma matriz) em uma variável e, em seguida, especificar a variável como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-164">When a parameter accepts multiple values, you can type a comma-separated list as the value of the parameter in the command, or save a comma-separated list (an array) in a variable, and then specify the variable as the parameter value.</span></span>

<span data-ttu-id="8e471-165">Por exemplo, o parâmetro ServiceName do `Get-Service` cmdlet aceita vários valores.</span><span class="sxs-lookup"><span data-stu-id="8e471-165">For example, the ServiceName parameter of the `Get-Service` cmdlet accepts multiple values.</span></span> <span data-ttu-id="8e471-166">Os seguintes comandos são válidos:</span><span class="sxs-lookup"><span data-stu-id="8e471-166">The following commands are both valid:</span></span>

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a><span data-ttu-id="8e471-167">Aceita entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="8e471-167">Accepts Pipeline Input</span></span>

<span data-ttu-id="8e471-168">Essa configuração indica se você pode usar o operador de pipeline ( `|` ) para enviar um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-168">This setting indicates whether you can use the pipeline operator ( `|` ) to send a value to the parameter.</span></span>

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

<span data-ttu-id="8e471-169">Quando um parâmetro é "true (por valor)", o PowerShell tenta associar quaisquer valores de pipe com esse parâmetro antes de tentar outros métodos para interpretar o comando.</span><span class="sxs-lookup"><span data-stu-id="8e471-169">When a parameter is "True (by Value)", PowerShell tries to associate any piped values with that parameter before it tries other methods to interpret the command.</span></span>

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

<span data-ttu-id="8e471-170">Por exemplo, você pode canalizar um valor para um parâmetro de **nome** somente quando o valor tiver uma propriedade chamada **Name** .</span><span class="sxs-lookup"><span data-stu-id="8e471-170">For example, you can pipe a value to a **Name** parameter only when the value has a property called **Name** .</span></span>

> [!NOTE]
> <span data-ttu-id="8e471-171">Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de **ligação de atraso** no parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-171">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
>
> <span data-ttu-id="8e471-172">O bloco de script de **ligação de atraso** é executado automaticamente durante o **parâmetrobinding** .</span><span class="sxs-lookup"><span data-stu-id="8e471-172">The **delay-bind** script block is run automatically during **ParameterBinding** .</span></span> <span data-ttu-id="8e471-173">O resultado é associado ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e471-173">The result is bound to the parameter.</span></span> <span data-ttu-id="8e471-174">A associação de atraso **não funciona para** parâmetros definidos como tipo `ScriptBlock` ou `System.Object` , o bloco de script é passado **sem** ser invocado.</span><span class="sxs-lookup"><span data-stu-id="8e471-174">Delay binding does **not** work for parameters defined as type `ScriptBlock` or `System.Object`, the script block is passed through **without** being invoked.</span></span>
>
> <span data-ttu-id="8e471-175">Você pode ler sobre blocos **de script de ligação de atraso** aqui [about_Script_Blocks. MD](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="8e471-175">You can read about **delay-bind** script blocks here [about_Script_Blocks.md](about_Script_Blocks.md)</span></span>

#### <a name="accepts-wildcard-characters"></a><span data-ttu-id="8e471-176">Aceita caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="8e471-176">Accepts Wildcard Characters</span></span>

<span data-ttu-id="8e471-177">Essa configuração indica se o valor do parâmetro pode conter caracteres curinga para que o valor do parâmetro possa ser correspondido a mais de um item existente no contêiner de destino.</span><span class="sxs-lookup"><span data-stu-id="8e471-177">This setting indicates whether the parameter's value can contain wildcard characters so that the parameter value can be matched to more than one existing item in the target container.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="8e471-178">Parâmetros comuns</span><span class="sxs-lookup"><span data-stu-id="8e471-178">Common Parameters</span></span>

<span data-ttu-id="8e471-179">Parâmetros comuns são parâmetros que você pode usar com qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e471-179">Common parameters are parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="8e471-180">Para obter mais informações sobre parâmetros comuns, consulte [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8e471-180">For more information about common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8e471-181">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e471-181">See also</span></span>

[<span data-ttu-id="8e471-182">about_Command_syntax</span><span class="sxs-lookup"><span data-stu-id="8e471-182">about_Command_syntax</span></span>](about_Command_syntax.md)

[<span data-ttu-id="8e471-183">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="8e471-183">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="8e471-184">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="8e471-184">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="8e471-185">about_Parameters_Default_Values</span><span class="sxs-lookup"><span data-stu-id="8e471-185">about_Parameters_Default_Values</span></span>](about_Parameters_Default_Values.md)

[<span data-ttu-id="8e471-186">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="8e471-186">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="8e471-187">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="8e471-187">about_Wildcards</span></span>](about_Wildcards.md)
