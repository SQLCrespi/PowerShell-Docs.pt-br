---
title: Código deC#exemplo GetProc04 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 439ba3f3-91b1-46a4-8d07-9af6edb71bc4
caps.latest.revision: 5
ms.openlocfilehash: d17a67019b7451f2da5595b3258457a01cc86b0b
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978348"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="d30e3-102">Código de exemplo GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="d30e3-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="d30e3-103">O código a seguir mostra a implementação de um cmdlet `Get-Process` que relata erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="d30e3-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="d30e3-104">Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="d30e3-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="d30e3-105">Você pode baixar o C# arquivo de origem (getprov04.cs) para este cmdlet Get-proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="d30e3-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d30e3-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d30e3-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d30e3-107">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="d30e3-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d30e3-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="d30e3-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="d30e3-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d30e3-109">See Also</span></span>

[<span data-ttu-id="d30e3-110">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d30e3-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d30e3-111">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d30e3-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
