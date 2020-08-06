---
title: Código de exemplo do GetProc03 (VB.NET) | Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: ad8a7b13d30b77acdaa2f5365b9b2da02aaeedce
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771916"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="821d1-102">Código de exemplo GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="821d1-102">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="821d1-103">O código a seguir mostra a implementação de um `Get-Process` cmdlet que pode aceitar entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="821d1-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="821d1-104">Essa implementação define um `Name` parâmetro que aceita entrada de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, usa o método [WriteObject (sistema. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="821d1-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="821d1-105">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="821d1-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
