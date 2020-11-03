---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-modulemanifest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ModuleManifest
ms.openlocfilehash: caf67f951beb054e9bedb46d010fe1a5d8db7ab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194703"
---
# <span data-ttu-id="5da9a-103">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="5da9a-103">New-ModuleManifest</span></span>

## <span data-ttu-id="5da9a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5da9a-104">SYNOPSIS</span></span>
<span data-ttu-id="5da9a-105">Cria um novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-105">Creates a new module manifest.</span></span>

## <span data-ttu-id="5da9a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5da9a-106">SYNTAX</span></span>

### <span data-ttu-id="5da9a-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="5da9a-107">All</span></span>

```
New-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-PowerShellVersion <Version>] [-CLRVersion <Version>] [-DotNetFrameworkVersion <Version>]
 [-PowerShellHostName <String>] [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>]
 [-RequiredAssemblies <String[]>] [-FileList <String[]>] [-ModuleList <Object[]>]
 [-FunctionsToExport <String[]>] [-AliasesToExport <String[]>] [-VariablesToExport <String[]>]
 [-CmdletsToExport <String[]>] [-DscResourcesToExport <String[]>] [-CompatiblePSEditions <String[]>]
 [-PrivateData <Object>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ReleaseNotes <String>] [-Prerelease <String>] [-RequireLicenseAcceptance]
 [-ExternalModuleDependencies <String[]>] [-HelpInfoUri <String>] [-PassThru]
 [-DefaultCommandPrefix <String>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="5da9a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5da9a-108">DESCRIPTION</span></span>

<span data-ttu-id="5da9a-109">O `New-ModuleManifest` cmdlet cria um novo arquivo de manifesto de módulo ( `.psd1` ), popula seus valores e salva o arquivo de manifesto no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-109">The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.</span></span>

<span data-ttu-id="5da9a-110">Autores de módulo podem usar este cmdlet para criar um manifesto para seu módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-110">Module authors can use this cmdlet to create a manifest for their module.</span></span> <span data-ttu-id="5da9a-111">Um manifesto de módulo é um `.psd1` arquivo que contém uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="5da9a-111">A module manifest is a `.psd1` file that contains a hash table.</span></span> <span data-ttu-id="5da9a-112">As chaves e os valores na tabela de hash descrevem o conteúdo e os atributos do módulo, definem os pré-requisitos e determinam como os componentes são processados.</span><span class="sxs-lookup"><span data-stu-id="5da9a-112">The keys and values in the hash table describe the contents and attributes of the module, define the prerequisites, and determine how the components are processed.</span></span> <span data-ttu-id="5da9a-113">Os manifestos não são necessários para um módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-113">Manifests aren't required for a module.</span></span>

<span data-ttu-id="5da9a-114">`New-ModuleManifest` Cria um manifesto que inclui todas as chaves de manifesto usadas com frequência, para que você possa usar a saída padrão como um modelo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-114">`New-ModuleManifest` creates a manifest that includes all the commonly used manifest keys, so you can use the default output as a manifest template.</span></span> <span data-ttu-id="5da9a-115">Para adicionar ou alterar valores, ou para adicionar chaves de módulo que esse cmdlet não adiciona, abra o arquivo resultante em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-115">To add or change values, or to add module keys that this cmdlet doesn't add, open the resulting file in a text editor.</span></span>

<span data-ttu-id="5da9a-116">Cada parâmetro, exceto **Path** e **PassThru** , cria uma chave de manifesto de módulo e seu valor.</span><span class="sxs-lookup"><span data-stu-id="5da9a-116">Each parameter, except for **Path** and **PassThru** , creates a module manifest key and its value.</span></span>
<span data-ttu-id="5da9a-117">Em um manifesto de módulo, somente a chave **ModuleVersion** é necessária.</span><span class="sxs-lookup"><span data-stu-id="5da9a-117">In a module manifest, only the **ModuleVersion** key is required.</span></span> <span data-ttu-id="5da9a-118">A menos que especificado na descrição do parâmetro, se você omitir um parâmetro do comando, `New-ModuleManifest` o criará uma cadeia de caracteres de comentário para o valor associado que não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="5da9a-118">Unless specified in the parameter description, if you omit a parameter from the command, `New-ModuleManifest` creates a comment string for the associated value that has no effect.</span></span>

<span data-ttu-id="5da9a-119">No PowerShell 2,0, `New-ModuleManifest` o solicita os valores de parâmetros comumente usados que não são especificados no comando, além dos valores de parâmetro necessários.</span><span class="sxs-lookup"><span data-stu-id="5da9a-119">In PowerShell 2.0, `New-ModuleManifest` prompts you for the values of commonly used parameters that aren't specified in the command, in addition to required parameter values.</span></span> <span data-ttu-id="5da9a-120">A partir do PowerShell 3,0, o `New-ModuleManifest` solicita somente quando os valores de parâmetro necessários não são especificados.</span><span class="sxs-lookup"><span data-stu-id="5da9a-120">Beginning in PowerShell 3.0, `New-ModuleManifest` prompts only when required parameter values aren't specified.</span></span>

<span data-ttu-id="5da9a-121">Se você estiver planejando publicar seu módulo no Galeria do PowerShell, o manifesto deverá conter valores para determinadas propriedades.</span><span class="sxs-lookup"><span data-stu-id="5da9a-121">If you are planning to publish your module in the PowerShell Gallery, the manifest must contain values for certain properties.</span></span> <span data-ttu-id="5da9a-122">Para obter mais informações, consulte [metadados necessários para itens publicados no Galeria do PowerShell](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) na documentação da galeria.</span><span class="sxs-lookup"><span data-stu-id="5da9a-122">For more information, see [Required metadata for items published to the PowerShell Gallery](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in the Gallery documentation.</span></span>

## <span data-ttu-id="5da9a-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5da9a-123">EXAMPLES</span></span>

### <span data-ttu-id="5da9a-124">Exemplo 1-criar um novo manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="5da9a-124">Example 1 - Create a new module manifest</span></span>

<span data-ttu-id="5da9a-125">Este exemplo cria um novo manifesto de módulo no arquivo que é especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-125">This example creates a new module manifest in the file that is specified by the **Path** parameter.</span></span>
<span data-ttu-id="5da9a-126">O parâmetro **PassThru** envia a saída para o pipeline e para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-126">The **PassThru** parameter sends the output to the pipeline and to the file.</span></span>

<span data-ttu-id="5da9a-127">A saída mostra os valores padrão de todas as chaves do manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-127">The output shows the default values of all keys in the manifest.</span></span>

```powershell
New-ModuleManifest -Path C:\ps-test\Test-Module\Test-Module.psd1 -PassThru
```

```Output
#
# Module manifest for module 'Test-Module'
#
# Generated by: ContosoAdmin
#
# Generated on: 7/12/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'e1826c6e-c420-4eef-9ac8-185e3669ca6a'

