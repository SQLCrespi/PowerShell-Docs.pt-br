---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: f74fe88cfb1d89e2f21d3f85e5c604d75f8ac55d
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "93194842"
---
# <span data-ttu-id="4c38d-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4c38d-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="4c38d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4c38d-104">SYNOPSIS</span></span>
<span data-ttu-id="4c38d-105">Configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4c38d-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="4c38d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c38d-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4c38d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c38d-107">DESCRIPTION</span></span>

<span data-ttu-id="4c38d-108">O `Enable-PSRemoting` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="4c38d-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span> <span data-ttu-id="4c38d-109">No momento, há suporte para a comunicação remota do PowerShell baseada em WS-Management apenas na plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="4c38d-109">WS-Management based PowerShell remoting is currently supported only on Windows platform.</span></span>

<span data-ttu-id="4c38d-110">A comunicação remota do PowerShell é habilitada por padrão nas plataformas do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4c38d-110">PowerShell remoting is enabled by default on Windows Server platforms.</span></span> <span data-ttu-id="4c38d-111">Você pode usar o `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell em outras versões com suporte do Windows e para reabilitar a comunicação remota se ela for desabilitada.</span><span class="sxs-lookup"><span data-stu-id="4c38d-111">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting if it becomes disabled.</span></span>

<span data-ttu-id="4c38d-112">Você precisa executar esse comando apenas uma vez em cada computador que receberá comandos.</span><span class="sxs-lookup"><span data-stu-id="4c38d-112">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="4c38d-113">Você não precisa executá-lo em computadores que só enviam comandos.</span><span class="sxs-lookup"><span data-stu-id="4c38d-113">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="4c38d-114">Como a configuração inicia os ouvintes para aceitar conexões remotas, é prudente executá-lo somente onde for necessário.</span><span class="sxs-lookup"><span data-stu-id="4c38d-114">Because the configuration starts listeners to accept remote connections, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="4c38d-115">Habilitar a comunicação remota do PowerShell em versões de cliente do Windows quando o computador está em uma rede pública normalmente não é permitido, mas você pode ignorar essa restrição usando o parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-115">Enabling PowerShell remoting on client versions of Windows when the computer is on a public network is normally disallowed, but you can skip this restriction by using the **SkipNetworkProfileCheck** parameter.</span></span> <span data-ttu-id="4c38d-116">Para obter mais informações, consulte a descrição do parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-116">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="4c38d-117">Várias instalações do PowerShell podem existir lado a lado em um único computador.</span><span class="sxs-lookup"><span data-stu-id="4c38d-117">Multiple PowerShell installations can exist side-by-side on a single computer.</span></span> <span data-ttu-id="4c38d-118">`Enable-PSRemoting`A execução irá configurar um ponto de extremidade de comunicação remota para a versão de instalação específica em que você está executando o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c38d-118">Running `Enable-PSRemoting` will configure a remoting endpoint for the specific installation version that you are running the cmdlet in.</span></span> <span data-ttu-id="4c38d-119">Portanto, se você executar `Enable-PSRemoting` o powershell 6,2 em execução, um ponto de extremidade de comunicação remota será configurado para executar o powershell 6,2.</span><span class="sxs-lookup"><span data-stu-id="4c38d-119">So if you run `Enable-PSRemoting` while running PowerShell 6.2, a remoting endpoint will be configured that runs PowerShell 6.2.</span></span> <span data-ttu-id="4c38d-120">Se você executar `Enable-PSRemoting` o PowerShell 7-Preview em execução, um ponto de extremidade de comunicação remota será configurado para executar o PowerShell 7-Preview.</span><span class="sxs-lookup"><span data-stu-id="4c38d-120">If you run `Enable-PSRemoting` while running PowerShell 7-preview, a remoting endpoint will be configured that runs PowerShell 7-preview.</span></span>

