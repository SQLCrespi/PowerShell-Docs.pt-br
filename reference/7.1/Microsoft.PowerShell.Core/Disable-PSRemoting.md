---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 82db14f6819a003f4f51a35844a9fcce7a146f03
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194777"
---
# <span data-ttu-id="486dc-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="486dc-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="486dc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="486dc-104">SYNOPSIS</span></span>
<span data-ttu-id="486dc-105">Impede que os pontos de extremidade do PowerShell recebam conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="486dc-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="486dc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="486dc-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="486dc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="486dc-107">DESCRIPTION</span></span>

<span data-ttu-id="486dc-108">O `Disable-PSRemoting` cmdlet bloqueia o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell versão 6 e superiores no computador local.</span><span class="sxs-lookup"><span data-stu-id="486dc-108">The `Disable-PSRemoting` cmdlet blocks remote access to all PowerShell version 6 and greater session endpoint configurations on the local computer.</span></span> <span data-ttu-id="486dc-109">Ele não afeta as configurações de ponto de extremidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-109">It does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="486dc-110">Para desabilitar as configurações de ponto de extremidade de sessão do Windows PowerShell, execute `Disable-PSRemoting` o comando de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-110">To disable Windows PowerShell session endpoint configurations, run `Disable-PSRemoting` command from within a Windows PowerShell session.</span></span>

<span data-ttu-id="486dc-111">Para reabilitar o acesso remoto a todas as configurações do PowerShell versão 6 e superiores de ponto de extremidade de sessão, use o `Enable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="486dc-111">To re-enable remote access to all PowerShell version 6 and greater session endpoint configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="486dc-112">Para reabilitar o acesso remoto a todas as configurações de ponto de extremidade de sessão do Windows PowerShell, execute `Enable-PSRemoting` de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-112">To re-enable remote access to all Windows PowerShell session endpoint configurations, run `Enable-PSRemoting` from within a Windows PowerShell session.</span></span>

> [!NOTE]
> <span data-ttu-id="486dc-113">Se você quiser desabilitar todo o acesso remoto do PowerShell para um computador local do Windows, deverá executar esse comando de um dentro do PowerShell versão 6 ou superior e de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-113">If you want to disable all PowerShell remote access to a local Windows machine, you must run this command both from a within PowerShell version 6 or greater session and from within a Windows PowerShell session.</span></span> <span data-ttu-id="486dc-114">Por padrão, o Windows PowerShell é instalado em todas as máquinas Windows.</span><span class="sxs-lookup"><span data-stu-id="486dc-114">Windows PowerShell is installed on all Windows machines by default.</span></span>

<span data-ttu-id="486dc-115">Para desabilitar e reabilitar o acesso remoto a configurações de ponto de extremidade de sessão específicas, use os `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="486dc-115">To disable and re-enable remote access to specific session endpoint configurations, use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="486dc-116">Para definir configurações de acesso específicas de pontos de extremidade individuais, use o `Set-PSSessionConfiguration` cmdlet junto com o parâmetro **AccessMode** .</span><span class="sxs-lookup"><span data-stu-id="486dc-116">To set specific access configurations of individual endpoints, use the `Set-PSSessionConfiguration` cmdlet along with the **AccessMode** parameter.</span></span> <span data-ttu-id="486dc-117">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="486dc-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="486dc-118">Mesmo após a execução `Disable-PSRemoting` , você ainda poderá fazer conexões de loopback no computador local.</span><span class="sxs-lookup"><span data-stu-id="486dc-118">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="486dc-119">Uma conexão de auto-retorno é uma sessão remota do PowerShell que se origina do e se conecta ao mesmo computador local.</span><span class="sxs-lookup"><span data-stu-id="486dc-119">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="486dc-120">As sessões remotas de fontes externas permanecem bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="486dc-120">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="486dc-121">Para conexões de loopback, você deve usar credenciais implícitas ao longo do parâmetro **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="486dc-121">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="486dc-122">Para obter mais informações sobre conexões de loopback, consulte [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="486dc-122">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="486dc-123">Esse cmdlet só está disponível na plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="486dc-123">This cmdlet is only available on the Windows platform.</span></span> <span data-ttu-id="486dc-124">Ele não está disponível nas versões Linux ou macOS do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-124">It is not available on Linux or macOS versions of PowerShell.</span></span> <span data-ttu-id="486dc-125">Para executar esse cmdlet, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="486dc-125">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="486dc-126">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="486dc-126">EXAMPLES</span></span>