# Author of this module
Author = 'ContosoAdmin'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) ContosoAdmin. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

        # Prerelease string of this module
        # Prerelease = ''

        # Flag to indicate whether the module requires explicit user acceptance for install/update/save
        # RequireLicenseAcceptance = $false

        # External dependent modules of this module
        # ExternalModuleDependencies = @()

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

### <span data-ttu-id="5da9a-128">Exemplo 2-criar um novo manifesto com algumas configurações preenchidas previamente</span><span class="sxs-lookup"><span data-stu-id="5da9a-128">Example 2 - Create a new manifest with some prepopulated settings</span></span>

<span data-ttu-id="5da9a-129">Este exemplo cria um novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-129">This example creates a new module manifest.</span></span> <span data-ttu-id="5da9a-130">Ele usa os parâmetros **PowerShellVersion** e **AliasesToExport** para adicionar valores às chaves de manifesto correspondentes.</span><span class="sxs-lookup"><span data-stu-id="5da9a-130">It uses the **PowerShellVersion** and **AliasesToExport** parameters to add values to the corresponding manifest keys.</span></span>

```powershell
New-ModuleManifest -PowerShellVersion 1.0 -AliasesToExport JKBC, DRC, TAC -Path C:\ps-test\ManifestTest.psd1
```

### <span data-ttu-id="5da9a-131">Exemplo 3-criar um manifesto que requer outros módulos</span><span class="sxs-lookup"><span data-stu-id="5da9a-131">Example 3 - Create a manifest that requires other modules</span></span>

<span data-ttu-id="5da9a-132">Este exemplo usa um formato de cadeia de caracteres para especificar o nome do módulo **BitsTransfer** e o formato da tabela de hash para especificar o nome, um **GUID** e uma versão do módulo **PSScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-132">This example uses a string format to specify the name of the **BitsTransfer** module and the hash table format to specify the name, a **GUID** , and a version of the **PSScheduledJob** module.</span></span>

