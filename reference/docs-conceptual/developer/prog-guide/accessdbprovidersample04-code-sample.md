---
title: Exemplo de código AccessDbProviderSample04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9374c4a-e499-4516-9eb6-107c59df98d9
caps.latest.revision: 7
ms.openlocfilehash: ff43286bc90c1a4d2270be0ee03ca5910867cec2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366965"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="ef0ba-102">Exemplo de código AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="ef0ba-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="ef0ba-103">O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ef0ba-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span> <span data-ttu-id="ef0ba-104">Esse provedor funciona em armazenamentos de dados de várias camadas.</span><span class="sxs-lookup"><span data-stu-id="ef0ba-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="ef0ba-105">Para esse tipo de armazenamento de dados, o nível superior do repositório contém os itens raiz e cada nível subsequente é referido como um nó de itens filho.</span><span class="sxs-lookup"><span data-stu-id="ef0ba-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="ef0ba-106">Ao permitir que o usuário trabalhe nesses nós filho, um usuário pode interagir hierarquicamente por meio do armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ef0ba-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ef0ba-107">Exemplo de Código</span><span class="sxs-lookup"><span data-stu-id="ef0ba-107">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="ef0ba-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef0ba-108">See Also</span></span>

[<span data-ttu-id="ef0ba-109">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef0ba-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
