---
title: Criando um InitialSessionState | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ae707db-52e0-408c-87fa-b35c42eaaab1
caps.latest.revision: 5
ms.openlocfilehash: 9140d03e046def2fbbcc2a842b9ea1b9e1fa2985
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367615"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="e4211-102">Criar um InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="e4211-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="e4211-103">Os comandos do PowerShell são executados em um runspace.</span><span class="sxs-lookup"><span data-stu-id="e4211-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="e4211-104">Para hospedar o PowerShell em seu aplicativo, você deve criar um objeto [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .</span><span class="sxs-lookup"><span data-stu-id="e4211-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="e4211-105">Cada runspace tem um objeto [System. Management. Automation. Runspaces. InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) associado a ele.</span><span class="sxs-lookup"><span data-stu-id="e4211-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="e4211-106">O InitialSessionState especifica características do runspace, como quais comandos, variáveis e módulos estão disponíveis para esse runspace.</span><span class="sxs-lookup"><span data-stu-id="e4211-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="e4211-107">Criar um InitialSessionState padrão</span><span class="sxs-lookup"><span data-stu-id="e4211-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="e4211-108">Os métodos [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) e [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) da classe **InitialSessionState** podem ser usados para criar um objeto **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="e4211-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="e4211-109">O método **CreateDefault** cria um **InitialSessionState** com todos os comandos internos carregados, enquanto o método **CreateDefault2** carrega apenas os comandos necessários para hospedar o PowerShell (os comandos do Módulo Microsoft. PowerShell. Core).</span><span class="sxs-lookup"><span data-stu-id="e4211-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="e4211-110">Se você quiser limitar ainda mais os comandos disponíveis no aplicativo host, será necessário criar um runspace restrito.</span><span class="sxs-lookup"><span data-stu-id="e4211-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="e4211-111">Para obter informações, consulte [criando um runspace restrito](creating-a-constrained-runspace.md).</span><span class="sxs-lookup"><span data-stu-id="e4211-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="e4211-112">O código a seguir mostra como criar um **InitialSessionState**, atribuí-lo a um runspace, adicionar comandos ao pipeline no runspace e invocar os comandos.</span><span class="sxs-lookup"><span data-stu-id="e4211-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="e4211-113">Para obter mais informações sobre como adicionar e invocar comandos, consulte [adicionando e invocando comandos](adding-and-invoking-commands.md).</span><span class="sxs-lookup"><span data-stu-id="e4211-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

```csharp
namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitialSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
      foreach (PSObject result in ps.Invoke())
      {
        Console.WriteLine("{0,-20}{1}",
            result.Members["Name"].Value,
            result.Members["Value"].Value);
      } // End foreach.

      // Close the runspace to free resources.
      rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a><span data-ttu-id="e4211-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4211-114">See Also</span></span>

[<span data-ttu-id="e4211-115">Criando um runspace restrito</span><span class="sxs-lookup"><span data-stu-id="e4211-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="e4211-116">Adicionando e invocando comandos</span><span class="sxs-lookup"><span data-stu-id="e4211-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