```powershell
$moduleSettings = @{
  RequiredModules = ("BitsTransfer", @{
    ModuleName="PSScheduledJob"
    ModuleVersion="1.0.0.0";
    GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"
  })
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="5da9a-133">Este exemplo mostra como usar a cadeia de caracteres e os formatos de tabela de hash do parâmetro **ModuleList** , **RequiredModules** e **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-133">This example shows how to use the string and hash table formats of the **ModuleList** , **RequiredModules** , and **NestedModules** parameter.</span></span> <span data-ttu-id="5da9a-134">Você pode combinar cadeias de caracteres e tabelas de hash no mesmo valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5da9a-134">You can combine strings and hash tables in the same parameter value.</span></span>

### <span data-ttu-id="5da9a-135">Exemplo 4-criar um manifesto que ofereça suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="5da9a-135">Example 4 - Create a manifest that supports updateable help</span></span>

<span data-ttu-id="5da9a-136">Este exemplo usa o parâmetro **HelpInfoUri** para criar uma chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-136">This example uses the **HelpInfoUri** parameter to create a **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="5da9a-137">O valor do parâmetro e a chave devem começar com **http** ou **https** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-137">The value of the parameter and the key must begin with **http** or **https** .</span></span> <span data-ttu-id="5da9a-138">Esse valor informa o sistema do Updatable Help onde encontrar o arquivo XML de informações de ajuda atualizável HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-138">This value tells the Updatable Help system where to find the HelpInfo XML updatable help information file for the module.</span></span>

```powershell
$moduleSettings = @{
  HelpInfoUri = 'http://https://go.microsoft.com/fwlink/?LinkID=603'
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="5da9a-139">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="5da9a-139">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="5da9a-140">Para obter informações sobre o arquivo XML HelpInfo, consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="5da9a-140">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

### <span data-ttu-id="5da9a-141">Exemplo 5-obtendo informações de módulo</span><span class="sxs-lookup"><span data-stu-id="5da9a-141">Example 5 - Getting module information</span></span>

<span data-ttu-id="5da9a-142">Este exemplo mostra como obter os valores de configuração de um módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-142">This example shows how to get the configuration values of a module.</span></span> <span data-ttu-id="5da9a-143">Os valores no manifesto do módulo são refletidos nos valores das propriedades do objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-143">The values in the module manifest are reflected in the values of properties of the module object.</span></span>

<span data-ttu-id="5da9a-144">O `Get-Module` cmdlet é usado para obter o módulo **Microsoft. PowerShell. Diagnostics** usando o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-144">The `Get-Module` cmdlet is used to get the **Microsoft.PowerShell.Diagnostics** module using the **List** parameter.</span></span> <span data-ttu-id="5da9a-145">O comando envia o módulo para o `Format-List` cmdlet para exibir todas as propriedades e valores do objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-145">The command sends the module to the `Format-List` cmdlet to display all properties and values of the module object.</span></span>

```powershell
Get-Module Microsoft.PowerShell.Diagnostics -List | Format-List -Property *
```

```Output
LogPipelineExecutionDetails : False
Name                        : Microsoft.PowerShell.Diagnostics
Path                        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics\Micro
                              soft.PowerShell.Diagnostics.psd1
Definition                  :
Description                 :
Guid                        : ca046f10-ca64-4740-8ff9-2565dba61a4f
HelpInfoUri                 : https://go.microsoft.com/fwlink/?LinkID=210596
ModuleBase                  : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics
PrivateData                 :
Version                     : 3.0.0.0
ModuleType                  : Manifest
Author                      : Microsoft Corporation
AccessMode                  : ReadWrite
ClrVersion                  : 4.0
CompanyName                 : Microsoft Corporation
Copyright                   : Microsoft Corporation. All rights reserved.
DotNetFrameworkVersion      :
ExportedFunctions           : {}
ExportedCmdlets             : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
ExportedCommands            : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
FileList                    : {}
ModuleList                  : {}
NestedModules               : {}
PowerShellHostName          :
PowerShellHostVersion       :
PowerShellVersion           : 3.0
ProcessorArchitecture       : None
Scripts                     : {}
RequiredAssemblies          : {}
RequiredModules             : {}
RootModule                  :
ExportedVariables           : {}
ExportedAliases             : {}
ExportedWorkflows           : {}
SessionState                :
OnRemove                    :
ExportedFormatFiles         : {C:\Windows\system32\WindowsPowerShell\v1.0\Event.format.ps1xml,
                              C:\Windows\system32\WindowsPowerShell\v1.0\Diagnostics.format.ps1xml}
ExportedTypeFiles           : {C:\Windows\system32\WindowsPowerShell\v1.0\GetEvent.types.ps1xml}
```

## <span data-ttu-id="5da9a-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5da9a-146">PARAMETERS</span></span>

### <span data-ttu-id="5da9a-147">-AliasesToExport</span><span class="sxs-lookup"><span data-stu-id="5da9a-147">-AliasesToExport</span></span>

<span data-ttu-id="5da9a-148">Especifica os aliases que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-148">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="5da9a-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-149">Wildcards are permitted.</span></span>

<span data-ttu-id="5da9a-150">Você pode usar esse parâmetro para restringir os aliases exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-150">You can use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="5da9a-151">Ele pode remover aliases da lista de aliases exportados, mas não pode adicionar aliases à lista.</span><span class="sxs-lookup"><span data-stu-id="5da9a-151">It can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

<span data-ttu-id="5da9a-152">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **AliasesToExport** com um valor de `*` (All), o que significa que todos os aliases definidos no módulo serão exportados pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-152">If you omit this parameter, `New-ModuleManifest` creates an **AliasesToExport** key with a value of `*` (all), meaning that all aliases defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5da9a-153">-Autor</span><span class="sxs-lookup"><span data-stu-id="5da9a-153">-Author</span></span>

<span data-ttu-id="5da9a-154">Especifica o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-154">Specifies the module author.</span></span>

<span data-ttu-id="5da9a-155">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave de **autor** com o nome do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="5da9a-155">If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Name of the current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-156">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="5da9a-156">-CmdletsToExport</span></span>

<span data-ttu-id="5da9a-157">Especifica os cmdlets que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-157">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="5da9a-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-158">Wildcards are permitted.</span></span>

<span data-ttu-id="5da9a-159">Você pode usar esse parâmetro para restringir os cmdlets exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-159">You can use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="5da9a-160">Ele pode remover cmdlets da lista de cmdlets exportados, mas não pode adicionar cmdlets à lista.</span><span class="sxs-lookup"><span data-stu-id="5da9a-160">It can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

<span data-ttu-id="5da9a-161">Se você omitir esse parâmetro, `New-ModuleManifest` o criará uma chave **CmdletsToExport** com um valor de `*` (All), o que significa que todos os cmdlets definidos no módulo serão exportados pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-161">If you omit this parameter, `New-ModuleManifest` creates a **CmdletsToExport** key with a value of `*` (all), meaning that all cmdlets defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5da9a-162">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="5da9a-162">-CompanyName</span></span>

<span data-ttu-id="5da9a-163">Identifica a empresa ou fornecedor que o módulo criou.</span><span class="sxs-lookup"><span data-stu-id="5da9a-163">Identifies the company or vendor who created the module.</span></span>

<span data-ttu-id="5da9a-164">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **CompanyName** com um valor de "Unknown".</span><span class="sxs-lookup"><span data-stu-id="5da9a-164">If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown".</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Unknown"
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-165">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="5da9a-165">-CompatiblePSEditions</span></span>

<span data-ttu-id="5da9a-166">Especifica o PSEditions compatível do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-166">Specifies the module's compatible PSEditions.</span></span> <span data-ttu-id="5da9a-167">Para obter informações sobre PSEdition, consulte [módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="5da9a-167">For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-168">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="5da9a-168">-Copyright</span></span>

<span data-ttu-id="5da9a-169">Especifica uma declaração de direitos autorais do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-169">Specifies a copyright statement for the module.</span></span>

<span data-ttu-id="5da9a-170">Se você omitir esse parâmetro, o `New-ModuleManifest` cria uma chave de **direitos autorais** com um valor de `(c) <year> <username>. All rights reserved.` onde `<year>` é o ano atual e `<username>` é o valor da chave de **autor** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-170">If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<year>` is the current year and `<username>` is the value of the **Author** key.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (c) <year> <username>. All rights reserved.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-171">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="5da9a-171">-DefaultCommandPrefix</span></span>

<span data-ttu-id="5da9a-172">Especifica um prefixo que é anexado aos substantivos de todos os comandos no módulo quando eles são importados para uma sessão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-172">Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session.</span></span> <span data-ttu-id="5da9a-173">Insira uma cadeia de caracteres de prefixo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-173">Enter a prefix string.</span></span> <span data-ttu-id="5da9a-174">Prefixos evitam conflitos de nomes de comando em uma sessão de usuário.</span><span class="sxs-lookup"><span data-stu-id="5da9a-174">Prefixes prevent command name conflicts in a user's session.</span></span>

<span data-ttu-id="5da9a-175">Os usuários do módulo podem substituir esse prefixo especificando o parâmetro de **prefixo** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5da9a-175">Module users can override this prefix by specifying the **Prefix** parameter of the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="5da9a-176">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5da9a-176">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5da9a-177">-Description</span><span class="sxs-lookup"><span data-stu-id="5da9a-177">-Description</span></span>

<span data-ttu-id="5da9a-178">Descreve o conteúdo do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-178">Describes the contents of the module.</span></span>

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

### <span data-ttu-id="5da9a-179">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="5da9a-179">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="5da9a-180">Especifica a versão mínima do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="5da9a-180">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="5da9a-181">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="5da9a-181">-DscResourcesToExport</span></span>

<span data-ttu-id="5da9a-182">Especifica os recursos de DSC (configuração de estado desejado) que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-182">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="5da9a-183">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-183">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="5da9a-184">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="5da9a-184">-ExternalModuleDependencies</span></span>

<span data-ttu-id="5da9a-185">Uma lista de módulos externos da qual este módulo depende.</span><span class="sxs-lookup"><span data-stu-id="5da9a-185">A list of external modules that this module is depends on.</span></span>

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

### <span data-ttu-id="5da9a-186">-FileList</span><span class="sxs-lookup"><span data-stu-id="5da9a-186">-FileList</span></span>

<span data-ttu-id="5da9a-187">Especifica todos os itens incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-187">Specifies all items that are included in the module.</span></span>

<span data-ttu-id="5da9a-188">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-188">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="5da9a-189">Os arquivos listados na chave são incluídos quando o módulo é publicado, mas todas as funções não são exportadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5da9a-189">The files listed in the key are included when the module is published, but any functions aren't automatically exported.</span></span>

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

### <span data-ttu-id="5da9a-190">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="5da9a-190">-FormatsToProcess</span></span>

<span data-ttu-id="5da9a-191">Especifica os arquivos de formatação ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-191">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="5da9a-192">Quando você importa um módulo, o PowerShell executa o `Update-FormatData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="5da9a-192">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="5da9a-193">Como os arquivos de formatação não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-193">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="5da9a-194">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="5da9a-194">-FunctionsToExport</span></span>

<span data-ttu-id="5da9a-195">Especifica as funções que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-195">Specifies the functions that the module exports.</span></span> <span data-ttu-id="5da9a-196">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-196">Wildcards are permitted.</span></span>

<span data-ttu-id="5da9a-197">Você pode usar esse parâmetro para restringir as funções exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-197">You can use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="5da9a-198">Ele pode remover funções da lista de aliases exportados, mas não pode adicionar funções à lista.</span><span class="sxs-lookup"><span data-stu-id="5da9a-198">It can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

<span data-ttu-id="5da9a-199">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **FunctionsToExport** com um valor de `*` (All), o que significa que todas as funções definidas no módulo serão exportadas pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-199">If you omit this parameter, `New-ModuleManifest` creates an **FunctionsToExport** key with a value of `*` (all), meaning that all functions defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5da9a-200">-GUID</span><span class="sxs-lookup"><span data-stu-id="5da9a-200">-Guid</span></span>

<span data-ttu-id="5da9a-201">Especifica um identificador exclusivo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-201">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="5da9a-202">O **GUID** pode ser usado para distinguir entre módulos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="5da9a-202">The **GUID** can be used to distinguish among modules with the same name.</span></span>

<span data-ttu-id="5da9a-203">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **GUID** no manifesto e gerará um **GUID** para o valor.</span><span class="sxs-lookup"><span data-stu-id="5da9a-203">If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in the manifest and generates a **GUID** for the value.</span></span>

<span data-ttu-id="5da9a-204">Para criar um novo **GUID** no PowerShell, digite `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="5da9a-204">To create a new **GUID** in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A GUID generated for the module
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-205">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="5da9a-205">-HelpInfoUri</span></span>

<span data-ttu-id="5da9a-206">Especifica o endereço da Internet do arquivo XML HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-206">Specifies the internet address of the HelpInfo XML file for the module.</span></span> <span data-ttu-id="5da9a-207">Insira um Uniform Resource Identifier (URI) que comece com **http** ou **https** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-207">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https** .</span></span>

<span data-ttu-id="5da9a-208">O arquivo XML HelpInfo dá suporte ao recurso de ajuda atualizável que foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5da9a-208">The HelpInfo XML file supports the Updatable Help feature that was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="5da9a-209">Ele contém informações sobre o local dos arquivos de ajuda que podem ser baixados para o módulo e os números de versão dos arquivos de ajuda mais recentes para cada localidade com suporte.</span><span class="sxs-lookup"><span data-stu-id="5da9a-209">It contains information about the location of downloadable help files for the module and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="5da9a-210">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="5da9a-210">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="5da9a-211">Para obter informações sobre o arquivo XML HelpInfo, consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="5da9a-211">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="5da9a-212">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5da9a-212">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5da9a-213">-IconUri</span><span class="sxs-lookup"><span data-stu-id="5da9a-213">-IconUri</span></span>

<span data-ttu-id="5da9a-214">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-214">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="5da9a-215">O ícone especificado é exibido na página da Galeria da Web para o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-215">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-216">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="5da9a-216">-LicenseUri</span></span>

<span data-ttu-id="5da9a-217">Especifica a URL dos termos de licenciamento do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-217">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-218">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="5da9a-218">-ModuleList</span></span>

<span data-ttu-id="5da9a-219">Lista todos os módulos incluídos neste módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-219">Lists all modules that are included in this module.</span></span>

<span data-ttu-id="5da9a-220">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-220">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="5da9a-221">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="5da9a-221">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="5da9a-222">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5da9a-222">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="5da9a-223">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-223">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="5da9a-224">Os módulos listados no valor dessa chave não são processados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5da9a-224">The modules that are listed in the value of this key aren't automatically processed.</span></span>

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

### <span data-ttu-id="5da9a-225">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="5da9a-225">-ModuleVersion</span></span>

<span data-ttu-id="5da9a-226">Especifica a versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-226">Specifies the module's version.</span></span>

<span data-ttu-id="5da9a-227">Esse parâmetro não é necessário, mas uma chave **ModuleVersion** é necessária no manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-227">This parameter isn't required, but a **ModuleVersion** key is required in the manifest.</span></span> <span data-ttu-id="5da9a-228">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **ModuleVersion** com um valor de 1,0.</span><span class="sxs-lookup"><span data-stu-id="5da9a-228">If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion** key with a value of 1.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1.0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-229">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="5da9a-229">-NestedModules</span></span>

<span data-ttu-id="5da9a-230">Especifica módulos de script ( `.psm1` ) e módulos binários ( `.dll` ) que são importados para o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-230">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="5da9a-231">Os arquivos na chave **NestedModules** são executados na ordem em que estão listados no valor.</span><span class="sxs-lookup"><span data-stu-id="5da9a-231">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="5da9a-232">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-232">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="5da9a-233">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="5da9a-233">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="5da9a-234">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5da9a-234">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="5da9a-235">Normalmente, módulos aninhados contêm comandos que o módulo raiz precisa para seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="5da9a-235">Typically, nested modules contain commands that the root module needs for its internal processing.</span></span>
<span data-ttu-id="5da9a-236">Por padrão, os comandos em módulos aninhados são exportados do estado de sessão do módulo para o estado de sessão do chamador, mas o módulo raiz pode restringir os comandos que ele exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-236">By default, the commands in nested modules are exported from the module's session state into the caller's session state, but the root module can restrict the commands that it exports.</span></span> <span data-ttu-id="5da9a-237">Por exemplo, usando um `Export-ModuleMember` comando.</span><span class="sxs-lookup"><span data-stu-id="5da9a-237">For example, by using an `Export-ModuleMember` command.</span></span>

<span data-ttu-id="5da9a-238">Os módulos aninhados no estado de sessão do módulo estão disponíveis para o módulo raiz, mas não são retornados por um `Get-Module` comando no estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="5da9a-238">Nested modules in the module session state are available to the root module, but they aren't returned by a `Get-Module` command in the caller's session state.</span></span>

<span data-ttu-id="5da9a-239">Os scripts ( `.ps1` ) listados na chave **NestedModules** são executados no estado de sessão do módulo, não no estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="5da9a-239">Scripts (`.ps1`) that are listed in the **NestedModules** key are run in the module's session state, not in the caller's session state.</span></span> <span data-ttu-id="5da9a-240">Para executar um script no estado de sessão do chamador, liste o nome do arquivo de script no valor da chave **ScriptsToProcess** do manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-240">To run a script in the caller's session state, list the script file name in the value of the **ScriptsToProcess** key in the manifest.</span></span>

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

### <span data-ttu-id="5da9a-241">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5da9a-241">-PassThru</span></span>

<span data-ttu-id="5da9a-242">Grava o manifesto do módulo resultante no console e cria um `.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-242">Writes the resulting module manifest to the console and creates a `.psd1` file.</span></span> <span data-ttu-id="5da9a-243">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5da9a-243">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-244">-Path</span><span class="sxs-lookup"><span data-stu-id="5da9a-244">-Path</span></span>

<span data-ttu-id="5da9a-245">Especifica o caminho e o nome de arquivo do novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-245">Specifies the path and file name of the new module manifest.</span></span> <span data-ttu-id="5da9a-246">Insira um caminho e um nome de arquivo com uma `.psd1` extensão de nome de arquivo, como `$pshome\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="5da9a-246">Enter a path and file name with a `.psd1` file name extension, such as `$pshome\Modules\MyModule\MyModule.psd1`.</span></span> <span data-ttu-id="5da9a-247">O parâmetro **path** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5da9a-247">The **Path** parameter is required.</span></span>

<span data-ttu-id="5da9a-248">Se você especificar o caminho para um arquivo existente, `New-ModuleManifest` o substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5da9a-248">If you specify the path to an existing file, `New-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="5da9a-249">O manifesto deve estar localizado no diretório do módulo e o nome do arquivo de manifesto deve ser o mesmo que o nome do diretório do módulo, mas com uma `.psd1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-249">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` file name extension.</span></span>

> [!NOTE]
> <span data-ttu-id="5da9a-250">Você não pode usar variáveis, como `$PSHOME` ou `$HOME` , em resposta a um prompt para um valor de parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-250">You cannot use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="5da9a-251">Para usar uma variável, inclua o parâmetro **Path** no comando.</span><span class="sxs-lookup"><span data-stu-id="5da9a-251">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-252">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="5da9a-252">-PowerShellHostName</span></span>

<span data-ttu-id="5da9a-253">Especifica o nome do programa de host do PowerShell que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="5da9a-253">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="5da9a-254">Insira o nome do programa host, como **ISE do Windows PowerShell host** ou **ConsoleHost** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-254">Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost** .</span></span> <span data-ttu-id="5da9a-255">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-255">Wildcards aren't permitted.</span></span>

<span data-ttu-id="5da9a-256">Para localizar o nome de um programa de host, no programa, digite `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="5da9a-256">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="5da9a-257">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="5da9a-257">-PowerShellHostVersion</span></span>

<span data-ttu-id="5da9a-258">Especifica a versão mínima do programa de host do PowerShell que funciona com o módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-258">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="5da9a-259">Insira um número de versão, como 1.1.</span><span class="sxs-lookup"><span data-stu-id="5da9a-259">Enter a version number, such as 1.1.</span></span>

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

### <span data-ttu-id="5da9a-260">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="5da9a-260">-PowerShellVersion</span></span>

<span data-ttu-id="5da9a-261">Especifica a versão mínima do PowerShell que funciona com este módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-261">Specifies the minimum version of PowerShell that works with this module.</span></span> <span data-ttu-id="5da9a-262">Por exemplo, você pode inserir 1,0, 2,0 ou 3,0 como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5da9a-262">For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value.</span></span>

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

### <span data-ttu-id="5da9a-263">-Pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="5da9a-263">-Prerelease</span></span>

<span data-ttu-id="5da9a-264">Cadeia de caracteres de pré-lançamento deste módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-264">Prerelease string of this module.</span></span> <span data-ttu-id="5da9a-265">Adicionar uma cadeia de caracteres de pré-lançamento identifica o módulo como uma versão de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="5da9a-265">Adding a Prerelease string identifies the module as a prerelease version.</span></span> <span data-ttu-id="5da9a-266">Quando o módulo é publicado no Galeria do PowerShell, esses dados são usados para identificar pacotes de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="5da9a-266">When the module is published to the PowerShell Gallery, this data is used to identify prerelease packages.</span></span> <span data-ttu-id="5da9a-267">Para adquirir pacotes de pré-lançamento da galeria, você deve usar o parâmetro **AllowPrerelease** com os comandos PowerShellGet `Find-Module` , `Install-Module` , `Update-Module` e `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="5da9a-267">To acquire prerelease packages from the Gallery, you must use the **AllowPrerelease** parameter with the PowerShellGet commands `Find-Module`, `Install-Module`, `Update-Module`, and `Save-Module`.</span></span>

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

### <span data-ttu-id="5da9a-268">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="5da9a-268">-PrivateData</span></span>

<span data-ttu-id="5da9a-269">Especifica os dados que são passados para o módulo quando ele é importado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-269">Specifies data that is passed to the module when it's imported.</span></span>

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

### <span data-ttu-id="5da9a-270">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="5da9a-270">-ProcessorArchitecture</span></span>

<span data-ttu-id="5da9a-271">Especifica a arquitetura do processador que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="5da9a-271">Specifies the processor architecture that the module requires.</span></span> <span data-ttu-id="5da9a-272">Os valores válidos são x86, AMD64, IA64, MSIL e nenhum (desconhecido ou não especificado).</span><span class="sxs-lookup"><span data-stu-id="5da9a-272">Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified).</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-273">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="5da9a-273">-ProjectUri</span></span>

