---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código Runspace01 (C#)
description: Exemplo de código Runspace01 (C#)
ms.openlocfilehash: e6121c144e1a4c1a1d9460d01119f44ee5835821
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657151"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="34fbc-103">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="34fbc-103">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="34fbc-104">Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="34fbc-104">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="34fbc-105">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="34fbc-105">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="34fbc-106">(Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline).</span><span class="sxs-lookup"><span data-stu-id="34fbc-106">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="34fbc-107">O comando que é invocado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="34fbc-107">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="34fbc-108">Você pode baixar o arquivo de origem do C# (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="34fbc-108">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="34fbc-109">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="34fbc-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="34fbc-110">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="34fbc-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="34fbc-111">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="34fbc-111">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="34fbc-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34fbc-112">See Also</span></span>

[<span data-ttu-id="34fbc-113">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34fbc-113">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="34fbc-114">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34fbc-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
