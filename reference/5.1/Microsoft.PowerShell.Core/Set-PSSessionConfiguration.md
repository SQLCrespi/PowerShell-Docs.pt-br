---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 33773769cd19373764cf4adbe86bb990589948ff
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194878"
---
# <span data-ttu-id="ed492-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="ed492-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ed492-104">SYNOPSIS</span></span>
<span data-ttu-id="ed492-105">Altera as propriedades de uma configuração de sessão registrada.</span><span class="sxs-lookup"><span data-stu-id="ed492-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="ed492-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed492-106">SYNTAX</span></span>

### <span data-ttu-id="ed492-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="ed492-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed492-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ed492-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed492-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ed492-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed492-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed492-110">DESCRIPTION</span></span>

<span data-ttu-id="ed492-111">O `Set-PSSessionConfiguration` cmdlet altera as propriedades das configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="ed492-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="ed492-112">Use o parâmetro **Name** para identificar a configuração da sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="ed492-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="ed492-113">Use os outros parâmetros para especificar novos valores para as propriedades da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="ed492-114">Para excluir um valor de propriedade da configuração e usar o valor padrão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` para o parâmetro correspondente.</span><span class="sxs-lookup"><span data-stu-id="ed492-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="ed492-115">A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="ed492-116">Esse recurso fornece um método simples e detectável para definir ou alterar as propriedades de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="ed492-117">Para especificar um arquivo de configuração de sessão, use o parâmetro **path** de `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ed492-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="ed492-118">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="ed492-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="ed492-119">Para obter informações sobre como criar e modificar um arquivo de configuração de sessão, consulte o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="ed492-120">As configurações de sessão definem o ambiente de sessões remotas ( **PSSessions** ) que se conectam ao computador local.</span><span class="sxs-lookup"><span data-stu-id="ed492-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="ed492-121">Cada **PSSession** usa uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="ed492-122">A configuração de sessão determina os recursos da **PSSession** , como os módulos disponíveis na sessão, os cmdlets que têm permissão para serem executados, o modo de linguagem, as cotas e os tempos limite.</span><span class="sxs-lookup"><span data-stu-id="ed492-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="ed492-123">O descritor de segurança da configuração de sessão determina quem pode usar a configuração de sessão para se conectar ao computador local.</span><span class="sxs-lookup"><span data-stu-id="ed492-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="ed492-124">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ed492-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="ed492-125">Para ver as propriedades de uma configuração de sessão, use o `Get-PSSessionConfiguration` cmdlet ou o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="ed492-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="ed492-126">Para obter mais informações sobre o provedor WSMan, digite `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="ed492-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="ed492-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ed492-127">EXAMPLES</span></span>

### <span data-ttu-id="ed492-128">Exemplo 1: alterar o estado de apartment do thread</span><span class="sxs-lookup"><span data-stu-id="ed492-128">Example 1: Change the thread apartment state</span></span>

```
PS C:\> Set-PSSessionConfiguration -Name "MaintenanceShell" -ThreadApartmentState STA
```

<span data-ttu-id="ed492-129">Esse comando altera o estado de apartment do thread na configuração MaintenanceShell para STA.</span><span class="sxs-lookup"><span data-stu-id="ed492-129">This command changes the thread apartment state in the MaintenanceShell configuration to STA.</span></span>
<span data-ttu-id="ed492-130">A alteração é eficaz quando você reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ed492-130">The change is effective when you restart the **WinRM** service.</span></span>

### <span data-ttu-id="ed492-131">Exemplo 2: criar e alterar uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="ed492-131">Example 2: Create and change a session configuration</span></span>

<span data-ttu-id="ed492-132">Este exemplo mostra como adicionar e remover um script de inicialização de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-132">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="ed492-133">O primeiro comando cria a configuração **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="ed492-133">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="ed492-134">O segundo comando adiciona o `AdminConfig.ps1` script à configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-134">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="ed492-135">A alteração é eficaz quando você reinicia o **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ed492-135">The change is effective when you restart **WinRM** .</span></span>
<span data-ttu-id="ed492-136">O terceiro comando Remove o `AdminConfig.ps1` script da configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-136">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="ed492-137">Exemplo 3: exibir resultados</span><span class="sxs-lookup"><span data-stu-id="ed492-137">Example 3: Display results</span></span>