<span data-ttu-id="4c38d-121">`Enable-PSRemoting` cria duas configurações de ponto de extremidade de comunicação remota conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c38d-121">`Enable-PSRemoting` creates two remoting endpoint configurations as needed.</span></span> <span data-ttu-id="4c38d-122">Se as configurações do ponto de extremidade já existirem, elas serão simplesmente habilitadas.</span><span class="sxs-lookup"><span data-stu-id="4c38d-122">If the endpoint configurations already exist, then they are simply ensured to be enabled.</span></span> <span data-ttu-id="4c38d-123">As configurações criadas são idênticas, mas têm nomes diferentes.</span><span class="sxs-lookup"><span data-stu-id="4c38d-123">The created configurations are identical but have different names.</span></span> <span data-ttu-id="4c38d-124">Uma terá um nome simples correspondente à versão do PowerShell que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="4c38d-124">One will have a simple name corresponding to the PowerShell version that hosts the session.</span></span> <span data-ttu-id="4c38d-125">O outro nome de configuração contém informações mais detalhadas sobre a versão do PowerShell que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="4c38d-125">The other configuration name contains more detailed information about the PowerShell version which hosts the session.</span></span> <span data-ttu-id="4c38d-126">Por exemplo, ao executar `Enable-PSRemoting` no PowerShell 6,2, você obterá dois pontos de extremidade configurados chamados **PowerShell. 6** , **PowerShell. 6.2.2** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-126">For example, when running `Enable-PSRemoting` in PowerShell 6.2, you will get two configured endpoints named **PowerShell.6** , **PowerShell.6.2.2** .</span></span>
<span data-ttu-id="4c38d-127">Isso permite que você crie uma conexão com a versão mais recente do host do PowerShell 6 usando o nome simples **PowerShell. 6** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-127">This allows you to create a connection to the latest PowerShell 6 host version by using the simple name **PowerShell.6** .</span></span> <span data-ttu-id="4c38d-128">Ou você pode se conectar a uma versão específica do host do PowerShell usando o nome mais longo **PowerShell. 6.2.2** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-128">Or you can connect to a specific PowerShell host version by using the longer name **PowerShell.6.2.2** .</span></span>

<span data-ttu-id="4c38d-129">Para usar os pontos de extremidade de comunicação remota habilitados recentemente, você deve especificá-los pelo nome com o parâmetro **ConfigurationName** ao criar uma conexão remota usando os `Invoke-Command` `New-PSSession` `Enter-PSSession` cmdlets,,.</span><span class="sxs-lookup"><span data-stu-id="4c38d-129">To use the newly enabled remoting endpoints, you must specify them by name with the **ConfigurationName** parameter when creating a remote connection using the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.</span></span> <span data-ttu-id="4c38d-130">Para obter mais informações, consulte o exemplo 4.</span><span class="sxs-lookup"><span data-stu-id="4c38d-130">For more information, see Example 4.</span></span>

