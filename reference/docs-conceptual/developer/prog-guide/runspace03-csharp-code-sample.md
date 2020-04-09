---
title: Exemplo deC#código RunSpace03 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 28cef037f56f2a101f631d3a234974a8868b4ef9
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978314"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="b4f23-102">Exemplo de código RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="b4f23-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="b4f23-103">Este é o C# código-fonte do aplicativo de console descrito em "criando um aplicativo de console que executa um script especificado".</span><span class="sxs-lookup"><span data-stu-id="b4f23-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="b4f23-104">Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar um script que recupera informações de processo usando a lista de nomes de processo passados para o script.</span><span class="sxs-lookup"><span data-stu-id="b4f23-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="b4f23-105">Ele mostra como passar objetos de entrada para um script e como recuperar objetos de erro, bem como os objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="b4f23-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="b4f23-106">Você pode baixar o C# arquivo de origem (runspace03.cs) para este exemplo usando os componentes de tempo de execução do Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="b4f23-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b4f23-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b4f23-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b4f23-108">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="b4f23-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b4f23-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="b4f23-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="b4f23-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4f23-110">See Also</span></span>

[<span data-ttu-id="b4f23-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f23-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b4f23-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f23-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
