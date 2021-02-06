---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: a41c52bf163aa0a73b54e75b5192389a14da82bb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596990"
---
# <span data-ttu-id="dbdad-102">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="dbdad-102">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="dbdad-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dbdad-103">SYNOPSIS</span></span>
<span data-ttu-id="dbdad-104">Cria um arquivo que define uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-104">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="dbdad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbdad-105">SYNTAX</span></span>

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## <span data-ttu-id="dbdad-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dbdad-106">DESCRIPTION</span></span>

<span data-ttu-id="dbdad-107">O `New-PSSessionConfigurationFile` cmdlet cria um arquivo de configurações que definem uma configuração de sessão e o ambiente de sessões que são criadas usando a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-107">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="dbdad-108">Para usar o arquivo em uma configuração de sessão, use o parâmetro **path** dos `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="dbdad-108">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="dbdad-109">O arquivo de configuração de sessão que o `New-PSSessionConfigurationFile` cria é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-109">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="dbdad-110">O arquivo tem uma `.pssc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-110">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="dbdad-111">Todos os parâmetros de `New-PSSessionConfigurationFile` são opcionais, exceto o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-111">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="dbdad-112">Se um parâmetro for omitido, a chave correspondente no arquivo de configuração de sessão é comentada, exceto onde observado na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dbdad-112">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="dbdad-113">Uma configuração de sessão, também conhecida como um ponto de extremidade, é uma coleção de configurações no computador local que definem o ambiente para sessões do PowerShell (**PSSessions**) que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="dbdad-113">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions (**PSSessions**) that connect to the computer.</span></span> <span data-ttu-id="dbdad-114">Todas as **PSSessions** usam uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-114">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="dbdad-115">Para especificar uma configuração de sessão específica, use o parâmetro **ConfigurationName** de cmdlets que criam uma sessão, como o `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-115">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="dbdad-116">Um session configuration file torna mais fácil definir uma configuração de sessão sem scripts complexos ou assemblies de código.</span><span class="sxs-lookup"><span data-stu-id="dbdad-116">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="dbdad-117">As configurações no arquivo são usadas com o script de inicialização opcional e quaisquer assemblies na configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-117">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="dbdad-118">Para obter mais informações sobre configurações de sessão e arquivos de configuração de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md) e [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="dbdad-118">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="dbdad-119">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="dbdad-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="dbdad-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dbdad-120">EXAMPLES</span></span>

### <span data-ttu-id="dbdad-121">Exemplo 1: Criando e usando uma sessão nolanguage</span><span class="sxs-lookup"><span data-stu-id="dbdad-121">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="dbdad-122">Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.</span><span class="sxs-lookup"><span data-stu-id="dbdad-122">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="dbdad-123">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="dbdad-123">The steps include:</span></span>

1. <span data-ttu-id="dbdad-124">Crie um novo arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-124">Create a new configuration file.</span></span>
1. <span data-ttu-id="dbdad-125">Registre a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-125">Register the configuration.</span></span>
1. <span data-ttu-id="dbdad-126">Crie uma nova sessão que usa a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-126">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="dbdad-127">Execute comandos nessa nova sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-127">Run commands in that new session.</span></span>

<span data-ttu-id="dbdad-128">Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="dbdad-128">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="dbdad-129">Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-129">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

<span data-ttu-id="dbdad-130">Neste exemplo, a `Invoke-Command` falha porque **languagemode** está definido como **nolanguage**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-130">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage**.</span></span>

### <span data-ttu-id="dbdad-131">Exemplo 2: Criando e usando uma sessão RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="dbdad-131">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="dbdad-132">Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.</span><span class="sxs-lookup"><span data-stu-id="dbdad-132">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="dbdad-133">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="dbdad-133">The steps include:</span></span>

1. <span data-ttu-id="dbdad-134">Crie um novo arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-134">Create a new configuration file.</span></span>
1. <span data-ttu-id="dbdad-135">Registre a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-135">Register the configuration.</span></span>
1. <span data-ttu-id="dbdad-136">Crie uma nova sessão que usa a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-136">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="dbdad-137">Execute comandos nessa nova sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-137">Run commands in that new session.</span></span>

<span data-ttu-id="dbdad-138">Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="dbdad-138">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="dbdad-139">Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-139">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

<span data-ttu-id="dbdad-140">Neste exemplo, o é com `Invoke-Command` sucesso porque o **languagemode** está definido como **RestrictedLanguage**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-140">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage**.</span></span>

### <span data-ttu-id="dbdad-141">Exemplo 3: alterando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="dbdad-141">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="dbdad-142">Este exemplo mostra como alterar o arquivo de configuração de sessão que é usado em uma sessão existente chamada "ITTasks".</span><span class="sxs-lookup"><span data-stu-id="dbdad-142">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="dbdad-143">Anteriormente, essas sessões tinham apenas os módulos principais e um módulo **ITTasks** interno.</span><span class="sxs-lookup"><span data-stu-id="dbdad-143">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="dbdad-144">O administrador deseja adicionar o módulo **PSScheduledJob** às sessões criadas usando a configuração de sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="dbdad-144">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="dbdad-145">O `New-PSSessionConfigurationFile` cmdlet para criar um arquivo de configuração de sessão que importa os módulos necessários.</span><span class="sxs-lookup"><span data-stu-id="dbdad-145">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="dbdad-146">O `Set-PSSessionConfiguration` cmdlet substitui o arquivo de configuração atual pelo novo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-146">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="dbdad-147">Essa nova configuração afeta apenas as novas sessões criadas após a alteração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-147">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="dbdad-148">As sessões "ITTasks" existentes não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="dbdad-148">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="dbdad-149">Exemplo 4: editando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="dbdad-149">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="dbdad-150">Este exemplo mostra como alterar uma configuração de sessão editando a cópia da configuração de sessão ativa do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-150">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="dbdad-151">Para modificar a cópia de configuração de sessão do arquivo de configuração, você deve ter acesso de controle total ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-151">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="dbdad-152">Isso pode exigir que você altere as permissões no arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-152">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="dbdad-153">Nesse cenário, queremos adicionar um novo alias para o `Select-String` cmdlet editando o arquivo de configuração ativa.</span><span class="sxs-lookup"><span data-stu-id="dbdad-153">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="dbdad-154">O código de exemplo a seguir executa as seguintes etapas para fazer essa alteração:</span><span class="sxs-lookup"><span data-stu-id="dbdad-154">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="dbdad-155">Obtenha o caminho do arquivo de configuração para a sessão ITConfig.</span><span class="sxs-lookup"><span data-stu-id="dbdad-155">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="dbdad-156">O usuário edita o arquivo de configuração usando **Notepad.exe** para alterar o valor de **AliasDefinitions** da seguinte maneira: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .</span><span class="sxs-lookup"><span data-stu-id="dbdad-156">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="dbdad-157">Teste o arquivo de configuração atualizado.</span><span class="sxs-lookup"><span data-stu-id="dbdad-157">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="dbdad-158">Use o parâmetro **Verbose** com `Test-PSSessionConfigurationFile` para exibir todos os erros detectados.</span><span class="sxs-lookup"><span data-stu-id="dbdad-158">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="dbdad-159">O cmdlet retorna `$True` se nenhum erro for detectado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-159">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="dbdad-160">Exemplo 5: criar um arquivo de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="dbdad-160">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="dbdad-161">Este exemplo mostra um `New-PSSessionConfigurationFile` comando que usa todos os parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-161">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="dbdad-162">Ele é fornecido para mostrar o formato correto de entrada para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dbdad-162">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="dbdad-163">O SampleFile.pssc resultante é exibido na saída.</span><span class="sxs-lookup"><span data-stu-id="dbdad-163">The resulting SampleFile.pssc is displayed in the output.</span></span>

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## <span data-ttu-id="dbdad-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbdad-164">PARAMETERS</span></span>

### <span data-ttu-id="dbdad-165">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="dbdad-165">-AliasDefinitions</span></span>

<span data-ttu-id="dbdad-166">Adiciona os aliases especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-166">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-167">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="dbdad-167">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="dbdad-168">Nome-nome do alias.</span><span class="sxs-lookup"><span data-stu-id="dbdad-168">Name - Name of the alias.</span></span> <span data-ttu-id="dbdad-169">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-169">This key is required.</span></span>
- <span data-ttu-id="dbdad-170">Value-o comando que o alias representa.</span><span class="sxs-lookup"><span data-stu-id="dbdad-170">Value - The command that the alias represents.</span></span> <span data-ttu-id="dbdad-171">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-171">This key is required.</span></span>
- <span data-ttu-id="dbdad-172">Descrição-uma cadeia de texto que descreve o alias.</span><span class="sxs-lookup"><span data-stu-id="dbdad-172">Description - A text string that describes the alias.</span></span> <span data-ttu-id="dbdad-173">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="dbdad-173">This key is optional.</span></span>
- <span data-ttu-id="dbdad-174">Opções-opções de alias.</span><span class="sxs-lookup"><span data-stu-id="dbdad-174">Options - Alias options.</span></span> <span data-ttu-id="dbdad-175">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="dbdad-175">This key is optional.</span></span> <span data-ttu-id="dbdad-176">O valor padrão é **None**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-176">The default value is **None**.</span></span> <span data-ttu-id="dbdad-177">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="dbdad-177">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="dbdad-178">Por exemplo: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="dbdad-178">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-179">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="dbdad-179">-AssembliesToLoad</span></span>

<span data-ttu-id="dbdad-180">Especifica os assemblies para carregar nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-180">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-181">-Autor</span><span class="sxs-lookup"><span data-stu-id="dbdad-181">-Author</span></span>

<span data-ttu-id="dbdad-182">Especifica o autor da configuração de sessão ou o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-182">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="dbdad-183">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="dbdad-183">The default is the current user.</span></span> <span data-ttu-id="dbdad-184">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-184">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="dbdad-185">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="dbdad-185">-CompanyName</span></span>

<span data-ttu-id="dbdad-186">Especifica a empresa que criou a configuração de sessão ou o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbdad-186">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="dbdad-187">O valor padrão é **Desconhecido**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-187">The default value is **Unknown**.</span></span> <span data-ttu-id="dbdad-188">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-188">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-189">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="dbdad-189">-Copyright</span></span>

<span data-ttu-id="dbdad-190">Especifica um direito autoral do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-190">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="dbdad-191">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-191">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="dbdad-192">Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-192">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="dbdad-193">-Description</span><span class="sxs-lookup"><span data-stu-id="dbdad-193">-Description</span></span>

<span data-ttu-id="dbdad-194">Especifica uma descrição da configuração de sessão ou do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-194">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="dbdad-195">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-195">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="dbdad-196">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="dbdad-196">-EnvironmentVariables</span></span>

<span data-ttu-id="dbdad-197">Adiciona variáveis de ambiente à sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-197">Adds environment variables to the session.</span></span> <span data-ttu-id="dbdad-198">Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="dbdad-198">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="dbdad-199">Por exemplo: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="dbdad-199">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-200">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="dbdad-200">-ExecutionPolicy</span></span>

<span data-ttu-id="dbdad-201">Especifica a política de execução de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-201">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-202">Se você omitir esse parâmetro, o valor da chave **ExecutionPolicy** no arquivo de configuração de sessão será **restrito**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-202">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted**.</span></span> <span data-ttu-id="dbdad-203">Para obter informações sobre as políticas de execução no PowerShell, consulte [about_Execution_Policies](about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbdad-203">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-204">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="dbdad-204">-FormatsToProcess</span></span>

<span data-ttu-id="dbdad-205">Especifica os arquivos de formatação (.ps1xml) executados em sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-205">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="dbdad-206">O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="dbdad-206">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-207">-Full</span><span class="sxs-lookup"><span data-stu-id="dbdad-207">-Full</span></span>

<span data-ttu-id="dbdad-208">Indica que essa operação inclui todas as propriedades de configuração possíveis no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-208">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="dbdad-209">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="dbdad-209">-FunctionDefinitions</span></span>

<span data-ttu-id="dbdad-210">Adiciona as funções especificadas às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-210">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-211">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="dbdad-211">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="dbdad-212">Nome-nome da função.</span><span class="sxs-lookup"><span data-stu-id="dbdad-212">Name - Name of the function.</span></span> <span data-ttu-id="dbdad-213">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-213">This key is required.</span></span>
- <span data-ttu-id="dbdad-214">ScriptBlock-corpo da função.</span><span class="sxs-lookup"><span data-stu-id="dbdad-214">ScriptBlock - Function body.</span></span> <span data-ttu-id="dbdad-215">Insira um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="dbdad-215">Enter a script block.</span></span> <span data-ttu-id="dbdad-216">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-216">This key is required.</span></span>
- <span data-ttu-id="dbdad-217">Opções-opções de função.</span><span class="sxs-lookup"><span data-stu-id="dbdad-217">Options - Function options.</span></span> <span data-ttu-id="dbdad-218">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="dbdad-218">This key is optional.</span></span> <span data-ttu-id="dbdad-219">O valor padrão é **None**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-219">The default value is **None**.</span></span> <span data-ttu-id="dbdad-220">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="dbdad-220">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="dbdad-221">Por exemplo: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="dbdad-221">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-222">-GroupManagedServiceAccount</span><span class="sxs-lookup"><span data-stu-id="dbdad-222">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="dbdad-223">Configura sessões usando essa configuração de sessão para execução no contexto da conta de serviço gerenciado de grupo especificada.</span><span class="sxs-lookup"><span data-stu-id="dbdad-223">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="dbdad-224">O computador em que essa configuração de sessão está registrada deve ter permissão para solicitar a senha gMSA para que as sessões sejam criadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="dbdad-224">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="dbdad-225">Este campo não pode ser usado com o parâmetro **RunAsVirtualAccount** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-225">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="dbdad-226">-GUID</span><span class="sxs-lookup"><span data-stu-id="dbdad-226">-Guid</span></span>

<span data-ttu-id="dbdad-227">Especifica um identificador exclusivo para o arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-227">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="dbdad-228">Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará um GUID para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-228">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="dbdad-229">Para criar um novo GUID no PowerShell, digite `New-Guid` .</span><span class="sxs-lookup"><span data-stu-id="dbdad-229">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-230">-Languagemode</span><span class="sxs-lookup"><span data-stu-id="dbdad-230">-LanguageMode</span></span>

<span data-ttu-id="dbdad-231">Determina quais elementos da linguagem do PowerShell são permitidos em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-231">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="dbdad-232">Você pode usar esse parâmetro para restringir os comandos que usuários específicos podem executar no computador.</span><span class="sxs-lookup"><span data-stu-id="dbdad-232">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="dbdad-233">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="dbdad-233">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dbdad-234">FullLanguage-todos os elementos de linguagem são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dbdad-234">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="dbdad-235">ConstrainedLanguage-os comandos que contêm scripts a serem avaliados não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dbdad-235">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="dbdad-236">O modo ConstrainedLanguage restringe o acesso do usuário a tipos, objetos ou métodos do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbdad-236">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="dbdad-237">Nolanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar nenhum elemento de linguagem, como blocos de script, variáveis ou operadores.</span><span class="sxs-lookup"><span data-stu-id="dbdad-237">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="dbdad-238">RestrictedLanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar os blocos de script ou variáveis, exceto as seguintes variáveis permitidas:,,, `$PSCulture` `$PSUICulture` `$True` `$False` e `$Null` .</span><span class="sxs-lookup"><span data-stu-id="dbdad-238">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="dbdad-239">Os usuários podem usar apenas os operadores de comparação básicos ( `-eq` , `-gt` , `-lt` ).</span><span class="sxs-lookup"><span data-stu-id="dbdad-239">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="dbdad-240">Não são permitidas instruções de atribuição, referências de propriedade e chamadas de método.</span><span class="sxs-lookup"><span data-stu-id="dbdad-240">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="dbdad-241">O valor padrão do parâmetro **LanguageMode** depende do valor do parâmetro **SessionType**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-241">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="dbdad-242">Vazio – não idioma</span><span class="sxs-lookup"><span data-stu-id="dbdad-242">Empty - NoLanguage</span></span>
- <span data-ttu-id="dbdad-243">RestrictedRemoteServer-nolanguage</span><span class="sxs-lookup"><span data-stu-id="dbdad-243">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="dbdad-244">Padrão-FullLanguage</span><span class="sxs-lookup"><span data-stu-id="dbdad-244">Default - FullLanguage</span></span>

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-245">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="dbdad-245">-ModulesToImport</span></span>

<span data-ttu-id="dbdad-246">Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-246">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="dbdad-247">Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões remotas, mas a menos que os cmdlets sejam excluídos, os usuários podem usar os `Import-Module` `Add-PSSnapin` cmdlets e para adicionar módulos e snap-ins à sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-247">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="dbdad-248">Cada módulo ou o snap-in no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="dbdad-248">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="dbdad-249">Uma cadeia de caracteres de módulo consiste apenas no nome do módulo ou snap-in.</span><span class="sxs-lookup"><span data-stu-id="dbdad-249">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="dbdad-250">Uma tabela de hash de módulo pode incluir as chaves **ModuleName**, **ModuleVersion** e **GUID** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-250">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="dbdad-251">Somente a chave **ModuleName** é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-251">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="dbdad-252">Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="dbdad-252">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="dbdad-253">Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.</span><span class="sxs-lookup"><span data-stu-id="dbdad-253">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="dbdad-254">O valor do parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **ModulesToImport** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-254">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-255">-MountUserDrive</span><span class="sxs-lookup"><span data-stu-id="dbdad-255">-MountUserDrive</span></span>

<span data-ttu-id="dbdad-256">Configura as sessões que usam essa configuração de sessão para expor a `User:` PSDrive.</span><span class="sxs-lookup"><span data-stu-id="dbdad-256">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="dbdad-257">As unidades de usuário são exclusivas para cada usuário conectado e permitem que os usuários copiem dados de e para pontos de extremidade do PowerShell, mesmo que o provedor do sistema de arquivos não esteja exposto.</span><span class="sxs-lookup"><span data-stu-id="dbdad-257">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="dbdad-258">As raízes da unidade do usuário são criadas em `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` .</span><span class="sxs-lookup"><span data-stu-id="dbdad-258">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="dbdad-259">Para cada usuário que se conecta ao ponto de extremidade, uma pasta é criada com o nome `$env:USERDOMAIN_$env:USERNAME`.</span><span class="sxs-lookup"><span data-stu-id="dbdad-259">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="dbdad-260">O conteúdo na unidade de usuário persiste entre as sessões do usuário e não é removido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dbdad-260">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="dbdad-261">Por padrão, os usuários só podem armazenar até 50 MB de dados na unidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="dbdad-261">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="dbdad-262">Isso pode ser personalizado com o parâmetro **UserDriveMaximumSize** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-262">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="dbdad-263">-Path</span><span class="sxs-lookup"><span data-stu-id="dbdad-263">-Path</span></span>

<span data-ttu-id="dbdad-264">Especifica o caminho e o nome do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-264">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="dbdad-265">O arquivo deve ter uma `.pssc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-265">The file must have a `.pssc` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-266">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="dbdad-266">-PowerShellVersion</span></span>

<span data-ttu-id="dbdad-267">Especifica a versão do mecanismo do PowerShell em sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-267">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-268">Os valores aceitáveis para esse parâmetro são: 2,0 e 3,0.</span><span class="sxs-lookup"><span data-stu-id="dbdad-268">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="dbdad-269">Se você omitir esse parâmetro, a chave **PowerShellVersion** será comentada e a versão mais recente do PowerShell será executada na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-269">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="dbdad-270">O valor do parâmetro **psversion** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-270">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-271">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="dbdad-271">-RequiredGroups</span></span>

<span data-ttu-id="dbdad-272">Especifica regras de acesso condicional para usuários que se conectam a sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-272">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="dbdad-273">Insira uma tabela de hash para compor sua lista de regras usando apenas uma chave por Hashtable, ' and ' ou ' or ', e defina o valor como uma matriz de nomes de grupos de segurança ou Hashtables adicionais.</span><span class="sxs-lookup"><span data-stu-id="dbdad-273">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="dbdad-274">Exemplo que exige a conexão de usuários para serem membros de um único grupo: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="dbdad-274">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="dbdad-275">Exemplo que exigem que os usuários pertençam ao grupo A ou aos dois grupos B e C para acessar o ponto de extremidade: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="dbdad-275">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-276">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="dbdad-276">-RoleDefinitions</span></span>

<span data-ttu-id="dbdad-277">Especifica o mapeamento entre grupos de segurança (ou usuários) e recursos de função.</span><span class="sxs-lookup"><span data-stu-id="dbdad-277">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="dbdad-278">Os usuários receberão acesso a todos os recursos de função que se aplicam à sua associação de grupo no momento em que a sessão é criada.</span><span class="sxs-lookup"><span data-stu-id="dbdad-278">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="dbdad-279">Insira uma tabela de hash na qual as chaves são o nome do grupo de segurança e os valores são tabelas de hash que contêm uma lista de recursos de função que devem ser disponibilizados para o grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="dbdad-279">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="dbdad-280">Por exemplo: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="dbdad-280">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-281">-RunAsVirtualAccount</span><span class="sxs-lookup"><span data-stu-id="dbdad-281">-RunAsVirtualAccount</span></span>

<span data-ttu-id="dbdad-282">Configura sessões que usam essa configuração de sessão para serem executadas como a conta de administrador do computador (virtual).</span><span class="sxs-lookup"><span data-stu-id="dbdad-282">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="dbdad-283">Este campo não pode ser usado com o parâmetro **GroupManagedServiceAccount** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-283">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="dbdad-284">-RunAsVirtualAccountGroups</span><span class="sxs-lookup"><span data-stu-id="dbdad-284">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="dbdad-285">Especifica os grupos de segurança a serem associados à conta virtual quando uma sessão que usa a configuração de sessão é executada como uma conta virtual.</span><span class="sxs-lookup"><span data-stu-id="dbdad-285">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="dbdad-286">Se omitido, a conta virtual pertence a administradores de domínio em controladores de domínio e administradores em todos os outros computadores.</span><span class="sxs-lookup"><span data-stu-id="dbdad-286">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-287">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="dbdad-287">-SchemaVersion</span></span>

<span data-ttu-id="dbdad-288">Especifica a versão do esquema de arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-288">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="dbdad-289">O valor padrão é "1.0.0.0".</span><span class="sxs-lookup"><span data-stu-id="dbdad-289">The default value is "1.0.0.0".</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-290">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="dbdad-290">-ScriptsToProcess</span></span>

<span data-ttu-id="dbdad-291">Adiciona os scripts especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-291">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-292">Digite os nomes de arquivo e caminho dos scripts.</span><span class="sxs-lookup"><span data-stu-id="dbdad-292">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="dbdad-293">O valor desse parâmetro deve ser um caminho completo ou absoluto de nomes de arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="dbdad-293">The value of this parameter must be a full or absolute path of script file names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-294">-SessionType</span><span class="sxs-lookup"><span data-stu-id="dbdad-294">-SessionType</span></span>

<span data-ttu-id="dbdad-295">Especifica o tipo de sessão que é criada usando a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-295">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="dbdad-296">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="dbdad-296">The default value is Default.</span></span> <span data-ttu-id="dbdad-297">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="dbdad-297">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dbdad-298">Empty-nenhum módulo é adicionado à sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-298">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="dbdad-299">Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-299">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="dbdad-300">Essa opção foi projetada para que você crie sessões personalizadas adicionando comandos selecionados.</span><span class="sxs-lookup"><span data-stu-id="dbdad-300">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="dbdad-301">Se não adicionar comandos a uma sessão vazia, a sessão é limitada a expressões e não pode ser utilizada.</span><span class="sxs-lookup"><span data-stu-id="dbdad-301">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="dbdad-302">Padrão-adiciona o módulo Microsoft. PowerShell. Core à sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-302">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="dbdad-303">Esse módulo inclui o `Import-Module` cmdlet que os usuários podem usar para importar outros módulos, a menos que você proíba explicitamente esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-303">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="dbdad-304">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="dbdad-304">RestrictedRemoteServer.</span></span> <span data-ttu-id="dbdad-305">Inclui apenas as seguintes funções de proxy:,,,,, `Exit-PSSession` `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` e `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="dbdad-305">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="dbdad-306">Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-306">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-307">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="dbdad-307">-TranscriptDirectory</span></span>

<span data-ttu-id="dbdad-308">Especifica o diretório para posicionar transcrições de sessão para sessões usando essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-308">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="dbdad-309">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="dbdad-309">-TypesToProcess</span></span>

<span data-ttu-id="dbdad-310">Adiciona os `.ps1xml` arquivos de tipo especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-310">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-311">Insira os nomes de filetype.</span><span class="sxs-lookup"><span data-stu-id="dbdad-311">Enter the type filenames.</span></span> <span data-ttu-id="dbdad-312">O valor desse parâmetro deve ser um caminho completo ou absoluto para digitar os nomes de texto.</span><span class="sxs-lookup"><span data-stu-id="dbdad-312">The value of this parameter must be a full or absolute path to type filenames.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-313">-UserDriveMaximumSize</span><span class="sxs-lookup"><span data-stu-id="dbdad-313">-UserDriveMaximumSize</span></span>

<span data-ttu-id="dbdad-314">Especifica o tamanho máximo para unidades de usuário expostas em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-314">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="dbdad-315">Quando omitido, o tamanho padrão de cada `User:` unidade raiz é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="dbdad-315">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="dbdad-316">Esse parâmetro deve ser usado com **MountUserDrive**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-316">This parameter should be used with **MountUserDrive**.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-317">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="dbdad-317">-VariableDefinitions</span></span>

<span data-ttu-id="dbdad-318">Adiciona as variáveis especificadas às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-318">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="dbdad-319">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="dbdad-319">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="dbdad-320">Nome-nome da variável.</span><span class="sxs-lookup"><span data-stu-id="dbdad-320">Name - Name of the variable.</span></span> <span data-ttu-id="dbdad-321">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-321">This key is required.</span></span>
- <span data-ttu-id="dbdad-322">Valor-variável de valor.</span><span class="sxs-lookup"><span data-stu-id="dbdad-322">Value - Variable value.</span></span> <span data-ttu-id="dbdad-323">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="dbdad-323">This key is required.</span></span>
- <span data-ttu-id="dbdad-324">Opções – opções de variáveis.</span><span class="sxs-lookup"><span data-stu-id="dbdad-324">Options - Variable options.</span></span> <span data-ttu-id="dbdad-325">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="dbdad-325">This key is optional.</span></span> <span data-ttu-id="dbdad-326">O valor padrão é **None**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-326">The default value is **None**.</span></span> <span data-ttu-id="dbdad-327">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="dbdad-327">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="dbdad-328">Por exemplo: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="dbdad-328">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-329">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="dbdad-329">-VisibleAliases</span></span>

<span data-ttu-id="dbdad-330">Limita os aliases na sessão aos especificados no valor desse parâmetro, além de todos os aliases definidos no parâmetro **AliasDefinition**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-330">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="dbdad-331">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="dbdad-331">Wildcard characters are supported.</span></span> <span data-ttu-id="dbdad-332">Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-332">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="dbdad-333">Por exemplo: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="dbdad-333">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="dbdad-334">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-334">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dbdad-335">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="dbdad-335">-VisibleCmdlets</span></span>

<span data-ttu-id="dbdad-336">Limita os cmdlets na sessão para aquelas especificadas no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dbdad-336">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="dbdad-337">Há suporte para caracteres curinga e nomes qualificados de módulo.</span><span class="sxs-lookup"><span data-stu-id="dbdad-337">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="dbdad-338">Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-338">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="dbdad-339">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-339">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="dbdad-340">Se nenhum módulo no **ModulesToImport** expor o cmdlet, o módulo apropriado tentará ser carregado de forma autocarregada.</span><span class="sxs-lookup"><span data-stu-id="dbdad-340">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="dbdad-341">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-341">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbdad-342">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="dbdad-342">-VisibleExternalCommands</span></span>

<span data-ttu-id="dbdad-343">Limita os binários, scripts e comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dbdad-343">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="dbdad-344">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="dbdad-344">Wildcard characters are supported.</span></span>

<span data-ttu-id="dbdad-345">Por padrão, nenhum comando externo é visível na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-345">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="dbdad-346">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-346">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dbdad-347">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="dbdad-347">-VisibleFunctions</span></span>

<span data-ttu-id="dbdad-348">Limita as funções na sessão às especificadas no valor desse parâmetro, além de todas as funções que você define no parâmetro **FunctionDefinition**.</span><span class="sxs-lookup"><span data-stu-id="dbdad-348">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="dbdad-349">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="dbdad-349">Wildcard characters are supported.</span></span>

<span data-ttu-id="dbdad-350">Por padrão, todos as funções que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-350">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="dbdad-351">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-351">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="dbdad-352">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-352">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dbdad-353">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="dbdad-353">-VisibleProviders</span></span>

<span data-ttu-id="dbdad-354">Limita os provedores do PowerShell na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dbdad-354">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="dbdad-355">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="dbdad-355">Wildcard characters are supported.</span></span>

<span data-ttu-id="dbdad-356">Por padrão, todos os provedores que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-356">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="dbdad-357">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-357">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="dbdad-358">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-358">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dbdad-359">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dbdad-359">CommonParameters</span></span>

<span data-ttu-id="dbdad-360">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dbdad-360">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbdad-361">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dbdad-361">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbdad-362">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dbdad-362">INPUTS</span></span>

### <span data-ttu-id="dbdad-363">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dbdad-363">None</span></span>

<span data-ttu-id="dbdad-364">Não é possível canalizar nenhum objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdad-364">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="dbdad-365">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dbdad-365">OUTPUTS</span></span>

### <span data-ttu-id="dbdad-366">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dbdad-366">None</span></span>

<span data-ttu-id="dbdad-367">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="dbdad-367">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dbdad-368">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dbdad-368">NOTES</span></span>

<span data-ttu-id="dbdad-369">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="dbdad-369">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="dbdad-370">Os parâmetros, como **VisibleCmdlets** e **VisibleProviders**, não importam itens para a sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders**, do not import items into the session.</span></span> <span data-ttu-id="dbdad-371">Em vez disso, eles selecionam entre os itens importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="dbdad-372">Por exemplo, se o valor do parâmetro **VisibleProviders** for o provedor de certificado, mas o parâmetro **ModulesToImport** não especificar o módulo **Microsoft. PowerShell. Security** que contém o provedor de certificado, o provedor de certificado não estará visível na sessão.</span><span class="sxs-lookup"><span data-stu-id="dbdad-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="dbdad-373">`New-PSSessionConfigurationFile` Cria um arquivo de configuração de sessão que tem uma extensão de nome de arquivo. PSSC no caminho que você especificar no parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="dbdad-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="dbdad-374">Quando você usa o arquivo de configuração de sessão para criar uma configuração de sessão, o `Register-PSSessionConfiguration` cmdlet copia o arquivo de configuração e salva uma cópia ativa do arquivo no subdiretório **SessionConfig** do `$PSHOME` diretório.</span><span class="sxs-lookup"><span data-stu-id="dbdad-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="dbdad-375">A propriedade **ConfigFilePath** da configuração de sessão contém o caminho totalmente qualificado do arquivo de configuração de sessão ativa.</span><span class="sxs-lookup"><span data-stu-id="dbdad-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="dbdad-376">Você pode modificar o arquivo de configuração ativo no `$PSHOME` diretório a qualquer momento usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="dbdad-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="dbdad-377">As alterações feitas afetam todas as novas sessões que usam a configuração de sessão, mas sessões não existentes.</span><span class="sxs-lookup"><span data-stu-id="dbdad-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="dbdad-378">Antes de usar um arquivo de configuração de sessão editado, use o `Test-PSSessionConfigurationFile` cmdlet para verificar se as entradas do arquivo de configuração são válidas.</span><span class="sxs-lookup"><span data-stu-id="dbdad-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="dbdad-379">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dbdad-379">RELATED LINKS</span></span>

[<span data-ttu-id="dbdad-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-381">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="dbdad-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="dbdad-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbdad-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="dbdad-387">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="dbdad-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="dbdad-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="dbdad-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="dbdad-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="dbdad-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