<span data-ttu-id="5da9a-274">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-274">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-275">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="5da9a-275">-ReleaseNotes</span></span>

<span data-ttu-id="5da9a-276">Especifica notas de versão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-276">Specifies release notes.</span></span>

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

### <span data-ttu-id="5da9a-277">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="5da9a-277">-RequiredAssemblies</span></span>

<span data-ttu-id="5da9a-278">Especifica os arquivos de assembly ( `.dll` ) que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="5da9a-278">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="5da9a-279">Digite os nomes de arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="5da9a-279">Enter the assembly file names.</span></span>
<span data-ttu-id="5da9a-280">O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-280">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="5da9a-281">Use esse parâmetro para listar todos os assemblies exigidos pelo módulo, incluindo assemblies que devem ser carregados para atualizar quaisquer formatações ou arquivos de tipo listados nas chaves **FormatsToProcess** ou **TypesToProcess** , mesmo se esses assemblies também estiverem listados como módulos binários na chave **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-281">Use this parameter to list all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="5da9a-282">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="5da9a-282">-RequiredModules</span></span>

<span data-ttu-id="5da9a-283">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="5da9a-283">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="5da9a-284">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="5da9a-284">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="5da9a-285">Se os módulos necessários não estiverem disponíveis, o `Import-Module` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="5da9a-285">If the required modules aren't available, the `Import-Module` command fails.</span></span>

