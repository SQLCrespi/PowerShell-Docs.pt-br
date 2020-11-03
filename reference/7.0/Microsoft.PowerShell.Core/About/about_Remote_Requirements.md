---
description: Descreve os requisitos de sistema e os requisitos de configuração para executar comandos remotos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: dc744a7c945bfccb876087ba8b13413674c52dd5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196272"
---
# <a name="about-remote-requirements"></a><span data-ttu-id="226af-104">Sobre requisitos remotos</span><span class="sxs-lookup"><span data-stu-id="226af-104">About Remote Requirements</span></span>

## <a name="short-description"></a><span data-ttu-id="226af-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="226af-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="226af-106">Descreve os requisitos de sistema e os requisitos de configuração para executar comandos remotos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-106">Describes the system requirements and configuration requirements for running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="226af-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="226af-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="226af-108">Este tópico descreve os requisitos de sistema, os requisitos de usuário e os requisitos de recursos para estabelecer conexões remotas e executar comandos remotos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-108">This topic describes the system requirements, user requirements, and resource requirements for establishing remote connections and running remote commands in PowerShell.</span></span> <span data-ttu-id="226af-109">Ele também fornece instruções para configurar operações remotas.</span><span class="sxs-lookup"><span data-stu-id="226af-109">It also provides instructions for configuring remote operations.</span></span>

<span data-ttu-id="226af-110">Observação: muitos cmdlets (incluindo o Get-Service, o Get-Process, o Get-WMIObject, o Get-EventLog e os cmdlets Get-WinEvent) obtêm objetos de computadores remotos usando métodos de Microsoft .NET Framework para recuperar os objetos.</span><span class="sxs-lookup"><span data-stu-id="226af-110">Note: Many cmdlets (including the Get-Service, Get-Process, Get-WMIObject, Get-EventLog, and Get-WinEvent cmdlets) get objects from remote computers by using Microsoft .NET Framework methods to retrieve the objects.</span></span> <span data-ttu-id="226af-111">Eles não usam a infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-111">They do not use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="226af-112">Os requisitos deste documento não se aplicam a esses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="226af-112">The requirements in this document do not apply to these cmdlets.</span></span>

<span data-ttu-id="226af-113">Para localizar os cmdlets que têm um parâmetro ComputerName, mas não usam a comunicação remota do PowerShell, leia a descrição do parâmetro ComputerName dos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="226af-113">To find the cmdlets that have a ComputerName parameter but do not use PowerShell remoting, read the description of the ComputerName parameter of the cmdlets.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="226af-114">REQUISITOS DO SISTEMA</span><span class="sxs-lookup"><span data-stu-id="226af-114">SYSTEM REQUIREMENTS</span></span>

<span data-ttu-id="226af-115">Para executar sessões remotas no Windows PowerShell 3,0, os computadores locais e remotos devem ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="226af-115">To run remote sessions on Windows PowerShell 3.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="226af-116">Windows PowerShell 3,0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="226af-116">Windows PowerShell 3.0 or later</span></span>
- <span data-ttu-id="226af-117">O Microsoft .NET Framework 4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="226af-117">The Microsoft .NET Framework 4 or later</span></span>
- <span data-ttu-id="226af-118">Gerenciamento Remoto do Windows 3,0</span><span class="sxs-lookup"><span data-stu-id="226af-118">Windows Remote Management 3.0</span></span>

<span data-ttu-id="226af-119">Para executar sessões remotas no Windows PowerShell 2,0, os computadores locais e remotos devem ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="226af-119">To run remote sessions on Windows PowerShell 2.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="226af-120">Windows PowerShell 2,0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="226af-120">Windows PowerShell 2.0 or later</span></span>
- <span data-ttu-id="226af-121">O Microsoft .NET Framework 2,0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="226af-121">The Microsoft .NET Framework 2.0 or later</span></span>
- <span data-ttu-id="226af-122">Gerenciamento Remoto do Windows 2,0</span><span class="sxs-lookup"><span data-stu-id="226af-122">Windows Remote Management 2.0</span></span>

<span data-ttu-id="226af-123">Você pode criar sessões remotas entre computadores que executam o Windows PowerShell 2,0 e o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="226af-123">You can create remote sessions between computers running Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span> <span data-ttu-id="226af-124">No entanto, os recursos que são executados somente no Windows PowerShell 3,0, como a capacidade de desconectar e reconectar-se a sessões, estão disponíveis somente quando ambos os computadores executam o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="226af-124">However, features that run only on Windows PowerShell 3.0, such as the ability to disconnect and reconnect to sessions, are available only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="226af-125">Para localizar o número de versão de uma versão instalada do PowerShell, use a variável automática $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="226af-125">To find the version number of an installed version of PowerShell, use the $PSVersionTable automatic variable.</span></span>

