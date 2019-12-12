---
title: Exemplo de PowerShell02 do Windows | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: db7ff3a2dbd92f562379d206db494ab92ef08736
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367295"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="0c08f-102">Amostra Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="0c08f-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="0c08f-103">Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="0c08f-103">This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="0c08f-104">O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.</span><span class="sxs-lookup"><span data-stu-id="0c08f-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c08f-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c08f-105">Requirements</span></span>

- <span data-ttu-id="0c08f-106">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="0c08f-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0c08f-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="0c08f-107">Demonstrates</span></span>

<span data-ttu-id="0c08f-108">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c08f-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="0c08f-109">A criação de um objeto RunspacePool com um número mínimo e máximo de espaços de uso podem ser abertos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0c08f-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>

- <span data-ttu-id="0c08f-110">Criando uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="0c08f-110">Creating a list of commands.</span></span>

- <span data-ttu-id="0c08f-111">Executar os comandos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="0c08f-111">Running the commands asynchronously.</span></span>

- <span data-ttu-id="0c08f-112">Chamando o método [System. Management. Automation. Runspaces. Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) para ver quantos espaços de execução são gratuitos.</span><span class="sxs-lookup"><span data-stu-id="0c08f-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>

- <span data-ttu-id="0c08f-113">Capturando a saída do comando com o método [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="0c08f-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="0c08f-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0c08f-114">Example</span></span>

<span data-ttu-id="0c08f-115">Este exemplo mostra como abrir os Runspaces de um pool de runspace e como executar comandos de forma assíncrona nesses espaços de execução.</span><span class="sxs-lookup"><span data-stu-id="0c08f-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

[!code-csharp[PowerShell02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a><span data-ttu-id="0c08f-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c08f-116">See Also</span></span>

[<span data-ttu-id="0c08f-117">Escrevendo um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c08f-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
