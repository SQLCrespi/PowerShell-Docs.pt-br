---
title: Exemplo de código AccessDbProviderSample01 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2e9f81b3011ea1b27bafd9e02ea7e0faf7903a62
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784819"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="591dc-102">Exemplo de código AccessDbProviderSample01</span><span class="sxs-lookup"><span data-stu-id="591dc-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="591dc-103">O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="591dc-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="591dc-104">Essa implementação fornece métodos para iniciar e interromper o provedor e, embora não forneça um meio para acessar um armazenamento de dados ou para obter ou definir os dados no repositório de dados, ele fornece a funcionalidade básica exigida por todos os provedores.</span><span class="sxs-lookup"><span data-stu-id="591dc-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="591dc-105">Você pode baixar o arquivo de origem do C# (AccessDBSampleProvider01.cs) para esse provedor usando o kit de desenvolvimento de software do Windows para componentes de tempo de execução do Windows Vista e Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="591dc-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="591dc-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="591dc-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="591dc-107">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="591dc-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="591dc-108">Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="591dc-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="591dc-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="591dc-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="591dc-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="591dc-110">See Also</span></span>

[<span data-ttu-id="591dc-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="591dc-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="591dc-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="591dc-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
