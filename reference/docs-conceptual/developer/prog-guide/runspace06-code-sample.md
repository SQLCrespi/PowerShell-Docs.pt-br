---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace06
description: Exemplo de código RunSpace06
ms.openlocfilehash: 627fa2be51721dd8bfdd63fabdd2e6f286d593be
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667463"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="fe3f2-103">Exemplo de código RunSpace06</span><span class="sxs-lookup"><span data-stu-id="fe3f2-103">RunSpace06 Code Sample</span></span>

<span data-ttu-id="fe3f2-104">Este é o código-fonte do exemplo Runspace06 descrito em [Configurando um runspace usando um snap-in do Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="fe3f2-104">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="fe3f2-105">Esse aplicativo de exemplo cria um runspace com base em um snap-in do Windows PowerShell, que é usado para executar um pipeline com um único comando.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-105">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="fe3f2-106">Para fazer isso, o aplicativo cria as informações de configuração do runspace, cria um runspace, cria um pipeline com um único comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-106">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="fe3f2-107">Você pode baixar o arquivo de origem do C# (runspace06.cs) usando o kit de desenvolvimento de software do Windows para componentes de tempo de execução do Windows Vista e do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-107">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="fe3f2-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="fe3f2-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="fe3f2-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="fe3f2-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="fe3f2-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="fe3f2-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe3f2-111">See Also</span></span>

[<span data-ttu-id="fe3f2-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe3f2-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="fe3f2-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe3f2-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
