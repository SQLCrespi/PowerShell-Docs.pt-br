---
title: Exemplo de código RunSpace06 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8767ac8dc3a3d9253c2a53a4754d9bd54304abb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784717"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="80cba-102">Exemplo de código RunSpace06</span><span class="sxs-lookup"><span data-stu-id="80cba-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="80cba-103">Este é o código-fonte do exemplo Runspace06 descrito em [Configurando um runspace usando um snap-in do Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="80cba-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="80cba-104">Esse aplicativo de exemplo cria um runspace com base em um snap-in do Windows PowerShell, que é usado para executar um pipeline com um único comando.</span><span class="sxs-lookup"><span data-stu-id="80cba-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="80cba-105">Para fazer isso, o aplicativo cria as informações de configuração do runspace, cria um runspace, cria um pipeline com um único comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="80cba-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="80cba-106">Você pode baixar o arquivo de origem do C# (runspace06.cs) usando o kit de desenvolvimento de software do Windows para componentes de tempo de execução do Windows Vista e do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="80cba-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="80cba-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="80cba-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="80cba-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="80cba-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="80cba-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="80cba-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="80cba-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80cba-110">See Also</span></span>

[<span data-ttu-id="80cba-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80cba-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="80cba-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80cba-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