<span data-ttu-id="4c38d-131">O `Enable-PSRemoting` cmdlet executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="4c38d-131">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="4c38d-132">Executa o cmdlet [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , que executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4c38d-132">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="4c38d-133">Inicia o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="4c38d-133">Starts the WinRM service.</span></span>
  - <span data-ttu-id="4c38d-134">Define o tipo de inicialização no serviço WinRM como automático.</span><span class="sxs-lookup"><span data-stu-id="4c38d-134">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="4c38d-135">Cria um ouvinte para aceitar solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="4c38d-135">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="4c38d-136">Habilita uma exceção de firewall para WS-Management comunicações.</span><span class="sxs-lookup"><span data-stu-id="4c38d-136">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="4c38d-137">Cria as configurações de ponto de extremidade de sessão de nome longo e simples, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4c38d-137">Creates the simple and long name session endpoint configurations if needed.</span></span>
  - <span data-ttu-id="4c38d-138">Habilita todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="4c38d-138">Enables all session configurations.</span></span>
  - <span data-ttu-id="4c38d-139">Altera o descritor de segurança de todas as configurações de sessão para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="4c38d-139">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="4c38d-140">Reinicia o serviço WinRM para tornar as alterações anteriores efetivas.</span><span class="sxs-lookup"><span data-stu-id="4c38d-140">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="4c38d-141">Para executar esse cmdlet na plataforma Windows, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="4c38d-141">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="4c38d-142">Este cmdlet não está disponível nas versões Linux ou MacOS do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c38d-142">This cmdlet is not available on Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="4c38d-143">Esse cmdlet não afeta as configurações de ponto de extremidade remoto criadas pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c38d-143">This cmdlet does not affect remote endpoint configurations created by Windows PowerShell.</span></span>
> <span data-ttu-id="4c38d-144">Ele só afeta os pontos de extremidade criados com o PowerShell versão 6 e superior.</span><span class="sxs-lookup"><span data-stu-id="4c38d-144">It only affects endpoints created with PowerShell version 6 and greater.</span></span> <span data-ttu-id="4c38d-145">Para habilitar e desabilitar pontos de extremidade de comunicação remota do PowerShell que são hospedados pelo Windows PowerShell, execute o `Enable-PSRemoting` cmdlet de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c38d-145">To enable and disable PowerShell remoting endpoints that are hosted by Windows PowerShell, run the `Enable-PSRemoting` cmdlet from within a Windows PowerShell session.</span></span>

## <span data-ttu-id="4c38d-146">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4c38d-146">EXAMPLES</span></span>

### <span data-ttu-id="4c38d-147">Exemplo 1: configurar um computador para receber comandos remotos</span><span class="sxs-lookup"><span data-stu-id="4c38d-147">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="4c38d-148">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4c38d-148">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="4c38d-149">Exemplo 2: configurar um computador para receber comandos remotos sem um prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="4c38d-149">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="4c38d-150">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4c38d-150">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="4c38d-151">O parâmetro **Force** suprime os prompts do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c38d-151">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="4c38d-152">Exemplo 3: permitir acesso remoto em clientes</span><span class="sxs-lookup"><span data-stu-id="4c38d-152">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="4c38d-153">Este exemplo mostra como permitir o acesso remoto de redes públicas em versões de cliente do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="4c38d-153">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="4c38d-154">O nome da regra de firewall pode ser diferente para diferentes versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c38d-154">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="4c38d-155">Use `Get-NetFirewallRule` para ver uma lista de regras.</span><span class="sxs-lookup"><span data-stu-id="4c38d-155">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="4c38d-156">Antes de habilitar a regra de firewall, exiba as configurações de segurança na regra para verificar se a configuração é apropriada para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4c38d-156">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="4c38d-157">Por padrão, o `Enable-PSRemoting` cria regras de rede que permitem o acesso remoto de redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="4c38d-157">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="4c38d-158">O comando usa o parâmetro **SkipNetworkProfileCheck** para permitir acesso remoto por meio de redes públicas contidas na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4c38d-158">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="4c38d-159">O comando especifica o parâmetro **Force** para suprimir as mensagens de confirmação.</span><span class="sxs-lookup"><span data-stu-id="4c38d-159">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="4c38d-160">O parâmetro **SkipNetworkProfileCheck** não afeta as versões de servidor do sistema operacional Windows, que permitem o acesso remoto de redes públicas na mesma sub-rede local por padrão.</span><span class="sxs-lookup"><span data-stu-id="4c38d-160">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="4c38d-161">O `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** adiciona uma regra de firewall que permite o acesso remoto de redes públicas de qualquer local remoto.</span><span class="sxs-lookup"><span data-stu-id="4c38d-161">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="4c38d-162">Isso inclui locais em sub-redes diferentes.</span><span class="sxs-lookup"><span data-stu-id="4c38d-162">This includes locations in different subnets.</span></span>

### <span data-ttu-id="4c38d-163">Exemplo 4: criar uma sessão remota para a configuração de ponto de extremidade habilitada recentemente</span><span class="sxs-lookup"><span data-stu-id="4c38d-163">Example 4: Create a remote session to the newly enabled endpoint configuration</span></span>

<span data-ttu-id="4c38d-164">Este exemplo mostra como habilitar a comunicação remota do PowerShell em um computador, localizar os nomes de ponto de extremidade configurados e criar uma sessão remota para um dos pontos de extremidades.</span><span class="sxs-lookup"><span data-stu-id="4c38d-164">This example shows how to enable PowerShell remoting on a computer, find the configured endpoint names, and create a remote session to one of the endpoints.</span></span>

<span data-ttu-id="4c38d-165">O primeiro comando habilita a comunicação remota do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="4c38d-165">The first command enables PowerShell remoting on the computer.</span></span>

<span data-ttu-id="4c38d-166">O segundo comando lista as configurações do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4c38d-166">The second command lists the endpoint configurations.</span></span>

<span data-ttu-id="4c38d-167">O terceiro comando cria uma sessão remota do PowerShell para o mesmo computador, especificando o ponto de extremidade do **PowerShell. 6** por nome.</span><span class="sxs-lookup"><span data-stu-id="4c38d-167">The third command creates a remote PowerShell session to the same machine, specifying the **PowerShell.6** endpoint by name.</span></span> <span data-ttu-id="4c38d-168">A sessão remota será hospedada com a versão mais recente do PowerShell 6 (6.2.2).</span><span class="sxs-lookup"><span data-stu-id="4c38d-168">The remote session will be hosted with the latest PowerShell 6 version (6.2.2).</span></span>

<span data-ttu-id="4c38d-169">O último comando acessa a `$PSVersionTable` variável na sessão remota para exibir a versão do PowerShell que está hospedando a sessão.</span><span class="sxs-lookup"><span data-stu-id="4c38d-169">The last command accesses the `$PSVersionTable` variable in the remote session to display the PowerShell version that is hosting the session.</span></span>

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> <span data-ttu-id="4c38d-170">O nome da regra de firewall pode ser diferente dependendo da versão do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c38d-170">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="4c38d-171">Use o `Get-NetFirewallRule` cmdlet para listar os nomes das regras em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="4c38d-171">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="4c38d-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c38d-172">PARAMETERS</span></span>

### <span data-ttu-id="4c38d-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4c38d-173">-Confirm</span></span>

<span data-ttu-id="4c38d-174">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c38d-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4c38d-175">-Force</span><span class="sxs-lookup"><span data-stu-id="4c38d-175">-Force</span></span>

<span data-ttu-id="4c38d-176">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c38d-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4c38d-177">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="4c38d-177">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="4c38d-178">Indica que esse cmdlet habilita a comunicação remota em versões de cliente do sistema operacional Windows quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="4c38d-178">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="4c38d-179">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4c38d-179">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="4c38d-180">Esse parâmetro não afeta as versões de servidor do sistema operacional Windows, que, por padrão, têm uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="4c38d-180">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="4c38d-181">Se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4c38d-181">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="4c38d-182">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-182">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="4c38d-183">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4c38d-183">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4c38d-184">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4c38d-184">-WhatIf</span></span>

<span data-ttu-id="4c38d-185">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="4c38d-185">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4c38d-186">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="4c38d-186">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4c38d-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c38d-187">CommonParameters</span></span>

<span data-ttu-id="4c38d-188">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c38d-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c38d-189">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c38d-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c38d-190">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4c38d-190">INPUTS</span></span>

### <span data-ttu-id="4c38d-191">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4c38d-191">None</span></span>

<span data-ttu-id="4c38d-192">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4c38d-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4c38d-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4c38d-193">OUTPUTS</span></span>

### <span data-ttu-id="4c38d-194">System.String</span><span class="sxs-lookup"><span data-stu-id="4c38d-194">System.String</span></span>

<span data-ttu-id="4c38d-195">Esse cmdlet retorna cadeias de caracteres que descrevem seus resultados.</span><span class="sxs-lookup"><span data-stu-id="4c38d-195">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="4c38d-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4c38d-196">NOTES</span></span>

<span data-ttu-id="4c38d-197">Em versões de servidor do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto e cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4c38d-197">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="4c38d-198">Nas versões cliente do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto irrestrito.</span><span class="sxs-lookup"><span data-stu-id="4c38d-198">On client versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="4c38d-199">Para criar uma regra de firewall para redes públicas que permite acesso remoto por meio da mesma sub-rede local, use o parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-199">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="4c38d-200">Em versões de cliente ou servidor do sistema operacional Windows, para criar uma regra de firewall para redes públicas que remove a restrição de sub-rede local e permite o acesso remoto, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity para executar o seguinte comando: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="4c38d-200">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="4c38d-201">`Enable-PSRemoting` habilita todas as configurações de sessão definindo o valor da propriedade **habilitada** de todas as configurações de sessão como `$True` .</span><span class="sxs-lookup"><span data-stu-id="4c38d-201">`Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="4c38d-202">`Enable-PSRemoting` Remove as configurações de **Deny_All** e **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="4c38d-202">`Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="4c38d-203">Isso fornece acesso remoto a configurações de sessão que foram reservadas para uso local.</span><span class="sxs-lookup"><span data-stu-id="4c38d-203">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="4c38d-204">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4c38d-204">RELATED LINKS</span></span>

[<span data-ttu-id="4c38d-205">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c38d-205">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4c38d-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c38d-206">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="4c38d-207">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c38d-207">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4c38d-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c38d-208">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="4c38d-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c38d-209">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4c38d-210">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4c38d-210">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="4c38d-211">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="4c38d-211">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="4c38d-212">about_Remote</span><span class="sxs-lookup"><span data-stu-id="4c38d-212">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="4c38d-213">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="4c38d-213">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
