---
title: Tipos de atributo | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782371"
---
# <a name="attribute-types"></a><span data-ttu-id="8cadb-102">Tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="8cadb-102">Attribute Types</span></span>

<span data-ttu-id="8cadb-103">Os atributos de cmdlet podem ser agrupados por funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="8cadb-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="8cadb-104">As seções a seguir descrevem os atributos disponíveis e descrevem o que o tempo de execução faz quando o atributo é invocado.</span><span class="sxs-lookup"><span data-stu-id="8cadb-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="8cadb-105">Atributos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cadb-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="8cadb-106">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cadb-106">Cmdlet</span></span>

<span data-ttu-id="8cadb-107">Identifica uma classe de .NET Framework como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="8cadb-108">Esse é o atributo base obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8cadb-108">This is the required base attribute.</span></span>
<span data-ttu-id="8cadb-109">Para obter mais informações, consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="8cadb-110">Atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="8cadb-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="8cadb-111">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="8cadb-111">Parameter</span></span>

<span data-ttu-id="8cadb-112">Identifica uma propriedade pública na classe cmdlet como um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="8cadb-113">Para obter mais informações, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="8cadb-114">Alias</span><span class="sxs-lookup"><span data-stu-id="8cadb-114">Alias</span></span>

<span data-ttu-id="8cadb-115">Especifica um ou mais aliases para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8cadb-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="8cadb-116">Para obter mais informações, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="8cadb-117">Atributos de validação de argumento</span><span class="sxs-lookup"><span data-stu-id="8cadb-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="8cadb-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="8cadb-118">ValidateCount</span></span>

<span data-ttu-id="8cadb-119">Especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="8cadb-120">Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="8cadb-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="8cadb-121">ValidateLength</span></span>

<span data-ttu-id="8cadb-122">Especifica um número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="8cadb-123">Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="8cadb-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="8cadb-124">ValidatePattern</span></span>

<span data-ttu-id="8cadb-125">Especifica um padrão de expressão regular que o argumento do parâmetro cmdlet deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="8cadb-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="8cadb-126">Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="8cadb-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="8cadb-127">ValidateRange</span></span>

<span data-ttu-id="8cadb-128">Especifica os valores mínimo e máximo para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="8cadb-129">Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="8cadb-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="8cadb-130">ValidateSet</span></span>

<span data-ttu-id="8cadb-131">Especifica um conjunto de valores válidos para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cadb-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="8cadb-132">Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8cadb-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8cadb-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8cadb-133">See Also</span></span>

[<span data-ttu-id="8cadb-134">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cadb-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