<span data-ttu-id="5da9a-286">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-286">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="5da9a-287">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="5da9a-287">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="5da9a-288">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5da9a-288">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="5da9a-289">No PowerShell 2,0, o `Import-Module` não importa os módulos necessários automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5da9a-289">In PowerShell 2.0, `Import-Module` doesn't import required modules automatically.</span></span> <span data-ttu-id="5da9a-290">Ele apenas verifica se os módulos necessários estão no estado da sessão global.</span><span class="sxs-lookup"><span data-stu-id="5da9a-290">It just verifies that the required modules are in the global session state.</span></span>

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

### <span data-ttu-id="5da9a-291">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="5da9a-291">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="5da9a-292">Sinalizador para indicar se o módulo requer aceitação explícita do usuário para Install, Update, orsave.</span><span class="sxs-lookup"><span data-stu-id="5da9a-292">Flag to indicate whether the module requires explicit user acceptance for install, update, orsave.</span></span>

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

### <span data-ttu-id="5da9a-293">-RootModule</span><span class="sxs-lookup"><span data-stu-id="5da9a-293">-RootModule</span></span>

<span data-ttu-id="5da9a-294">Especifica o arquivo primário ou raiz do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-294">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="5da9a-295">Insira o nome de arquivo de um script ( `.ps1` ), um módulo de script ( `.psm1` ), um manifesto de módulo ( `.psd1` ), um assembly ( `.dll` ), um arquivo XML de definição de cmdlet ( `.cdxml` ) ou um fluxo de trabalho ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="5da9a-295">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="5da9a-296">Quando o módulo é importado, os membros que são exportados do arquivo do módulo raiz são importados para o estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="5da9a-296">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="5da9a-297">Se um módulo tiver um arquivo de manifesto e nenhum arquivo raiz tiver sido designado na chave **RootModule** , o manifesto se tornará o arquivo primário do módulo e o módulo se tornará um módulo de manifesto (módulotype = manifesto).</span><span class="sxs-lookup"><span data-stu-id="5da9a-297">If a module has a manifest file and no root file was designated in the **RootModule** key, the manifest becomes the primary file for the module, and the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="5da9a-298">Para exportar membros de `.psm1` ou `.dll` arquivos em um módulo que tenha um manifesto, os nomes desses arquivos devem ser especificados nos valores das chaves **RootModule** ou **NestedModules** no manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-298">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="5da9a-299">Caso contrário, seus membros não serão exportados.</span><span class="sxs-lookup"><span data-stu-id="5da9a-299">Otherwise, their members aren't exported.</span></span>

