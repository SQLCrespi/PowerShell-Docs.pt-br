---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 0ec31d32ef73108b53b18b529cc93aa80787fe25
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598029"
---
# <span data-ttu-id="44ed2-102">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-102">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="44ed2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="44ed2-103">SYNOPSIS</span></span>
<span data-ttu-id="44ed2-104">Cria e registra uma nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-104">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="44ed2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44ed2-105">SYNTAX</span></span>

### <span data-ttu-id="44ed2-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="44ed2-106">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44ed2-107">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="44ed2-107">AssemblyNameParameterSet</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44ed2-108">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="44ed2-108">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="44ed2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44ed2-109">DESCRIPTION</span></span>

<span data-ttu-id="44ed2-110">O `Register-PSSessionConfiguration` cmdlet cria e registra uma nova configuração de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="44ed2-110">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="44ed2-111">Esse é um cmdlet avançado que você pode usar para criar sessões personalizadas para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="44ed2-111">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="44ed2-112">Cada sessão do PowerShell (**PSSession**) usa uma configuração de sessão, também conhecida como um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="44ed2-112">Every PowerShell session (**PSSession**) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="44ed2-113">Quando os usuários criam uma sessão que se conecta ao computador, eles podem selecionar uma configuração de sessão ou usar a configuração de sessão padrão que é registrada quando você habilita a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ed2-113">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="44ed2-114">Os usuários também podem definir a variável de preferência $PSSessionConfigurationName, que especifica uma configuração padrão para sessões remotas criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="44ed2-114">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="44ed2-115">A configuração da sessão define o ambiente para a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="44ed2-115">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="44ed2-116">A configuração pode determinar quais comandos e elementos de idioma estão disponíveis na sessão, e pode incluir configurações que protegem o computador, tal como as que limitam a quantidade de dados que a sessão pode receber remotamente em um único objeto ou o comando.</span><span class="sxs-lookup"><span data-stu-id="44ed2-116">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="44ed2-117">O descritor de segurança da configuração de sessão determina quais usuários têm permissão para usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-117">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="44ed2-118">Você pode definir os elementos de configuração por meio de um assembly que implementa uma nova classe de configuração e usando um script que é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-118">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="44ed2-119">A partir do PowerShell 3,0, você também pode usar um arquivo de configuração de sessão para definir a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-119">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="44ed2-120">Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="44ed2-120">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="44ed2-121">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="44ed2-121">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="44ed2-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="44ed2-122">EXAMPLES</span></span>

### <span data-ttu-id="44ed2-123">Exemplo 1: registrar uma configuração de sessão NewShell</span><span class="sxs-lookup"><span data-stu-id="44ed2-123">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="44ed2-124">Neste exemplo, registramos a configuração de sessão **NewShell** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-124">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="44ed2-125">Os parâmetros **AssemblyName** e **ApplicationBase** especificam o local do arquivo de **MyShell.dll** , que especifica os cmdlets e provedores na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-125">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="44ed2-126">O parâmetro **ConfigurationTypeName** especifica a classe de configuração a ser usada no assembly.</span><span class="sxs-lookup"><span data-stu-id="44ed2-126">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="44ed2-127">Para usar essa configuração, digite `New-PSSession -ConfigurationName newshell` .</span><span class="sxs-lookup"><span data-stu-id="44ed2-127">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="44ed2-128">Exemplo 2: registrar uma configuração de sessão MaintenanceShell</span><span class="sxs-lookup"><span data-stu-id="44ed2-128">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="44ed2-129">Este exemplo registra a configuração de sessão **MaintenanceShell** no computador local.</span><span class="sxs-lookup"><span data-stu-id="44ed2-129">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="44ed2-130">O parâmetro **StartupScript** especifica o `Maintenance.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="44ed2-130">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="44ed2-131">Quando um usuário usa um `New-PSSession` comando e seleciona a configuração **MaintenanceShell** , o `Maintenance.ps1` script é executado na nova sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-131">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="44ed2-132">O script pode configurar a sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-132">The script can configure the session.</span></span> <span data-ttu-id="44ed2-133">Isso inclui a importação de módulos e a definição da política de execução para a sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-133">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="44ed2-134">Se o script gerar erros, incluindo erros de não encerramento, o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="44ed2-134">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="44ed2-135">Exemplo 3: registrar uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="44ed2-135">Example 3: Register a session configuration</span></span>

