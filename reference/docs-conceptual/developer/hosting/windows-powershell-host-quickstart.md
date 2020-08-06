---
title: Início rápido do host do Windows PowerShell | Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: fea6bd5ae49ecf552c583271ee9d869b1ccebae8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779396"
---
# <a name="windows-powershell-host-quickstart"></a>Início rápido do Windows PowerShell Host

Para hospedar o Windows PowerShell em seu aplicativo, use a classe [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .
Essa classe fornece métodos que criam um pipeline de comandos e executam esses comandos em um runspace.
A maneira mais simples de criar um aplicativo host é usar o runspace padrão.
O runspace padrão contém todos os comandos principais do Windows PowerShell.
Se você quiser que seu aplicativo exponha apenas um subconjunto dos comandos do Windows PowerShell, deverá criar um runspace personalizado.

## <a name="using-the-default-runspace"></a>Usando o runspace padrão

Para começar, usaremos o runspace padrão e usamos os métodos da classe [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) para adicionar comandos, parâmetros, instruções e scripts a um pipeline.

### <a name="addcommand"></a>O AddCommand

Você usa o método [System. Management. Automation. PowerShell. AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) para adicionar comandos ao pipeline.
Por exemplo, suponha que você deseja obter a lista de processos em execução no computador.
A maneira de executar esse comando é a seguinte:

1. Crie um objeto [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .

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

Se você chamar o método AddCommand mais de uma vez antes de chamar o método [System. Management. Automation. PowerShell. Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , o resultado do primeiro comando será canalizado para o segundo e assim por diante.
Se você não quiser canalizar o resultado de um comando anterior para um comando, adicione-o chamando o [System. Management. Automation. PowerShell. Setstatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) em vez disso.

### <a name="addparameter"></a>AddParameter

O exemplo anterior executa um único comando sem parâmetros.
Você pode adicionar parâmetros ao comando usando o método [System. Management. Automation. PSCommand. addparâmetro](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .
Por exemplo, o código a seguir obtém uma lista de todos os processos nomeados `PowerShell` em execução no computador.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

Você pode adicionar parâmetros adicionais chamando o método AddParameter repetidamente.

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

Você também pode adicionar um dicionário de nomes e valores de parâmetro chamando o método [System. Management. Automation. PowerShell. Parameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>Addstatement

Você pode simular o envio em lote usando o método [System. Management. Automation. PowerShell. Addstatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , que adiciona uma instrução adicional ao final do pipeline.
O código a seguir obtém uma lista de processos em execução com o nome `PowerShell` e obtém a lista de serviços em execução.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

Você pode executar um script existente chamando o método [System. Management. Automation. PowerShell. addScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) .
O exemplo a seguir adiciona um script ao pipeline e o executa.
Este exemplo pressupõe que já existe um script chamado `MyScript.ps1` em uma pasta chamada `D:\PSScripts` .

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

Há também uma versão do método addScript que usa um parâmetro booleano denominado `useLocalScope` .
Se esse parâmetro for definido como `true` , o script será executado no escopo local.
O código a seguir executará o script no escopo local.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a>Criando um runspace personalizado

Embora o runspace padrão usado nos exemplos anteriores carregue todos os comandos principais do Windows PowerShell, você pode criar um runspace personalizado que carrega apenas um subconjunto especificado de todos os comandos.
Talvez você queira fazer isso para melhorar o desempenho (carregar um número maior de comandos é um impacto no desempenho) ou para restringir a capacidade do usuário de executar operações.
Um runspace que expõe apenas um número limitado de comandos é chamado de runspace restrito.
Para criar um runspace restrito, use as classes [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) e [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

### <a name="creating-an-initialsessionstate-object"></a>Criando um objeto InitialSessionState

Para criar um runspace personalizado, você deve primeiro criar um objeto [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .
No exemplo a seguir, usamos o [System. Management. Automation. Runspaces. RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) para criar um runspace depois de criar um objeto InitialSessionState padrão.

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a>Restringindo o runspace

No exemplo anterior, criamos um objeto de [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) padrão que carrega todo o Windows PowerShell interno.
Também poderíamos ter chamado o método [System.Management.Automation.Runspaces.InitialSessionState. CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) para criar um objeto InitialSessionState que carregaria apenas os comandos no snap-in Microsoft. PowerShell. Core.
Para criar um runspace mais restrito, você deve criar um objeto InitialSessionState vazio chamando o método [System.Management.Automation.Runspaces.InitialSessionState. Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) e, em seguida, adicionar comandos ao InitialSessionState.

Usar um runspace que carrega apenas os comandos que você especificar fornece um desempenho significativamente aprimorado.

Você usa os métodos da classe [System. Management. Automation. Runspaces. SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) para definir cmdlets para o estado de sessão inicial.
O exemplo a seguir cria um estado de sessão inicial vazio e, em seguida, define e adiciona os `Get-Command` `Import-Module` comandos e ao estado de sessão inicial.
Em seguida, criamos um runspace restrito por esse estado de sessão inicial e executamos os comandos nesse espaço de execução.

Crie o estado de sessão inicial.

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

Defina e adicione comandos ao estado de sessão inicial.

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

Crie e abra o runspace.

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

Execute um comando e mostre o resultado.

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

Quando executado, a saída desse código terá a seguinte aparência.

```powershell
Get-Command
Import-Module
```
