---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateCount
description: Declaração de atributo ValidateCount
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646278"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="629eb-103">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="629eb-103">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="629eb-104">O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="629eb-104">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="629eb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="629eb-105">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="629eb-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="629eb-106">Parameters</span></span>

<span data-ttu-id="629eb-107">`MinLength` ([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="629eb-107">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="629eb-108">Especifica o número mínimo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="629eb-108">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="629eb-109">`MaxLength`([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="629eb-109">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="629eb-110">Especifica o número máximo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="629eb-110">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="629eb-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="629eb-111">Remarks</span></span>

- <span data-ttu-id="629eb-112">Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].</span><span class="sxs-lookup"><span data-stu-id="629eb-112">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="629eb-113">Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="629eb-113">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="629eb-114">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="629eb-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="629eb-115">Os `MinLength` `MaxLength` parâmetros de atributo e não são do tipo [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="629eb-115">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="629eb-116">O valor do `MaxLength` parâmetro de atributo é menor que o valor do `MinLength` parâmetro de atributo.</span><span class="sxs-lookup"><span data-stu-id="629eb-116">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="629eb-117">O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .</span><span class="sxs-lookup"><span data-stu-id="629eb-117">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="629eb-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="629eb-118">See Also</span></span>

<span data-ttu-id="629eb-119">[System. Management. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="629eb-119">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="629eb-120">[Como validar uma contagem de argumentos][]</span><span class="sxs-lookup"><span data-stu-id="629eb-120">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="629eb-121">[Writing a Windows PowerShell Cmdlet][] (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="629eb-121">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md (Escrevendo um Cmdlet do Windows PowerShell)

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
