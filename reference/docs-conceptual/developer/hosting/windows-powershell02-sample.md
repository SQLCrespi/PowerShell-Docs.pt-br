---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra Windows PowerShell02
description: Amostra Windows PowerShell02
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657361"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="1ba9f-103">Amostra Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="1ba9f-103">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="1ba9f-104">Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-104">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="1ba9f-105">O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-105">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ba9f-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ba9f-106">Requirements</span></span>

- <span data-ttu-id="1ba9f-107">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1ba9f-108">Demonstra</span><span class="sxs-lookup"><span data-stu-id="1ba9f-108">Demonstrates</span></span>

<span data-ttu-id="1ba9f-109">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ba9f-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="1ba9f-110">A criação de um objeto RunspacePool com um número mínimo e máximo de espaços de uso podem ser abertos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-110">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="1ba9f-111">Criando uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-111">Creating a list of commands.</span></span>
- <span data-ttu-id="1ba9f-112">Executar os comandos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-112">Running the commands asynchronously.</span></span>
- <span data-ttu-id="1ba9f-113">Chamando o método [System. Management. Automation. Runspaces. Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) para ver quantos espaços de execução são gratuitos.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-113">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="1ba9f-114">Capturando a saída do comando com o método [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="1ba9f-114">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="1ba9f-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1ba9f-115">Example</span></span>

<span data-ttu-id="1ba9f-116">Este exemplo mostra como abrir os Runspaces de um pool de runspace e como executar comandos de forma assíncrona nesses espaços de execução.</span><span class="sxs-lookup"><span data-stu-id="1ba9f-116">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="1ba9f-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ba9f-117">See Also</span></span>

[<span data-ttu-id="1ba9f-118">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ba9f-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
