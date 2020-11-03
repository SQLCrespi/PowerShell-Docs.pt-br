---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: 300fc3dee2e0d625e5aea42bfdcf45ea2e8b5a7f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195028"
---
# <span data-ttu-id="04121-103">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-103">Get-PSSessionConfiguration</span></span>

## <span data-ttu-id="04121-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="04121-104">SYNOPSIS</span></span>
<span data-ttu-id="04121-105">Obtém as configurações de sessão registradas no computador.</span><span class="sxs-lookup"><span data-stu-id="04121-105">Gets the registered session configurations on the computer.</span></span>

## <span data-ttu-id="04121-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04121-106">SYNTAX</span></span>

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="04121-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04121-107">DESCRIPTION</span></span>

<span data-ttu-id="04121-108">O `Get-PSSessionConfiguration` cmdlet obtém as configurações de sessão que foram registradas no computador local.</span><span class="sxs-lookup"><span data-stu-id="04121-108">The `Get-PSSessionConfiguration` cmdlet gets the session configurations that have been registered on the local computer.</span></span> <span data-ttu-id="04121-109">Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="04121-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="04121-110">A partir do PowerShell 3,0, você pode definir as propriedades de uma configuração de sessão usando um arquivo de configuração de sessão (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="04121-110">Beginning in PowerShell 3.0, you can define the properties of a session configuration by using a session configuration (.pssc) file.</span></span> <span data-ttu-id="04121-111">Esse recurso permite criar sessões restritas e personalizadas sem escrever um programa de computador.</span><span class="sxs-lookup"><span data-stu-id="04121-111">This feature lets you create customized and restricted sessions without writing a computer program.</span></span> <span data-ttu-id="04121-112">Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="04121-112">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="04121-113">Além disso, a partir do PowerShell 3,0, novas propriedades de observação foram adicionadas ao objeto de configuração de sessão que `Get-PSSessionConfiguration` retorna.</span><span class="sxs-lookup"><span data-stu-id="04121-113">Also, beginning in PowerShell 3.0, new note properties have been added to the session configuration object that `Get-PSSessionConfiguration` returns.</span></span> <span data-ttu-id="04121-114">Essas propriedades facilitam para os usuários e autores de configuração de sessão examinarem e compararem as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-114">These properties make it easier for users and session configuration authors to examine and compare session configurations.</span></span>

<span data-ttu-id="04121-115">Para criar e registrar uma configuração de sessão, use o `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="04121-115">To create and register a session configuration, use the `Register-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="04121-116">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="04121-116">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="04121-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="04121-117">EXAMPLES</span></span>

### <span data-ttu-id="04121-118">Exemplo 1-obter configurações de sessão no computador local</span><span class="sxs-lookup"><span data-stu-id="04121-118">Example 1 - Get session configurations on the local computer</span></span>

```powershell
Get-PSSessionConfiguration
```

### <span data-ttu-id="04121-119">Exemplo 2-obter as duas configurações de sessão padrão</span><span class="sxs-lookup"><span data-stu-id="04121-119">Example 2 - Get the two default session configurations</span></span>

<span data-ttu-id="04121-120">O comando usa o parâmetro **Name** de `Get-PSSessionConfiguration` para obter apenas as configurações de sessão com nomes que começam com "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="04121-120">The command uses the **Name** parameter of `Get-PSSessionConfiguration` to get only the session configurations with names that begin with "Microsoft".</span></span>

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### <span data-ttu-id="04121-121">Exemplo 3-obter as propriedades e os valores de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="04121-121">Example 3 - Get the properties and values of a session configuration</span></span>

<span data-ttu-id="04121-122">Este exemplo mostra as propriedades e os valores de propriedade de uma configuração de sessão que foi criada utilizando um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-122">This example shows the properties and property values of a session configuration that was created by using a session configuration file.</span></span>

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

<span data-ttu-id="04121-123">O exemplo usa o `Get-PSSessionConfiguration` cmdlet para obter a configuração de sessão completa.</span><span class="sxs-lookup"><span data-stu-id="04121-123">The example uses the `Get-PSSessionConfiguration` cmdlet to get the full session configuration.</span></span> <span data-ttu-id="04121-124">Um operador de pipeline envia a configuração de sessão completa para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="04121-124">A pipeline operator sends the Full session configuration to the `Format-List` cmdlet.</span></span> <span data-ttu-id="04121-125">O parâmetro **Property** com um valor de `*` (All) direciona `Format-List` para exibir todas as propriedades e valores do objeto em uma lista.</span><span class="sxs-lookup"><span data-stu-id="04121-125">The **Property** parameter with a value of `*` (all) directs `Format-List` to display all the properties and values of the object in a list.</span></span>

