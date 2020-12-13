---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc01 (C#)
description: Código de exemplo GetProc01 (C#)
ms.openlocfilehash: 79509ff12afb32c907058f4ddb0c707f3823857a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654488"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="e728f-103">Código de exemplo GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="e728f-103">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="e728f-104">O código a seguir mostra a implementação do cmdlet de exemplo GetProc01.</span><span class="sxs-lookup"><span data-stu-id="e728f-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="e728f-105">Observe que o cmdlet é simplificado deixando o trabalho real de recuperação do processo com o método [System. Diagnostics. Process. GetProcesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="e728f-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="e728f-106">Você pode baixar o arquivo de origem C# (getproc01.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="e728f-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e728f-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e728f-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="e728f-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="e728f-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e728f-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="e728f-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="e728f-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e728f-110">See Also</span></span>

[<span data-ttu-id="e728f-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e728f-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e728f-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e728f-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
