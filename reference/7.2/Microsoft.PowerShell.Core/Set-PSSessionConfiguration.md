---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: c3c3c0bbb0436ef2e6857adc35f83e627d03f4b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598413"
---
# <span data-ttu-id="2f262-102">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-102">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="2f262-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2f262-103">SYNOPSIS</span></span>
<span data-ttu-id="2f262-104">Altera as propriedades de uma configuração de sessão registrada.</span><span class="sxs-lookup"><span data-stu-id="2f262-104">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="2f262-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f262-105">SYNTAX</span></span>

### <span data-ttu-id="2f262-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="2f262-106">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2f262-107">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="2f262-107">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2f262-108">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2f262-108">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2f262-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f262-109">DESCRIPTION</span></span>

<span data-ttu-id="2f262-110">O `Set-PSSessionConfiguration` cmdlet altera as propriedades das configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="2f262-110">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="2f262-111">Use o parâmetro **Name** para identificar a configuração da sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="2f262-111">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="2f262-112">Use os outros parâmetros para especificar novos valores para as propriedades da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-112">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="2f262-113">Para excluir um valor de propriedade da configuração e usar o valor padrão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` para o parâmetro correspondente.</span><span class="sxs-lookup"><span data-stu-id="2f262-113">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="2f262-114">A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-114">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="2f262-115">Esse recurso fornece um método simples e detectável para definir ou alterar as propriedades de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-115">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="2f262-116">Para especificar um arquivo de configuração de sessão, use o parâmetro **path** de `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="2f262-116">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="2f262-117">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="2f262-117">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="2f262-118">Para obter informações sobre como criar e modificar um arquivo de configuração de sessão, consulte o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-118">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="2f262-119">As configurações de sessão definem o ambiente de sessões remotas (**PSSessions**) que se conectam ao computador local.</span><span class="sxs-lookup"><span data-stu-id="2f262-119">Session configurations define the environment of remote sessions (**PSSessions**) that connect to the local computer.</span></span> <span data-ttu-id="2f262-120">Cada **PSSession** usa uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-120">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="2f262-121">A configuração de sessão determina os recursos da **PSSession**, como os módulos disponíveis na sessão, os cmdlets que têm permissão para serem executados, o modo de linguagem, as cotas e os tempos limite.</span><span class="sxs-lookup"><span data-stu-id="2f262-121">The session configuration determines the features of the **PSSession**, such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="2f262-122">O descritor de segurança da configuração de sessão determina quem pode usar a configuração de sessão para se conectar ao computador local.</span><span class="sxs-lookup"><span data-stu-id="2f262-122">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="2f262-123">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2f262-123">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="2f262-124">Para ver as propriedades de uma configuração de sessão, use o `Get-PSSessionConfiguration` cmdlet ou o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="2f262-124">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="2f262-125">Para obter mais informações sobre o provedor WSMan, digite `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="2f262-125">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="2f262-126">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2f262-126">EXAMPLES</span></span>

### <span data-ttu-id="2f262-127">Exemplo 1: criar e alterar uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="2f262-127">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="2f262-128">Este exemplo mostra como adicionar e remover um script de inicialização de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-128">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="2f262-129">O primeiro comando cria a configuração **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="2f262-129">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="2f262-130">O segundo comando adiciona o `AdminConfig.ps1` script à configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-130">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="2f262-131">A alteração é eficaz quando você reinicia o **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="2f262-131">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="2f262-132">O terceiro comando Remove o `AdminConfig.ps1` script da configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-132">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="2f262-133">Exemplo 2: exibir resultados</span><span class="sxs-lookup"><span data-stu-id="2f262-133">Example 2: Display results</span></span>

<span data-ttu-id="2f262-134">Este exemplo aumenta o valor da propriedade **MaximumReceivedObjectSizeMB** para 20.</span><span class="sxs-lookup"><span data-stu-id="2f262-134">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="2f262-135">Esse comando também solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2f262-135">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="2f262-136">A alteração não será eficaz até que o serviço **WinRM** seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="2f262-136">The change is not effective until the **WinRM** service is restarted.</span></span>

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### <span data-ttu-id="2f262-137">Exemplo 3: exibir resultados de diferentes maneiras</span><span class="sxs-lookup"><span data-stu-id="2f262-137">Example 3: Display results in different ways</span></span>

<span data-ttu-id="2f262-138">Neste exemplo, `Set-PSSessionConfiguration` altera o script de inicialização na configuração de sessão **MaintenanceShell** para `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2f262-138">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="2f262-139">A saída mostra a alteração e solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2f262-139">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="2f262-140">A resposta é "y" (sim).</span><span class="sxs-lookup"><span data-stu-id="2f262-140">The response is "y" (yes).</span></span>

