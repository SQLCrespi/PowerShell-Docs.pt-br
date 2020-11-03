---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: 4f326fcfb2c2af6816ae7cc58f12699e748f163a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192985"
---
# <span data-ttu-id="16f3b-103">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="16f3b-103">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="16f3b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="16f3b-104">SYNOPSIS</span></span>
<span data-ttu-id="16f3b-105">Cria um arquivo que define uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-105">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="16f3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="16f3b-106">SYNTAX</span></span>

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

## <span data-ttu-id="16f3b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="16f3b-107">DESCRIPTION</span></span>

<span data-ttu-id="16f3b-108">O `New-PSSessionConfigurationFile` cmdlet cria um arquivo de configurações que definem uma configuração de sessão e o ambiente de sessões que são criadas usando a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-108">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="16f3b-109">Para usar o arquivo em uma configuração de sessão, use o parâmetro **path** dos `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="16f3b-109">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="16f3b-110">O arquivo de configuração de sessão que o `New-PSSessionConfigurationFile` cria é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-110">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="16f3b-111">O arquivo tem uma `.pssc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-111">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="16f3b-112">Todos os parâmetros de `New-PSSessionConfigurationFile` são opcionais, exceto o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-112">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="16f3b-113">Se um parâmetro for omitido, a chave correspondente no arquivo de configuração de sessão é comentada, exceto onde observado na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f3b-113">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="16f3b-114">Uma configuração de sessão, também conhecida como um ponto de extremidade, é uma coleção de configurações no computador local que definem o ambiente para sessões do PowerShell ( **PSSessions** ) que se conectam ao computador.</span><span class="sxs-lookup"><span data-stu-id="16f3b-114">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions ( **PSSessions** ) that connect to the computer.</span></span> <span data-ttu-id="16f3b-115">Todas as **PSSessions** usam uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-115">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="16f3b-116">Para especificar uma configuração de sessão específica, use o parâmetro **ConfigurationName** de cmdlets que criam uma sessão, como o `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-116">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="16f3b-117">Um session configuration file torna mais fácil definir uma configuração de sessão sem scripts complexos ou assemblies de código.</span><span class="sxs-lookup"><span data-stu-id="16f3b-117">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="16f3b-118">As configurações no arquivo são usadas com o script de inicialização opcional e quaisquer assemblies na configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-118">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="16f3b-119">Para obter mais informações sobre configurações de sessão e arquivos de configuração de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md) e [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="16f3b-119">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="16f3b-120">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="16f3b-120">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="16f3b-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="16f3b-121">EXAMPLES</span></span>

### <span data-ttu-id="16f3b-122">Exemplo 1: Criando e usando uma sessão nolanguage</span><span class="sxs-lookup"><span data-stu-id="16f3b-122">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="16f3b-123">Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.</span><span class="sxs-lookup"><span data-stu-id="16f3b-123">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="16f3b-124">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="16f3b-124">The steps include:</span></span>

1. <span data-ttu-id="16f3b-125">Crie um novo arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-125">Create a new configuration file.</span></span>
1. <span data-ttu-id="16f3b-126">Registre a configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-126">Register the configuration.</span></span>
1. <span data-ttu-id="16f3b-127">Crie uma nova sessão que usa a configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-127">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="16f3b-128">Execute comandos nessa nova sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-128">Run commands in that new session.</span></span>

<span data-ttu-id="16f3b-129">Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="16f3b-129">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="16f3b-130">Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-130">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

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

<span data-ttu-id="16f3b-131">Neste exemplo, a `Invoke-Command` falha porque **languagemode** está definido como **nolanguage** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-131">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage** .</span></span>

### <span data-ttu-id="16f3b-132">Exemplo 2: Criando e usando uma sessão RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="16f3b-132">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="16f3b-133">Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.</span><span class="sxs-lookup"><span data-stu-id="16f3b-133">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="16f3b-134">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="16f3b-134">The steps include:</span></span>

1. <span data-ttu-id="16f3b-135">Crie um novo arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-135">Create a new configuration file.</span></span>
1. <span data-ttu-id="16f3b-136">Registre a configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-136">Register the configuration.</span></span>
1. <span data-ttu-id="16f3b-137">Crie uma nova sessão que usa a configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-137">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="16f3b-138">Execute comandos nessa nova sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-138">Run commands in that new session.</span></span>

<span data-ttu-id="16f3b-139">Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="16f3b-139">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="16f3b-140">Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-140">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

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

<span data-ttu-id="16f3b-141">Neste exemplo, o é com `Invoke-Command` sucesso porque o **languagemode** está definido como **RestrictedLanguage** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-141">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage** .</span></span>

### <span data-ttu-id="16f3b-142">Exemplo 3: alterando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="16f3b-142">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="16f3b-143">Este exemplo mostra como alterar o arquivo de configuração de sessão que é usado em uma sessão existente chamada "ITTasks".</span><span class="sxs-lookup"><span data-stu-id="16f3b-143">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="16f3b-144">Anteriormente, essas sessões tinham apenas os módulos principais e um módulo **ITTasks** interno.</span><span class="sxs-lookup"><span data-stu-id="16f3b-144">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="16f3b-145">O administrador deseja adicionar o módulo **PSScheduledJob** às sessões criadas usando a configuração de sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="16f3b-145">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="16f3b-146">O `New-PSSessionConfigurationFile` cmdlet para criar um arquivo de configuração de sessão que importa os módulos necessários.</span><span class="sxs-lookup"><span data-stu-id="16f3b-146">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="16f3b-147">O `Set-PSSessionConfiguration` cmdlet substitui o arquivo de configuração atual pelo novo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-147">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="16f3b-148">Essa nova configuração afeta apenas as novas sessões criadas após a alteração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-148">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="16f3b-149">As sessões "ITTasks" existentes não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="16f3b-149">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="16f3b-150">Exemplo 4: editando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="16f3b-150">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="16f3b-151">Este exemplo mostra como alterar uma configuração de sessão editando a cópia da configuração de sessão ativa do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-151">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="16f3b-152">Para modificar a cópia de configuração de sessão do arquivo de configuração, você deve ter acesso de controle total ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-152">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="16f3b-153">Isso pode exigir que você altere as permissões no arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-153">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="16f3b-154">Nesse cenário, queremos adicionar um novo alias para o `Select-String` cmdlet editando o arquivo de configuração ativa.</span><span class="sxs-lookup"><span data-stu-id="16f3b-154">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="16f3b-155">O código de exemplo a seguir executa as seguintes etapas para fazer essa alteração:</span><span class="sxs-lookup"><span data-stu-id="16f3b-155">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="16f3b-156">Obtenha o caminho do arquivo de configuração para a sessão ITConfig.</span><span class="sxs-lookup"><span data-stu-id="16f3b-156">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="16f3b-157">O usuário edita o arquivo de configuração usando **Notepad.exe** para alterar o valor de **AliasDefinitions** da seguinte maneira: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .</span><span class="sxs-lookup"><span data-stu-id="16f3b-157">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="16f3b-158">Teste o arquivo de configuração atualizado.</span><span class="sxs-lookup"><span data-stu-id="16f3b-158">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="16f3b-159">Use o parâmetro **Verbose** com `Test-PSSessionConfigurationFile` para exibir todos os erros detectados.</span><span class="sxs-lookup"><span data-stu-id="16f3b-159">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="16f3b-160">O cmdlet retorna `$True` se nenhum erro for detectado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-160">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="16f3b-161">Exemplo 5: criar um arquivo de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="16f3b-161">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="16f3b-162">Este exemplo mostra um `New-PSSessionConfigurationFile` comando que usa todos os parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-162">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="16f3b-163">Ele é fornecido para mostrar o formato correto de entrada para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f3b-163">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="16f3b-164">O SampleFile.pssc resultante é exibido na saída.</span><span class="sxs-lookup"><span data-stu-id="16f3b-164">The resulting SampleFile.pssc is displayed in the output.</span></span>

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

## <span data-ttu-id="16f3b-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="16f3b-165">PARAMETERS</span></span>

### <span data-ttu-id="16f3b-166">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="16f3b-166">-AliasDefinitions</span></span>

<span data-ttu-id="16f3b-167">Adiciona os aliases especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-167">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-168">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="16f3b-168">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="16f3b-169">Nome-nome do alias.</span><span class="sxs-lookup"><span data-stu-id="16f3b-169">Name - Name of the alias.</span></span> <span data-ttu-id="16f3b-170">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-170">This key is required.</span></span>
- <span data-ttu-id="16f3b-171">Value-o comando que o alias representa.</span><span class="sxs-lookup"><span data-stu-id="16f3b-171">Value - The command that the alias represents.</span></span> <span data-ttu-id="16f3b-172">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-172">This key is required.</span></span>
- <span data-ttu-id="16f3b-173">Descrição-uma cadeia de texto que descreve o alias.</span><span class="sxs-lookup"><span data-stu-id="16f3b-173">Description - A text string that describes the alias.</span></span> <span data-ttu-id="16f3b-174">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="16f3b-174">This key is optional.</span></span>
- <span data-ttu-id="16f3b-175">Opções-opções de alias.</span><span class="sxs-lookup"><span data-stu-id="16f3b-175">Options - Alias options.</span></span> <span data-ttu-id="16f3b-176">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="16f3b-176">This key is optional.</span></span> <span data-ttu-id="16f3b-177">O valor padrão é **None** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-177">The default value is **None** .</span></span> <span data-ttu-id="16f3b-178">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="16f3b-178">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="16f3b-179">Por exemplo: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="16f3b-179">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

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

### <span data-ttu-id="16f3b-180">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="16f3b-180">-AssembliesToLoad</span></span>

<span data-ttu-id="16f3b-181">Especifica os assemblies para carregar nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-181">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

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

### <span data-ttu-id="16f3b-182">-Autor</span><span class="sxs-lookup"><span data-stu-id="16f3b-182">-Author</span></span>

<span data-ttu-id="16f3b-183">Especifica o autor da configuração de sessão ou o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-183">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="16f3b-184">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="16f3b-184">The default is the current user.</span></span> <span data-ttu-id="16f3b-185">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-185">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="16f3b-186">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="16f3b-186">-CompanyName</span></span>

<span data-ttu-id="16f3b-187">Especifica a empresa que criou a configuração de sessão ou o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16f3b-187">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="16f3b-188">O valor padrão é **Desconhecido** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-188">The default value is **Unknown** .</span></span> <span data-ttu-id="16f3b-189">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-189">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="16f3b-190">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="16f3b-190">-Copyright</span></span>

<span data-ttu-id="16f3b-191">Especifica um direito autoral do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-191">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="16f3b-192">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-192">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="16f3b-193">Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-193">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="16f3b-194">-Description</span><span class="sxs-lookup"><span data-stu-id="16f3b-194">-Description</span></span>

<span data-ttu-id="16f3b-195">Especifica uma descrição da configuração de sessão ou do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-195">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="16f3b-196">O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-196">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="16f3b-197">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="16f3b-197">-EnvironmentVariables</span></span>

<span data-ttu-id="16f3b-198">Adiciona variáveis de ambiente à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-198">Adds environment variables to the session.</span></span> <span data-ttu-id="16f3b-199">Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="16f3b-199">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="16f3b-200">Por exemplo: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="16f3b-200">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

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

### <span data-ttu-id="16f3b-201">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="16f3b-201">-ExecutionPolicy</span></span>

<span data-ttu-id="16f3b-202">Especifica a política de execução de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-202">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-203">Se você omitir esse parâmetro, o valor da chave **ExecutionPolicy** no arquivo de configuração de sessão será **restrito** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-203">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted** .</span></span> <span data-ttu-id="16f3b-204">Para obter informações sobre as políticas de execução no PowerShell, consulte [about_Execution_Policies](about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="16f3b-204">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

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

### <span data-ttu-id="16f3b-205">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="16f3b-205">-FormatsToProcess</span></span>

<span data-ttu-id="16f3b-206">Especifica os arquivos de formatação (.ps1xml) executados em sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-206">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="16f3b-207">O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="16f3b-207">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="16f3b-208">-Full</span><span class="sxs-lookup"><span data-stu-id="16f3b-208">-Full</span></span>

<span data-ttu-id="16f3b-209">Indica que essa operação inclui todas as propriedades de configuração possíveis no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-209">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="16f3b-210">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="16f3b-210">-FunctionDefinitions</span></span>

<span data-ttu-id="16f3b-211">Adiciona as funções especificadas às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-211">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-212">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="16f3b-212">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="16f3b-213">Nome-nome da função.</span><span class="sxs-lookup"><span data-stu-id="16f3b-213">Name - Name of the function.</span></span> <span data-ttu-id="16f3b-214">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-214">This key is required.</span></span>
- <span data-ttu-id="16f3b-215">ScriptBlock-corpo da função.</span><span class="sxs-lookup"><span data-stu-id="16f3b-215">ScriptBlock - Function body.</span></span> <span data-ttu-id="16f3b-216">Insira um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="16f3b-216">Enter a script block.</span></span> <span data-ttu-id="16f3b-217">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-217">This key is required.</span></span>
- <span data-ttu-id="16f3b-218">Opções-opções de função.</span><span class="sxs-lookup"><span data-stu-id="16f3b-218">Options - Function options.</span></span> <span data-ttu-id="16f3b-219">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="16f3b-219">This key is optional.</span></span> <span data-ttu-id="16f3b-220">O valor padrão é **None** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-220">The default value is **None** .</span></span> <span data-ttu-id="16f3b-221">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="16f3b-221">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="16f3b-222">Por exemplo: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="16f3b-222">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

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

### <span data-ttu-id="16f3b-223">-GroupManagedServiceAccount</span><span class="sxs-lookup"><span data-stu-id="16f3b-223">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="16f3b-224">Configura sessões usando essa configuração de sessão para execução no contexto da conta de serviço gerenciado de grupo especificada.</span><span class="sxs-lookup"><span data-stu-id="16f3b-224">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="16f3b-225">O computador em que essa configuração de sessão está registrada deve ter permissão para solicitar a senha gMSA para que as sessões sejam criadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="16f3b-225">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="16f3b-226">Este campo não pode ser usado com o parâmetro **RunAsVirtualAccount** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-226">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="16f3b-227">-GUID</span><span class="sxs-lookup"><span data-stu-id="16f3b-227">-Guid</span></span>

<span data-ttu-id="16f3b-228">Especifica um identificador exclusivo para o arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-228">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="16f3b-229">Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará um GUID para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-229">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="16f3b-230">Para criar um novo GUID no PowerShell, digite `New-Guid` .</span><span class="sxs-lookup"><span data-stu-id="16f3b-230">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

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

### <span data-ttu-id="16f3b-231">-Languagemode</span><span class="sxs-lookup"><span data-stu-id="16f3b-231">-LanguageMode</span></span>

<span data-ttu-id="16f3b-232">Determina quais elementos da linguagem do PowerShell são permitidos em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-232">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="16f3b-233">Você pode usar esse parâmetro para restringir os comandos que usuários específicos podem executar no computador.</span><span class="sxs-lookup"><span data-stu-id="16f3b-233">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="16f3b-234">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="16f3b-234">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="16f3b-235">FullLanguage-todos os elementos de linguagem são permitidos.</span><span class="sxs-lookup"><span data-stu-id="16f3b-235">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="16f3b-236">ConstrainedLanguage-os comandos que contêm scripts a serem avaliados não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="16f3b-236">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="16f3b-237">O modo ConstrainedLanguage restringe o acesso do usuário a tipos, objetos ou métodos do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16f3b-237">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="16f3b-238">Nolanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar nenhum elemento de linguagem, como blocos de script, variáveis ou operadores.</span><span class="sxs-lookup"><span data-stu-id="16f3b-238">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="16f3b-239">RestrictedLanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar os blocos de script ou variáveis, exceto as seguintes variáveis permitidas:,,, `$PSCulture` `$PSUICulture` `$True` `$False` e `$Null` .</span><span class="sxs-lookup"><span data-stu-id="16f3b-239">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="16f3b-240">Os usuários podem usar apenas os operadores de comparação básicos ( `-eq` , `-gt` , `-lt` ).</span><span class="sxs-lookup"><span data-stu-id="16f3b-240">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="16f3b-241">Não são permitidas instruções de atribuição, referências de propriedade e chamadas de método.</span><span class="sxs-lookup"><span data-stu-id="16f3b-241">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="16f3b-242">O valor padrão do parâmetro **LanguageMode** depende do valor do parâmetro **SessionType** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-242">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="16f3b-243">Vazio – não idioma</span><span class="sxs-lookup"><span data-stu-id="16f3b-243">Empty - NoLanguage</span></span>
- <span data-ttu-id="16f3b-244">RestrictedRemoteServer-nolanguage</span><span class="sxs-lookup"><span data-stu-id="16f3b-244">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="16f3b-245">Padrão-FullLanguage</span><span class="sxs-lookup"><span data-stu-id="16f3b-245">Default - FullLanguage</span></span>

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

### <span data-ttu-id="16f3b-246">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="16f3b-246">-ModulesToImport</span></span>

<span data-ttu-id="16f3b-247">Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-247">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="16f3b-248">Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões remotas, mas a menos que os cmdlets sejam excluídos, os usuários podem usar os `Import-Module` `Add-PSSnapin` cmdlets e para adicionar módulos e snap-ins à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-248">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="16f3b-249">Cada módulo ou o snap-in no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="16f3b-249">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="16f3b-250">Uma cadeia de caracteres de módulo consiste apenas no nome do módulo ou snap-in.</span><span class="sxs-lookup"><span data-stu-id="16f3b-250">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="16f3b-251">Uma tabela de hash de módulo pode incluir as chaves **ModuleName** , **ModuleVersion** e **GUID** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-251">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="16f3b-252">Somente a chave **ModuleName** é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-252">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="16f3b-253">Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="16f3b-253">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="16f3b-254">Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.</span><span class="sxs-lookup"><span data-stu-id="16f3b-254">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="16f3b-255">O valor do parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **ModulesToImport** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-255">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

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

### <span data-ttu-id="16f3b-256">-MountUserDrive</span><span class="sxs-lookup"><span data-stu-id="16f3b-256">-MountUserDrive</span></span>

<span data-ttu-id="16f3b-257">Configura as sessões que usam essa configuração de sessão para expor a `User:` PSDrive.</span><span class="sxs-lookup"><span data-stu-id="16f3b-257">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="16f3b-258">As unidades de usuário são exclusivas para cada usuário conectado e permitem que os usuários copiem dados de e para pontos de extremidade do PowerShell, mesmo que o provedor do sistema de arquivos não esteja exposto.</span><span class="sxs-lookup"><span data-stu-id="16f3b-258">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="16f3b-259">As raízes da unidade do usuário são criadas em `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` .</span><span class="sxs-lookup"><span data-stu-id="16f3b-259">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="16f3b-260">Para cada usuário que se conecta ao ponto de extremidade, uma pasta é criada com o nome `$env:USERDOMAIN_$env:USERNAME`.</span><span class="sxs-lookup"><span data-stu-id="16f3b-260">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="16f3b-261">O conteúdo na unidade de usuário persiste entre as sessões do usuário e não é removido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="16f3b-261">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="16f3b-262">Por padrão, os usuários só podem armazenar até 50 MB de dados na unidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="16f3b-262">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="16f3b-263">Isso pode ser personalizado com o parâmetro **UserDriveMaximumSize** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-263">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="16f3b-264">-Path</span><span class="sxs-lookup"><span data-stu-id="16f3b-264">-Path</span></span>

<span data-ttu-id="16f3b-265">Especifica o caminho e o nome do arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-265">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="16f3b-266">O arquivo deve ter uma `.pssc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-266">The file must have a `.pssc` file name extension.</span></span>

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

### <span data-ttu-id="16f3b-267">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="16f3b-267">-PowerShellVersion</span></span>

<span data-ttu-id="16f3b-268">Especifica a versão do mecanismo do PowerShell em sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-268">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-269">Os valores aceitáveis para esse parâmetro são: 2,0 e 3,0.</span><span class="sxs-lookup"><span data-stu-id="16f3b-269">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="16f3b-270">Se você omitir esse parâmetro, a chave **PowerShellVersion** será comentada e a versão mais recente do PowerShell será executada na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-270">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="16f3b-271">O valor do parâmetro **psversion** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-271">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

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

### <span data-ttu-id="16f3b-272">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="16f3b-272">-RequiredGroups</span></span>

<span data-ttu-id="16f3b-273">Especifica regras de acesso condicional para usuários que se conectam a sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-273">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="16f3b-274">Insira uma tabela de hash para compor sua lista de regras usando apenas uma chave por Hashtable, ' and ' ou ' or ', e defina o valor como uma matriz de nomes de grupos de segurança ou Hashtables adicionais.</span><span class="sxs-lookup"><span data-stu-id="16f3b-274">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="16f3b-275">Exemplo que exige a conexão de usuários para serem membros de um único grupo: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="16f3b-275">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="16f3b-276">Exemplo que exigem que os usuários pertençam ao grupo A ou aos dois grupos B e C para acessar o ponto de extremidade: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="16f3b-276">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

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

### <span data-ttu-id="16f3b-277">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="16f3b-277">-RoleDefinitions</span></span>

<span data-ttu-id="16f3b-278">Especifica o mapeamento entre grupos de segurança (ou usuários) e recursos de função.</span><span class="sxs-lookup"><span data-stu-id="16f3b-278">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="16f3b-279">Os usuários receberão acesso a todos os recursos de função que se aplicam à sua associação de grupo no momento em que a sessão é criada.</span><span class="sxs-lookup"><span data-stu-id="16f3b-279">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="16f3b-280">Insira uma tabela de hash na qual as chaves são o nome do grupo de segurança e os valores são tabelas de hash que contêm uma lista de recursos de função que devem ser disponibilizados para o grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="16f3b-280">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="16f3b-281">Por exemplo: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="16f3b-281">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

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

### <span data-ttu-id="16f3b-282">-RunAsVirtualAccount</span><span class="sxs-lookup"><span data-stu-id="16f3b-282">-RunAsVirtualAccount</span></span>

<span data-ttu-id="16f3b-283">Configura sessões que usam essa configuração de sessão para serem executadas como a conta de administrador do computador (virtual).</span><span class="sxs-lookup"><span data-stu-id="16f3b-283">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="16f3b-284">Este campo não pode ser usado com o parâmetro **GroupManagedServiceAccount** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-284">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="16f3b-285">-RunAsVirtualAccountGroups</span><span class="sxs-lookup"><span data-stu-id="16f3b-285">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="16f3b-286">Especifica os grupos de segurança a serem associados à conta virtual quando uma sessão que usa a configuração de sessão é executada como uma conta virtual.</span><span class="sxs-lookup"><span data-stu-id="16f3b-286">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="16f3b-287">Se omitido, a conta virtual pertence a administradores de domínio em controladores de domínio e administradores em todos os outros computadores.</span><span class="sxs-lookup"><span data-stu-id="16f3b-287">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

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

### <span data-ttu-id="16f3b-288">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="16f3b-288">-SchemaVersion</span></span>

<span data-ttu-id="16f3b-289">Especifica a versão do esquema de arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-289">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="16f3b-290">O valor padrão é "1.0.0.0".</span><span class="sxs-lookup"><span data-stu-id="16f3b-290">The default value is "1.0.0.0".</span></span>

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

### <span data-ttu-id="16f3b-291">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="16f3b-291">-ScriptsToProcess</span></span>

<span data-ttu-id="16f3b-292">Adiciona os scripts especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-292">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-293">Digite os nomes de arquivo e caminho dos scripts.</span><span class="sxs-lookup"><span data-stu-id="16f3b-293">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="16f3b-294">O valor desse parâmetro deve ser um caminho completo ou absoluto de nomes de arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="16f3b-294">The value of this parameter must be a full or absolute path of script file names.</span></span>

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

### <span data-ttu-id="16f3b-295">-SessionType</span><span class="sxs-lookup"><span data-stu-id="16f3b-295">-SessionType</span></span>

<span data-ttu-id="16f3b-296">Especifica o tipo de sessão que é criada usando a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-296">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="16f3b-297">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="16f3b-297">The default value is Default.</span></span> <span data-ttu-id="16f3b-298">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="16f3b-298">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="16f3b-299">Empty-nenhum módulo é adicionado à sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-299">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="16f3b-300">Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-300">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="16f3b-301">Essa opção foi projetada para que você crie sessões personalizadas adicionando comandos selecionados.</span><span class="sxs-lookup"><span data-stu-id="16f3b-301">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="16f3b-302">Se não adicionar comandos a uma sessão vazia, a sessão é limitada a expressões e não pode ser utilizada.</span><span class="sxs-lookup"><span data-stu-id="16f3b-302">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="16f3b-303">Padrão-adiciona o módulo Microsoft. PowerShell. Core à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-303">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="16f3b-304">Esse módulo inclui o `Import-Module` cmdlet que os usuários podem usar para importar outros módulos, a menos que você proíba explicitamente esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-304">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="16f3b-305">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="16f3b-305">RestrictedRemoteServer.</span></span> <span data-ttu-id="16f3b-306">Inclui apenas as seguintes funções de proxy:,,,,, `Exit-PSSession` `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` e `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="16f3b-306">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="16f3b-307">Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-307">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

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

### <span data-ttu-id="16f3b-308">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="16f3b-308">-TranscriptDirectory</span></span>

<span data-ttu-id="16f3b-309">Especifica o diretório para posicionar transcrições de sessão para sessões usando essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-309">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="16f3b-310">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="16f3b-310">-TypesToProcess</span></span>

<span data-ttu-id="16f3b-311">Adiciona os `.ps1xml` arquivos de tipo especificados às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-311">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-312">Insira os nomes de filetype.</span><span class="sxs-lookup"><span data-stu-id="16f3b-312">Enter the type filenames.</span></span> <span data-ttu-id="16f3b-313">O valor desse parâmetro deve ser um caminho completo ou absoluto para digitar os nomes de texto.</span><span class="sxs-lookup"><span data-stu-id="16f3b-313">The value of this parameter must be a full or absolute path to type filenames.</span></span>

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

### <span data-ttu-id="16f3b-314">-UserDriveMaximumSize</span><span class="sxs-lookup"><span data-stu-id="16f3b-314">-UserDriveMaximumSize</span></span>

<span data-ttu-id="16f3b-315">Especifica o tamanho máximo para unidades de usuário expostas em sessões que usam essa configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-315">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="16f3b-316">Quando omitido, o tamanho padrão de cada `User:` unidade raiz é 50 MB.</span><span class="sxs-lookup"><span data-stu-id="16f3b-316">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="16f3b-317">Esse parâmetro deve ser usado com **MountUserDrive** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-317">This parameter should be used with **MountUserDrive** .</span></span>

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

### <span data-ttu-id="16f3b-318">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="16f3b-318">-VariableDefinitions</span></span>

<span data-ttu-id="16f3b-319">Adiciona as variáveis especificadas às sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-319">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="16f3b-320">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="16f3b-320">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="16f3b-321">Nome-nome da variável.</span><span class="sxs-lookup"><span data-stu-id="16f3b-321">Name - Name of the variable.</span></span> <span data-ttu-id="16f3b-322">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-322">This key is required.</span></span>
- <span data-ttu-id="16f3b-323">Valor-variável de valor.</span><span class="sxs-lookup"><span data-stu-id="16f3b-323">Value - Variable value.</span></span> <span data-ttu-id="16f3b-324">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="16f3b-324">This key is required.</span></span>
- <span data-ttu-id="16f3b-325">Opções – opções de variáveis.</span><span class="sxs-lookup"><span data-stu-id="16f3b-325">Options - Variable options.</span></span> <span data-ttu-id="16f3b-326">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="16f3b-326">This key is optional.</span></span> <span data-ttu-id="16f3b-327">O valor padrão é **None** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-327">The default value is **None** .</span></span> <span data-ttu-id="16f3b-328">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="16f3b-328">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="16f3b-329">Por exemplo: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="16f3b-329">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

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

### <span data-ttu-id="16f3b-330">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="16f3b-330">-VisibleAliases</span></span>

<span data-ttu-id="16f3b-331">Limita os aliases na sessão aos especificados no valor desse parâmetro, além de todos os aliases definidos no parâmetro **AliasDefinition** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-331">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="16f3b-332">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="16f3b-332">Wildcard characters are supported.</span></span> <span data-ttu-id="16f3b-333">Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-333">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="16f3b-334">Por exemplo: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="16f3b-334">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="16f3b-335">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-335">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="16f3b-336">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="16f3b-336">-VisibleCmdlets</span></span>

<span data-ttu-id="16f3b-337">Limita os cmdlets na sessão para aquelas especificadas no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f3b-337">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="16f3b-338">Há suporte para caracteres curinga e nomes qualificados de módulo.</span><span class="sxs-lookup"><span data-stu-id="16f3b-338">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="16f3b-339">Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-339">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="16f3b-340">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-340">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="16f3b-341">Se nenhum módulo no **ModulesToImport** expor o cmdlet, o módulo apropriado tentará ser carregado de forma autocarregada.</span><span class="sxs-lookup"><span data-stu-id="16f3b-341">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="16f3b-342">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-342">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="16f3b-343">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="16f3b-343">-VisibleExternalCommands</span></span>

<span data-ttu-id="16f3b-344">Limita os binários, scripts e comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f3b-344">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="16f3b-345">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="16f3b-345">Wildcard characters are supported.</span></span>

<span data-ttu-id="16f3b-346">Por padrão, nenhum comando externo é visível na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-346">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="16f3b-347">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-347">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="16f3b-348">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="16f3b-348">-VisibleFunctions</span></span>

<span data-ttu-id="16f3b-349">Limita as funções na sessão às especificadas no valor desse parâmetro, além de todas as funções que você define no parâmetro **FunctionDefinition** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-349">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="16f3b-350">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="16f3b-350">Wildcard characters are supported.</span></span>

<span data-ttu-id="16f3b-351">Por padrão, todos as funções que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-351">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="16f3b-352">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-352">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="16f3b-353">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-353">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="16f3b-354">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="16f3b-354">-VisibleProviders</span></span>

<span data-ttu-id="16f3b-355">Limita os provedores do PowerShell na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f3b-355">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="16f3b-356">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="16f3b-356">Wildcard characters are supported.</span></span>

<span data-ttu-id="16f3b-357">Por padrão, todos os provedores que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-357">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="16f3b-358">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-358">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="16f3b-359">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-359">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="16f3b-360">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="16f3b-360">CommonParameters</span></span>

<span data-ttu-id="16f3b-361">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="16f3b-361">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="16f3b-362">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="16f3b-362">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="16f3b-363">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="16f3b-363">INPUTS</span></span>

### <span data-ttu-id="16f3b-364">Nenhum</span><span class="sxs-lookup"><span data-stu-id="16f3b-364">None</span></span>

<span data-ttu-id="16f3b-365">Não é possível canalizar nenhum objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16f3b-365">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="16f3b-366">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="16f3b-366">OUTPUTS</span></span>

### <span data-ttu-id="16f3b-367">Nenhum</span><span class="sxs-lookup"><span data-stu-id="16f3b-367">None</span></span>

<span data-ttu-id="16f3b-368">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="16f3b-368">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="16f3b-369">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="16f3b-369">NOTES</span></span>

- <span data-ttu-id="16f3b-370">Os parâmetros, como **VisibleCmdlets** e **VisibleProviders** , não importam itens para a sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders** , do not import items into the session.</span></span> <span data-ttu-id="16f3b-371">Em vez disso, eles selecionam entre os itens importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="16f3b-372">Por exemplo, se o valor do parâmetro **VisibleProviders** for o provedor de certificado, mas o parâmetro **ModulesToImport** não especificar o módulo **Microsoft. PowerShell. Security** que contém o provedor de certificado, o provedor de certificado não estará visível na sessão.</span><span class="sxs-lookup"><span data-stu-id="16f3b-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="16f3b-373">`New-PSSessionConfigurationFile` Cria um arquivo de configuração de sessão que tem uma extensão de nome de arquivo. PSSC no caminho que você especificar no parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="16f3b-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="16f3b-374">Quando você usa o arquivo de configuração de sessão para criar uma configuração de sessão, o `Register-PSSessionConfiguration` cmdlet copia o arquivo de configuração e salva uma cópia ativa do arquivo no subdiretório **SessionConfig** do `$PSHOME` diretório.</span><span class="sxs-lookup"><span data-stu-id="16f3b-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="16f3b-375">A propriedade **ConfigFilePath** da configuração de sessão contém o caminho totalmente qualificado do arquivo de configuração de sessão ativa.</span><span class="sxs-lookup"><span data-stu-id="16f3b-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="16f3b-376">Você pode modificar o arquivo de configuração ativo no `$PSHOME` diretório a qualquer momento usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="16f3b-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="16f3b-377">As alterações feitas afetam todas as novas sessões que usam a configuração de sessão, mas sessões não existentes.</span><span class="sxs-lookup"><span data-stu-id="16f3b-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="16f3b-378">Antes de usar um arquivo de configuração de sessão editado, use o `Test-PSSessionConfigurationFile` cmdlet para verificar se as entradas do arquivo de configuração são válidas.</span><span class="sxs-lookup"><span data-stu-id="16f3b-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="16f3b-379">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="16f3b-379">RELATED LINKS</span></span>

[<span data-ttu-id="16f3b-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-381">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="16f3b-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="16f3b-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="16f3b-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="16f3b-387">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="16f3b-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="16f3b-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="16f3b-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="16f3b-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="16f3b-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
