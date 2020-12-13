---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra Runspace04
description: Amostra Runspace04
ms.openlocfilehash: 5a2e1137963e02def419bb924c63b0d651b0fdfa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657747"
---
# <a name="runspace04-sample"></a><span data-ttu-id="b6e35-103">Amostra Runspace04</span><span class="sxs-lookup"><span data-stu-id="b6e35-103">Runspace04 Sample</span></span>

<span data-ttu-id="b6e35-104">Este exemplo mostra como usar a classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) para executar comandos e como detectar erros de encerramento que são lançados durante a execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="b6e35-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="b6e35-105">Dois comandos são executados e o último comando é passado um argumento de parâmetro que não é válido.</span><span class="sxs-lookup"><span data-stu-id="b6e35-105">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="b6e35-106">Como resultado, nenhum objeto é retornado e um erro de encerramento é gerado.</span><span class="sxs-lookup"><span data-stu-id="b6e35-106">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6e35-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6e35-107">Requirements</span></span>

<span data-ttu-id="b6e35-108">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="b6e35-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b6e35-109">Demonstra</span><span class="sxs-lookup"><span data-stu-id="b6e35-109">Demonstrates</span></span>

<span data-ttu-id="b6e35-110">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="b6e35-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="b6e35-111">Criando um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="b6e35-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="b6e35-112">Adicionar comandos ao pipeline do objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="b6e35-112">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="b6e35-113">Adicionando argumentos de parâmetro ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="b6e35-113">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="b6e35-114">Invocar os comandos de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="b6e35-114">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="b6e35-115">Usando objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) para extrair e exibir propriedades dos objetos retornados pelos comandos.</span><span class="sxs-lookup"><span data-stu-id="b6e35-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="b6e35-116">Recuperar e exibir os registros de erro que foram gerados durante a execução dos comandos.</span><span class="sxs-lookup"><span data-stu-id="b6e35-116">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="b6e35-117">Captura e exibição de exceções de encerramento geradas pelos comandos.</span><span class="sxs-lookup"><span data-stu-id="b6e35-117">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="b6e35-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b6e35-118">Example</span></span>

<span data-ttu-id="b6e35-119">Este exemplo executa comandos de forma síncrona no runspace padrão fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6e35-119">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="b6e35-120">O último comando gera um erro de encerramento porque um argumento de parâmetro que não é válido é passado para o comando.</span><span class="sxs-lookup"><span data-stu-id="b6e35-120">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="b6e35-121">O erro de encerramento é interceptado e exibido.</span><span class="sxs-lookup"><span data-stu-id="b6e35-121">The terminating error is trapped and displayed.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace04
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands.
    /// The commands generate a terminating exception that the caller
    /// should catch and process.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run commands.
    /// 2. Adding commands to the pipeline of  the PowerShell object.
    /// 3. Passing input objects to the commands from the calling program.
    /// 4. Using PSObject objects to extract and display properties from the
    ///    objects returned by the commands.
    /// 5. Retrieving and displaying error records that were generated
    ///    while running the commands.
    /// 6. Catching and displaying terminating exceptions generated
    ///    while running the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object.
      using (PowerShell powershell = PowerShell.Create())
      {
        // Add the commands to the PowerShell object.
        powershell.AddCommand("Get-ChildItem").AddCommand("Select-String").AddArgument("*");

        // Run the commands synchronously. Because of the bad regular expression,
        // no objects will be returned. Instead, an exception will be thrown.
        try
        {
          foreach (PSObject result in powershell.Invoke())
          {
            Console.WriteLine("'{0}'", result.ToString());
          }

          // Process any error records that were generated while running the commands.
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
        catch (RuntimeException runtimeException)
        {
          // Trap any exception generated by the commands. These exceptions
          // will all be derived from the RuntimeException exception.
          System.Console.WriteLine(
                        "Runtime exception: {0}: {1}\n{2}",
                        runtimeException.ErrorRecord.InvocationInfo.InvocationName,
                        runtimeException.Message,
                        runtimeException.ErrorRecord.InvocationInfo.PositionMessage);
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="b6e35-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6e35-122">See Also</span></span>

[<span data-ttu-id="b6e35-123">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6e35-123">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
