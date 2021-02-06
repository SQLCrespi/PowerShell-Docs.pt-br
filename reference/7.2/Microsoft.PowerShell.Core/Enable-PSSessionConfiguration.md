---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 86650f33f376ccb7d1428836c9d0070e749cf0ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596181"
---
# <span data-ttu-id="b340d-102">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-102">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="b340d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b340d-103">SYNOPSIS</span></span>
<span data-ttu-id="b340d-104">Habilita as configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="b340d-104">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="b340d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b340d-105">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b340d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b340d-106">DESCRIPTION</span></span>

<span data-ttu-id="b340d-107">O `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão registradas que foram desabilitadas, como usando `Disable-PSSessionConfiguration` os `Disable-PSRemoting` cmdlets ou ou o parâmetro **AccessMode** de `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="b340d-107">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="b340d-108">Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b340d-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="b340d-109">Sem parâmetros, `Enable-PSSessionConfiguration` habilita a configuração do **Microsoft. PowerShell** , que é a configuração padrão usada para sessões.</span><span class="sxs-lookup"><span data-stu-id="b340d-109">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="b340d-110">`Enable-PSSessionConfiguration` Remove a configuração de **Deny_All** do descritor de segurança das configurações de sessão afetadas, ativa o ouvinte que aceita solicitações em qualquer endereço IP e reinicia o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="b340d-110">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="b340d-111">A partir do PowerShell 3,0, `Enable-PSSessionConfiguration` também define o valor da propriedade **Enabled** da configuração de sessão ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) como true.</span><span class="sxs-lookup"><span data-stu-id="b340d-111">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="b340d-112">No entanto, `Enable-PSSessionConfiguration` o não remove ou  altera a `AccessMode=Local` configuração do descritor de segurança Network_Deny_All () que permite que somente usuários do computador local usem para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b340d-112">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="b340d-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b340d-113">EXAMPLES</span></span>

### <span data-ttu-id="b340d-114">Exemplo 1: reabilitar a sessão padrão</span><span class="sxs-lookup"><span data-stu-id="b340d-114">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="b340d-115">Este exemplo habilita novamente a configuração de sessão padrão do **Microsoft. PowerShell** no computador.</span><span class="sxs-lookup"><span data-stu-id="b340d-115">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="b340d-116">Exemplo 2: reabilitar as sessões especificadas</span><span class="sxs-lookup"><span data-stu-id="b340d-116">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="b340d-117">Este exemplo habilita novamente as configurações de sessão **MaintenanceShell** e **AdminShell** no computador.</span><span class="sxs-lookup"><span data-stu-id="b340d-117">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="b340d-118">Exemplo 3: reabilitar todas as sessões</span><span class="sxs-lookup"><span data-stu-id="b340d-118">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="b340d-119">Este exemplo habilita novamente todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="b340d-119">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="b340d-120">Esses comandos são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="b340d-120">These commands are equivalent.</span></span>
<span data-ttu-id="b340d-121">Portanto, você pode usar qualquer um.</span><span class="sxs-lookup"><span data-stu-id="b340d-121">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="b340d-122">`Enable-PSSessionConfiguration` não gerará um erro se você habilitar uma configuração de sessão que já está habilitada.</span><span class="sxs-lookup"><span data-stu-id="b340d-122">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="b340d-123">Exemplo 4: reabilitar uma sessão e especificar um novo descritor de segurança</span><span class="sxs-lookup"><span data-stu-id="b340d-123">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="b340d-124">Este exemplo habilita novamente a configuração de sessão **MaintenanceShell** e especifica um novo descritor de segurança para a configuração.</span><span class="sxs-lookup"><span data-stu-id="b340d-124">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="b340d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b340d-125">PARAMETERS</span></span>

### <span data-ttu-id="b340d-126">-Force</span><span class="sxs-lookup"><span data-stu-id="b340d-126">-Force</span></span>