<span data-ttu-id="ed492-138">Este exemplo aumenta o valor da propriedade **MaximumReceivedObjectSizeMB** para 20.</span><span class="sxs-lookup"><span data-stu-id="ed492-138">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="ed492-139">Esse comando também solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ed492-139">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="ed492-140">A alteração não será eficaz até que o serviço **WinRM** seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="ed492-140">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="ed492-141">Exemplo 4: exibir resultados de diferentes maneiras</span><span class="sxs-lookup"><span data-stu-id="ed492-141">Example 4: Display results in different ways</span></span>

<span data-ttu-id="ed492-142">Neste exemplo, `Set-PSSessionConfiguration` altera o script de inicialização na configuração de sessão **MaintenanceShell** para `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ed492-142">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="ed492-143">A saída mostra a alteração e solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ed492-143">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="ed492-144">A resposta é "y" (sim).</span><span class="sxs-lookup"><span data-stu-id="ed492-144">The response is "y" (yes).</span></span>

<span data-ttu-id="ed492-145">`Get-PSSessionConfiguration` Obtém a configuração da sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ed492-145">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="ed492-146">O operador de pipeline (|) envia os resultados do comando para `Format-List` , que exibe todas as propriedades do objeto de configuração em uma lista.</span><span class="sxs-lookup"><span data-stu-id="ed492-146">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="ed492-147">Em seguida, usando o provedor WSMan, exibimos os parâmetros de inicialização para a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ed492-147">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="ed492-148">`Get-ChildItem` (alias `dir` ) Obtém os itens filho no nó **InitializationParameters** para o plug-in **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="ed492-148">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="ed492-149">Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="ed492-149">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```
PS> Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PS> Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *

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

PS> dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="ed492-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed492-150">PARAMETERS</span></span>

### <span data-ttu-id="ed492-151">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="ed492-151">-AccessMode</span></span>

<span data-ttu-id="ed492-152">Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador.</span><span class="sxs-lookup"><span data-stu-id="ed492-152">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="ed492-153">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="ed492-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ed492-154">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="ed492-154">Disabled.</span></span> <span data-ttu-id="ed492-155">Desabilita a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-155">Disables the session configuration.</span></span> <span data-ttu-id="ed492-156">Ele não pode ser usado para acesso remoto ou local no computador.</span><span class="sxs-lookup"><span data-stu-id="ed492-156">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="ed492-157">Esse valor define a propriedade **Enabled** da configuração de sessão ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) como **false** .</span><span class="sxs-lookup"><span data-stu-id="ed492-157">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False** .</span></span>
- <span data-ttu-id="ed492-158">Local.</span><span class="sxs-lookup"><span data-stu-id="ed492-158">Local.</span></span> <span data-ttu-id="ed492-159">Adiciona uma entrada **Network_Deny_All** ao descritor de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-159">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="ed492-160">Os usuários do computador local podem usar a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas os usuários remotos têm o acesso negado.</span><span class="sxs-lookup"><span data-stu-id="ed492-160">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="ed492-161">Controle.</span><span class="sxs-lookup"><span data-stu-id="ed492-161">Remote.</span></span> <span data-ttu-id="ed492-162">Remove as entradas **Deny_All** e **Network_Deny_All** dos descritores de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-162">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="ed492-163">Usuários de computadores locais e remotos podem usar a configuração da sessão para criar sessões e executar comandos nesse computador.</span><span class="sxs-lookup"><span data-stu-id="ed492-163">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="ed492-164">O valor padrão é **remoto** .</span><span class="sxs-lookup"><span data-stu-id="ed492-164">The default value is **Remote** .</span></span>

<span data-ttu-id="ed492-165">Outros cmdlets podem substituir o valor desse parâmetro posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ed492-165">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="ed492-166">Por exemplo, o `Enable-PSRemoting` cmdlet habilita todas as configurações de sessão no computador e permite o acesso remoto a elas, e o `Disable-PSRemoting` cmdlet permite apenas acesso local a todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="ed492-166">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="ed492-167">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-167">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-168">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="ed492-168">-ApplicationBase</span></span>

