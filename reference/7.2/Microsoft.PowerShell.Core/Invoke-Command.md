---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: d8f0a8a56792a39371a307166788f047fec99a9a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598632"
---
# <span data-ttu-id="43df6-102">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="43df6-102">Invoke-Command</span></span>

## <span data-ttu-id="43df6-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="43df6-103">SYNOPSIS</span></span>
<span data-ttu-id="43df6-104">Executa comandos em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-104">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="43df6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43df6-105">SYNTAX</span></span>

### <span data-ttu-id="43df6-106">Inprocessar (padrão)</span><span class="sxs-lookup"><span data-stu-id="43df6-106">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-107">FilePathRunspace</span><span class="sxs-lookup"><span data-stu-id="43df6-107">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-108">Sessão</span><span class="sxs-lookup"><span data-stu-id="43df6-108">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-109">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="43df6-109">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="43df6-110">ComputerName</span><span class="sxs-lookup"><span data-stu-id="43df6-110">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="43df6-111">Uri</span><span class="sxs-lookup"><span data-stu-id="43df6-111">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-112">FilePathUri</span><span class="sxs-lookup"><span data-stu-id="43df6-112">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-113">VMId</span><span class="sxs-lookup"><span data-stu-id="43df6-113">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-114">VMName</span><span class="sxs-lookup"><span data-stu-id="43df6-114">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-115">FilePathVMId</span><span class="sxs-lookup"><span data-stu-id="43df6-115">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-116">FilePathVMName</span><span class="sxs-lookup"><span data-stu-id="43df6-116">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-117">SSHHost</span><span class="sxs-lookup"><span data-stu-id="43df6-117">SSHHost</span></span>

```
Invoke-Command [-Port <Int32>] [-AsJob] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> -HostName <String[]> [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-118">ContainerId</span><span class="sxs-lookup"><span data-stu-id="43df6-118">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-119">FilePathContainerId</span><span class="sxs-lookup"><span data-stu-id="43df6-119">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="43df6-120">SSHHostHashParam</span><span class="sxs-lookup"><span data-stu-id="43df6-120">SSHHostHashParam</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] [-JobName <String>] [-ScriptBlock] <ScriptBlock>
 -SSHConnection <Hashtable[]> [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="43df6-121">FilePathSSHHost</span><span class="sxs-lookup"><span data-stu-id="43df6-121">FilePathSSHHost</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -HostName <String[]>
 [-UserName <String>] [-KeyFilePath <String>] [-SSHTransport] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="43df6-122">FilePathSSHHostHash</span><span class="sxs-lookup"><span data-stu-id="43df6-122">FilePathSSHHostHash</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -SSHConnection <Hashtable[]>
 [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="43df6-123">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43df6-123">DESCRIPTION</span></span>

<span data-ttu-id="43df6-124">O `Invoke-Command` cmdlet executa comandos em um computador local ou remoto e retorna toda a saída dos comandos, incluindo erros.</span><span class="sxs-lookup"><span data-stu-id="43df6-124">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="43df6-125">Usando um único `Invoke-Command` comando, você pode executar comandos em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-125">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="43df6-126">Para executar um único comando em um computador remoto, use o parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="43df6-126">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="43df6-127">Para executar uma série de comandos relacionados que compartilham dados, use o `New-PSSession` cmdlet para criar uma **PSSession** (uma conexão persistente) no computador remoto e, em seguida, use o parâmetro **Session** de `Invoke-Command` para executar o comando em **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="43df6-127">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession**.</span></span> <span data-ttu-id="43df6-128">Para executar um comando em uma sessão desconectada, use o parâmetro **InDisconnectedSession**.</span><span class="sxs-lookup"><span data-stu-id="43df6-128">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="43df6-129">Para executar um comando em um trabalho em segundo plano, use o parâmetro **AsJob**.</span><span class="sxs-lookup"><span data-stu-id="43df6-129">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="43df6-130">Você também pode usar `Invoke-Command` em um computador local para um bloco de script como um comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-130">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="43df6-131">O PowerShell executa o bloco de script imediatamente em um escopo filho do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="43df6-131">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="43df6-132">Antes de usar o `Invoke-Command` para executar comandos em um computador remoto, leia [about_Remote](./About/about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-132">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="43df6-133">A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com o e invocar comandos em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-133">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and invoke commands on remote computers.</span></span> <span data-ttu-id="43df6-134">O SSH deve ser instalado no computador local e o computador remoto deve ser configurado com um ponto de extremidade SSH do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43df6-134">SSH must be installed on the local computer and the remote computer must be configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="43df6-135">O benefício de uma sessão remota do PowerShell baseada em SSH é que ela funciona em várias plataformas (Windows, Linux e macOS).</span><span class="sxs-lookup"><span data-stu-id="43df6-135">The benefit of an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="43df6-136">Para sessão baseada em SSH, use os parâmetros **hostname** ou **SSHConnection** para especificar o computador remoto e as informações de conexão relevantes.</span><span class="sxs-lookup"><span data-stu-id="43df6-136">For SSH based session you use the **HostName** or **SSHConnection** parameters to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="43df6-137">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="43df6-137">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="43df6-138">Alguns exemplos de código usam nivelamento para reduzir o comprimento da linha.</span><span class="sxs-lookup"><span data-stu-id="43df6-138">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="43df6-139">Para obter mais informações, consulte [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-139">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="43df6-140">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="43df6-140">EXAMPLES</span></span>

### <span data-ttu-id="43df6-141">Exemplo 1: executar um script em um servidor</span><span class="sxs-lookup"><span data-stu-id="43df6-141">Example 1: Run a script on a server</span></span>

<span data-ttu-id="43df6-142">Este exemplo executa o `Test.ps1` script no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="43df6-142">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="43df6-143">O parâmetro **FilePath** especifica um script que está localizado no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-143">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="43df6-144">O script é executado no computador remoto e os resultados são retornados ao computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-144">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="43df6-145">Exemplo 2: executar um comando em um servidor remoto</span><span class="sxs-lookup"><span data-stu-id="43df6-145">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="43df6-146">Este exemplo executa um `Get-Culture` comando no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="43df6-146">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="43df6-147">O parâmetro **ComputerName** especifica o nome do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-147">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="43df6-148">O parâmetro **Credential** é usado para executar o comando no contexto de segurança de Domínio01 \ Usuário01, um usuário que tem permissão para executar comandos.</span><span class="sxs-lookup"><span data-stu-id="43df6-148">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="43df6-149">O parâmetro **scriptblock** especifica o comando a ser executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-149">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="43df6-150">Em resposta, o PowerShell solicita a senha e um método de autenticação para a conta User01.</span><span class="sxs-lookup"><span data-stu-id="43df6-150">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="43df6-151">Em seguida, ele executa o comando no computador Server01 e retorna o resultado.</span><span class="sxs-lookup"><span data-stu-id="43df6-151">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="43df6-152">Exemplo 3: executar um comando em uma conexão persistente</span><span class="sxs-lookup"><span data-stu-id="43df6-152">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="43df6-153">Este exemplo executa o mesmo `Get-Culture` comando em uma sessão, usando uma conexão persistente, no computador remoto chamado Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-153">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="43df6-154">O `New-PSSession` cmdlet cria uma sessão no computador remoto Server02 e salva-a na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-154">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="43df6-155">Normalmente, você cria uma sessão somente quando executa uma série de comandos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-155">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="43df6-156">O `Invoke-Command` cmdlet executa o `Get-Culture` comando em Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-156">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="43df6-157">O parâmetro **Session** especifica a sessão salva na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-157">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="43df6-158">Em resposta, o PowerShell executa o comando na sessão no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-158">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="43df6-159">Exemplo 4: usar uma sessão para executar uma série de comandos que compartilham dados</span><span class="sxs-lookup"><span data-stu-id="43df6-159">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="43df6-160">Este exemplo compara os efeitos do uso de **ComputerName** e de parâmetros de **sessão** do `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="43df6-160">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="43df6-161">Ele mostra como utilizar uma sessão para executar uma série de comandos que compartilham os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="43df6-161">It shows how to use a session to run a series of commands that share the same data.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

