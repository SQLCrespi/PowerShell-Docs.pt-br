---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: 4ac7605ada0fdb682e9df31c2422d368d6e64f57
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598819"
---
# <span data-ttu-id="ec4c0-102">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-102">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="ec4c0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ec4c0-103">SYNOPSIS</span></span>
<span data-ttu-id="ec4c0-104">Exclui configurações de sessão registradas do computador.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-104">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="ec4c0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec4c0-105">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="ec4c0-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec4c0-106">DESCRIPTION</span></span>

<span data-ttu-id="ec4c0-107">O `Unregister-PSSessionConfiguration` cmdlet exclui as configurações de sessão registradas do computador.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-107">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="ec4c0-108">Esse cmdlet foi projetado para administradores de sistema gerenciar configurações de sessão personalizadas para usuários.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-108">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="ec4c0-109">Para que a alteração entre em vigor, `Unregister-PSSessionConfiguration` o reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-109">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="ec4c0-110">Para evitar a reinicialização, especifique o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-110">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="ec4c0-111">Se você excluir acidentalmente as configurações de sessão padrão **Microsoft. PowerShell** ou **Microsoft. powershell32** , use o `Enable-PSRemoting` cmdlet para restaurá-las.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-111">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="ec4c0-112">Para obter mais informações, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ec4c0-112">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="ec4c0-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ec4c0-113">EXAMPLES</span></span>

### <span data-ttu-id="ec4c0-114">Exemplo 1: excluir uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="ec4c0-114">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="ec4c0-115">Este exemplo exclui a configuração de sessão **MaintenanceShell** do computador.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-115">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="ec4c0-116">Exemplo 2: excluir uma configuração de sessão e reiniciar o serviço WinRM</span><span class="sxs-lookup"><span data-stu-id="ec4c0-116">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="ec4c0-117">Neste exemplo, excluímos a configuração **MaintenanceShell** e reiniciamos o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-117">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="ec4c0-118">O parâmetro **Force** suprime todas as mensagens de usuário para reiniciar o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-118">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="ec4c0-119">Exemplo 3: excluir todas as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="ec4c0-119">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="ec4c0-120">Este exemplo mostra duas maneiras de excluir todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-120">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="ec4c0-121">Ambos os comandos têm o mesmo efeito e podem ser usados de forma intercambiável.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-121">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="ec4c0-122">Exemplo 4: cancelar o registro sem uma reinicialização</span><span class="sxs-lookup"><span data-stu-id="ec4c0-122">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="ec4c0-123">Este exemplo mostra o efeito de usar o parâmetro **NoServiceRestart** para impedir que uma reinicialização de serviço interrompa as sessões no computador.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-123">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="ec4c0-124">O `Unregister-PSSessionConfiguration` exclui a configuração de sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-124">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="ec4c0-125">No entanto, como o comando usa o parâmetro **NoServiceRestart** , o serviço **WinRM** não é reiniciado e a alteração ainda não está completamente efetiva.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-125">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="ec4c0-126">Em seguida, o `Get-PSSessionConfiguration` tenta obter a sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-126">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="ec4c0-127">Como a sessão foi removida da tabela de recursos WS-Management, `Get-PSSessionConfiguration` não é possível retorná-la.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-127">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="ec4c0-128">O `New-PSSession` cmdlet cria uma sessão usando a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-128">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="ec4c0-129">O comando é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-129">The command succeeds.</span></span> <span data-ttu-id="ec4c0-130">Em seguida, reiniciamos o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-130">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="ec4c0-131">Por fim, o `New-PSSession` cmdlet tenta criar uma sessão que usa a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-131">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="ec4c0-132">Desta vez, a sessão falhará porque a configuração **MaintenanceShell** foi excluída quando o serviço WinRM for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-132">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="ec4c0-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec4c0-133">PARAMETERS</span></span>

### <span data-ttu-id="ec4c0-134">-Force</span><span class="sxs-lookup"><span data-stu-id="ec4c0-134">-Force</span></span>

<span data-ttu-id="ec4c0-135">Indica que o cmdlet não solicita confirmação e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-135">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="ec4c0-136">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-136">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="ec4c0-137">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-137">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="ec4c0-138">-Name</span><span class="sxs-lookup"><span data-stu-id="ec4c0-138">-Name</span></span>

<span data-ttu-id="ec4c0-139">Especifica os nomes das configurações de sessão a excluir.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-139">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="ec4c0-140">Insira um nome de configuração de sessão ou um padrão de nome de configuração.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-140">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="ec4c0-141">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="ec4c0-142">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-142">This parameter is required.</span></span>

<span data-ttu-id="ec4c0-143">Você também pode canalizar as configurações de sessão para o `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-143">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ec4c0-144">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="ec4c0-144">-NoServiceRestart</span></span>

<span data-ttu-id="ec4c0-145">Indica que esse cmdlet não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-145">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="ec4c0-146">Por padrão, quando você executa um `Unregister-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para que a alteração seja efetiva.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-146">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="ec4c0-147">Até que o serviço **WinRM** seja reiniciado, os usuários ainda poderão usar a configuração de sessão não registrada, embora `Get-PSSessionConfiguration` não o encontre.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-147">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="ec4c0-148">Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-148">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="ec4c0-149">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-149">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="ec4c0-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ec4c0-150">-Confirm</span></span>

<span data-ttu-id="ec4c0-151">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ec4c0-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ec4c0-152">-WhatIf</span></span>

<span data-ttu-id="ec4c0-153">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ec4c0-154">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ec4c0-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec4c0-155">CommonParameters</span></span>

<span data-ttu-id="ec4c0-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec4c0-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec4c0-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec4c0-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ec4c0-158">INPUTS</span></span>

### <span data-ttu-id="ec4c0-159">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-159">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="ec4c0-160">É possível canalizar um objeto de configuração de sessão `Get-PSSessionConfiguration` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-160">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="ec4c0-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ec4c0-161">OUTPUTS</span></span>

### <span data-ttu-id="ec4c0-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ec4c0-162">None</span></span>

<span data-ttu-id="ec4c0-163">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-163">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="ec4c0-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ec4c0-164">NOTES</span></span>

<span data-ttu-id="ec4c0-165">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="ec4c0-165">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="ec4c0-166">Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="ec4c0-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="ec4c0-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ec4c0-167">RELATED LINKS</span></span>

[<span data-ttu-id="ec4c0-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ec4c0-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="ec4c0-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="ec4c0-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="ec4c0-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ec4c0-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="ec4c0-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec4c0-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="ec4c0-177">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="ec4c0-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="ec4c0-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="ec4c0-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="ec4c0-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="ec4c0-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