<span data-ttu-id="04121-126">A saída inclui informações úteis, incluindo o autor da configuração de sessão, o tipo de sessão, o modo de linguagem e a política de execução de sessões criadas com essa configuração de sessão, cotas de sessão e o caminho completo para o arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-126">The output includes useful information, including the author of the session configuration, the session type, language mode, and execution policy of sessions that are created with this session configuration, session quotas, and the full path to the session configuration file.</span></span>

<span data-ttu-id="04121-127">Este modo de exibição de uma configuração de sessão é utilizado para sessões que incluem um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-127">This view of a session configuration is used for sessions that include a session configuration file.</span></span>
<span data-ttu-id="04121-128">Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="04121-128">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

### <span data-ttu-id="04121-129">Exemplo 4-outra maneira de examinar as configurações de sessão</span><span class="sxs-lookup"><span data-stu-id="04121-129">Example 4 - Another way to look at the session configurations</span></span>

<span data-ttu-id="04121-130">Este exemplo usa o `Get-ChildItem` cmdlet (alias `dir` ) na unidade WSMan: Provider para examinar o conteúdo do nó plugin.</span><span class="sxs-lookup"><span data-stu-id="04121-130">This example uses the `Get-ChildItem` cmdlet (alias `dir`) in the WSMan: provider drive to look at the content of the Plugin node.</span></span> <span data-ttu-id="04121-131">Essa é outra maneira para examinar as configurações de sessão no computador.</span><span class="sxs-lookup"><span data-stu-id="04121-131">This is another way to look at the session configurations on the computer.</span></span>

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="04121-132">O nó **plugin** contém objetos **ContainerElement** (Microsoft. WSMan. Management. WSManConfigContainerElement) que representam as configurações de sessão do PowerShell registradas, juntamente com outros plug-ins para WS-Management.</span><span class="sxs-lookup"><span data-stu-id="04121-132">The **PlugIn** node contains **ContainerElement** objects (Microsoft.WSMan.Management.WSManConfigContainerElement) that represent the registered PowerShell session configurations, along with other plug-ins for WS-Management.</span></span>

### <span data-ttu-id="04121-133">Exemplo 6-exibir configurações de sessão em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="04121-133">Example 6 - View session configurations on a remote computer</span></span>

<span data-ttu-id="04121-134">Este exemplo mostra como utilizar o provedor WSMan para exibir as configurações de sessão em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-134">This example shows how to use the WSMan provider to view the session configurations on a remote computer.</span></span> <span data-ttu-id="04121-135">Esse método não fornece tantas informações quanto um `Get-PSSessionConfiguration` comando, mas o usuário não precisa ser um membro do grupo de administradores para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="04121-135">This method does not provide as much information as a `Get-PSSessionConfiguration` command, but the user does not need to be a member of the Administrators group to run this cmdlet.</span></span>

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="04121-136">O `Connect-WSMan` cmdlet se conecta ao serviço WinRM no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="04121-136">The `Connect-WSMan` cmdlet connects to the WinRM service on the Server01 remote computer.</span></span> <span data-ttu-id="04121-137">O `Get-ChildItem` cmdlet (alias `dir` ) da unidade WSMan: Obtém os itens no caminho **Server01\Plugin** .</span><span class="sxs-lookup"><span data-stu-id="04121-137">The `Get-ChildItem` cmdlet (alias `dir`) of the WSMan: drive gets the items in the **Server01\Plugin** path.</span></span> <span data-ttu-id="04121-138">A saída mostra os itens no diretório de plug-in no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="04121-138">The output shows the items in the Plugin directory on the Server01 computer.</span></span> <span data-ttu-id="04121-139">Os itens incluem as configurações de sessão, que são um tipo de plug-in, junto com outros tipos de plug-ins no computador WSMan.</span><span class="sxs-lookup"><span data-stu-id="04121-139">The items include the session configurations, which are a type of WSMan plug-in, along with other types of plug-ins on the computer.</span></span>

### <span data-ttu-id="04121-140">Exemplo 7-obter configurações de sessão detalhadas de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="04121-140">Example 7 - Get detailed session configurations from a remote computer</span></span>

