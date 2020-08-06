---
title: Declaração de atributo OutputType | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786536"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="11da9-102">Declaração de atributo OutputType</span><span class="sxs-lookup"><span data-stu-id="11da9-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="11da9-103">O `OutputType` atributo identifica os tipos de .NET Framework retornados por um cmdlet, uma função ou um script.</span><span class="sxs-lookup"><span data-stu-id="11da9-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="11da9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11da9-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="11da9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="11da9-105">Parameters</span></span>

<span data-ttu-id="11da9-106">Digite ( `string[]` ou `Type[]` ) obrigatório.</span><span class="sxs-lookup"><span data-stu-id="11da9-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="11da9-107">Especifica os tipos retornados pela função de cmdlet ou script.</span><span class="sxs-lookup"><span data-stu-id="11da9-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="11da9-108">ParameterSetName (String []) opcional.</span><span class="sxs-lookup"><span data-stu-id="11da9-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="11da9-109">Especifica os conjuntos de parâmetros que retornam os tipos especificados no `type` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="11da9-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="11da9-110">providerCmdlet opcional.</span><span class="sxs-lookup"><span data-stu-id="11da9-110">providerCmdlet Optional.</span></span> <span data-ttu-id="11da9-111">Especifica o cmdlet do provedor que retorna os tipos especificados no `type` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="11da9-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="11da9-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11da9-112">See Also</span></span>

[<span data-ttu-id="11da9-113">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11da9-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
