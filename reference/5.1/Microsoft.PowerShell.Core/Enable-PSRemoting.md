---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "93194844"
---
# <span data-ttu-id="4fb44-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4fb44-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="4fb44-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4fb44-104">SYNOPSIS</span></span>
<span data-ttu-id="4fb44-105">Configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4fb44-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="4fb44-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4fb44-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4fb44-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4fb44-107">DESCRIPTION</span></span>

<span data-ttu-id="4fb44-108">O `Enable-PSRemoting` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="4fb44-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span>

<span data-ttu-id="4fb44-109">A comunicação remota do PowerShell é habilitada por padrão no Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="4fb44-109">PowerShell remoting is enabled by default on Windows Server 2012.</span></span> <span data-ttu-id="4fb44-110">Você pode usar o `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell em outras versões com suporte do Windows e para reabilitar a comunicação remota no Windows Server 2012 se ele se tornar desabilitado.</span><span class="sxs-lookup"><span data-stu-id="4fb44-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting on Windows Server 2012 if it becomes disabled.</span></span>

<span data-ttu-id="4fb44-111">Você precisa executar esse comando apenas uma vez em cada computador que receberá comandos.</span><span class="sxs-lookup"><span data-stu-id="4fb44-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="4fb44-112">Você não precisa executá-lo em computadores que só enviam comandos.</span><span class="sxs-lookup"><span data-stu-id="4fb44-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="4fb44-113">Como a configuração inicia os ouvintes, é prudente executá-lo somente onde for necessário.</span><span class="sxs-lookup"><span data-stu-id="4fb44-113">Because the configuration starts listeners, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="4fb44-114">A partir do PowerShell 3,0, o `Enable-PSRemoting` cmdlet pode habilitar a comunicação remota do PowerShell em versões cliente do Windows quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="4fb44-114">Beginning in PowerShell 3.0, the `Enable-PSRemoting` cmdlet can enable PowerShell remoting on client versions of Windows when the computer is on a public network.</span></span> <span data-ttu-id="4fb44-115">Para obter mais informações, consulte a descrição do parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="4fb44-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="4fb44-116">O `Enable-PSRemoting` cmdlet executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="4fb44-116">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="4fb44-117">Executa o cmdlet [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , que executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4fb44-117">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="4fb44-118">Inicia o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="4fb44-118">Starts the WinRM service.</span></span>
  - <span data-ttu-id="4fb44-119">Define o tipo de inicialização no serviço WinRM como automático.</span><span class="sxs-lookup"><span data-stu-id="4fb44-119">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="4fb44-120">Cria um ouvinte para aceitar solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="4fb44-120">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="4fb44-121">Habilita uma exceção de firewall para WS-Management comunicações.</span><span class="sxs-lookup"><span data-stu-id="4fb44-121">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="4fb44-122">Registra as configurações de sessão **Microsoft. PowerShell** e **Microsoft. PowerShell. Workflow** , se elas ainda não estiverem registradas.</span><span class="sxs-lookup"><span data-stu-id="4fb44-122">Registers the **Microsoft.PowerShell** and **Microsoft.PowerShell.Workflow** session configurations, if it they are not already registered.</span></span>
  - <span data-ttu-id="4fb44-123">Registra a configuração de sessão **Microsoft. powershell32** em computadores de 64 bits, se ainda não estiver registrado.</span><span class="sxs-lookup"><span data-stu-id="4fb44-123">Registers the **Microsoft.PowerShell32** session configuration on 64-bit computers, if it is not already registered.</span></span>
  - <span data-ttu-id="4fb44-124">Habilita todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="4fb44-124">Enables all session configurations.</span></span>
  - <span data-ttu-id="4fb44-125">Altera o descritor de segurança de todas as configurações de sessão para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="4fb44-125">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="4fb44-126">Reinicia o serviço WinRM para tornar as alterações anteriores efetivas.</span><span class="sxs-lookup"><span data-stu-id="4fb44-126">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="4fb44-127">Para executar esse cmdlet na plataforma Windows, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="4fb44-127">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="4fb44-128">Isso não se aplica às versões Linux ou MacOS do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fb44-128">This does not apply to Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="4fb44-129">Em sistemas que têm o PowerShell 3,0 e o PowerShell 2,0, não use o PowerShell 2,0 para executar `Enable-PSRemoting` os `Disable-PSRemoting` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="4fb44-129">On systems that have both PowerShell 3.0 and PowerShell 2.0, do not use PowerShell 2.0 to run the `Enable-PSRemoting` and `Disable-PSRemoting` cmdlets.</span></span> <span data-ttu-id="4fb44-130">Os comandos podem parecer bem-sucedidos, mas a comunicação remota não está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="4fb44-130">The commands might appear to succeed, but the remoting is not configured correctly.</span></span> <span data-ttu-id="4fb44-131">Os comandos remotos e tentativas posteriores de habilitar e desabilitar a comunicação remota, provavelmente falharão.</span><span class="sxs-lookup"><span data-stu-id="4fb44-131">Remote commands and later attempts to enable and disable remoting, are likely to fail.</span></span>

## <span data-ttu-id="4fb44-132">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4fb44-132">EXAMPLES</span></span>

### <span data-ttu-id="4fb44-133">Exemplo 1: configurar um computador para receber comandos remotos</span><span class="sxs-lookup"><span data-stu-id="4fb44-133">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="4fb44-134">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4fb44-134">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

### <span data-ttu-id="4fb44-135">Exemplo 2: configurar um computador para receber comandos remotos sem um prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="4fb44-135">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="4fb44-136">Este comando configura o computador para receber comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4fb44-136">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="4fb44-137">O parâmetro **Force** suprime os prompts do usuário.</span><span class="sxs-lookup"><span data-stu-id="4fb44-137">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

### <span data-ttu-id="4fb44-138">Exemplo 3: permitir acesso remoto em clientes</span><span class="sxs-lookup"><span data-stu-id="4fb44-138">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="4fb44-139">Este exemplo mostra como permitir o acesso remoto de redes públicas em versões de cliente do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="4fb44-139">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="4fb44-140">O nome da regra de firewall pode ser diferente para diferentes versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="4fb44-140">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="4fb44-141">Use `Get-NetFirewallRule` para ver uma lista de regras.</span><span class="sxs-lookup"><span data-stu-id="4fb44-141">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="4fb44-142">Antes de habilitar a regra de firewall, exiba as configurações de segurança na regra para verificar se a configuração é apropriada para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fb44-142">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

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

<span data-ttu-id="4fb44-143">Por padrão, o `Enable-PSRemoting` cria regras de rede que permitem o acesso remoto de redes privadas e de domínio.</span><span class="sxs-lookup"><span data-stu-id="4fb44-143">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="4fb44-144">O comando usa o parâmetro **SkipNetworkProfileCheck** para permitir acesso remoto por meio de redes públicas contidas na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4fb44-144">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="4fb44-145">O comando especifica o parâmetro **Force** para suprimir as mensagens de confirmação.</span><span class="sxs-lookup"><span data-stu-id="4fb44-145">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="4fb44-146">O parâmetro **SkipNetworkProfileCheck** não afeta as versões de servidor do sistema operacional Windows, que permitem o acesso remoto de redes públicas na mesma sub-rede local por padrão.</span><span class="sxs-lookup"><span data-stu-id="4fb44-146">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="4fb44-147">O `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** adiciona uma regra de firewall que permite o acesso remoto de redes públicas de qualquer local remoto.</span><span class="sxs-lookup"><span data-stu-id="4fb44-147">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="4fb44-148">Isso inclui locais em sub-redes diferentes.</span><span class="sxs-lookup"><span data-stu-id="4fb44-148">This includes locations in different subnets.</span></span>