<span data-ttu-id="2f262-141">`Get-PSSessionConfiguration` Obtém a configuração da sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2f262-141">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="2f262-142">O operador de pipeline (|) envia os resultados do comando para `Format-List` , que exibe todas as propriedades do objeto de configuração em uma lista.</span><span class="sxs-lookup"><span data-stu-id="2f262-142">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="2f262-143">Em seguida, usando o provedor WSMan, exibimos os parâmetros de inicialização para a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2f262-143">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="2f262-144">`Get-ChildItem` (alias `dir` ) Obtém os itens filho no nó **InitializationParameters** para o plug-in **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="2f262-144">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="2f262-145">Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="2f262-145">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="2f262-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f262-146">PARAMETERS</span></span>

### <span data-ttu-id="2f262-147">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="2f262-147">-AccessMode</span></span>

<span data-ttu-id="2f262-148">Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador.</span><span class="sxs-lookup"><span data-stu-id="2f262-148">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="2f262-149">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="2f262-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2f262-150">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2f262-150">Disabled.</span></span> <span data-ttu-id="2f262-151">Desabilita a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-151">Disables the session configuration.</span></span> <span data-ttu-id="2f262-152">Ele não pode ser usado para acesso remoto ou local no computador.</span><span class="sxs-lookup"><span data-stu-id="2f262-152">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="2f262-153">Esse valor define a propriedade **Enabled** da configuração de sessão ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) como **false**.</span><span class="sxs-lookup"><span data-stu-id="2f262-153">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="2f262-154">Local.</span><span class="sxs-lookup"><span data-stu-id="2f262-154">Local.</span></span> <span data-ttu-id="2f262-155">Adiciona uma entrada **Network_Deny_All** ao descritor de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-155">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="2f262-156">Os usuários do computador local podem usar a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas os usuários remotos têm o acesso negado.</span><span class="sxs-lookup"><span data-stu-id="2f262-156">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="2f262-157">Controle.</span><span class="sxs-lookup"><span data-stu-id="2f262-157">Remote.</span></span> <span data-ttu-id="2f262-158">Remove as entradas **Deny_All** e **Network_Deny_All** dos descritores de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-158">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="2f262-159">Usuários de computadores locais e remotos podem usar a configuração da sessão para criar sessões e executar comandos nesse computador.</span><span class="sxs-lookup"><span data-stu-id="2f262-159">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="2f262-160">O valor padrão é **remoto**.</span><span class="sxs-lookup"><span data-stu-id="2f262-160">The default value is **Remote**.</span></span>

<span data-ttu-id="2f262-161">Outros cmdlets podem substituir o valor desse parâmetro posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2f262-161">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="2f262-162">Por exemplo, o `Enable-PSRemoting` cmdlet habilita todas as configurações de sessão no computador e permite o acesso remoto a elas, e o `Disable-PSRemoting` cmdlet permite apenas acesso local a todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="2f262-162">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="2f262-163">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-163">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-164">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="2f262-164">-ApplicationBase</span></span>

<span data-ttu-id="2f262-165">Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="2f262-165">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-166">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="2f262-166">-AssemblyName</span></span>

