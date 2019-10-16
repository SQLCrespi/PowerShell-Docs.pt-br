---
title: Exemplo de código AccessDbProviderSample06 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baab6a56-c199-48d7-a03e-a904b1bb1baa
caps.latest.revision: 7
ms.openlocfilehash: 90927917550ade695f32c6f763f8cc4a8b347275
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366935"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="39679-102">Exemplo de código AccessDbProviderSample06</span><span class="sxs-lookup"><span data-stu-id="39679-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="39679-103">O código a seguir mostra a implementação do provedor de conteúdo do Windows PowerShell descrito em [criando um provedor de conteúdo do Windows PowerShell](./creating-a-windows-powershell-content-provider.md).</span><span class="sxs-lookup"><span data-stu-id="39679-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span> <span data-ttu-id="39679-104">Esse provedor permite que o usuário manipule o conteúdo dos itens em um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="39679-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="39679-105">Você pode baixar o C# arquivo de origem (AccessDBSampleProvider06.cs) para esse provedor usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="39679-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="39679-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="39679-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="39679-107">Os arquivos de origem baixados estão disponíveis no diretório de **exemplos do \<PowerShell >** .</span><span class="sxs-lookup"><span data-stu-id="39679-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="39679-108">Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="39679-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="39679-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="39679-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="39679-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39679-110">See Also</span></span>

[<span data-ttu-id="39679-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39679-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="39679-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39679-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
