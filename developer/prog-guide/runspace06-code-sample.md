---
title: Exemplo de código RunSpace06 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: b6fdad90f7339e941d77646936b1b5952cd65500
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734938"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="28a34-102">Exemplo de código RunSpace06</span><span class="sxs-lookup"><span data-stu-id="28a34-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="28a34-103">Aqui está o código-fonte para o exemplo Runspace06 descrito [Configurando um Runspace usando um Snap-in do PowerShell do Windows](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="28a34-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span> <span data-ttu-id="28a34-104">Este aplicativo de exemplo cria um espaço de execução com base em um snap-in do Windows PowerShell, que é usado para executar um pipeline com um único comando.</span><span class="sxs-lookup"><span data-stu-id="28a34-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="28a34-105">Para fazer isso, o aplicativo cria as informações de configuração do espaço de execução, cria um espaço de execução, cria um pipeline com um único comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="28a34-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="28a34-106">Você pode baixar o C# arquivo de origem (runspace06.cs) usando o Windows Software Development Kit do Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="28a34-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="28a34-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="28a34-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="28a34-108">Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.</span><span class="sxs-lookup"><span data-stu-id="28a34-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="28a34-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="28a34-109">Code Sample</span></span>

[!code-csharp[Runspace06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a><span data-ttu-id="28a34-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28a34-110">See Also</span></span>

[<span data-ttu-id="28a34-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28a34-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="28a34-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28a34-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)