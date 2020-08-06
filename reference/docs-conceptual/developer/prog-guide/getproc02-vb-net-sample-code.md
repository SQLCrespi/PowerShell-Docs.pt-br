---
title: Código de exemplo do GetProc02 (VB.NET) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 98261f2d6678e24bb8e8df6d2c8a405b25203364
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787165"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="9695d-102">Código de exemplo GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="9695d-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="9695d-103">O código a seguir mostra a implementação de um `Get-Process` cmdlet que aceita a entrada de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9695d-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="9695d-104">Observe que essa implementação define um `Name` parâmetro para permitir a entrada da linha de comando e usa o método [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="9695d-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9695d-105">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="9695d-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="9695d-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9695d-106">See Also</span></span>

[<span data-ttu-id="9695d-107">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9695d-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
