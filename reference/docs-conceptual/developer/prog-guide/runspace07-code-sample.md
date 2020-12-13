---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace07
description: Exemplo de código RunSpace07
ms.openlocfilehash: 6e8c9f48a6e9c5a642ecf93bca8a85003b3cfbf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647393"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="dec11-103">Exemplo de código RunSpace07</span><span class="sxs-lookup"><span data-stu-id="dec11-103">RunSpace07 Code Sample</span></span>

<span data-ttu-id="dec11-104">Aqui está o código-fonte para o exemplo de Runspace07 descrito em [criando um aplicativo de console que adiciona comandos a um pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span><span class="sxs-lookup"><span data-stu-id="dec11-104">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="dec11-105">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="dec11-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="dec11-106">Os comandos adicionados ao pipeline são os `Get-Process` `Measure-Object` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="dec11-106">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="dec11-107">Você pode baixar o arquivo de origem do C# (runspace07.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="dec11-107">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="dec11-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="dec11-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="dec11-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="dec11-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="dec11-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="dec11-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="dec11-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dec11-111">See Also</span></span>

[<span data-ttu-id="dec11-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dec11-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="dec11-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dec11-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
