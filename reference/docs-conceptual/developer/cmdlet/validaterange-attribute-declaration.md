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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369125"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="d47fa-102">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="d47fa-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="d47fa-103">O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d47fa-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="d47fa-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d47fa-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="d47fa-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d47fa-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="d47fa-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d47fa-106">Parameters</span></span>

<span data-ttu-id="d47fa-107">`MinRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="d47fa-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="d47fa-108">Especifica o valor mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="d47fa-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="d47fa-109">`MaxRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="d47fa-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="d47fa-110">Especifica o valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="d47fa-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d47fa-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="d47fa-111">Remarks</span></span>

- <span data-ttu-id="d47fa-112">O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do parâmetro `MinRange` é maior que o valor do parâmetro `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="d47fa-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="d47fa-113">O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="d47fa-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="d47fa-114">Quando o valor do argumento é menor que o limite de `MinRange` ou maior que o limite de `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="d47fa-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="d47fa-115">Quando o argumento não é do mesmo tipo que o `MinRange` e os parâmetros de `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="d47fa-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="d47fa-116">O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="d47fa-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d47fa-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d47fa-117">See Also</span></span>

[<span data-ttu-id="d47fa-118">System. Management. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="d47fa-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

<span data-ttu-id="d47fa-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="d47fa-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