<span data-ttu-id="2f262-167">Especifica o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="2f262-167">Specifies the assembly name.</span></span> <span data-ttu-id="2f262-168">Esse cmdlet cria uma configuração de sessão com base em uma classe que é definida em um assembly.</span><span class="sxs-lookup"><span data-stu-id="2f262-168">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="2f262-169">Insira o nome de arquivo ou caminho completo de um arquivos assembly. dll que define uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-169">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="2f262-170">Se você inserir apenas o nome do arquivo, poderá inserir o caminho no valor do parâmetro **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="2f262-170">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-171">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="2f262-171">-ConfigurationTypeName</span></span>

<span data-ttu-id="2f262-172">Especifica o tipo de configuração de sessão que é definido no assembly no parâmetro **AssemblyName**.</span><span class="sxs-lookup"><span data-stu-id="2f262-172">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="2f262-173">O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="2f262-173">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="2f262-174">Esse parâmetro é necessário quando você especifica um nome de assembly.</span><span class="sxs-lookup"><span data-stu-id="2f262-174">This parameter is required when you specify an assembly name.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-175">-Force</span><span class="sxs-lookup"><span data-stu-id="2f262-175">-Force</span></span>

<span data-ttu-id="2f262-176">Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="2f262-176">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="2f262-177">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="2f262-177">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="2f262-178">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="2f262-178">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="2f262-179">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="2f262-179">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="2f262-180">Especifica o limite da quantidade de dados que podem ser enviados para este computador em qualquer comando remoto único.</span><span class="sxs-lookup"><span data-stu-id="2f262-180">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="2f262-181">Insira o tamanho dos dados em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="2f262-181">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="2f262-182">O valor padrão é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="2f262-182">The default is 50 MB.</span></span>

<span data-ttu-id="2f262-183">Se um limite de tamanho de dados for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="2f262-183">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="2f262-184">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="2f262-184">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-185">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="2f262-185">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="2f262-186">Especifica os limites na quantidade de dados que podem ser enviados para este computador em qualquer objeto único.</span><span class="sxs-lookup"><span data-stu-id="2f262-186">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="2f262-187">Insira o tamanho dos dados em megabytes.</span><span class="sxs-lookup"><span data-stu-id="2f262-187">Enter the data size in megabytes.</span></span> <span data-ttu-id="2f262-188">O padrão é 10 MB.</span><span class="sxs-lookup"><span data-stu-id="2f262-188">The default is 10 MB.</span></span>

<span data-ttu-id="2f262-189">Se um limite de tamanho de objeto for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="2f262-189">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="2f262-190">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="2f262-190">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-191">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="2f262-191">-ModulesToImport</span></span>

<span data-ttu-id="2f262-192">Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-192">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="2f262-193">Digite os nomes de módulo e o snap-in.</span><span class="sxs-lookup"><span data-stu-id="2f262-193">Enter the module and snap-in names.</span></span>

<span data-ttu-id="2f262-194">Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões, mas a menos que os cmdlets sejam excluídos, você pode usar os `Import-Module` cmdlets e Add-PSSnapin para adicionar módulos e snap-ins à sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-194">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="2f262-195">Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos especificados no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="2f262-195">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="2f262-196">No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.</span><span class="sxs-lookup"><span data-stu-id="2f262-196">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="2f262-197">Os módulos especificados nesse valor de parâmetro substituem a lista de módulos especificados usando o parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-197">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="2f262-198">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-198">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-199">-Name</span><span class="sxs-lookup"><span data-stu-id="2f262-199">-Name</span></span>

<span data-ttu-id="2f262-200">Especifica o nome da configuração de sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="2f262-200">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="2f262-201">Você não pode usar esse parâmetro para alterar o nome da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-201">You cannot use this parameter to change the name of the session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-202">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="2f262-202">-NoServiceRestart</span></span>

