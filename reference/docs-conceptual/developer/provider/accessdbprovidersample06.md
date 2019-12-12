---
title: AccessDBProviderSample06 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: 9c00ec6de987729fec42dc57245a949d11e31f4b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366325"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="760af-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="760af-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="760af-103">Este exemplo mostra como substituir os métodos de conteúdo para dar suporte a chamadas para os cmdlets `Clear-Content`, `Get-Content`e `Set-Content`.</span><span class="sxs-lookup"><span data-stu-id="760af-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="760af-104">Esses métodos devem ser implementados quando o usuário precisa gerenciar o conteúdo dos itens no armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="760af-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="760af-105">A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) e implementa a interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="760af-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="760af-106">Demonstra</span><span class="sxs-lookup"><span data-stu-id="760af-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="760af-107">Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:</span><span class="sxs-lookup"><span data-stu-id="760af-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="760af-108">Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="760af-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="760af-109">Consulte [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="760af-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="760af-110">Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="760af-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="760af-111">Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="760af-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="760af-112">Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="760af-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="760af-113">Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="760af-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="760af-114">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="760af-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="760af-115">Declarando o atributo `CmdletProvider`.</span><span class="sxs-lookup"><span data-stu-id="760af-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="760af-116">Definir uma classe de provedor que deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) e que declara a interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="760af-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="760af-117">Substituindo o método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) para alterar o comportamento do cmdlet `Clear-Content`, permitindo que o usuário remova o conteúdo de um item.</span><span class="sxs-lookup"><span data-stu-id="760af-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="760af-118">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Clear-Content`.)</span><span class="sxs-lookup"><span data-stu-id="760af-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="760af-119">Substituindo o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) para alterar o comportamento do cmdlet `Get-Content`, permitindo que o usuário recupere o conteúdo de um item.</span><span class="sxs-lookup"><span data-stu-id="760af-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="760af-120">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Get-Content`.).</span><span class="sxs-lookup"><span data-stu-id="760af-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="760af-121">Substituindo o método [Microsoft. PowerShell. Commands. FileSystemProvider. Getcontentwriter \*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) para alterar o comportamento do cmdlet `Set-Content`, permitindo que o usuário atualize o conteúdo de um item.</span><span class="sxs-lookup"><span data-stu-id="760af-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="760af-122">(Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Set-Content`.)</span><span class="sxs-lookup"><span data-stu-id="760af-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="760af-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="760af-123">Example</span></span>

<span data-ttu-id="760af-124">Este exemplo mostra como substituir os métodos necessários para limpar, obter e definir o conteúdo de itens em um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="760af-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="760af-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="760af-125">See Also</span></span>

[<span data-ttu-id="760af-126">System. Management. Automation. Provider. createcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="760af-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="760af-127">System. Management. Automation. Provider. Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="760af-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="760af-128">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="760af-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="760af-129">Criando seu provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="760af-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