### <span data-ttu-id="486dc-127">Exemplo 1: impedir o acesso remoto a todas as configurações de sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="486dc-127">Example 1: Prevent remote access to all PowerShell session configurations</span></span>

<span data-ttu-id="486dc-128">Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-128">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="486dc-129">Exemplo 2: impedir o acesso remoto a todas as configurações de sessão do PowerShell sem prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="486dc-129">Example 2: Prevent remote access to all PowerShell session configurations without confirmation prompt</span></span>

<span data-ttu-id="486dc-130">Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador sem avisar.</span><span class="sxs-lookup"><span data-stu-id="486dc-130">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="486dc-131">Exemplo 3: efeitos da execução deste cmdlet</span><span class="sxs-lookup"><span data-stu-id="486dc-131">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="486dc-132">Este exemplo mostra o efeito de usar o `Disable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="486dc-132">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="486dc-133">Para executar essa sequência de comandos, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="486dc-133">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="486dc-134">Depois de desabilitar as configurações de sessões, o `New-PSSession` cmdlet tenta criar uma sessão remota para o computador local (também conhecido como "Loopback").</span><span class="sxs-lookup"><span data-stu-id="486dc-134">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="486dc-135">Como o acesso remoto está desabilitado no computador local, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="486dc-135">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### <span data-ttu-id="486dc-136">Exemplo 4: efeitos da execução deste cmdlet e Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="486dc-136">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="486dc-137">Este exemplo mostra o efeito nas configurações de sessão do usando os `Disable-PSRemoting` `Enable-PSRemoting` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="486dc-137">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="486dc-138">`Disable-PSRemoting` é usado para desabilitar o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-138">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="486dc-139">O parâmetro **Force** suprime todos os prompts de usuário.</span><span class="sxs-lookup"><span data-stu-id="486dc-139">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="486dc-140">Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-140">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="486dc-141">A saída mostra que todos os usuários remotos com um token de rede têm acesso negado às configurações do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="486dc-141">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="486dc-142">O grupo de administradores no computador local tem permissão para acessar as configurações do ponto de extremidade, desde que eles estejam se conectando localmente (também conhecido como loopback) e usando credenciais implícitas.</span><span class="sxs-lookup"><span data-stu-id="486dc-142">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

<span data-ttu-id="486dc-143">O `Enable-PSRemoting` cmdlet habilita novamente o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-143">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="486dc-144">O parâmetro **Force** suprime todos os prompts do usuário e reinicia o serviço WinRM sem avisar.</span><span class="sxs-lookup"><span data-stu-id="486dc-144">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="486dc-145">A nova saída mostra que os descritores de segurança **AccessDenied** foram removidos de todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="486dc-145">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="486dc-146">Exemplo 5: conexões de loopback com configurações de ponto de extremidade de sessão desabilitadas</span><span class="sxs-lookup"><span data-stu-id="486dc-146">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="486dc-147">Este exemplo demonstra como as configurações de ponto de extremidade estão desabilitadas e mostra como fazer uma conexão de loopback bem-sucedida para um ponto de extremidade desabilitado.</span><span class="sxs-lookup"><span data-stu-id="486dc-147">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="486dc-148">`Disable-PSRemoting` desabilita todas as configurações de ponto de extremidade de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-148">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="486dc-149">O primeiro uso de `New-PSSession` tentativas para criar uma sessão remota para o computador local.</span><span class="sxs-lookup"><span data-stu-id="486dc-149">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="486dc-150">O parâmetro **ConfigurationName** é usado para especificar um ponto de extremidade desabilitado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-150">The **ConfigurationName** parameter is used to specify a disabled PowerShell endpoint.</span></span> <span data-ttu-id="486dc-151">As credenciais são passadas explicitamente para o comando por meio do parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="486dc-151">Credentials are explicitly passed to the command through the **Credential** parameter.</span></span> <span data-ttu-id="486dc-152">Esse tipo de conexão passa pela pilha de rede e não é um loopback.</span><span class="sxs-lookup"><span data-stu-id="486dc-152">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="486dc-153">Consequentemente, a tentativa de conexão com o ponto de extremidade desabilitado falha com um erro de **acesso negado** .</span><span class="sxs-lookup"><span data-stu-id="486dc-153">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="486dc-154">O segundo uso do `New-PSSession` também tenta criar uma sessão remota para o computador local.</span><span class="sxs-lookup"><span data-stu-id="486dc-154">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="486dc-155">Nesse caso, ele é executado com sucesso porque é uma conexão de loopback que ignora a pilha de rede.</span><span class="sxs-lookup"><span data-stu-id="486dc-155">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="486dc-156">Uma conexão de loopback é criada quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="486dc-156">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="486dc-157">O nome do computador ao qual se conectar é ' localhost '.</span><span class="sxs-lookup"><span data-stu-id="486dc-157">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="486dc-158">Nenhuma credencial é passada.</span><span class="sxs-lookup"><span data-stu-id="486dc-158">No credentials are passed in.</span></span> <span data-ttu-id="486dc-159">O usuário conectado no momento (credenciais implícitas) é usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="486dc-159">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="486dc-160">O parâmetro de opção **EnableNetworkAccess** é usado.</span><span class="sxs-lookup"><span data-stu-id="486dc-160">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="486dc-161">Para obter mais informações sobre conexões de loopback, consulte o documento [New-PSSession](New-PSSession.md) .</span><span class="sxs-lookup"><span data-stu-id="486dc-161">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="486dc-162">Exemplo 6: desabilitando todas as configurações de ponto de extremidade de comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="486dc-162">Example 6: Disabling all PowerShell remoting endpoint configurations</span></span>

<span data-ttu-id="486dc-163">Este exemplo demonstra como a execução do `Disable-PSRemoting` comando não afeta as configurações de ponto de extremidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-163">This example demonstrates how running the `Disable-PSRemoting` command does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="486dc-164">`Get-PSSessionConfiguration` executar no Windows PowerShell mostra todas as configurações de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="486dc-164">`Get-PSSessionConfiguration` run within Windows PowerShell shows all endpoint configurations.</span></span> <span data-ttu-id="486dc-165">Vemos que as configurações de ponto de extremidade do Windows PowerShell não estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="486dc-165">We see that the Windows PowerShell endpoint configurations are not disabled.</span></span>

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

<span data-ttu-id="486dc-166">Para desabilitar essas configurações de ponto de extremidade, o `Disable-PSRemoting` comando deve ser executado de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486dc-166">To disable these endpoint configurations, the `Disable-PSRemoting` command must be run from within a Windows PowerShell session.</span></span> <span data-ttu-id="486dc-167">Agora, `Get-PSSessionConfiguration` Executar de dentro do Windows PowerShell mostra que todas as configurações de ponto de extremidade estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="486dc-167">Now, `Get-PSSessionConfiguration` run from within Windows PowerShell shows that all endpoint configurations are disabled.</span></span>

### <span data-ttu-id="486dc-168">Exemplo 7: impedir o acesso remoto a configurações de sessão que têm descritores de segurança personalizados</span><span class="sxs-lookup"><span data-stu-id="486dc-168">Example 7: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="486dc-169">Este exemplo demonstra que o `Disable-PSRemoting` cmdlet desabilita o acesso remoto a todas as configurações de sessão que incluem configurações de sessão com descritores de segurança personalizados.</span><span class="sxs-lookup"><span data-stu-id="486dc-169">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="486dc-170">`Register-PSSessionConfiguration` cria a configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="486dc-170">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="486dc-171">O parâmetro **FilePath** especifica um arquivo de configuração de sessão que personaliza a sessão.</span><span class="sxs-lookup"><span data-stu-id="486dc-171">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="486dc-172">O parâmetro **ShowSecurityDescriptorUI dos** exibe uma caixa de diálogo que define permissões para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="486dc-172">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="486dc-173">Na caixa de diálogo permissões, criamos permissões personalizadas de acesso completo para o usuário indicado.</span><span class="sxs-lookup"><span data-stu-id="486dc-173">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="486dc-174">Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="486dc-174">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="486dc-175">A saída mostra que a configuração da sessão de **teste** permite acesso interativo e permissões especiais para o usuário indicado.</span><span class="sxs-lookup"><span data-stu-id="486dc-175">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="486dc-176">`Disable-PSRemoting` desabilita o acesso remoto a todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="486dc-176">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

<span data-ttu-id="486dc-177">Agora `Get-PSSessionConfiguration` , os `Format-Table` cmdlets e mostram que um descritor de segurança **AccessDenied** para todos os usuários de rede é adicionado a todas as configurações de sessão, incluindo a configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="486dc-177">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="486dc-178">Embora os outros descritores de segurança não sejam alterados, a descrição de segurança "network_deny_all" tem precedência.</span><span class="sxs-lookup"><span data-stu-id="486dc-178">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="486dc-179">Isso é ilustrado pela tentativa de usar `New-PSSession` o para se conectar à configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="486dc-179">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="486dc-180">Exemplo 8: reabilitar o acesso remoto para as configurações de sessão selecionadas</span><span class="sxs-lookup"><span data-stu-id="486dc-180">Example 8: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="486dc-181">Este exemplo mostra como reabilitar o acesso remoto apenas para as configurações de sessão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="486dc-181">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="486dc-182">Depois de desabilitar todas as configurações de sessão, reabilitamos uma sessão específica.</span><span class="sxs-lookup"><span data-stu-id="486dc-182">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="486dc-183">O `Set-PSSessionConfiguration` cmdlet é usado para alterar a configuração de sessão do **PowerShell. 6** .</span><span class="sxs-lookup"><span data-stu-id="486dc-183">The `Set-PSSessionConfiguration` cmdlet is used to change the **PowerShell.6** session configuration.</span></span> <span data-ttu-id="486dc-184">O parâmetro **AccessMode** com um valor de reabilitar **remotamente** o acesso remoto à configuração.</span><span class="sxs-lookup"><span data-stu-id="486dc-184">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

## <span data-ttu-id="486dc-185">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="486dc-185">PARAMETERS</span></span>

### <span data-ttu-id="486dc-186">-Confirm</span><span class="sxs-lookup"><span data-stu-id="486dc-186">-Confirm</span></span>

<span data-ttu-id="486dc-187">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="486dc-187">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="486dc-188">-Force</span><span class="sxs-lookup"><span data-stu-id="486dc-188">-Force</span></span>

<span data-ttu-id="486dc-189">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="486dc-189">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="486dc-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="486dc-190">-WhatIf</span></span>

<span data-ttu-id="486dc-191">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="486dc-191">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="486dc-192">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="486dc-192">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="486dc-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="486dc-193">CommonParameters</span></span>

<span data-ttu-id="486dc-194">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="486dc-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="486dc-195">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="486dc-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="486dc-196">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="486dc-196">INPUTS</span></span>

### <span data-ttu-id="486dc-197">Nenhum</span><span class="sxs-lookup"><span data-stu-id="486dc-197">None</span></span>

<span data-ttu-id="486dc-198">Não é possível canalizar nenhum objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="486dc-198">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="486dc-199">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="486dc-199">OUTPUTS</span></span>

### <span data-ttu-id="486dc-200">Nenhum</span><span class="sxs-lookup"><span data-stu-id="486dc-200">None</span></span>

<span data-ttu-id="486dc-201">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="486dc-201">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="486dc-202">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="486dc-202">NOTES</span></span>

- <span data-ttu-id="486dc-203">Desabilitar as configurações de sessão não desfaz todas as alterações feitas pelos `Enable-PSRemoting` `Enable-PSSessionConfiguration` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="486dc-203">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="486dc-204">Você talvez precise desfazer, manualmente, as alterações listadas a seguir.</span><span class="sxs-lookup"><span data-stu-id="486dc-204">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="486dc-205">Interrompa e desabilite o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="486dc-205">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="486dc-206">Exclua o ouvinte que aceita solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="486dc-206">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="486dc-207">Desabilite as exceções de firewall para comunicações do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="486dc-207">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="486dc-208">Restaure o valor de LocalAccountTokenFilterPolicy para 0, o que restringe o acesso remoto apenas a membros do grupo Administradores do computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-208">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

- <span data-ttu-id="486dc-209">Uma configuração de ponto de extremidade de sessão é um grupo de configurações que definem o ambiente de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="486dc-209">A session endpoint configuration is a group of settings that define the environment for a session.</span></span>
  <span data-ttu-id="486dc-210">Cada sessão que se conecta ao computador deve usar uma das configurações de ponto de extremidade de sessão registradas no computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-210">Every session that connects to the computer must use one of the session endpoint configurations that are registered on the computer.</span></span> <span data-ttu-id="486dc-211">Ao negar acesso remoto a todas as configurações de ponto de extremidade de sessão, você efetivamente impede que usuários remotos estabeleçam sessões que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="486dc-211">By denying remote access to all session endpoint configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

## <span data-ttu-id="486dc-212">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="486dc-212">RELATED LINKS</span></span>

[<span data-ttu-id="486dc-213">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="486dc-213">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="486dc-214">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="486dc-214">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="486dc-215">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="486dc-215">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="486dc-216">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="486dc-216">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="486dc-217">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="486dc-217">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="486dc-218">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="486dc-218">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="486dc-219">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="486dc-219">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="486dc-220">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="486dc-220">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