> [!NOTE]
> <span data-ttu-id="5da9a-300">No PowerShell 2,0, essa chave foi chamada de **ModuleToProcess** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-300">In PowerShell 2.0, this key was called **ModuleToProcess** .</span></span> <span data-ttu-id="5da9a-301">Você pode usar o nome do parâmetro **RootModule** ou seu alias **ModuleToProcess** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-301">You can use the **RootModule** parameter name or its **ModuleToProcess** alias.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ModuleToProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5da9a-302">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="5da9a-302">-ScriptsToProcess</span></span>

<span data-ttu-id="5da9a-303">Especifica os arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-303">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="5da9a-304">Você pode usar esses scripts para preparar um ambiente, assim como você pode usar um script de logon.</span><span class="sxs-lookup"><span data-stu-id="5da9a-304">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="5da9a-305">Para especificar scripts que são executados no estado de sessão do módulo, use a chave **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-305">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="5da9a-306">-Marcas</span><span class="sxs-lookup"><span data-stu-id="5da9a-306">-Tags</span></span>

<span data-ttu-id="5da9a-307">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="5da9a-307">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="5da9a-308">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="5da9a-308">-TypesToProcess</span></span>

<span data-ttu-id="5da9a-309">Especifica os arquivos de tipo ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-309">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="5da9a-310">Quando você importa o módulo, o PowerShell executa o `Update-TypeData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="5da9a-310">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="5da9a-311">Como os arquivos de tipo não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-311">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="5da9a-312">-VariablesToExport</span><span class="sxs-lookup"><span data-stu-id="5da9a-312">-VariablesToExport</span></span>

