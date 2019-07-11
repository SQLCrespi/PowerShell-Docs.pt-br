---
title: Exemplo de código RunSpace07 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: 232b282e366c9fad167686337696ef2ccd8b30d8
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734949"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="e0d1b-102">Exemplo de código RunSpace07</span><span class="sxs-lookup"><span data-stu-id="e0d1b-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="e0d1b-103">Aqui está o código-fonte para o exemplo Runspace07 descrito [criando um aplicativo que adiciona comandos do Console a um Pipeline](https://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).</span><span class="sxs-lookup"><span data-stu-id="e0d1b-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span> <span data-ttu-id="e0d1b-104">Este aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos para o pipeline e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="e0d1b-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="e0d1b-105">Os comandos adicionados ao pipeline são as `Get-Process` e `Measure-Object` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e0d1b-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="e0d1b-106">Você pode baixar o C# arquivo de origem (runspace07.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="e0d1b-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e0d1b-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e0d1b-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="e0d1b-108">Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.</span><span class="sxs-lookup"><span data-stu-id="e0d1b-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e0d1b-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="e0d1b-109">Code Sample</span></span>

[!code-csharp[Runspace07.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a><span data-ttu-id="e0d1b-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0d1b-110">See Also</span></span>

[<span data-ttu-id="e0d1b-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0d1b-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e0d1b-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0d1b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)