---
title: Exemplo de Runspace03 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d4fa3bca883fb8d78ca1bc8b0c0f9b70f304be06
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772171"
---
# <a name="runspace03-sample"></a><span data-ttu-id="71ac2-102">Amostra Runspace03</span><span class="sxs-lookup"><span data-stu-id="71ac2-102">Runspace03 Sample</span></span>

<span data-ttu-id="71ac2-103">Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar um script de forma síncrona e como lidar com erros de não finalização.</span><span class="sxs-lookup"><span data-stu-id="71ac2-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="71ac2-104">O script recebe uma lista de nomes de processo e, em seguida, recupera tais processos.</span><span class="sxs-lookup"><span data-stu-id="71ac2-104">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="71ac2-105">Os resultados do script, incluindo quaisquer erros de não encerramento gerados durante a execução do script, são exibidos em uma janela do console.</span><span class="sxs-lookup"><span data-stu-id="71ac2-105">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="71ac2-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71ac2-106">Requirements</span></span>

<span data-ttu-id="71ac2-107">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="71ac2-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="71ac2-108">Demonstra</span><span class="sxs-lookup"><span data-stu-id="71ac2-108">Demonstrates</span></span>

<span data-ttu-id="71ac2-109">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="71ac2-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="71ac2-110">Criando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar um script.</span><span class="sxs-lookup"><span data-stu-id="71ac2-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a script.</span></span>

- <span data-ttu-id="71ac2-111">Adicionar um script ao pipeline do objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="71ac2-111">Adding a script to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="71ac2-112">Passando objetos de entrada para o script do programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="71ac2-112">Passing input objects to the script from the calling program.</span></span>

- <span data-ttu-id="71ac2-113">Executando o script de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="71ac2-113">Running the script synchronously.</span></span>

- <span data-ttu-id="71ac2-114">Usando objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) para extrair e exibir propriedades dos objetos retornados pelo script.</span><span class="sxs-lookup"><span data-stu-id="71ac2-114">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the script.</span></span>

- <span data-ttu-id="71ac2-115">Recuperação e exibição de registros de erro que foram gerados quando o script foi executado.</span><span class="sxs-lookup"><span data-stu-id="71ac2-115">Retrieving and displaying error records that were generated when the script was run.</span></span>

## <a name="example"></a><span data-ttu-id="71ac2-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="71ac2-116">Example</span></span>

<span data-ttu-id="71ac2-117">Este exemplo executa um script de forma síncrona no runspace padrão fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71ac2-117">This sample runs a script synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="71ac2-118">A saída do script e quaisquer erros de não encerramento gerados são exibidos em uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="71ac2-118">The output of the script and any non-terminating errors that were generated are displayed in a console window.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace03
  {
    /// <summary>
    /// This sample shows how to use the PowerShell class to run a
    /// script that retrieves process information for the list of
    /// process names passed to the script. It shows how to pass input
    /// objects to a script and how to retrieve error objects as well
    /// as the output objects.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerSHell object to run a script.
    /// 2. Adding a script to the pipeline of the PowerShell object.
    /// 3. Passing input objects to the script from the calling program.
    /// 4. Running the script synchronously.
    /// 5. Using PSObject objects to extract and display properties from
    ///    the objects returned by the script.
    /// 6. Retrieving and displaying error records that were generated
    ///    when the script was run.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Define a list of processes to look for.
      string[] processNames = new string[]
      {
        "lsass", "nosuchprocess", "services", "nosuchprocess2"
      };

      // The script to run to get these processes. Input passed
      // to the script will be available in the $input variable.
      string script = "$input | get-process -name {$_}";

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the script.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddScript(script);

        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the script synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke(processNames))
        {
          Console.WriteLine(
                            "{0,-20} {1}",
                            result.Members["ProcessName"].Value,
                            result.Members["HandleCount"].Value);
        }

        // Process any error records that were generated while running
        //  the script.
        Console.WriteLine("\nThe following non-terminating errors occurred:\n");
        PSDataCollection<ErrorRecord> errors = powershell.Streams.Error;
        if (errors != null && errors.Count > 0)
        {
          foreach (ErrorRecord err in errors)
          {
            System.Console.WriteLine("    error: {0}", err.ToString());
          }
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="71ac2-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71ac2-119">See Also</span></span>

[<span data-ttu-id="71ac2-120">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71ac2-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
