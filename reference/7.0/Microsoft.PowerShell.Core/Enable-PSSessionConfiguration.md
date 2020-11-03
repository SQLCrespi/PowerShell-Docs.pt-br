---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 237fe83af05de7a97113deb95a831d8295c9f4c4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192991"
---
# <span data-ttu-id="39e43-103">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-103">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="39e43-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="39e43-104">SYNOPSIS</span></span>
<span data-ttu-id="39e43-105">Habilita as configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="39e43-105">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="39e43-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39e43-106">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="39e43-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39e43-107">DESCRIPTION</span></span>

<span data-ttu-id="39e43-108">O `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão registradas que foram desabilitadas, como usando `Disable-PSSessionConfiguration` os `Disable-PSRemoting` cmdlets ou ou o parâmetro **AccessMode** de `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="39e43-108">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="39e43-109">Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="39e43-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="39e43-110">Sem parâmetros, `Enable-PSSessionConfiguration` habilita a configuração do **Microsoft. PowerShell** , que é a configuração padrão usada para sessões.</span><span class="sxs-lookup"><span data-stu-id="39e43-110">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="39e43-111">`Enable-PSSessionConfiguration` Remove a configuração de **Deny_All** do descritor de segurança das configurações de sessão afetadas, ativa o ouvinte que aceita solicitações em qualquer endereço IP e reinicia o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="39e43-111">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="39e43-112">A partir do PowerShell 3,0, `Enable-PSSessionConfiguration` também define o valor da propriedade **Enabled** da configuração de sessão ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) como true.</span><span class="sxs-lookup"><span data-stu-id="39e43-112">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="39e43-113">No entanto, `Enable-PSSessionConfiguration` o não remove ou **Network_Deny_All** altera a `AccessMode=Local` configuração do descritor de segurança Network_Deny_All () que permite que somente usuários do computador local usem para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="39e43-113">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="39e43-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="39e43-114">EXAMPLES</span></span>

### <span data-ttu-id="39e43-115">Exemplo 1: reabilitar a sessão padrão</span><span class="sxs-lookup"><span data-stu-id="39e43-115">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="39e43-116">Este exemplo habilita novamente a configuração de sessão padrão do **Microsoft. PowerShell** no computador.</span><span class="sxs-lookup"><span data-stu-id="39e43-116">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="39e43-117">Exemplo 2: reabilitar as sessões especificadas</span><span class="sxs-lookup"><span data-stu-id="39e43-117">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="39e43-118">Este exemplo habilita novamente as configurações de sessão **MaintenanceShell** e **AdminShell** no computador.</span><span class="sxs-lookup"><span data-stu-id="39e43-118">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="39e43-119">Exemplo 3: reabilitar todas as sessões</span><span class="sxs-lookup"><span data-stu-id="39e43-119">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="39e43-120">Este exemplo habilita novamente todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="39e43-120">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="39e43-121">Esses comandos são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="39e43-121">These commands are equivalent.</span></span>
<span data-ttu-id="39e43-122">Portanto, você pode usar qualquer um.</span><span class="sxs-lookup"><span data-stu-id="39e43-122">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="39e43-123">`Enable-PSSessionConfiguration` não gerará um erro se você habilitar uma configuração de sessão que já está habilitada.</span><span class="sxs-lookup"><span data-stu-id="39e43-123">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="39e43-124">Exemplo 4: reabilitar uma sessão e especificar um novo descritor de segurança</span><span class="sxs-lookup"><span data-stu-id="39e43-124">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="39e43-125">Este exemplo habilita novamente a configuração de sessão **MaintenanceShell** e especifica um novo descritor de segurança para a configuração.</span><span class="sxs-lookup"><span data-stu-id="39e43-125">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="39e43-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39e43-126">PARAMETERS</span></span>

### <span data-ttu-id="39e43-127">-Force</span><span class="sxs-lookup"><span data-stu-id="39e43-127">-Force</span></span>