<span data-ttu-id="44ed2-136">Este exemplo registra a configuração de sessão **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-136">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="44ed2-137">A `$sessionParams` variável é uma Hashtable que contém todos os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="44ed2-137">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="44ed2-138">Essa tabela de hash é passada para o cmdlet usando o PowerShell nivelamento.</span><span class="sxs-lookup"><span data-stu-id="44ed2-138">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="44ed2-139">O `Register-PSSessionConfiguration` comando usa o parâmetro **SecurityDescritorSDDL** para especificar o SDDL no valor da `$sddl` variável e o parâmetro **MaximumReceivedObjectSizeMB** para aumentar o limite de tamanho do objeto.</span><span class="sxs-lookup"><span data-stu-id="44ed2-139">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="44ed2-140">Ele também usa o parâmetro **StartupScript** para especificar um script que configura a sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-140">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### <span data-ttu-id="44ed2-141">Exemplo 4: retornar um elemento de contêiner de configuração</span><span class="sxs-lookup"><span data-stu-id="44ed2-141">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="44ed2-142">Este exemplo mostra como registrar a configuração do **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-142">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="44ed2-143">`Register-PSSessionConfiguration` Retorna um objeto **WSManConfigContainerElement** armazenado na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="44ed2-143">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="44ed2-144">`Format-List` exibe todas as propriedades do objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-144">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="44ed2-145">A propriedade **PSPath** mostra que o objeto é armazenado em um diretório da unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="44ed2-145">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="44ed2-146">`Get-ChildItem` (alias `dir` ) exibe os itens no `WSMan:\LocalHost\PlugIn` caminho.</span><span class="sxs-lookup"><span data-stu-id="44ed2-146">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="44ed2-147">Isso inclui a nova configuração do **MaintenanceShell** e as duas configurações padrão que vêm com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ed2-147">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### <span data-ttu-id="44ed2-148">Exemplo 5: registrar uma configuração de sessão com um script de inicialização</span><span class="sxs-lookup"><span data-stu-id="44ed2-148">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="44ed2-149">Neste exemplo, criamos e registramos a configuração de sessão **WithProfile** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-149">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="44ed2-150">O parâmetro **StartupScript** direciona o PowerShell para executar o script especificado para qualquer sessão que usa a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-150">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="44ed2-151">O script contém um único comando que usa o fornecimento de ponto para executar o perfil do usuário **CurrentUserAllHosts** no escopo da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="44ed2-151">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="44ed2-152">Para obter mais informações sobre perfis, consulte [about_Profiles](./About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="44ed2-152">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="44ed2-153">Para obter mais informações sobre como usar fontes de pontos, consulte [about_Scopes](./About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="44ed2-153">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="44ed2-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44ed2-154">PARAMETERS</span></span>

### <span data-ttu-id="44ed2-155">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="44ed2-155">-AccessMode</span></span>

<span data-ttu-id="44ed2-156">Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador.</span><span class="sxs-lookup"><span data-stu-id="44ed2-156">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="44ed2-157">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="44ed2-157">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="44ed2-158">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-158">Disabled.</span></span> <span data-ttu-id="44ed2-159">Desabilita a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-159">Disables the session configuration.</span></span> <span data-ttu-id="44ed2-160">Ele não pode ser usado para acesso remoto ou local no computador.</span><span class="sxs-lookup"><span data-stu-id="44ed2-160">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="44ed2-161">Local.</span><span class="sxs-lookup"><span data-stu-id="44ed2-161">Local.</span></span> <span data-ttu-id="44ed2-162">Permite que os usuários do computador local usem a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas nega o acesso a usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="44ed2-162">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="44ed2-163">Controle.</span><span class="sxs-lookup"><span data-stu-id="44ed2-163">Remote.</span></span> <span data-ttu-id="44ed2-164">Permite que os usuários locais e remotos usem a configuração da sessão para criar sessões e executar comandos nesse computador.</span><span class="sxs-lookup"><span data-stu-id="44ed2-164">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="44ed2-165">O valor padrão é remoto.</span><span class="sxs-lookup"><span data-stu-id="44ed2-165">The default value is Remote.</span></span>

