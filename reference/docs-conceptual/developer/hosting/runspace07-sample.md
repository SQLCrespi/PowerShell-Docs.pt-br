---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra Runspace07
description: Amostra Runspace07
ms.openlocfilehash: 4356f33a1d962a0a6c5ca1ebb8c3e4c579463022
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657654"
---
# <a name="runspace07-sample"></a><span data-ttu-id="7de6f-103">Amostra Runspace07</span><span class="sxs-lookup"><span data-stu-id="7de6f-103">Runspace07 Sample</span></span>

<span data-ttu-id="7de6f-104">Este exemplo mostra como criar um runspace e, em seguida, usar esse runspace para executar dois cmdlets de forma síncrona usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="7de6f-104">This sample shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="7de6f-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7de6f-105">Requirements</span></span>

<span data-ttu-id="7de6f-106">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="7de6f-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7de6f-107">Demonstra</span><span class="sxs-lookup"><span data-stu-id="7de6f-107">Demonstrates</span></span>

<span data-ttu-id="7de6f-108">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="7de6f-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="7de6f-109">Criando um objeto [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) usando a classe [System. Management. Automation. Runspaces. Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) .</span><span class="sxs-lookup"><span data-stu-id="7de6f-109">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="7de6f-110">Criando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) que usa o runspace.</span><span class="sxs-lookup"><span data-stu-id="7de6f-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="7de6f-111">Adicionar cmdlets ao pipeline do objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="7de6f-111">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="7de6f-112">Executando os cmdlets de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="7de6f-112">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="7de6f-113">Extraindo propriedades dos objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) retornados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="7de6f-113">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="7de6f-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7de6f-114">Example</span></span>

<span data-ttu-id="7de6f-115">Este exemplo cria um runspace que é usado por um objeto [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) para executar os cmdlets [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) e [Measure-Object](/powershell/module/microsoft.powershell.utility/measure-object) .</span><span class="sxs-lookup"><span data-stu-id="7de6f-115">This sample creates a runspace that used by a [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) object to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Measure-Object](/powershell/module/microsoft.powershell.utility/measure-object) cmdlets.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace07
  {
    /// <summary>
    /// This sample shows how to create a runspace and how to run commands
    /// using a PowerShell object. It builds a pipeline that runs the
    /// get-process cmdlet, which is piped to the measure-object
    /// cmdlet to count the number of processes running on the system.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a runspace using the RunspaceFactory class.
    /// 2. Creating a PowerShell object that uses the runspace.
    /// 3. Adding cmdlets to the pipeline of the PowerShell object.
    /// 4. Running the cmdlets synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the cmdlets.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> result;     // Will hold the result
                                       // of running the cmdlets.

      // Create a runspace. We can not use the RunspaceInvoke class
      // because we need to get at the underlying runspace to
      // explicitly add the commands. Notice that no PSHost object is
      // supplied to the CreateRunspace method so the default host is
      // used. See the Host samples for more information on creating
      // your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace())
      {
        myRunSpace.Open();

        // Create a PowerShell object and specify the runspace.
        PowerShell powershell = PowerShell.Create();
        powershell.Runspace = myRunSpace;

        // Use the using statement so we dispose of the PowerShell object
        // when we're done.
        using (powershell)
        {
          // Add the get-process cmdlet to the PowerShell object. Notice
          // we are specify the name of the cmdlet, not a script.
          powershell.AddCommand("get-process");

          // Add the measure-object cmdlet to count the number
          // of objects being returned. Commands are always added to the end
          // of the pipeline.
          powershell.AddCommand("measure-object");

          // Run the cmdlets synchronously and save the objects returned.
          result = powershell.Invoke();
        }

        // Even after disposing of the pipeLine, we still need to set
        // the powershell variable to null so that the garbage collector
        // can clean it up.
        powershell = null;

        // Display the results of running the commands (checking that
        // everything is ok first.
        if (result == null || result.Count != 1)
        {
          throw new InvalidOperationException(
                    "pipeline.Invoke() returned the wrong number of objects");
        }

        PSMemberInfo count = result[0].Properties["Count"];
        if (count == null)
        {
          throw new InvalidOperationException(
                    "The object returned doesn't have a 'count' property");
        }

        Console.WriteLine(
                   "Runspace07: The Get-Process cmdlet returned {0} objects",
                   count.Value);

        // Close the runspace to release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="7de6f-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7de6f-116">See Also</span></span>

[<span data-ttu-id="7de6f-117">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7de6f-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
