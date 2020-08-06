---
title: Declaração de atributo de parâmetro | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, Parameter
- Parameter attribute, described
- Parameter attribute
ms.openlocfilehash: 55b157b93c3a42324d63e16ddfa8db1f0d38f82b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781844"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="77ae9-102">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="77ae9-102">Parameter Attribute Declaration</span></span>

<span data-ttu-id="77ae9-103">O atributo Parameter identifica uma propriedade pública da classe cmdlet como um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77ae9-103">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="77ae9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="77ae9-104">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="77ae9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="77ae9-105">Parameters</span></span>

<span data-ttu-id="77ae9-106">`Mandatory`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-107">`True`indica que o parâmetro de cmdlet é necessário.</span><span class="sxs-lookup"><span data-stu-id="77ae9-107">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="77ae9-108">Se um parâmetro necessário não for fornecido quando o cmdlet for invocado, o Windows PowerShell solicitará ao usuário um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="77ae9-108">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="77ae9-109">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="77ae9-109">The default is `false`.</span></span>

<span data-ttu-id="77ae9-110">`ParameterSetName`([System. String](/dotnet/api/System.String)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-111">Especifica o conjunto de parâmetros ao qual este parâmetro de cmdlet pertence.</span><span class="sxs-lookup"><span data-stu-id="77ae9-111">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="77ae9-112">Se nenhum conjunto de parâmetros for especificado, o parâmetro pertencerá a todos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="77ae9-112">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="77ae9-113">`Position`([System. Int32](/dotnet/api/System.Int32)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-113">`Position` ([System.Int32](/dotnet/api/System.Int32)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-114">Especifica a posição do parâmetro em um comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77ae9-114">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="77ae9-115">`ValueFromPipeline`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-116">`True`indica que o parâmetro de cmdlet obtém seu valor de um objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="77ae9-116">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="77ae9-117">Especifique essa palavra-chave se o cmdlet acessar o objeto completo, não apenas uma propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="77ae9-117">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="77ae9-118">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="77ae9-118">The default is `false`.</span></span>

<span data-ttu-id="77ae9-119">`ValueFromPipelineByPropertyName`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-120">`True`indica que o parâmetro de cmdlet obtém seu valor de uma propriedade de um objeto de pipeline que tem o mesmo nome ou o mesmo alias que esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="77ae9-120">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="77ae9-121">Por exemplo, se o cmdlet tiver um `Name` parâmetro e o objeto de pipeline também tiver uma `Name` propriedade, o valor da `Name` propriedade será atribuído ao `Name` parâmetro do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77ae9-121">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="77ae9-122">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="77ae9-122">The default is `false`.</span></span>

<span data-ttu-id="77ae9-123">`ValueFromRemainingArguments`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="77ae9-124">`True`indica que o parâmetro de cmdlet aceita todos os argumentos restantes que são passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77ae9-124">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="77ae9-125">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="77ae9-125">The default is `false`.</span></span>

<span data-ttu-id="77ae9-126">`HelpMessage`Parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="77ae9-126">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="77ae9-127">Especifica uma breve descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="77ae9-127">Specifies a short description of the parameter.</span></span> <span data-ttu-id="77ae9-128">O Windows PowerShell exibe essa mensagem quando um cmdlet é executado e um parâmetro obrigatório não é especificado.</span><span class="sxs-lookup"><span data-stu-id="77ae9-128">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="77ae9-129">`HelpMessageBaseName`Parâmetro nomeado opcional. Especifica o local onde os identificadores de recursos residem.</span><span class="sxs-lookup"><span data-stu-id="77ae9-129">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="77ae9-130">Por exemplo, esse parâmetro pode especificar um assembly de recurso que contém mensagens de ajuda que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="77ae9-130">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="77ae9-131">`HelpMessageResourceId`Parâmetro nomeado opcional. Especifica o identificador de recurso para uma mensagem de ajuda.</span><span class="sxs-lookup"><span data-stu-id="77ae9-131">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="77ae9-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="77ae9-132">Remarks</span></span>

- <span data-ttu-id="77ae9-133">Para obter mais informações sobre como declarar esse atributo, consulte [como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="77ae9-133">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="77ae9-134">Um cmdlet pode ter qualquer número de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="77ae9-134">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="77ae9-135">No entanto, para uma melhor experiência do usuário, limite o número de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="77ae9-135">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="77ae9-136">Os parâmetros devem ser declarados em Propriedades ou campos públicos não estáticos.</span><span class="sxs-lookup"><span data-stu-id="77ae9-136">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="77ae9-137">Os parâmetros devem ser declarados em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="77ae9-137">Parameters should be declared on properties.</span></span> <span data-ttu-id="77ae9-138">A propriedade deve ter um acessador set público e, se a `ValueFromPipeline` `ValueFromPipelineByPropertyName` palavra-chave ou for especificada, a propriedade deverá ter um acessador get público.</span><span class="sxs-lookup"><span data-stu-id="77ae9-138">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="77ae9-139">Quando você especifica parâmetros posicionais, limite o número de parâmetros posicionais em um parâmetro definido para menos de cinco.</span><span class="sxs-lookup"><span data-stu-id="77ae9-139">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="77ae9-140">E os parâmetros posicionais não precisam ser contíguos.</span><span class="sxs-lookup"><span data-stu-id="77ae9-140">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="77ae9-141">As posições 5, 100 e 250 funcionam da mesma forma que as posições 0, 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="77ae9-141">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="77ae9-142">Quando a `Position` palavra-chave não for especificada, o parâmetro de cmdlet deverá ser referenciado por seu nome.</span><span class="sxs-lookup"><span data-stu-id="77ae9-142">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="77ae9-143">Ao usar conjuntos de parâmetros, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="77ae9-143">When you use parameter sets, note the following:</span></span>

  - <span data-ttu-id="77ae9-144">Cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo.</span><span class="sxs-lookup"><span data-stu-id="77ae9-144">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="77ae9-145">Um bom design de cmdlet indica que esse parâmetro exclusivo também deve ser obrigatório, se possível.</span><span class="sxs-lookup"><span data-stu-id="77ae9-145">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="77ae9-146">Se o cmdlet for projetado para ser executado sem parâmetros, o parâmetro exclusivo não poderá ser obrigatório.</span><span class="sxs-lookup"><span data-stu-id="77ae9-146">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

  - <span data-ttu-id="77ae9-147">Nenhum conjunto de parâmetros deve conter mais de um parâmetro posicional com a mesma posição.</span><span class="sxs-lookup"><span data-stu-id="77ae9-147">No parameter set should contain more than one positional parameter with the same position.</span></span>

  - <span data-ttu-id="77ae9-148">Somente um parâmetro em um conjunto de parâmetros deve declarar `ValueFromPipeline = true` .</span><span class="sxs-lookup"><span data-stu-id="77ae9-148">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="77ae9-149">Vários parâmetros podem ser definidos `ValueFromPipelineByPropertyName = true` .</span><span class="sxs-lookup"><span data-stu-id="77ae9-149">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

  - <span data-ttu-id="77ae9-150">Vários parâmetros podem ser definidos `ValueFromPipelineByPropertyName = true` .</span><span class="sxs-lookup"><span data-stu-id="77ae9-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="77ae9-151">Para obter mais informações sobre as diretrizes para nomes de parâmetro, consulte [nomes de parâmetro de cmdlet](standard-cmdlet-parameter-names-and-types.md).</span><span class="sxs-lookup"><span data-stu-id="77ae9-151">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="77ae9-152">O atributo de parâmetro é definido pela classe [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="77ae9-152">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="77ae9-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77ae9-153">See Also</span></span>

[<span data-ttu-id="77ae9-154">System. Management. Automation. ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="77ae9-154">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="77ae9-155">Nomes de parâmetro de cmdlet</span><span class="sxs-lookup"><span data-stu-id="77ae9-155">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="77ae9-156">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77ae9-156">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
