---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo OutputType
description: Declaração de atributo OutputType
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646458"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="2d3a6-103">Declaração de atributo OutputType</span><span class="sxs-lookup"><span data-stu-id="2d3a6-103">OutputType Attribute Declaration</span></span>

<span data-ttu-id="2d3a6-104">O `OutputType` atributo identifica os tipos de .NET Framework retornados por um cmdlet, uma função ou um script.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-104">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d3a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2d3a6-105">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="2d3a6-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2d3a6-106">Parameters</span></span>

<span data-ttu-id="2d3a6-107">Digite ( `string[]` ou `Type[]` ) obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-107">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="2d3a6-108">Especifica os tipos retornados pela função de cmdlet ou script.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-108">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="2d3a6-109">ParameterSetName (String []) opcional.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-109">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="2d3a6-110">Especifica os conjuntos de parâmetros que retornam os tipos especificados no `type` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-110">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="2d3a6-111">providerCmdlet opcional.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-111">providerCmdlet Optional.</span></span> <span data-ttu-id="2d3a6-112">Especifica o cmdlet do provedor que retorna os tipos especificados no `type` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2d3a6-112">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d3a6-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d3a6-113">See Also</span></span>

[<span data-ttu-id="2d3a6-114">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d3a6-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