<span data-ttu-id="39e43-128">Indica que o cmdlet não solicita confirmação e reinicia o serviço WinRM sem avisar.</span><span class="sxs-lookup"><span data-stu-id="39e43-128">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="39e43-129">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="39e43-129">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="39e43-130">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="39e43-130">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="39e43-131">-Name</span><span class="sxs-lookup"><span data-stu-id="39e43-131">-Name</span></span>

<span data-ttu-id="39e43-132">Especifica os nomes das configurações de sessão a habilitar.</span><span class="sxs-lookup"><span data-stu-id="39e43-132">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="39e43-133">Insira um ou mais nomes de configuração.</span><span class="sxs-lookup"><span data-stu-id="39e43-133">Enter one or more configuration names.</span></span>
<span data-ttu-id="39e43-134">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="39e43-134">Wildcard characters are permitted.</span></span>

<span data-ttu-id="39e43-135">Você também pode canalizar uma cadeia de caracteres que contém um nome de configuração ou um objeto de configuração de sessão para `Enable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="39e43-135">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="39e43-136">Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o habilitará a configuração de sessão do **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="39e43-136">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="39e43-137">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="39e43-137">-NoServiceRestart</span></span>

<span data-ttu-id="39e43-138">Indica que o cmdlet não reinicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="39e43-138">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="39e43-139">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="39e43-139">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="39e43-140">Especifica um descritor de segurança com o qual esse cmdlet substitui o descritor de segurança na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="39e43-140">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="39e43-141">Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o excluirá apenas o item negar tudo do descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="39e43-141">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39e43-142">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="39e43-142">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="39e43-143">Indica que esse cmdlet habilita a configuração de sessão quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="39e43-143">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="39e43-144">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="39e43-144">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="39e43-145">Por padrão, `Enable-PSSessionConfiguration` o falha em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="39e43-145">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="39e43-146">Esse parâmetro é projetado para versões de cliente do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="39e43-146">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="39e43-147">As versões de servidor do sistema operacional Windows têm uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="39e43-147">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="39e43-148">No entanto, se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor do sistema operacional Windows, esse parâmetro o habilitará novamente.</span><span class="sxs-lookup"><span data-stu-id="39e43-148">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="39e43-149">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="39e43-149">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="39e43-150">Para obter mais informações, consulte `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="39e43-150">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="39e43-151">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="39e43-151">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="39e43-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39e43-152">-Confirm</span></span>

<span data-ttu-id="39e43-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39e43-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39e43-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39e43-154">-WhatIf</span></span>

<span data-ttu-id="39e43-155">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="39e43-155">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="39e43-156">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="39e43-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="39e43-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39e43-157">CommonParameters</span></span>

<span data-ttu-id="39e43-158">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39e43-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39e43-159">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39e43-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39e43-160">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="39e43-160">INPUTS</span></span>

### <span data-ttu-id="39e43-161">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="39e43-161">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="39e43-162">É possível canalizar um objeto de configuração de sessão ou uma cadeia de caracteres que contém o nome de uma configuração de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39e43-162">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="39e43-163">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="39e43-163">OUTPUTS</span></span>

### <span data-ttu-id="39e43-164">Nenhum</span><span class="sxs-lookup"><span data-stu-id="39e43-164">None</span></span>

<span data-ttu-id="39e43-165">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="39e43-165">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="39e43-166">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="39e43-166">NOTES</span></span>

<span data-ttu-id="39e43-167">Para usar esse cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="39e43-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="39e43-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="39e43-168">RELATED LINKS</span></span>

[<span data-ttu-id="39e43-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="39e43-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="39e43-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="39e43-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="39e43-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="39e43-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="39e43-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="39e43-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="39e43-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="39e43-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="39e43-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="39e43-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="39e43-177">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="39e43-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="39e43-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="39e43-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="39e43-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="39e43-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
