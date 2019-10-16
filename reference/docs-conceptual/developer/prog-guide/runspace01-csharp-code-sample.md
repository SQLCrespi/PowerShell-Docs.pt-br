---
title: Exemplo deC#código Runspace01 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 39e7d49b51942da51a581ab33dbe46ab848ca1c3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366635"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="6339c-102">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="6339c-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="6339c-103">Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="6339c-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="6339c-104">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="6339c-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="6339c-105">(Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline).</span><span class="sxs-lookup"><span data-stu-id="6339c-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="6339c-106">O comando que é invocado é o cmdlet `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="6339c-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6339c-107">Você pode baixar o C# arquivo de origem (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="6339c-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="6339c-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="6339c-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="6339c-109">Os arquivos de origem baixados estão disponíveis no diretório de **exemplos do \<PowerShell >** .</span><span class="sxs-lookup"><span data-stu-id="6339c-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="6339c-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="6339c-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="6339c-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6339c-111">See Also</span></span>

[<span data-ttu-id="6339c-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6339c-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="6339c-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6339c-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
