---
title: Exemplo de código RunSpace07 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784700"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="5ace8-102">Exemplo de código RunSpace07</span><span class="sxs-lookup"><span data-stu-id="5ace8-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="5ace8-103">Aqui está o código-fonte para o exemplo de Runspace07 descrito em [criando um aplicativo de console que adiciona comandos a um pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span><span class="sxs-lookup"><span data-stu-id="5ace8-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="5ace8-104">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="5ace8-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="5ace8-105">Os comandos adicionados ao pipeline são os `Get-Process` `Measure-Object` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="5ace8-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="5ace8-106">Você pode baixar o arquivo de origem do C# (runspace07.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="5ace8-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="5ace8-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="5ace8-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="5ace8-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="5ace8-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5ace8-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="5ace8-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="5ace8-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ace8-110">See Also</span></span>

[<span data-ttu-id="5ace8-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ace8-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5ace8-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ace8-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
