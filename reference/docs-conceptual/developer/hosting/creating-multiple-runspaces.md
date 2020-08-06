---
title: Criando vários espaços de Tróia | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1047492d2b859ae14ddd279e25e5e1dff0013820
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779618"
---
# <a name="creating-multiple-runspaces"></a><span data-ttu-id="db1e1-102">Criar vários runspaces</span><span class="sxs-lookup"><span data-stu-id="db1e1-102">Creating multiple runspaces</span></span>

<span data-ttu-id="db1e1-103">Se você criar um grande número de Runspaces, poderá considerar a criação de um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="db1e1-103">If you create a large number of runspaces, you might consider creating a runspace pool.</span></span> <span data-ttu-id="db1e1-104">Usando um objeto [System. Management. Automation. Runspaces. Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool) , em vez de criar um grande número de Runspaces individuais com as mesmas características, o pode melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="db1e1-104">Using a [System.Management.Automation.Runspaces.Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool) object, rather than creating a large number of individual runspaces with the same characteristics, can improve performance.</span></span>

## <a name="creating-and-using-a-runspace-pool"></a><span data-ttu-id="db1e1-105">Criando e usando um pool de runspace.</span><span class="sxs-lookup"><span data-stu-id="db1e1-105">Creating and using a runspace pool.</span></span>

 <span data-ttu-id="db1e1-106">O exemplo a seguir mostra como criar um pool de runspace e como executar um comando de forma assíncrona em um runspace do pool.</span><span class="sxs-lookup"><span data-stu-id="db1e1-106">The following example shows how to create a runspace pool and how to run a command asynchronously in a runspace of the pool.</span></span>

```csharp
namespace HostRunspacePool
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  /// <summary>
  /// This class provides the Main entry point for the Host application.
  /// </summary>
  internal class HostRunspacePool
  {
    /// <summary>
    /// This sample demonstrates the following.
    /// 1. Creating and opening a runspace pool.
    /// 2. Creating a PowerShell object.
    /// 3. Adding commands and arguments to the PowerShell object.
    /// 4. Running the commands asynchronously using the runspace
    ///    of the runspace pool.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    private static void Main(string[] args)
    {
      // Create a pool of runspaces.
      using (RunspacePool rsp = RunspaceFactory.CreateRunspacePool())
      {
        rsp.Open();

        // Create a PowerShell object to run the following command.
        //  get-process wmi*
        PowerShell gpc = PowerShell.Create();
        // Specify the runspace to use and add commands.
        gpc.RunspacePool = rsp;
        gpc.AddCommand("Get-Process").AddArgument("wmi*");

        // Invoke the command asynchronously.
        IAsyncResult gpcAsyncResult = gpc.BeginInvoke();
        // Get the results of running the command.
        PSDataCollection<PSObject> gpcOutput = gpc.EndInvoke(gpcAsyncResult);

        // Process the output.
        Console.WriteLine("The output from running the command: get-process wmi*");
        for (int i= 0; i < gpcOutput.Count; i++)
        {
         Console.WriteLine(
                           "Process Name: {0} Process Id: {1}",
                           gpcOutput[i].Properties["ProcessName"].Value,
                           gpcOutput[i].Properties["Id"].Value);
        }
      } // End using.
    } // End Main entry point.
  } // End HostPs5 class.
}
```

## <a name="see-also"></a><span data-ttu-id="db1e1-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db1e1-107">See Also</span></span>

 [<span data-ttu-id="db1e1-108">Criar um InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="db1e1-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)
