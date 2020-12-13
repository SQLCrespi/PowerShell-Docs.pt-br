---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace03 (C#)
description: Exemplo de código RunSpace03 (C#)
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653837"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="67fc4-103">Exemplo de código RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="67fc4-103">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="67fc4-104">Aqui está o código-fonte do C# para o aplicativo de console descrito em "criando um aplicativo de console que executa um script especificado".</span><span class="sxs-lookup"><span data-stu-id="67fc4-104">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="67fc4-105">Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar um script que recupera informações de processo usando a lista de nomes de processo passados para o script.</span><span class="sxs-lookup"><span data-stu-id="67fc4-105">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="67fc4-106">Ele mostra como passar objetos de entrada para um script e como recuperar objetos de erro, bem como os objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="67fc4-106">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="67fc4-107">Você pode baixar o arquivo de origem do C# (runspace03.cs) para este exemplo usando os componentes de tempo de execução do Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="67fc4-107">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="67fc4-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="67fc4-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="67fc4-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="67fc4-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="67fc4-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="67fc4-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="67fc4-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67fc4-111">See Also</span></span>

[<span data-ttu-id="67fc4-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc4-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="67fc4-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc4-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
