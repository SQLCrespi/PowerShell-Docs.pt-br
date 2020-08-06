---
title: Declaração de atributo ValidateCount | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786315"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="98340-102">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="98340-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="98340-103">O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98340-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="98340-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="98340-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="98340-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="98340-105">Parameters</span></span>

<span data-ttu-id="98340-106">`MinLength`([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="98340-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="98340-107">Especifica o número mínimo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="98340-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="98340-108">`MaxLength`([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="98340-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="98340-109">Especifica o número máximo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="98340-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="98340-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="98340-110">Remarks</span></span>

- <span data-ttu-id="98340-111">Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].</span><span class="sxs-lookup"><span data-stu-id="98340-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="98340-112">Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="98340-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="98340-113">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="98340-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="98340-114">Os `MinLength` `MaxLength` parâmetros de atributo e não são do tipo [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="98340-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="98340-115">O valor do `MaxLength` parâmetro de atributo é menor que o valor do `MinLength` parâmetro de atributo.</span><span class="sxs-lookup"><span data-stu-id="98340-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="98340-116">O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .</span><span class="sxs-lookup"><span data-stu-id="98340-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="98340-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98340-117">See Also</span></span>

<span data-ttu-id="98340-118">[System. Management. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="98340-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="98340-119">[Como validar uma contagem de argumentos][]</span><span class="sxs-lookup"><span data-stu-id="98340-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="98340-120">[Escrevendo um Cmdlet do Windows PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="98340-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Escrevendo um Cmdlet do Windows PowerShell]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System. Int32]: /dotnet/api/System.Int32
[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
