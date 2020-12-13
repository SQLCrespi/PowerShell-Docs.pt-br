---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace08
description: Exemplo de código RunSpace08
ms.openlocfilehash: f8d08e5b6bbd98d0901abe5b05c8b9ee682b8e04
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654221"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="2d2e1-103">Exemplo de código RunSpace08</span><span class="sxs-lookup"><span data-stu-id="2d2e1-103">RunSpace08 Code Sample</span></span>

<span data-ttu-id="2d2e1-104">Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="2d2e1-104">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="2d2e1-105">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="2d2e1-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="2d2e1-106">Os comandos que são adicionados ao pipeline são os `Get-Process` `Sort-Object` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="2d2e1-106">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="2d2e1-107">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="2d2e1-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="2d2e1-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d2e1-108">See Also</span></span>

[<span data-ttu-id="2d2e1-109">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d2e1-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
