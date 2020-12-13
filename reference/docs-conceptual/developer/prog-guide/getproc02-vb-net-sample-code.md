---
ms.date: 09/13/2016
ms.topic: reference
title: Código de exemplo GetProc02 (VB.NET)
description: Código de exemplo GetProc02 (VB.NET)
ms.openlocfilehash: aefc3a4df5e0f29120916648ecdca41931a4c1c6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354534"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="23b9e-103">Código de exemplo GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="23b9e-103">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="23b9e-104">O código a seguir mostra a implementação de um `Get-Process` cmdlet que aceita a entrada de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="23b9e-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="23b9e-105">Observe que essa implementação define um `Name` parâmetro para permitir a entrada da linha de comando e usa o método [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="23b9e-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="23b9e-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="23b9e-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="23b9e-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23b9e-107">See Also</span></span>

[<span data-ttu-id="23b9e-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23b9e-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
