---
title: Declaração de atributo ValidateRange | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369125"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="e57d5-102">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="e57d5-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="e57d5-103">O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e57d5-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="e57d5-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57d5-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="e57d5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e57d5-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="e57d5-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e57d5-106">Parameters</span></span>

<span data-ttu-id="e57d5-107">`MinRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="e57d5-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="e57d5-108">Especifica o valor mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="e57d5-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="e57d5-109">`MaxRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="e57d5-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="e57d5-110">Especifica o valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="e57d5-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e57d5-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="e57d5-111">Remarks</span></span>

- <span data-ttu-id="e57d5-112">O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do parâmetro `MinRange` é maior que o valor do parâmetro `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="e57d5-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="e57d5-113">O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="e57d5-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="e57d5-114">Quando o valor do argumento é menor que o limite de `MinRange` ou maior que o limite de `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="e57d5-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="e57d5-115">Quando o argumento não é do mesmo tipo que os parâmetros `MinRange` e `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="e57d5-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="e57d5-116">O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e57d5-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e57d5-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e57d5-117">See Also</span></span>

[<span data-ttu-id="e57d5-118">System. Management. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="e57d5-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

<span data-ttu-id="e57d5-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e57d5-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