<span data-ttu-id="ed492-169">Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="ed492-169">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="ed492-170">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="ed492-170">-AssemblyName</span></span>

<span data-ttu-id="ed492-171">Especifica o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="ed492-171">Specifies the assembly name.</span></span> <span data-ttu-id="ed492-172">Esse cmdlet cria uma configuração de sessão com base em uma classe que é definida em um assembly.</span><span class="sxs-lookup"><span data-stu-id="ed492-172">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="ed492-173">Insira o nome de arquivo ou caminho completo de um arquivos assembly. dll que define uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-173">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="ed492-174">Se você inserir apenas o nome do arquivo, poderá inserir o caminho no valor do parâmetro **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="ed492-174">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="ed492-175">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="ed492-175">-ConfigurationTypeName</span></span>

<span data-ttu-id="ed492-176">Especifica o tipo de configuração de sessão que é definido no assembly no parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="ed492-176">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="ed492-177">O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ed492-177">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="ed492-178">Esse parâmetro é necessário quando você especifica um nome de assembly.</span><span class="sxs-lookup"><span data-stu-id="ed492-178">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="ed492-179">-Force</span><span class="sxs-lookup"><span data-stu-id="ed492-179">-Force</span></span>

<span data-ttu-id="ed492-180">Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="ed492-180">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="ed492-181">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="ed492-181">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="ed492-182">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="ed492-182">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="ed492-183">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="ed492-183">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="ed492-184">Especifica o limite da quantidade de dados que podem ser enviados para este computador em qualquer comando remoto único.</span><span class="sxs-lookup"><span data-stu-id="ed492-184">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="ed492-185">Insira o tamanho dos dados em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="ed492-185">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="ed492-186">O valor padrão é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="ed492-186">The default is 50 MB.</span></span>

<span data-ttu-id="ed492-187">Se um limite de tamanho de dados for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="ed492-187">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="ed492-188">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="ed492-188">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed492-189">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="ed492-189">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="ed492-190">Especifica os limites na quantidade de dados que podem ser enviados para este computador em qualquer objeto único.</span><span class="sxs-lookup"><span data-stu-id="ed492-190">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="ed492-191">Insira o tamanho dos dados em megabytes.</span><span class="sxs-lookup"><span data-stu-id="ed492-191">Enter the data size in megabytes.</span></span> <span data-ttu-id="ed492-192">O padrão é 10 MB.</span><span class="sxs-lookup"><span data-stu-id="ed492-192">The default is 10 MB.</span></span>

<span data-ttu-id="ed492-193">Se um limite de tamanho de objeto for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="ed492-193">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="ed492-194">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="ed492-194">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed492-195">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="ed492-195">-ModulesToImport</span></span>

<span data-ttu-id="ed492-196">Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-196">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="ed492-197">Digite os nomes de módulo e o snap-in.</span><span class="sxs-lookup"><span data-stu-id="ed492-197">Enter the module and snap-in names.</span></span>

<span data-ttu-id="ed492-198">Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões, mas a menos que os cmdlets sejam excluídos, você pode usar os `Import-Module` cmdlets e Add-PSSnapin para adicionar módulos e snap-ins à sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-198">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="ed492-199">Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos especificados no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="ed492-199">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="ed492-200">No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.</span><span class="sxs-lookup"><span data-stu-id="ed492-200">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="ed492-201">Os módulos especificados nesse valor de parâmetro substituem a lista de módulos especificados usando o parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-201">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="ed492-202">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-202">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-203">-Name</span><span class="sxs-lookup"><span data-stu-id="ed492-203">-Name</span></span>

<span data-ttu-id="ed492-204">Especifica o nome da configuração de sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="ed492-204">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="ed492-205">Você não pode usar esse parâmetro para alterar o nome da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-205">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="ed492-206">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="ed492-206">-NoServiceRestart</span></span>

