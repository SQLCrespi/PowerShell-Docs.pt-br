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
ms.openlocfilehash: 607113ed566fc1e08e5b1d7092c83da2a22366ca
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74418009"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="a81d0-102">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="a81d0-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="a81d0-103">Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="a81d0-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="a81d0-104">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="a81d0-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="a81d0-105">(Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline).</span><span class="sxs-lookup"><span data-stu-id="a81d0-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="a81d0-106">O comando que é invocado é o cmdlet `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="a81d0-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a81d0-107">Você pode baixar o C# arquivo de origem (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="a81d0-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a81d0-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a81d0-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a81d0-109">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="a81d0-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a81d0-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="a81d0-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="a81d0-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a81d0-111">See Also</span></span>

[<span data-ttu-id="a81d0-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a81d0-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a81d0-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a81d0-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
