---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateRange
description: Declaração de atributo ValidateRange
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660605"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="389e6-103">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="389e6-103">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="389e6-104">O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="389e6-104">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="389e6-105">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389e6-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="389e6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="389e6-106">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="389e6-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="389e6-107">Parameters</span></span>

<span data-ttu-id="389e6-108">`MinRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="389e6-108">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="389e6-109">Especifica o valor mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="389e6-109">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="389e6-110">`MaxRange` ([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="389e6-110">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="389e6-111">Especifica o valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="389e6-111">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="389e6-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="389e6-112">Remarks</span></span>

- <span data-ttu-id="389e6-113">O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do `MinRange` parâmetro é maior que o valor do `MaxRange` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="389e6-113">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="389e6-114">O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="389e6-114">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="389e6-115">Quando o valor do argumento é menor que o `MinRange` limite ou maior que o `MaxRange` limite.</span><span class="sxs-lookup"><span data-stu-id="389e6-115">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="389e6-116">Quando o argumento não é do mesmo tipo que os `MinRange` `MaxRange` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="389e6-116">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="389e6-117">O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="389e6-117">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="389e6-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="389e6-118">See Also</span></span>

[<span data-ttu-id="389e6-119">System. Management. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="389e6-119">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

<span data-ttu-id="389e6-120">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="389e6-120">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
