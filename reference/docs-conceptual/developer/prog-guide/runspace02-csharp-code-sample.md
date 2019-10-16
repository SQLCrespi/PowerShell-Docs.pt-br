---
title: Exemplo deC#código Runspace02 () | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59a7b8b9-f72e-43fd-9a10-77404441a3f2
caps.latest.revision: 6
ms.openlocfilehash: abf539bc29bd9ccac59bd5957397fbe68951f266
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366615"
---
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="1cd24-102">Exemplo de código Runspace02 (C#)</span><span class="sxs-lookup"><span data-stu-id="1cd24-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="1cd24-103">Aqui está o C# código-fonte do exemplo Runspace02.</span><span class="sxs-lookup"><span data-stu-id="1cd24-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="1cd24-104">Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar o cmdlet `Get-Process` de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="1cd24-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="1cd24-105">Windows Forms e a ligação de dados são usados para exibir os resultados em um controle DataGridView</span><span class="sxs-lookup"><span data-stu-id="1cd24-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="1cd24-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="1cd24-106">Code Sample</span></span>

[!code-csharp[Runspace02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs#L11-L82 "Runspace02.cs")]

## <a name="see-also"></a><span data-ttu-id="1cd24-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cd24-107">See Also</span></span>

[<span data-ttu-id="1cd24-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1cd24-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