<span data-ttu-id="ed492-207">Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="ed492-207">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="ed492-208">Por padrão, quando você executa `Set-PSSessionConfiguration` o, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz.</span><span class="sxs-lookup"><span data-stu-id="ed492-208">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="ed492-209">Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="ed492-209">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="ed492-210">Para reiniciar o serviço **WinRM** sem avisar, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="ed492-210">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="ed492-211">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-211">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="ed492-212">-Path</span><span class="sxs-lookup"><span data-stu-id="ed492-212">-Path</span></span>

<span data-ttu-id="ed492-213">Especifica o caminho de um arquivo de configuração de sessão (. PSSC), como um criado pelo `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-213">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="ed492-214">Se você omitir o caminho, o padrão será o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="ed492-214">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="ed492-215">Para obter informações sobre como modificar um arquivo de configuração de sessão, consulte o tópico da ajuda para o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-215">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="ed492-216">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-217">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="ed492-217">-PSVersion</span></span>

<span data-ttu-id="ed492-218">Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-218">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="ed492-219">O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-219">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="ed492-220">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-220">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-221">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ed492-221">-RunAsCredential</span></span>

<span data-ttu-id="ed492-222">Especifica as credenciais para os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-222">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="ed492-223">Por padrão, os comandos são executados com as permissões do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="ed492-223">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="ed492-224">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-224">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-225">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="ed492-225">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="ed492-226">Especifica uma cadeia de caracteres SDDL (Security Descriptor Definition Language) diferentes para a configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-226">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="ed492-227">Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-227">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="ed492-228">Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-228">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="ed492-229">Para usar o descritor de segurança padrão para a configuração, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="ed492-229">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="ed492-230">O padrão é o SDDL raiz na unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="ed492-230">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="ed492-231">Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI dos** em vez deste.</span><span class="sxs-lookup"><span data-stu-id="ed492-231">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="ed492-232">Não é possível usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="ed492-232">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="ed492-233">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="ed492-233">-SessionTypeOption</span></span>

<span data-ttu-id="ed492-234">Especifica opções específicas de tipo para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-234">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="ed492-235">Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="ed492-235">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="ed492-236">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-236">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="ed492-237">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-237">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="ed492-238">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-238">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="ed492-239">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-239">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-240">-ShowSecurityDescriptorUI dos</span><span class="sxs-lookup"><span data-stu-id="ed492-240">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="ed492-241">Indica que esse cmdlet é uma folha de propriedades que ajuda a criar uma nova SDDL para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-241">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="ed492-242">A folha de propriedades aparece depois que você executa o `Set-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ed492-242">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="ed492-243">Quando você define permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-243">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="ed492-244">Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="ed492-244">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="ed492-245">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="ed492-245">-StartupScript</span></span>

<span data-ttu-id="ed492-246">Especifica o script de inicialização para a configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-246">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="ed492-247">Insira o caminho totalmente qualificado de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed492-247">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="ed492-248">O script especificado é executado na nova sessão que usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-248">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="ed492-249">Para excluir um script de inicialização de uma configuração de sessão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="ed492-249">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="ed492-250">Você pode usar um script de inicialização para configurar ainda mais a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed492-250">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="ed492-251">Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="ed492-251">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="ed492-252">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="ed492-252">-ThreadApartmentState</span></span>

<span data-ttu-id="ed492-253">Especifica a configuração de estado de apartamento para os threads na sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-253">Specifies the apartment state setting for the threads in the session.</span></span>
<span data-ttu-id="ed492-254">Os valores aceitáveis para esse parâmetro são: STA, MTA e Unknown.</span><span class="sxs-lookup"><span data-stu-id="ed492-254">The acceptable values for this parameter are: STA, MTA, and Unknown.</span></span>
<span data-ttu-id="ed492-255">O valor padrão é Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="ed492-255">The default value is Unknown.</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:
Accepted values: STA, MTA, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed492-256">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="ed492-256">-ThreadOptions</span></span>

<span data-ttu-id="ed492-257">Especifica a configuração de opções de thread na configuração.</span><span class="sxs-lookup"><span data-stu-id="ed492-257">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="ed492-258">Essa configuração define como threads são criados e usados quando um comando é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-258">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="ed492-259">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="ed492-259">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ed492-260">Padrão</span><span class="sxs-lookup"><span data-stu-id="ed492-260">Default</span></span>
- <span data-ttu-id="ed492-261">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="ed492-261">ReuseThread</span></span>
- <span data-ttu-id="ed492-262">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="ed492-262">UseCurrentThread</span></span>
- <span data-ttu-id="ed492-263">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="ed492-263">UseNewThread</span></span>