<span data-ttu-id="44ed2-166">Outros cmdlets podem substituir o valor desse parâmetro posteriormente.</span><span class="sxs-lookup"><span data-stu-id="44ed2-166">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="44ed2-167">Por exemplo, o `Enable-PSRemoting` cmdlet permite o acesso remoto a todas as configurações de sessão, o `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão e o `Disable-PSRemoting` cmdlet impede o acesso remoto a todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-167">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="44ed2-168">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-168">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-169">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="44ed2-169">-ApplicationBase</span></span>

<span data-ttu-id="44ed2-170">Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-170">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="44ed2-171">Use esse parâmetro quando o valor do parâmetro **AssemblyName** não incluir um caminho.</span><span class="sxs-lookup"><span data-stu-id="44ed2-171">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="44ed2-172">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="44ed2-172">The default is the current directory.</span></span>

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

### <span data-ttu-id="44ed2-173">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="44ed2-173">-AssemblyName</span></span>

<span data-ttu-id="44ed2-174">Especifica o nome de um arquivo de assembly ( \* . dll) no qual o tipo de configuração é definido.</span><span class="sxs-lookup"><span data-stu-id="44ed2-174">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="44ed2-175">Você pode especificar o caminho do. dll nesse parâmetro ou no valor do parâmetro **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-175">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="44ed2-176">Esse parâmetro é necessário quando você especifica o parâmetro **ConfigurationTypeName** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-176">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

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

### <span data-ttu-id="44ed2-177">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="44ed2-177">-ConfigurationTypeName</span></span>

<span data-ttu-id="44ed2-178">Especifica o nome totalmente qualificado do tipo do Microsoft .NET Framework usado para esta configuração.</span><span class="sxs-lookup"><span data-stu-id="44ed2-178">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="44ed2-179">O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="44ed2-179">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="44ed2-180">Para especificar o arquivo de assembly ( \* . dll) que implementa o tipo de configuração, especifique os parâmetros **AssemblyName** e **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-180">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="44ed2-181">A criação de um tipo permite controlar mais aspectos da configuração de sessão, como expor ou ocultar determinados parâmetros de cmdlets ou definir o tamanho dos dados e limites de tamanho de objeto que os usuários não podem substituir.</span><span class="sxs-lookup"><span data-stu-id="44ed2-181">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="44ed2-182">Se você omitir esse parâmetro, a classe **DefaultRemotePowerShellConfiguration** é usada para a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-182">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

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

### <span data-ttu-id="44ed2-183">-Force</span><span class="sxs-lookup"><span data-stu-id="44ed2-183">-Force</span></span>

<span data-ttu-id="44ed2-184">Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="44ed2-184">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="44ed2-185">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="44ed2-185">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="44ed2-186">Para evitar uma reinicialização e suprimir o prompt de reinicialização, especifique o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-186">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="44ed2-187">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="44ed2-187">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="44ed2-188">Especifica um limite para a quantidade de dados que podem ser enviados a este computador em qualquer comando remoto único.</span><span class="sxs-lookup"><span data-stu-id="44ed2-188">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="44ed2-189">Insira o tamanho dos dados em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="44ed2-189">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="44ed2-190">O valor padrão é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="44ed2-190">The default is 50 MB.</span></span>

<span data-ttu-id="44ed2-191">Se um limite de tamanho de dados é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName**, o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-191">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="44ed2-192">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="44ed2-192">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="44ed2-193">Especifica um limite para a quantidade de dados que podem ser enviados para este computador em qualquer objeto único.</span><span class="sxs-lookup"><span data-stu-id="44ed2-193">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="44ed2-194">Insira o tamanho dos dados em megabytes.</span><span class="sxs-lookup"><span data-stu-id="44ed2-194">Enter the data size in megabytes.</span></span> <span data-ttu-id="44ed2-195">O padrão é 10 MB.</span><span class="sxs-lookup"><span data-stu-id="44ed2-195">The default is 10 MB.</span></span>

<span data-ttu-id="44ed2-196">Se um limite de tamanho do objeto é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName**, o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-196">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="44ed2-197">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="44ed2-197">-ModulesToImport</span></span>

<span data-ttu-id="44ed2-198">Especifica os módulos que são automaticamente importados para sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-198">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="44ed2-199">Por padrão, somente **o Microsoft. PowerShell. Core** é importado para sessões.</span><span class="sxs-lookup"><span data-stu-id="44ed2-199">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="44ed2-200">A menos que os cmdlets sejam excluídos, você pode usar o `Import-Module` para adicionar módulos à sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-200">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="44ed2-201">Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos que são especificados pelo parâmetro **SessionType** e aqueles listados na chave **ModulesToImport** no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="44ed2-201">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="44ed2-202">No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.</span><span class="sxs-lookup"><span data-stu-id="44ed2-202">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="44ed2-203">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-203">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-204">-Name</span><span class="sxs-lookup"><span data-stu-id="44ed2-204">-Name</span></span>

<span data-ttu-id="44ed2-205">Especifica um nome para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-205">Specifies a name for the session configuration.</span></span> <span data-ttu-id="44ed2-206">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="44ed2-206">This parameter is required.</span></span>

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

### <span data-ttu-id="44ed2-207">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="44ed2-207">-NoServiceRestart</span></span>

<span data-ttu-id="44ed2-208">Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="44ed2-208">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="44ed2-209">Por padrão, quando você executa um `Register-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz.</span><span class="sxs-lookup"><span data-stu-id="44ed2-209">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="44ed2-210">Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="44ed2-210">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="44ed2-211">Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-211">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="44ed2-212">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44ed2-212">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="44ed2-213">-Path</span><span class="sxs-lookup"><span data-stu-id="44ed2-213">-Path</span></span>

