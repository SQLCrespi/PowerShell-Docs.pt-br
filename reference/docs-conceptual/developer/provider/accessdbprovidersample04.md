---
title: AccessDBProviderSample04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: c0efd10680d3323b6c8d932604176c4425e7266a
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633355"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="81671-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="81671-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="81671-103">Este exemplo mostra como substituir métodos de contêiner para dar suporte a chamadas para os `Copy-Item` `Get-ChildItem` `New-Item` cmdlets,, e `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="81671-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="81671-104">Esses métodos devem ser implementados quando o armazenamento de dados contiver itens que são contêineres.</span><span class="sxs-lookup"><span data-stu-id="81671-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="81671-105">Um contêiner é um grupo de itens filho em um item pai comum.</span><span class="sxs-lookup"><span data-stu-id="81671-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="81671-106">A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="81671-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="81671-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="81671-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81671-108">Sua classe de provedor provavelmente será derivada do [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="81671-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="81671-109">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="81671-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="81671-110">Declarando o `CmdletProvider` atributo.</span><span class="sxs-lookup"><span data-stu-id="81671-110">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="81671-111">Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="81671-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>
- <span data-ttu-id="81671-112">Substituindo o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) para alterar o comportamento do `Copy-Item` cmdlet que permite ao usuário copiar itens de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="81671-112">Overwriting the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="81671-113">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Copy-Item` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="81671-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>
- <span data-ttu-id="81671-114">Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) para alterar o comportamento do cmdlet Get-ChildItems, que permite ao usuário recuperar os itens filho do item pai.</span><span class="sxs-lookup"><span data-stu-id="81671-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="81671-115">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet Get-ChildItems.)</span><span class="sxs-lookup"><span data-stu-id="81671-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>
- <span data-ttu-id="81671-116">Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) para alterar o comportamento do cmdlet Get-ChildItems quando o `Name` parâmetro do cmdlet é especificado.</span><span class="sxs-lookup"><span data-stu-id="81671-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>
- <span data-ttu-id="81671-117">Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) para alterar o comportamento do `New-Item` cmdlet, que permite ao usuário adicionar itens ao armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="81671-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="81671-118">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao `New-Item` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="81671-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>
- <span data-ttu-id="81671-119">Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) para alterar o comportamento do `Remove-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="81671-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="81671-120">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Remove-Item` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="81671-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="81671-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="81671-121">Example</span></span>

<span data-ttu-id="81671-122">Este exemplo mostra como substituir os métodos necessários para copiar, criar e remover itens, bem como métodos para obter os itens filho de um item pai.</span><span class="sxs-lookup"><span data-stu-id="81671-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="81671-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81671-123">See Also</span></span>

[<span data-ttu-id="81671-124">System. Management. Automation. Provider. createcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="81671-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="81671-125">System. Management. Automation. Provider. Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="81671-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="81671-126">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="81671-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="81671-127">Projetar seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81671-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
