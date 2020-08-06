---
title: Exemplo de Runspace08 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fcf58eceb415f9f02391c22d2719e9140c77ea9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783153"
---
# <a name="runspace08-sample"></a><span data-ttu-id="239e9-102">Amostra Runspace08</span><span class="sxs-lookup"><span data-stu-id="239e9-102">Runspace08 Sample</span></span>

<span data-ttu-id="239e9-103">Este exemplo mostra como adicionar comandos e argumentos ao pipeline de um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) e como executar os comandos de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="239e9-103">This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

## <a name="requirements"></a><span data-ttu-id="239e9-104">Requisitos</span><span class="sxs-lookup"><span data-stu-id="239e9-104">Requirements</span></span>

<span data-ttu-id="239e9-105">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="239e9-105">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="239e9-106">Demonstra</span><span class="sxs-lookup"><span data-stu-id="239e9-106">Demonstrates</span></span>

<span data-ttu-id="239e9-107">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="239e9-107">This sample demonstrates the following.</span></span>

- <span data-ttu-id="239e9-108">Criando um objeto [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) usando a classe [System. Management. Automation. Runspaces. Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) .</span><span class="sxs-lookup"><span data-stu-id="239e9-108">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="239e9-109">Criando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) que usa o runspace.</span><span class="sxs-lookup"><span data-stu-id="239e9-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="239e9-110">Adicionar cmdlets ao pipeline do objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="239e9-110">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="239e9-111">Executando os cmdlets de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="239e9-111">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="239e9-112">Extraindo propriedades dos objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) retornados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="239e9-112">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="239e9-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="239e9-113">Example</span></span>

<span data-ttu-id="239e9-114">Este exemplo executa os cmdlets [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) e [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) usando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="239e9-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace08
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands. The
    /// PowerShell object builds a pipeline that include the get-process cmdlet,
    /// which is then piped to the sort-object cmdlet. Parameters are added to the
    /// sort-object cmdlet to sort the HandleCount property in descending order.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates:
    /// 1. Creating a PowerShell object
    /// 2. Adding individual commands to the PowerShell object.
    /// 3. Adding parameters to the commands.
    /// 4. Running the pipeline of the PowerShell object synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> results; // Holds the result of the pipeline execution.

      // Create the PowerShell object. Notice that no runspace is specified so a
      // new default runspace is used.
      PowerShell powershell = PowerShell.Create();

      // Use the using statement so that we can dispose of the PowerShell object
      // when we are done.
      using (powershell)
      {
        // Add the get-process cmdlet to the pipeline of the PowerShell object.
        powershell.AddCommand("get-process");

        // Add the sort-object cmdlet and its parameters to the pipeline of
        // the PowerShell object so that we can sort the HandleCount property
        //  in descending order.
        powershell.AddCommand("sort-object").AddParameter("descending").AddParameter("property", "handlecount");

        // Run the commands of the pipeline synchronously.
        results = powershell.Invoke();
      }

      // Even after disposing of the PowerShell object, we still
      // need to set the powershell variable to null so that the
      // garbage collector can clean it up.
      powershell = null;

      Console.WriteLine("Process              HandleCount");
      Console.WriteLine("--------------------------------");

      // Display the results returned by the commands.
      foreach (PSObject result in results)
      {
        Console.WriteLine(
                          "{0,-20} {1}",
                          result.Members["ProcessName"].Value,
                          result.Members["HandleCount"].Value);
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="239e9-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="239e9-115">See Also</span></span>

[<span data-ttu-id="239e9-116">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="239e9-116">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
