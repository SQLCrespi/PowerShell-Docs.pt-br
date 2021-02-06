---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: a3d9506a0fd2adbb9cc093fb24f99e922dc8a938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595369"
---
# <span data-ttu-id="5a670-102">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="5a670-102">Enable-PSRemoting</span></span>

## <span data-ttu-id="5a670-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5a670-103">SYNOPSIS</span></span>
<span data-ttu-id="5a670-104">Configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="5a670-104">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="5a670-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a670-105">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a670-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a670-106">DESCRIPTION</span></span>

<span data-ttu-id="5a670-107">O `Enable-PSRemoting` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="5a670-107">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span> <span data-ttu-id="5a670-108">No momento, há suporte para a comunicação remota do PowerShell baseada em WS-Management apenas na plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5a670-108">WS-Management based PowerShell remoting is currently supported only on Windows platform.</span></span>

<span data-ttu-id="5a670-109">A comunicação remota do PowerShell é habilitada por padrão nas plataformas do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5a670-109">PowerShell remoting is enabled by default on Windows Server platforms.</span></span> <span data-ttu-id="5a670-110">Você pode usar o `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell em outras versões com suporte do Windows e para reabilitar a comunicação remota se ela for desabilitada.</span><span class="sxs-lookup"><span data-stu-id="5a670-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting if it becomes disabled.</span></span>

<span data-ttu-id="5a670-111">Você precisa executar esse comando apenas uma vez em cada computador que receberá comandos.</span><span class="sxs-lookup"><span data-stu-id="5a670-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="5a670-112">Você não precisa executá-lo em computadores que só enviam comandos.</span><span class="sxs-lookup"><span data-stu-id="5a670-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="5a670-113">Como a configuração inicia os ouvintes para aceitar conexões remotas, é prudente executá-lo somente onde for necessário.</span><span class="sxs-lookup"><span data-stu-id="5a670-113">Because the configuration starts listeners to accept remote connections, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="5a670-114">Habilitar a comunicação remota do PowerShell em versões de cliente do Windows quando o computador está em uma rede pública normalmente não é permitido, mas você pode ignorar essa restrição usando o parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="5a670-114">Enabling PowerShell remoting on client versions of Windows when the computer is on a public network is normally disallowed, but you can skip this restriction by using the **SkipNetworkProfileCheck** parameter.</span></span> <span data-ttu-id="5a670-115">Para obter mais informações, consulte a descrição do parâmetro **SkipNetworkProfileCheck**.</span><span class="sxs-lookup"><span data-stu-id="5a670-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="5a670-116">Várias instalações do PowerShell podem existir lado a lado em um único computador.</span><span class="sxs-lookup"><span data-stu-id="5a670-116">Multiple PowerShell installations can exist side-by-side on a single computer.</span></span> <span data-ttu-id="5a670-117">`Enable-PSRemoting`A execução irá configurar um ponto de extremidade de comunicação remota para a versão de instalação específica em que você está executando o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a670-117">Running `Enable-PSRemoting` will configure a remoting endpoint for the specific installation version that you are running the cmdlet in.</span></span> <span data-ttu-id="5a670-118">Portanto, se você executar `Enable-PSRemoting` o powershell 6,2 em execução, um ponto de extremidade de comunicação remota será configurado para executar o powershell 6,2.</span><span class="sxs-lookup"><span data-stu-id="5a670-118">So if you run `Enable-PSRemoting` while running PowerShell 6.2, a remoting endpoint will be configured that runs PowerShell 6.2.</span></span> <span data-ttu-id="5a670-119">Se você executar `Enable-PSRemoting` o PowerShell 7-Preview em execução, um ponto de extremidade de comunicação remota será configurado para executar o PowerShell 7-Preview.</span><span class="sxs-lookup"><span data-stu-id="5a670-119">If you run `Enable-PSRemoting` while running PowerShell 7-preview, a remoting endpoint will be configured that runs PowerShell 7-preview.</span></span>

