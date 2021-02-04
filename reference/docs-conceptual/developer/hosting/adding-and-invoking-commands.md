---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar e invocar comandos
description: Adicionar e invocar comandos
ms.openlocfilehash: f539172eaf119fe5774e158c77a00276c8ba9e0a
ms.sourcegitcommit: 880b00218708724a76503000c9eca181f4e00891
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99049418"
---
# <a name="adding-and-invoking-commands"></a>Adicionar e invocar comandos

Depois de criar um runspace, você pode adicionar PowerShellcommands e scripts do Windows a um pipeline e, em seguida, invocar o pipeline de forma síncrona ou assíncrona.

## <a name="creating-a-pipeline"></a>Criando um pipeline

A classe [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) fornece vários métodos para adicionar comandos, parâmetros e scripts ao pipeline. Você pode invocar o pipeline de forma síncrona chamando uma sobrecarga do método [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , ou assincronamente, chamando uma sobrecarga de [System. Management. Automation. PowerShell. BeginInvoke *](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) e, em seguida, o método [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

### <a name="addcommand"></a>O AddCommand

1. Crie um objeto [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. Adicione o comando que você deseja executar.

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. Invoque o comando.

   ```csharp
   ps.Invoke();
   ```

Se você chamar o método [System. Management. Automation. PowerShell. AddCommand *](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) mais de uma vez antes de chamar o método [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , o resultado do primeiro comando será canalizado para o segundo e assim por diante. Se você não quiser canalizar o resultado de um comando anterior para um comando, adicione-o chamando o [System. Management. Automation. PowerShell. setstatement *](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) em vez disso.

### <a name="addparameter"></a>AddParameter

 O exemplo anterior executa um único comando sem parâmetros. Você pode adicionar parâmetros ao comando usando o método [System. Management. Automation. PSCommand. AddParameter *](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) , por exemplo, o código a seguir obtém uma lista de todos os processos nomeados `PowerShell` em execução no computador.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

Você pode adicionar parâmetros adicionais chamando [System. Management. Automation. PSCommand. AddParameter *](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repetidamente.

```csharp
PowerShell.Create().AddCommand("Get-Command")
                   .AddParameter("Name", "Get-VM")
                   .AddParameter("Module", "Hyper-V")
                   .Invoke();
```

Você também pode adicionar um dicionário de nomes e valores de parâmetro chamando o método [System. Management. Automation. PowerShell. Parameters *](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "Get-VM");

parameters.Add("Module", "Hyper-V");
PowerShell.Create().AddCommand("Get-Command")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>Addstatement

Você pode simular o envio em lote usando o método [System. Management. Automation. PowerShell. addstatement *](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , que adiciona uma instrução adicional ao final do pipeline. o código a seguir obtém uma lista de processos em execução com o nome `PowerShell` e, em seguida, obtém a lista de serviços em execução.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

Você pode executar um script existente chamando o método [System. Management. Automation. PowerShell. addScript *](/dotnet/api/System.Management.Automation.PowerShell.AddScript) . O exemplo a seguir adiciona um script ao pipeline e o executa. Este exemplo pressupõe que já existe um script chamado `MyScript.ps1` em uma pasta chamada `D:\PSScripts` .

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1")).Invoke();
```

Também há uma versão do método [System. Management. Automation. PowerShell. addScript *](/dotnet/api/System.Management.Automation.PowerShell.AddScript) que usa um parâmetro booliano denominado `useLocalScope` . Se esse parâmetro for definido como `true` , o script será executado no escopo local. O código a seguir executará o script no escopo local.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1"), true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a>Invocar um pipeline de forma síncrona

Depois de adicionar elementos ao pipeline, você o invoca. Para invocar o pipeline de forma síncrona, você chama uma sobrecarga do método [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) . O exemplo a seguir mostra como invocar de forma síncrona um pipeline.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a>Invocar um pipeline de forma assíncrona

Você invoca um pipeline de forma assíncrona chamando uma sobrecarga de [System. Management. Automation. PowerShell. BeginInvoke *](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) para criar um objeto [IAsyncResult](/dotnet/api/system.iasyncresult) e, em seguida, chamando o método [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

 O exemplo a seguir mostra como invocar um pipeline de forma assíncrona.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult asyncpl = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(asyncpl))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a>Consulte Também

 [Criar um InitialSessionState](./creating-an-initialsessionstate.md)

 [Criar um runspace com restrição](./creating-a-constrained-runspace.md)