<span data-ttu-id="226af-126">Gerenciamento Remoto do Windows (WinRM) 3,0 e Microsoft .NET Framework 4 estão incluídos no Windows 8, no Windows Server 2012 e em versões mais recentes do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="226af-126">Windows Remote Management (WinRM) 3.0 and Microsoft .NET Framework 4 are included in Windows 8, Windows Server 2012, and newer releases of the Windows operating system.</span></span> <span data-ttu-id="226af-127">O WinRM 3,0 está incluído no Windows Management Framework 3,0 para sistemas operacionais mais antigos.</span><span class="sxs-lookup"><span data-stu-id="226af-127">WinRM 3.0 is included in Windows Management Framework 3.0 for older operating systems.</span></span> <span data-ttu-id="226af-128">Se o computador não tiver a versão necessária do WinRM ou a estrutura de Microsoft .NET, a instalação falhará.</span><span class="sxs-lookup"><span data-stu-id="226af-128">If the computer does not have the required version of WinRM or the Microsoft .NET Framework, the installation fails.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="226af-129">PERMISSÕES DO USUÁRIO</span><span class="sxs-lookup"><span data-stu-id="226af-129">USER PERMISSIONS</span></span>

<span data-ttu-id="226af-130">Para criar sessões remotas e executar comandos remotos, por padrão, o usuário atual deve ser um membro do grupo Administradores no computador remoto ou fornecer as credenciais de um administrador.</span><span class="sxs-lookup"><span data-stu-id="226af-130">To create remote sessions and run remote commands, by default, the current user must be a member of the Administrators group on the remote computer or provide the credentials of an administrator.</span></span> <span data-ttu-id="226af-131">Caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="226af-131">Otherwise, the command fails.</span></span>

<span data-ttu-id="226af-132">As permissões necessárias para criar sessões e executar comandos em um computador remoto (ou em uma sessão remota no computador local) são estabelecidas pela configuração de sessão (também conhecida como "ponto de extremidade") no computador remoto ao qual a sessão se conecta.</span><span class="sxs-lookup"><span data-stu-id="226af-132">The permissions required to create sessions and run commands on a remote computer (or in a remote session on the local computer) are established by the session configuration (also known as an "endpoint") on the remote computer to which the session connects.</span></span> <span data-ttu-id="226af-133">Especificamente, o descritor de segurança na configuração da sessão determina quem tem acesso à configuração de sessão e quem pode usá-la para se conectar.</span><span class="sxs-lookup"><span data-stu-id="226af-133">Specifically, the security descriptor on the session configuration determines who has access to the session configuration and who can use it to connect.</span></span>

<span data-ttu-id="226af-134">Os descritores de segurança nas configurações de sessão padrão, Microsoft. PowerShell, Microsoft. PowerShell32 e Microsoft. PowerShell. Workflow, permitem acesso somente aos membros do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="226af-134">The security descriptors on the default session configurations, Microsoft.PowerShell, Microsoft.PowerShell32, and Microsoft.PowerShell.Workflow, allow access only to members of the Administrators group.</span></span>

<span data-ttu-id="226af-135">Se o usuário atual não tiver permissão para usar a configuração de sessão, o comando para executar um comando (que usa uma sessão temporária) ou criar uma sessão persistente no computador remoto falhará.</span><span class="sxs-lookup"><span data-stu-id="226af-135">If the current user doesn't have permission to use the session configuration, the command to run a command (which uses a temporary session) or create a persistent session on the remote computer fails.</span></span> <span data-ttu-id="226af-136">O usuário pode usar o parâmetro ConfigurationName de cmdlets que criam sessões para selecionar uma configuração de sessão diferente, se houver uma disponível.</span><span class="sxs-lookup"><span data-stu-id="226af-136">The user can use the ConfigurationName parameter of cmdlets that create sessions to select a different session configuration, if one is available.</span></span>

<span data-ttu-id="226af-137">Os membros do grupo Administradores em um computador podem determinar quem tem permissão para se conectar ao computador remotamente, alterando os descritores de segurança nas configurações de sessão padrão e criando novas configurações de sessão com descritores de segurança diferentes.</span><span class="sxs-lookup"><span data-stu-id="226af-137">Members of the Administrators group on a computer can determine who has permission to connect to the computer remotely by changing the security descriptors on the default session configurations and by creating new session configurations with different security descriptors.</span></span>