<span data-ttu-id="43df6-162">Os dois primeiros comandos usam o parâmetro **ComputerName** do `Invoke-Command` para executar comandos no computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-162">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="43df6-163">O primeiro comando usa o `Get-Process` cmdlet para obter o processo do PowerShell no computador remoto e salvá-lo na `$p` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-163">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="43df6-164">O segundo comando obtém o valor da propriedade **VirtualMemorySize** do processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43df6-164">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="43df6-165">Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma nova sessão para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-165">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="43df6-166">A sessão é fechada quando o comando é concluído.</span><span class="sxs-lookup"><span data-stu-id="43df6-166">The session is closed when the command completes.</span></span> <span data-ttu-id="43df6-167">A `$p` variável foi criada em uma conexão, mas ela não existe na conexão criada para o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-167">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="43df6-168">O problema é resolvido com a criação de uma sessão persistente no computador remoto e, em seguida, a execução dos dois comandos na mesma sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-168">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="43df6-169">O `New-PSSession` cmdlet cria uma sessão persistente no computador Server02 e salva a sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-169">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="43df6-170">As `Invoke-Command` linhas a seguir usam o parâmetro **Session** para executar os dois comandos na mesma sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-170">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="43df6-171">Como ambos os comandos são executados na mesma sessão, o `$p` valor permanece ativo.</span><span class="sxs-lookup"><span data-stu-id="43df6-171">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="43df6-172">Exemplo 5: inserir um comando armazenado em uma variável local</span><span class="sxs-lookup"><span data-stu-id="43df6-172">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="43df6-173">Este exemplo mostra como criar um comando que é armazenado como um bloco de script em uma variável local.</span><span class="sxs-lookup"><span data-stu-id="43df6-173">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="43df6-174">Quando o bloco de script é salvo em uma variável local, você pode especificar a variável como o valor do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="43df6-174">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-WinEvent -LogName PowerShellCore/Operational |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="43df6-175">A `$command` variável armazena o `Get-WinEvent` comando que é formatado como um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="43df6-175">The `$command` variable stores the `Get-WinEvent` command that's formatted as a script block.</span></span> <span data-ttu-id="43df6-176">O `Invoke-Command` executa o comando armazenado em `$command` nos computadores remotos S1 e S2.</span><span class="sxs-lookup"><span data-stu-id="43df6-176">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="43df6-177">Exemplo 6: executar um único comando em vários computadores</span><span class="sxs-lookup"><span data-stu-id="43df6-177">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="43df6-178">Este exemplo demonstra como usar `Invoke-Command` o para executar um único comando em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-178">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-WinEvent -LogName PowerShellCore/Operational }
}
Invoke-Command @parameters
```

<span data-ttu-id="43df6-179">O parâmetro **ComputerName** especifica uma lista separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-179">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="43df6-180">A lista de computadores inclui o valor de localhost, que representa o computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-180">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="43df6-181">O parâmetro **ConfigurationName** especifica uma configuração de sessão alternativa.</span><span class="sxs-lookup"><span data-stu-id="43df6-181">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="43df6-182">O parâmetro **scriptblock** é executado `Get-WinEvent` para obter os logs de eventos PowerShellCore/operacionais de cada computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-182">The **ScriptBlock** parameter runs `Get-WinEvent` to get the PowerShellCore/Operational event logs from each computer.</span></span>

### <span data-ttu-id="43df6-183">Exemplo 7: obter a versão do programa host em vários computadores</span><span class="sxs-lookup"><span data-stu-id="43df6-183">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="43df6-184">Este exemplo obtém a versão do programa host do PowerShell em execução em computadores remotos 200.</span><span class="sxs-lookup"><span data-stu-id="43df6-184">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="43df6-185">Como apenas um comando é executado, você não precisa criar conexões persistentes para cada um dos computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-185">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="43df6-186">Em vez disso, o comando usa o parâmetro **ComputerName** para indicar os computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-186">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="43df6-187">Para especificar os computadores, ele usa o `Get-Content` cmdlet para obter o conteúdo do arquivo de Machine.txt, um arquivo de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-187">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="43df6-188">O `Invoke-Command` cmdlet executa um `Get-Host` comando nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-188">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="43df6-189">Ele usa a notação de ponto para obter a propriedade **version** do host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43df6-189">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="43df6-190">Esses comandos são executados um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="43df6-190">These commands run one at a time.</span></span> <span data-ttu-id="43df6-191">Quando os comandos forem concluídos, a saída dos comandos de todos os computadores será salva na `$version` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-191">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="43df6-192">A saída inclui o nome do computador de origem de dados.</span><span class="sxs-lookup"><span data-stu-id="43df6-192">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="43df6-193">Exemplo 8: executar um trabalho em segundo plano em vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="43df6-193">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="43df6-194">Este exemplo executa um comando em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-194">This example runs a command on two remote computers.</span></span> <span data-ttu-id="43df6-195">O `Invoke-Command` comando usa o parâmetro **AsJob** para que o comando seja executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="43df6-195">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="43df6-196">Os comandos são executados nos computadores remotos, mas o trabalho existe no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-196">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="43df6-197">Os resultados são transmitidos para o computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-197">The results are transmitted to the local computer.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

<span data-ttu-id="43df6-198">O `New-PSSession` cmdlet cria sessões nos computadores remotos Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-198">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="43df6-199">O `Invoke-Command` cmdlet executa um trabalho em segundo plano em cada uma das sessões.</span><span class="sxs-lookup"><span data-stu-id="43df6-199">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="43df6-200">O comando usa o parâmetro **AsJob** para executar o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="43df6-200">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="43df6-201">Esse comando retorna um objeto de trabalho que contém dois objetos de trabalho filho, um para cada um dos trabalhos executados nos dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-201">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="43df6-202">O `Get-Job` comando salva o objeto de trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-202">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="43df6-203">`$j`Em seguida, a variável é canalizada para o `Format-List` cmdlet para exibir todas as propriedades do objeto de trabalho em uma lista.</span><span class="sxs-lookup"><span data-stu-id="43df6-203">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="43df6-204">O último comando obtém os resultados dos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="43df6-204">The last command gets the results of the jobs.</span></span> <span data-ttu-id="43df6-205">Ele canaliza o objeto de trabalho `$j` para o `Receive-Job` cmdlet e armazena os resultados na `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-205">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="43df6-206">Exemplo 9: incluir variáveis locais em um comando executado em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="43df6-206">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="43df6-207">Este exemplo mostra como incluir os valores das variáveis locais em um comando executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-207">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="43df6-208">O comando usa o `Using` modificador de escopo para identificar uma variável local em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-208">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="43df6-209">Por padrão, todas as variáveis devem ser definidas na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43df6-209">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="43df6-210">O `Using` modificador de escopo foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-210">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="43df6-211">Para obter mais informações sobre o `Using` modificador de escopo, consulte [about_Remote_Variables](./About/about_Remote_Variables.md) e [about_Scopes](./about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-211">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "PowerShellCore/Operational"
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-WinEvent -LogName $Using:Log -MaxEvents 10}
```

<span data-ttu-id="43df6-212">A `$Log` variável armazena o nome do log de eventos, PowerShellCore/Operational.</span><span class="sxs-lookup"><span data-stu-id="43df6-212">The `$Log` variable stores the name of the event log, PowerShellCore/Operational.</span></span> <span data-ttu-id="43df6-213">O `Invoke-Command` cmdlet é executado `Get-WinEvent` no Server01 para obter os dez eventos mais recentes do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="43df6-213">The `Invoke-Command` cmdlet runs `Get-WinEvent` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="43df6-214">O valor do parâmetro **LogName** é a `$Log` variável que é prefixada pelo `Using` modificador de escopo para indicar que ele foi criado na sessão local, não na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43df6-214">The value of the **LogName** parameter is the `$Log` variable that is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="43df6-215">Exemplo 10: ocultar o nome do computador</span><span class="sxs-lookup"><span data-stu-id="43df6-215">Example 10: Hide the computer name</span></span>

<span data-ttu-id="43df6-216">Este exemplo mostra o efeito de usar o parâmetro **HideComputerName** de `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="43df6-216">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="43df6-217">**HideComputerName** não altera o objeto retornado por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-217">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="43df6-218">Ele altera apenas a exibição.</span><span class="sxs-lookup"><span data-stu-id="43df6-218">It changes only the display.</span></span> <span data-ttu-id="43df6-219">Você ainda pode usar os cmdlets **Format** para exibir a propriedade **PSComputerName** de qualquer um dos objetos afetados.</span><span class="sxs-lookup"><span data-stu-id="43df6-219">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

