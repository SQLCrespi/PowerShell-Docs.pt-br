---
ms.date: 09/13/2016
ms.topic: reference
title: Criar um runspace com restrição
description: Criar um runspace com restrição
ms.openlocfilehash: 53fee3cc7d8625425bc6a73196aee9eee7f17ed6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651174"
---
# <a name="creating-a-constrained-runspace"></a>Criar um runspace com restrição

Por motivos de desempenho ou de segurança, talvez você queira restringir os comandos do Windows PowerShell disponíveis para seu aplicativo host. Para fazer isso, você cria um [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) vazio chamando o [System.Management.Automation.Runspaces.Initialsessionstate. Crie](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) o método * e, em seguida, adicione apenas os comandos que você deseja disponibilizar.

 Usar um runspace que carrega apenas os comandos que você especificar fornece um desempenho significativamente aprimorado.

 Você usa os métodos da classe [System. Management. Automation. Runspaces. Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) para definir cmdlets para o estado de sessão inicial.

 Você também pode tornar os comandos privados. Os comandos privados podem ser usados pelo aplicativo host, mas não pelos usuários do aplicativo.

## <a name="adding-commands-to-an-empty-runspace"></a>Adicionando comandos a um runspace vazio

 O exemplo a seguir demonstra como criar um InitialSessionState vazio e adicionar comandos a ele.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using Microsoft.PowerShell.Commands;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class Runspace10b
  {
    /// <summary>
    /// This sample shows how to create an empty initial session state,
    /// how to add commands to the session state, and then how to create a
    /// runspace that has only those two commands. A PowerShell object
    /// is used to run the Get-Command cmdlet to show that only two commands
    /// are available.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create an empty InitialSessionState and then add two commands.
      InitialSessionState iss = InitialSessionState.Create();

      // Add the Get-Process and Get-Command cmdlets to the session state.
      SessionStateCmdletEntry ssce1 = new SessionStateCmdletEntry(
                                                            "get-process",
                                                            typeof(GetProcessCommand),
                                                            null);
      iss.Commands.Add(ssce1);

      SessionStateCmdletEntry ssce2 = new SessionStateCmdletEntry(
                                                            "get-command",
                                                            typeof(GetCommandCommand),
                                                            null);
      iss.Commands.Add(ssce2);

      // Create a runspace.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Create a pipeline with the Get-Command command.
          powershell.AddCommand("get-command");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Verb                 Noun");
          Console.WriteLine("----------------------------");

          // Display each result object.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                             "{0,-20} {1}",
                             result.Members["verb"].Value,
                             result.Members["Noun"].Value);
          }
        }

        // Close the runspace and release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="making-commands-private"></a>Tornando os comandos privados

 Você também pode tornar um comando privado, definindo-o como a propriedade [System. Management. Automation. CommandInfo. Visibility](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) como [System. Management. Automation. SessionStateEntryVisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **particular**. O aplicativo host e outros comandos podem chamar esse comando, mas o usuário do aplicativo não pode. No exemplo a seguir, o comando [Get-ChildItem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) é privado.

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a>Consulte Também

 [Criar um InitialSessionState](./creating-an-initialsessionstate.md)