<span data-ttu-id="226af-138">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="226af-138">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="windows-network-locations"></a><span data-ttu-id="226af-139">LOCAIS DE REDE DO WINDOWS</span><span class="sxs-lookup"><span data-stu-id="226af-139">WINDOWS NETWORK LOCATIONS</span></span>

<span data-ttu-id="226af-140">A partir do Windows PowerShell 3,0, o cmdlet Enable-PSRemoting pode habilitar a comunicação remota em versões de cliente e servidor do Windows em redes privadas, de domínio e públicas.</span><span class="sxs-lookup"><span data-stu-id="226af-140">Beginning in Windows PowerShell 3.0, the Enable-PSRemoting cmdlet can enable remoting on client and server versions of Windows on private, domain, and public networks.</span></span>

<span data-ttu-id="226af-141">Em versões de servidor do Windows com redes privadas e de domínio, o cmdlet Enable-PSRemoting cria regras de firewall que permitem acesso remoto irrestrito.</span><span class="sxs-lookup"><span data-stu-id="226af-141">On server versions of Windows with private and domain networks, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span> <span data-ttu-id="226af-142">Ele também cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="226af-142">It also creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="226af-143">Essa regra de firewall de sub-rede local é habilitada por padrão nas versões de servidor do Windows em redes públicas, mas Enable-PSRemoting reaplica a regra caso ela tenha sido alterada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="226af-143">This local subnet firewall rule is enabled by default on server versions of Windows on public networks, but Enable-PSRemoting reapplies the rule in case it was changed or deleted.</span></span>

<span data-ttu-id="226af-144">Em versões de cliente do Windows com redes privadas e de domínio, por padrão, o cmdlet Enable-PSRemoting cria regras de firewall que permitem acesso remoto irrestrito.</span><span class="sxs-lookup"><span data-stu-id="226af-144">On client versions of Windows with private and domain networks, by default, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span>

<span data-ttu-id="226af-145">Para habilitar a comunicação remota em versões de cliente do Windows com redes públicas, use o parâmetro SkipNetworkProfileCheck do cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="226af-145">To enable remoting on client versions of Windows with public networks, use the SkipNetworkProfileCheck parameter of the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="226af-146">Ele cria uma regra de firewall que permite o acesso remoto somente de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="226af-146">It creates a firewall rule that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="226af-147">Para remover a restrição de sub-rede local em redes públicas e permitir o acesso remoto de todos os locais nas versões de cliente e servidor do Windows, use o cmdlet Set-NetFirewallRule no módulo NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="226af-147">To remove the local subnet restriction on public networks and allow remote access from all locations on client and server versions of Windows, use the Set-NetFirewallRule cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="226af-148">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="226af-148">Run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="226af-149">No Windows PowerShell 2,0, em versões de servidor do Windows, Enable-PSRemoting cria regras de firewall que permitem o acesso remoto em todas as redes.</span><span class="sxs-lookup"><span data-stu-id="226af-149">In Windows PowerShell 2.0, on server versions of Windows, Enable-PSRemoting creates firewall rules that permit remote access on all networks.</span></span>

<span data-ttu-id="226af-150">No Windows PowerShell 2,0, em versões de cliente do Windows, Enable-PSRemoting cria regras de firewall somente em redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="226af-150">In Windows PowerShell 2.0, on client versions of Windows, Enable-PSRemoting creates firewall rules only on private and domain networks.</span></span> <span data-ttu-id="226af-151">Se o local de rede for público, Enable-PSRemoting falhará.</span><span class="sxs-lookup"><span data-stu-id="226af-151">If the network location is public, Enable-PSRemoting fails.</span></span>

## <a name="run-as-administrator"></a><span data-ttu-id="226af-152">EXECUTAR COMO ADMINISTRADOR</span><span class="sxs-lookup"><span data-stu-id="226af-152">RUN AS ADMINISTRATOR</span></span>

<span data-ttu-id="226af-153">São necessários privilégios de administrador para as seguintes operações de comunicação remota:</span><span class="sxs-lookup"><span data-stu-id="226af-153">Administrator privileges are required for the following remoting operations:</span></span>

