---
title: Declaração de atributo OutputType | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365335"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="6bdd3-102">Declaração de atributo OutputType</span><span class="sxs-lookup"><span data-stu-id="6bdd3-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="6bdd3-103">O atributo `OutputType` identifica os tipos de .NET Framework retornados por um cmdlet, uma função ou um script.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="6bdd3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6bdd3-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="6bdd3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6bdd3-105">Parameters</span></span>

<span data-ttu-id="6bdd3-106">Digite (`string[]` ou `Type[]`) necessário.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="6bdd3-107">Especifica os tipos retornados pela função de cmdlet ou script.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="6bdd3-108">ParameterSetName (String []) opcional.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="6bdd3-109">Especifica os conjuntos de parâmetros que retornam os tipos especificados no parâmetro `type`.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="6bdd3-110">providerCmdlet opcional.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-110">providerCmdlet Optional.</span></span> <span data-ttu-id="6bdd3-111">Especifica o cmdlet do provedor que retorna os tipos especificados no parâmetro `type`.</span><span class="sxs-lookup"><span data-stu-id="6bdd3-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bdd3-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6bdd3-112">See Also</span></span>

<span data-ttu-id="6bdd3-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="6bdd3-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
