---
title: Código deC#exemplo GetProc03 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc0d538-69ac-43d5-837d-b6f47344fc6a
caps.latest.revision: 5
ms.openlocfilehash: 126df3092c0722b0fc9d02cb61d3faf0578b8e97
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416135"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="91c7f-102">Código de exemplo GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="91c7f-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="91c7f-103">O código a seguir mostra a implementação de um cmdlet `Get-Process` que pode aceitar a entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="91c7f-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="91c7f-104">Essa implementação define um parâmetro `Name` que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="91c7f-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="91c7f-105">Você pode baixar o C# arquivo de origem (getprov03.cs) para este cmdlet Get-proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="91c7f-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="91c7f-106">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="91c7f-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="91c7f-107">Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.</span><span class="sxs-lookup"><span data-stu-id="91c7f-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="91c7f-108">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="91c7f-108">Code Sample</span></span>

[!code-csharp[GetProcessSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L11-L78 "GetProcessSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="91c7f-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="91c7f-109">See Also</span></span>

[<span data-ttu-id="91c7f-110">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91c7f-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="91c7f-111">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91c7f-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
