---
description: Descreve como trabalhar com parâmetros de comando no PowerShell.
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: c9d7ab62c13a7cafcf93103f9a70f6575d5dd7b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598852"
---
# <a name="about-parameters"></a><span data-ttu-id="86999-103">Sobre parâmetros</span><span class="sxs-lookup"><span data-stu-id="86999-103">About Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="86999-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="86999-104">Short description</span></span>
<span data-ttu-id="86999-105">Descreve como trabalhar com parâmetros de comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86999-105">Describes how to work with command parameters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="86999-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="86999-106">Long description</span></span>

<span data-ttu-id="86999-107">A maioria dos comandos do PowerShell, como cmdlets, funções e scripts, depende de parâmetros para permitir que os usuários selecionem opções ou forneçam entradas.</span><span class="sxs-lookup"><span data-stu-id="86999-107">Most PowerShell commands, such as cmdlets, functions, and scripts, rely on parameters to allow users to select options or provide input.</span></span> <span data-ttu-id="86999-108">Os parâmetros seguem o nome do comando e têm o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="86999-108">The parameters follow the command name and have the following form:</span></span>

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

<span data-ttu-id="86999-109">O nome do parâmetro é precedido por um hífen (-), que sinaliza ao PowerShell que a palavra que segue o hífen é um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-109">The name of the parameter is preceded by a hyphen (-), which signals to PowerShell that the word following the hyphen is a parameter name.</span></span> <span data-ttu-id="86999-110">O nome e o valor do parâmetro podem ser separados por um espaço ou um caractere de dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="86999-110">The parameter name and value can be separated by a space or a colon character.</span></span> <span data-ttu-id="86999-111">Alguns parâmetros não exigem ou aceitam um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-111">Some parameters do not require or accept a parameter value.</span></span> <span data-ttu-id="86999-112">Outros parâmetros exigem um valor, mas não exigem o nome do parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="86999-112">Other parameters require a value, but do not require the parameter name in the command.</span></span>

