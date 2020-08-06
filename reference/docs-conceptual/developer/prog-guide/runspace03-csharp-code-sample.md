---
title: Exemplo de código do RunSpace03 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: df34652f60ed85b13739a04485cf6622cf924872
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784785"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="4f502-102">Exemplo de código RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="4f502-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="4f502-103">Aqui está o código-fonte do C# para o aplicativo de console descrito em "criando um aplicativo de console que executa um script especificado".</span><span class="sxs-lookup"><span data-stu-id="4f502-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="4f502-104">Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar um script que recupera informações de processo usando a lista de nomes de processo passados para o script.</span><span class="sxs-lookup"><span data-stu-id="4f502-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="4f502-105">Ele mostra como passar objetos de entrada para um script e como recuperar objetos de erro, bem como os objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="4f502-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="4f502-106">Você pode baixar o arquivo de origem do C# (runspace03.cs) para este exemplo usando os componentes de tempo de execução do Microsoft Windows Software Development Kit para Windows Vista e Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f502-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="4f502-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="4f502-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="4f502-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="4f502-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="4f502-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="4f502-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="4f502-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f502-110">See Also</span></span>

[<span data-ttu-id="4f502-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f502-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="4f502-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f502-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
