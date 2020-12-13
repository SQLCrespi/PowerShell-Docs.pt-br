---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample05
description: AccessDBProviderSample05
ms.openlocfilehash: ad273720ded0b200530f4f81482d01a8fbb82aa3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92656910"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="907b7-103">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="907b7-103">AccessDBProviderSample05</span></span>

<span data-ttu-id="907b7-104">Este exemplo mostra como substituir métodos de contêiner para dar suporte a chamadas para os `Move-Item` `Join-Path` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="907b7-104">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="907b7-105">Esses métodos deverão ser implementados quando o usuário precisar mover itens dentro de um contêiner e se o armazenamento de dados contiver contêineres aninhados.</span><span class="sxs-lookup"><span data-stu-id="907b7-105">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="907b7-106">A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="907b7-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="907b7-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="907b7-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="907b7-108">Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:</span><span class="sxs-lookup"><span data-stu-id="907b7-108">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="907b7-109">Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="907b7-109">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="907b7-110">Consulte [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="907b7-110">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="907b7-111">Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="907b7-111">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="907b7-112">Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="907b7-112">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="907b7-113">Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="907b7-113">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="907b7-114">Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="907b7-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="907b7-115">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="907b7-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="907b7-116">Declarando o `CmdletProvider` atributo.</span><span class="sxs-lookup"><span data-stu-id="907b7-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="907b7-117">Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="907b7-117">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="907b7-118">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) para alterar o comportamento do `Move-Item` cmdlet, permitindo que o usuário mova itens de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="907b7-118">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="907b7-119">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Move-Item` cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="907b7-119">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="907b7-120">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) para alterar o comportamento do `Join-Path` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="907b7-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="907b7-121">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. IsItemContainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) .</span><span class="sxs-lookup"><span data-stu-id="907b7-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="907b7-122">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) .</span><span class="sxs-lookup"><span data-stu-id="907b7-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="907b7-123">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. GetParentPath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) .</span><span class="sxs-lookup"><span data-stu-id="907b7-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="907b7-124">Substituindo o método [System. Management. Automation. Provider. Navigationcmdletprovider. Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) .</span><span class="sxs-lookup"><span data-stu-id="907b7-124">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="907b7-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="907b7-125">Example</span></span>

<span data-ttu-id="907b7-126">Este exemplo mostra como substituir os métodos necessários para mover itens em um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="907b7-126">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="907b7-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="907b7-127">See Also</span></span>

[<span data-ttu-id="907b7-128">System. Management. Automation. Provider. createcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="907b7-128">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="907b7-129">System. Management. Automation. Provider. Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="907b7-129">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="907b7-130">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="907b7-130">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="907b7-131">Projetar seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="907b7-131">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