<span data-ttu-id="43df6-220">Os dois primeiros comandos usam `Invoke-Command` para executar um `Get-Process` comando para o processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43df6-220">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="43df6-221">A saída do primeiro comando inclui a propriedade **PsComputerName**, que contém o nome do computador no qual o comando foi executado.</span><span class="sxs-lookup"><span data-stu-id="43df6-221">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="43df6-222">A saída do segundo comando, que usa **HideComputerName**, não inclui a coluna **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="43df6-222">The output of the second command, which uses **HideComputerName**, doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="43df6-223">Exemplo 11: usar a palavra-chave param em um bloco de script</span><span class="sxs-lookup"><span data-stu-id="43df6-223">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="43df6-224">A `Param` palavra-chave e o parâmetro **ArgumentList** são usados para passar valores de variáveis para parâmetros nomeados em um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="43df6-224">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="43df6-225">Este exemplo exibe os nomes de nome que começam com a letra `a` e têm a `.pdf` extensão.</span><span class="sxs-lookup"><span data-stu-id="43df6-225">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="43df6-226">Para obter mais informações sobre a `Param` palavra-chave, consulte [about_Language_Keywords](./about/about_language_keywords.md#param).</span><span class="sxs-lookup"><span data-stu-id="43df6-226">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

<span data-ttu-id="43df6-227">`Invoke-Command` usa o parâmetro **scriptblock** que define duas variáveis, `$param1` e `$param2` .</span><span class="sxs-lookup"><span data-stu-id="43df6-227">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="43df6-228">`Get-ChildItem` usa os parâmetros nomeados, **Name** e **include** com os nomes de variáveis.</span><span class="sxs-lookup"><span data-stu-id="43df6-228">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="43df6-229">O **argumentolist** passa os valores para as variáveis.</span><span class="sxs-lookup"><span data-stu-id="43df6-229">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="43df6-230">Exemplo 12: usar a $args variável automática em um bloco de script</span><span class="sxs-lookup"><span data-stu-id="43df6-230">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="43df6-231">A `$args` variável automática e o parâmetro **ArgumentList** são usados para passar valores de matriz para posições de parâmetro em um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="43df6-231">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="43df6-232">Este exemplo exibe o conteúdo do diretório de arquivos de um servidor `.txt` .</span><span class="sxs-lookup"><span data-stu-id="43df6-232">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="43df6-233">O `Get-ChildItem` parâmetro de **caminho** é a posição 0 e o parâmetro de **filtro** é posição</span><span class="sxs-lookup"><span data-stu-id="43df6-233">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="43df6-234">Para obter mais informações sobre a `$args` variável, consulte [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="43df6-234">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

<span data-ttu-id="43df6-235">`Invoke-Command` usa um parâmetro **scriptblock** e `Get-ChildItem` especifica os `$args[0]` valores de `$args[1]` matriz e.</span><span class="sxs-lookup"><span data-stu-id="43df6-235">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="43df6-236">O **argumentolist** passa os `$args` valores de matriz para as `Get-ChildItem` posições de parâmetro para **caminho** e **filtro**.</span><span class="sxs-lookup"><span data-stu-id="43df6-236">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter**.</span></span>

### <span data-ttu-id="43df6-237">Exemplo 13: executar um script em todos os computadores listados em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="43df6-237">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="43df6-238">Este exemplo usa o `Invoke-Command` cmdlet para executar o `Sample.ps1` script em todos os computadores listados no `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="43df6-238">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="43df6-239">O comando usa o parâmetro **FilePath** para especificar o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="43df6-239">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="43df6-240">Esse comando permite que você execute o script nos computadores remotos, mesmo que o arquivo de script não esteja acessível para os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-240">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="43df6-241">Quando você envia o comando, o conteúdo do `Sample.ps1` arquivo é copiado em um bloco de script e o bloco de script é executado em cada um dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-241">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="43df6-242">Esse procedimento equivale a utilizar o parâmetro **ScriptBlock** para enviar o conteúdo do script.</span><span class="sxs-lookup"><span data-stu-id="43df6-242">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="43df6-243">Exemplo 14: executar um comando em um computador remoto usando um URI</span><span class="sxs-lookup"><span data-stu-id="43df6-243">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="43df6-244">Este exemplo mostra como executar um comando em um computador remoto que é identificado por um Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="43df6-244">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="43df6-245">Este exemplo específico executa um `Set-Mailbox` comando em um servidor Exchange remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-245">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

<span data-ttu-id="43df6-246">A primeira linha usa o `Get-Credential` cmdlet para armazenar as credenciais do Windows Live ID na `$LiveCred` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-246">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="43df6-247">O PowerShell solicita que o usuário insira as credenciais do Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="43df6-247">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="43df6-248">A `$parameters` variável é uma tabela de hash que contém os parâmetros a serem passados para o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-248">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="43df6-249">O `Invoke-Command` cmdlet executa um `Set-Mailbox` comando usando a configuração de sessão do **Microsoft. Exchange** .</span><span class="sxs-lookup"><span data-stu-id="43df6-249">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="43df6-250">O parâmetro **ConnectionURI** especifica a URL do ponto de extremidade do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="43df6-250">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="43df6-251">O parâmetro **Credential** especifica as credenciais armazenadas na `$LiveCred` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-251">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="43df6-252">O parâmetro **AuthenticationMechanism** especifica o uso da autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="43df6-252">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="43df6-253">O parâmetro **ScriptBlock** especifica um bloco de script que contém o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-253">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="43df6-254">Exemplo 15: usar uma opção de sessão</span><span class="sxs-lookup"><span data-stu-id="43df6-254">Example 15: Use a session option</span></span>

<span data-ttu-id="43df6-255">Este exemplo mostra como criar e usar um parâmetro **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="43df6-255">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="43df6-256">O `New-PSSessionOption` cmdlet cria um objeto de opção de sessão que faz com que a extremidade remota não verifique a autoridade de certificação, o nome canônico e as listas de revogação ao avaliar a conexão HTTPS de entrada.</span><span class="sxs-lookup"><span data-stu-id="43df6-256">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="43df6-257">O objeto **SessionOption** é salvo na `$so` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-257">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="43df6-258">A desabilitação dessas verificações é conveniente para a solução de problemas, mas, obviamente, não é segura.</span><span class="sxs-lookup"><span data-stu-id="43df6-258">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="43df6-259">O `Invoke-Command` cmdlet executa um `Get-HotFix` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="43df6-259">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="43df6-260">O parâmetro **SessionOption** recebe a `$so` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-260">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="43df6-261">Exemplo 16: gerenciar o redirecionamento de URI em um comando remoto</span><span class="sxs-lookup"><span data-stu-id="43df6-261">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="43df6-262">Este exemplo mostra como usar os parâmetros **AllowRedirection** e **SessionOption** para gerenciar o redirecionamento de URI em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-262">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

<span data-ttu-id="43df6-263">O `New-PSSessionOption` cmdlet cria um objeto **PSSessionOption** que é salvo na `$max` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-263">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="43df6-264">O comando utiliza o parâmetro **MaximumRedirection** para definir a propriedade **MaximumConnectionRedirectionCount** do objeto **PSSessionOption** como 1.</span><span class="sxs-lookup"><span data-stu-id="43df6-264">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="43df6-265">O `Invoke-Command` cmdlet executa um `Get-Mailbox` comando em um servidor remoto do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="43df6-265">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="43df6-266">O parâmetro **AllowRedirection** fornece permissão explícita para redirecionar a conexão para um ponto de extremidade alternativo.</span><span class="sxs-lookup"><span data-stu-id="43df6-266">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="43df6-267">O parâmetro **SessionOption** usa o objeto de sessão armazenado na `$max` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-267">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="43df6-268">Como resultado, se o computador remoto especificado por **conexãouri** retornar uma mensagem de redirecionamento, o PowerShell redireciona a conexão, mas se o novo destino retornar outra mensagem de redirecionamento, o valor de contagem de redirecionamento de 1 será excedido e `Invoke-Command` retornará um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="43df6-268">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="43df6-269">Exemplo 17: acessar um compartilhamento de rede em uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="43df6-269">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="43df6-270">Este exemplo mostra como acessar um compartilhamento de rede de uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43df6-270">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="43df6-271">Três computadores são usados para demonstrar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="43df6-271">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="43df6-272">Server01 é o computador local, Server02 é o computador remoto e Net03 contém o compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-272">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="43df6-273">Server01 conecta-se ao Server02 e, em seguida, o Server02 faz um segundo salto para o Net03 acessar o compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-273">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="43df6-274">Para obter mais informações sobre como a comunicação remota do PowerShell dá suporte a saltos entre computadores, consulte [tornando o segundo salto na comunicação remota do PowerShell](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span><span class="sxs-lookup"><span data-stu-id="43df6-274">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="43df6-275">A delegação necessária da CredSSP (provedor de suporte à segurança de credencial) está habilitada nas configurações do cliente no computador local e nas configurações do serviço no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-275">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="43df6-276">Para executar os comandos neste exemplo, você deve ser um membro do grupo **Administradores** no computador local e no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-276">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

<span data-ttu-id="43df6-277">O `Enable-WSManCredSSP` cmdlet habilita a delegação de CredSSP do computador local Server01 para o computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-277">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="43df6-278">O parâmetro **role** especifica o **cliente** para definir a configuração do cliente CredSSP no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-278">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="43df6-279">`New-PSSession` Cria um objeto **PSSession** para Server02 e armazena o objeto na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="43df6-279">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="43df6-280">O `Invoke-Command` cmdlet usa a `$s` variável para se conectar ao computador remoto, Server02.</span><span class="sxs-lookup"><span data-stu-id="43df6-280">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="43df6-281">O parâmetro **scriptblock** é executado `Enable-WSManCredSSP` no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-281">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="43df6-282">O parâmetro de **função** especifica **servidor** para configurar a configuração do servidor CredSSP no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-282">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="43df6-283">A `$parameters` variável contém os valores de parâmetro para se conectar ao compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-283">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="43df6-284">O `Invoke-Command` cmdlet executa um `Get-Item` comando na sessão no `$s` .</span><span class="sxs-lookup"><span data-stu-id="43df6-284">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="43df6-285">Esse comando obtém um script do `\\Net03\Scripts` compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-285">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="43df6-286">O comando usa o parâmetro de **autenticação** com um valor de **CredSSP** e o parâmetro **Credential** com um valor de **domain01\admin01**.</span><span class="sxs-lookup"><span data-stu-id="43df6-286">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01**.</span></span>

### <span data-ttu-id="43df6-287">Exemplo 18: iniciar scripts em vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="43df6-287">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="43df6-288">Este exemplo executa um script em mais de uma centena de computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-288">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="43df6-289">Para minimizar o impacto no computador local, ele se conecta a cada computador, inicia o script e, em seguida, desconecta de cada computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-289">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="43df6-290">O script continuará a ser executado nas sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="43df6-290">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="43df6-291">O comando usa `Invoke-Command` para executar o script.</span><span class="sxs-lookup"><span data-stu-id="43df6-291">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="43df6-292">O valor do parâmetro **ComputerName** é um `Get-Content` comando que obtém os nomes dos computadores remotos a partir de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="43df6-292">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="43df6-293">O parâmetro **InDisconnectedSession** desconecta as sessões assim que ele inicia o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-293">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="43df6-294">O valor do parâmetro **FilePath** é o script que `Invoke-Command` é executado em cada computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-294">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="43df6-295">O valor de **SessionOption** é uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="43df6-295">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="43df6-296">O valor de **OutputBufferingMode** é definido como **drop** e o valor de **IdleTimeout** é definido como **43,2 milhões** milissegundos (12 horas).</span><span class="sxs-lookup"><span data-stu-id="43df6-296">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="43df6-297">Para obter os resultados de comandos e scripts que são executados em sessões desconectadas, use o `Receive-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-297">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

### <span data-ttu-id="43df6-298">Exemplo 19: executar um comando em um computador remoto usando SSH</span><span class="sxs-lookup"><span data-stu-id="43df6-298">Example 19: Run a command on a remote computer using SSH</span></span>

<span data-ttu-id="43df6-299">Este exemplo mostra como executar um comando em um computador remoto usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="43df6-299">This example shows how to run a command on a remote computer using Secure Shell (SSH).</span></span> <span data-ttu-id="43df6-300">Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="43df6-300">If SSH is configured on the remote computer to prompt for passwords, then you'll get a password prompt.</span></span>
<span data-ttu-id="43df6-301">Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.</span><span class="sxs-lookup"><span data-stu-id="43df6-301">Otherwise, you'll have to use SSH key-based user authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * }
```

### <span data-ttu-id="43df6-302">Exemplo 20: executar um comando em um computador remoto usando SSH e especificar uma chave de autenticação de usuário</span><span class="sxs-lookup"><span data-stu-id="43df6-302">Example 20: Run a command on a remote computer using SSH and specify a user authentication key</span></span>

<span data-ttu-id="43df6-303">Este exemplo mostra como executar um comando em um computador remoto usando SSH e especificando um arquivo de chave para autenticação de usuário.</span><span class="sxs-lookup"><span data-stu-id="43df6-303">This example shows how to run a command on a remote computer using SSH and specifying a key file for user authentication.</span></span> <span data-ttu-id="43df6-304">Não será solicitada uma senha a menos que a autenticação de chave falhe e o computador remoto esteja configurado para permitir a autenticação de senha básica.</span><span class="sxs-lookup"><span data-stu-id="43df6-304">You won't be prompted for a password unless the key authentication fails and the remote computer is configured to allow basic password authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * } -KeyFilePath /UserA/UserAKey_rsa
```

### <span data-ttu-id="43df6-305">Exemplo 21: executar um arquivo de script em vários computadores remotos usando SSH como um trabalho</span><span class="sxs-lookup"><span data-stu-id="43df6-305">Example 21: Run a script file on multiple remote computers using SSH as a job</span></span>

<span data-ttu-id="43df6-306">Este exemplo mostra como executar um arquivo de script em vários computadores remotos usando SSH e o conjunto de parâmetros **SSHConnection** .</span><span class="sxs-lookup"><span data-stu-id="43df6-306">This example shows how to run a script file on multiple remote computers using SSH and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="43df6-307">O parâmetro **SSHConnection** usa uma matriz de tabelas de hash que contêm informações de conexão para cada computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-307">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each computer.</span></span> <span data-ttu-id="43df6-308">Este exemplo requer que os computadores remotos de destino tenham o SSH configurado para dar suporte à autenticação de usuário baseada em chave.</span><span class="sxs-lookup"><span data-stu-id="43df6-308">This example requires that the target remote computers have SSH configured to support key-based user authentication.</span></span>

```powershell
$sshConnections =
@{ HostName="WinServer1"; UserName="Domain\UserA"; KeyFilePath="C:\Users\UserA\id_rsa" },
@{ HostName="UserB@LinuxServer5"; KeyFilePath="/Users/UserB/id_rsa" }
$results = Invoke-Command -FilePath c:\Scripts\CollectEvents.ps1 -SSHConnection $sshConnections
```

## <span data-ttu-id="43df6-309">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43df6-309">PARAMETERS</span></span>

### <span data-ttu-id="43df6-310">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="43df6-310">-AllowRedirection</span></span>

<span data-ttu-id="43df6-311">Permite o redirecionamento da conexão para um URI (Uniform Resource Identifier) alternativo.</span><span class="sxs-lookup"><span data-stu-id="43df6-311">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="43df6-312">Quando você usa o parâmetro **ConnectionURI**, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="43df6-312">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="43df6-313">Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-313">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="43df6-314">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="43df6-314">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="43df6-315">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="43df6-315">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="43df6-316">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="43df6-316">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-317">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="43df6-317">-ApplicationName</span></span>

<span data-ttu-id="43df6-318">Especifica o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-318">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="43df6-319">Use esse parâmetro para especificar o nome do aplicativo quando você não estiver usando o parâmetro **conexãouri** no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-319">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="43df6-320">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-320">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="43df6-321">Se essa variável de preferência não for definida, o valor padrão será WSMAN.</span><span class="sxs-lookup"><span data-stu-id="43df6-321">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="43df6-322">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="43df6-322">This value is appropriate for most uses.</span></span> <span data-ttu-id="43df6-323">Para obter mais informações, consulte [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-323">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="43df6-324">O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-324">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="43df6-325">O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-325">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-326">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="43df6-326">-ArgumentList</span></span>

<span data-ttu-id="43df6-327">Fornece os valores de variáveis locais no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-327">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="43df6-328">As variáveis no comando são substituídas por esses valores antes do comando ser executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-328">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="43df6-329">Digite os valores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="43df6-329">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="43df6-330">Os valores são associados a variáveis na ordem em que estão listados.</span><span class="sxs-lookup"><span data-stu-id="43df6-330">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="43df6-331">O alias para **ArgumentList** é args.</span><span class="sxs-lookup"><span data-stu-id="43df6-331">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="43df6-332">Os valores no parâmetro **ArgumentList** podem ser valores reais, como 1024, ou podem ser referências a variáveis locais, como `$max` .</span><span class="sxs-lookup"><span data-stu-id="43df6-332">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="43df6-333">Para utilizar variáveis locais em um comando, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="43df6-333">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="43df6-334">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - ou - `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="43df6-334">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="43df6-335">A palavra-chave **param** lista as variáveis locais que são usadas no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-335">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="43df6-336">**ArgumentList** fornece os valores das variáveis, na ordem em que estão listadas.</span><span class="sxs-lookup"><span data-stu-id="43df6-336">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="43df6-337">Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="43df6-337">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-338">-AsJob</span><span class="sxs-lookup"><span data-stu-id="43df6-338">-AsJob</span></span>

<span data-ttu-id="43df6-339">Indica que esse cmdlet executa o comando como um trabalho em segundo plano em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-339">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="43df6-340">Use esse parâmetro para executar comandos que levam muito tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="43df6-340">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="43df6-341">Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho e, em seguida, exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-341">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="43df6-342">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="43df6-342">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="43df6-343">Para gerenciar o trabalho, use os `*-Job` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="43df6-343">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="43df6-344">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-344">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="43df6-345">O parâmetro **AsJob** é semelhante ao uso do `Invoke-Command` cmdlet para executar um `Start-Job` cmdlet remotamente.</span><span class="sxs-lookup"><span data-stu-id="43df6-345">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="43df6-346">No entanto, com **AsJob**, o trabalho é criado no computador local, embora o trabalho seja executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-346">However, with **AsJob**, the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="43df6-347">Os resultados do trabalho remoto são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-347">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="43df6-348">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](About/about_Jobs.md) e [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-348">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-349">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="43df6-349">-Authentication</span></span>

<span data-ttu-id="43df6-350">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="43df6-350">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="43df6-351">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="43df6-351">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="43df6-352">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="43df6-352">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="43df6-353">Padrão</span><span class="sxs-lookup"><span data-stu-id="43df6-353">Default</span></span>
- <span data-ttu-id="43df6-354">Básico</span><span class="sxs-lookup"><span data-stu-id="43df6-354">Basic</span></span>
- <span data-ttu-id="43df6-355">CredSSP</span><span class="sxs-lookup"><span data-stu-id="43df6-355">Credssp</span></span>
- <span data-ttu-id="43df6-356">Digest</span><span class="sxs-lookup"><span data-stu-id="43df6-356">Digest</span></span>
- <span data-ttu-id="43df6-357">Kerberos</span><span class="sxs-lookup"><span data-stu-id="43df6-357">Kerberos</span></span>
- <span data-ttu-id="43df6-358">Negotiate</span><span class="sxs-lookup"><span data-stu-id="43df6-358">Negotiate</span></span>
- <span data-ttu-id="43df6-359">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="43df6-359">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="43df6-360">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="43df6-360">The default value is Default.</span></span>

<span data-ttu-id="43df6-361">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="43df6-361">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="43df6-362">A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="43df6-362">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="43df6-363">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="43df6-363">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="43df6-364">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-364">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="43df6-365">Para obter mais informações, consulte [provedor de suporte à segurança de credenciais](/windows/win32/secauthn/credential-security-support-provider).</span><span class="sxs-lookup"><span data-stu-id="43df6-365">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:
Accepted values: Basic, Default, Credssp, Digest, Kerberos, Negotiate, NegotiateWithImplicitCredential

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-366">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="43df6-366">-CertificateThumbprint</span></span>

<span data-ttu-id="43df6-367">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="43df6-367">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="43df6-368">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="43df6-368">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="43df6-369">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="43df6-369">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="43df6-370">Eles podem ser mapeados apenas para contas de usuário local e não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="43df6-370">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="43df6-371">Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="43df6-371">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-372">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="43df6-372">-ComputerName</span></span>

<span data-ttu-id="43df6-373">Especifica os computadores em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="43df6-373">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="43df6-374">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-374">The default is the local computer.</span></span>

<span data-ttu-id="43df6-375">Quando você usa o parâmetro **ComputerName** , o PowerShell cria uma conexão temporária que é usada somente para executar o comando especificado e, em seguida, é fechada.</span><span class="sxs-lookup"><span data-stu-id="43df6-375">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="43df6-376">Se você precisar de uma conexão persistente, use o parâmetro **Session** .</span><span class="sxs-lookup"><span data-stu-id="43df6-376">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="43df6-377">Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="43df6-377">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="43df6-378">Para especificar o computador local, digite o nome do computador, localhost ou um ponto ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="43df6-378">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="43df6-379">Para usar um endereço IP no valor de **ComputerName**, o comando deve incluir o parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="43df6-379">To use an IP address in the value of **ComputerName**, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="43df6-380">O computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista de **TrustedHosts** WinRM do computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-380">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="43df6-381">Para obter instruções para adicionar um nome de computador à lista **TrustedHosts** , consulte [como adicionar um computador à lista de hosts confiáveis](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span><span class="sxs-lookup"><span data-stu-id="43df6-381">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="43df6-382">No Windows Vista e versões posteriores do sistema operacional Windows, para incluir o computador local no valor **ComputerName**, você deve executar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="43df6-382">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName**, you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-383">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="43df6-383">-ConfigurationName</span></span>

<span data-ttu-id="43df6-384">Especifica a configuração de sessão que é usada para a nova **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="43df6-384">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="43df6-385">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-385">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="43df6-386">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="43df6-386">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="43df6-387">Quando usado com SSH, esse parâmetro especifica o subsistema a ser usado no destino, conforme definido em `sshd_config` .</span><span class="sxs-lookup"><span data-stu-id="43df6-387">When used with SSH, this parameter specifies the subsystem to use on the target as defined in `sshd_config`.</span></span> <span data-ttu-id="43df6-388">O valor padrão para SSH é o `powershell` subsistema.</span><span class="sxs-lookup"><span data-stu-id="43df6-388">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="43df6-389">A configuração da sessão para uma sessão está localizada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-389">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="43df6-390">Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="43df6-390">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="43df6-391">O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-391">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="43df6-392">Se essa variável de preferência não for definida, o padrão será **Microsoft. PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="43df6-392">If this preference variable isn't set, the default is **Microsoft.PowerShell**.</span></span> <span data-ttu-id="43df6-393">Para obter mais informações, consulte [about_Preference_Variables](about/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-393">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-394">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="43df6-394">-ConnectionUri</span></span>

<span data-ttu-id="43df6-395">Especifica um URI (Uniform Resource Identifier) que define o ponto de extremidade de conexão da sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-395">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="43df6-396">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="43df6-396">The URI must be fully qualified.</span></span>

<span data-ttu-id="43df6-397">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="43df6-397">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="43df6-398">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="43df6-398">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="43df6-399">Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL** e **Port** para especificar os valores de URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-399">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="43df6-400">Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43df6-400">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="43df6-401">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com as portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43df6-401">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="43df6-402">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43df6-402">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="43df6-403">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-403">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-404">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="43df6-404">-ContainerId</span></span>

<span data-ttu-id="43df6-405">Especifica uma matriz de IDs de contêiner.</span><span class="sxs-lookup"><span data-stu-id="43df6-405">Specifies an array of container IDs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-406">-Credential</span><span class="sxs-lookup"><span data-stu-id="43df6-406">-Credential</span></span>

<span data-ttu-id="43df6-407">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="43df6-407">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="43df6-408">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="43df6-408">The default is the current user.</span></span>

<span data-ttu-id="43df6-409">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-409">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="43df6-410">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="43df6-410">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="43df6-411">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="43df6-411">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="43df6-412">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="43df6-412">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-413">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="43df6-413">-EnableNetworkAccess</span></span>

<span data-ttu-id="43df6-414">Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="43df6-414">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="43df6-415">O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-415">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="43df6-416">Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-416">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="43df6-417">Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-417">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="43df6-418">Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como ponto ( `.` ), localhost ou o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="43df6-418">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="43df6-419">Por padrão, as sessões de loopback são criadas usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-419">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="43df6-420">O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="43df6-420">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="43df6-421">Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="43df6-421">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="43df6-422">Você pode permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro de **autenticação** , que delega as credenciais de sessão para outros computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-422">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="43df6-423">Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, que são aquelas criadas usando **EnableNetworkAccess**, podem ser reconectadas somente do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="43df6-423">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess**, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="43df6-424">Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-424">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="43df6-425">Para obter mais informações, consulte `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="43df6-425">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="43df6-426">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-426">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-427">-FilePath</span><span class="sxs-lookup"><span data-stu-id="43df6-427">-FilePath</span></span>

<span data-ttu-id="43df6-428">Especifica um script local que esse cmdlet executa em um ou mais computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43df6-428">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="43df6-429">Insira o caminho e o nome de arquivo do script ou redirecione um caminho de script para `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="43df6-429">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="43df6-430">O script deve existir no computador local ou em um diretório que o computador local possa acessar.</span><span class="sxs-lookup"><span data-stu-id="43df6-430">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="43df6-431">Use **ArgumentList** para especificar os valores dos parâmetros no script.</span><span class="sxs-lookup"><span data-stu-id="43df6-431">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="43df6-432">Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script, transmite o bloco de script para o computador remoto e o executa no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-432">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId, FilePathSSHHost, FilePathSSHHostHash
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-433">-HideComputerName</span><span class="sxs-lookup"><span data-stu-id="43df6-433">-HideComputerName</span></span>

<span data-ttu-id="43df6-434">Indica que esse cmdlet omite o nome do computador de cada objeto da exibição de saída.</span><span class="sxs-lookup"><span data-stu-id="43df6-434">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="43df6-435">Por padrão, o nome do computador que gerou o objeto aparece na exibição.</span><span class="sxs-lookup"><span data-stu-id="43df6-435">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="43df6-436">Este parâmetro afeta somente a exibição de saída.</span><span class="sxs-lookup"><span data-stu-id="43df6-436">This parameter affects only the output display.</span></span> <span data-ttu-id="43df6-437">Ele não altera o objeto.</span><span class="sxs-lookup"><span data-stu-id="43df6-437">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases: HCN

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-438">-HostName</span><span class="sxs-lookup"><span data-stu-id="43df6-438">-HostName</span></span>

<span data-ttu-id="43df6-439">Especifica uma matriz de nomes de computador para uma conexão baseada em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="43df6-439">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="43df6-440">Isso é semelhante ao parâmetro **ComputerName** , exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows.</span><span class="sxs-lookup"><span data-stu-id="43df6-440">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="43df6-441">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-441">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-442">-InDisconnectedSession</span><span class="sxs-lookup"><span data-stu-id="43df6-442">-InDisconnectedSession</span></span>

<span data-ttu-id="43df6-443">Indica que este cmdlet executa um comando ou script em uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="43df6-443">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="43df6-444">Quando você usa o parâmetro **InDisconnectedSession** , o `Invoke-Command` cria uma sessão persistente em cada computador remoto, inicia o comando especificado pelo parâmetro **scriptblock** ou **FilePath** e, em seguida, desconecta-se da sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-444">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="43df6-445">Os comandos continuam a ser executados nas sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="43df6-445">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="43df6-446">O **InDisconnectedSession** permite que você execute comandos sem manter uma conexão com as sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="43df6-446">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="43df6-447">E, como a sessão é desconectada antes de qualquer resultado ser retornado, o **InDisconnectedSession** garante que todos os resultados de comando sejam retornados para a sessão reconectada, em vez de serem divididos entre as sessões.</span><span class="sxs-lookup"><span data-stu-id="43df6-447">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="43df6-448">Você não pode usar **InDisconnectedSession** com o parâmetro **Session** ou o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="43df6-448">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="43df6-449">Comandos que usam **InDisconnectedSession** retornam um objeto **PSSession** que representa a sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="43df6-449">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="43df6-450">Eles não retornam a saída do comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-450">They don't return the command output.</span></span> <span data-ttu-id="43df6-451">Para se conectar à sessão desconectada, use os `Connect-PSSession` `Receive-PSSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="43df6-451">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="43df6-452">Para obter os resultados dos comandos que foram executados na sessão, use o `Receive-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df6-452">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="43df6-453">Para executar comandos que geram saída em uma sessão desconectada, defina o valor da opção de sessão **OutputBufferingMode** como **drop**.</span><span class="sxs-lookup"><span data-stu-id="43df6-453">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop**.</span></span> <span data-ttu-id="43df6-454">Se você pretende se conectar à sessão desconectada, defina o tempo limite ocioso na sessão para que ela forneça tempo suficiente para que você se conecte antes de excluir a sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-454">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="43df6-455">Você pode definir o modo de buffer de saída e o tempo limite ocioso no parâmetro **SessionOption** ou na `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="43df6-455">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="43df6-456">Para obter mais informações sobre as opções de sessão, consulte `New-PSSessionOption` e [about_Preference_Variables](./about/about_preference_variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-456">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="43df6-457">Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-457">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="43df6-458">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-458">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-459">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43df6-459">-InputObject</span></span>

<span data-ttu-id="43df6-460">Especifica a entrada para o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-460">Specifies input to the command.</span></span> <span data-ttu-id="43df6-461">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="43df6-461">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="43df6-462">Ao usar o parâmetro **InputObject** , use a `$Input` variável automática no valor do parâmetro **scriptblock** para representar os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="43df6-462">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-463">-JobName</span><span class="sxs-lookup"><span data-stu-id="43df6-463">-JobName</span></span>

<span data-ttu-id="43df6-464">Especifica um nome amigável para o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="43df6-464">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="43df6-465">Por padrão, os trabalhos são nomeados `Job<n>` , em que `<n>` é um número ordinal.</span><span class="sxs-lookup"><span data-stu-id="43df6-465">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="43df6-466">Se você usar o parâmetro **JobName** em um comando, o comando será executado como um trabalho e `Invoke-Command` retornará um objeto de trabalho, mesmo que você não inclua **AsJob** no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-466">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="43df6-467">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-467">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-468">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="43df6-468">-KeyFilePath</span></span>

<span data-ttu-id="43df6-469">Especifica um caminho de arquivo de chave usado pelo Secure Shell (SSH) para autenticar um usuário em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-469">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="43df6-470">O SSH permite que a autenticação do usuário seja executada por meio de chaves públicas e privadas como uma alternativa à autenticação de senha básica.</span><span class="sxs-lookup"><span data-stu-id="43df6-470">SSH allows user authentication to be performed via private and public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="43df6-471">Se o computador remoto estiver configurado para autenticação de chave, esse parâmetro poderá ser usado para fornecer a chave que identifica o usuário.</span><span class="sxs-lookup"><span data-stu-id="43df6-471">If the remote computer is configured for key authentication, then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="43df6-472">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-472">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-473">-NoNewScope</span><span class="sxs-lookup"><span data-stu-id="43df6-473">-NoNewScope</span></span>

<span data-ttu-id="43df6-474">Indica que esse cmdlet executa o comando especificado no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="43df6-474">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="43df6-475">Por padrão, `Invoke-Command` o executa comandos em seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="43df6-475">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="43df6-476">Esse parâmetro é válido somente em comandos que são executados na sessão atual, ou seja, comandos que omitem ambos os parâmetros **ComputerName** e **Session**.</span><span class="sxs-lookup"><span data-stu-id="43df6-476">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="43df6-477">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-477">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-478">-Port</span><span class="sxs-lookup"><span data-stu-id="43df6-478">-Port</span></span>

<span data-ttu-id="43df6-479">Especifica a porta de rede no computador remoto que é usada para este comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-479">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="43df6-480">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-480">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="43df6-481">As portas padrão são 5985 (porta do WinRM para HTTP) e 5986 (porta do WinRM para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="43df6-481">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="43df6-482">Antes de usar uma porta alternativa, configure o ouvinte WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="43df6-482">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="43df6-483">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="43df6-483">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="43df6-484">Não use o parâmetro **Port** , a menos que você precise.</span><span class="sxs-lookup"><span data-stu-id="43df6-484">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="43df6-485">A porta que está definida no comando se aplica a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="43df6-485">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="43df6-486">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="43df6-486">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, FilePathComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-487">-RemoteDebug</span><span class="sxs-lookup"><span data-stu-id="43df6-487">-RemoteDebug</span></span>

<span data-ttu-id="43df6-488">Usado para executar o comando chamado no modo de depuração na sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43df6-488">Used to run the invoked command in debug mode in the remote PowerShell session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-489">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="43df6-489">-RunAsAdministrator</span></span>

<span data-ttu-id="43df6-490">Indica que esse cmdlet invoca um comando como administrador.</span><span class="sxs-lookup"><span data-stu-id="43df6-490">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-491">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="43df6-491">-ScriptBlock</span></span>

<span data-ttu-id="43df6-492">Especifica os comandos a serem executados.</span><span class="sxs-lookup"><span data-stu-id="43df6-492">Specifies the commands to run.</span></span> <span data-ttu-id="43df6-493">Coloque os comandos entre chaves `{ }` para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="43df6-493">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="43df6-494">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="43df6-494">This parameter is required.</span></span>

<span data-ttu-id="43df6-495">Por padrão, todas as variáveis no comando são avaliadas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-495">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="43df6-496">Para incluir variáveis locais no comando, use **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="43df6-496">To include local variables in the command, use **ArgumentList**.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, SSHHost, ContainerId, SSHHostHashParam
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-497">-Sessão</span><span class="sxs-lookup"><span data-stu-id="43df6-497">-Session</span></span>

<span data-ttu-id="43df6-498">Especifica uma matriz de sessões em que esse cmdlet executa o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-498">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="43df6-499">Insira uma variável que contenha objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `New-PSSession` `Get-PSSession` comando ou.</span><span class="sxs-lookup"><span data-stu-id="43df6-499">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="43df6-500">Quando você cria uma **PSSession**, o PowerShell estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-500">When you create a **PSSession**, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="43df6-501">Use uma **PSSession** para executar uma série de comandos relacionados que compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="43df6-501">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="43df6-502">Para executar um único comando ou uma série de comandos não relacionados, use o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="43df6-502">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="43df6-503">Para obter mais informações, consulte [about_PSSessions](./About/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-503">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: FilePathRunspace, Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-504">-SESSIONNAME</span><span class="sxs-lookup"><span data-stu-id="43df6-504">-SessionName</span></span>

<span data-ttu-id="43df6-505">Especifica um nome amigável para uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="43df6-505">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="43df6-506">Você pode usar o nome para fazer referência à sessão em comandos subsequentes, como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-506">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="43df6-507">Esse parâmetro é válido somente com o parâmetro **InDisconnectedSession**.</span><span class="sxs-lookup"><span data-stu-id="43df6-507">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="43df6-508">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-508">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-509">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="43df6-509">-SessionOption</span></span>

<span data-ttu-id="43df6-510">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-510">Specifies advanced options for the session.</span></span> <span data-ttu-id="43df6-511">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-511">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="43df6-512">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se ele estiver definido.</span><span class="sxs-lookup"><span data-stu-id="43df6-512">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="43df6-513">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-513">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="43df6-514">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-514">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="43df6-515">No entanto, eles não têm precedência sobre os valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-515">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="43df6-516">Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="43df6-516">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="43df6-517">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-517">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="43df6-518">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="43df6-518">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-519">-SSHConnection</span><span class="sxs-lookup"><span data-stu-id="43df6-519">-SSHConnection</span></span>

<span data-ttu-id="43df6-520">Esse parâmetro usa uma matriz de tabelas de hash em que cada tabela de hash contém um ou mais parâmetros de conexão necessários para estabelecer uma conexão de Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="43df6-520">This parameter takes an array of hash tables where each hash table contains one or more connection parameters needed to establish a Secure Shell (SSH) connection.</span></span> <span data-ttu-id="43df6-521">O parâmetro **SSHConnection** é útil para criar várias sessões em que cada sessão requer informações de conexão diferentes.</span><span class="sxs-lookup"><span data-stu-id="43df6-521">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="43df6-522">A tabela de hash tem os seguintes membros:</span><span class="sxs-lookup"><span data-stu-id="43df6-522">The hashtable has the following members:</span></span>

- <span data-ttu-id="43df6-523">**Nome do** **computador** (ou hostname)</span><span class="sxs-lookup"><span data-stu-id="43df6-523">**ComputerName** (or **HostName**)</span></span>
- <span data-ttu-id="43df6-524">**Porta**</span><span class="sxs-lookup"><span data-stu-id="43df6-524">**Port**</span></span>
- <span data-ttu-id="43df6-525">**UserName**</span><span class="sxs-lookup"><span data-stu-id="43df6-525">**UserName**</span></span>
- <span data-ttu-id="43df6-526">**KeyFilePath** (ou **IdentityFilePath**)</span><span class="sxs-lookup"><span data-stu-id="43df6-526">**KeyFilePath** (or **IdentityFilePath**)</span></span>

<span data-ttu-id="43df6-527">**ComputerName** (ou **hostname**) é o único par chave-valor necessário.</span><span class="sxs-lookup"><span data-stu-id="43df6-527">**ComputerName** (or **HostName**) is the only key-value pair that is required.</span></span>

<span data-ttu-id="43df6-528">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-528">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam, FilePathSSHHostHash
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-529">-SSHTransport</span><span class="sxs-lookup"><span data-stu-id="43df6-529">-SSHTransport</span></span>

<span data-ttu-id="43df6-530">Indica que a conexão remota é estabelecida usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="43df6-530">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="43df6-531">Por padrão, o PowerShell usa o Windows WinRM para se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-531">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="43df6-532">Essa opção força o PowerShell a usar o parâmetro **hostname** para estabelecer uma conexão remota com base em SSH.</span><span class="sxs-lookup"><span data-stu-id="43df6-532">This switch forces PowerShell to use the **HostName** parameter for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="43df6-533">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-533">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-534">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="43df6-534">-ThrottleLimit</span></span>

<span data-ttu-id="43df6-535">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-535">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="43df6-536">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="43df6-536">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="43df6-537">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-537">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-538">-UserName</span><span class="sxs-lookup"><span data-stu-id="43df6-538">-UserName</span></span>

<span data-ttu-id="43df6-539">Especifica o nome de usuário para a conta usada para executar um comando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-539">Specifies the username for the account used to run a command on the remote computer.</span></span> <span data-ttu-id="43df6-540">O método de autenticação de usuário depende de como o Secure Shell (SSH) é configurado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-540">The user authentication method depends on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="43df6-541">Se o SSH estiver configurado para autenticação de senha básica, a senha do usuário será solicitada.</span><span class="sxs-lookup"><span data-stu-id="43df6-541">If SSH is configured for basic password authentication, then you'll be prompted for the user password.</span></span>

<span data-ttu-id="43df6-542">Se o SSH estiver configurado para autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro **keyFilePath** e nenhum prompt de senha ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="43df6-542">If SSH is configured for key-based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt occurs.</span></span> <span data-ttu-id="43df6-543">Se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro **keyFilePath** não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="43df6-543">If the client user key file is located in an SSH known location, then the **KeyFilePath** parameter isn't needed for key-based authentication, and user authentication occurs automatically based on the username.</span></span> <span data-ttu-id="43df6-544">Para obter mais informações, consulte a documentação do SSH da sua plataforma sobre a autenticação de usuário baseada em chave.</span><span class="sxs-lookup"><span data-stu-id="43df6-544">For more information, see your platform's SSH documentation about key-based user authentication.</span></span>

<span data-ttu-id="43df6-545">Esse não é um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="43df6-545">This isn't a required parameter.</span></span> <span data-ttu-id="43df6-546">Se o parâmetro **username** não for especificado, o nome de usuário conectado no momento será usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="43df6-546">If the **UserName** parameter isn't specified, then the current logged on username is used for the connection.</span></span>

<span data-ttu-id="43df6-547">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-547">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-548">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="43df6-548">-UseSSL</span></span>

<span data-ttu-id="43df6-549">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-549">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="43df6-550">Por padrão, o SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="43df6-550">By default, SSL isn't used.</span></span>

<span data-ttu-id="43df6-551">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="43df6-551">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="43df6-552">O parâmetro **UseSSL** é uma proteção adicional que envia os dados por um https, em vez de http.</span><span class="sxs-lookup"><span data-stu-id="43df6-552">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="43df6-553">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="43df6-553">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-554">-VMId</span><span class="sxs-lookup"><span data-stu-id="43df6-554">-VMId</span></span>

<span data-ttu-id="43df6-555">Especifica uma matriz de IDs de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="43df6-555">Specifies an array of IDs of virtual machines.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-556">-VMName</span><span class="sxs-lookup"><span data-stu-id="43df6-556">-VMName</span></span>

<span data-ttu-id="43df6-557">Especifica uma matriz de nomes de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="43df6-557">Specifies an array of names of virtual machines.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-558">-Subsistema</span><span class="sxs-lookup"><span data-stu-id="43df6-558">-Subsystem</span></span>

<span data-ttu-id="43df6-559">Especifica o subsistema SSH usado para a nova **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="43df6-559">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="43df6-560">Isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config.</span><span class="sxs-lookup"><span data-stu-id="43df6-560">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="43df6-561">O subsistema inicia uma versão específica do PowerShell com parâmetros predefinidos.</span><span class="sxs-lookup"><span data-stu-id="43df6-561">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="43df6-562">Se o subsistema especificado não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="43df6-562">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="43df6-563">Se esse parâmetro não for usado, o padrão será o subsistema ' PowerShell '.</span><span class="sxs-lookup"><span data-stu-id="43df6-563">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df6-564">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43df6-564">CommonParameters</span></span>

<span data-ttu-id="43df6-565">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43df6-565">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43df6-566">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43df6-566">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43df6-567">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="43df6-567">INPUTS</span></span>

### <span data-ttu-id="43df6-568">System. Management. Automation. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="43df6-568">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="43df6-569">É possível canalizar um comando em um bloco de script para `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="43df6-569">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="43df6-570">Use a `$Input` variável automática para representar os objetos de entrada no comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-570">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="43df6-571">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="43df6-571">OUTPUTS</span></span>

### <span data-ttu-id="43df6-572">System. Management. Automation. PSRemotingJob, System. Management. Automation. Runspaces. PSSession ou a saída do comando invocado</span><span class="sxs-lookup"><span data-stu-id="43df6-572">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="43df6-573">Esse cmdlet retorna um objeto de trabalho, se você usar o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="43df6-573">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="43df6-574">Se você especificar o parâmetro **InDisconnectedSession** , `Invoke-Command` retornará um objeto **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="43df6-574">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="43df6-575">Caso contrário, ele retorna a saída do comando invocado, que é o valor do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="43df6-575">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="43df6-576">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="43df6-576">NOTES</span></span>

<span data-ttu-id="43df6-577">No Windows Vista e versões posteriores do sistema operacional Windows, para usar o parâmetro **ComputerName** do `Invoke-Command` para executar um comando no computador local, você deve executar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="43df6-577">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="43df6-578">Quando você executa comandos em vários computadores, o PowerShell se conecta aos computadores na ordem em que aparecem na lista.</span><span class="sxs-lookup"><span data-stu-id="43df6-578">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="43df6-579">No entanto, a saída do comando é exibida na ordem em que ela é recebida dos computadores remotos, o que pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="43df6-579">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="43df6-580">Os erros resultantes do comando `Invoke-Command` executado são incluídos nos resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="43df6-580">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="43df6-581">Erros que poderiam ser erros de finalização em um comando local são tratados como erros de não finalização em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="43df6-581">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="43df6-582">Essa estratégia garante que os erros de encerramento em um computador não fechem o comando em todos os computadores nos quais ele é executado.</span><span class="sxs-lookup"><span data-stu-id="43df6-582">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="43df6-583">Essa prática é utilizada mesmo quando um comando remoto é executado em um único computador.</span><span class="sxs-lookup"><span data-stu-id="43df6-583">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="43df6-584">Se o computador remoto não estiver em um domínio no qual o computador local confia, talvez o computador não consiga autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="43df6-584">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="43df6-585">Para adicionar o computador remoto à lista de hosts confiáveis no WS-Management, use o seguinte comando no `WSMAN` provedor, em que `<Remote-Computer-Name>` é o nome do computador remoto:</span><span class="sxs-lookup"><span data-stu-id="43df6-585">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="43df6-586">Quando você desconecta uma **PSSession** usando o parâmetro **InDisconnectedSession** , o estado da sessão é **desconectado** e a disponibilidade é **nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="43df6-586">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None**.</span></span> <span data-ttu-id="43df6-587">O valor da propriedade **State** é relativo a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43df6-587">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="43df6-588">Um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43df6-588">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="43df6-589">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="43df6-589">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="43df6-590">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="43df6-590">It might be connected to a different session.</span></span> <span data-ttu-id="43df6-591">Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.</span><span class="sxs-lookup"><span data-stu-id="43df6-591">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="43df6-592">Um valor **Availability** de **None** indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-592">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="43df6-593">Um valor de **ocupado** indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="43df6-593">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="43df6-594">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="43df6-594">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="43df6-595">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="43df6-595">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

<span data-ttu-id="43df6-596">Os parâmetros **hostname** e **SSHConnection** foram incluídos a partir do PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="43df6-596">The **HostName** and **SSHConnection** parameters were included starting with PowerShell 6.0.</span></span> <span data-ttu-id="43df6-597">Elas foram adicionadas para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="43df6-597">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="43df6-598">O PowerShell e o SSH têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funciona nessas plataformas em que o PowerShell e o SSH estão instalados e configurados.</span><span class="sxs-lookup"><span data-stu-id="43df6-598">PowerShell and SSH are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting works over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="43df6-599">Isso é separado da somente comunicação remota do Windows anterior que é baseada no WinRM e que muitos dos recursos e limitações específicos do WinRM não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="43df6-599">This is separate from the previous Windows only remoting that is based on WinRM and many of the WinRM specific features and limitations don't apply.</span></span> <span data-ttu-id="43df6-600">Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="43df6-600">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="43df6-601">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="43df6-601">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="43df6-602">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="43df6-602">RELATED LINKS</span></span>

[<span data-ttu-id="43df6-603">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="43df6-603">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="43df6-604">about_Remote</span><span class="sxs-lookup"><span data-stu-id="43df6-604">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="43df6-605">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="43df6-605">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="43df6-606">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="43df6-606">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="43df6-607">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="43df6-607">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="43df6-608">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="43df6-608">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="43df6-609">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df6-609">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="43df6-610">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df6-610">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="43df6-611">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df6-611">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="43df6-612">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="43df6-612">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="43df6-613">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df6-613">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="43df6-614">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df6-614">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="43df6-615">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="43df6-615">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