- <span data-ttu-id="226af-154">Estabelecendo uma conexão remota com o computador local.</span><span class="sxs-lookup"><span data-stu-id="226af-154">Establishing a remote connection to the local computer.</span></span> <span data-ttu-id="226af-155">Isso é normalmente conhecido como um cenário de "Loopback".</span><span class="sxs-lookup"><span data-stu-id="226af-155">This is commonly known as a "loopback" scenario.</span></span>

- <span data-ttu-id="226af-156">Gerenciamento de configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="226af-156">Managing session configurations on the local computer.</span></span>

- <span data-ttu-id="226af-157">Exibir e alterar as configurações de WS-Management no computador local.</span><span class="sxs-lookup"><span data-stu-id="226af-157">Viewing and changing WS-Management settings on the local computer.</span></span> <span data-ttu-id="226af-158">Essas são as configurações no nó LocalHost da unidade WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="226af-158">These are the settings in the LocalHost node of the WSMAN: drive.</span></span>

<span data-ttu-id="226af-159">Para executar essas tarefas, você deve iniciar o PowerShell com a opção "executar como administrador", mesmo se você for um membro do grupo de administradores no computador local.</span><span class="sxs-lookup"><span data-stu-id="226af-159">To perform these tasks, you must start PowerShell with the "Run as administrator" option even if you are a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="226af-160">No Windows 7 e no Windows Server 2008 R2, para iniciar o Windows PowerShell com a opção "executar como administrador":</span><span class="sxs-lookup"><span data-stu-id="226af-160">In Windows 7 and in Windows Server 2008 R2, to start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="226af-161">Clique em Iniciar, em todos os programas, em acessórios e, em seguida, clique na pasta Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-161">Click Start, click All Programs, click Accessories, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="226af-162">Clique com o botão direito do mouse em Windows PowerShell e clique em "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="226af-162">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="226af-163">Para iniciar o Windows PowerShell com a opção "executar como administrador":</span><span class="sxs-lookup"><span data-stu-id="226af-163">To start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="226af-164">Clique em Iniciar, todos os programas e, em seguida, clique na pasta Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-164">Click Start, click All Programs, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="226af-165">Clique com o botão direito do mouse em Windows PowerShell e clique em "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="226af-165">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="226af-166">A opção "executar como administrador" também está disponível em outras entradas do Windows Explorer para o Windows PowerShell, incluindo atalhos.</span><span class="sxs-lookup"><span data-stu-id="226af-166">The "Run as administrator" option is also available in other Windows Explorer entries for Windows PowerShell, including shortcuts.</span></span> <span data-ttu-id="226af-167">Basta clicar com o botão direito do mouse no item e clicar em "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="226af-167">Just right-click the item, and then click "Run as administrator".</span></span>

<span data-ttu-id="226af-168">Quando você inicia o Windows PowerShell de outro programa, como Cmd.exe, use a opção "executar como administrador" para iniciar o programa.</span><span class="sxs-lookup"><span data-stu-id="226af-168">When you start Windows PowerShell from another program such as Cmd.exe, use the "Run as administrator" option to start the program.</span></span>

## <a name="how-to-configure-your-computer-for-remoting"></a><span data-ttu-id="226af-169">COMO CONFIGURAR SEU COMPUTADOR PARA COMUNICAÇÃO REMOTA</span><span class="sxs-lookup"><span data-stu-id="226af-169">HOW TO CONFIGURE YOUR COMPUTER FOR REMOTING</span></span>

<span data-ttu-id="226af-170">Os computadores que executam todas as versões com suporte do Windows podem estabelecer conexões remotas e executar comandos remotos no PowerShell sem nenhuma configuração.</span><span class="sxs-lookup"><span data-stu-id="226af-170">Computers running all supported versions of Windows can establish remote connections to and run remote commands in PowerShell without any configuration.</span></span> <span data-ttu-id="226af-171">No entanto, para receber conexões e permitir que os usuários criem sessões locais e remotas do PowerShell gerenciadas pelo usuário ("PSSessions") e executem comandos no computador local, você deve habilitar a comunicação remota do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="226af-171">However, to receive connections, and allow users to create local and remote user-managed PowerShell sessions ("PSSessions") and run commands on the local computer, you must enable PowerShell remoting on the computer.</span></span>

