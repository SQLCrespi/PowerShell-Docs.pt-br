---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc04 (C#)
description: Código de exemplo GetProc04 (C#)
ms.openlocfilehash: 80020b60a7ab34caec0c856b9b7d12021f4276b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654375"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="3a73b-103">Código de exemplo GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a73b-103">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="3a73b-104">O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="3a73b-104">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="3a73b-105">Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="3a73b-105">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3a73b-106">Você pode baixar o arquivo de origem C# (getprov04.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="3a73b-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3a73b-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="3a73b-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3a73b-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="3a73b-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3a73b-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="3a73b-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="3a73b-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a73b-110">See Also</span></span>

[<span data-ttu-id="3a73b-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a73b-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3a73b-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a73b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
