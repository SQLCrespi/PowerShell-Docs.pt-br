---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193342"
---
# <span data-ttu-id="14dd0-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="14dd0-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="14dd0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="14dd0-104">SYNOPSIS</span></span>
<span data-ttu-id="14dd0-105">Impede que os pontos de extremidade do PowerShell recebam conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="14dd0-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="14dd0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14dd0-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="14dd0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14dd0-107">DESCRIPTION</span></span>

<span data-ttu-id="14dd0-108">O `Disable-PSRemoting` cmdlet bloqueia o acesso remoto a todas as configurações de ponto de extremidade de sessão do Windows PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-108">The `Disable-PSRemoting` cmdlet blocks remote access to all Windows PowerShell session endpoint configurations on the local computer.</span></span> <span data-ttu-id="14dd0-109">Isso inclui todos os pontos de extremidade criados pelo PowerShell 6 ou superior.</span><span class="sxs-lookup"><span data-stu-id="14dd0-109">This includes any endpoints created by PowerShell 6 or higher.</span></span>

<span data-ttu-id="14dd0-110">Para reabilitar o acesso remoto a todas as configurações de sessão, use o `Enable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14dd0-110">To re-enable remote access to all session configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="14dd0-111">Isso inclui todos os pontos de extremidade criados pelo PowerShell 6 ou superior.</span><span class="sxs-lookup"><span data-stu-id="14dd0-111">This includes any endpoints created by PowerShell 6 or higher.</span></span> <span data-ttu-id="14dd0-112">Para habilitar o acesso remoto às configurações de sessão selecionadas, use o parâmetro **AccessMode** do `Set-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14dd0-112">To enable remote access to selected session configurations, use the **AccessMode** parameter of the `Set-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="14dd0-113">Você também pode usar os `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` cmdlets e para habilitar e desabilitar as configurações de sessão para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="14dd0-113">You can also use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets to enable and disable session configurations for all users.</span></span> <span data-ttu-id="14dd0-114">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="14dd0-114">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="14dd0-115">Mesmo após a execução `Disable-PSRemoting` , você ainda poderá fazer conexões de loopback no computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-115">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="14dd0-116">Uma conexão de auto-retorno é uma sessão remota do PowerShell que se origina do e se conecta ao mesmo computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-116">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="14dd0-117">As sessões remotas de fontes externas permanecem bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="14dd0-117">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="14dd0-118">Para conexões de loopback, você deve usar credenciais implícitas ao longo do parâmetro **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-118">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="14dd0-119">Para obter mais informações sobre conexões de loopback, consulte [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="14dd0-119">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="14dd0-120">Para executar esse cmdlet, inicie o Windows PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-120">To run this cmdlet, start Windows PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="14dd0-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="14dd0-121">EXAMPLES</span></span>

### <span data-ttu-id="14dd0-122">Exemplo 1: impedir o acesso remoto a todas as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="14dd0-122">Example 1: Prevent remote access to all session configurations</span></span>

<span data-ttu-id="14dd0-123">Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-123">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="14dd0-124">Exemplo 2: impedir o acesso remoto a todas as configurações de sessão sem prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="14dd0-124">Example 2: Prevent remote access to all session configurations without confirmation prompt</span></span>

<span data-ttu-id="14dd0-125">Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador sem avisar.</span><span class="sxs-lookup"><span data-stu-id="14dd0-125">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="14dd0-126">Exemplo 3: efeitos da execução deste cmdlet</span><span class="sxs-lookup"><span data-stu-id="14dd0-126">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="14dd0-127">Este exemplo mostra o efeito de usar o `Disable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14dd0-127">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="14dd0-128">Para executar essa sequência de comandos, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-128">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="14dd0-129">Depois de desabilitar as configurações de sessões, o `New-PSSession` cmdlet tenta criar uma sessão remota para o computador local (também conhecido como "Loopback").</span><span class="sxs-lookup"><span data-stu-id="14dd0-129">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="14dd0-130">Como o acesso remoto está desabilitado no computador local, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="14dd0-130">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
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

### <span data-ttu-id="14dd0-131">Exemplo 4: efeitos da execução deste cmdlet e Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="14dd0-131">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="14dd0-132">Este exemplo mostra o efeito nas configurações de sessão do usando os `Disable-PSRemoting` `Enable-PSRemoting` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="14dd0-132">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="14dd0-133">`Disable-PSRemoting` é usado para desabilitar o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14dd0-133">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="14dd0-134">O parâmetro **Force** suprime todos os prompts de usuário.</span><span class="sxs-lookup"><span data-stu-id="14dd0-134">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="14dd0-135">Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-135">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="14dd0-136">A saída mostra que todos os usuários remotos com um token de rede têm acesso negado às configurações do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="14dd0-136">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="14dd0-137">O grupo de administradores no computador local tem permissão para acessar as configurações do ponto de extremidade, desde que eles estejam se conectando localmente (também conhecido como loopback) e usando credenciais implícitas.</span><span class="sxs-lookup"><span data-stu-id="14dd0-137">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="14dd0-138">O `Enable-PSRemoting` cmdlet habilita novamente o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-138">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="14dd0-139">O parâmetro **Force** suprime todos os prompts do usuário e reinicia o serviço WinRM sem avisar.</span><span class="sxs-lookup"><span data-stu-id="14dd0-139">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="14dd0-140">A nova saída mostra que os descritores de segurança **AccessDenied** foram removidos de todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-140">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="14dd0-141">Exemplo 5: conexões de loopback com configurações de ponto de extremidade de sessão desabilitadas</span><span class="sxs-lookup"><span data-stu-id="14dd0-141">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="14dd0-142">Este exemplo demonstra como as configurações de ponto de extremidade estão desabilitadas e mostra como fazer uma conexão de loopback bem-sucedida para um ponto de extremidade desabilitado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-142">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="14dd0-143">`Disable-PSRemoting` desabilita todas as configurações de ponto de extremidade de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14dd0-143">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="14dd0-144">O primeiro uso de `New-PSSession` tentativas para criar uma sessão remota para o computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-144">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="14dd0-145">Esse tipo de conexão passa pela pilha de rede e não é um loopback.</span><span class="sxs-lookup"><span data-stu-id="14dd0-145">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="14dd0-146">Consequentemente, a tentativa de conexão com o ponto de extremidade desabilitado falha com um erro de **acesso negado** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-146">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="14dd0-147">O segundo uso do `New-PSSession` também tenta criar uma sessão remota para o computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-147">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="14dd0-148">Nesse caso, ele é executado com sucesso porque é uma conexão de loopback que ignora a pilha de rede.</span><span class="sxs-lookup"><span data-stu-id="14dd0-148">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="14dd0-149">Uma conexão de loopback é criada quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="14dd0-149">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="14dd0-150">O nome do computador ao qual se conectar é ' localhost '.</span><span class="sxs-lookup"><span data-stu-id="14dd0-150">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="14dd0-151">Nenhuma credencial é passada.</span><span class="sxs-lookup"><span data-stu-id="14dd0-151">No credentials are passed in.</span></span> <span data-ttu-id="14dd0-152">O usuário conectado no momento (credenciais implícitas) é usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-152">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="14dd0-153">O parâmetro de opção **EnableNetworkAccess** é usado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-153">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="14dd0-154">Para obter mais informações sobre conexões de loopback, consulte o documento [New-PSSession](New-PSSession.md) .</span><span class="sxs-lookup"><span data-stu-id="14dd0-154">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="14dd0-155">Exemplo 6: impedir o acesso remoto a configurações de sessão que têm descritores de segurança personalizados</span><span class="sxs-lookup"><span data-stu-id="14dd0-155">Example 6: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="14dd0-156">Este exemplo demonstra que o `Disable-PSRemoting` cmdlet desabilita o acesso remoto a todas as configurações de sessão que incluem configurações de sessão com descritores de segurança personalizados.</span><span class="sxs-lookup"><span data-stu-id="14dd0-156">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="14dd0-157">`Register-PSSessionConfiguration` cria a configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-157">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="14dd0-158">O parâmetro **FilePath** especifica um arquivo de configuração de sessão que personaliza a sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-158">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="14dd0-159">O parâmetro **ShowSecurityDescriptorUI dos** exibe uma caixa de diálogo que define permissões para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-159">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="14dd0-160">Na caixa de diálogo permissões, criamos permissões personalizadas de acesso completo para o usuário indicado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-160">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="14dd0-161">Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="14dd0-161">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="14dd0-162">A saída mostra que a configuração da sessão de **teste** permite acesso interativo e permissões especiais para o usuário indicado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-162">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="14dd0-163">`Disable-PSRemoting` desabilita o acesso remoto a todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-163">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="14dd0-164">Agora `Get-PSSessionConfiguration` , os `Format-Table` cmdlets e mostram que um descritor de segurança **AccessDenied** para todos os usuários de rede é adicionado a todas as configurações de sessão, incluindo a configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-164">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="14dd0-165">Embora os outros descritores de segurança não sejam alterados, a descrição de segurança "network_deny_all" tem precedência.</span><span class="sxs-lookup"><span data-stu-id="14dd0-165">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="14dd0-166">Isso é ilustrado pela tentativa de usar `New-PSSession` o para se conectar à configuração da sessão de **teste** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-166">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="14dd0-167">Exemplo 7: reabilitar o acesso remoto para as configurações de sessão selecionadas</span><span class="sxs-lookup"><span data-stu-id="14dd0-167">Example 7: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="14dd0-168">Este exemplo mostra como reabilitar o acesso remoto apenas para as configurações de sessão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="14dd0-168">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="14dd0-169">Depois de desabilitar todas as configurações de sessão, reabilitamos uma sessão específica.</span><span class="sxs-lookup"><span data-stu-id="14dd0-169">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="14dd0-170">O `Set-PSSessionConfiguration` cmdlet é usado para alterar o **Microsoft. Configuração de sessão do ServerManager** .</span><span class="sxs-lookup"><span data-stu-id="14dd0-170">The `Set-PSSessionConfiguration` cmdlet is used to change the **microsoft.ServerManager** session configuration.</span></span> <span data-ttu-id="14dd0-171">O parâmetro **AccessMode** com um valor de reabilitar **remotamente** o acesso remoto à configuração.</span><span class="sxs-lookup"><span data-stu-id="14dd0-171">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
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

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## <span data-ttu-id="14dd0-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14dd0-172">PARAMETERS</span></span>

### <span data-ttu-id="14dd0-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="14dd0-173">-Confirm</span></span>

<span data-ttu-id="14dd0-174">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14dd0-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="14dd0-175">-Force</span><span class="sxs-lookup"><span data-stu-id="14dd0-175">-Force</span></span>
<span data-ttu-id="14dd0-176">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="14dd0-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="14dd0-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="14dd0-177">-WhatIf</span></span>

<span data-ttu-id="14dd0-178">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="14dd0-179">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="14dd0-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="14dd0-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14dd0-180">CommonParameters</span></span>

<span data-ttu-id="14dd0-181">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14dd0-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14dd0-182">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="14dd0-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14dd0-183">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="14dd0-183">INPUTS</span></span>

### <span data-ttu-id="14dd0-184">Nenhum</span><span class="sxs-lookup"><span data-stu-id="14dd0-184">None</span></span>

<span data-ttu-id="14dd0-185">Não é possível canalizar nenhum objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14dd0-185">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="14dd0-186">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="14dd0-186">OUTPUTS</span></span>

### <span data-ttu-id="14dd0-187">Nenhum</span><span class="sxs-lookup"><span data-stu-id="14dd0-187">None</span></span>

<span data-ttu-id="14dd0-188">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="14dd0-188">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="14dd0-189">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="14dd0-189">NOTES</span></span>

- <span data-ttu-id="14dd0-190">Desabilitar as configurações de sessão não desfaz todas as alterações feitas pelos `Enable-PSRemoting` `Enable-PSSessionConfiguration` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="14dd0-190">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="14dd0-191">Você talvez precise desfazer, manualmente, as alterações listadas a seguir.</span><span class="sxs-lookup"><span data-stu-id="14dd0-191">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="14dd0-192">Interrompa e desabilite o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="14dd0-192">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="14dd0-193">Exclua o ouvinte que aceita solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="14dd0-193">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="14dd0-194">Desabilite as exceções de firewall para comunicações do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="14dd0-194">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="14dd0-195">Restaure o valor de LocalAccountTokenFilterPolicy para 0, o que restringe o acesso remoto apenas a membros do grupo Administradores do computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-195">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

  <span data-ttu-id="14dd0-196">Uma configuração de sessão é um grupo de configurações que definem o ambiente para uma sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-196">A session configuration is a group of settings that define the environment for a session.</span></span> <span data-ttu-id="14dd0-197">Cada sessão que se conecta ao computador deve usar uma das configurações de sessão registradas no computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-197">Every session that connects to the computer must use one of the session configurations that are registered on the computer.</span></span> <span data-ttu-id="14dd0-198">Negando acesso remoto a todas as configurações de sessão, você impede efetivamente que usuários remotos estabeleçam sessões com conexão ao computador.</span><span class="sxs-lookup"><span data-stu-id="14dd0-198">By denying remote access to all session configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

  <span data-ttu-id="14dd0-199">No Windows PowerShell 2,0, `Disable-PSRemoting` o adiciona uma entrada de Deny_All aos descritores de segurança de todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-199">In Windows PowerShell 2.0, `Disable-PSRemoting` adds a Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="14dd0-200">Essa configuração impede que todos os usuários criem sessões gerenciadas pelo usuário para o computador local.</span><span class="sxs-lookup"><span data-stu-id="14dd0-200">This setting prevents all users from creating user-managed sessions to the local computer.</span></span> <span data-ttu-id="14dd0-201">No Windows PowerShell 3,0, `Disable-PSRemoting` o adiciona uma entrada de Network_Deny_All aos descritores de segurança de todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="14dd0-201">In Windows PowerShell 3.0, `Disable-PSRemoting` adds a Network_Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="14dd0-202">Essa configuração impede que os usuários em outros computadores criem sessões gerenciadas pelo usuário no computador local, mas permite aos usuários do computador local criar sessões de auto-retorno gerenciadas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="14dd0-202">This setting prevents users on other computers from creating user-managed sessions on the local computer, but allows users of the local computer to create user-managed loopback sessions.</span></span>

  <span data-ttu-id="14dd0-203">No Windows PowerShell 2,0, `Disable-PSRemoting` é o equivalente de `Disable-PSSessionConfiguration -Name *` .</span><span class="sxs-lookup"><span data-stu-id="14dd0-203">In Windows PowerShell 2.0, `Disable-PSRemoting` is the equivalent of `Disable-PSSessionConfiguration -Name *`.</span></span> <span data-ttu-id="14dd0-204">No Windows PowerShell 3,0 e versões posteriores, `Disable-PSRemoting` é o equivalente de `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span><span class="sxs-lookup"><span data-stu-id="14dd0-204">In Windows PowerShell 3.0 and later releases, `Disable-PSRemoting` is the equivalent of `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span></span>

## <span data-ttu-id="14dd0-205">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="14dd0-205">RELATED LINKS</span></span>

[<span data-ttu-id="14dd0-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14dd0-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="14dd0-207">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="14dd0-207">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="14dd0-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14dd0-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="14dd0-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="14dd0-209">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="14dd0-210">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14dd0-210">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="14dd0-211">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14dd0-211">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="14dd0-212">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14dd0-212">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="14dd0-213">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="14dd0-213">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
