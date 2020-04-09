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
ms.openlocfilehash: 21d7c4fe69e5026089676c43ad69a4263732cc34
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978246"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="7ddec-102">Exemplo de código RunSpace08</span><span class="sxs-lookup"><span data-stu-id="7ddec-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="7ddec-103">Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="7ddec-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="7ddec-104">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="7ddec-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="7ddec-105">Os comandos que são adicionados ao pipeline são os cmdlets `Get-Process` e `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="7ddec-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="7ddec-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="7ddec-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="7ddec-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ddec-107">See Also</span></span>

[<span data-ttu-id="7ddec-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ddec-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
