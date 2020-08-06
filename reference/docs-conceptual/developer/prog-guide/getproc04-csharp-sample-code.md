---
title: Código de exemplo de GetProc04 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: dd3965ee504641b1b629ba203090ee14c670da43
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771882"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="ec4a0-102">Código de exemplo GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="ec4a0-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="ec4a0-103">O código a seguir mostra a implementação de um `Get-Process` cmdlet que relata erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="ec4a0-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="ec4a0-104">Essa implementação chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="ec4a0-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a0-105">Você pode baixar o arquivo de origem do C# (getprov04.cs) para este cmdlet Get-proc usando o Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="ec4a0-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="ec4a0-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="ec4a0-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="ec4a0-107">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="ec4a0-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ec4a0-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="ec4a0-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="ec4a0-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec4a0-109">See Also</span></span>

[<span data-ttu-id="ec4a0-110">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec4a0-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="ec4a0-111">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec4a0-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
