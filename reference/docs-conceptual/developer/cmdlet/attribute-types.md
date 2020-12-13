---
ms.date: 09/13/2016
ms.topic: reference
title: Tipos de atributo
description: Tipos de atributo
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667106"
---
# <a name="attribute-types"></a><span data-ttu-id="2eb0e-103">Tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="2eb0e-103">Attribute Types</span></span>

<span data-ttu-id="2eb0e-104">Os atributos de cmdlet podem ser agrupados por funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-104">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="2eb0e-105">As seções a seguir descrevem os atributos disponíveis e descrevem o que o tempo de execução faz quando o atributo é invocado.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-105">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="2eb0e-106">Atributos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="2eb0e-106">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="2eb0e-107">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2eb0e-107">Cmdlet</span></span>

<span data-ttu-id="2eb0e-108">Identifica uma classe de .NET Framework como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-108">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="2eb0e-109">Esse é o atributo base obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-109">This is the required base attribute.</span></span>
<span data-ttu-id="2eb0e-110">Para obter mais informações, consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-110">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="2eb0e-111">Atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="2eb0e-111">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="2eb0e-112">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="2eb0e-112">Parameter</span></span>

<span data-ttu-id="2eb0e-113">Identifica uma propriedade pública na classe cmdlet como um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-113">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="2eb0e-114">Para obter mais informações, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-114">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="2eb0e-115">Alias</span><span class="sxs-lookup"><span data-stu-id="2eb0e-115">Alias</span></span>

<span data-ttu-id="2eb0e-116">Especifica um ou mais aliases para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-116">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="2eb0e-117">Para obter mais informações, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-117">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="2eb0e-118">Atributos de validação de argumento</span><span class="sxs-lookup"><span data-stu-id="2eb0e-118">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="2eb0e-119">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="2eb0e-119">ValidateCount</span></span>

<span data-ttu-id="2eb0e-120">Especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-120">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="2eb0e-121">Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-121">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="2eb0e-122">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="2eb0e-122">ValidateLength</span></span>

<span data-ttu-id="2eb0e-123">Especifica um número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-123">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb0e-124">Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-124">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="2eb0e-125">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="2eb0e-125">ValidatePattern</span></span>

<span data-ttu-id="2eb0e-126">Especifica um padrão de expressão regular que o argumento do parâmetro cmdlet deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-126">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="2eb0e-127">Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-127">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="2eb0e-128">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="2eb0e-128">ValidateRange</span></span>

<span data-ttu-id="2eb0e-129">Especifica os valores mínimo e máximo para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-129">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb0e-130">Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-130">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="2eb0e-131">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="2eb0e-131">ValidateSet</span></span>

<span data-ttu-id="2eb0e-132">Especifica um conjunto de valores válidos para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-132">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb0e-133">Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-133">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2eb0e-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2eb0e-134">See Also</span></span>

[<span data-ttu-id="2eb0e-135">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2eb0e-135">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
