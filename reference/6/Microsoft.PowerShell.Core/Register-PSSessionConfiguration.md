---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 6417881880cb7f317e7a42d6749b8b7f2cb712fb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345469"
---
# <span data-ttu-id="4f66c-103">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-103">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="4f66c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4f66c-104">SYNOPSIS</span></span>
<span data-ttu-id="4f66c-105">Cria e registra uma nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-105">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="4f66c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f66c-106">SYNTAX</span></span>

### <span data-ttu-id="4f66c-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="4f66c-107">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-SessionType <PSSessionType>]
 [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4f66c-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="4f66c-108">AssemblyNameParameterSet</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4f66c-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4f66c-109">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4f66c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4f66c-110">DESCRIPTION</span></span>

<span data-ttu-id="4f66c-111">O `Register-PSSessionConfiguration` cmdlet cria e registra uma nova configuração de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="4f66c-111">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="4f66c-112">Esse é um cmdlet avançado que você pode usar para criar sessões personalizadas para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="4f66c-112">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="4f66c-113">Cada sessão do PowerShell ( **PSSession** ) usa uma configuração de sessão, também conhecida como um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4f66c-113">Every PowerShell session ( **PSSession** ) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="4f66c-114">Quando os usuários criam uma sessão que se conecta ao computador, eles podem selecionar uma configuração de sessão ou usar a configuração de sessão padrão que é registrada quando você habilita a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f66c-114">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="4f66c-115">Os usuários também podem definir a variável de preferência $PSSessionConfigurationName, que especifica uma configuração padrão para sessões remotas criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4f66c-115">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="4f66c-116">A configuração da sessão define o ambiente para a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="4f66c-116">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="4f66c-117">A configuração pode determinar quais comandos e elementos de idioma estão disponíveis na sessão, e pode incluir configurações que protegem o computador, tal como as que limitam a quantidade de dados que a sessão pode receber remotamente em um único objeto ou o comando.</span><span class="sxs-lookup"><span data-stu-id="4f66c-117">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="4f66c-118">O descritor de segurança da configuração de sessão determina quais usuários têm permissão para usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-118">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="4f66c-119">Você pode definir os elementos de configuração por meio de um assembly que implementa uma nova classe de configuração e usando um script que é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-119">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="4f66c-120">A partir do PowerShell 3,0, você também pode usar um arquivo de configuração de sessão para definir a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-120">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="4f66c-121">Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4f66c-121">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="4f66c-122">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="4f66c-122">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="4f66c-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4f66c-123">EXAMPLES</span></span>

### <span data-ttu-id="4f66c-124">Exemplo 1: registrar uma configuração de sessão NewShell</span><span class="sxs-lookup"><span data-stu-id="4f66c-124">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="4f66c-125">Neste exemplo, registramos a configuração de sessão **NewShell** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-125">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="4f66c-126">Os parâmetros **AssemblyName** e **ApplicationBase** especificam o local do arquivo de **MyShell.dll** , que especifica os cmdlets e provedores na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-126">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="4f66c-127">O parâmetro **ConfigurationTypeName** especifica a classe de configuração a ser usada no assembly.</span><span class="sxs-lookup"><span data-stu-id="4f66c-127">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="4f66c-128">Para usar essa configuração, digite `New-PSSession -ConfigurationName newshell` .</span><span class="sxs-lookup"><span data-stu-id="4f66c-128">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="4f66c-129">Exemplo 2: registrar uma configuração de sessão MaintenanceShell</span><span class="sxs-lookup"><span data-stu-id="4f66c-129">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="4f66c-130">Este exemplo registra a configuração de sessão **MaintenanceShell** no computador local.</span><span class="sxs-lookup"><span data-stu-id="4f66c-130">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="4f66c-131">O parâmetro **StartupScript** especifica o `Maintenance.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="4f66c-131">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="4f66c-132">Quando um usuário usa um `New-PSSession` comando e seleciona a configuração **MaintenanceShell** , o `Maintenance.ps1` script é executado na nova sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-132">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="4f66c-133">O script pode configurar a sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-133">The script can configure the session.</span></span> <span data-ttu-id="4f66c-134">Isso inclui a importação de módulos e a definição da política de execução para a sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-134">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="4f66c-135">Se o script gerar erros, incluindo erros de não encerramento, o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="4f66c-135">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="4f66c-136">Exemplo 3: registrar uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="4f66c-136">Example 3: Register a session configuration</span></span>

<span data-ttu-id="4f66c-137">Este exemplo registra a configuração de sessão **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-137">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="4f66c-138">A `$sessionParams` variável é uma Hashtable que contém todos os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4f66c-138">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="4f66c-139">Essa tabela de hash é passada para o cmdlet usando o PowerShell nivelamento.</span><span class="sxs-lookup"><span data-stu-id="4f66c-139">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="4f66c-140">O `Register-PSSessionConfiguration` comando usa o parâmetro **SecurityDescritorSDDL** para especificar o SDDL no valor da `$sddl` variável e o parâmetro **MaximumReceivedObjectSizeMB** para aumentar o limite de tamanho do objeto.</span><span class="sxs-lookup"><span data-stu-id="4f66c-140">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="4f66c-141">Ele também usa o parâmetro **StartupScript** para especificar um script que configura a sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-141">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

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

### <span data-ttu-id="4f66c-142">Exemplo 4: retornar um elemento de contêiner de configuração</span><span class="sxs-lookup"><span data-stu-id="4f66c-142">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="4f66c-143">Este exemplo mostra como registrar a configuração do **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-143">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="4f66c-144">`Register-PSSessionConfiguration` Retorna um objeto **WSManConfigContainerElement** armazenado na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="4f66c-144">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="4f66c-145">`Format-List` exibe todas as propriedades do objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-145">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="4f66c-146">A propriedade **PSPath** mostra que o objeto é armazenado em um diretório da unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="4f66c-146">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="4f66c-147">`Get-ChildItem` (alias `dir` ) exibe os itens no `WSMan:\LocalHost\PlugIn` caminho.</span><span class="sxs-lookup"><span data-stu-id="4f66c-147">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="4f66c-148">Isso inclui a nova configuração do **MaintenanceShell** e as duas configurações padrão que vêm com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f66c-148">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

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

### <span data-ttu-id="4f66c-149">Exemplo 5: registrar uma configuração de sessão com um script de inicialização</span><span class="sxs-lookup"><span data-stu-id="4f66c-149">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="4f66c-150">Neste exemplo, criamos e registramos a configuração de sessão **WithProfile** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-150">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="4f66c-151">O parâmetro **StartupScript** direciona o PowerShell para executar o script especificado para qualquer sessão que usa a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-151">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="4f66c-152">O script contém um único comando que usa o fornecimento de ponto para executar o perfil do usuário **CurrentUserAllHosts** no escopo da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4f66c-152">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="4f66c-153">Para obter mais informações sobre perfis, consulte [about_Profiles](./About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4f66c-153">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="4f66c-154">Para obter mais informações sobre como usar fontes de pontos, consulte [about_Scopes](./About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="4f66c-154">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="4f66c-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f66c-155">PARAMETERS</span></span>

### <span data-ttu-id="4f66c-156">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="4f66c-156">-AccessMode</span></span>

<span data-ttu-id="4f66c-157">Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador.</span><span class="sxs-lookup"><span data-stu-id="4f66c-157">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="4f66c-158">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="4f66c-158">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4f66c-159">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-159">Disabled.</span></span> <span data-ttu-id="4f66c-160">Desabilita a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-160">Disables the session configuration.</span></span> <span data-ttu-id="4f66c-161">Ele não pode ser usado para acesso remoto ou local no computador.</span><span class="sxs-lookup"><span data-stu-id="4f66c-161">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="4f66c-162">Local.</span><span class="sxs-lookup"><span data-stu-id="4f66c-162">Local.</span></span> <span data-ttu-id="4f66c-163">Permite que os usuários do computador local usem a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas nega o acesso a usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="4f66c-163">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="4f66c-164">Controle.</span><span class="sxs-lookup"><span data-stu-id="4f66c-164">Remote.</span></span> <span data-ttu-id="4f66c-165">Permite que os usuários locais e remotos usem a configuração da sessão para criar sessões e executar comandos nesse computador.</span><span class="sxs-lookup"><span data-stu-id="4f66c-165">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="4f66c-166">O valor padrão é remoto.</span><span class="sxs-lookup"><span data-stu-id="4f66c-166">The default value is Remote.</span></span>

<span data-ttu-id="4f66c-167">Outros cmdlets podem substituir o valor desse parâmetro posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f66c-167">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="4f66c-168">Por exemplo, o `Enable-PSRemoting` cmdlet permite o acesso remoto a todas as configurações de sessão, o `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão e o `Disable-PSRemoting` cmdlet impede o acesso remoto a todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-168">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="4f66c-169">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-169">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-170">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="4f66c-170">-ApplicationBase</span></span>

<span data-ttu-id="4f66c-171">Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-171">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="4f66c-172">Use esse parâmetro quando o valor do parâmetro **AssemblyName** não incluir um caminho.</span><span class="sxs-lookup"><span data-stu-id="4f66c-172">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="4f66c-173">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="4f66c-173">The default is the current directory.</span></span>

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

### <span data-ttu-id="4f66c-174">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="4f66c-174">-AssemblyName</span></span>

<span data-ttu-id="4f66c-175">Especifica o nome de um arquivo de assembly ( \* . dll) no qual o tipo de configuração é definido.</span><span class="sxs-lookup"><span data-stu-id="4f66c-175">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="4f66c-176">Você pode especificar o caminho do. dll nesse parâmetro ou no valor do parâmetro **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-176">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="4f66c-177">Esse parâmetro é necessário quando você especifica o parâmetro **ConfigurationTypeName** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-177">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

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

### <span data-ttu-id="4f66c-178">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="4f66c-178">-ConfigurationTypeName</span></span>

<span data-ttu-id="4f66c-179">Especifica o nome totalmente qualificado do tipo do Microsoft .NET Framework usado para esta configuração.</span><span class="sxs-lookup"><span data-stu-id="4f66c-179">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="4f66c-180">O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4f66c-180">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="4f66c-181">Para especificar o arquivo de assembly ( \* . dll) que implementa o tipo de configuração, especifique os parâmetros **AssemblyName** e **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-181">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="4f66c-182">A criação de um tipo permite controlar mais aspectos da configuração de sessão, como expor ou ocultar determinados parâmetros de cmdlets ou definir o tamanho dos dados e limites de tamanho de objeto que os usuários não podem substituir.</span><span class="sxs-lookup"><span data-stu-id="4f66c-182">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="4f66c-183">Se você omitir esse parâmetro, a classe **DefaultRemotePowerShellConfiguration** é usada para a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-183">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

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

### <span data-ttu-id="4f66c-184">-Force</span><span class="sxs-lookup"><span data-stu-id="4f66c-184">-Force</span></span>

<span data-ttu-id="4f66c-185">Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar.</span><span class="sxs-lookup"><span data-stu-id="4f66c-185">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="4f66c-186">Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="4f66c-186">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="4f66c-187">Para evitar uma reinicialização e suprimir o prompt de reinicialização, especifique o parâmetro **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-187">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="4f66c-188">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="4f66c-188">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="4f66c-189">Especifica um limite para a quantidade de dados que podem ser enviados a este computador em qualquer comando remoto único.</span><span class="sxs-lookup"><span data-stu-id="4f66c-189">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="4f66c-190">Insira o tamanho dos dados em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="4f66c-190">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="4f66c-191">O valor padrão é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="4f66c-191">The default is 50 MB.</span></span>

<span data-ttu-id="4f66c-192">Se um limite de tamanho de dados é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-192">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="4f66c-193">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="4f66c-193">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="4f66c-194">Especifica um limite para a quantidade de dados que podem ser enviados para este computador em qualquer objeto único.</span><span class="sxs-lookup"><span data-stu-id="4f66c-194">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="4f66c-195">Insira o tamanho dos dados em megabytes.</span><span class="sxs-lookup"><span data-stu-id="4f66c-195">Enter the data size in megabytes.</span></span> <span data-ttu-id="4f66c-196">O padrão é 10 MB.</span><span class="sxs-lookup"><span data-stu-id="4f66c-196">The default is 10 MB.</span></span>

<span data-ttu-id="4f66c-197">Se um limite de tamanho do objeto é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-197">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="4f66c-198">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="4f66c-198">-ModulesToImport</span></span>

<span data-ttu-id="4f66c-199">Especifica os módulos que são automaticamente importados para sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-199">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="4f66c-200">Por padrão, somente **o Microsoft. PowerShell. Core** é importado para sessões.</span><span class="sxs-lookup"><span data-stu-id="4f66c-200">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="4f66c-201">A menos que os cmdlets sejam excluídos, você pode usar o `Import-Module` para adicionar módulos à sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-201">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="4f66c-202">Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos que são especificados pelo parâmetro **SessionType** e aqueles listados na chave **ModulesToImport** no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="4f66c-202">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="4f66c-203">No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.</span><span class="sxs-lookup"><span data-stu-id="4f66c-203">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="4f66c-204">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-204">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-205">-Name</span><span class="sxs-lookup"><span data-stu-id="4f66c-205">-Name</span></span>

<span data-ttu-id="4f66c-206">Especifica um nome para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-206">Specifies a name for the session configuration.</span></span> <span data-ttu-id="4f66c-207">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="4f66c-207">This parameter is required.</span></span>

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

### <span data-ttu-id="4f66c-208">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="4f66c-208">-NoServiceRestart</span></span>

<span data-ttu-id="4f66c-209">Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="4f66c-209">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="4f66c-210">Por padrão, quando você executa um `Register-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz.</span><span class="sxs-lookup"><span data-stu-id="4f66c-210">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="4f66c-211">Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="4f66c-211">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="4f66c-212">Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-212">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="4f66c-213">Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f66c-213">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="4f66c-214">-Path</span><span class="sxs-lookup"><span data-stu-id="4f66c-214">-Path</span></span>

<span data-ttu-id="4f66c-215">Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC), como um criado por `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="4f66c-215">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="4f66c-216">Se você omitir o caminho, o padrão será o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="4f66c-216">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="4f66c-217">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-218">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="4f66c-218">-ProcessorArchitecture</span></span>

<span data-ttu-id="4f66c-219">Determina se uma versão de 32 bits ou 64 bits do processo do PowerShell é iniciada em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-219">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="4f66c-220">Os valores aceitáveis para esse parâmetro são: x86 (32 bits) e AMD64 (64 bits).</span><span class="sxs-lookup"><span data-stu-id="4f66c-220">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="4f66c-221">O valor padrão é determinado pela arquitetura de processador do computador que hospeda a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-221">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="4f66c-222">Você pode usar esse parâmetro para criar uma sessão de 32 bits em um computador de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4f66c-222">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="4f66c-223">Tentativas de criar um processo de 64 bits em um computador de 32 bits falharão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-223">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

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

### <span data-ttu-id="4f66c-224">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="4f66c-224">-PSVersion</span></span>

<span data-ttu-id="4f66c-225">Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-225">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="4f66c-226">O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-226">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="4f66c-227">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-228">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="4f66c-228">-RunAsCredential</span></span>

<span data-ttu-id="4f66c-229">Especifica as credenciais para os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-229">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="4f66c-230">Por padrão, os comandos são executados com as permissões do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="4f66c-230">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="4f66c-231">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-231">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-232">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="4f66c-232">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="4f66c-233">Especifica uma cadeia de caracteres Security Descriptor Definition Language (SDDL) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="4f66c-233">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="4f66c-234">Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-234">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="4f66c-235">Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.</span><span class="sxs-lookup"><span data-stu-id="4f66c-235">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="4f66c-236">Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI** em vez desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4f66c-236">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="4f66c-237">Não é possível usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="4f66c-237">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="4f66c-238">Se você omitir esse parâmetro, o SDDL raiz para o serviço **WinRM** será usado para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="4f66c-238">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="4f66c-239">Para exibir ou alterar a raiz SDDL, use o provedor de WSMan.</span><span class="sxs-lookup"><span data-stu-id="4f66c-239">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="4f66c-240">Por exemplo, `Get-Item wsman:\localhost\service\rootSDDL`.</span><span class="sxs-lookup"><span data-stu-id="4f66c-240">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="4f66c-241">Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="4f66c-241">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

### <span data-ttu-id="4f66c-242">-SessionType</span><span class="sxs-lookup"><span data-stu-id="4f66c-242">-SessionType</span></span>

<span data-ttu-id="4f66c-243">Especifica o tipo de sessão que é criada usando a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-243">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="4f66c-244">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="4f66c-244">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4f66c-245">Vazio.</span><span class="sxs-lookup"><span data-stu-id="4f66c-245">Empty.</span></span> <span data-ttu-id="4f66c-246">Nenhum módulo é adicionado à sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-246">No modules are added to session by default.</span></span> <span data-ttu-id="4f66c-247">Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-247">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>
- <span data-ttu-id="4f66c-248">Padrão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-248">Default.</span></span> <span data-ttu-id="4f66c-249">Adiciona o Microsoft. PowerShell. Core à sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-249">Adds Microsoft.PowerShell.Core to the session.</span></span> <span data-ttu-id="4f66c-250">Esse módulo inclui o `Import-Module` cmdlet que os usuários podem usar para importar outros módulos, a menos que você proíba explicitamente o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f66c-250">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit the cmdlet.</span></span>
- <span data-ttu-id="4f66c-251">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="4f66c-251">RestrictedRemoteServer.</span></span> <span data-ttu-id="4f66c-252">Inclui apenas os seguintes cmdlets:,,,,, `Exit-PSSession` `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` e `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="4f66c-252">Includes only the following cmdlets: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span> <span data-ttu-id="4f66c-253">Use um script ou assembly, ou então as chaves no arquivo de configuração de sessão, para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-253">Use a script or assembly, or the keys in the session configuration file, to add modules, functions, scripts, and other features to the session.</span></span>

<span data-ttu-id="4f66c-254">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="4f66c-254">The default value is Default.</span></span>

<span data-ttu-id="4f66c-255">O valor desse parâmetro tem precedência sobre o valor da chave **SessionType** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-255">The value of this parameter takes precedence over the value of the **SessionType** key in the session configuration file.</span></span>

<span data-ttu-id="4f66c-256">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-256">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionType
Parameter Sets: NameParameterSet
Aliases:
Accepted values: DefaultRemoteShell, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f66c-257">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="4f66c-257">-SessionTypeOption</span></span>

<span data-ttu-id="4f66c-258">Especifica opções específicas de tipo para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-258">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="4f66c-259">Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="4f66c-259">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="4f66c-260">As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-260">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="4f66c-261">A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-261">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="4f66c-262">No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-262">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="4f66c-263">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-263">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-264">-ShowSecurityDescriptorUI dos</span><span class="sxs-lookup"><span data-stu-id="4f66c-264">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="4f66c-265">Indica que esse cmdlet exibe uma folha de propriedades que ajuda a criar o SDDL para a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-265">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="4f66c-266">A folha de propriedades aparece depois que você insere o `Register-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-266">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="4f66c-267">Ao definir as permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-267">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="4f66c-268">Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="4f66c-268">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="4f66c-269">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="4f66c-269">-StartupScript</span></span>

<span data-ttu-id="4f66c-270">Especifica o caminho totalmente qualificado de um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f66c-270">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="4f66c-271">O script especificado é executado na nova sessão que usar a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-271">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="4f66c-272">Você pode usar o script para configurar também a sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-272">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="4f66c-273">Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="4f66c-273">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="4f66c-274">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="4f66c-274">-ThreadOptions</span></span>

<span data-ttu-id="4f66c-275">Especifica como os threads são criados e usados quando um comando é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-275">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="4f66c-276">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="4f66c-276">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4f66c-277">Padrão</span><span class="sxs-lookup"><span data-stu-id="4f66c-277">Default</span></span>
- <span data-ttu-id="4f66c-278">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="4f66c-278">ReuseThread</span></span>
- <span data-ttu-id="4f66c-279">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="4f66c-279">UseCurrentThread</span></span>
- <span data-ttu-id="4f66c-280">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="4f66c-280">UseNewThread</span></span>

<span data-ttu-id="4f66c-281">O valor padrão é **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="4f66c-281">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="4f66c-282">Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="4f66c-282">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="4f66c-283">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="4f66c-283">-TransportOption</span></span>

<span data-ttu-id="4f66c-284">Especifica a opção de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f66c-284">Specifies the transport option.</span></span>

<span data-ttu-id="4f66c-285">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-285">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-286">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="4f66c-286">-UseSharedProcess</span></span>

<span data-ttu-id="4f66c-287">Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="4f66c-287">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="4f66c-288">Por padrão, cada sessão é hospedada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="4f66c-288">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="4f66c-289">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f66c-289">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f66c-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4f66c-290">-Confirm</span></span>

<span data-ttu-id="4f66c-291">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f66c-291">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4f66c-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4f66c-292">-WhatIf</span></span>

<span data-ttu-id="4f66c-293">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4f66c-294">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="4f66c-294">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4f66c-295">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4f66c-295">CommonParameters</span></span>

<span data-ttu-id="4f66c-296">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4f66c-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f66c-297">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4f66c-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f66c-298">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4f66c-298">INPUTS</span></span>

### <span data-ttu-id="4f66c-299">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4f66c-299">None</span></span>

<span data-ttu-id="4f66c-300">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f66c-300">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4f66c-301">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4f66c-301">OUTPUTS</span></span>

### <span data-ttu-id="4f66c-302">Microsoft. WSMan. Management. WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="4f66c-302">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="4f66c-303">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4f66c-303">NOTES</span></span>

<span data-ttu-id="4f66c-304">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="4f66c-304">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="4f66c-305">Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="4f66c-305">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="4f66c-306">Esse cmdlet gera XML que representa uma configuração de plug-in de serviços Web para gerenciamento (WS-Management) e envia o XML para WS-Management, que registra o plug-in no computador local ( `New-Item wsman:\localhost\plugin` ).</span><span class="sxs-lookup"><span data-stu-id="4f66c-306">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="4f66c-307">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="4f66c-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="4f66c-308">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="4f66c-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="4f66c-309">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4f66c-309">RELATED LINKS</span></span>

[<span data-ttu-id="4f66c-310">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-310">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4f66c-311">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-311">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="4f66c-312">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-312">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4f66c-313">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4f66c-313">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="4f66c-314">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-314">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4f66c-315">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4f66c-315">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="4f66c-316">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f66c-316">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="4f66c-317">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="4f66c-317">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="4f66c-318">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="4f66c-318">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="4f66c-319">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="4f66c-319">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
