---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Usando JEA
description: Este artigo descreve as várias maneiras pelas quais você pode se conectar a um ponto de extremidade JEA e usá-lo.
ms.openlocfilehash: b3d81cc0aa76549c81136e5a1a5af28df9c6fa7a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501534"
---
# <a name="using-jea"></a><span data-ttu-id="64a03-104">Usando JEA</span><span class="sxs-lookup"><span data-stu-id="64a03-104">Using JEA</span></span>

<span data-ttu-id="64a03-105">Este artigo descreve as várias maneiras pelas quais você pode se conectar a um ponto de extremidade JEA e usá-lo.</span><span class="sxs-lookup"><span data-stu-id="64a03-105">This article describes the various ways you can connect to and use a JEA endpoint.</span></span>

## <a name="using-jea-interactively"></a><span data-ttu-id="64a03-106">Usando o JEA interativamente</span><span class="sxs-lookup"><span data-stu-id="64a03-106">Using JEA interactively</span></span>

<span data-ttu-id="64a03-107">Se você estiver testando sua configuração JEA ou tiver tarefas simples para os usuários, use o JEA da mesma forma que faria com uma sessão de comunicação remota regular do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64a03-107">If you're testing your JEA configuration or have simple tasks for users, you can use JEA the same way you would a regular PowerShell remoting session.</span></span> <span data-ttu-id="64a03-108">Para tarefas complexas de comunicação remota, é recomendável usar a [comunicação remota implícita](#using-jea-with-implicit-remoting).</span><span class="sxs-lookup"><span data-stu-id="64a03-108">For complex remoting tasks, it's recommended to use [implicit remoting](#using-jea-with-implicit-remoting).</span></span> <span data-ttu-id="64a03-109">A comunicação remota implícita permite que os usuários operem com os objetos de dados localmente.</span><span class="sxs-lookup"><span data-stu-id="64a03-109">Implicit remoting allows users to operate with the data objects locally.</span></span>

<span data-ttu-id="64a03-110">Para usar o JEA de maneira interativamente, você precisará:</span><span class="sxs-lookup"><span data-stu-id="64a03-110">To use JEA interactively, you need:</span></span>

- <span data-ttu-id="64a03-111">Do nome do computador ao qual está se conectando (pode ser o computador local)</span><span class="sxs-lookup"><span data-stu-id="64a03-111">The name of the computer you're connecting to (can be the local machine)</span></span>
- <span data-ttu-id="64a03-112">Do nome do ponto de extremidade JEA registrado nesse computador</span><span class="sxs-lookup"><span data-stu-id="64a03-112">The name of the JEA endpoint registered on that computer</span></span>
- <span data-ttu-id="64a03-113">Das credenciais que têm acesso ao ponto de extremidade JEA nesse computador</span><span class="sxs-lookup"><span data-stu-id="64a03-113">Credentials that have access to the JEA endpoint on that computer</span></span>

