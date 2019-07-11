---
title: RunSpace03 (C#) exemplo de código | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: e1fc91174a959d6acc306330afb8d5c2e7a9a860
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734996"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="a2c55-102">Exemplo de código RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="a2c55-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="a2c55-103">Aqui está o C# código-fonte do que o aplicativo de console descrito [criando um Console do aplicativo que é executado em um Script especificado](fd).</span><span class="sxs-lookup"><span data-stu-id="a2c55-103">Here is the C# source code for the console application described in [Creating a Console Application That Runs a Specified Script](fd).</span></span> <span data-ttu-id="a2c55-104">Este exemplo usa o [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) classe para executar um script que recupera informações de processo usando a lista de nomes de processos passado para o script.</span><span class="sxs-lookup"><span data-stu-id="a2c55-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="a2c55-105">Ele mostra como passar objetos de entrada para um script e como recuperar objetos de erro, bem como os objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="a2c55-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a2c55-106">Você pode baixar o C# arquivo de origem (runspace03.cs) para este exemplo usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="a2c55-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a2c55-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a2c55-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a2c55-108">Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.</span><span class="sxs-lookup"><span data-stu-id="a2c55-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a2c55-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="a2c55-109">Code Sample</span></span>

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a><span data-ttu-id="a2c55-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2c55-110">See Also</span></span>

[<span data-ttu-id="a2c55-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2c55-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a2c55-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2c55-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)