---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código AccessDbProviderSample02
description: Exemplo de código AccessDbProviderSample02
ms.openlocfilehash: f467ee59b36027e80852ae1f7b2f1af5c9aa8569
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659401"
---
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="e2b3d-103">Exemplo de código AccessDbProviderSample02</span><span class="sxs-lookup"><span data-stu-id="e2b3d-103">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="e2b3d-104">O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e2b3d-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>
<span data-ttu-id="e2b3d-105">Essa implementação cria um caminho, estabelece uma conexão com um banco de dados do Access e, em seguida, remove a unidade.</span><span class="sxs-lookup"><span data-stu-id="e2b3d-105">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b3d-106">Você pode baixar o arquivo de origem do C# (AccessDBSampleProvider02.cs) para este provedor usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="e2b3d-106">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e2b3d-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e2b3d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="e2b3d-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="e2b3d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="e2b3d-109">Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e2b3d-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="e2b3d-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="e2b3d-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="e2b3d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2b3d-111">See Also</span></span>

[<span data-ttu-id="e2b3d-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2b3d-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e2b3d-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2b3d-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
