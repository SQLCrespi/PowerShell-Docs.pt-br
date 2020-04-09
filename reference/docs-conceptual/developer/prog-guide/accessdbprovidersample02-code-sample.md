---
title: Exemplo de código AccessDbProviderSample02 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b89a4903-3efc-4b08-9b20-2baadf1d1b66
caps.latest.revision: 6
ms.openlocfilehash: 32abcfafb207ada23667cc6f0f03d382c6868ccb
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978593"
---
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="13f3b-102">Exemplo de código AccessDbProviderSample02</span><span class="sxs-lookup"><span data-stu-id="13f3b-102">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="13f3b-103">O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).</span><span class="sxs-lookup"><span data-stu-id="13f3b-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>
<span data-ttu-id="13f3b-104">Essa implementação cria um caminho, estabelece uma conexão com um banco de dados do Access e, em seguida, remove a unidade.</span><span class="sxs-lookup"><span data-stu-id="13f3b-104">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="13f3b-105">Você pode baixar o C# arquivo de origem (AccessDBSampleProvider02.cs) para este provedor usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="13f3b-105">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="13f3b-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="13f3b-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="13f3b-107">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="13f3b-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="13f3b-108">Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="13f3b-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="13f3b-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="13f3b-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="13f3b-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13f3b-110">See Also</span></span>

[<span data-ttu-id="13f3b-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13f3b-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="13f3b-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13f3b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
