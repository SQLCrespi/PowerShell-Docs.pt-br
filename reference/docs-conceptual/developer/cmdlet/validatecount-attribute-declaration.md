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
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692379"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="4799b-102">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="4799b-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="4799b-103">O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4799b-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="4799b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4799b-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="4799b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4799b-105">Parameters</span></span>

<span data-ttu-id="4799b-106">`MinLength`([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="4799b-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="4799b-107">Especifica o número mínimo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4799b-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="4799b-108">`MaxLength`([System. Int32][]) necessário.</span><span class="sxs-lookup"><span data-stu-id="4799b-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="4799b-109">Especifica o número máximo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4799b-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="4799b-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="4799b-110">Remarks</span></span>

- <span data-ttu-id="4799b-111">Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].</span><span class="sxs-lookup"><span data-stu-id="4799b-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="4799b-112">Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4799b-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="4799b-113">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="4799b-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="4799b-114">Os `MinLength` `MaxLength` parâmetros de atributo e não são do tipo [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="4799b-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="4799b-115">O valor do `MaxLength` parâmetro de atributo é menor que o valor do `MinLength` parâmetro de atributo.</span><span class="sxs-lookup"><span data-stu-id="4799b-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="4799b-116">O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .</span><span class="sxs-lookup"><span data-stu-id="4799b-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="4799b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4799b-117">See Also</span></span>

<span data-ttu-id="4799b-118">[System. Management. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="4799b-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="4799b-119">[Como validar uma contagem de argumentos][]</span><span class="sxs-lookup"><span data-stu-id="4799b-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="4799b-120">[Escrevendo um Cmdlet do Windows PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="4799b-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Escrevendo um Cmdlet do Windows PowerShell]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System. Int32]: /dotnet/api/System.Int32
[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
