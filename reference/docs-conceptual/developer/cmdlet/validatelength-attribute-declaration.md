---
title: Declaração de atributo ValidateLength | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369175"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="500d4-102">Declaração de atributo ValidateLength</span><span class="sxs-lookup"><span data-stu-id="500d4-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="500d4-103">O atributo ValidateLength especifica o número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="500d4-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="500d4-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="500d4-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="500d4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="500d4-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="500d4-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="500d4-106">Parameters</span></span>

<span data-ttu-id="500d4-107">`MinLength` ([System. Int32](/dotnet/api/System.Int32)) necessário.</span><span class="sxs-lookup"><span data-stu-id="500d4-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="500d4-108">Especifica o número mínimo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="500d4-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="500d4-109">`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) necessário.</span><span class="sxs-lookup"><span data-stu-id="500d4-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="500d4-110">Especifica o número máximo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="500d4-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="500d4-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="500d4-111">Remarks</span></span>

- <span data-ttu-id="500d4-112">Para obter mais informações sobre como declarar esse atributo, consulte [como declarar regras de validação de entrada](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="500d4-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="500d4-113">Quando esse atributo não é usado, o argumento de parâmetro correspondente pode ter qualquer comprimento.</span><span class="sxs-lookup"><span data-stu-id="500d4-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="500d4-114">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="500d4-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="500d4-115">Quando o valor do parâmetro de atributo `MaxLength` é menor que o valor do parâmetro de atributo `MinLength`.</span><span class="sxs-lookup"><span data-stu-id="500d4-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="500d4-116">Quando o parâmetro de atributo `MaxLength` é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="500d4-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="500d4-117">Quando o argumento não é uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="500d4-117">When the argument is not a string.</span></span>

- <span data-ttu-id="500d4-118">O atributo ValidateLength é definido pela classe [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .</span><span class="sxs-lookup"><span data-stu-id="500d4-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="500d4-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="500d4-119">See Also</span></span>

[<span data-ttu-id="500d4-120">System. Management. Automation. Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="500d4-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

<span data-ttu-id="500d4-121">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="500d4-121">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
