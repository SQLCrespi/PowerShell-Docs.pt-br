---
title: Criando um InitialSessionState | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 946adf1006d1afcad2810c85e39f14514e837327
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779719"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="44605-102">Criar um InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="44605-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="44605-103">Os comandos do PowerShell são executados em um runspace.</span><span class="sxs-lookup"><span data-stu-id="44605-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="44605-104">Para hospedar o PowerShell em seu aplicativo, você deve criar um objeto [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .</span><span class="sxs-lookup"><span data-stu-id="44605-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="44605-105">Cada runspace tem um objeto [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) associado a ele.</span><span class="sxs-lookup"><span data-stu-id="44605-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="44605-106">O InitialSessionState especifica características do runspace, como quais comandos, variáveis e módulos estão disponíveis para esse runspace.</span><span class="sxs-lookup"><span data-stu-id="44605-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="44605-107">Criar um InitialSessionState padrão</span><span class="sxs-lookup"><span data-stu-id="44605-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="44605-108">Os métodos [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) e [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) da classe **InitialSessionState** podem ser usados para criar um objeto **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="44605-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="44605-109">O método **CreateDefault** cria um **InitialSessionState** com todos os comandos internos carregados, enquanto o método **CreateDefault2** carrega apenas os comandos necessários para hospedar o PowerShell (os comandos do módulo Microsoft. PowerShell. Core).</span><span class="sxs-lookup"><span data-stu-id="44605-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="44605-110">Se você quiser limitar ainda mais os comandos disponíveis no aplicativo host, será necessário criar um runspace restrito.</span><span class="sxs-lookup"><span data-stu-id="44605-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="44605-111">Para obter informações, consulte [criando um runspace restrito](creating-a-constrained-runspace.md).</span><span class="sxs-lookup"><span data-stu-id="44605-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="44605-112">O código a seguir mostra como criar um **InitialSessionState**, atribuí-lo a um runspace, adicionar comandos ao pipeline no runspace e invocar os comandos.</span><span class="sxs-lookup"><span data-stu-id="44605-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="44605-113">Para obter mais informações sobre como adicionar e invocar comandos, consulte [adicionando e invocando comandos](adding-and-invoking-commands.md).</span><span class="sxs-lookup"><span data-stu-id="44605-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="44605-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44605-114">See Also</span></span>

[<span data-ttu-id="44605-115">Criar um runspace com restrição</span><span class="sxs-lookup"><span data-stu-id="44605-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="44605-116">Adicionar e invocar comandos</span><span class="sxs-lookup"><span data-stu-id="44605-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