<span data-ttu-id="5a670-120">`Enable-PSRemoting` cria duas configurações de ponto de extremidade de comunicação remota conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5a670-120">`Enable-PSRemoting` creates two remoting endpoint configurations as needed.</span></span> <span data-ttu-id="5a670-121">Se as configurações do ponto de extremidade já existirem, elas serão simplesmente habilitadas.</span><span class="sxs-lookup"><span data-stu-id="5a670-121">If the endpoint configurations already exist, then they are simply ensured to be enabled.</span></span> <span data-ttu-id="5a670-122">As configurações criadas são idênticas, mas têm nomes diferentes.</span><span class="sxs-lookup"><span data-stu-id="5a670-122">The created configurations are identical but have different names.</span></span> <span data-ttu-id="5a670-123">Uma terá um nome simples correspondente à versão do PowerShell que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="5a670-123">One will have a simple name corresponding to the PowerShell version that hosts the session.</span></span> <span data-ttu-id="5a670-124">O outro nome de configuração contém informações mais detalhadas sobre a versão do PowerShell que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="5a670-124">The other configuration name contains more detailed information about the PowerShell version which hosts the session.</span></span> <span data-ttu-id="5a670-125">Por exemplo, ao executar `Enable-PSRemoting` no PowerShell 6,2, você obterá dois pontos de extremidade configurados chamados **PowerShell. 6**, **PowerShell. 6.2.2**.</span><span class="sxs-lookup"><span data-stu-id="5a670-125">For example, when running `Enable-PSRemoting` in PowerShell 6.2, you will get two configured endpoints named **PowerShell.6**, **PowerShell.6.2.2**.</span></span>
<span data-ttu-id="5a670-126">Isso permite que você crie uma conexão com a versão mais recente do host do PowerShell 6 usando o nome simples **PowerShell. 6**.</span><span class="sxs-lookup"><span data-stu-id="5a670-126">This allows you to create a connection to the latest PowerShell 6 host version by using the simple name **PowerShell.6**.</span></span> <span data-ttu-id="5a670-127">Ou você pode se conectar a uma versão específica do host do PowerShell usando o nome mais longo **PowerShell. 6.2.2**.</span><span class="sxs-lookup"><span data-stu-id="5a670-127">Or you can connect to a specific PowerShell host version by using the longer name **PowerShell.6.2.2**.</span></span>

<span data-ttu-id="5a670-128">Para usar os pontos de extremidade de comunicação remota habilitados recentemente, você deve especificá-los pelo nome com o parâmetro **ConfigurationName** ao criar uma conexão remota usando os `Invoke-Command` `New-PSSession` `Enter-PSSession` cmdlets,,.</span><span class="sxs-lookup"><span data-stu-id="5a670-128">To use the newly enabled remoting endpoints, you must specify them by name with the **ConfigurationName** parameter when creating a remote connection using the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.</span></span> <span data-ttu-id="5a670-129">Para obter mais informações, consulte o exemplo 4.</span><span class="sxs-lookup"><span data-stu-id="5a670-129">For more information, see Example 4.</span></span>

