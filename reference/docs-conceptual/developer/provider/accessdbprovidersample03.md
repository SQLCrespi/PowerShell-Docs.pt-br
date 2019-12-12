---
title: AccessDBProviderSample03 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: aa67bb605f90c1ea40323b4583766069ff1226fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359985"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="d1ca6-102">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="d1ca6-102">AccessDBProviderSample03</span></span>

<span data-ttu-id="d1ca6-103">Este exemplo mostra como substituir os métodos [System. Management. Automation. Provider. createcmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) e [System. Management. Automation. Provider. docmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para dar suporte a chamadas para os cmdlets `Get-Item` e `Set-Item`.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="d1ca6-104">A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d1ca6-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d1ca6-105">Demonstra</span><span class="sxs-lookup"><span data-stu-id="d1ca6-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1ca6-106">Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:</span><span class="sxs-lookup"><span data-stu-id="d1ca6-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="d1ca6-107">Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d1ca6-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> -   <span data-ttu-id="d1ca6-108">Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d1ca6-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="d1ca6-109">Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="d1ca6-109">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="d1ca6-110">Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d1ca6-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="d1ca6-111">Consulte [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="d1ca6-111">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="d1ca6-112">Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="d1ca6-112">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="d1ca6-113">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1ca6-113">This sample demonstrates the following:</span></span>

- <span data-ttu-id="d1ca6-114">Declarando o atributo `CmdletProvider`.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-114">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="d1ca6-115">Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. mycmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d1ca6-115">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

- <span data-ttu-id="d1ca6-116">Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) para alterar o comportamento do cmdlet `New-PSDrive`, permitindo que o usuário crie novas unidades.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-116">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span> <span data-ttu-id="d1ca6-117">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `New-PSDrive`.)</span><span class="sxs-lookup"><span data-stu-id="d1ca6-117">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="d1ca6-118">Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para dar suporte à remoção de unidades existentes.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

- <span data-ttu-id="d1ca6-119">Substituindo o método [System. Management. Automation. Provider. docmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) para alterar o comportamento do cmdlet `Get-Item`, permitindo que o usuário recupere itens do armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-119">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="d1ca6-120">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Get-Item`.)</span><span class="sxs-lookup"><span data-stu-id="d1ca6-120">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="d1ca6-121">Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para alterar o comportamento do cmdlet `Set-Item`, permitindo que o usuário atualize os itens no repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-121">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="d1ca6-122">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Get-Item`.)</span><span class="sxs-lookup"><span data-stu-id="d1ca6-122">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="d1ca6-123">Substituindo o método [System. Management. Automation. Provider. docmdletprovider. myexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) para alterar o comportamento do cmdlet `Test-Path`.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-123">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="d1ca6-124">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Test-Path`.)</span><span class="sxs-lookup"><span data-stu-id="d1ca6-124">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>

- <span data-ttu-id="d1ca6-125">Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) para determinar se o caminho fornecido é válido.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-125">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="d1ca6-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d1ca6-126">Example</span></span>

<span data-ttu-id="d1ca6-127">Este exemplo mostra como substituir os métodos necessários para obter e definir itens em um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="d1ca6-127">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="d1ca6-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1ca6-128">See Also</span></span>

[<span data-ttu-id="d1ca6-129">System. Management. Automation. Provider. createcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="d1ca6-129">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="d1ca6-130">System. Management. Automation. Provider. Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="d1ca6-130">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="d1ca6-131">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="d1ca6-131">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="d1ca6-132">Criando seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1ca6-132">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
