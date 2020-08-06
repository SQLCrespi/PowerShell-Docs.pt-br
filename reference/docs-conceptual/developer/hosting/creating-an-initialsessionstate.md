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
# <a name="creating-an-initialsessionstate"></a>Criar um InitialSessionState

Os comandos do PowerShell são executados em um runspace.
Para hospedar o PowerShell em seu aplicativo, você deve criar um objeto [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .
Cada runspace tem um objeto [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) associado a ele.
O InitialSessionState especifica características do runspace, como quais comandos, variáveis e módulos estão disponíveis para esse runspace.

## <a name="create-a-default-initialsessionstate"></a>Criar um InitialSessionState padrão

Os métodos [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) e [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) da classe **InitialSessionState** podem ser usados para criar um objeto **InitialSessionState** .
O método **CreateDefault** cria um **InitialSessionState** com todos os comandos internos carregados, enquanto o método **CreateDefault2** carrega apenas os comandos necessários para hospedar o PowerShell (os comandos do módulo Microsoft. PowerShell. Core).

Se você quiser limitar ainda mais os comandos disponíveis no aplicativo host, será necessário criar um runspace restrito.
Para obter informações, consulte [criando um runspace restrito](creating-a-constrained-runspace.md).

O código a seguir mostra como criar um **InitialSessionState**, atribuí-lo a um runspace, adicionar comandos ao pipeline no runspace e invocar os comandos.
Para obter mais informações sobre como adicionar e invocar comandos, consulte [adicionando e invocando comandos](adding-and-invoking-commands.md).

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

## <a name="see-also"></a>Consulte Também

[Criar um runspace com restrição](creating-a-constrained-runspace.md)

[Adicionar e invocar comandos](adding-and-invoking-commands.md)
