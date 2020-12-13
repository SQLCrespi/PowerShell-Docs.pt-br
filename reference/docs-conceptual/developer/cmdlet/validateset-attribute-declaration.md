---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateSet
description: Declaração de atributo ValidateSet
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660474"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="e5e05-103">Declaração de atributo ValidateSet</span><span class="sxs-lookup"><span data-stu-id="e5e05-103">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="e5e05-104">O atributo ValidateSetAttribute especifica um conjunto de valores possíveis para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5e05-104">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="e5e05-105">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5e05-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="e5e05-106">Quando esse atributo é especificado, o tempo de execução do Windows PowerShell determina se o argumento fornecido para o parâmetro de cmdlet corresponde a um elemento no conjunto de elementos fornecido.</span><span class="sxs-lookup"><span data-stu-id="e5e05-106">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="e5e05-107">O cmdlet será executado somente se o argumento de parâmetro corresponder a um elemento no conjunto.</span><span class="sxs-lookup"><span data-stu-id="e5e05-107">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="e5e05-108">Se nenhuma correspondência for encontrada, um erro será gerado pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5e05-108">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5e05-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e5e05-109">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="e5e05-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e5e05-110">Parameters</span></span>

<span data-ttu-id="e5e05-111">`ValidValues` ([System. String](/dotnet/api/System.String)) necessário.</span><span class="sxs-lookup"><span data-stu-id="e5e05-111">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="e5e05-112">Especifica os valores de elemento de parâmetro válidos.</span><span class="sxs-lookup"><span data-stu-id="e5e05-112">Specifies the valid parameter element values.</span></span> <span data-ttu-id="e5e05-113">O exemplo a seguir mostra como especificar um elemento ou vários elementos.</span><span class="sxs-lookup"><span data-stu-id="e5e05-113">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="e5e05-114">`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="e5e05-114">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="e5e05-115">O valor padrão de `true` indica que o caso é ignorado.</span><span class="sxs-lookup"><span data-stu-id="e5e05-115">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="e5e05-116">Um valor `false` torna o cmdlet diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e5e05-116">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5e05-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="e5e05-117">Remarks</span></span>

- <span data-ttu-id="e5e05-118">Esse atributo pode ser usado apenas uma vez por parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e5e05-118">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="e5e05-119">Se o valor do parâmetro for uma matriz, cada elemento da matriz deverá corresponder a um elemento do conjunto de atributos.</span><span class="sxs-lookup"><span data-stu-id="e5e05-119">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="e5e05-120">O atributo ValidateSetAttribute é definido pela classe [System. Management. Automation. ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e5e05-120">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5e05-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5e05-121">See Also</span></span>

[<span data-ttu-id="e5e05-122">System. Management. Automation. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="e5e05-122">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

<span data-ttu-id="e5e05-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e5e05-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
