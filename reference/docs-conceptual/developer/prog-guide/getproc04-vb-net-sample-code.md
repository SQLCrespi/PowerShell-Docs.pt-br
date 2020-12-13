---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc04 (VB.NET)
description: Código de exemplo GetProc04 (VB.NET)
ms.openlocfilehash: c46a374ab9d77f343b5ac6f45be1711eaec6dd75
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659228"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="32653-103">Código de exemplo GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="32653-103">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="32653-104">O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="32653-104">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="32653-105">Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="32653-105">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="32653-106">Você pode baixar o arquivo de origem C# (getprov04.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="32653-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="32653-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="32653-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="32653-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="32653-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="32653-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="32653-109">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="32653-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32653-110">See Also</span></span>

[<span data-ttu-id="32653-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32653-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="32653-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32653-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
