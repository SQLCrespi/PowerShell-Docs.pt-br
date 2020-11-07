---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 72ee8c7eebf7d74920fd0d39e3a508841e57b7c5
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347492"
---
# <span data-ttu-id="d7d4d-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="d7d4d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d7d4d-104">SYNOPSIS</span></span>
<span data-ttu-id="d7d4d-105">Altera as propriedades de uma configuração de sessão registrada.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="d7d4d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7d4d-106">SYNTAX</span></span>

### <span data-ttu-id="d7d4d-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d7d4d-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d7d4d-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="d7d4d-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d7d4d-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d7d4d-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d7d4d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7d4d-110">DESCRIPTION</span></span>

<span data-ttu-id="d7d4d-111">O `Set-PSSessionConfiguration` cmdlet altera as propriedades das configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="d7d4d-112">Use o parâmetro **Name** para identificar a configuração da sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="d7d4d-113">Use os outros parâmetros para especificar novos valores para as propriedades da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="d7d4d-114">Para excluir um valor de propriedade da configuração e usar o valor padrão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` para o parâmetro correspondente.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="d7d4d-115">A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="d7d4d-116">Esse recurso fornece um método simples e detectável para definir ou alterar as propriedades de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="d7d4d-117">Para especificar um arquivo de configuração de sessão, use o parâmetro **path** de `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="d7d4d-118">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="d7d4d-119">Para obter informações sobre como criar e modificar um arquivo de configuração de sessão, consulte o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="d7d4d-120">As configurações de sessão definem o ambiente de sessões remotas ( **PSSessions** ) que se conectam ao computador local.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="d7d4d-121">Cada **PSSession** usa uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="d7d4d-122">A configuração de sessão determina os recursos da **PSSession** , como os módulos disponíveis na sessão, os cmdlets que têm permissão para serem executados, o modo de linguagem, as cotas e os tempos limite.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="d7d4d-123">O descritor de segurança da configuração de sessão determina quem pode usar a configuração de sessão para se conectar ao computador local.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="d7d4d-124">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="d7d4d-125">Para ver as propriedades de uma configuração de sessão, use o `Get-PSSessionConfiguration` cmdlet ou o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="d7d4d-126">Para obter mais informações sobre o provedor WSMan, digite `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="d7d4d-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d7d4d-127">EXAMPLES</span></span>

### <span data-ttu-id="d7d4d-128">Exemplo 1: criar e alterar uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="d7d4d-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="d7d4d-129">Este exemplo mostra como adicionar e remover um script de inicialização de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="d7d4d-130">O primeiro comando cria a configuração **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="d7d4d-131">O segundo comando adiciona o `AdminConfig.ps1` script à configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="d7d4d-132">A alteração é eficaz quando você reinicia o **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-132">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="d7d4d-133">O terceiro comando Remove o `AdminConfig.ps1` script da configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="d7d4d-134">Exemplo 2: exibir resultados</span><span class="sxs-lookup"><span data-stu-id="d7d4d-134">Example 2: Display results</span></span>

<span data-ttu-id="d7d4d-135">Este exemplo aumenta o valor da propriedade **MaximumReceivedObjectSizeMB** para 20.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="d7d4d-136">Esse comando também solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="d7d4d-137">A alteração não será eficaz até que o serviço **WinRM** seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="d7d4d-138">Exemplo 3: exibir resultados de diferentes maneiras</span><span class="sxs-lookup"><span data-stu-id="d7d4d-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="d7d4d-139">Neste exemplo, `Set-PSSessionConfiguration` altera o script de inicialização na configuração de sessão **MaintenanceShell** para `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="d7d4d-140">A saída mostra a alteração e solicita que você reinicie o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="d7d4d-141">A resposta é "y" (sim).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-141">The response is "y" (yes).</span></span>

<span data-ttu-id="d7d4d-142">`Get-PSSessionConfiguration` Obtém a configuração da sessão **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="d7d4d-143">O operador de pipeline (|) envia os resultados do comando para `Format-List` , que exibe todas as propriedades do objeto de configuração em uma lista.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="d7d4d-144">Em seguida, usando o provedor WSMan, exibimos os parâmetros de inicialização para a configuração **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="d7d4d-145">`Get-ChildItem` (alias `dir` ) Obtém os itens filho no nó **InitializationParameters** para o plug-in **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="d7d4d-146">Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

