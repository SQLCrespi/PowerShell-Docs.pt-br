---
title: Declaração de atributo ValidateCount | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369225"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="864d6-102">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="864d6-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="864d6-103">O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="864d6-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="864d6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="864d6-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="864d6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="864d6-105">Parameters</span></span>

<span data-ttu-id="864d6-106">`MinLength` ([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="864d6-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="864d6-107">Especifica o número mínimo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="864d6-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="864d6-108">`MaxLength` ([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="864d6-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="864d6-109">Especifica o número máximo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="864d6-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="864d6-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="864d6-110">Remarks</span></span>

- <span data-ttu-id="864d6-111">Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].</span><span class="sxs-lookup"><span data-stu-id="864d6-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="864d6-112">Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="864d6-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="864d6-113">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="864d6-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="864d6-114">Os parâmetros de atributo `MinLength` e `MaxLength` não são do tipo [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="864d6-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

    - <span data-ttu-id="864d6-115">O valor do parâmetro de atributo `MaxLength` é menor que o valor do parâmetro de atributo `MinLength`.</span><span class="sxs-lookup"><span data-stu-id="864d6-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="864d6-116">O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .</span><span class="sxs-lookup"><span data-stu-id="864d6-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="864d6-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="864d6-117">See Also</span></span>

<span data-ttu-id="864d6-118">[System. Management. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="864d6-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="864d6-119">[Como validar uma contagem de argumentos][]</span><span class="sxs-lookup"><span data-stu-id="864d6-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="864d6-120">[Writing a Windows PowerShell Cmdlet][] (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="864d6-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md (Escrevendo um Cmdlet do Windows PowerShell)

[System. Int32]: /dotnet/api/System.Int32
[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
