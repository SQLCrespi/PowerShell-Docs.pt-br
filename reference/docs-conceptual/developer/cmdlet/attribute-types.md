---
title: Tipos de atributo | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364575"
---
# <a name="attribute-types"></a><span data-ttu-id="3bb64-102">Tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="3bb64-102">Attribute Types</span></span>

<span data-ttu-id="3bb64-103">Os atributos de cmdlet podem ser agrupados por funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="3bb64-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="3bb64-104">As seções a seguir descrevem os atributos disponíveis e descrevem o que o tempo de execução faz quando o atributo é invocado.</span><span class="sxs-lookup"><span data-stu-id="3bb64-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="3bb64-105">Atributos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="3bb64-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="3bb64-106">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3bb64-106">Cmdlet</span></span>

<span data-ttu-id="3bb64-107">Identifica uma classe de .NET Framework como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="3bb64-108">Esse é o atributo base obrigatório.</span><span class="sxs-lookup"><span data-stu-id="3bb64-108">This is the required base attribute.</span></span>
<span data-ttu-id="3bb64-109">Para obter mais informações, consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="3bb64-110">Atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="3bb64-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="3bb64-111">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3bb64-111">Parameter</span></span>

<span data-ttu-id="3bb64-112">Identifica uma propriedade pública na classe cmdlet como um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="3bb64-113">Para obter mais informações, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="3bb64-114">Alias</span><span class="sxs-lookup"><span data-stu-id="3bb64-114">Alias</span></span>

<span data-ttu-id="3bb64-115">Especifica um ou mais aliases para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3bb64-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="3bb64-116">Para obter mais informações, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="3bb64-117">Atributos de validação de argumento</span><span class="sxs-lookup"><span data-stu-id="3bb64-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="3bb64-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="3bb64-118">ValidateCount</span></span>

<span data-ttu-id="3bb64-119">Especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="3bb64-120">Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="3bb64-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="3bb64-121">ValidateLength</span></span>

<span data-ttu-id="3bb64-122">Especifica um número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="3bb64-123">Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="3bb64-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="3bb64-124">ValidatePattern</span></span>

<span data-ttu-id="3bb64-125">Especifica um padrão de expressão regular que o argumento do parâmetro cmdlet deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="3bb64-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="3bb64-126">Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="3bb64-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="3bb64-127">ValidateRange</span></span>

<span data-ttu-id="3bb64-128">Especifica os valores mínimo e máximo para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="3bb64-129">Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="3bb64-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="3bb64-130">ValidateSet</span></span>

<span data-ttu-id="3bb64-131">Especifica um conjunto de valores válidos para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bb64-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="3bb64-132">Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3bb64-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3bb64-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3bb64-133">See Also</span></span>

[<span data-ttu-id="3bb64-134">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb64-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
