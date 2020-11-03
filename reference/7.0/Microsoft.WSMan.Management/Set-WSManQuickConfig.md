---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: 570355eb1f793cbdd7a8a87fdcba312cce0113ca
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "93195291"
---
# <span data-ttu-id="0e018-103">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="0e018-103">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="0e018-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0e018-104">SYNOPSIS</span></span>
<span data-ttu-id="0e018-105">Configura o computador local para gerenciamento remoto.</span><span class="sxs-lookup"><span data-stu-id="0e018-105">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="0e018-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e018-106">SYNTAX</span></span>

### <span data-ttu-id="0e018-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="0e018-107">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="0e018-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e018-108">DESCRIPTION</span></span>

<span data-ttu-id="0e018-109">O `Set-WSManQuickConfig` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia Web Services for Management (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="0e018-109">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="0e018-110">`Set-WSManQuickConfig` executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="0e018-110">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="0e018-111">Verifica se o serviço WinRM está em execução.</span><span class="sxs-lookup"><span data-stu-id="0e018-111">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="0e018-112">Se o serviço WinRM não estiver em execução, o serviço será iniciado.</span><span class="sxs-lookup"><span data-stu-id="0e018-112">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="0e018-113">Define o tipo de inicialização do serviço WinRM como automático.</span><span class="sxs-lookup"><span data-stu-id="0e018-113">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="0e018-114">Cria um ouvinte para aceitar solicitações em qualquer endereço IP.</span><span class="sxs-lookup"><span data-stu-id="0e018-114">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="0e018-115">O transporte padrão é **http** .</span><span class="sxs-lookup"><span data-stu-id="0e018-115">The default transport is **HTTP** .</span></span>
- <span data-ttu-id="0e018-116">Habilita uma exceção de firewall para o tráfego do WinRM.</span><span class="sxs-lookup"><span data-stu-id="0e018-116">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="0e018-117">Para executar `Set-WSManQuickConfig` , inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="0e018-117">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="0e018-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0e018-118">EXAMPLES</span></span>

### <span data-ttu-id="0e018-119">Exemplo 1: habilitar o gerenciamento remoto do computador local por HTTP</span><span class="sxs-lookup"><span data-stu-id="0e018-119">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="0e018-120">Este exemplo define a configuração necessária para habilitar o gerenciamento remoto do computador local.</span><span class="sxs-lookup"><span data-stu-id="0e018-120">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="0e018-121">Por padrão, esse comando cria um ouvinte de WS-Management em **http** .</span><span class="sxs-lookup"><span data-stu-id="0e018-121">By default, this command creates a WS-Management listener on **HTTP** .</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="0e018-122">Exemplo 2: habilitar o gerenciamento remoto do computador local por HTTPS</span><span class="sxs-lookup"><span data-stu-id="0e018-122">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="0e018-123">Este exemplo define a configuração necessária para habilitar o gerenciamento remoto do computador local.</span><span class="sxs-lookup"><span data-stu-id="0e018-123">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="0e018-124">O parâmetro **UseSSL** especifica que o **https** é usado para se comunicar com o computador.</span><span class="sxs-lookup"><span data-stu-id="0e018-124">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="0e018-125">O **https** requer configuração manual.</span><span class="sxs-lookup"><span data-stu-id="0e018-125">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="0e018-126">Para obter mais informações, consulte a descrição do parâmetro **UseSSL** .</span><span class="sxs-lookup"><span data-stu-id="0e018-126">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="0e018-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e018-127">PARAMETERS</span></span>

### <span data-ttu-id="0e018-128">-Force</span><span class="sxs-lookup"><span data-stu-id="0e018-128">-Force</span></span>

<span data-ttu-id="0e018-129">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="0e018-129">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e018-130">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="0e018-130">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="0e018-131">Configura as versões do cliente do Windows para comunicação remota quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="0e018-131">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="0e018-132">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="0e018-132">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="0e018-133">Esse parâmetro não tem nenhum efeito nas versões de servidor do Windows, por padrão, ter uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="0e018-133">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="0e018-134">Se a regra de firewall de sub-rede local estiver desabilitada na versão de servidor do Windows, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0e018-134">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="0e018-135">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="0e018-135">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="0e018-136">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0e018-136">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e018-137">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="0e018-137">-UseSSL</span></span>

<span data-ttu-id="0e018-138">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0e018-138">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="0e018-139">Por padrão, o SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="0e018-139">By default, SSL isn't used.</span></span>

<span data-ttu-id="0e018-140">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="0e018-140">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="0e018-141">O parâmetro **UseSSL** permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="0e018-141">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="0e018-142">Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para a conexão, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0e018-142">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="0e018-143">O **https** requer configuração manual de regras de firewall e WinRM.</span><span class="sxs-lookup"><span data-stu-id="0e018-143">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="0e018-144">Para obter mais informações, consulte [como: configurar o WinRM para https](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span><span class="sxs-lookup"><span data-stu-id="0e018-144">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e018-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e018-145">CommonParameters</span></span>

<span data-ttu-id="0e018-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e018-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e018-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e018-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e018-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0e018-148">INPUTS</span></span>

### <span data-ttu-id="0e018-149">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0e018-149">None</span></span>

<span data-ttu-id="0e018-150">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="0e018-150">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="0e018-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0e018-151">OUTPUTS</span></span>

### <span data-ttu-id="0e018-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0e018-152">None</span></span>

<span data-ttu-id="0e018-153">Esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0e018-153">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="0e018-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0e018-154">NOTES</span></span>

## <span data-ttu-id="0e018-155">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0e018-155">RELATED LINKS</span></span>

[<span data-ttu-id="0e018-156">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0e018-156">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="0e018-157">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0e018-157">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="0e018-158">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0e018-158">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="0e018-159">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="0e018-159">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="0e018-160">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0e018-160">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="0e018-161">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0e018-161">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="0e018-162">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0e018-162">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="0e018-163">Como configurar o WINRM para HTTPS</span><span class="sxs-lookup"><span data-stu-id="0e018-163">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="0e018-164">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0e018-164">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="0e018-165">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0e018-165">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="0e018-166">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0e018-166">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="0e018-167">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="0e018-167">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="0e018-168">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="0e018-168">Test-WSMan</span></span>](Test-WSMan.md)