<span data-ttu-id="5da9a-313">Especifica as variáveis que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="5da9a-313">Specifies the variables that the module exports.</span></span> <span data-ttu-id="5da9a-314">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5da9a-314">Wildcards are permitted.</span></span>

<span data-ttu-id="5da9a-315">Você pode usar esse parâmetro para restringir as variáveis exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-315">You can use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="5da9a-316">Ele pode remover variáveis da lista de variáveis exportadas, mas não pode adicionar variáveis à lista.</span><span class="sxs-lookup"><span data-stu-id="5da9a-316">It can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

<span data-ttu-id="5da9a-317">Se você omitir esse parâmetro, `New-ModuleManifest` o criará uma chave **VariablesToExport** com um valor de `*` (All), o que significa que todas as variáveis definidas no módulo serão exportadas pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="5da9a-317">If you omit this parameter, `New-ModuleManifest` creates a **VariablesToExport** key with a value of `*` (all), meaning that all variables defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5da9a-318">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5da9a-318">-Confirm</span></span>

<span data-ttu-id="5da9a-319">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5da9a-319">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5da9a-320">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5da9a-320">-WhatIf</span></span>

<span data-ttu-id="5da9a-321">Mostra o que aconteceria se `New-ModuleManifest` for executado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-321">Shows what would happen if `New-ModuleManifest` runs.</span></span> <span data-ttu-id="5da9a-322">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-322">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="5da9a-323">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="5da9a-323">-ClrVersion</span></span>

