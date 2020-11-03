---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: d56d71dccc54c07154a6f3302634b84779c00129
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195024"
---
# <span data-ttu-id="2ae38-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="2ae38-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2ae38-104">SYNOPSIS</span></span>
<span data-ttu-id="2ae38-105">Exclui configurações de sessão registradas do computador.</span><span class="sxs-lookup"><span data-stu-id="2ae38-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="2ae38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ae38-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2ae38-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ae38-107">DESCRIPTION</span></span>

<span data-ttu-id="2ae38-108">O `Unregister-PSSessionConfiguration` cmdlet exclui as configurações de sessão registradas do computador.</span><span class="sxs-lookup"><span data-stu-id="2ae38-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="2ae38-109">Esse cmdlet foi projetado para administradores de sistema gerenciar configurações de sessão personalizadas para usuários.</span><span class="sxs-lookup"><span data-stu-id="2ae38-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="2ae38-110">Para que a alteração entre em vigor, `Unregister-PSSessionConfiguration` o reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="2ae38-111">Para evitar a reinicialização, especifique o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="2ae38-112">Se você excluir acidentalmente as configurações de sessão padrão **Microsoft. PowerShell** ou **Microsoft. powershell32** , use o `Enable-PSRemoting` cmdlet para restaurá-las.</span><span class="sxs-lookup"><span data-stu-id="2ae38-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="2ae38-113">Para obter mais informações, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2ae38-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="2ae38-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2ae38-114">EXAMPLES</span></span>

### <span data-ttu-id="2ae38-115">Exemplo 1: excluir uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="2ae38-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="2ae38-116">Este exemplo exclui a configuração de sessão **MaintenanceShell** do computador.</span><span class="sxs-lookup"><span data-stu-id="2ae38-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="2ae38-117">Exemplo 2: excluir uma configuração de sessão e reiniciar o serviço WinRM</span><span class="sxs-lookup"><span data-stu-id="2ae38-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="2ae38-118">Neste exemplo, excluímos a configuração **MaintenanceShell** e reiniciamos o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="2ae38-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="2ae38-119">O parâmetro **Force** suprime todas as mensagens de usuário para reiniciar o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="2ae38-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="2ae38-120">Exemplo 3: excluir todas as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="2ae38-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="2ae38-121">Este exemplo mostra duas maneiras de excluir todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="2ae38-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="2ae38-122">Ambos os comandos têm o mesmo efeito e podem ser usados de forma intercambiável.</span><span class="sxs-lookup"><span data-stu-id="2ae38-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="2ae38-123">Exemplo 4: cancelar o registro sem uma reinicialização</span><span class="sxs-lookup"><span data-stu-id="2ae38-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="2ae38-124">Este exemplo mostra o efeito de usar o parâmetro **NoServiceRestart** para impedir que uma reinicialização de serviço interrompa as sessões no computador.</span><span class="sxs-lookup"><span data-stu-id="2ae38-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

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

<span data-ttu-id="2ae38-125">O `Unregister-PSSessionConfiguration` exclui a configuração de sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="2ae38-126">No entanto, como o comando usa o parâmetro **NoServiceRestart** , o serviço **WinRM** não é reiniciado e a alteração ainda não está completamente efetiva.</span><span class="sxs-lookup"><span data-stu-id="2ae38-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="2ae38-127">Em seguida, o `Get-PSSessionConfiguration` tenta obter a sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="2ae38-128">Como a sessão foi removida da tabela de recursos WS-Management, `Get-PSSessionConfiguration` não é possível retorná-la.</span><span class="sxs-lookup"><span data-stu-id="2ae38-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="2ae38-129">O `New-PSSession` cmdlet cria uma sessão usando a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="2ae38-130">O comando é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="2ae38-130">The command succeeds.</span></span> <span data-ttu-id="2ae38-131">Em seguida, reiniciamos o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="2ae38-132">Por fim, o `New-PSSession` cmdlet tenta criar uma sessão que usa a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="2ae38-133">Desta vez, a sessão falhará porque a configuração **MaintenanceShell** foi excluída quando o serviço WinRM for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="2ae38-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="2ae38-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ae38-134">PARAMETERS</span></span>

### <span data-ttu-id="2ae38-135">-Force</span><span class="sxs-lookup"><span data-stu-id="2ae38-135">-Force</span></span>

<span data-ttu-id="2ae38-136">Indica que o cmdlet não solicita confirmação e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="2ae38-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="2ae38-137">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="2ae38-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="2ae38-138">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="2ae38-139">-Name</span><span class="sxs-lookup"><span data-stu-id="2ae38-139">-Name</span></span>

<span data-ttu-id="2ae38-140">Especifica os nomes das configurações de sessão a excluir.</span><span class="sxs-lookup"><span data-stu-id="2ae38-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="2ae38-141">Insira um nome de configuração de sessão ou um padrão de nome de configuração.</span><span class="sxs-lookup"><span data-stu-id="2ae38-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="2ae38-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2ae38-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="2ae38-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2ae38-143">This parameter is required.</span></span>

<span data-ttu-id="2ae38-144">Você também pode canalizar as configurações de sessão para o `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="2ae38-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

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

### <span data-ttu-id="2ae38-145">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="2ae38-145">-NoServiceRestart</span></span>

<span data-ttu-id="2ae38-146">Indica que esse cmdlet não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2ae38-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="2ae38-147">Por padrão, quando você executa um `Unregister-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para que a alteração seja efetiva.</span><span class="sxs-lookup"><span data-stu-id="2ae38-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="2ae38-148">Até que o serviço **WinRM** seja reiniciado, os usuários ainda poderão usar a configuração de sessão não registrada, embora `Get-PSSessionConfiguration` não o encontre.</span><span class="sxs-lookup"><span data-stu-id="2ae38-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="2ae38-149">Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="2ae38-150">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ae38-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="2ae38-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2ae38-151">-Confirm</span></span>

<span data-ttu-id="2ae38-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ae38-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2ae38-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2ae38-153">-WhatIf</span></span>

<span data-ttu-id="2ae38-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2ae38-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2ae38-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2ae38-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2ae38-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ae38-156">CommonParameters</span></span>

<span data-ttu-id="2ae38-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ae38-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ae38-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ae38-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ae38-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2ae38-159">INPUTS</span></span>

### <span data-ttu-id="2ae38-160">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="2ae38-161">É possível canalizar um objeto de configuração de sessão `Get-PSSessionConfiguration` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ae38-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="2ae38-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2ae38-162">OUTPUTS</span></span>

### <span data-ttu-id="2ae38-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2ae38-163">None</span></span>

<span data-ttu-id="2ae38-164">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="2ae38-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="2ae38-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2ae38-165">NOTES</span></span>

<span data-ttu-id="2ae38-166">Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="2ae38-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="2ae38-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2ae38-167">RELATED LINKS</span></span>

[<span data-ttu-id="2ae38-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2ae38-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2ae38-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2ae38-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="2ae38-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2ae38-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2ae38-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae38-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2ae38-177">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="2ae38-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2ae38-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2ae38-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2ae38-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2ae38-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)