<span data-ttu-id="5a670-130">O `Enable-PSRemoting` cmdlet executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="5a670-130">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="5a670-131">Executa o cmdlet [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , que executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5a670-131">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="5a670-132">Inicia o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="5a670-132">Starts the WinRM service.</span></span>
  - <span data-ttu-id="5a670-133">Define o tipo de inicialização no serviço WinRM como automático.</span><span class="sxs-lookup"><span data-stu-id="5a670-133">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="5a670-134">Cria um ouvinte para aceitar solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="5a670-134">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="5a670-135">Habilita uma exceção de firewall para WS-Management comunicações.</span><span class="sxs-lookup"><span data-stu-id="5a670-135">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="5a670-136">Cria as configurações de ponto de extremidade de sessão de nome longo e simples, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5a670-136">Creates the simple and long name session endpoint configurations if needed.</span></span>
  - <span data-ttu-id="5a670-137">Habilita todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="5a670-137">Enables all session configurations.</span></span>
  - <span data-ttu-id="5a670-138">Altera o descritor de segurança de todas as configurações de sessão para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="5a670-138">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="5a670-139">Reinicia o serviço WinRM para tornar as alterações anteriores efetivas.</span><span class="sxs-lookup"><span data-stu-id="5a670-139">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="5a670-140">Para executar esse cmdlet na plataforma Windows, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="5a670-140">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="5a670-141">Este cmdlet não está disponível nas versões Linux ou MacOS do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a670-141">This cmdlet is not available on Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="5a670-142">Esse cmdlet não afeta as configurações de ponto de extremidade remoto criadas pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a670-142">This cmdlet does not affect remote endpoint configurations created by Windows PowerShell.</span></span>
> <span data-ttu-id="5a670-143">Ele só afeta os pontos de extremidade criados com o PowerShell versão 6 e superior.</span><span class="sxs-lookup"><span data-stu-id="5a670-143">It only affects endpoints created with PowerShell version 6 and greater.</span></span> <span data-ttu-id="5a670-144">Para habilitar e desabilitar pontos de extremidade de comunicação remota do PowerShell que são hospedados pelo Windows PowerShell, execute o `Enable-PSRemoting` cmdlet de dentro de uma sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a670-144">To enable and disable PowerShell remoting endpoints that are hosted by Windows PowerShell, run the `Enable-PSRemoting` cmdlet from within a Windows PowerShell session.</span></span>

## <span data-ttu-id="5a670-145">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5a670-145">EXAMPLES</span></span>

### <span data-ttu-id="5a670-146">Exemplo 1: configurar um computador para receber comandos remotos</span><span class="sxs-lookup"><span data-stu-id="5a670-146">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="5a670-147">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="5a670-147">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="5a670-148">Exemplo 2: configurar um computador para receber comandos remotos sem um prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="5a670-148">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="5a670-149">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="5a670-149">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="5a670-150">O parâmetro **Force** suprime os prompts do usuário.</span><span class="sxs-lookup"><span data-stu-id="5a670-150">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="5a670-151">Exemplo 3: permitir acesso remoto em clientes</span><span class="sxs-lookup"><span data-stu-id="5a670-151">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="5a670-152">Este exemplo mostra como permitir o acesso remoto de redes públicas em versões de cliente do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="5a670-152">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="5a670-153">O nome da regra de firewall pode ser diferente para diferentes versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="5a670-153">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="5a670-154">Use `Get-NetFirewallRule` para ver uma lista de regras.</span><span class="sxs-lookup"><span data-stu-id="5a670-154">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="5a670-155">Antes de habilitar a regra de firewall, exiba as configurações de segurança na regra para verificar se a configuração é apropriada para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="5a670-155">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

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

<span data-ttu-id="5a670-156">Por padrão, o `Enable-PSRemoting` cria regras de rede que permitem o acesso remoto de redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="5a670-156">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="5a670-157">O comando usa o parâmetro **SkipNetworkProfileCheck** para permitir acesso remoto por meio de redes públicas contidas na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="5a670-157">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="5a670-158">O comando especifica o parâmetro **Force** para suprimir as mensagens de confirmação.</span><span class="sxs-lookup"><span data-stu-id="5a670-158">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="5a670-159">O parâmetro **SkipNetworkProfileCheck** não afeta as versões de servidor do sistema operacional Windows, que permitem o acesso remoto de redes públicas na mesma sub-rede local por padrão.</span><span class="sxs-lookup"><span data-stu-id="5a670-159">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="5a670-160">O `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** adiciona uma regra de firewall que permite o acesso remoto de redes públicas de qualquer local remoto.</span><span class="sxs-lookup"><span data-stu-id="5a670-160">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="5a670-161">Isso inclui locais em sub-redes diferentes.</span><span class="sxs-lookup"><span data-stu-id="5a670-161">This includes locations in different subnets.</span></span>

### <span data-ttu-id="5a670-162">Exemplo 4: criar uma sessão remota para a configuração de ponto de extremidade habilitada recentemente</span><span class="sxs-lookup"><span data-stu-id="5a670-162">Example 4: Create a remote session to the newly enabled endpoint configuration</span></span>

<span data-ttu-id="5a670-163">Este exemplo mostra como habilitar a comunicação remota do PowerShell em um computador, localizar os nomes de ponto de extremidade configurados e criar uma sessão remota para um dos pontos de extremidades.</span><span class="sxs-lookup"><span data-stu-id="5a670-163">This example shows how to enable PowerShell remoting on a computer, find the configured endpoint names, and create a remote session to one of the endpoints.</span></span>

<span data-ttu-id="5a670-164">O primeiro comando habilita a comunicação remota do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="5a670-164">The first command enables PowerShell remoting on the computer.</span></span>

<span data-ttu-id="5a670-165">O segundo comando lista as configurações do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5a670-165">The second command lists the endpoint configurations.</span></span>

<span data-ttu-id="5a670-166">O terceiro comando cria uma sessão remota do PowerShell para o mesmo computador, especificando o ponto de extremidade do **PowerShell. 6** por nome.</span><span class="sxs-lookup"><span data-stu-id="5a670-166">The third command creates a remote PowerShell session to the same machine, specifying the **PowerShell.6** endpoint by name.</span></span> <span data-ttu-id="5a670-167">A sessão remota será hospedada com a versão mais recente do PowerShell 6 (6.2.2).</span><span class="sxs-lookup"><span data-stu-id="5a670-167">The remote session will be hosted with the latest PowerShell 6 version (6.2.2).</span></span>

<span data-ttu-id="5a670-168">O último comando acessa a `$PSVersionTable` variável na sessão remota para exibir a versão do PowerShell que está hospedando a sessão.</span><span class="sxs-lookup"><span data-stu-id="5a670-168">The last command accesses the `$PSVersionTable` variable in the remote session to display the PowerShell version that is hosting the session.</span></span>

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
> <span data-ttu-id="5a670-169">O nome da regra de firewall pode ser diferente dependendo da versão do Windows.</span><span class="sxs-lookup"><span data-stu-id="5a670-169">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="5a670-170">Use o `Get-NetFirewallRule` cmdlet para listar os nomes das regras em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="5a670-170">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="5a670-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a670-171">PARAMETERS</span></span>

### <span data-ttu-id="5a670-172">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a670-172">-Confirm</span></span>

<span data-ttu-id="5a670-173">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a670-173">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a670-174">-Force</span><span class="sxs-lookup"><span data-stu-id="5a670-174">-Force</span></span>

<span data-ttu-id="5a670-175">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="5a670-175">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5a670-176">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="5a670-176">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="5a670-177">Indica que esse cmdlet habilita a comunicação remota em versões de cliente do sistema operacional Windows quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="5a670-177">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="5a670-178">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="5a670-178">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="5a670-179">Esse parâmetro não afeta as versões de servidor do sistema operacional Windows, que, por padrão, têm uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="5a670-179">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="5a670-180">Se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5a670-180">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="5a670-181">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="5a670-181">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="5a670-182">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5a670-182">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a670-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a670-183">-WhatIf</span></span>

<span data-ttu-id="5a670-184">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5a670-184">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5a670-185">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5a670-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a670-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a670-186">CommonParameters</span></span>

<span data-ttu-id="5a670-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a670-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a670-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a670-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a670-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5a670-189">INPUTS</span></span>

### <span data-ttu-id="5a670-190">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5a670-190">None</span></span>

<span data-ttu-id="5a670-191">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a670-191">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5a670-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5a670-192">OUTPUTS</span></span>

### <span data-ttu-id="5a670-193">System.String</span><span class="sxs-lookup"><span data-stu-id="5a670-193">System.String</span></span>

<span data-ttu-id="5a670-194">Esse cmdlet retorna cadeias de caracteres que descrevem seus resultados.</span><span class="sxs-lookup"><span data-stu-id="5a670-194">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="5a670-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5a670-195">NOTES</span></span>

<span data-ttu-id="5a670-196">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="5a670-196">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="5a670-197">Em versões de servidor do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto e cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="5a670-197">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="5a670-198">Nas versões cliente do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto irrestrito.</span><span class="sxs-lookup"><span data-stu-id="5a670-198">On client versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="5a670-199">Para criar uma regra de firewall para redes públicas que permite acesso remoto por meio da mesma sub-rede local, use o parâmetro **SkipNetworkProfileCheck**.</span><span class="sxs-lookup"><span data-stu-id="5a670-199">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="5a670-200">Em versões de cliente ou servidor do sistema operacional Windows, para criar uma regra de firewall para redes públicas que remove a restrição de sub-rede local e permite o acesso remoto, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity para executar o seguinte comando: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="5a670-200">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="5a670-201">`Enable-PSRemoting` habilita todas as configurações de sessão definindo o valor da propriedade **habilitada** de todas as configurações de sessão como `$True` .</span><span class="sxs-lookup"><span data-stu-id="5a670-201">`Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="5a670-202">`Enable-PSRemoting` Remove as configurações de **Deny_All** e **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="5a670-202">`Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="5a670-203">Isso fornece acesso remoto a configurações de sessão que foram reservadas para uso local.</span><span class="sxs-lookup"><span data-stu-id="5a670-203">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="5a670-204">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5a670-204">RELATED LINKS</span></span>

[<span data-ttu-id="5a670-205">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a670-205">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="5a670-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a670-206">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="5a670-207">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a670-207">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="5a670-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a670-208">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="5a670-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a670-209">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="5a670-210">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="5a670-210">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="5a670-211">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="5a670-211">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="5a670-212">about_Remote</span><span class="sxs-lookup"><span data-stu-id="5a670-212">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="5a670-213">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="5a670-213">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