<span data-ttu-id="2f262-203">Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2f262-203">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="2f262-204">Por padrão, quando você executa `Set-PSSessionConfiguration` o, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz.</span><span class="sxs-lookup"><span data-stu-id="2f262-204">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="2f262-205">Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="2f262-205">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="2f262-206">Para reiniciar o serviço **WinRM** sem avisar, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="2f262-206">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="2f262-207">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-207">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="2f262-208">-Path</span><span class="sxs-lookup"><span data-stu-id="2f262-208">-Path</span></span>

<span data-ttu-id="2f262-209">Especifica o caminho de um arquivo de configuração de sessão (. PSSC), como um criado pelo `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-209">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="2f262-210">Se você omitir o caminho, o padrão será o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2f262-210">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="2f262-211">Para obter informações sobre como modificar um arquivo de configuração de sessão, consulte o tópico da ajuda para o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-211">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="2f262-212">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-212">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-213">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="2f262-213">-PSVersion</span></span>

<span data-ttu-id="2f262-214">Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-214">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="2f262-215">O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-215">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="2f262-216">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-217">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2f262-217">-RunAsCredential</span></span>

<span data-ttu-id="2f262-218">Especifica as credenciais para os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-218">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="2f262-219">Por padrão, os comandos são executados com as permissões do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2f262-219">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="2f262-220">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-220">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-221">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="2f262-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2f262-222">Especifica uma cadeia de caracteres SDDL (Security Descriptor Definition Language) diferentes para a configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-222">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="2f262-223">Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-223">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="2f262-224">Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-224">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="2f262-225">Para usar o descritor de segurança padrão para a configuração, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="2f262-225">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="2f262-226">O padrão é o SDDL raiz na unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="2f262-226">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="2f262-227">Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI dos** em vez deste.</span><span class="sxs-lookup"><span data-stu-id="2f262-227">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="2f262-228">Não é possível usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f262-228">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="2f262-229">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="2f262-229">-SessionTypeOption</span></span>

<span data-ttu-id="2f262-230">Especifica opções específicas de tipo para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-230">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="2f262-231">Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="2f262-231">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="2f262-232">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-232">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="2f262-233">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-233">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="2f262-234">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-234">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="2f262-235">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-235">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-236">-ShowSecurityDescriptorUI dos</span><span class="sxs-lookup"><span data-stu-id="2f262-236">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="2f262-237">Indica que esse cmdlet é uma folha de propriedades que ajuda a criar uma nova SDDL para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-237">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="2f262-238">A folha de propriedades aparece depois que você executa o `Set-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2f262-238">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="2f262-239">Quando você define permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-239">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="2f262-240">Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f262-240">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="2f262-241">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="2f262-241">-StartupScript</span></span>

<span data-ttu-id="2f262-242">Especifica o script de inicialização para a configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-242">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="2f262-243">Insira o caminho totalmente qualificado de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f262-243">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="2f262-244">O script especificado é executado na nova sessão que usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-244">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="2f262-245">Para excluir um script de inicialização de uma configuração de sessão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="2f262-245">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="2f262-246">Você pode usar um script de inicialização para configurar ainda mais a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f262-246">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="2f262-247">Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="2f262-247">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="2f262-248">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="2f262-248">-ThreadOptions</span></span>

<span data-ttu-id="2f262-249">Especifica a configuração de opções de thread na configuração.</span><span class="sxs-lookup"><span data-stu-id="2f262-249">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="2f262-250">Essa configuração define como threads são criados e usados quando um comando é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-250">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="2f262-251">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="2f262-251">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2f262-252">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f262-252">Default</span></span>
- <span data-ttu-id="2f262-253">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="2f262-253">ReuseThread</span></span>
- <span data-ttu-id="2f262-254">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="2f262-254">UseCurrentThread</span></span>
- <span data-ttu-id="2f262-255">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="2f262-255">UseNewThread</span></span>

<span data-ttu-id="2f262-256">O valor padrão é **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="2f262-256">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="2f262-257">Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="2f262-257">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-258">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="2f262-258">-TransportOption</span></span>

