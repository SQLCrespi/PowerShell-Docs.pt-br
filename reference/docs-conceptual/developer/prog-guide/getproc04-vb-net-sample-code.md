---
title: Código de exemplo do GetProc04 (VB.NET) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 63fbbb2d6bef4634bf72d4b0f9e429de9ed9deca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771865"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="c8aee-102">Código de exemplo GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="c8aee-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="c8aee-103">O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="c8aee-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="c8aee-104">Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="c8aee-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="c8aee-105">Você pode baixar o arquivo de origem do C# (getprov04.cs) para este cmdlet Get-proc usando o Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="c8aee-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c8aee-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="c8aee-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="c8aee-107">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="c8aee-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c8aee-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="c8aee-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="c8aee-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8aee-109">See Also</span></span>

[<span data-ttu-id="c8aee-110">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8aee-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c8aee-111">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8aee-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
