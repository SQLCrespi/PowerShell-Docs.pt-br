---
ms.date: 09/13/2016
ms.topic: reference
title: Amostras de API do Windows PowerShell
description: Amostras de API do Windows PowerShell
ms.openlocfilehash: b6336ae7a2abb98cbbaa69bf6c9455f893db2d94
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657542"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="56524-103">Amostras de API do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56524-103">Windows PowerShell API Samples</span></span>

<span data-ttu-id="56524-104">Esta seção inclui um código de exemplo que mostra como criar espaços de execução que restringem a funcionalidade e como executar comandos de forma assíncrona usando um pool de runspace para fornecer os Runspaces.</span><span class="sxs-lookup"><span data-stu-id="56524-104">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="56524-105">Você pode usar Microsoft Visual Studio para criar um aplicativo de console e, em seguida, copiar o código dos tópicos nesta seção para seu aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="56524-105">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="56524-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="56524-106">In This Section</span></span>

<span data-ttu-id="56524-107">[Exemplo de PowerShell01](./windows-powershell01-sample.md) Este exemplo mostra como usar um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) para limitar a funcionalidade de um runspace.</span><span class="sxs-lookup"><span data-stu-id="56524-107">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="56524-108">A saída deste exemplo demonstra como restringir o modo de linguagem do runspace, como marcar um cmdlet como particular, como adicionar e remover cmdlets e provedores, como adicionar um comando de proxy e muito mais.</span><span class="sxs-lookup"><span data-stu-id="56524-108">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="56524-109">[Exemplo de PowerShell02](./windows-powershell02-sample.md) Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="56524-109">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="56524-110">O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.</span><span class="sxs-lookup"><span data-stu-id="56524-110">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>
