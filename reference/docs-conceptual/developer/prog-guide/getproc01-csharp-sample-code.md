---
title: Código deC#exemplo GetProc01 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 71ba68521ed8d26d0c85169d2b0d547cc6d2d5e3
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978416"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="b863d-102">Código de exemplo GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="b863d-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="b863d-103">O código a seguir mostra a implementação do cmdlet de exemplo GetProc01.</span><span class="sxs-lookup"><span data-stu-id="b863d-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="b863d-104">Observe que o cmdlet é simplificado deixando o trabalho real de recuperação do processo com o método [System. Diagnostics. Process. GetProcesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="b863d-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="b863d-105">Você pode baixar o C# arquivo de origem (getproc01.cs) para este cmdlet Get-proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="b863d-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b863d-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b863d-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b863d-107">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="b863d-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b863d-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="b863d-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="b863d-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b863d-109">See Also</span></span>

[<span data-ttu-id="b863d-110">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b863d-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b863d-111">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b863d-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