<span data-ttu-id="2f262-259">Especifica as opções de transporte para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-259">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="2f262-260">Insira um objeto de opções de transporte, como o objeto **WSManConfigurationOption** que o `New-PSTransportOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="2f262-260">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="2f262-261">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-261">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="2f262-262">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-262">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="2f262-263">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-263">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="2f262-264">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-264">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-265">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="2f262-265">-UseSharedProcess</span></span>

<span data-ttu-id="2f262-266">Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-266">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="2f262-267">Por padrão, cada sessão é hospedada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="2f262-267">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="2f262-268">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-268">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2f262-269">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2f262-269">-Confirm</span></span>

<span data-ttu-id="2f262-270">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-270">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2f262-271">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2f262-271">-WhatIf</span></span>

<span data-ttu-id="2f262-272">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2f262-272">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2f262-273">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2f262-273">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2f262-274">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="2f262-274">-ThreadApartmentState</span></span>

<span data-ttu-id="2f262-275">Especifica o estado de apartment do módulo de Threading a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2f262-275">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="2f262-276">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="2f262-276">Acceptable values are:</span></span>

- <span data-ttu-id="2f262-277">Unknown</span><span class="sxs-lookup"><span data-stu-id="2f262-277">Unknown</span></span>
- <span data-ttu-id="2f262-278">MTA</span><span class="sxs-lookup"><span data-stu-id="2f262-278">MTA</span></span>
- <span data-ttu-id="2f262-279">STA</span><span class="sxs-lookup"><span data-stu-id="2f262-279">STA</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f262-280">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2f262-280">CommonParameters</span></span>

<span data-ttu-id="2f262-281">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2f262-281">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f262-282">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2f262-282">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f262-283">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2f262-283">INPUTS</span></span>

### <span data-ttu-id="2f262-284">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2f262-284">None</span></span>

<span data-ttu-id="2f262-285">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-285">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2f262-286">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2f262-286">OUTPUTS</span></span>

### <span data-ttu-id="2f262-287">Microsoft. WSMan. Management. WSManConfigLeafElement</span><span class="sxs-lookup"><span data-stu-id="2f262-287">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="2f262-288">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2f262-288">NOTES</span></span>

<span data-ttu-id="2f262-289">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="2f262-289">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="2f262-290">Para executar esse cmdlet, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="2f262-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="2f262-291">O `Set-PSSessionConfiguration` cmdlet não altera o nome da configuração e o provedor **WSMan** não oferece suporte ao `Rename-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f262-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="2f262-292">Para alterar o nome de uma configuração de sessão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração e, em seguida, use o `Register-PSSessionConfiguration` cmdlet para criar e registrar uma nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="2f262-293">Você pode usar o `Set-PSSessionConfiguration` cmdlet para alterar as configurações de sessão padrão Microsoft. PowerShell e Microsoft. powershell32.</span><span class="sxs-lookup"><span data-stu-id="2f262-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="2f262-294">Elas não são protegidas.</span><span class="sxs-lookup"><span data-stu-id="2f262-294">They are not protected.</span></span> <span data-ttu-id="2f262-295">Para reverter para a versão original de uma configuração de sessão padrão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração de sessão padrão e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-la.</span><span class="sxs-lookup"><span data-stu-id="2f262-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="2f262-296">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="2f262-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="2f262-297">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="2f262-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="2f262-298">É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f262-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="2f262-299">No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode**.</span><span class="sxs-lookup"><span data-stu-id="2f262-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="2f262-300">Os comandos do Windows PowerShell 2.0 não geram um erro, mas são ineficazes.</span><span class="sxs-lookup"><span data-stu-id="2f262-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="2f262-301">Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f262-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="2f262-302">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2f262-302">RELATED LINKS</span></span>

[<span data-ttu-id="2f262-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="2f262-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="2f262-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2f262-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2f262-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2f262-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2f262-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="2f262-308">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="2f262-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="2f262-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2f262-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2f262-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2f262-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f262-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2f262-312">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="2f262-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2f262-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2f262-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2f262-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2f262-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
