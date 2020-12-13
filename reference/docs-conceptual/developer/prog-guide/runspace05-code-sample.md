---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace05
description: Exemplo de código RunSpace05
ms.openlocfilehash: f128e09522bdb05cba2c160bce4944c829a5c108
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654212"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="d4462-103">Exemplo de código RunSpace05</span><span class="sxs-lookup"><span data-stu-id="d4462-103">RunSpace05 Code Sample</span></span>

<span data-ttu-id="d4462-104">Este é o código-fonte do exemplo Runspace05 descrito em [Configurando um runspace usando RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span><span class="sxs-lookup"><span data-stu-id="d4462-104">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="d4462-105">Este exemplo mostra como criar as informações de configuração do runspace, criar um runspace, criar um pipeline com um único comando e, em seguida, executar o pipeline.</span><span class="sxs-lookup"><span data-stu-id="d4462-105">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="d4462-106">O comando executado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4462-106">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d4462-107">Você pode baixar o arquivo de origem do C# (runspace05.cs) usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="d4462-107">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d4462-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d4462-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d4462-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="d4462-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d4462-110">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="d4462-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="d4462-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4462-111">See Also</span></span>

[<span data-ttu-id="d4462-112">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4462-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d4462-113">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4462-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
