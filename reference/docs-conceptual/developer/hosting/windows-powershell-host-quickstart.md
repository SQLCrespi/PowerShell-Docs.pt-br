---
title: Início rápido do host do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: 390eb2d0153c65967d8c0711c852aa6e13fe4660
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360815"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="72842-102">Início rápido do Windows PowerShell Host</span><span class="sxs-lookup"><span data-stu-id="72842-102">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="72842-103">Para hospedar o Windows PowerShell em seu aplicativo, use a classe [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .</span><span class="sxs-lookup"><span data-stu-id="72842-103">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span>
<span data-ttu-id="72842-104">Essa classe fornece métodos que criam um pipeline de comandos e executam esses comandos em um runspace.</span><span class="sxs-lookup"><span data-stu-id="72842-104">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span>
<span data-ttu-id="72842-105">A maneira mais simples de criar um aplicativo host é usar o runspace padrão.</span><span class="sxs-lookup"><span data-stu-id="72842-105">The simplest way to create a host application is to use the default runspace.</span></span>
<span data-ttu-id="72842-106">O runspace padrão contém todos os comandos principais do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72842-106">The default runspace contains all of the core Windows PowerShell commands.</span></span>
<span data-ttu-id="72842-107">Se você quiser que seu aplicativo exponha apenas um subconjunto dos comandos do Windows PowerShell, deverá criar um runspace personalizado.</span><span class="sxs-lookup"><span data-stu-id="72842-107">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="72842-108">Usando o runspace padrão</span><span class="sxs-lookup"><span data-stu-id="72842-108">Using the default runspace</span></span>

<span data-ttu-id="72842-109">Para começar, usaremos o runspace padrão e usamos os métodos da classe [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) para adicionar comandos, parâmetros, instruções e scripts a um pipeline.</span><span class="sxs-lookup"><span data-stu-id="72842-109">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="72842-110">O AddCommand</span><span class="sxs-lookup"><span data-stu-id="72842-110">AddCommand</span></span>

