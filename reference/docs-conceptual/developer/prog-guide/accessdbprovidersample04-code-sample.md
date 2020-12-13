---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código AccessDbProviderSample04
description: Exemplo de código AccessDbProviderSample04
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647567"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="5ef0f-103">Exemplo de código AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="5ef0f-103">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="5ef0f-104">O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5ef0f-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="5ef0f-105">Esse provedor funciona em armazenamentos de dados de várias camadas.</span><span class="sxs-lookup"><span data-stu-id="5ef0f-105">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="5ef0f-106">Para esse tipo de armazenamento de dados, o nível superior do repositório contém os itens raiz e cada nível subsequente é referido como um nó de itens filho.</span><span class="sxs-lookup"><span data-stu-id="5ef0f-106">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="5ef0f-107">Ao permitir que o usuário trabalhe nesses nós filho, um usuário pode interagir hierarquicamente por meio do armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="5ef0f-107">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5ef0f-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="5ef0f-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="5ef0f-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ef0f-109">See Also</span></span>

[<span data-ttu-id="5ef0f-110">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ef0f-110">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