<span data-ttu-id="226af-172">O Windows Server 2012 e versões mais recentes do Windows Server são habilitados para a comunicação remota do PowerShell por padrão.</span><span class="sxs-lookup"><span data-stu-id="226af-172">Windows Server 2012 and newer releases of Windows Server are enabled for PowerShell remoting by default.</span></span> <span data-ttu-id="226af-173">Se as configurações forem alteradas, você poderá restaurar as configurações padrão executando o cmdlet Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="226af-173">If the settings are changed, you can restore the default settings by running the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="226af-174">Em todas as outras versões com suporte do Windows, você precisa executar o cmdlet Enable-PSRemoting para habilitar a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="226af-174">On all other supported versions of Windows, you need to run the Enable-PSRemoting cmdlet to enable PowerShell remoting.</span></span>

<span data-ttu-id="226af-175">Os recursos de comunicação remota do PowerShell têm suporte do serviço WinRM, que é a implementação da Microsoft do protocolo WS-Management (Web Services for Management).</span><span class="sxs-lookup"><span data-stu-id="226af-175">The remoting features of PowerShell are supported by the WinRM service, which is the Microsoft implementation of the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="226af-176">Ao habilitar a comunicação remota do PowerShell, você altera a configuração padrão de WS-Management e adiciona a configuração do sistema que permite que os usuários se conectem ao WS-Management.</span><span class="sxs-lookup"><span data-stu-id="226af-176">When you enable PowerShell remoting, you change the default configuration of WS-Management and add system configuration that allow users to connect to WS-Management.</span></span>

<span data-ttu-id="226af-177">Para configurar o PowerShell para receber comandos remotos:</span><span class="sxs-lookup"><span data-stu-id="226af-177">To configure PowerShell to receive remote commands:</span></span>

1. <span data-ttu-id="226af-178">Inicie o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="226af-178">Start PowerShell with the "Run as administrator" option.</span></span>
2. <span data-ttu-id="226af-179">No prompt de comando, digite: `Enable-PSRemoting`</span><span class="sxs-lookup"><span data-stu-id="226af-179">At the command prompt, type: `Enable-PSRemoting`</span></span>

<span data-ttu-id="226af-180">Para verificar se a comunicação remota está configurada corretamente, execute um comando de teste, como o comando a seguir, que cria uma sessão remota no computador local.</span><span class="sxs-lookup"><span data-stu-id="226af-180">To verify that remoting is configured correctly, run a test command such as the following command, which creates a remote session on the local computer.</span></span>

```powershell
New-PSSession
```

<span data-ttu-id="226af-181">Se a comunicação remota estiver configurada corretamente, o comando criará uma sessão no computador local e retornará um objeto que representa a sessão.</span><span class="sxs-lookup"><span data-stu-id="226af-181">If remoting is configured correctly, the command will create a session on the local computer and return an object that represents the session.</span></span> <span data-ttu-id="226af-182">A saída deve se parecer com a seguinte saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="226af-182">The output should resemble the following sample output:</span></span>

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

