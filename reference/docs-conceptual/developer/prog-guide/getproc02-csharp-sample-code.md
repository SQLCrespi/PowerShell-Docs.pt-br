---
title: Código de exemplo de GetProc02 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d9afa8fff23d99661987c067e8082a9294c12717
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787148"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="2cd8c-102">Código de exemplo GetProc02 (C#)</span><span class="sxs-lookup"><span data-stu-id="2cd8c-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="2cd8c-103">O código a seguir mostra a implementação de um `Get-Process` cmdlet que aceita a entrada de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2cd8c-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="2cd8c-104">Observe que essa implementação define um `Name` parâmetro para permitir a entrada da linha de comando e usa o método [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) como o mecanismo de saída para enviar objetos de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cd8c-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="2cd8c-105">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="2cd8c-105">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="2cd8c-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cd8c-106">See Also</span></span>

[<span data-ttu-id="2cd8c-107">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cd8c-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
