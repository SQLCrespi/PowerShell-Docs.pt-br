---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc03 (C#)
description: Código de exemplo GetProc03 (C#)
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355571"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="bf97c-103">Código de exemplo GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="bf97c-103">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="bf97c-104">O código a seguir mostra a implementação de um `Get-Process` cmdlet que pode aceitar entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="bf97c-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="bf97c-105">Essa implementação define um `Name` parâmetro que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (sistema. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="bf97c-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="bf97c-106">Você pode baixar o arquivo de origem C# (getprov03.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="bf97c-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="bf97c-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="bf97c-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="bf97c-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="bf97c-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="bf97c-109">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="bf97c-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="bf97c-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf97c-110">See Also</span></span>

[<span data-ttu-id="bf97c-111">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf97c-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="bf97c-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf97c-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
