---
title: Declaração de atributo ValidateSet | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.openlocfilehash: 0b6833efb0ce8e9474e9d91049fd201fc845cbea
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787760"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="44a71-102">Declaração de atributo ValidateSet</span><span class="sxs-lookup"><span data-stu-id="44a71-102">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="44a71-103">O atributo ValidateSetAttribute especifica um conjunto de valores possíveis para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44a71-103">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="44a71-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44a71-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="44a71-105">Quando esse atributo é especificado, o tempo de execução do Windows PowerShell determina se o argumento fornecido para o parâmetro de cmdlet corresponde a um elemento no conjunto de elementos fornecido.</span><span class="sxs-lookup"><span data-stu-id="44a71-105">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="44a71-106">O cmdlet será executado somente se o argumento de parâmetro corresponder a um elemento no conjunto.</span><span class="sxs-lookup"><span data-stu-id="44a71-106">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="44a71-107">Se nenhuma correspondência for encontrada, um erro será gerado pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44a71-107">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="44a71-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="44a71-108">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="44a71-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="44a71-109">Parameters</span></span>

<span data-ttu-id="44a71-110">`ValidValues`([System. String](/dotnet/api/System.String)) necessário.</span><span class="sxs-lookup"><span data-stu-id="44a71-110">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="44a71-111">Especifica os valores de elemento de parâmetro válidos.</span><span class="sxs-lookup"><span data-stu-id="44a71-111">Specifies the valid parameter element values.</span></span> <span data-ttu-id="44a71-112">O exemplo a seguir mostra como especificar um elemento ou vários elementos.</span><span class="sxs-lookup"><span data-stu-id="44a71-112">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="44a71-113">`IgnoreCase`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="44a71-113">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="44a71-114">O valor padrão de `true` indica que o caso é ignorado.</span><span class="sxs-lookup"><span data-stu-id="44a71-114">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="44a71-115">Um valor `false` torna o cmdlet diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="44a71-115">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="44a71-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="44a71-116">Remarks</span></span>

- <span data-ttu-id="44a71-117">Esse atributo pode ser usado apenas uma vez por parâmetro.</span><span class="sxs-lookup"><span data-stu-id="44a71-117">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="44a71-118">Se o valor do parâmetro for uma matriz, cada elemento da matriz deverá corresponder a um elemento do conjunto de atributos.</span><span class="sxs-lookup"><span data-stu-id="44a71-118">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="44a71-119">O atributo ValidateSetAttribute é definido pela classe [System. Management. Automation. ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .</span><span class="sxs-lookup"><span data-stu-id="44a71-119">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a71-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44a71-120">See Also</span></span>

[<span data-ttu-id="44a71-121">System. Management. Automation. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="44a71-121">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="44a71-122">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44a71-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
