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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067171"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="546eb-102">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="546eb-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="546eb-103">O atributo ValidateCount Especifica o número mínimo e máximo de argumentos permitido para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="546eb-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="546eb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="546eb-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="546eb-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="546eb-105">Parameters</span></span>

<span data-ttu-id="546eb-106">`MinLength` ([System.Int32][]) Required.</span><span class="sxs-lookup"><span data-stu-id="546eb-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="546eb-107">Especifica o número mínimo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="546eb-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="546eb-108">`MaxLength`([System.Int32][]) Required.</span><span class="sxs-lookup"><span data-stu-id="546eb-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="546eb-109">Especifica o número máximo de argumentos.</span><span class="sxs-lookup"><span data-stu-id="546eb-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="546eb-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="546eb-110">Remarks</span></span>

- <span data-ttu-id="546eb-111">Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumento][].</span><span class="sxs-lookup"><span data-stu-id="546eb-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="546eb-112">Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="546eb-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="546eb-113">O tempo de execução do Windows PowerShell gera um erro sob as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="546eb-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="546eb-114">O `MinLength` e `MaxLength` parâmetros de atributo não são do tipo [System.Int32][].</span><span class="sxs-lookup"><span data-stu-id="546eb-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

    - <span data-ttu-id="546eb-115">O valor da `MaxLength` parâmetro de atributo é menor que o valor da `MinLength` parâmetro do atributo.</span><span class="sxs-lookup"><span data-stu-id="546eb-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="546eb-116">O atributo ValidateCount é definido pela [System.Management.Automation.ValidateCountAttribute][] classe.</span><span class="sxs-lookup"><span data-stu-id="546eb-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="546eb-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="546eb-117">See Also</span></span>

<span data-ttu-id="546eb-118">[System.Management.Automation.ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="546eb-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="546eb-119">[Como validar uma contagem de argumento][]</span><span class="sxs-lookup"><span data-stu-id="546eb-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="546eb-120">[Writing a Windows PowerShell Cmdlet][] (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="546eb-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Como validar uma contagem de argumento]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md (Escrevendo um Cmdlet do Windows PowerShell)

[System.Int32]: /dotnet/api/System.Int32
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