## <span data-ttu-id="d7d4d-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7d4d-147">PARAMETERS</span></span>

### <span data-ttu-id="d7d4d-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="d7d4d-148">-AccessMode</span></span>

<span data-ttu-id="d7d4d-149">Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="d7d4d-150">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d7d4d-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d7d4d-151">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-151">Disabled.</span></span> <span data-ttu-id="d7d4d-152">Desabilita a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-152">Disables the session configuration.</span></span> <span data-ttu-id="d7d4d-153">Ele não pode ser usado para acesso remoto ou local no computador.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="d7d4d-154">Esse valor define a propriedade **Enabled** da configuração de sessão ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) como **false**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="d7d4d-155">Local.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-155">Local.</span></span> <span data-ttu-id="d7d4d-156">Adiciona uma entrada **Network_Deny_All** ao descritor de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="d7d4d-157">Os usuários do computador local podem usar a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas os usuários remotos têm o acesso negado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="d7d4d-158">Controle.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-158">Remote.</span></span> <span data-ttu-id="d7d4d-159">Remove as entradas **Deny_All** e **Network_Deny_All** dos descritores de segurança da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="d7d4d-160">Usuários de computadores locais e remotos podem usar a configuração da sessão para criar sessões e executar comandos nesse computador.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="d7d4d-161">O valor padrão é **remoto**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-161">The default value is **Remote**.</span></span>

<span data-ttu-id="d7d4d-162">Outros cmdlets podem substituir o valor desse parâmetro posteriormente.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="d7d4d-163">Por exemplo, o `Enable-PSRemoting` cmdlet habilita todas as configurações de sessão no computador e permite o acesso remoto a elas, e o `Disable-PSRemoting` cmdlet permite apenas acesso local a todas as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="d7d4d-164">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="d7d4d-165">-ApplicationBase</span></span>

<span data-ttu-id="d7d4d-166">Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="d7d4d-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="d7d4d-167">-AssemblyName</span></span>

<span data-ttu-id="d7d4d-168">Especifica o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-168">Specifies the assembly name.</span></span> <span data-ttu-id="d7d4d-169">Esse cmdlet cria uma configuração de sessão com base em uma classe que é definida em um assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="d7d4d-170">Insira o nome de arquivo ou caminho completo de um arquivos assembly. dll que define uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="d7d4d-171">Se você inserir apenas o nome do arquivo, poderá inserir o caminho no valor do parâmetro **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="d7d4d-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="d7d4d-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="d7d4d-173">Especifica o tipo de configuração de sessão que é definido no assembly no parâmetro **AssemblyName**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="d7d4d-174">O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="d7d4d-175">Esse parâmetro é necessário quando você especifica um nome de assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="d7d4d-176">-Force</span><span class="sxs-lookup"><span data-stu-id="d7d4d-176">-Force</span></span>

<span data-ttu-id="d7d4d-177">Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="d7d4d-178">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="d7d4d-179">Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="d7d4d-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="d7d4d-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="d7d4d-181">Especifica o limite da quantidade de dados que podem ser enviados para este computador em qualquer comando remoto único.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="d7d4d-182">Insira o tamanho dos dados em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="d7d4d-183">O valor padrão é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-183">The default is 50 MB.</span></span>

<span data-ttu-id="d7d4d-184">Se um limite de tamanho de dados for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="d7d4d-185">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="d7d4d-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="d7d4d-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="d7d4d-187">Especifica os limites na quantidade de dados que podem ser enviados para este computador em qualquer objeto único.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="d7d4d-188">Insira o tamanho dos dados em megabytes.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="d7d4d-189">O padrão é 10 MB.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-189">The default is 10 MB.</span></span>

<span data-ttu-id="d7d4d-190">Se um limite de tamanho de objeto for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="d7d4d-191">O valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="d7d4d-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="d7d4d-192">-ModulesToImport</span></span>

