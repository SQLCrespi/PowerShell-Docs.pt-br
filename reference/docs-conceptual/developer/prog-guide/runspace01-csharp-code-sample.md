---
title: Exemplo de código do Runspace01 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787046"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="67c28-102">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="67c28-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="67c28-103">Aqui estão os exemplos de código para o runspace descrito em [criando um aplicativo de console que executa um comando especificado](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="67c28-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="67c28-104">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="67c28-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="67c28-105">(Observe que esse aplicativo não especifica informações de configuração de runspace, nem cria explicitamente um pipeline).</span><span class="sxs-lookup"><span data-stu-id="67c28-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="67c28-106">O comando que é invocado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67c28-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="67c28-107">Você pode baixar o arquivo de origem do C# (runspace01.cs) para este runspace usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="67c28-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="67c28-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="67c28-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="67c28-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="67c28-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="67c28-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="67c28-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="67c28-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67c28-111">See Also</span></span>

[<span data-ttu-id="67c28-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67c28-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="67c28-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67c28-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