<span data-ttu-id="04121-141">Este exemplo mostra como executar um `Get-PSSessionConfiguration` comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-141">This example shows how to run a `Get-PSSessionConfiguration` command on a remote computer.</span></span> <span data-ttu-id="04121-142">O comando requer que a delegação CredSSP esteja habilitada nas configurações do cliente no computador local e as configurações de serviço no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-142">The command requires that CredSSP delegation be enabled in the client settings on the local computer and in the service settings on the remote computer.</span></span>

<span data-ttu-id="04121-143">Para executar os comandos neste exemplo, você deve ser um membro do grupo Administradores nos computadores locais e remotos, e você deve iniciar o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="04121-143">To run the commands in this example, you must be a member of the Administrators group on the local and remote computers and you must start PowerShell with the **Run as administrator** option.</span></span>

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

<span data-ttu-id="04121-144">O `Enable-WSManCredSSP` cmdlet habilita a delegação **CredSSP** em Server01, o computador local.</span><span class="sxs-lookup"><span data-stu-id="04121-144">The `Enable-WSManCredSSP` cmdlet enables **CredSSP** delegation on Server01, the local computer.</span></span> <span data-ttu-id="04121-145">O `Connect-WSMan` cmdlet se conecta ao computador Server02.</span><span class="sxs-lookup"><span data-stu-id="04121-145">The `Connect-WSMan` cmdlet connects to Server02 computer.</span></span> <span data-ttu-id="04121-146">Essa ação adiciona um nó para Server02 à unidade WSMan: no computador local, permitindo que você exiba e altere as configurações de WS-Management no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="04121-146">This action adds a node for Server02 to the WSMan: drive on the local computer, allowing you to view and change the WS-Management settings on the Server02 computer.</span></span> <span data-ttu-id="04121-147">O `Set-Item` cmdlet altera o valor do item **CredSSP** no nó de serviço do computador Server02 para **true** .</span><span class="sxs-lookup"><span data-stu-id="04121-147">The `Set-Item` cmdlet changes the value of the **CredSSP** item in the Service node of the Server02 computer to **True** .</span></span> <span data-ttu-id="04121-148">Isso define as configurações de serviço no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-148">This configures the service settings on the remote computer.</span></span> <span data-ttu-id="04121-149">O `Invoke-Command` cmdlet executa o `Get-PSSessionConfiguration` comando no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="04121-149">The `Invoke-Command` cmdlet runs the`Get-PSSessionConfiguration` command on the Server02 computer.</span></span> <span data-ttu-id="04121-150">O comando utiliza os parâmetros **Credential** e **Authentication** com um valor **CredSSP** .</span><span class="sxs-lookup"><span data-stu-id="04121-150">The command uses the **Credential** parameter, and it uses the **Authentication** parameter with a value of **CredSSP** .</span></span> <span data-ttu-id="04121-151">A saída mostra as configurações de sessão no computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="04121-151">The output shows the session configurations on the Server02 remote computer.</span></span>

### <span data-ttu-id="04121-152">Exemplo 8-obter o URI de recurso de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="04121-152">Example 8 - Get the resource URI of a session configuration</span></span>

<span data-ttu-id="04121-153">Este exemplo é útil para definir o valor da `$PSSessionConfigurationName` variável de preferência, que usa um URI de recurso.</span><span class="sxs-lookup"><span data-stu-id="04121-153">This example is useful for setting the value of the `$PSSessionConfigurationName` preference variable, which takes a resource URI.</span></span>

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

<span data-ttu-id="04121-154">A `$PSSessionConfigurationName` variável especifica a configuração padrão que é usada quando você cria uma sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-154">The `$PSSessionConfigurationName` variable specifies the default configuration that is used when you create a session.</span></span> <span data-ttu-id="04121-155">Essa variável é definida no computador local, mas ela especifica uma configuração no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-155">This variable is set on the local computer, but it specifies a configuration on the remote computer.</span></span> <span data-ttu-id="04121-156">Para obter mais informações sobre a `$PSSessionConfiguration` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="04121-156">For more information about the `$PSSessionConfiguration` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="04121-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04121-157">PARAMETERS</span></span>

### <span data-ttu-id="04121-158">-Force</span><span class="sxs-lookup"><span data-stu-id="04121-158">-Force</span></span>

