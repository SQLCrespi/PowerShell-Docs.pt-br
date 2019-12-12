---
title: Exemplo de código RunSpace08 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 20032913969606f722f3768b0433775aeaa8c3a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366475"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="e3f2d-102">Exemplo de código RunSpace08</span><span class="sxs-lookup"><span data-stu-id="e3f2d-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="e3f2d-103">Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="e3f2d-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span> <span data-ttu-id="e3f2d-104">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="e3f2d-105">Os comandos que são adicionados ao pipeline são os cmdlets `Get-Process` e `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e3f2d-106">Exemplo de Código</span><span class="sxs-lookup"><span data-stu-id="e3f2d-106">Code Sample</span></span>

[!code-csharp[Runspace08.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a><span data-ttu-id="e3f2d-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3f2d-107">See Also</span></span>

[<span data-ttu-id="e3f2d-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3f2d-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
