---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateLength
description: Declaração de atributo ValidateLength
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646187"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="0138e-103">Declaração de atributo ValidateLength</span><span class="sxs-lookup"><span data-stu-id="0138e-103">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="0138e-104">O atributo ValidateLength especifica o número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0138e-104">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="0138e-105">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0138e-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="0138e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0138e-106">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="0138e-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0138e-107">Parameters</span></span>

<span data-ttu-id="0138e-108">`MinLength` ([System. Int32](/dotnet/api/System.Int32)) necessário.</span><span class="sxs-lookup"><span data-stu-id="0138e-108">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="0138e-109">Especifica o número mínimo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="0138e-109">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="0138e-110">`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) necessário.</span><span class="sxs-lookup"><span data-stu-id="0138e-110">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="0138e-111">Especifica o número máximo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="0138e-111">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="0138e-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="0138e-112">Remarks</span></span>

- <span data-ttu-id="0138e-113">Para obter mais informações sobre como declarar esse atributo, consulte [como declarar regras de validação de entrada](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="0138e-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="0138e-114">Quando esse atributo não é usado, o argumento de parâmetro correspondente pode ter qualquer comprimento.</span><span class="sxs-lookup"><span data-stu-id="0138e-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="0138e-115">O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="0138e-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="0138e-116">Quando o valor do `MaxLength` parâmetro Attribute é menor que o valor do `MinLength` parâmetro Attribute.</span><span class="sxs-lookup"><span data-stu-id="0138e-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="0138e-117">Quando o `MaxLength` parâmetro de atributo é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="0138e-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="0138e-118">Quando o argumento não é uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0138e-118">When the argument is not a string.</span></span>

- <span data-ttu-id="0138e-119">O atributo ValidateLength é definido pela classe [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .</span><span class="sxs-lookup"><span data-stu-id="0138e-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0138e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0138e-120">See Also</span></span>

[<span data-ttu-id="0138e-121">System. Management. Automation. Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="0138e-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

<span data-ttu-id="0138e-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="0138e-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
