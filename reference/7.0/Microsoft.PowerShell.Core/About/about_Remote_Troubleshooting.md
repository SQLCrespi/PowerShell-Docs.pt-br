---
description: Descreve como solucionar problemas de operações remotas no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: acf4f86d8c20f5a8059be48623255696afabbefb
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "93196656"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="91aa1-104">Sobre a solução de problemas remoto</span><span class="sxs-lookup"><span data-stu-id="91aa1-104">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="91aa1-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="91aa1-105">Short description</span></span>
<span data-ttu-id="91aa1-106">Descreve como solucionar problemas de operações remotas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91aa1-106">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="91aa1-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="91aa1-107">Long description</span></span>

<span data-ttu-id="91aa1-108">Esta seção descreve alguns dos problemas que você pode encontrar ao usar os recursos de comunicação remota do PowerShell baseados em tecnologia de WS-Management e ele sugere soluções para esses problemas.</span><span class="sxs-lookup"><span data-stu-id="91aa1-108">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="91aa1-109">Antes de usar a comunicação remota do PowerShell, consulte [about_Remote](about_remote.md) e [about_Remote_Requirements](about_Remote_Requirements.md) para obter diretrizes sobre a configuração e o uso básico.</span><span class="sxs-lookup"><span data-stu-id="91aa1-109">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="91aa1-110">Além disso, os tópicos de ajuda para cada um dos cmdlets de comunicação remota, especialmente as descrições de parâmetro, têm informações úteis que são projetadas para ajudá-lo a evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="91aa1-110">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="91aa1-111">Para exibir ou alterar as configurações do computador local na unidade WSMan:, incluindo alterações nas configurações de sessão, hosts confiáveis, portas ou ouvintes, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-111">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="91aa1-112">Solucionando problemas de permissão e autenticação</span><span class="sxs-lookup"><span data-stu-id="91aa1-112">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="91aa1-113">Esta seção aborda problemas de comunicação remota relacionados a permissões de usuário e computador e a requisitos de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-113">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="91aa1-114">Como executar como administrador</span><span class="sxs-lookup"><span data-stu-id="91aa1-114">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="91aa1-115">Para iniciar uma sessão remota no computador local ou para exibir ou alterar as configurações do computador local na unidade WSMan:, incluindo alterações nas configurações de sessão, hosts confiáveis, portas ou ouvintes, inicie o Windows PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-115">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="91aa1-116">Para iniciar o Windows PowerShell com a opção **Executar como administrador** :</span><span class="sxs-lookup"><span data-stu-id="91aa1-116">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="91aa1-117">Clique com o botão direito do mouse em um ícone do Windows PowerShell (ou ISE do Windows PowerShell) e clique em **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-117">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator** .</span></span>

  <span data-ttu-id="91aa1-118">Para iniciar o Windows PowerShell com a opção **Executar como administrador** no Windows 7 e no windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="91aa1-118">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="91aa1-119">Na barra de tarefas do Windows, clique com o botão direito do mouse no ícone do Windows PowerShell e clique em **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-119">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator** .</span></span>

  <span data-ttu-id="91aa1-120">No Windows Server 2008 R2, o ícone do Windows PowerShell é fixado na barra de tarefas por padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-120">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="91aa1-121">Como habilitar a comunicação remota</span><span class="sxs-lookup"><span data-stu-id="91aa1-121">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="91aa1-122">Nenhuma configuração é necessária para permitir que um computador envie comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-122">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="91aa1-123">No entanto, para receber comandos remotos, a comunicação remota do PowerShell deve estar habilitada no computador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-123">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="91aa1-124">A habilitação inclui a inicialização do serviço WinRM, a definição do tipo de inicialização para o serviço WinRM como automático, a criação de ouvintes para conexões HTTP e HTTPS e a criação de configurações de sessão padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-124">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="91aa1-125">A comunicação remota do Windows PowerShell está habilitada no Windows Server 2012 e em versões mais recentes do Windows Server por padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-125">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="91aa1-126">Em todos os outros sistemas, execute o `Enable-PSRemoting` cmdlet para habilitar a comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-126">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="91aa1-127">Também é possível executar o `Enable-PSRemoting` cmdlet para reabilitar a comunicação remota no Windows server 2012 e versões mais recentes do Windows Server se a comunicação remota estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="91aa1-127">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="91aa1-128">Para configurar um computador para receber comandos remotos, use o `Enable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91aa1-128">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="91aa1-129">O comando a seguir habilita todas as configurações remotas necessárias, habilita as configurações de sessão e reinicia o serviço WinRM para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="91aa1-129">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="91aa1-130">Para suprimir todos os prompts de usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="91aa1-130">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="91aa1-131">Para obter mais informações, consulte [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span><span class="sxs-lookup"><span data-stu-id="91aa1-131">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="91aa1-132">Como habilitar a comunicação remota em uma empresa</span><span class="sxs-lookup"><span data-stu-id="91aa1-132">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="91aa1-133">Para permitir que um único computador receba comandos remotos do PowerShell e aceite conexões, use o `Enable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91aa1-133">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="91aa1-134">Para habilitar a comunicação remota para vários computadores em uma empresa, você pode usar as seguintes opções de escala.</span><span class="sxs-lookup"><span data-stu-id="91aa1-134">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="91aa1-135">Para configurar ouvintes para comunicação remota, habilite a política **de grupo permitir configuração automática de ouvintes** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-135">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="91aa1-136">Para definir o tipo de inicialização do Gerenciamento Remoto do Windows (WinRM) como automático em vários computadores, use o `Set-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91aa1-136">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="91aa1-137">Para habilitar uma exceção de firewall, use a política de grupo **Firewall do Windows: permitir exceções de porta local** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-137">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="91aa1-138">Como habilitar ouvintes usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="91aa1-138">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="91aa1-139">Para configurar os ouvintes para todos os computadores em um domínio, habilite a política **permitir configuração automática de ouvintes** no seguinte caminho de política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="91aa1-139">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="91aa1-140">Habilite a política e especifique os filtros IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="91aa1-140">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="91aa1-141">Caracteres curinga ( `*` ) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-141">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="91aa1-142">Como habilitar a comunicação remota em redes públicas</span><span class="sxs-lookup"><span data-stu-id="91aa1-142">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="91aa1-143">O `Enable-PSRemoting` cmdlet retorna esse erro quando a rede local é pública e o parâmetro **SkipNetworkProfileCheck** não é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="91aa1-143">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="91aa1-144">Em versões de servidor do Windows, o tem `Enable-PSRemoting` sucesso em todos os tipos de local de rede.</span><span class="sxs-lookup"><span data-stu-id="91aa1-144">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="91aa1-145">Ele cria regras de firewall que permitem acesso remoto a redes privadas e de domínio ("página inicial" e "trabalho").</span><span class="sxs-lookup"><span data-stu-id="91aa1-145">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="91aa1-146">Para redes públicas, ele cria regras de firewall que permitem o acesso remoto da mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-146">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="91aa1-147">Nas versões cliente do Windows, o é `Enable-PSRemoting` bem sucedido em redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="91aa1-147">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="91aa1-148">Por padrão, ele falha em redes públicas, mas se você usar o parâmetro **SkipNetworkProfileCheck** , o `Enable-PSRemoting` terá êxito e criará uma regra de firewall que permite o tráfego da mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-148">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="91aa1-149">Para remover a restrição de sub-rede local em redes públicas e permitir o acesso remoto de qualquer local, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-149">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="91aa1-150">O `Set-NetFirewallRule` cmdlet é exportado pelo módulo NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="91aa1-150">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="91aa1-151">No Windows PowerShell 2,0, em computadores que executam versões de servidor do Windows, o `Enable-PSRemoting` cria regras de firewall que permitem o acesso remoto em redes privadas, de domínio e públicas.</span><span class="sxs-lookup"><span data-stu-id="91aa1-151">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="91aa1-152">Em computadores que executam versões cliente do Windows, o `Enable-PSRemoting` cria regras de firewall que permitem o acesso remoto somente em redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="91aa1-152">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="91aa1-153">Como habilitar uma exceção de firewall usando uma política de grupo</span><span class="sxs-lookup"><span data-stu-id="91aa1-153">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="91aa1-154">Para habilitar uma exceção de firewall para o em todos os computadores em um domínio, habilite a política **Firewall do Windows: permitir exceções de porta local** no seguinte caminho de política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="91aa1-154">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="91aa1-155">Essa política permite que os membros do grupo Administradores no computador usem o **Firewall do Windows** no **painel de controle** para criar uma exceção de firewall para o serviço de gerenciamento remoto do Windows.</span><span class="sxs-lookup"><span data-stu-id="91aa1-155">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="91aa1-156">Se a configuração da política estiver incorreta, você poderá receber o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="91aa1-156">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="91aa1-157">Um erro de configuração na política resulta em um valor vazio para a propriedade **listening** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-157">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="91aa1-158">Use o comando a seguir para verificar o valor.</span><span class="sxs-lookup"><span data-stu-id="91aa1-158">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="91aa1-159">Como definir o tipo de inicialização do serviço WinRM</span><span class="sxs-lookup"><span data-stu-id="91aa1-159">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="91aa1-160">A comunicação remota do PowerShell depende do serviço de Gerenciamento Remoto do Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="91aa1-160">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="91aa1-161">O serviço deve estar em execução para dar suporte a comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-161">The service must be running to support remote commands.</span></span>

<span data-ttu-id="91aa1-162">Nas versões de servidor do Windows, o tipo de inicialização do serviço de Gerenciamento Remoto do Windows (WinRM) é automático.</span><span class="sxs-lookup"><span data-stu-id="91aa1-162">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="91aa1-163">No entanto, nas versões cliente do Windows, o serviço WinRM é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-163">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="91aa1-164">Para definir o tipo de inicialização de um serviço em um computador remoto, use o `Set-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91aa1-164">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="91aa1-165">Para executar o comando em vários computadores, você pode criar um arquivo de texto ou arquivo CSV dos nomes dos computadores.</span><span class="sxs-lookup"><span data-stu-id="91aa1-165">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="91aa1-166">Por exemplo, os comandos a seguir obtêm uma lista de nomes de computador do `Servers.txt` arquivo e, em seguida, definem o tipo de inicialização do serviço WinRM em todos os computadores como **automáticos** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-166">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic** .</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="91aa1-167">Para ver os resultados, use o `Get-WMIObject` cmdlet com o objeto **Win32_Service** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-167">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="91aa1-168">Para obter mais informações, consulte [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span><span class="sxs-lookup"><span data-stu-id="91aa1-168">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="91aa1-169">Como recriar as configurações de sessão padrão</span><span class="sxs-lookup"><span data-stu-id="91aa1-169">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="91aa1-170">Para se conectar ao computador local e executar comandos remotamente, o computador local deve incluir configurações de sessão para comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-170">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="91aa1-171">Quando você usa `Enable-PSRemoting` o, ele cria configurações de sessão padrão no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-171">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="91aa1-172">Os usuários remotos usam essas configurações de sessão sempre que um comando remoto não inclui o parâmetro **ConfigurationName** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-172">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="91aa1-173">Se as configurações padrão em um computador tiverem o registro cancelado ou excluído, use o `Enable-PSRemoting` cmdlet para recriá-las.</span><span class="sxs-lookup"><span data-stu-id="91aa1-173">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="91aa1-174">Você pode usar esse cmdlet repetidamente.</span><span class="sxs-lookup"><span data-stu-id="91aa1-174">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="91aa1-175">Ele não gerará erros se um recurso já estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="91aa1-175">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="91aa1-176">Se você alterar as configurações de sessão padrão e quiser restaurar as configurações de sessão padrão originais, use o `Unregister-PSSessionConfiguration` cmdlet para excluir as configurações de sessão alteradas e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-las.</span><span class="sxs-lookup"><span data-stu-id="91aa1-176">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="91aa1-177">`Enable-PSRemoting` Não altera as configurações de sessão existentes.</span><span class="sxs-lookup"><span data-stu-id="91aa1-177">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="91aa1-178">Quando `Enable-PSRemoting` o restaura a configuração de sessão padrão, ele não cria descritores de segurança explícitos para as configurações.</span><span class="sxs-lookup"><span data-stu-id="91aa1-178">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="91aa1-179">Em vez disso, as configurações herdam o descritor de segurança do RootSDDL, que é seguro por padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-179">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="91aa1-180">Para ver o descritor de segurança RootSDDL, digite:</span><span class="sxs-lookup"><span data-stu-id="91aa1-180">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="91aa1-181">Para alterar o RootSDDL, use o `Set-Item` cmdlet na unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="91aa1-181">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="91aa1-182">Para alterar o descritor de segurança de uma configuração de sessão, use o `Set-PSSessionConfiguration` cmdlet com os parâmetros **SecurityDescriptorSDDL** ou **ShowSecurityDescriptorUI dos** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-182">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="91aa1-183">Para obter mais informações sobre a unidade WSMan:, consulte o tópico da ajuda para o provedor WSMan ("get-help WSMan").</span><span class="sxs-lookup"><span data-stu-id="91aa1-183">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="91aa1-184">Como fornecer credenciais de administrador</span><span class="sxs-lookup"><span data-stu-id="91aa1-184">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="91aa1-185">Para criar uma PSSession ou executar comandos em um computador remoto, por padrão, o usuário atual deve ser um membro do grupo Administradores no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="91aa1-185">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="91aa1-186">Às vezes, as credenciais são necessárias mesmo quando o usuário atual está conectado a uma conta que seja membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="91aa1-186">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="91aa1-187">Se o usuário atual for um membro do grupo Administradores no computador remoto, ou puder fornecer as credenciais de um membro do grupo Administradores, use o parâmetro **Credential** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets ou para se conectar remotamente.</span><span class="sxs-lookup"><span data-stu-id="91aa1-187">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="91aa1-188">Por exemplo, o comando a seguir fornece as credenciais de um administrador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-188">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="91aa1-189">Para obter mais informações sobre o parâmetro **Credential** , consulte [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) ou [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="91aa1-189">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="91aa1-190">Como habilitar a comunicação remota para usuários não administrativos</span><span class="sxs-lookup"><span data-stu-id="91aa1-190">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="91aa1-191">Para estabelecer uma PSSession ou executar um comando em um computador remoto, o usuário deve ter permissão para usar as configurações de sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="91aa1-191">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="91aa1-192">Por padrão, somente os membros do grupo Administradores em um computador têm permissão para usar as configurações de sessão padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-192">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="91aa1-193">Portanto, somente os membros do grupo Administradores podem se conectar ao computador remotamente.</span><span class="sxs-lookup"><span data-stu-id="91aa1-193">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="91aa1-194">Para permitir que outros usuários se conectem ao computador local, dê ao usuário permissões de execução para as configurações de sessão padrão no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-194">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="91aa1-195">O comando a seguir abre uma folha de propriedades que permite alterar o descritor de segurança da configuração de sessão padrão do Microsoft. PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-195">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="91aa1-196">Para obter mais informações, consulte [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-196">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="91aa1-197">Como habilitar a comunicação remota para administradores em outros domínios</span><span class="sxs-lookup"><span data-stu-id="91aa1-197">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="91aa1-198">Quando um usuário em outro domínio é membro do grupo Administradores no computador local, o usuário não pode se conectar ao computador local remotamente com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-198">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="91aa1-199">Por padrão, conexões remotas de outros domínios são executadas somente com tokens de privilégio de usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-199">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="91aa1-200">No entanto, você pode usar a entrada do registro **LocalAccountTokenFilterPolicy** para alterar o comportamento padrão e permitir que usuários remotos que sejam membros do grupo Administradores sejam executados com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-200">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="91aa1-201">A entrada **LocalAccountTokenFilterPolicy** desabilita as restrições remotas do UAC (controle de conta de usuário) para todos os usuários de todos os computadores afetados.</span><span class="sxs-lookup"><span data-stu-id="91aa1-201">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="91aa1-202">Considere as implicações dessa configuração cuidadosamente antes de alterar a política.</span><span class="sxs-lookup"><span data-stu-id="91aa1-202">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="91aa1-203">Para alterar a política, use o comando a seguir para definir o valor da entrada do registro **LocalAccountTokenFilterPolicy** como 1.</span><span class="sxs-lookup"><span data-stu-id="91aa1-203">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="91aa1-204">Como usar um endereço IP em um comando remoto</span><span class="sxs-lookup"><span data-stu-id="91aa1-204">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="91aa1-205">O parâmetro **ComputerName** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets e aceita um endereço IP como um valor válido.</span><span class="sxs-lookup"><span data-stu-id="91aa1-205">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="91aa1-206">No entanto, como a autenticação Kerberos não dá suporte a endereços IP, a autenticação NTLM é usada por padrão sempre que você especifica um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="91aa1-206">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="91aa1-207">Ao usar a autenticação NTLM, o procedimento a seguir é necessário para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-207">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="91aa1-208">Configure o computador para transporte HTTPS ou adicione os endereços IP dos computadores remotos à lista TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-208">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="91aa1-209">Use o parâmetro **Credential** em todos os comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-209">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="91aa1-210">Isso é necessário mesmo quando você está enviando as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="91aa1-210">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="91aa1-211">Como se conectar remotamente de um computador baseado em grupo de trabalho</span><span class="sxs-lookup"><span data-stu-id="91aa1-211">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="91aa1-212">Quando o computador local não está em um domínio, o procedimento a seguir é necessário para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-212">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="91aa1-213">Configure o computador para transporte HTTPS ou adicione os nomes dos computadores remotos à lista TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-213">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="91aa1-214">Verifique se uma senha está definida no computador baseado em grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="91aa1-214">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="91aa1-215">Se uma senha não estiver definida ou o valor da senha estiver vazio, você não poderá executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-215">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="91aa1-216">Para definir a senha para sua conta de usuário, use contas de usuário no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="91aa1-216">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="91aa1-217">Use o parâmetro **Credential** em todos os comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-217">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="91aa1-218">Isso é necessário mesmo quando você está enviando as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="91aa1-218">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="91aa1-219">Como adicionar um computador à lista de hosts confiáveis</span><span class="sxs-lookup"><span data-stu-id="91aa1-219">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="91aa1-220">O item TrustedHosts pode conter uma lista separada por vírgulas de nomes de computador, endereços IP e nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="91aa1-220">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="91aa1-221">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-221">Wildcards are permitted.</span></span>

<span data-ttu-id="91aa1-222">Para exibir ou alterar a lista de hosts confiáveis, use a unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="91aa1-222">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="91aa1-223">O item TrustedHost está no `WSMan:\localhost\Client` nó.</span><span class="sxs-lookup"><span data-stu-id="91aa1-223">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="91aa1-224">Somente os membros do grupo Administradores no computador têm permissão para alterar a lista de hosts confiáveis no computador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-224">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="91aa1-225">Cuidado: o valor que você define para o item TrustedHosts afeta todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-225">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="91aa1-226">Para exibir a lista de hosts confiáveis, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-226">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="91aa1-227">Você também pode usar o `Set-Location` cmdlet (alias = CD) para navegar por meio da unidade WSMan: para o local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-227">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="91aa1-228">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="91aa1-228">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="91aa1-229">Para adicionar todos os computadores à lista de hosts confiáveis, use o comando a seguir, que coloca um valor de \* (All) no ComputerName</span><span class="sxs-lookup"><span data-stu-id="91aa1-229">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="91aa1-230">Você também pode usar um caractere curinga ( `*` ) para adicionar todos os computadores em um domínio específico à lista de hosts confiáveis.</span><span class="sxs-lookup"><span data-stu-id="91aa1-230">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="91aa1-231">Por exemplo, o comando a seguir adiciona todos os computadores do domínio fabrikam à lista de hosts confiáveis.</span><span class="sxs-lookup"><span data-stu-id="91aa1-231">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="91aa1-232">Para adicionar os nomes de computadores específicos à lista de hosts confiáveis, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-232">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="91aa1-233">onde cada valor `<ComputerName>` deve ter o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="91aa1-233">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="91aa1-234">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="91aa1-234">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="91aa1-235">Para adicionar um nome de computador a uma lista existente de hosts confiáveis, primeiro salve o valor atual em uma variável e, em seguida, defina o valor para uma lista separada por vírgulas que inclui os valores atuais e novos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-235">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="91aa1-236">Por exemplo, para adicionar o computador Server01 a uma lista de hosts confiáveis existente, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-236">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="91aa1-237">Para adicionar os endereços IP de determinados computadores à lista de hosts confiáveis, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-237">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="91aa1-238">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="91aa1-238">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="91aa1-239">Para adicionar um computador à lista TrustedHosts de um computador remoto, use o `Connect-WSMan` cmdlet para adicionar um nó do computador remoto à unidade WSMan: no computador local.</span><span class="sxs-lookup"><span data-stu-id="91aa1-239">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="91aa1-240">Em seguida, use um `Set-Item` comando para adicionar o computador.</span><span class="sxs-lookup"><span data-stu-id="91aa1-240">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="91aa1-241">Para obter mais informações sobre o `Connect-WSMan` cmdlet, consulte [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="91aa1-241">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="91aa1-242">Solucionando problemas de configuração do computador</span><span class="sxs-lookup"><span data-stu-id="91aa1-242">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="91aa1-243">Esta seção aborda problemas de comunicação remota relacionados a configurações específicas de um computador, domínio ou empresa.</span><span class="sxs-lookup"><span data-stu-id="91aa1-243">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="91aa1-244">Como configurar a comunicação remota em portas alternativas</span><span class="sxs-lookup"><span data-stu-id="91aa1-244">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="91aa1-245">A comunicação remota do PowerShell usa a porta 80 para o transporte HTTP por padrão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-245">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="91aa1-246">A porta padrão é usada sempre que o usuário não especificar os parâmetros de **porta** ou **conexãouri** em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="91aa1-246">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="91aa1-247">Para alterar a porta padrão usada pelo PowerShell, use `Set-Item` o cmdlet na unidade WSMan: para alterar o valor da porta no nó folha do ouvinte.</span><span class="sxs-lookup"><span data-stu-id="91aa1-247">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="91aa1-248">Por exemplo, o comando a seguir altera a porta padrão para 8080.</span><span class="sxs-lookup"><span data-stu-id="91aa1-248">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="91aa1-249">Como configurar a comunicação remota com um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="91aa1-249">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="91aa1-250">Como a comunicação remota do PowerShell usa o protocolo HTTP, ela é afetada pelas configurações de proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="91aa1-250">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="91aa1-251">Em empresas que têm servidores proxy, os usuários não podem acessar um computador remoto do PowerShell diretamente.</span><span class="sxs-lookup"><span data-stu-id="91aa1-251">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="91aa1-252">Para resolver esse problema, use as opções de configuração de proxy no comando remoto.</span><span class="sxs-lookup"><span data-stu-id="91aa1-252">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="91aa1-253">As seguintes configurações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="91aa1-253">The following settings are available:</span></span>

- <span data-ttu-id="91aa1-254">ProxyAccessType</span><span class="sxs-lookup"><span data-stu-id="91aa1-254">ProxyAccessType</span></span>
- <span data-ttu-id="91aa1-255">ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="91aa1-255">ProxyAuthentication</span></span>
- <span data-ttu-id="91aa1-256">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="91aa1-256">ProxyCredential</span></span>

<span data-ttu-id="91aa1-257">Para definir essas opções para um comando específico, use o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="91aa1-257">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="91aa1-258">Use os parâmetros **ProxyAccessType** , **ProxyAuthentication** e **ProxyCredential** do `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão com as configurações de proxy para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="91aa1-258">Use the **ProxyAccessType** , **ProxyAuthentication** , and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="91aa1-259">Salvar o objeto de opção é uma variável.</span><span class="sxs-lookup"><span data-stu-id="91aa1-259">Save the option object is a variable.</span></span>

1. <span data-ttu-id="91aa1-260">Use a variável que contém o objeto Option como o valor do parâmetro **SessionOption** de um `New-PSSession` comando, `Enter-PSSession` ou `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="91aa1-260">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="91aa1-261">Por exemplo, o comando a seguir cria um objeto de opção de sessão com opções de sessão de proxy e, em seguida, usa o objeto para criar uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-261">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="91aa1-262">Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="91aa1-262">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="91aa1-263">Para definir essas opções para todos os comandos remotos na sessão atual, use o objeto Option que `New-PSSessionOption` cria no valor da `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="91aa1-263">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="91aa1-264">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-264">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="91aa1-265">Para definir essas opções para todos os comandos remotos todas as sessões do PowerShell no computador local, adicione a `$PSSessionOption` variável de preferência ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91aa1-265">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="91aa1-266">Para obter mais informações sobre perfis do PowerShell, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-266">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="91aa1-267">Como detectar uma sessão de 32 bits em um computador de 64 bits</span><span class="sxs-lookup"><span data-stu-id="91aa1-267">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="91aa1-268">Se o computador remoto estiver executando uma versão de 64 bits do Windows, e o comando remoto estiver usando uma configuração de sessão de 32 bits, como Microsoft. PowerShell32, o Gerenciamento Remoto do Windows (WinRM) carregará um processo WOW64 e o Windows redirecionará automaticamente todas as referências ao `$env:Windir\System32` diretório para o `$env:Windir\SysWOW64` diretório.</span><span class="sxs-lookup"><span data-stu-id="91aa1-268">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="91aa1-269">Como resultado, se você tentar usar as ferramentas no diretório system32 que não têm contrapartes no diretório SysWow64, como `Defrag.exe` , as ferramentas não podem ser encontradas no diretório.</span><span class="sxs-lookup"><span data-stu-id="91aa1-269">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="91aa1-270">Para localizar a arquitetura do processador que está sendo usada na sessão, use o valor da variável de ambiente **PROCESSOR_ARCHITECTURE** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-270">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="91aa1-271">O comando a seguir localiza a arquitetura do processador da sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="91aa1-271">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="91aa1-272">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-272">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="91aa1-273">Solucionando problemas de política e problemas de preferência</span><span class="sxs-lookup"><span data-stu-id="91aa1-273">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="91aa1-274">Esta seção aborda problemas de comunicação remota relacionados a políticas e preferências definidas nos computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="91aa1-274">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="91aa1-275">Como alterar a política de execução para Import-PSSession e Import-Module</span><span class="sxs-lookup"><span data-stu-id="91aa1-275">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="91aa1-276">Os `Import-PSSession` `Export-PSSession` cmdlets e criam módulos que contêm arquivos de script não assinados e arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="91aa1-276">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="91aa1-277">Para importar os módulos criados por esses cmdlets, usando `Import-PSSession` `Import-Module` o ou o, a política de execução na sessão atual não pode ser restrita ou AllSigned.</span><span class="sxs-lookup"><span data-stu-id="91aa1-277">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="91aa1-278">Para obter informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-278">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="91aa1-279">Para importar os módulos sem alterar a política de execução para o computador local definido no registro, use o parâmetro **Scope** de `Set-ExecutionPolicy` para definir uma política de execução menos restritiva para um único processo.</span><span class="sxs-lookup"><span data-stu-id="91aa1-279">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="91aa1-280">Por exemplo, o comando a seguir inicia um processo com a `RemoteSigned` política de execução.</span><span class="sxs-lookup"><span data-stu-id="91aa1-280">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="91aa1-281">A alteração da política de execução afeta apenas o processo atual e não altera a configuração do registro **ExecutionPolicy** do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91aa1-281">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="91aa1-282">Você também pode usar o parâmetro **ExecutionPolicy** do `PowerShell.exe` para iniciar uma única sessão com uma política de execução menos restritiva.</span><span class="sxs-lookup"><span data-stu-id="91aa1-282">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="91aa1-283">Para obter mais informações sobre políticas de execução, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-283">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="91aa1-284">Para obter mais informações, digite `PowerShell.exe -?`.</span><span class="sxs-lookup"><span data-stu-id="91aa1-284">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="91aa1-285">Como definir e alterar cotas</span><span class="sxs-lookup"><span data-stu-id="91aa1-285">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="91aa1-286">Você pode usar cotas para proteger o computador local e o computador remoto contra o uso excessivo de recursos, acidental e mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="91aa1-286">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="91aa1-287">As cotas a seguir estão disponíveis na configuração básica.</span><span class="sxs-lookup"><span data-stu-id="91aa1-287">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="91aa1-288">O provedor WSMan (WSMan:) fornece várias configurações de cota, como as configurações de **MaxEnvelopeSizeKB** e **MaxProviderRequests** no `WSMan:<ComputerName>` nó e as configurações de **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** e **MaxConnections** no `WSMan:<ComputerName>\Service` nó.</span><span class="sxs-lookup"><span data-stu-id="91aa1-288">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** , and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="91aa1-289">Você pode proteger o computador local usando os parâmetros **MaximumReceivedDataSizePerCommand** e **MaximumReceivedObjectSize** do `New-PSSessionOption` cmdlet e a variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="91aa1-289">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="91aa1-290">Você pode proteger o computador remoto adicionando restrições às configurações de sessão, como usando os parâmetros **MaximumReceivedDataSizePerCommandMB** e **MaximumReceivedObjectSizeMB** do `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91aa1-290">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="91aa1-291">Quando as cotas entram em conflito com um comando, o PowerShell gera um erro.</span><span class="sxs-lookup"><span data-stu-id="91aa1-291">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="91aa1-292">Para resolver o erro, altere o comando remoto para que ele esteja em conformidade com a cota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-292">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="91aa1-293">Ou determine a origem da cota e, em seguida, aumente a cota para permitir que o comando seja concluído.</span><span class="sxs-lookup"><span data-stu-id="91aa1-293">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="91aa1-294">Por exemplo, o comando a seguir aumenta a cota de tamanho do objeto na configuração de sessão do Microsoft. PowerShell no computador remoto de 10 MB (o valor padrão) para 11 MB.</span><span class="sxs-lookup"><span data-stu-id="91aa1-294">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="91aa1-295">Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="91aa1-295">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="91aa1-296">Para obter mais informações sobre as cotas de WS-Management, consulte [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="91aa1-296">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="91aa1-297">Como resolver erros de tempo limite</span><span class="sxs-lookup"><span data-stu-id="91aa1-297">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="91aa1-298">Você pode usar tempos limite para proteger o computador local e o computador remoto contra o uso excessivo de recursos, acidental e mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="91aa1-298">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="91aa1-299">Quando os tempos limite são definidos no computador local e remoto, o PowerShell usa as configurações de tempo limite mais curtas.</span><span class="sxs-lookup"><span data-stu-id="91aa1-299">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="91aa1-300">Os tempos limite a seguir estão disponíveis na configuração básica.</span><span class="sxs-lookup"><span data-stu-id="91aa1-300">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="91aa1-301">O provedor WSMan (WSMan:) fornece várias configurações do lado do cliente e do tempo limite do lado do serviço, como a configuração **MaxTimeoutms** no `WSMan:<ComputerName>` nó e as configurações **EnumerationTimeoutms** e **MaxPacketRetrievalTimeSeconds** no `WSMan:<ComputerName>\Service` nó.</span><span class="sxs-lookup"><span data-stu-id="91aa1-301">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="91aa1-302">Você pode proteger o computador local usando os parâmetros **CancelTimeout** , **IdleTimeout** , **OpenTimeout** e **OperationTimeout** do `New-PSSessionOption` cmdlet e a `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="91aa1-302">You can protect the local computer by using the **CancelTimeout** , **IdleTimeout** , **OpenTimeout** , and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="91aa1-303">Você também pode proteger o computador remoto definindo valores de tempo limite programaticamente na configuração de sessão para a sessão.</span><span class="sxs-lookup"><span data-stu-id="91aa1-303">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="91aa1-304">Quando um valor de tempo limite não permite que uma operação seja concluída, o PowerShell encerra a operação e gera um erro.</span><span class="sxs-lookup"><span data-stu-id="91aa1-304">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="91aa1-305">Para resolver o erro, altere o comando para concluir dentro do intervalo de tempo limite ou determine a origem do limite de tempo limite e aumente o intervalo de tempo limite para permitir que o comando seja concluído.</span><span class="sxs-lookup"><span data-stu-id="91aa1-305">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="91aa1-306">Por exemplo, os comandos a seguir usam o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão com um valor de **OperationTimeout** de 4 minutos (em MS) e, em seguida, usar o objeto de opção de sessão para criar uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-306">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="91aa1-307">Para obter mais informações sobre o tempo limite do WS-Management, consulte o tópico da ajuda para o provedor WSMan (tipo `Get-Help WSMan` ).</span><span class="sxs-lookup"><span data-stu-id="91aa1-307">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="91aa1-308">Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="91aa1-308">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="91aa1-309">Solucionando problemas de comportamento sem resposta</span><span class="sxs-lookup"><span data-stu-id="91aa1-309">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="91aa1-310">Esta seção aborda problemas de comunicação remota que impedem que um comando conclua e impeça ou atrase o retorno do prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91aa1-310">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="91aa1-311">Como interromper um comando</span><span class="sxs-lookup"><span data-stu-id="91aa1-311">How to interrupt a command</span></span>

<span data-ttu-id="91aa1-312">Alguns programas nativos do Windows, como programas com uma interface do usuário, aplicativos de console que solicitam entrada e aplicativos de console que usam a API do console Win32, não funcionam corretamente no host remoto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91aa1-312">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="91aa1-313">Ao usar esses programas, você poderá ver um comportamento inesperado, como nenhuma saída, saída parcial ou um comando remoto que não é concluído.</span><span class="sxs-lookup"><span data-stu-id="91aa1-313">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="91aa1-314">Para encerrar um programa sem resposta, digite <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="91aa1-314">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="91aa1-315">Para exibir os erros que podem ter sido relatados, digite `$error` o host local e a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91aa1-315">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="91aa1-316">Como recuperar-se de uma falha de operação</span><span class="sxs-lookup"><span data-stu-id="91aa1-316">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="91aa1-317">Esse erro é retornado quando uma operação é encerrada antes de ser concluída.</span><span class="sxs-lookup"><span data-stu-id="91aa1-317">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="91aa1-318">Normalmente, ocorre quando o serviço WinRM para ou é reiniciado enquanto outras operações do WinRM estão em andamento.</span><span class="sxs-lookup"><span data-stu-id="91aa1-318">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="91aa1-319">Para resolver esse problema, verifique se o serviço WinRM está em execução e tente o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="91aa1-319">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="91aa1-320">Inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="91aa1-320">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="91aa1-321">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="91aa1-321">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="91aa1-322">Execute novamente o comando que gerou o erro.</span><span class="sxs-lookup"><span data-stu-id="91aa1-322">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="91aa1-323">Limitações do Linux e do macOS</span><span class="sxs-lookup"><span data-stu-id="91aa1-323">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="91aa1-324">Autenticação</span><span class="sxs-lookup"><span data-stu-id="91aa1-324">Authentication</span></span>

<span data-ttu-id="91aa1-325">Somente a autenticação básica funciona no macOS e a tentativa de usar outros esquemas de autenticação pode resultar na falha do processo.</span><span class="sxs-lookup"><span data-stu-id="91aa1-325">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="91aa1-326">Consulte as instruções de [autenticação do OMI](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .</span><span class="sxs-lookup"><span data-stu-id="91aa1-326">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="91aa1-327">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="91aa1-327">SEE ALSO</span></span>

[<span data-ttu-id="91aa1-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="91aa1-328">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="91aa1-329">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="91aa1-329">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="91aa1-330">Import-Module</span><span class="sxs-lookup"><span data-stu-id="91aa1-330">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="91aa1-331">about_Remote</span><span class="sxs-lookup"><span data-stu-id="91aa1-331">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="91aa1-332">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="91aa1-332">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="91aa1-333">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="91aa1-333">about_Remote_Variables</span></span>](about_Remote_Variables.md)
