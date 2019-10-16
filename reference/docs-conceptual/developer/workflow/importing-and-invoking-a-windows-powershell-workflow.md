---
title: Importando e invocando um fluxo de trabalho do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50e6f9b1-2678-4f53-9250-7c48843a9549
caps.latest.revision: 5
ms.openlocfilehash: 1113c0d1cd68bb97d2f96b529f755b62137d1f40
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366035"
---
# <a name="importing-and-invoking-a-windows-powershell-workflow"></a>Importar e invocar um fluxo de trabalho do Windows PowerShell

O Windows PowerShell 3 permite que você importe e invoque um fluxo de trabalho que é empacotado como um módulo do Windows PowerShell. Para obter informações sobre os módulos do Windows PowerShell, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).

A classe [System. Management. Automation. Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)é usada como um proxy do lado do cliente para objetos de fluxo de trabalho no servidor. O procedimento a seguir explica como usar um objeto [System. Management. Automation. Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy)para invocar um fluxo de trabalho.

### <a name="creating-a-psjobproxy-object-to-execute-workflow-commands-on-a-remote-server"></a>Criando um objeto PSJobProxy para executar comandos de fluxo de trabalho em um servidor remoto.

1. Crie um objeto [System. Management. Automation. Runspaces. Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)para criar uma conexão com um runspace remoto.

2. Defina a propriedade [System. Management. Automation. Runspaces. Wsmanconnectioninfo. Shelluri *](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri) do objeto [System. Management. Automation. Runspaces. Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)como `Microsoft.PowerShell.Workflow` para especificar um ponto de extremidade do Windows PowerShell.

3. Crie um runspace que usa a conexão criada ao concluir as etapas anteriores.

4. Crie um objeto [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell)e defina sua propriedade [System. Management. Automation. PowerShell. runspace *](/dotnet/api/System.Management.Automation.PowerShell.Runspace) para o runspace criado na etapa anterior.

5. Importe o módulo de fluxo de trabalho e seus comandos para o [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell).

6. Crie um objeto [System. Management. Automation. Psjobproxy](/dotnet/api/System.Management.Automation.PSJobProxy) e use-o para executar comandos de fluxo de trabalho no servidor remoto.

## <a name="example"></a>Exemplo

O exemplo de código a seguir demonstra como invocar um fluxo de trabalho usando o Windows PowerShell.

Este exemplo requer o Windows PowerShell 3.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;
using System.Management.Automation.Runspaces;

namespace WorkflowHostTest
{

class Program
    {
        static void Main(string[] args)
        {
            if (args.Length == 0)
            {
                Console.WriteLine("Specify path to Workflow module");
                return;
            }

            string moduleFile = args[0];

            Console.Write("Creating Remote runspace connection...");
            WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

            //Set the shellURI to workflow endpoint Microsoft.PowerShell.Workflow
            connectionInfo.ShellUri = "Microsoft.PowerShell.Workflow";

            //Create and open a runspace.
            Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo);
            runspace.Open();
            Console.WriteLine("done");

            PowerShell powershell = PowerShell.Create();
            powershell.Runspace = runspace;
            Console.Write("Setting $VerbosePreference=\"Continue\"...");
            powershell.AddScript("$VerbosePreference=\"Continue\"");
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Importing Workflow module...");
            powershell.Commands.Clear();

            //Import the module in to the PowerShell runspace. A XAML file could also be imported directly by using Import-Module.
            powershell.AddCommand("Import-Module").AddArgument(moduleFile);
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Creating job proxy...");
            powershell.Commands.Clear();
            powershell.AddCommand("Get-Proc").AddArgument("*");
            PSJobProxy job = powershell.AsJobProxy();
            Console.WriteLine("done");

                Console.WriteLine();
                Console.WriteLine("Using job proxy and performing operations...");
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine("Starting job...");
                job.StartJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());

                // use blocking enumerator to wait for objects until job finishes
                job.Output.BlockingEnumerator = true;
                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                // wait for a random time before attempting to stop job
                Random random = new Random();
                int time = random.Next(1, 10);
                Console.Write("Sleeping for {0} seconds when job is running on another thread...", time);
                System.Threading.Thread.Sleep(time * 1000);
                Console.WriteLine("done");
                Console.WriteLine("Stopping job...");
                job.StopJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine();
                job.Finished.WaitOne();
                Console.WriteLine("Output from job");
                Console.WriteLine("---------------");

                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                Console.WriteLine();
                Console.WriteLine("Verbose messages from job");
                Console.WriteLine("-------------------------");
                foreach (VerboseRecord v in job.Verbose)
                {
                    Console.WriteLine(v.Message);
                }

            runspace.Close();
        }
    }
}

```