> [!NOTE]
> <span data-ttu-id="4fb44-149">O nome da regra de firewall pode ser diferente dependendo da versão do Windows.</span><span class="sxs-lookup"><span data-stu-id="4fb44-149">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="4fb44-150">Use o `Get-NetFirewallRule` cmdlet para listar os nomes das regras em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="4fb44-150">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="4fb44-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4fb44-151">PARAMETERS</span></span>

### <span data-ttu-id="4fb44-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4fb44-152">-Confirm</span></span>

<span data-ttu-id="4fb44-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fb44-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4fb44-154">-Force</span><span class="sxs-lookup"><span data-stu-id="4fb44-154">-Force</span></span>

<span data-ttu-id="4fb44-155">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="4fb44-155">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4fb44-156">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="4fb44-156">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="4fb44-157">Indica que esse cmdlet habilita a comunicação remota em versões de cliente do sistema operacional Windows quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="4fb44-157">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="4fb44-158">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4fb44-158">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="4fb44-159">Esse parâmetro não afeta as versões de servidor do sistema operacional Windows, que, por padrão, têm uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="4fb44-159">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="4fb44-160">Se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fb44-160">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="4fb44-161">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="4fb44-161">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="4fb44-162">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4fb44-162">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4fb44-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4fb44-163">-WhatIf</span></span>

<span data-ttu-id="4fb44-164">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="4fb44-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4fb44-165">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="4fb44-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4fb44-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4fb44-166">CommonParameters</span></span>

<span data-ttu-id="4fb44-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4fb44-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4fb44-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4fb44-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4fb44-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4fb44-169">INPUTS</span></span>

### <span data-ttu-id="4fb44-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4fb44-170">None</span></span>