<span data-ttu-id="72842-111">Você usa o método [System. Management. Automation. PowerShell. AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) para adicionar comandos ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="72842-111">You use the [System.Management.Automation.Powershell.AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method to add commands to the pipeline.</span></span>
<span data-ttu-id="72842-112">Por exemplo, suponha que você deseja obter a lista de processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="72842-112">For example, suppose you want to get the list of running processes on the machine.</span></span>
<span data-ttu-id="72842-113">A maneira de executar esse comando é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="72842-113">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="72842-114">Crie um objeto [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .</span><span class="sxs-lookup"><span data-stu-id="72842-114">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="72842-115">Adicione o comando que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="72842-115">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="72842-116">Invoque o comando.</span><span class="sxs-lookup"><span data-stu-id="72842-116">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="72842-117">Se você chamar o método AddCommand mais de uma vez antes de chamar o método [System. Management. Automation. PowerShell. Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , o resultado do primeiro comando será canalizado para o segundo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="72842-117">If you call the AddCommand method more than once before you call the [System.Management.Automation.Powershell.Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span>
<span data-ttu-id="72842-118">Se você não quiser canalizar o resultado de um comando anterior para um comando, adicione-o chamando o [System. Management. Automation. PowerShell. Setstatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="72842-118">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="72842-119">AddParameter</span><span class="sxs-lookup"><span data-stu-id="72842-119">AddParameter</span></span>

<span data-ttu-id="72842-120">O exemplo anterior executa um único comando sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="72842-120">The previous example executes a single command without any parameters.</span></span>
<span data-ttu-id="72842-121">Você pode adicionar parâmetros ao comando usando o método [System. Management. Automation. PSCommand. addparâmetro](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .</span><span class="sxs-lookup"><span data-stu-id="72842-121">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method.</span></span>
<span data-ttu-id="72842-122">Por exemplo, o código a seguir obtém uma lista de todos os processos nomeados `PowerShell` em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="72842-122">For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="72842-123">Você pode adicionar parâmetros adicionais chamando o método AddParameter repetidamente.</span><span class="sxs-lookup"><span data-stu-id="72842-123">You can add additional parameters by calling the AddParameter method repeatedly.</span></span>

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

<span data-ttu-id="72842-124">Você também pode adicionar um dicionário de nomes e valores de parâmetro chamando o método [System. Management. Automation. PowerShell. Parameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .</span><span class="sxs-lookup"><span data-stu-id="72842-124">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="72842-125">Addstatement</span><span class="sxs-lookup"><span data-stu-id="72842-125">AddStatement</span></span>

<span data-ttu-id="72842-126">Você pode simular o envio em lote usando o método [System. Management. Automation. PowerShell. Addstatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , que adiciona uma instrução adicional ao final do pipeline.</span><span class="sxs-lookup"><span data-stu-id="72842-126">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline.</span></span>
<span data-ttu-id="72842-127">O código a seguir obtém uma lista de processos em execução com o nome `PowerShell` e obtém a lista de serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="72842-127">The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="72842-128">AddScript</span><span class="sxs-lookup"><span data-stu-id="72842-128">AddScript</span></span>

<span data-ttu-id="72842-129">Você pode executar um script existente chamando o método [System. Management. Automation. PowerShell. addScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) .</span><span class="sxs-lookup"><span data-stu-id="72842-129">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span>
<span data-ttu-id="72842-130">O exemplo a seguir adiciona um script ao pipeline e o executa.</span><span class="sxs-lookup"><span data-stu-id="72842-130">The following example adds a script to the pipeline and runs it.</span></span>
<span data-ttu-id="72842-131">Este exemplo pressupõe que já existe um script chamado `MyScript.ps1` em uma pasta chamada `D:\PSScripts`.</span><span class="sxs-lookup"><span data-stu-id="72842-131">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="72842-132">Também há uma versão do método addScript que usa um parâmetro booleano denominado `useLocalScope`.</span><span class="sxs-lookup"><span data-stu-id="72842-132">There is also a version of the AddScript method that takes a boolean parameter named `useLocalScope`.</span></span>
<span data-ttu-id="72842-133">Se esse parâmetro for definido como `true`, o script será executado no escopo local.</span><span class="sxs-lookup"><span data-stu-id="72842-133">If this parameter is set to `true`, then the script is run in the local scope.</span></span>
<span data-ttu-id="72842-134">O código a seguir executará o script no escopo local.</span><span class="sxs-lookup"><span data-stu-id="72842-134">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="72842-135">Criando um runspace personalizado</span><span class="sxs-lookup"><span data-stu-id="72842-135">Creating a custom runspace</span></span>

<span data-ttu-id="72842-136">Embora o runspace padrão usado nos exemplos anteriores carregue todos os comandos principais do Windows PowerShell, você pode criar um runspace personalizado que carrega apenas um subconjunto especificado de todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="72842-136">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span>
<span data-ttu-id="72842-137">Talvez você queira fazer isso para melhorar o desempenho (carregar um número maior de comandos é um impacto no desempenho) ou para restringir a capacidade do usuário de executar operações.</span><span class="sxs-lookup"><span data-stu-id="72842-137">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span>
<span data-ttu-id="72842-138">Um runspace que expõe apenas um número limitado de comandos é chamado de runspace restrito.</span><span class="sxs-lookup"><span data-stu-id="72842-138">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span>
<span data-ttu-id="72842-139">Para criar um runspace restrito, use as classes [System. Management. Automation. Runspaces. runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) e [System. Management. Automation. Runspaces. InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .</span><span class="sxs-lookup"><span data-stu-id="72842-139">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="72842-140">Criando um objeto InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="72842-140">Creating an InitialSessionState object</span></span>

<span data-ttu-id="72842-141">Para criar um runspace personalizado, você deve primeiro criar um objeto [System. Management. Automation. Runspaces. InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .</span><span class="sxs-lookup"><span data-stu-id="72842-141">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>
<span data-ttu-id="72842-142">No exemplo a seguir, usamos o [System. Management. Automation. Runspaces. RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) para criar um runspace depois de criar um objeto InitialSessionState padrão.</span><span class="sxs-lookup"><span data-stu-id="72842-142">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a runspace after creating a default InitialSessionState object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="72842-143">Restringindo o runspace</span><span class="sxs-lookup"><span data-stu-id="72842-143">Constraining the runspace</span></span>

<span data-ttu-id="72842-144">No exemplo anterior, criamos um objeto [System. Management. Automation. Runspaces. InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) padrão que carrega todo o Windows PowerShell interno.</span><span class="sxs-lookup"><span data-stu-id="72842-144">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span>
<span data-ttu-id="72842-145">Também poderíamos ter chamado o método [System. Management. Automation. Runspaces. InitialSessionState. CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) para criar um objeto InitialSessionState que carregaria apenas os comandos no snap-in Microsoft. PowerShell. Core.</span><span class="sxs-lookup"><span data-stu-id="72842-145">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Microsoft.PowerShell.Core snapin.</span></span>
<span data-ttu-id="72842-146">Para criar um runspace mais restrito, você deve criar um objeto InitialSessionState vazio chamando o método [System. Management. Automation. Runspaces. InitialSessionState. Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) e, em seguida, adicionar comandos ao InitialSessionState.</span><span class="sxs-lookup"><span data-stu-id="72842-146">To create a more constrained runspace, you must create an empty InitialSessionState object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="72842-147">Usar um runspace que carrega apenas os comandos que você especificar fornece um desempenho significativamente aprimorado.</span><span class="sxs-lookup"><span data-stu-id="72842-147">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="72842-148">Você usa os métodos da classe [System. Management. Automation. Runspaces. SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) para definir cmdlets para o estado de sessão inicial.</span><span class="sxs-lookup"><span data-stu-id="72842-148">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span>
<span data-ttu-id="72842-149">O exemplo a seguir cria um estado de sessão inicial vazio e, em seguida, define e adiciona os comandos `Get-Command` e `Import-Module` ao estado de sessão inicial.</span><span class="sxs-lookup"><span data-stu-id="72842-149">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span>
<span data-ttu-id="72842-150">Em seguida, criamos um runspace restrito por esse estado de sessão inicial e executamos os comandos nesse espaço de execução.</span><span class="sxs-lookup"><span data-stu-id="72842-150">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="72842-151">Crie o estado de sessão inicial.</span><span class="sxs-lookup"><span data-stu-id="72842-151">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="72842-152">Defina e adicione comandos ao estado de sessão inicial.</span><span class="sxs-lookup"><span data-stu-id="72842-152">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="72842-153">Crie e abra o runspace.</span><span class="sxs-lookup"><span data-stu-id="72842-153">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="72842-154">Execute um comando e mostre o resultado.</span><span class="sxs-lookup"><span data-stu-id="72842-154">Execute a command and show the result.</span></span>

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

<span data-ttu-id="72842-155">Quando executado, a saída desse código terá a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="72842-155">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```
