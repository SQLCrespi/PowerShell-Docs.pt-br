---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace09
description: Exemplo de código RunSpace09
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654198"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="30927-103">Exemplo de código RunSpace09</span><span class="sxs-lookup"><span data-stu-id="30927-103">RunSpace09 Code Sample</span></span>

<span data-ttu-id="30927-104">Aqui está o código-fonte para o exemplo de Runspace09 descrito em [criando um aplicativo de console que invoca um pipeline de forma assíncrona](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span><span class="sxs-lookup"><span data-stu-id="30927-104">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="30927-105">Esse aplicativo de exemplo cria e abre um runspace, cria e invoca de forma assíncrona um pipeline e, em seguida, usa eventos de pipeline para processar o script de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="30927-105">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="30927-106">O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundos (500 MS).</span><span class="sxs-lookup"><span data-stu-id="30927-106">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="30927-107">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="30927-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="30927-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="30927-108">See Also</span></span>

[<span data-ttu-id="30927-109">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30927-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