<span data-ttu-id="5da9a-324">Especifica a versão mínima do CLR (Common Language Runtime) do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="5da9a-324">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="5da9a-325">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5da9a-325">CommonParameters</span></span>
<span data-ttu-id="5da9a-326">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5da9a-326">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5da9a-327">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5da9a-327">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5da9a-328">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5da9a-328">INPUTS</span></span>

### <span data-ttu-id="5da9a-329">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5da9a-329">None</span></span>

<span data-ttu-id="5da9a-330">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5da9a-330">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5da9a-331">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5da9a-331">OUTPUTS</span></span>

### <span data-ttu-id="5da9a-332">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="5da9a-332">None or System.String</span></span>

<span data-ttu-id="5da9a-333">Por padrão, o `New-ModuleManifest` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5da9a-333">By default, `New-ModuleManifest` doesn't generate any output.</span></span> <span data-ttu-id="5da9a-334">No entanto, se você usar o parâmetro **PassThru** , ele gerará um objeto **System. String** que representa o manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-334">However, if you use the **PassThru** parameter, it generates a **System.String** object representing the module manifest.</span></span>

## <span data-ttu-id="5da9a-335">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5da9a-335">NOTES</span></span>

<span data-ttu-id="5da9a-336">`New-ModuleManifest` a execução em plataformas Windows e não Windows cria arquivos de manifesto de módulo ( `.psd1` ) codificados como **UTF8NoBOM** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-336">`New-ModuleManifest` running on Windows and non-Windows platforms creates module manifest (`.psd1`) files encoded as **UTF8NoBOM** .</span></span>

<span data-ttu-id="5da9a-337">Manifestos de módulo são geralmente opcionais.</span><span class="sxs-lookup"><span data-stu-id="5da9a-337">Module manifests are usually optional.</span></span> <span data-ttu-id="5da9a-338">No entanto, um manifesto de módulo é necessária para exportar um assembly instalado no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="5da9a-338">However, a module manifest is required to export an assembly that is installed in the global assembly cache.</span></span>

<span data-ttu-id="5da9a-339">Para adicionar ou alterar arquivos no `$pshome\Modules` diretório, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="5da9a-339">To add or change files in the `$pshome\Modules` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="5da9a-340">No PowerShell 2,0, muitos parâmetros de `New-ModuleManifest` eram obrigatórios, embora não sejam necessários em um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-340">In PowerShell 2.0, many parameters of `New-ModuleManifest` were mandatory, even though they weren't required in a module manifest.</span></span> <span data-ttu-id="5da9a-341">A partir do PowerShell 3,0, somente o parâmetro **path** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5da9a-341">Beginning in PowerShell 3.0, only the **Path** parameter is mandatory.</span></span>

<span data-ttu-id="5da9a-342">Uma sessão é uma instância do ambiente de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5da9a-342">A session is an instance of the PowerShell execution environment.</span></span> <span data-ttu-id="5da9a-343">Uma sessão pode ter um ou mais estados de sessão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-343">A session can have one or more session states.</span></span> <span data-ttu-id="5da9a-344">Por padrão, uma sessão tem apenas um estado de sessão global, mas cada módulo importado tem seu próprio estado de sessão.</span><span class="sxs-lookup"><span data-stu-id="5da9a-344">By default, a session has only a global session state, but each imported module has its own session state.</span></span> <span data-ttu-id="5da9a-345">Estados de sessão permitem que os comandos em um módulo sejam executados sem afetar o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="5da9a-345">Session states allow the commands in a module to run without affecting the global session state.</span></span>

<span data-ttu-id="5da9a-346">O estado de sessão do chamador é o estado da sessão no qual um módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="5da9a-346">The caller's session state is the session state into which a module is imported.</span></span> <span data-ttu-id="5da9a-347">Normalmente, ele se refere ao estado de sessão global, mas quando um módulo importa módulos aninhados, o chamador é o módulo e o estado de sessão do chamador é o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="5da9a-347">Typically, it refers to the global session state, but when a module imports nested modules, the caller is the module and the caller's session state is the module's session state.</span></span>

## <span data-ttu-id="5da9a-348">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5da9a-348">RELATED LINKS</span></span>

[<span data-ttu-id="5da9a-349">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="5da9a-349">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="5da9a-350">Get-Module</span><span class="sxs-lookup"><span data-stu-id="5da9a-350">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="5da9a-351">Import-Module</span><span class="sxs-lookup"><span data-stu-id="5da9a-351">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="5da9a-352">New-Module</span><span class="sxs-lookup"><span data-stu-id="5da9a-352">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="5da9a-353">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="5da9a-353">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="5da9a-354">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="5da9a-354">Test-ModuleManifest</span></span>](Test-ModuleManifest.md)

[<span data-ttu-id="5da9a-355">about_Modules</span><span class="sxs-lookup"><span data-stu-id="5da9a-355">about_Modules</span></span>](./About/about_Modules.md)

