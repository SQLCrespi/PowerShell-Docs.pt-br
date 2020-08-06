---
title: Exemplo de código RunSpace08 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784683"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="f65c1-102">Exemplo de código RunSpace08</span><span class="sxs-lookup"><span data-stu-id="f65c1-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="f65c1-103">Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="f65c1-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="f65c1-104">Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="f65c1-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="f65c1-105">Os comandos que são adicionados ao pipeline são os `Get-Process` `Sort-Object` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="f65c1-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f65c1-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="f65c1-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="f65c1-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f65c1-107">See Also</span></span>

[<span data-ttu-id="f65c1-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65c1-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