<span data-ttu-id="d7d4d-193">Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="d7d4d-194">Digite os nomes de módulo e o snap-in.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="d7d4d-195">Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões, mas a menos que os cmdlets sejam excluídos, você pode usar os `Import-Module` cmdlets e Add-PSSnapin para adicionar módulos e snap-ins à sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="d7d4d-196">Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos especificados no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="d7d4d-197">No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="d7d4d-198">Os módulos especificados nesse valor de parâmetro substituem a lista de módulos especificados usando o parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="d7d4d-199">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-200">-Name</span><span class="sxs-lookup"><span data-stu-id="d7d4d-200">-Name</span></span>

<span data-ttu-id="d7d4d-201">Especifica o nome da configuração de sessão que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="d7d4d-202">Você não pode usar esse parâmetro para alterar o nome da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="d7d4d-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="d7d4d-203">-NoServiceRestart</span></span>

<span data-ttu-id="d7d4d-204">Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="d7d4d-205">Por padrão, quando você executa `Set-PSSessionConfiguration` o, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="d7d4d-206">Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="d7d4d-207">Para reiniciar o serviço **WinRM** sem avisar, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="d7d4d-208">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="d7d4d-209">-Path</span><span class="sxs-lookup"><span data-stu-id="d7d4d-209">-Path</span></span>

<span data-ttu-id="d7d4d-210">Especifica o caminho de um arquivo de configuração de sessão (. PSSC), como um criado pelo `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="d7d4d-211">Se você omitir o caminho, o padrão será o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="d7d4d-212">Para obter informações sobre como modificar um arquivo de configuração de sessão, consulte o tópico da ajuda para o `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="d7d4d-213">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="d7d4d-214">-PSVersion</span></span>

<span data-ttu-id="d7d4d-215">Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="d7d4d-216">O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="d7d4d-217">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="d7d4d-218">-RunAsCredential</span></span>

<span data-ttu-id="d7d4d-219">Especifica as credenciais para os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="d7d4d-220">Por padrão, os comandos são executados com as permissões do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="d7d4d-221">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-222">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="d7d4d-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="d7d4d-223">Especifica uma cadeia de caracteres SDDL (Security Descriptor Definition Language) diferentes para a configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="d7d4d-224">Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="d7d4d-225">Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="d7d4d-226">Para usar o descritor de segurança padrão para a configuração, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="d7d4d-227">O padrão é o SDDL raiz na unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="d7d4d-228">Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI dos** em vez deste.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="d7d4d-229">Não é possível usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="d7d4d-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="d7d4d-230">-SessionTypeOption</span></span>

<span data-ttu-id="d7d4d-231">Especifica opções específicas de tipo para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="d7d4d-232">Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="d7d4d-233">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="d7d4d-234">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="d7d4d-235">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="d7d4d-236">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-237">-ShowSecurityDescriptorUI dos</span><span class="sxs-lookup"><span data-stu-id="d7d4d-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="d7d4d-238">Indica que esse cmdlet é uma folha de propriedades que ajuda a criar uma nova SDDL para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="d7d4d-239">A folha de propriedades aparece depois que você executa o `Set-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="d7d4d-240">Quando você define permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="d7d4d-241">Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="d7d4d-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="d7d4d-242">-StartupScript</span></span>

<span data-ttu-id="d7d4d-243">Especifica o script de inicialização para a configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="d7d4d-244">Insira o caminho totalmente qualificado de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="d7d4d-245">O script especificado é executado na nova sessão que usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="d7d4d-246">Para excluir um script de inicialização de uma configuração de sessão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .</span><span class="sxs-lookup"><span data-stu-id="d7d4d-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="d7d4d-247">Você pode usar um script de inicialização para configurar ainda mais a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="d7d4d-248">Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="d7d4d-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="d7d4d-249">-ThreadOptions</span></span>

<span data-ttu-id="d7d4d-250">Especifica a configuração de opções de thread na configuração.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="d7d4d-251">Essa configuração define como threads são criados e usados quando um comando é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="d7d4d-252">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d7d4d-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d7d4d-253">Padrão</span><span class="sxs-lookup"><span data-stu-id="d7d4d-253">Default</span></span>
- <span data-ttu-id="d7d4d-254">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="d7d4d-254">ReuseThread</span></span>
- <span data-ttu-id="d7d4d-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="d7d4d-255">UseCurrentThread</span></span>
- <span data-ttu-id="d7d4d-256">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="d7d4d-256">UseNewThread</span></span>

<span data-ttu-id="d7d4d-257">O valor padrão é **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-257">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="d7d4d-258">Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="d7d4d-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="d7d4d-259">-TransportOption</span></span>

<span data-ttu-id="d7d4d-260">Especifica as opções de transporte para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="d7d4d-261">Insira um objeto de opções de transporte, como o objeto **WSManConfigurationOption** que o `New-PSTransportOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="d7d4d-262">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="d7d4d-263">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="d7d4d-264">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="d7d4d-265">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="d7d4d-266">-UseSharedProcess</span></span>