<span data-ttu-id="86999-113">O tipo de parâmetros e os requisitos para esses parâmetros variam.</span><span class="sxs-lookup"><span data-stu-id="86999-113">The type of parameters and the requirements for those parameters vary.</span></span> <span data-ttu-id="86999-114">Para localizar informações sobre os parâmetros de um comando, use o `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86999-114">To find information about the parameters of a command, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="86999-115">Por exemplo, para encontrar informações sobre os parâmetros do `Get-ChildItem` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="86999-115">For example, to find information about the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="86999-116">Para encontrar informações sobre os parâmetros de um script, use o caminho completo para o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="86999-116">To find information about the parameters of a script, use the full path to the script file.</span></span> <span data-ttu-id="86999-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86999-117">For example:</span></span>

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

<span data-ttu-id="86999-118">O `Get-Help` cmdlet retorna vários detalhes sobre o comando, incluindo uma descrição, a sintaxe do comando, informações sobre os parâmetros e exemplos que mostram como usar os parâmetros em um comando.</span><span class="sxs-lookup"><span data-stu-id="86999-118">The `Get-Help` cmdlet returns various details about the command, including a description, the command syntax, information about the parameters, and examples showing how to use the parameters in a command.</span></span>

<span data-ttu-id="86999-119">Você também pode usar o parâmetro Parameter do `Get-Help` cmdlet para encontrar informações sobre um determinado parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-119">You can also use the Parameter parameter of the `Get-Help` cmdlet to find information about a particular parameter.</span></span> <span data-ttu-id="86999-120">Ou, você pode usar o parâmetro **Parameter** com o valor Character curinga ( `*` ) para encontrar informações sobre todos os parâmetros do comando.</span><span class="sxs-lookup"><span data-stu-id="86999-120">Or, you can use the **Parameter** parameter with the wildcard character ( `*` ) value to find information about all parameters of the command.</span></span> <span data-ttu-id="86999-121">Por exemplo, o comando a seguir obtém informações sobre todos os parâmetros do `Get-Member` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="86999-121">For example, the following command gets information about all parameters of the `Get-Member` cmdlet:</span></span>

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a><span data-ttu-id="86999-122">Valores do parâmetro padrão</span><span class="sxs-lookup"><span data-stu-id="86999-122">Default parameter values</span></span>

<span data-ttu-id="86999-123">Os parâmetros opcionais têm um valor padrão, que é o valor que é usado ou assumido quando o parâmetro não é especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="86999-123">Optional parameters have a default value, which is the value that is used or assumed when the parameter is not specified in the command.</span></span>

<span data-ttu-id="86999-124">Por exemplo, o valor padrão do parâmetro **ComputerName** de muitos cmdlets é o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="86999-124">For example, the default value of the **ComputerName** parameter of many cmdlets is the name of the local computer.</span></span> <span data-ttu-id="86999-125">Como resultado, o nome do computador local é usado no comando, a menos que o parâmetro **ComputerName** seja especificado.</span><span class="sxs-lookup"><span data-stu-id="86999-125">As a result, the local computer name is used in the command unless the **ComputerName** parameter is specified.</span></span>

<span data-ttu-id="86999-126">Para localizar o valor do parâmetro padrão, consulte o tópico da ajuda para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86999-126">To find the default parameter value, see help topic for the cmdlet.</span></span> <span data-ttu-id="86999-127">A descrição do parâmetro deve incluir o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="86999-127">The parameter description should include the default value.</span></span>

<span data-ttu-id="86999-128">Você também pode definir um valor padrão personalizado para qualquer parâmetro de um cmdlet ou função avançada.</span><span class="sxs-lookup"><span data-stu-id="86999-128">You can also set a custom default value for any parameter of a cmdlet or advanced function.</span></span> <span data-ttu-id="86999-129">Para obter informações sobre como definir valores padrão personalizados, consulte [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="86999-129">For information about setting custom default values, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="86999-130">Tabela de atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="86999-130">Parameter attribute table</span></span>

<span data-ttu-id="86999-131">Quando você usa os parâmetros **completo**, **parâmetro** ou **online** do `Get-Help` cmdlet, `Get-Help` o exibe uma tabela de atributos de parâmetro com informações detalhadas sobre o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-131">When you use the **Full**, **Parameter**, or **Online** parameters of the `Get-Help` cmdlet, `Get-Help` displays a parameter attribute table with detailed information about the parameter.</span></span>

<span data-ttu-id="86999-132">Essas informações incluem os detalhes que você precisa saber para usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-132">This information includes the details you need to know to use the parameter.</span></span>
<span data-ttu-id="86999-133">Por exemplo, o tópico da ajuda para o `Get-ChildItem` cmdlet inclui os seguintes detalhes sobre seu parâmetro de caminho:</span><span class="sxs-lookup"><span data-stu-id="86999-133">For example, the help topic for the `Get-ChildItem` cmdlet includes the following details about its Path parameter:</span></span>

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

<span data-ttu-id="86999-134">As informações de parâmetro incluem a sintaxe do parâmetro, uma descrição do parâmetro e os atributos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-134">The parameter information includes the parameter syntax, a description of the parameter, and the parameter attributes.</span></span> <span data-ttu-id="86999-135">As seções a seguir descrevem os atributos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-135">The following sections describe the parameter attributes.</span></span>

#### <a name="parameter-required"></a><span data-ttu-id="86999-136">Parâmetro necessário</span><span class="sxs-lookup"><span data-stu-id="86999-136">Parameter Required</span></span>

<span data-ttu-id="86999-137">Essa configuração indica se o parâmetro é obrigatório, ou seja, se todos os comandos que usam esse cmdlet devem incluir esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-137">This setting indicates whether the parameter is mandatory, that is, whether all commands that use this cmdlet must include this parameter.</span></span> <span data-ttu-id="86999-138">Quando o valor for **true** e o parâmetro estiver ausente no comando, o PowerShell solicitará um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-138">When the value is **True** and the parameter is missing from the command, PowerShell prompts you for a value for the parameter.</span></span>

#### <a name="parameter-position"></a><span data-ttu-id="86999-139">Posição do parâmetro</span><span class="sxs-lookup"><span data-stu-id="86999-139">Parameter Position</span></span>

<span data-ttu-id="86999-140">Se a `Position` configuração for definida como um inteiro positivo, o nome do parâmetro não será necessário.</span><span class="sxs-lookup"><span data-stu-id="86999-140">If the `Position` setting is set to a positive integer, the parameter name is not required.</span></span> <span data-ttu-id="86999-141">Esse tipo de parâmetro é conhecido como um parâmetro posicional e o número indica a posição em que o parâmetro deve aparecer em relação a outros parâmetros de posição.</span><span class="sxs-lookup"><span data-stu-id="86999-141">This type of parameter is referred to as a positional parameter, and the number indicates the position in which the parameter must appear in relation to other positional parameters.</span></span> <span data-ttu-id="86999-142">Um parâmetro nomeado pode ser listado em qualquer posição após o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86999-142">A named parameter can be listed in any position after the cmdlet name.</span></span> <span data-ttu-id="86999-143">Se você incluir o nome do parâmetro para um parâmetro posicional, o parâmetro poderá ser listado em qualquer posição após o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86999-143">If you include the parameter name for a positional parameter, the parameter can be listed in any position after the cmdlet name.</span></span>

<span data-ttu-id="86999-144">Por exemplo, o `Get-ChildItem` cmdlet tem parâmetros Path e exclude.</span><span class="sxs-lookup"><span data-stu-id="86999-144">For example, the `Get-ChildItem` cmdlet has Path and Exclude parameters.</span></span> <span data-ttu-id="86999-145">A `Position` configuração para **Path** é **0**, o que significa que ele é um parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="86999-145">The `Position` setting for **Path** is **0**, which means that it is a positional parameter.</span></span> <span data-ttu-id="86999-146">A `Position` configuração para **excluir** é **denominada**.</span><span class="sxs-lookup"><span data-stu-id="86999-146">The `Position` setting for **Exclude** is **named**.</span></span>

<span data-ttu-id="86999-147">Isso significa que o **caminho** não requer o nome do parâmetro, mas seu valor de parâmetro deve ser o primeiro ou apenas o valor do parâmetro não nomeado no comando.</span><span class="sxs-lookup"><span data-stu-id="86999-147">This means that **Path** does not require the parameter name, but its parameter value must be the first or only unnamed parameter value in the command.</span></span>
<span data-ttu-id="86999-148">No entanto, como o parâmetro Exclude é um parâmetro nomeado, você pode colocá-lo em qualquer posição no comando.</span><span class="sxs-lookup"><span data-stu-id="86999-148">However, because the Exclude parameter is a named parameter, you can place it in any position in the command.</span></span>

<span data-ttu-id="86999-149">Como resultado das `Position` configurações para esses dois parâmetros, você pode usar qualquer um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="86999-149">As a result of the `Position` settings for these two parameters, you can use any of the following commands:</span></span>

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

<span data-ttu-id="86999-150">Se você tiver que incluir outro parâmetro posicional sem incluir o nome do parâmetro, esse parâmetro deverá ser colocado na ordem especificada pela `Position` configuração.</span><span class="sxs-lookup"><span data-stu-id="86999-150">If you were to include another positional parameter without including the parameter name, that parameter must be placed in the order specified by the `Position` setting.</span></span>

#### <a name="parameter-type"></a><span data-ttu-id="86999-151">Tipo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="86999-151">Parameter Type</span></span>

<span data-ttu-id="86999-152">Essa configuração especifica o tipo de Microsoft .NET Framework do valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-152">This setting specifies the Microsoft .NET Framework type of the parameter value.</span></span> <span data-ttu-id="86999-153">Por exemplo, se o tipo for **Int32**, o valor do parâmetro deverá ser um inteiro.</span><span class="sxs-lookup"><span data-stu-id="86999-153">For example, if the type is **Int32**, the parameter value must be an integer.</span></span> <span data-ttu-id="86999-154">Se o tipo for String, o valor do parâmetro deverá ser uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="86999-154">If the type is string, the parameter value must be a character string.</span></span> <span data-ttu-id="86999-155">Se a cadeia de caracteres contiver espaços, o valor deverá ser colocado entre aspas ou os espaços devem ser precedidos pelo caractere de escape (').</span><span class="sxs-lookup"><span data-stu-id="86999-155">If the string contains spaces, the value must be enclosed in quotation marks, or the spaces must be preceded by the escape character ( \` ).</span></span>

#### <a name="default-value"></a><span data-ttu-id="86999-156">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="86999-156">Default Value</span></span>

<span data-ttu-id="86999-157">Essa configuração especifica o valor que o parâmetro assumirá se nenhum outro valor for fornecido.</span><span class="sxs-lookup"><span data-stu-id="86999-157">This setting specifies the value that the parameter will assume if no other value is provided.</span></span> <span data-ttu-id="86999-158">Por exemplo, o valor padrão do parâmetro Path é geralmente o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="86999-158">For example, the default value of the Path parameter is often the current directory.</span></span> <span data-ttu-id="86999-159">Os parâmetros necessários nunca têm um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="86999-159">Required parameters never have a default value.</span></span>
<span data-ttu-id="86999-160">Para muitos parâmetros opcionais, não há nenhum padrão porque o parâmetro não tem efeito se não for usado.</span><span class="sxs-lookup"><span data-stu-id="86999-160">For many optional parameters, there is no default because the parameter has no effect if it is not used.</span></span>

#### <a name="accepts-multiple-values"></a><span data-ttu-id="86999-161">Aceita vários valores</span><span class="sxs-lookup"><span data-stu-id="86999-161">Accepts Multiple Values</span></span>

<span data-ttu-id="86999-162">Essa configuração indica se um parâmetro aceita vários valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-162">This setting indicates whether a parameter accepts multiple parameter values.</span></span>
<span data-ttu-id="86999-163">Quando um parâmetro aceita vários valores, você pode digitar uma lista separada por vírgulas como o valor do parâmetro no comando ou salvar uma lista separada por vírgulas (uma matriz) em uma variável e, em seguida, especificar a variável como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-163">When a parameter accepts multiple values, you can type a comma-separated list as the value of the parameter in the command, or save a comma-separated list (an array) in a variable, and then specify the variable as the parameter value.</span></span>

<span data-ttu-id="86999-164">Por exemplo, o parâmetro ServiceName do `Get-Service` cmdlet aceita vários valores.</span><span class="sxs-lookup"><span data-stu-id="86999-164">For example, the ServiceName parameter of the `Get-Service` cmdlet accepts multiple values.</span></span> <span data-ttu-id="86999-165">Os seguintes comandos são válidos:</span><span class="sxs-lookup"><span data-stu-id="86999-165">The following commands are both valid:</span></span>

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a><span data-ttu-id="86999-166">Aceita entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="86999-166">Accepts Pipeline Input</span></span>

<span data-ttu-id="86999-167">Essa configuração indica se você pode usar o operador de pipeline ( `|` ) para enviar um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-167">This setting indicates whether you can use the pipeline operator ( `|` ) to send a value to the parameter.</span></span>

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

<span data-ttu-id="86999-168">Quando um parâmetro é "true (por valor)", o PowerShell tenta associar quaisquer valores de pipe com esse parâmetro antes de tentar outros métodos para interpretar o comando.</span><span class="sxs-lookup"><span data-stu-id="86999-168">When a parameter is "True (by Value)", PowerShell tries to associate any piped values with that parameter before it tries other methods to interpret the command.</span></span>

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

<span data-ttu-id="86999-169">Por exemplo, você pode canalizar um valor para um parâmetro de **nome** somente quando o valor tiver uma propriedade chamada **Name**.</span><span class="sxs-lookup"><span data-stu-id="86999-169">For example, you can pipe a value to a **Name** parameter only when the value has a property called **Name**.</span></span>

> [!NOTE]
> <span data-ttu-id="86999-170">Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de **ligação de atraso** no parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-170">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
>
> <span data-ttu-id="86999-171">O bloco de script de **ligação de atraso** é executado automaticamente durante o **parâmetrobinding**.</span><span class="sxs-lookup"><span data-stu-id="86999-171">The **delay-bind** script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="86999-172">O resultado é associado ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="86999-172">The result is bound to the parameter.</span></span> <span data-ttu-id="86999-173">A associação de atraso **não funciona para** parâmetros definidos como tipo `ScriptBlock` ou `System.Object` , o bloco de script é passado **sem** ser invocado.</span><span class="sxs-lookup"><span data-stu-id="86999-173">Delay binding does **not** work for parameters defined as type `ScriptBlock` or `System.Object`, the script block is passed through **without** being invoked.</span></span>
>
> <span data-ttu-id="86999-174">Você pode ler sobre blocos **de script de ligação de atraso** aqui [about_Script_Blocks. MD](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="86999-174">You can read about **delay-bind** script blocks here [about_Script_Blocks.md](about_Script_Blocks.md)</span></span>

#### <a name="accepts-wildcard-characters"></a><span data-ttu-id="86999-175">Aceita caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="86999-175">Accepts Wildcard Characters</span></span>

<span data-ttu-id="86999-176">Essa configuração indica se o valor do parâmetro pode conter caracteres curinga para que o valor do parâmetro possa ser correspondido a mais de um item existente no contêiner de destino.</span><span class="sxs-lookup"><span data-stu-id="86999-176">This setting indicates whether the parameter's value can contain wildcard characters so that the parameter value can be matched to more than one existing item in the target container.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="86999-177">Parâmetros comuns</span><span class="sxs-lookup"><span data-stu-id="86999-177">Common Parameters</span></span>

<span data-ttu-id="86999-178">Parâmetros comuns são parâmetros que você pode usar com qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86999-178">Common parameters are parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="86999-179">Para obter mais informações sobre parâmetros comuns, consulte [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="86999-179">For more information about common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="86999-180">Consulte também</span><span class="sxs-lookup"><span data-stu-id="86999-180">See also</span></span>

[<span data-ttu-id="86999-181">about_Command_syntax</span><span class="sxs-lookup"><span data-stu-id="86999-181">about_Command_syntax</span></span>](about_Command_syntax.md)

[<span data-ttu-id="86999-182">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="86999-182">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="86999-183">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="86999-183">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="86999-184">about_Parameters_Default_Values</span><span class="sxs-lookup"><span data-stu-id="86999-184">about_Parameters_Default_Values</span></span>](about_Parameters_Default_Values.md)

[<span data-ttu-id="86999-185">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="86999-185">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="86999-186">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="86999-186">about_Wildcards</span></span>](about_Wildcards.md)