<span data-ttu-id="44ed2-214">Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC), como um criado por `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="44ed2-214">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="44ed2-215">Se você omitir o caminho, o padrão será o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="44ed2-215">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="44ed2-216">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-217">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="44ed2-217">-ProcessorArchitecture</span></span>

<span data-ttu-id="44ed2-218">Determina se uma versão de 32 bits ou 64 bits do processo do PowerShell é iniciada em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-218">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="44ed2-219">Os valores aceitáveis para esse parâmetro são: x86 (32 bits) e AMD64 (64 bits).</span><span class="sxs-lookup"><span data-stu-id="44ed2-219">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="44ed2-220">O valor padrão é determinado pela arquitetura de processador do computador que hospeda a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-220">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="44ed2-221">Você pode usar esse parâmetro para criar uma sessão de 32 bits em um computador de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="44ed2-221">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="44ed2-222">Tentativas de criar um processo de 64 bits em um computador de 32 bits falharão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-222">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44ed2-223">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="44ed2-223">-PSVersion</span></span>

<span data-ttu-id="44ed2-224">Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-224">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="44ed2-225">O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-225">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="44ed2-226">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-226">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-227">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="44ed2-227">-RunAsCredential</span></span>

<span data-ttu-id="44ed2-228">Especifica as credenciais para os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-228">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="44ed2-229">Por padrão, os comandos são executados com as permissões do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="44ed2-229">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="44ed2-230">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-230">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-231">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="44ed2-231">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="44ed2-232">Especifica uma cadeia de caracteres Security Descriptor Definition Language (SDDL) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="44ed2-232">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="44ed2-233">Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-233">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="44ed2-234">Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="44ed2-234">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="44ed2-235">Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI** em vez desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="44ed2-235">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="44ed2-236">Não é possível usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="44ed2-236">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="44ed2-237">Se você omitir esse parâmetro, o SDDL raiz para o serviço **WinRM** será usado para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="44ed2-237">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="44ed2-238">Para exibir ou alterar a raiz SDDL, use o provedor de WSMan.</span><span class="sxs-lookup"><span data-stu-id="44ed2-238">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="44ed2-239">Por exemplo, `Get-Item wsman:\localhost\service\rootSDDL`.</span><span class="sxs-lookup"><span data-stu-id="44ed2-239">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="44ed2-240">Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="44ed2-240">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

### <span data-ttu-id="44ed2-241">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="44ed2-241">-SessionTypeOption</span></span>

<span data-ttu-id="44ed2-242">Especifica opções específicas de tipo para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-242">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="44ed2-243">Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="44ed2-243">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="44ed2-244">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-244">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="44ed2-245">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-245">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="44ed2-246">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-246">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="44ed2-247">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-247">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-248">-ShowSecurityDescriptorUI dos</span><span class="sxs-lookup"><span data-stu-id="44ed2-248">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="44ed2-249">Indica que esse cmdlet exibe uma folha de propriedades que ajuda a criar o SDDL para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-249">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="44ed2-250">A folha de propriedades aparece depois que você insere o `Register-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-250">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="44ed2-251">Ao definir as permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-251">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="44ed2-252">Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="44ed2-252">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="44ed2-253">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="44ed2-253">-StartupScript</span></span>

