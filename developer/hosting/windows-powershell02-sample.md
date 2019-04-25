---
title: Exemplo do Windows PowerShell02 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 89ad17257ebac56105a93672317a149515e80d32
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082508"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="0ae08-102">Amostra Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="0ae08-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="0ae08-103">Este exemplo mostra como executar comandos de forma assíncrona usando os espaços de execução de um pool de Runspaces.</span><span class="sxs-lookup"><span data-stu-id="0ae08-103">This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="0ae08-104">O exemplo gera uma lista de comandos e, em seguida, executa esses comandos, enquanto o mecanismo Windows PowerShell abre um espaço de execução do pool quando ele for necessário.</span><span class="sxs-lookup"><span data-stu-id="0ae08-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="0ae08-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ae08-105">Requirements</span></span>

- <span data-ttu-id="0ae08-106">Este exemplo requer o Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="0ae08-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0ae08-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="0ae08-107">Demonstrates</span></span>

<span data-ttu-id="0ae08-108">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ae08-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="0ae08-109">Criando um objeto RunspacePool com um número mínimo e máximo de espaços de execução pode estar aberto ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0ae08-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>

- <span data-ttu-id="0ae08-110">Criando uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="0ae08-110">Creating a list of commands.</span></span>

- <span data-ttu-id="0ae08-111">Executando os comandos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="0ae08-111">Running the commands asynchronously.</span></span>

- <span data-ttu-id="0ae08-112">Chamar o [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) método para ver quantos espaços de execução são gratuitos.</span><span class="sxs-lookup"><span data-stu-id="0ae08-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>

- <span data-ttu-id="0ae08-113">Capturar a saída do comando com o [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) método.</span><span class="sxs-lookup"><span data-stu-id="0ae08-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="0ae08-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0ae08-114">Example</span></span>

<span data-ttu-id="0ae08-115">Este exemplo mostra como abrir os espaços de execução de um pool de Runspaces e como executar comandos assincronamente esses espaços de execução.</span><span class="sxs-lookup"><span data-stu-id="0ae08-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

[!code-csharp[PowerShell02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a><span data-ttu-id="0ae08-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ae08-116">See Also</span></span>

[<span data-ttu-id="0ae08-117">Escrevendo um aplicativo de Host do PowerShell do Windows</span><span class="sxs-lookup"><span data-stu-id="0ae08-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)