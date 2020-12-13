---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo de alias
description: Declaração de atributo de alias
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668296"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="651a4-103">Declaração de atributo de alias</span><span class="sxs-lookup"><span data-stu-id="651a4-103">Alias Attribute Declaration</span></span>

<span data-ttu-id="651a4-104">O atributo alias permite que o usuário especifique nomes diferentes para um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="651a4-104">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="651a4-105">Os aliases podem ser usados para fornecer atalhos para um nome de parâmetro ou podem fornecer nomes diferentes que são apropriados para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="651a4-105">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="651a4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="651a4-106">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="651a4-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="651a4-107">Parameters</span></span>

<span data-ttu-id="651a4-108">`aliasName` (Cadeia de caracteres []) Necessário.</span><span class="sxs-lookup"><span data-stu-id="651a4-108">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="651a4-109">Especifica um conjunto de nomes de alias separados por vírgula para o parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="651a4-109">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="651a4-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="651a4-110">Remarks</span></span>

- <span data-ttu-id="651a4-111">O atributo alias é usado com o atributo Parameter quando você especifica um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="651a4-111">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="651a4-112">Para obter mais informações sobre como declarar esses atributos, consulte [como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="651a4-112">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="651a4-113">Cada nome de alias deve ser exclusivo dentro de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="651a4-113">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="651a4-114">O Windows PowerShell não verifica nomes de alias duplicados.</span><span class="sxs-lookup"><span data-stu-id="651a4-114">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="651a4-115">O atributo alias é usado uma vez para cada parâmetro em um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="651a4-115">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="651a4-116">O atributo alias é definido pela classe [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) .</span><span class="sxs-lookup"><span data-stu-id="651a4-116">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="651a4-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="651a4-117">See Also</span></span>

[<span data-ttu-id="651a4-118">Aliases de parâmetro</span><span class="sxs-lookup"><span data-stu-id="651a4-118">Parameter Aliases</span></span>](./parameter-aliases.md)

<span data-ttu-id="651a4-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="651a4-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