<span data-ttu-id="226af-183">Se o comando falhar, para obter assistência, consulte [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="226af-183">If the command fails, for assistance, see [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span></span>

## <a name="understand-policies"></a><span data-ttu-id="226af-184">ENTENDER AS POLÍTICAS</span><span class="sxs-lookup"><span data-stu-id="226af-184">UNDERSTAND POLICIES</span></span>

<span data-ttu-id="226af-185">Quando você trabalha remotamente, usa duas instâncias do PowerShell, uma no computador local e outra no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="226af-185">When you work remotely, you use two instances of PowerShell, one on the local computer and one on the remote computer.</span></span> <span data-ttu-id="226af-186">Como resultado, seu trabalho é afetado pelas políticas do Windows e pelas políticas do PowerShell nos computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="226af-186">As a result, your work is affected by the Windows policies and the PowerShell policies on the local and remote computers.</span></span>

<span data-ttu-id="226af-187">Em geral, antes de se conectar e enquanto você estiver estabelecendo a conexão, as políticas no computador local estarão em vigor.</span><span class="sxs-lookup"><span data-stu-id="226af-187">In general, before you connect and as you are establishing the connection, the policies on the local computer are in effect.</span></span> <span data-ttu-id="226af-188">Quando você estiver usando a conexão, as políticas no computador remoto estarão em vigor.</span><span class="sxs-lookup"><span data-stu-id="226af-188">When you are using the connection, the policies on the remote computer are in effect.</span></span>

## <a name="basic-authentication-limitations-on-linux-and-macos"></a><span data-ttu-id="226af-189">Limitações de autenticação básica no Linux e no macOS</span><span class="sxs-lookup"><span data-stu-id="226af-189">Basic Authentication Limitations on Linux and macOS</span></span>

<span data-ttu-id="226af-190">Ao conectar-se de um sistema Linux ou macOS ao Windows, não há suporte para a autenticação básica sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="226af-190">When connecting from a Linux or macOS system to Windows, Basic Authentication over HTTP is not supported.</span></span> <span data-ttu-id="226af-191">A autenticação básica pode ser usada em HTTPS por meio da instalação de um certificado no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="226af-191">Basic Authentication can be used over HTTPS by installing a certificate on the target server.</span></span> <span data-ttu-id="226af-192">O certificado deve ter um nome CN que corresponda ao nome de host, não expirado ou revogado.</span><span class="sxs-lookup"><span data-stu-id="226af-192">The certificate must have a CN name that matches the hostname, is not expired or revoked.</span></span> <span data-ttu-id="226af-193">Um certificado autoassinado pode ser usado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="226af-193">A self-signed certificate may be used for testing purposes.</span></span>

<span data-ttu-id="226af-194">Consulte [como: configurar o WinRM para https](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="226af-194">See [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) for additional details.</span></span>

<span data-ttu-id="226af-195">O comando a seguir, executado em um prompt de comando com privilégios elevados, configurará o ouvinte HTTPS no Windows com o certificado instalado.</span><span class="sxs-lookup"><span data-stu-id="226af-195">The following command, run from an elevated command prompt, will configure the HTTPS listener on Windows with the installed certificate.</span></span>

```powershell
$hostinfo = '@{Hostname="<DNS_NAME>"; CertificateThumbprint="<THUMBPRINT>"}'
winrm create winrm/config/Listener?Address=*+Transport=HTTPS $hostinfo
```

<span data-ttu-id="226af-196">No lado do Linux ou do macOS, selecione básico para autenticação e-UseSSl.</span><span class="sxs-lookup"><span data-stu-id="226af-196">On the Linux or macOS side, select Basic for authentication and -UseSSl.</span></span>

> <span data-ttu-id="226af-197">Observação: a autenticação básica não pode ser usada com contas de domínio; uma conta local é necessária e a conta deve estar no grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="226af-197">NOTE: Basic authentication cannot be used with domain accounts; a local account is required and the account must be in the Administrators group.</span></span>

```powershell
# The specified local user must have administrator rights on the target machine.
# Specify the unqualified username.
$cred = Get-Credential username
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Basic -UseSSL
```

<span data-ttu-id="226af-198">Uma alternativa à autenticação básica por HTTPS é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="226af-198">An alternative to Basic Authentication over HTTPS is Negotiate.</span></span> <span data-ttu-id="226af-199">Isso resulta na autenticação NTLM entre o cliente e o servidor e a carga é criptografada por HTTP.</span><span class="sxs-lookup"><span data-stu-id="226af-199">This results in NTLM authentication between the client and server and payload is encrypted over HTTP.</span></span>

<span data-ttu-id="226af-200">O seguinte ilustra o uso de Negotiate com New-PSSession:</span><span class="sxs-lookup"><span data-stu-id="226af-200">The following illustrates using Negotiate with New-PSSession:</span></span>

```powershell
# The specified user must have administrator rights on the target machine.
$cred = Get-Credential username@hostname
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Negotiate
```

> [!NOTE]
> <span data-ttu-id="226af-201">O Windows Server requer uma configuração de registro adicional para permitir que os administradores, além do administrador interno, se conectem usando NTLM.</span><span class="sxs-lookup"><span data-stu-id="226af-201">Windows Server requires an additional registry setting to enable administrators, other than the built in administrator, to connect using NTLM.</span></span>
> <span data-ttu-id="226af-202">Consulte a configuração do Registro LocalAccountTokenFilterPolicy em negociar autenticação em [autenticação para conexões remotas](/windows/win32/winrm/authentication-for-remote-connections)</span><span class="sxs-lookup"><span data-stu-id="226af-202">Refer to the LocalAccountTokenFilterPolicy registry setting under Negotiate Authentication in [Authentication for Remote Connections](/windows/win32/winrm/authentication-for-remote-connections)</span></span>

## <a name="see-also"></a><span data-ttu-id="226af-203">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="226af-203">SEE ALSO</span></span>

[<span data-ttu-id="226af-204">about_Remote</span><span class="sxs-lookup"><span data-stu-id="226af-204">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="226af-205">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="226af-205">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="226af-206">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="226af-206">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="226af-207">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="226af-207">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="226af-208">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="226af-208">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="226af-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="226af-209">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
