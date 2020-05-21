---
title: AccessDBProviderSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: 67c2b6cfd36a805fce25bf0c7c55db56ec14092c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83690914"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="5bc33-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="5bc33-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="5bc33-103">Este exemplo mostra como declarar uma classe de provedor que deriva diretamente da classe [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="5bc33-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="5bc33-104">Ele é incluído aqui apenas para fins de integridade.</span><span class="sxs-lookup"><span data-stu-id="5bc33-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5bc33-105">Demonstra</span><span class="sxs-lookup"><span data-stu-id="5bc33-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bc33-106">Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:</span><span class="sxs-lookup"><span data-stu-id="5bc33-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="5bc33-107">Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="5bc33-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="5bc33-108">Consulte [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="5bc33-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="5bc33-109">Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="5bc33-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="5bc33-110">Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="5bc33-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="5bc33-111">Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="5bc33-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="5bc33-112">Consulte [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="5bc33-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="5bc33-113">Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="5bc33-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="5bc33-114">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5bc33-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="5bc33-115">Declarando o `CmdletProvider` atributo.</span><span class="sxs-lookup"><span data-stu-id="5bc33-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="5bc33-116">Definição de uma classe de provedor que deriva diretamente da classe [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="5bc33-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="5bc33-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5bc33-117">Example</span></span>

<span data-ttu-id="5bc33-118">Este exemplo mostra como definir uma classe de provedor e como declarar o `CmdletProvider` atributo.</span><span class="sxs-lookup"><span data-stu-id="5bc33-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a><span data-ttu-id="5bc33-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5bc33-119">See Also</span></span>

[<span data-ttu-id="5bc33-120">System. Management. Automation. Provider. createcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="5bc33-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="5bc33-121">System. Management. Automation. Provider. Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="5bc33-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="5bc33-122">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="5bc33-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="5bc33-123">Projetar seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bc33-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