<span data-ttu-id="d7d4d-267">Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="d7d4d-268">Por padrão, cada sessão é hospedada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="d7d4d-269">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d7d4d-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d7d4d-270">-Confirm</span></span>

<span data-ttu-id="d7d4d-271">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d7d4d-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d7d4d-272">-WhatIf</span></span>

<span data-ttu-id="d7d4d-273">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d7d4d-274">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d7d4d-275">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="d7d4d-275">-ThreadApartmentState</span></span>

<span data-ttu-id="d7d4d-276">Especifica o estado de apartment do módulo de Threading a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="d7d4d-277">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="d7d4d-277">Acceptable values are:</span></span>

- <span data-ttu-id="d7d4d-278">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="d7d4d-278">Unknown</span></span>
- <span data-ttu-id="d7d4d-279">MTA</span><span class="sxs-lookup"><span data-stu-id="d7d4d-279">MTA</span></span>
- <span data-ttu-id="d7d4d-280">STA</span><span class="sxs-lookup"><span data-stu-id="d7d4d-280">STA</span></span>

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

### <span data-ttu-id="d7d4d-281">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d7d4d-281">CommonParameters</span></span>

<span data-ttu-id="d7d4d-282">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7d4d-283">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d7d4d-284">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d7d4d-284">INPUTS</span></span>

### <span data-ttu-id="d7d4d-285">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7d4d-285">None</span></span>

<span data-ttu-id="d7d4d-286">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d7d4d-287">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d7d4d-287">OUTPUTS</span></span>

### <span data-ttu-id="d7d4d-288">Microsoft. WSMan. Management. WSManConfigLeafElement</span><span class="sxs-lookup"><span data-stu-id="d7d4d-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="d7d4d-289">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d7d4d-289">NOTES</span></span>

<span data-ttu-id="d7d4d-290">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-290">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="d7d4d-291">Para executar esse cmdlet, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="d7d4d-292">O `Set-PSSessionConfiguration` cmdlet não altera o nome da configuração e o provedor **WSMan** não oferece suporte ao `Rename-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="d7d4d-293">Para alterar o nome de uma configuração de sessão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração e, em seguida, use o `Register-PSSessionConfiguration` cmdlet para criar e registrar uma nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="d7d4d-294">Você pode usar o `Set-PSSessionConfiguration` cmdlet para alterar as configurações de sessão padrão Microsoft. PowerShell e Microsoft. powershell32.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="d7d4d-295">Elas não são protegidas.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-295">They are not protected.</span></span> <span data-ttu-id="d7d4d-296">Para reverter para a versão original de uma configuração de sessão padrão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração de sessão padrão e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-la.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="d7d4d-297">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="d7d4d-298">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="d7d4d-299">É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="d7d4d-300">No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode**.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="d7d4d-301">Os comandos do Windows PowerShell 2.0 não geram um erro, mas são ineficazes.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="d7d4d-302">Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="d7d4d-303">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d7d4d-303">RELATED LINKS</span></span>

[<span data-ttu-id="d7d4d-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="d7d4d-305">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="d7d4d-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="d7d4d-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d7d4d-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="d7d4d-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="d7d4d-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="d7d4d-309">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="d7d4d-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="d7d4d-310">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-310">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="d7d4d-311">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d7d4d-311">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="d7d4d-312">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7d4d-312">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="d7d4d-313">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="d7d4d-313">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="d7d4d-314">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="d7d4d-314">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="d7d4d-315">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="d7d4d-315">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