<span data-ttu-id="4fb44-171">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fb44-171">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4fb44-172">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4fb44-172">OUTPUTS</span></span>

### <span data-ttu-id="4fb44-173">System.String</span><span class="sxs-lookup"><span data-stu-id="4fb44-173">System.String</span></span>

<span data-ttu-id="4fb44-174">Esse cmdlet retorna cadeias de caracteres que descrevem seus resultados.</span><span class="sxs-lookup"><span data-stu-id="4fb44-174">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="4fb44-175">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4fb44-175">NOTES</span></span>

<span data-ttu-id="4fb44-176">No PowerShell 3,0, `Enable-PSRemoting` o cria as seguintes exceções de firewall para WS-Management comunicações.</span><span class="sxs-lookup"><span data-stu-id="4fb44-176">In PowerShell 3.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="4fb44-177">Em versões de servidor do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto e cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="4fb44-177">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="4fb44-178">Em versões de cliente do sistema operacional Windows, `Enable-PSRemoting` no PowerShell 3,0 cria regras de firewall para redes privadas e de domínio que permitem acesso remoto irrestrito.</span><span class="sxs-lookup"><span data-stu-id="4fb44-178">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 3.0 creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="4fb44-179">Para criar uma regra de firewall para redes públicas que permite acesso remoto por meio da mesma sub-rede local, use o parâmetro **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="4fb44-179">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="4fb44-180">Em versões de cliente ou servidor do sistema operacional Windows, para criar uma regra de firewall para redes públicas que remove a restrição de sub-rede local e permite o acesso remoto, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity para executar o seguinte comando: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="4fb44-180">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="4fb44-181">No PowerShell 2,0, `Enable-PSRemoting` o cria as seguintes exceções de firewall para WS-Management comunicações.</span><span class="sxs-lookup"><span data-stu-id="4fb44-181">In PowerShell 2.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="4fb44-182">Em versões de servidor do sistema operacional Windows, ele cria regras de firewall para todas as redes que permitem acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="4fb44-182">On server versions of the Windows operating system, it creates firewall rules for all networks that allow remote access.</span></span>

<span data-ttu-id="4fb44-183">Nas versões cliente do sistema operacional Windows, `Enable-PSRemoting` no PowerShell 2,0 cria uma exceção de firewall somente para locais de rede privada e de domínio.</span><span class="sxs-lookup"><span data-stu-id="4fb44-183">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 2.0 creates a firewall exception only for domain and private network locations.</span></span> <span data-ttu-id="4fb44-184">Para minimizar os riscos de segurança, `Enable-PSRemoting` o não cria uma regra de firewall para redes públicas em versões de cliente do Windows.</span><span class="sxs-lookup"><span data-stu-id="4fb44-184">To minimize security risks, `Enable-PSRemoting` does not create a firewall rule for public networks on client versions of Windows.</span></span> <span data-ttu-id="4fb44-185">Quando o local de rede atual é público, `Enable-PSRemoting` retorna a seguinte mensagem: não é possível verificar o status do firewall.</span><span class="sxs-lookup"><span data-stu-id="4fb44-185">When the current network location is public, `Enable-PSRemoting` returns the following message: Unable to check the status of the firewall.</span></span>

<span data-ttu-id="4fb44-186">A partir do PowerShell 3,0, `Enable-PSRemoting` o habilita todas as configurações de sessão definindo o valor da propriedade **Enabled** de todas as configurações de sessão como `$True` .</span><span class="sxs-lookup"><span data-stu-id="4fb44-186">Starting in PowerShell 3.0, `Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="4fb44-187">No PowerShell 2,0, `Enable-PSRemoting` Remove a configuração **Deny_All** do descritor de segurança de configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="4fb44-187">In PowerShell 2.0, `Enable-PSRemoting` removes the **Deny_All** setting from the security descriptor of session configurations.</span></span> <span data-ttu-id="4fb44-188">No PowerShell 3,0, `Enable-PSRemoting` Remove as configurações de **Deny_All** e **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="4fb44-188">In PowerShell 3.0, `Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="4fb44-189">Isso fornece acesso remoto a configurações de sessão que foram reservadas para uso local.</span><span class="sxs-lookup"><span data-stu-id="4fb44-189">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="4fb44-190">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4fb44-190">RELATED LINKS</span></span>

[<span data-ttu-id="4fb44-191">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fb44-191">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4fb44-192">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fb44-192">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="4fb44-193">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fb44-193">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4fb44-194">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fb44-194">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="4fb44-195">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fb44-195">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4fb44-196">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4fb44-196">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="4fb44-197">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="4fb44-197">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="4fb44-198">about_Remote</span><span class="sxs-lookup"><span data-stu-id="4fb44-198">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="4fb44-199">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="4fb44-199">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