<span data-ttu-id="04121-159">Suprime o prompt para reiniciar o serviço WinRM, se o serviço não estiver sendo executado.</span><span class="sxs-lookup"><span data-stu-id="04121-159">Suppresses the prompt to restart the WinRM service, if the service is not already running.</span></span>

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

### <span data-ttu-id="04121-160">-Name</span><span class="sxs-lookup"><span data-stu-id="04121-160">-Name</span></span>

<span data-ttu-id="04121-161">Obtém somente as configurações de sessão com o nome especificado ou o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="04121-161">Gets only the session configurations with the specified name or name pattern.</span></span> <span data-ttu-id="04121-162">Insira um ou mais nomes de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-162">Enter one or more session configuration names.</span></span> <span data-ttu-id="04121-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="04121-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="04121-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="04121-164">CommonParameters</span></span>

<span data-ttu-id="04121-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04121-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04121-166">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="04121-166">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="04121-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="04121-167">INPUTS</span></span>

### <span data-ttu-id="04121-168">Nenhum</span><span class="sxs-lookup"><span data-stu-id="04121-168">None</span></span>

<span data-ttu-id="04121-169">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="04121-169">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="04121-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="04121-170">OUTPUTS</span></span>

### <span data-ttu-id="04121-171">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-171">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

## <span data-ttu-id="04121-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="04121-172">NOTES</span></span>

- <span data-ttu-id="04121-173">Para executar esse cmdlet, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="04121-173">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

- <span data-ttu-id="04121-174">Para exibir as configurações de sessão no computador, você deve ser um membro do grupo Administradores no computador.</span><span class="sxs-lookup"><span data-stu-id="04121-174">To view the session configurations on the computer, you must be a member of the Administrators group on the computer.</span></span>

- <span data-ttu-id="04121-175">Para executar um `Get-PSSessionConfiguration` comando em um computador remoto, a autenticação de CredSSP (provedor de serviços de segurança de credencial) deve ser habilitada nas configurações do cliente no computador local (usando o `Enable-WSManCredSSP` cmdlet) e nas configurações de serviço no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="04121-175">To run a `Get-PSSessionConfiguration` command on a remote computer, Credential Security Service Provider (CredSSP) authentication must be enabled in the client settings on the local computer (by using the `Enable-WSManCredSSP` cmdlet) and in the service settings on the remote computer.</span></span> <span data-ttu-id="04121-176">Além disso, você deve usar o valor **CredSSP** do parâmetro de **autenticação** ao estabelecer a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="04121-176">Also, you must use the **CredSSP** value of the **Authentication** parameter when establishing the remote session.</span></span> <span data-ttu-id="04121-177">Caso contrário, o acesso é negado.</span><span class="sxs-lookup"><span data-stu-id="04121-177">Otherwise, access is denied.</span></span>

- <span data-ttu-id="04121-178">As propriedades de observação do objeto que `Get-PSSessionConfiguration` retorna aparecem no objeto somente quando eles têm um valor.</span><span class="sxs-lookup"><span data-stu-id="04121-178">The note properties of the object that `Get-PSSessionConfiguration` returns appear on the object only when they have a value.</span></span> <span data-ttu-id="04121-179">Somente as configurações de sessão que foram criadas usando um arquivo de configuração de sessão têm todas as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="04121-179">Only session configurations that were created by using a session configuration file have all the defined properties.</span></span>

- <span data-ttu-id="04121-180">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="04121-180">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="04121-181">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="04121-181">Also, session configurations that use a session configuration file have additional properties.</span></span>

- <span data-ttu-id="04121-182">É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="04121-182">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
  <span data-ttu-id="04121-183">No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode** .</span><span class="sxs-lookup"><span data-stu-id="04121-183">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="04121-184">Os comandos do PowerShell 2,0 não geram um erro, mas eles são ineficazes.</span><span class="sxs-lookup"><span data-stu-id="04121-184">PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="04121-185">Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="04121-185">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="04121-186">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="04121-186">RELATED LINKS</span></span>

[<span data-ttu-id="04121-187">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-187">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="04121-188">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-188">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="04121-189">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-189">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="04121-190">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="04121-190">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="04121-191">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="04121-191">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="04121-192">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-192">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="04121-193">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-193">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="04121-194">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="04121-194">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="04121-195">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="04121-195">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="04121-196">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="04121-196">WSMan Provider</span></span>](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[<span data-ttu-id="04121-197">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="04121-197">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="04121-198">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="04121-198">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)

