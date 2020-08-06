---
title: Exemplo de código RunSpace09 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fc5d8d4d182cca6bfc42d63c68a14a7a5e5f9c97
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784666"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="54223-102">Exemplo de código RunSpace09</span><span class="sxs-lookup"><span data-stu-id="54223-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="54223-103">Aqui está o código-fonte para o exemplo de Runspace09 descrito em [criando um aplicativo de console que invoca um pipeline de forma assíncrona](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span><span class="sxs-lookup"><span data-stu-id="54223-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="54223-104">Esse aplicativo de exemplo cria e abre um runspace, cria e invoca de forma assíncrona um pipeline e, em seguida, usa eventos de pipeline para processar o script de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="54223-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="54223-105">O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundos (500 MS).</span><span class="sxs-lookup"><span data-stu-id="54223-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="54223-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="54223-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="54223-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54223-107">See Also</span></span>

[<span data-ttu-id="54223-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54223-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
