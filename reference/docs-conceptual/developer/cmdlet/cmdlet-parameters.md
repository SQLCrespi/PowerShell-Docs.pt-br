---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de cmdlets
description: Parâmetros de cmdlets
ms.openlocfilehash: 1ab495cb674f6b2cd769c3f64d899aec67704216
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668262"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="df01d-103">Parâmetros de cmdlets</span><span class="sxs-lookup"><span data-stu-id="df01d-103">Cmdlet Parameters</span></span>

<span data-ttu-id="df01d-104">Os parâmetros de cmdlet fornecem o mecanismo que permite que um cmdlet aceite entrada.</span><span class="sxs-lookup"><span data-stu-id="df01d-104">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="df01d-105">Os parâmetros podem aceitar a entrada diretamente da linha de comando ou de objetos passados para o cmdlet por meio do pipeline, os argumentos (também conhecidos como *valores*) desses parâmetros podem especificar a entrada que o cmdlet aceita, como o cmdlet deve executar suas ações e os dados que o cmdlet retorna para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="df01d-105">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="df01d-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="df01d-106">In This Section</span></span>

<span data-ttu-id="df01d-107">[Declarando propriedades como parâmetros](./declaring-properties-as-parameters.md) Fornece informações básicas que você deve entender antes de declarar os parâmetros de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df01d-107">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="df01d-108">[Tipos de parâmetros de cmdlet](./types-of-cmdlet-parameters.md) Descreve os diferentes tipos de parâmetros que você pode declarar em cmdlets.</span><span class="sxs-lookup"><span data-stu-id="df01d-108">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="df01d-109">[Diretrizes de funcionalidade e nome de parâmetro de cmdlet](./standard-cmdlet-parameter-names-and-types.md) Discute os nomes, o tipo de dados recomendado e a funcionalidade dos parâmetros padrão.</span><span class="sxs-lookup"><span data-stu-id="df01d-109">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discusses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="df01d-110">[Aliases de parâmetro](./parameter-aliases.md) Discute os aliases que você pode definir para parâmetros.</span><span class="sxs-lookup"><span data-stu-id="df01d-110">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="df01d-111">[Nomes de parâmetro comuns](./common-parameter-names.md) Este tópico descreve os parâmetros que o Windows PowerShell adiciona aos cmdlets do.</span><span class="sxs-lookup"><span data-stu-id="df01d-111">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="df01d-112">[Conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md) Discute como os conjuntos de parâmetros permitem que você escreva um único cmdlet que possa executar ações diferentes para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="df01d-112">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="df01d-113">[Parâmetros dinâmicos de cmdlet](./cmdlet-dynamic-parameters.md) Discute os parâmetros que estão disponíveis para o usuário em condições especiais.</span><span class="sxs-lookup"><span data-stu-id="df01d-113">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="df01d-114">[Suporte a caracteres curinga em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md) Descreve como fornecer suporte para caracteres curinga quando você cria um cmdlet que será executado em um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="df01d-114">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="df01d-115">[Validando entrada de parâmetro](./validating-parameter-input.md) Descreve como o Windows PowerShell valida os argumentos passados para parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df01d-115">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="df01d-116">[Parâmetros de filtro de entrada](./input-filter-parameters.md) Discute os `Filter` parâmetros, `Include` e `Exclude` que filtram o conjunto de objetos de entrada que o cmdlet afeta.</span><span class="sxs-lookup"><span data-stu-id="df01d-116">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="df01d-117">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="df01d-117">Related Sections</span></span>

[<span data-ttu-id="df01d-118">Como validar a entrada de parâmetro</span><span class="sxs-lookup"><span data-stu-id="df01d-118">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="df01d-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df01d-119">See Also</span></span>

[<span data-ttu-id="df01d-120">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="df01d-120">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="df01d-121">Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df01d-121">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)
