---
title: Exemplo de Runspace01 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1ac286512f3cb3b97a6b3179c9dd45f1fefe1ecf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772188"
---
# <a name="runspace01-sample"></a><span data-ttu-id="a2ab5-102">Amostra Runspace01</span><span class="sxs-lookup"><span data-stu-id="a2ab5-102">Runspace01 Sample</span></span>

<span data-ttu-id="a2ab5-103">Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span> <span data-ttu-id="a2ab5-104">O cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) retorna objetos [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) para cada processo em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer.</span></span> <span data-ttu-id="a2ab5-105">Os valores das propriedades [System. Diagnostics. Process. ProcessName \*](/dotnet/api/System.Diagnostics.Process.ProcessName) e [System. Diagnostics. Process. HandleCount \*](/dotnet/api/System.Diagnostics.Process.Handlecount) são extraídos dos objetos retornados e exibidos em uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-105">The values of the [System.Diagnostics.Process.Processname\*](/dotnet/api/System.Diagnostics.Process.ProcessName) and [System.Diagnostics.Process.Handlecount\*](/dotnet/api/System.Diagnostics.Process.Handlecount) properties are then extracted from the returned objects and displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2ab5-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2ab5-106">Requirements</span></span>

 <span data-ttu-id="a2ab5-107">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a2ab5-108">Demonstra</span><span class="sxs-lookup"><span data-stu-id="a2ab5-108">Demonstrates</span></span>

- <span data-ttu-id="a2ab5-109">Criando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar um comando.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a command.</span></span>

- <span data-ttu-id="a2ab5-110">Adicionar um comando ao pipeline do objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="a2ab5-110">Adding a command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="a2ab5-111">Executando o comando de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-111">Running the command synchronously.</span></span>

- <span data-ttu-id="a2ab5-112">Usando objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) para extrair propriedades dos objetos retornados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-112">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract properties from the objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="a2ab5-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a2ab5-113">Example</span></span>

 <span data-ttu-id="a2ab5-114">Este exemplo executa o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) de forma síncrona no runspace padrão fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously in the default runspace provided by Windows PowerShell.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="a2ab5-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2ab5-115">See Also</span></span>