<span data-ttu-id="44ed2-254">Especifica o caminho totalmente qualificado de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ed2-254">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="44ed2-255">O script especificado é executado na nova sessão que usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-255">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="44ed2-256">Você pode usar o script para configurar também a sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-256">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="44ed2-257">Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="44ed2-257">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="44ed2-258">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="44ed2-258">-ThreadOptions</span></span>

<span data-ttu-id="44ed2-259">Especifica como os threads são criados e usados quando um comando é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-259">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="44ed2-260">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="44ed2-260">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="44ed2-261">Padrão</span><span class="sxs-lookup"><span data-stu-id="44ed2-261">Default</span></span>
- <span data-ttu-id="44ed2-262">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="44ed2-262">ReuseThread</span></span>
- <span data-ttu-id="44ed2-263">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="44ed2-263">UseCurrentThread</span></span>
- <span data-ttu-id="44ed2-264">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="44ed2-264">UseNewThread</span></span>

<span data-ttu-id="44ed2-265">O valor padrão é **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="44ed2-265">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="44ed2-266">Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="44ed2-266">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="44ed2-267">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="44ed2-267">-TransportOption</span></span>

<span data-ttu-id="44ed2-268">Especifica a opção de transporte.</span><span class="sxs-lookup"><span data-stu-id="44ed2-268">Specifies the transport option.</span></span>

<span data-ttu-id="44ed2-269">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-270">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="44ed2-270">-UseSharedProcess</span></span>

<span data-ttu-id="44ed2-271">Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="44ed2-271">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="44ed2-272">Por padrão, cada sessão é hospedada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="44ed2-272">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="44ed2-273">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="44ed2-273">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="44ed2-274">-Confirm</span><span class="sxs-lookup"><span data-stu-id="44ed2-274">-Confirm</span></span>

<span data-ttu-id="44ed2-275">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44ed2-275">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="44ed2-276">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="44ed2-276">-WhatIf</span></span>

<span data-ttu-id="44ed2-277">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-277">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="44ed2-278">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-278">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="44ed2-279">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="44ed2-279">-ThreadApartmentState</span></span>

<span data-ttu-id="44ed2-280">Especifica o estado de apartment do módulo de Threading a ser usado.</span><span class="sxs-lookup"><span data-stu-id="44ed2-280">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="44ed2-281">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="44ed2-281">Acceptable values are:</span></span>

- <span data-ttu-id="44ed2-282">Unknown</span><span class="sxs-lookup"><span data-stu-id="44ed2-282">Unknown</span></span>
- <span data-ttu-id="44ed2-283">MTA</span><span class="sxs-lookup"><span data-stu-id="44ed2-283">MTA</span></span>
- <span data-ttu-id="44ed2-284">STA</span><span class="sxs-lookup"><span data-stu-id="44ed2-284">STA</span></span>

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

### <span data-ttu-id="44ed2-285">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44ed2-285">CommonParameters</span></span>

<span data-ttu-id="44ed2-286">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44ed2-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44ed2-287">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44ed2-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44ed2-288">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="44ed2-288">INPUTS</span></span>

### <span data-ttu-id="44ed2-289">Nenhum</span><span class="sxs-lookup"><span data-stu-id="44ed2-289">None</span></span>

<span data-ttu-id="44ed2-290">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44ed2-290">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="44ed2-291">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="44ed2-291">OUTPUTS</span></span>

### <span data-ttu-id="44ed2-292">Microsoft. WSMan. Management. WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="44ed2-292">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="44ed2-293">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="44ed2-293">NOTES</span></span>

<span data-ttu-id="44ed2-294">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="44ed2-294">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="44ed2-295">Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="44ed2-295">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="44ed2-296">Esse cmdlet gera XML que representa uma configuração de plug-in de serviços Web para gerenciamento (WS-Management) e envia o XML para WS-Management, que registra o plug-in no computador local ( `New-Item wsman:\localhost\plugin` ).</span><span class="sxs-lookup"><span data-stu-id="44ed2-296">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="44ed2-297">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="44ed2-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="44ed2-298">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="44ed2-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="44ed2-299">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="44ed2-299">RELATED LINKS</span></span>

[<span data-ttu-id="44ed2-300">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-300">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="44ed2-301">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-301">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="44ed2-302">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-302">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="44ed2-303">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="44ed2-303">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="44ed2-304">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-304">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="44ed2-305">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="44ed2-305">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="44ed2-306">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44ed2-306">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="44ed2-307">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="44ed2-307">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="44ed2-308">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="44ed2-308">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="44ed2-309">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="44ed2-309">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
