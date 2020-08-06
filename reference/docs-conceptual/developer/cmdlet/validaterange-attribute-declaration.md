---
title: Declaração de atributo ValidateRange | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787777"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="3e4f7-102">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="3e4f7-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="3e4f7-103">O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="3e4f7-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e4f7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e4f7-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="3e4f7-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3e4f7-106">Parameters</span></span>

<span data-ttu-id="3e4f7-107">`MinRange`([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="3e4f7-108">Especifica o valor mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="3e4f7-109">`MaxRange`([System. Object](/dotnet/api/system.object)) necessário.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="3e4f7-110">Especifica o valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e4f7-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="3e4f7-111">Remarks</span></span>

- <span data-ttu-id="3e4f7-112">O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do `MinRange` parâmetro é maior que o valor do `MaxRange` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="3e4f7-113">O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="3e4f7-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="3e4f7-114">Quando o valor do argumento é menor que o `MinRange` limite ou maior que o `MaxRange` limite.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="3e4f7-115">Quando o argumento não é do mesmo tipo que os `MinRange` `MaxRange` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="3e4f7-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="3e4f7-116">O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="3e4f7-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e4f7-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e4f7-117">See Also</span></span>

[<span data-ttu-id="3e4f7-118">System. Management. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="3e4f7-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="3e4f7-119">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e4f7-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