<span data-ttu-id="ed492-264">O valor padrão é **UseCurrentThread** .</span><span class="sxs-lookup"><span data-stu-id="ed492-264">The default value is **UseCurrentThread** .</span></span>

<span data-ttu-id="ed492-265">Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="ed492-265">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="ed492-266">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="ed492-266">-TransportOption</span></span>

<span data-ttu-id="ed492-267">Especifica as opções de transporte para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-267">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="ed492-268">Insira um objeto de opções de transporte, como o objeto **WSManConfigurationOption** que o `New-PSTransportOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="ed492-268">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="ed492-269">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-269">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="ed492-270">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-270">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="ed492-271">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-271">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="ed492-272">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-272">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-273">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="ed492-273">-UseSharedProcess</span></span>

<span data-ttu-id="ed492-274">Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-274">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="ed492-275">Por padrão, cada sessão é hospedada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="ed492-275">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="ed492-276">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-276">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed492-277">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed492-277">-Confirm</span></span>

<span data-ttu-id="ed492-278">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-278">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed492-279">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed492-279">-WhatIf</span></span>

<span data-ttu-id="ed492-280">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="ed492-280">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ed492-281">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="ed492-281">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed492-282">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed492-282">CommonParameters</span></span>

<span data-ttu-id="ed492-283">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed492-283">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed492-284">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed492-284">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed492-285">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ed492-285">INPUTS</span></span>

### <span data-ttu-id="ed492-286">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ed492-286">None</span></span>

<span data-ttu-id="ed492-287">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-287">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ed492-288">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ed492-288">OUTPUTS</span></span>

### <span data-ttu-id="ed492-289">Microsoft. WSMan. Management. WSManConfigLeafElement</span><span class="sxs-lookup"><span data-stu-id="ed492-289">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="ed492-290">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ed492-290">NOTES</span></span>

<span data-ttu-id="ed492-291">Para executar esse cmdlet, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="ed492-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="ed492-292">O `Set-PSSessionConfiguration` cmdlet não altera o nome da configuração e o provedor **WSMan** não oferece suporte ao `Rename-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed492-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="ed492-293">Para alterar o nome de uma configuração de sessão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração e, em seguida, use o `Register-PSSessionConfiguration` cmdlet para criar e registrar uma nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="ed492-294">Você pode usar o `Set-PSSessionConfiguration` cmdlet para alterar as configurações de sessão padrão Microsoft. PowerShell e Microsoft. powershell32.</span><span class="sxs-lookup"><span data-stu-id="ed492-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="ed492-295">Elas não são protegidas.</span><span class="sxs-lookup"><span data-stu-id="ed492-295">They are not protected.</span></span> <span data-ttu-id="ed492-296">Para reverter para a versão original de uma configuração de sessão padrão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração de sessão padrão e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-la.</span><span class="sxs-lookup"><span data-stu-id="ed492-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="ed492-297">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="ed492-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="ed492-298">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="ed492-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="ed492-299">É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="ed492-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="ed492-300">No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode** .</span><span class="sxs-lookup"><span data-stu-id="ed492-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="ed492-301">Os comandos do Windows PowerShell 2.0 não geram um erro, mas são ineficazes.</span><span class="sxs-lookup"><span data-stu-id="ed492-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="ed492-302">Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed492-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="ed492-303">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ed492-303">RELATED LINKS</span></span>

[<span data-ttu-id="ed492-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-305">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ed492-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="ed492-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="ed492-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="ed492-309">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="ed492-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="ed492-310">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="ed492-310">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="ed492-311">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-311">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-312">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-312">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-313">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ed492-313">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="ed492-314">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed492-314">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="ed492-315">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="ed492-315">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="ed492-316">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="ed492-316">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="ed492-317">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="ed492-317">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
