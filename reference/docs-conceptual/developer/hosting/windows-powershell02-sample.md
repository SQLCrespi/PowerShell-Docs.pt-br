---
title: Exemplo de PowerShell02 do Windows | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779379"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="b6e3b-102">Amostra Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="b6e3b-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="b6e3b-103">Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-103">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="b6e3b-104">O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6e3b-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6e3b-105">Requirements</span></span>

- <span data-ttu-id="b6e3b-106">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b6e3b-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="b6e3b-107">Demonstrates</span></span>

<span data-ttu-id="b6e3b-108">Este exemplo demonstra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b6e3b-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="b6e3b-109">A criação de um objeto RunspacePool com um número mínimo e máximo de espaços de uso podem ser abertos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="b6e3b-110">Criando uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-110">Creating a list of commands.</span></span>
- <span data-ttu-id="b6e3b-111">Executar os comandos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-111">Running the commands asynchronously.</span></span>
- <span data-ttu-id="b6e3b-112">Chamando o método [System. Management. Automation. Runspaces. Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) para ver quantos espaços de execução são gratuitos.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="b6e3b-113">Capturando a saída do comando com o método [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="b6e3b-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="b6e3b-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b6e3b-114">Example</span></span>

<span data-ttu-id="b6e3b-115">Este exemplo mostra como abrir os Runspaces de um pool de runspace e como executar comandos de forma assíncrona nesses espaços de execução.</span><span class="sxs-lookup"><span data-stu-id="b6e3b-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="b6e3b-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6e3b-116">See Also</span></span>

[<span data-ttu-id="b6e3b-117">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6e3b-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
