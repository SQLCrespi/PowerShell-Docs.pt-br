---
ms.date: 09/12/2016
ms.topic: reference
title: Código de exemplo GetProc03 (VB.NET)
description: Código de exemplo GetProc03 (VB.NET)
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355554"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="12485-103">Código de exemplo GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="12485-103">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="12485-104">O código a seguir mostra a implementação de um `Get-Process` cmdlet que pode aceitar entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="12485-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="12485-105">Essa implementação define um `Name` parâmetro que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (sistema. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="12485-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="12485-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="12485-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