<span data-ttu-id="b340d-127">Indica que o cmdlet não solicita confirmação e reinicia o serviço WinRM sem avisar.</span><span class="sxs-lookup"><span data-stu-id="b340d-127">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="b340d-128">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="b340d-128">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="b340d-129">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="b340d-129">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="b340d-130">-Name</span><span class="sxs-lookup"><span data-stu-id="b340d-130">-Name</span></span>

<span data-ttu-id="b340d-131">Especifica os nomes das configurações de sessão a habilitar.</span><span class="sxs-lookup"><span data-stu-id="b340d-131">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="b340d-132">Insira um ou mais nomes de configuração.</span><span class="sxs-lookup"><span data-stu-id="b340d-132">Enter one or more configuration names.</span></span>
<span data-ttu-id="b340d-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b340d-133">Wildcard characters are permitted.</span></span>

<span data-ttu-id="b340d-134">Você também pode canalizar uma cadeia de caracteres que contém um nome de configuração ou um objeto de configuração de sessão para `Enable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="b340d-134">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="b340d-135">Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o habilitará a configuração de sessão do **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="b340d-135">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

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

### <span data-ttu-id="b340d-136">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="b340d-136">-NoServiceRestart</span></span>

<span data-ttu-id="b340d-137">Indica que o cmdlet não reinicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="b340d-137">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="b340d-138">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="b340d-138">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="b340d-139">Especifica um descritor de segurança com o qual esse cmdlet substitui o descritor de segurança na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="b340d-139">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="b340d-140">Se você omitir esse parâmetro, `Enable-PSSessionConfiguration` o excluirá apenas o item negar tudo do descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="b340d-140">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

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

### <span data-ttu-id="b340d-141">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="b340d-141">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="b340d-142">Indica que esse cmdlet habilita a configuração de sessão quando o computador está em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="b340d-142">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="b340d-143">Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.</span><span class="sxs-lookup"><span data-stu-id="b340d-143">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="b340d-144">Por padrão, `Enable-PSSessionConfiguration` o falha em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="b340d-144">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="b340d-145">Esse parâmetro é projetado para versões de cliente do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="b340d-145">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="b340d-146">As versões de servidor do sistema operacional Windows têm uma regra de firewall de sub-rede local para redes públicas.</span><span class="sxs-lookup"><span data-stu-id="b340d-146">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="b340d-147">No entanto, se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor do sistema operacional Windows, esse parâmetro o habilitará novamente.</span><span class="sxs-lookup"><span data-stu-id="b340d-147">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="b340d-148">Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="b340d-148">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="b340d-149">Para obter mais informações, consulte `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="b340d-149">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="b340d-150">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b340d-150">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b340d-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b340d-151">-Confirm</span></span>

<span data-ttu-id="b340d-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b340d-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b340d-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b340d-153">-WhatIf</span></span>

<span data-ttu-id="b340d-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b340d-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b340d-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b340d-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b340d-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b340d-156">CommonParameters</span></span>

<span data-ttu-id="b340d-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b340d-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b340d-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b340d-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b340d-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b340d-159">INPUTS</span></span>

### <span data-ttu-id="b340d-160">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="b340d-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="b340d-161">É possível canalizar um objeto de configuração de sessão ou uma cadeia de caracteres que contém o nome de uma configuração de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b340d-161">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="b340d-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b340d-162">OUTPUTS</span></span>

### <span data-ttu-id="b340d-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b340d-163">None</span></span>

<span data-ttu-id="b340d-164">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="b340d-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="b340d-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b340d-165">NOTES</span></span>

<span data-ttu-id="b340d-166">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="b340d-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="b340d-167">Para usar esse cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="b340d-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="b340d-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b340d-168">RELATED LINKS</span></span>

[<span data-ttu-id="b340d-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="b340d-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="b340d-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="b340d-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="b340d-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="b340d-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="b340d-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="b340d-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="b340d-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="b340d-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="b340d-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b340d-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="b340d-177">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="b340d-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="b340d-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="b340d-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="b340d-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="b340d-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