<span data-ttu-id="64a03-114">Considerando essas informações, você poderá iniciar uma sessão JEA usando [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) ou [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="64a03-114">Given that information, you can start a JEA session using the [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) or [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlets.</span></span>

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

<span data-ttu-id="64a03-115">Se a conta de usuário atual tiver acesso ao ponto de extremidade JEA, você poderá omitir o parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="64a03-115">If the current user account has access to the JEA endpoint, you can omit the **Credential** parameter.</span></span>

<span data-ttu-id="64a03-116">Quando o prompt do PowerShell mudar para `[localhost]: PS>`, você saberá que está interagindo com a sessão JEA remota.</span><span class="sxs-lookup"><span data-stu-id="64a03-116">When the PowerShell prompt changes to `[localhost]: PS>` you know that you're now interacting with the remote JEA session.</span></span> <span data-ttu-id="64a03-117">Você pode executar o `Get-Command` para verificar quais comandos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="64a03-117">You can run `Get-Command` to check which commands are available.</span></span> <span data-ttu-id="64a03-118">Consulte o administrador para saber se há alguma restrição nos parâmetros disponíveis ou nos valores de parâmetros permitidos.</span><span class="sxs-lookup"><span data-stu-id="64a03-118">Consult with your administrator to learn if there are any restrictions on the available parameters or allowed parameter values.</span></span>

<span data-ttu-id="64a03-119">Lembre-se de que as sessões JEA operam no modo NoLanguage.</span><span class="sxs-lookup"><span data-stu-id="64a03-119">Remember, JEA sessions operate in NoLanguage mode.</span></span> <span data-ttu-id="64a03-120">Algumas das maneiras habituais de usar o PowerShell podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="64a03-120">Some of the ways you typically use PowerShell may not be available.</span></span> <span data-ttu-id="64a03-121">Por exemplo, você não pode usar variáveis para armazenar dados ou inspecionar as propriedades em objetos retornados de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="64a03-121">For instance, you can't use variables to store data or inspect the properties on objects returned from cmdlets.</span></span> <span data-ttu-id="64a03-122">O exemplo a seguir mostra duas abordagens para fazer com que os mesmos comandos funcionem no modo NoLanguage.</span><span class="sxs-lookup"><span data-stu-id="64a03-122">The following example shows two approaches to get the same commands to work in NoLanguage mode.</span></span>

```powershell
# Using variables is prohibited in NoLanguage mode. The following will not work:
# $vm = Get-VM -Name 'SQL01'
# Start-VM -VM $vm

# You can use pipes to pass data through to commands that accept input from the pipeline
Get-VM -Name 'SQL01' | Start-VM

# You can also wrap subcommands in parentheses and enter them inline as arguments
Start-VM -VM (Get-VM -Name 'SQL01')

# You can also use parameter sets that don't require extra data to be passed in
Start-VM -VMName 'SQL01'
```

<span data-ttu-id="64a03-123">Para invocações de comando mais complexas que dificultam essa abordagem, considere o uso da [comunicação remota implícita](#using-jea-with-implicit-remoting) ou a [criação de funções personalizadas](role-capabilities.md#creating-custom-functions) que encapsulam a funcionalidade necessária.</span><span class="sxs-lookup"><span data-stu-id="64a03-123">For more complex command invocations that make this approach difficult, consider using [implicit remoting](#using-jea-with-implicit-remoting) or [creating custom functions](role-capabilities.md#creating-custom-functions) that wrap the functionality you require.</span></span>

## <a name="using-jea-with-implicit-remoting"></a><span data-ttu-id="64a03-124">Usando o JEA com comunicação remota implícita</span><span class="sxs-lookup"><span data-stu-id="64a03-124">Using JEA with implicit remoting</span></span>

<span data-ttu-id="64a03-125">O PowerShell tem um modelo de comunicação remota implícita que permite importar cmdlets de proxy de um computador remoto e interagir com eles como se fossem comandos locais.</span><span class="sxs-lookup"><span data-stu-id="64a03-125">PowerShell has an implicit remoting model that lets you import proxy cmdlets from a remote machine and interact with them as if they were local commands.</span></span> <span data-ttu-id="64a03-126">A comunicação remota implícita é explicada nesta **postagem no blog**</span><span class="sxs-lookup"><span data-stu-id="64a03-126">Implicit remoting is explained in this **Hey, Scripting Guy!**</span></span> <span data-ttu-id="64a03-127">[Hey, Scripting Guy!](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/)</span><span class="sxs-lookup"><span data-stu-id="64a03-127">[blog post](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/).</span></span>
<span data-ttu-id="64a03-128">A comunicação remota implícita é útil ao trabalhar com o JEA porque permite que você trabalhe com os cmdlets do JEA em um modo de linguagem completa.</span><span class="sxs-lookup"><span data-stu-id="64a03-128">Implicit remoting is useful when working with JEA because it allows you to work with JEA cmdlets in a full language mode.</span></span> <span data-ttu-id="64a03-129">Você pode usar a preenchimento com Tab, variáveis, manipular objetos e, até mesmo, usar scripts locais para automatizar tarefas em um ponto de extremidade JEA.</span><span class="sxs-lookup"><span data-stu-id="64a03-129">You can use tab completion, variables, manipulate objects, and even use local scripts to automate tasks against a JEA endpoint.</span></span> <span data-ttu-id="64a03-130">Sempre que você invocar um comando de proxy, os dados serão enviados ao ponto de extremidade JEA no computador remoto e executados nele.</span><span class="sxs-lookup"><span data-stu-id="64a03-130">Anytime you invoke a proxy command, the data is sent to the JEA endpoint on the remote machine and executed there.</span></span>

<span data-ttu-id="64a03-131">A comunicação remota implícita funciona ao importar cmdlets de uma sessão existente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64a03-131">Implicit remoting works by importing cmdlets from an existing PowerShell session.</span></span> <span data-ttu-id="64a03-132">Opcionalmente, você pode optar por colocar prefixos nos substantivos de cada cmdlet de proxy com uma cadeia de caracteres de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="64a03-132">You can optionally choose to prefix the nouns of each proxy cmdlet with a string of your choosing.</span></span> <span data-ttu-id="64a03-133">O prefixo permite distinguir os comandos que são destinados ao sistema remoto.</span><span class="sxs-lookup"><span data-stu-id="64a03-133">The prefix allows you to distinguish the commands that are for the remote system.</span></span> <span data-ttu-id="64a03-134">Um módulo de script temporário contendo todos os comandos de proxy será criado e importado durante a sessão local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64a03-134">A temporary script module containing all the proxy commands is created and imported for the duration of your local PowerShell session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> <span data-ttu-id="64a03-135">Alguns sistemas poderão não ser capazes de importar uma sessão inteira do JEA devido a restrições em cmdlets padrão do JEA.</span><span class="sxs-lookup"><span data-stu-id="64a03-135">Some systems may not be able to import an entire JEA session due to constraints in the default JEA cmdlets.</span></span> <span data-ttu-id="64a03-136">Para contornar isso, importe apenas os comandos necessários da sessão JEA fornecendo explicitamente os nomes deles para o parâmetro `-CommandName`.</span><span class="sxs-lookup"><span data-stu-id="64a03-136">To get around this, only import the commands you need from the JEA session by explicitly providing their names to the `-CommandName` parameter.</span></span> <span data-ttu-id="64a03-137">Uma atualização futura solucionará o problema com a importação de sessões inteiras do JEA nos sistemas afetados.</span><span class="sxs-lookup"><span data-stu-id="64a03-137">A future update will address the issue with importing entire JEA sessions on affected systems.</span></span>

<span data-ttu-id="64a03-138">Se você não puder importar uma sessão JEA devido às restrições do JEA nos parâmetros padrão, siga as etapas abaixo para filtrar os comandos padrão do conjunto importado.</span><span class="sxs-lookup"><span data-stu-id="64a03-138">If you're unable to import a JEA session because of JEA constraints on the default parameters, follow the steps below to filter out the default commands from the imported set.</span></span> <span data-ttu-id="64a03-139">Você poderá continuar usando comandos como `Select-Object`, mas apenas usará a versão local instalada no computador em vez daquela importada da sessão JEA remota.</span><span class="sxs-lookup"><span data-stu-id="64a03-139">You can continue use commands like `Select-Object`, but you'll just use the local version installed on your computer instead of the one imported from the remote JEA session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Get a list of all the commands on the JEA endpoint
$commands = Invoke-Command -Session $jeasession -ScriptBlock { Get-Command }

# Filter out the default cmdlets
$jeaDefaultCmdlets = 'Clear-Host', 'Exit-PSSession', 'Get-Command', 'Get-FormatData', 'Get-Help', 'Measure-Object', 'Out-Default', 'Select-Object'
$filteredCommands = $commands.Name | Where-Object { $jeaDefaultCmdlets -notcontains $_ }

# Import only commands explicitly added in role capabilities and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA' -CommandName $filteredCommands
```

<span data-ttu-id="64a03-140">Também é possível manter os cmdlets do proxy da comunicação remota implícita, usando o [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).</span><span class="sxs-lookup"><span data-stu-id="64a03-140">You can also persist the proxied cmdlets from implicit remoting using [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).</span></span>
<span data-ttu-id="64a03-141">Para obter mais informações sobre a comunicação remota implícita, confira a documentação de [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) e [Import-Module](/powershell/module/microsoft.powershell.core/import-module).</span><span class="sxs-lookup"><span data-stu-id="64a03-141">For more information about implicit remoting, see the documentation for [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) and [Import-Module](/powershell/module/microsoft.powershell.core/import-module).</span></span>

## <a name="using-jea-programmatically"></a><span data-ttu-id="64a03-142">Usando o JEA de forma programática</span><span class="sxs-lookup"><span data-stu-id="64a03-142">Using JEA programmatically</span></span>

<span data-ttu-id="64a03-143">O JEA também pode ser usado em sistemas de automação e em aplicativos de usuário, como sites e aplicativos de assistência técnica na empresa.</span><span class="sxs-lookup"><span data-stu-id="64a03-143">JEA can also be used in automation systems and in user applications, such as in-house helpdesk apps and websites.</span></span> <span data-ttu-id="64a03-144">A abordagem é a mesma usada para a criação de aplicativos que se comunicam com pontos de extremidade irrestritos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64a03-144">The approach is the same as that for building apps that talk to unconstrained PowerShell endpoints.</span></span> <span data-ttu-id="64a03-145">Garanta que o programa seja projetado para trabalhar com a limitação imposta pelo JEA.</span><span class="sxs-lookup"><span data-stu-id="64a03-145">Ensure the program is designed to work with limitation imposed by JEA.</span></span>

<span data-ttu-id="64a03-146">Para tarefas simples e únicas, use [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) para executar comandos em uma sessão JEA.</span><span class="sxs-lookup"><span data-stu-id="64a03-146">For simple, one-off tasks, you can use [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) to run commands in a JEA session.</span></span>

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

<span data-ttu-id="64a03-147">Para verificar quais comandos estão disponíveis para uso quando você se conectar a uma sessão JEA, execute o `Get-Command` e percorra os resultados para verificar os parâmetros permitidos.</span><span class="sxs-lookup"><span data-stu-id="64a03-147">To check which commands are available for use when you connect to a JEA session, run `Get-Command` and iterate through the results to check for the allowed parameters.</span></span>

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

<span data-ttu-id="64a03-148">Se você estiver criando um aplicativo C#, crie um runspace do PowerShell que se conecta a uma sessão JEA especificando o nome da configuração em um objeto [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo).</span><span class="sxs-lookup"><span data-stu-id="64a03-148">If you're building a C# app, you can create a PowerShell runspace that connects to a JEA session by specifying the configuration name in a [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo) object.</span></span>

```csharp
// using System.Management.Automation;
var computerName = "SERVER01";
var configName   = "JEAMaintenance";
// See https://docs.microsoft.com/dotnet/api/system.management.automation.pscredential
var creds        = // create a PSCredential object here

WSManConnectionInfo connectionInfo = new WSManConnectionInfo(
    false,                 // Use SSL
    computerName,          // Computer name
    5985,                  // WSMan Port
    "/wsman",              // WSMan Path
                           // Connection URI with config name
    string.Format(CultureInfo.InvariantCulture, "http://schemas.microsoft.com/powershell/{0}", configName),
    creds);                // Credentials

// Now, use the connection info to create a runspace where you can run the commands
using (Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo))
{
    // Open the runspace
    runspace.Open();

    using (PowerShell ps = PowerShell.Create())
    {
        // Set the PowerShell object to use the JEA runspace
        ps.Runspace = runspace;

        // Now you can add and invoke commands
        ps.AddCommand("Get-Command");
        foreach (var result in ps.Invoke())
        {
            Console.WriteLine(result);
        }
    }

    // Close the runspace
    runspace.Close();
}
```

## <a name="using-jea-with-powershell-direct"></a><span data-ttu-id="64a03-149">Usando o JEA com o PowerShell Direct</span><span class="sxs-lookup"><span data-stu-id="64a03-149">Using JEA with PowerShell Direct</span></span>

<span data-ttu-id="64a03-150">O Hyper-V no Windows 10 e no Windows Server 2016 oferece o [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), um recurso que permite aos administradores do Hyper-V gerenciar máquinas virtuais com o PowerShell, independentemente da configuração da rede ou das configurações de gerenciamento remoto na máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="64a03-150">Hyper-V in Windows 10 and Windows Server 2016 offers [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), a feature that allows Hyper-V administrators to manage virtual machines with PowerShell regardless of the network configuration or remote management settings on the virtual machine.</span></span>

<span data-ttu-id="64a03-151">Use o PowerShell Direct com o JEA para fornecer acesso limitado de administrador do Hyper-V à VM.</span><span class="sxs-lookup"><span data-stu-id="64a03-151">You can use PowerShell Direct with JEA to give a Hyper-V administrator limited access to your VM.</span></span>
<span data-ttu-id="64a03-152">Isso poderá ser útil se você perder a conectividade de rede com a VM e precisar de um administrador de datacenter para corrigir as configurações da rede.</span><span class="sxs-lookup"><span data-stu-id="64a03-152">This can be useful if you lose network connectivity to your VM and need a datacenter admin to fix the network settings.</span></span>

<span data-ttu-id="64a03-153">Nenhuma configuração adicional é necessária para usar o JEA com o PowerShell Direct.</span><span class="sxs-lookup"><span data-stu-id="64a03-153">No additional configuration is required to use JEA over PowerShell Direct.</span></span> <span data-ttu-id="64a03-154">No entanto, o sistema operacional convidado em execução na máquina virtual precisa ser o Windows 10, o Windows Server 2016 ou superior.</span><span class="sxs-lookup"><span data-stu-id="64a03-154">However, the guest operating system running inside the virtual machine must be Windows 10, Windows Server 2016, or higher.</span></span> <span data-ttu-id="64a03-155">O administrador do Hyper-V pode se conectar ao ponto de extremidade JEA usando os parâmetros `-VMName` ou `-VMId` em cmdlets PSRemoting:</span><span class="sxs-lookup"><span data-stu-id="64a03-155">The Hyper-V admin can connect to the JEA endpoint by using the `-VMName` or `-VMId` parameters on PSRemoting cmdlets:</span></span>

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

<span data-ttu-id="64a03-156">É recomendável que você crie uma conta de usuário dedicada com os direitos mínimos necessários para gerenciar o sistema para uso por um administrador do Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="64a03-156">It's recommended you create a dedicated user account with the minimum rights needed to manage the system for use by a Hyper-V administrator.</span></span> <span data-ttu-id="64a03-157">Lembre-se de que, até mesmo, um usuário sem privilégios pode entrar em um computador Windows por padrão, incluindo o uso do PowerShell irrestrito.</span><span class="sxs-lookup"><span data-stu-id="64a03-157">Remember, even an unprivileged user can sign into a Windows machine by default, including using unconstrained PowerShell.</span></span> <span data-ttu-id="64a03-158">Isso permite que ele navegue pelo sistema de arquivos e saiba mais sobre o ambiente do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="64a03-158">That allows them to browse the file system and learn more about your OS environment.</span></span> <span data-ttu-id="64a03-159">Para bloquear um administrador do Hyper-V e limitá-lo somente ao acesso de uma VM usando o PowerShell Direct com o JEA, você precisará negar direitos de logon local à conta do JEA do administrador do Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="64a03-159">To lock down a Hyper-V administrator and limit them to only access a VM using PowerShell Direct with JEA, you must deny local logon rights to the Hyper-V admin's JEA account.</span></span>
