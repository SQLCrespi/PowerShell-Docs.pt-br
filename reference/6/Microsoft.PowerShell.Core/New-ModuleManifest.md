---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/02/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-modulemanifest?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ModuleManifest
ms.openlocfilehash: d72bc32ffa96720a9eb2451ff28ad126b69f0d7a
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239777"
---
# <span data-ttu-id="8f39f-103">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="8f39f-103">New-ModuleManifest</span></span>

## <span data-ttu-id="8f39f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8f39f-104">SYNOPSIS</span></span>
<span data-ttu-id="8f39f-105">Cria um novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-105">Creates a new module manifest.</span></span>

## <span data-ttu-id="8f39f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f39f-106">SYNTAX</span></span>

### <span data-ttu-id="8f39f-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="8f39f-107">All</span></span>

```
New-ModuleManifest [-Path] <string> [-NestedModules <Object[]>] [-Guid <guid>] [-Author <string>]
 [-CompanyName <string>] [-Copyright <string>] [-RootModule <string>] [-ModuleVersion <version>]
 [-Description <string>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-PowerShellVersion <version>] [-ClrVersion <version>] [-DotNetFrameworkVersion <version>]
 [-PowerShellHostName <string>] [-PowerShellHostVersion <version>] [-RequiredModules <Object[]>]
 [-TypesToProcess <string[]>] [-FormatsToProcess <string[]>] [-ScriptsToProcess <string[]>]
 [-RequiredAssemblies <string[]>] [-FileList <string[]>] [-ModuleList <Object[]>]
 [-FunctionsToExport <string[]>] [-AliasesToExport <string[]>] [-VariablesToExport <string[]>]
 [-CmdletsToExport <string[]>] [-DscResourcesToExport <string[]>] [-CompatiblePSEditions <string[]>]
 [-PrivateData <Object>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>]
 [-ReleaseNotes <string>] [-HelpInfoUri <string>] [-PassThru] [-DefaultCommandPrefix <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8f39f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f39f-108">DESCRIPTION</span></span>

<span data-ttu-id="8f39f-109">O `New-ModuleManifest` cmdlet cria um novo arquivo de manifesto de módulo ( `.psd1` ), popula seus valores e salva o arquivo de manifesto no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-109">The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.</span></span>

<span data-ttu-id="8f39f-110">Autores de módulo podem usar este cmdlet para criar um manifesto para seu módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-110">Module authors can use this cmdlet to create a manifest for their module.</span></span> <span data-ttu-id="8f39f-111">Um manifesto de módulo é um `.psd1` arquivo que contém uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="8f39f-111">A module manifest is a `.psd1` file that contains a hash table.</span></span> <span data-ttu-id="8f39f-112">As chaves e os valores na tabela de hash descrevem o conteúdo e os atributos do módulo, definem os pré-requisitos e determinam como os componentes são processados.</span><span class="sxs-lookup"><span data-stu-id="8f39f-112">The keys and values in the hash table describe the contents and attributes of the module, define the prerequisites, and determine how the components are processed.</span></span> <span data-ttu-id="8f39f-113">Os manifestos não são necessários para um módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-113">Manifests aren't required for a module.</span></span>

<span data-ttu-id="8f39f-114">`New-ModuleManifest` Cria um manifesto que inclui todas as chaves de manifesto usadas com frequência, para que você possa usar a saída padrão como um modelo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-114">`New-ModuleManifest` creates a manifest that includes all the commonly used manifest keys, so you can use the default output as a manifest template.</span></span> <span data-ttu-id="8f39f-115">Para adicionar ou alterar valores, ou para adicionar chaves de módulo que esse cmdlet não adiciona, abra o arquivo resultante em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-115">To add or change values, or to add module keys that this cmdlet doesn't add, open the resulting file in a text editor.</span></span>

<span data-ttu-id="8f39f-116">Cada parâmetro, exceto **Path** e **PassThru** , cria uma chave de manifesto de módulo e seu valor.</span><span class="sxs-lookup"><span data-stu-id="8f39f-116">Each parameter, except for **Path** and **PassThru** , creates a module manifest key and its value.</span></span>
<span data-ttu-id="8f39f-117">Em um manifesto de módulo, somente a chave **ModuleVersion** é necessária.</span><span class="sxs-lookup"><span data-stu-id="8f39f-117">In a module manifest, only the **ModuleVersion** key is required.</span></span> <span data-ttu-id="8f39f-118">A menos que especificado na descrição do parâmetro, se você omitir um parâmetro do comando, `New-ModuleManifest` o criará uma cadeia de caracteres de comentário para o valor associado que não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="8f39f-118">Unless specified in the parameter description, if you omit a parameter from the command, `New-ModuleManifest` creates a comment string for the associated value that has no effect.</span></span>

<span data-ttu-id="8f39f-119">No PowerShell 2,0, `New-ModuleManifest` o solicita os valores de parâmetros comumente usados que não são especificados no comando, além dos valores de parâmetro necessários.</span><span class="sxs-lookup"><span data-stu-id="8f39f-119">In PowerShell 2.0, `New-ModuleManifest` prompts you for the values of commonly used parameters that aren't specified in the command, in addition to required parameter values.</span></span> <span data-ttu-id="8f39f-120">A partir do PowerShell 3,0, o `New-ModuleManifest` solicita somente quando os valores de parâmetro necessários não são especificados.</span><span class="sxs-lookup"><span data-stu-id="8f39f-120">Beginning in PowerShell 3.0, `New-ModuleManifest` prompts only when required parameter values aren't specified.</span></span>

<span data-ttu-id="8f39f-121">Se você estiver planejando publicar seu módulo no Galeria do PowerShell, o manifesto deverá conter valores para determinadas propriedades.</span><span class="sxs-lookup"><span data-stu-id="8f39f-121">If you are planning to publish your module in the PowerShell Gallery, the manifest must contain values for certain properties.</span></span> <span data-ttu-id="8f39f-122">Para obter mais informações, consulte [metadados necessários para itens publicados no Galeria do PowerShell](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) na documentação da galeria.</span><span class="sxs-lookup"><span data-stu-id="8f39f-122">For more information, see [Required metadata for items published to the PowerShell Gallery](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in the Gallery documentation.</span></span>

## <span data-ttu-id="8f39f-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8f39f-123">EXAMPLES</span></span>

### <span data-ttu-id="8f39f-124">Exemplo 1-criar um novo manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="8f39f-124">Example 1 - Create a new module manifest</span></span>

<span data-ttu-id="8f39f-125">Este exemplo cria um novo manifesto de módulo no arquivo que é especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-125">This example creates a new module manifest in the file that is specified by the **Path** parameter.</span></span>
<span data-ttu-id="8f39f-126">O parâmetro **PassThru** envia a saída para o pipeline e para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-126">The **PassThru** parameter sends the output to the pipeline and to the file.</span></span>

<span data-ttu-id="8f39f-127">A saída mostra os valores padrão de todas as chaves do manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-127">The output shows the default values of all keys in the manifest.</span></span>

```powershell
New-ModuleManifest -Path C:\ps-test\Test-Module\Test-Module.psd1 -PassThru
```

```Output
#
# Module manifest for module 'Test-Module'
#
# Generated by: ContosoAdmin
#
# Generated on: 1/22/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = '47179120-0bcb-4f14-8d80-f4560107f85c'

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

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

### <span data-ttu-id="8f39f-128">Exemplo 2-criar um novo manifesto com algumas configurações preenchidas previamente</span><span class="sxs-lookup"><span data-stu-id="8f39f-128">Example 2 - Create a new manifest with some prepopulated settings</span></span>

<span data-ttu-id="8f39f-129">Este exemplo cria um novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-129">This example creates a new module manifest.</span></span> <span data-ttu-id="8f39f-130">Ele usa os parâmetros **PowerShellVersion** e **AliasesToExport** para adicionar valores às chaves de manifesto correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8f39f-130">It uses the **PowerShellVersion** and **AliasesToExport** parameters to add values to the corresponding manifest keys.</span></span>

```powershell
New-ModuleManifest -PowerShellVersion 1.0 -AliasesToExport JKBC, DRC, TAC -Path C:\ps-test\ManifestTest.psd1
```

### <span data-ttu-id="8f39f-131">Exemplo 3-criar um manifesto que requer outros módulos</span><span class="sxs-lookup"><span data-stu-id="8f39f-131">Example 3 - Create a manifest that requires other modules</span></span>

<span data-ttu-id="8f39f-132">Este exemplo usa um formato de cadeia de caracteres para especificar o nome do módulo **BitsTransfer** e o formato da tabela de hash para especificar o nome, um **GUID** e uma versão do módulo **PSScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-132">This example uses a string format to specify the name of the **BitsTransfer** module and the hash table format to specify the name, a **GUID** , and a version of the **PSScheduledJob** module.</span></span>

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

<span data-ttu-id="8f39f-133">Este exemplo mostra como usar a cadeia de caracteres e os formatos de tabela de hash do parâmetro **ModuleList** , **RequiredModules** e **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-133">This example shows how to use the string and hash table formats of the **ModuleList** , **RequiredModules** , and **NestedModules** parameter.</span></span> <span data-ttu-id="8f39f-134">Você pode combinar cadeias de caracteres e tabelas de hash no mesmo valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f39f-134">You can combine strings and hash tables in the same parameter value.</span></span>

### <span data-ttu-id="8f39f-135">Exemplo 4-criar um manifesto que ofereça suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="8f39f-135">Example 4 - Create a manifest that supports updateable help</span></span>

<span data-ttu-id="8f39f-136">Este exemplo usa o parâmetro **HelpInfoUri** para criar uma chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-136">This example uses the **HelpInfoUri** parameter to create a **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="8f39f-137">O valor do parâmetro e a chave devem começar com **http** ou **https**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-137">The value of the parameter and the key must begin with **http** or **https**.</span></span> <span data-ttu-id="8f39f-138">Esse valor informa o sistema do Updatable Help onde encontrar o arquivo XML de informações de ajuda atualizável HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-138">This value tells the Updatable Help system where to find the HelpInfo XML updatable help information file for the module.</span></span>

```powershell
$moduleSettings = @{
  HelpInfoUri = 'http://https://go.microsoft.com/fwlink/?LinkID=603'
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="8f39f-139">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="8f39f-139">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="8f39f-140">Para obter informações sobre o arquivo XML HelpInfo, consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="8f39f-140">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

### <span data-ttu-id="8f39f-141">Exemplo 5-obtendo informações de módulo</span><span class="sxs-lookup"><span data-stu-id="8f39f-141">Example 5 - Getting module information</span></span>

<span data-ttu-id="8f39f-142">Este exemplo mostra como obter os valores de configuração de um módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-142">This example shows how to get the configuration values of a module.</span></span> <span data-ttu-id="8f39f-143">Os valores no manifesto do módulo são refletidos nos valores das propriedades do objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-143">The values in the module manifest are reflected in the values of properties of the module object.</span></span>

<span data-ttu-id="8f39f-144">O `Get-Module` cmdlet é usado para obter o módulo **Microsoft. PowerShell. Diagnostics** usando o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-144">The `Get-Module` cmdlet is used to get the **Microsoft.PowerShell.Diagnostics** module using the **List** parameter.</span></span> <span data-ttu-id="8f39f-145">O comando envia o módulo para o `Format-List` cmdlet para exibir todas as propriedades e valores do objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-145">The command sends the module to the `Format-List` cmdlet to display all properties and values of the module object.</span></span>

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

## <span data-ttu-id="8f39f-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f39f-146">PARAMETERS</span></span>

### <span data-ttu-id="8f39f-147">-AliasesToExport</span><span class="sxs-lookup"><span data-stu-id="8f39f-147">-AliasesToExport</span></span>

<span data-ttu-id="8f39f-148">Especifica os aliases que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-148">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="8f39f-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-149">Wildcards are permitted.</span></span>

<span data-ttu-id="8f39f-150">Você pode usar esse parâmetro para restringir os aliases exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-150">You can use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="8f39f-151">Ele pode remover aliases da lista de aliases exportados, mas não pode adicionar aliases à lista.</span><span class="sxs-lookup"><span data-stu-id="8f39f-151">It can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

<span data-ttu-id="8f39f-152">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **AliasesToExport** com um valor de `*` (All), o que significa que todos os aliases definidos no módulo serão exportados pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-152">If you omit this parameter, `New-ModuleManifest` creates an **AliasesToExport** key with a value of `*` (all), meaning that all aliases defined in the module are exported by the manifest.</span></span>

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

### <span data-ttu-id="8f39f-153">-Autor</span><span class="sxs-lookup"><span data-stu-id="8f39f-153">-Author</span></span>

<span data-ttu-id="8f39f-154">Especifica o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-154">Specifies the module author.</span></span>

<span data-ttu-id="8f39f-155">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave de **autor** com o nome do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8f39f-155">If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user.</span></span>

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

### <span data-ttu-id="8f39f-156">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="8f39f-156">-ClrVersion</span></span>

<span data-ttu-id="8f39f-157">Especifica a versão mínima do CLR (Common Language Runtime) do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="8f39f-157">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="8f39f-158">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="8f39f-158">-CmdletsToExport</span></span>

<span data-ttu-id="8f39f-159">Especifica os cmdlets que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-159">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="8f39f-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-160">Wildcards are permitted.</span></span>

<span data-ttu-id="8f39f-161">Você pode usar esse parâmetro para restringir os cmdlets exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-161">You can use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="8f39f-162">Ele pode remover cmdlets da lista de cmdlets exportados, mas não pode adicionar cmdlets à lista.</span><span class="sxs-lookup"><span data-stu-id="8f39f-162">It can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

<span data-ttu-id="8f39f-163">Se você omitir esse parâmetro, `New-ModuleManifest` o criará uma chave **CmdletsToExport** com um valor de `*` (All), o que significa que todos os cmdlets definidos no módulo serão exportados pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-163">If you omit this parameter, `New-ModuleManifest` creates a **CmdletsToExport** key with a value of `*` (all), meaning that all cmdlets defined in the module are exported by the manifest.</span></span>

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

### <span data-ttu-id="8f39f-164">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="8f39f-164">-CompanyName</span></span>

<span data-ttu-id="8f39f-165">Identifica a empresa ou fornecedor que o módulo criou.</span><span class="sxs-lookup"><span data-stu-id="8f39f-165">Identifies the company or vendor who created the module.</span></span>

<span data-ttu-id="8f39f-166">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **CompanyName** com um valor de "Unknown".</span><span class="sxs-lookup"><span data-stu-id="8f39f-166">If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown".</span></span>

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

### <span data-ttu-id="8f39f-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8f39f-167">-Confirm</span></span>

<span data-ttu-id="8f39f-168">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f39f-168">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8f39f-169">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="8f39f-169">-CompatiblePSEditions</span></span>

<span data-ttu-id="8f39f-170">Especifica o PSEditions compatível do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-170">Specifies the module's compatible PSEditions.</span></span> <span data-ttu-id="8f39f-171">Para obter informações sobre PSEdition, consulte [módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="8f39f-171">For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

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

### <span data-ttu-id="8f39f-172">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="8f39f-172">-Copyright</span></span>

<span data-ttu-id="8f39f-173">Especifica uma declaração de direitos autorais do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-173">Specifies a copyright statement for the module.</span></span>

<span data-ttu-id="8f39f-174">Se você omitir esse parâmetro, o `New-ModuleManifest` cria uma chave de **direitos autorais** com um valor de `(c) <year> <username>. All rights reserved.` onde `<year>` é o ano atual e `<username>` é o valor da chave de **autor** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-174">If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<year>` is the current year and `<username>` is the value of the **Author** key.</span></span>

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

### <span data-ttu-id="8f39f-175">-Description</span><span class="sxs-lookup"><span data-stu-id="8f39f-175">-Description</span></span>

<span data-ttu-id="8f39f-176">Descreve o conteúdo do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-176">Describes the contents of the module.</span></span>

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

### <span data-ttu-id="8f39f-177">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="8f39f-177">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="8f39f-178">Especifica a versão mínima do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="8f39f-178">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="8f39f-179">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="8f39f-179">-DscResourcesToExport</span></span>

<span data-ttu-id="8f39f-180">Especifica os recursos de DSC (configuração de estado desejado) que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-180">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="8f39f-181">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-181">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="8f39f-182">-FileList</span><span class="sxs-lookup"><span data-stu-id="8f39f-182">-FileList</span></span>

<span data-ttu-id="8f39f-183">Especifica todos os itens incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-183">Specifies all items that are included in the module.</span></span>

<span data-ttu-id="8f39f-184">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-184">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="8f39f-185">Os arquivos listados na chave são incluídos quando o módulo é publicado, mas todas as funções não são exportadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f39f-185">The files listed in the key are included when the module is published, but any functions aren't automatically exported.</span></span>

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

### <span data-ttu-id="8f39f-186">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="8f39f-186">-FormatsToProcess</span></span>

<span data-ttu-id="8f39f-187">Especifica os arquivos de formatação ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-187">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="8f39f-188">Quando você importa um módulo, o PowerShell executa o `Update-FormatData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="8f39f-188">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="8f39f-189">Como os arquivos de formatação não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-189">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="8f39f-190">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="8f39f-190">-FunctionsToExport</span></span>

<span data-ttu-id="8f39f-191">Especifica as funções que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-191">Specifies the functions that the module exports.</span></span> <span data-ttu-id="8f39f-192">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-192">Wildcards are permitted.</span></span>

<span data-ttu-id="8f39f-193">Você pode usar esse parâmetro para restringir as funções exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-193">You can use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="8f39f-194">Ele pode remover funções da lista de aliases exportados, mas não pode adicionar funções à lista.</span><span class="sxs-lookup"><span data-stu-id="8f39f-194">It can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

<span data-ttu-id="8f39f-195">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **FunctionsToExport** com um valor de `*` (All), o que significa que todas as funções definidas no módulo serão exportadas pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-195">If you omit this parameter, `New-ModuleManifest` creates an **FunctionsToExport** key with a value of `*` (all), meaning that all functions defined in the module are exported by the manifest.</span></span>

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

### <span data-ttu-id="8f39f-196">-GUID</span><span class="sxs-lookup"><span data-stu-id="8f39f-196">-Guid</span></span>

<span data-ttu-id="8f39f-197">Especifica um identificador exclusivo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-197">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="8f39f-198">O **GUID** pode ser usado para distinguir entre módulos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="8f39f-198">The **GUID** can be used to distinguish among modules with the same name.</span></span>

<span data-ttu-id="8f39f-199">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **GUID** no manifesto e gerará um **GUID** para o valor.</span><span class="sxs-lookup"><span data-stu-id="8f39f-199">If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in the manifest and generates a **GUID** for the value.</span></span>

<span data-ttu-id="8f39f-200">Para criar um novo **GUID** no PowerShell, digite `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="8f39f-200">To create a new **GUID** in PowerShell, type `[guid]::NewGuid()`.</span></span>

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

### <span data-ttu-id="8f39f-201">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="8f39f-201">-HelpInfoUri</span></span>

<span data-ttu-id="8f39f-202">Especifica o endereço da Internet do arquivo XML HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-202">Specifies the internet address of the HelpInfo XML file for the module.</span></span> <span data-ttu-id="8f39f-203">Insira um Uniform Resource Identifier (URI) que comece com **http** ou **https**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-203">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="8f39f-204">O arquivo XML HelpInfo dá suporte ao recurso de ajuda atualizável que foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8f39f-204">The HelpInfo XML file supports the Updatable Help feature that was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="8f39f-205">Ele contém informações sobre o local dos arquivos de ajuda que podem ser baixados para o módulo e os números de versão dos arquivos de ajuda mais recentes para cada localidade com suporte.</span><span class="sxs-lookup"><span data-stu-id="8f39f-205">It contains information about the location of downloadable help files for the module and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="8f39f-206">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="8f39f-206">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="8f39f-207">Para obter informações sobre o arquivo XML HelpInfo, consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="8f39f-207">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="8f39f-208">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8f39f-208">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8f39f-209">-IconUri</span><span class="sxs-lookup"><span data-stu-id="8f39f-209">-IconUri</span></span>

<span data-ttu-id="8f39f-210">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-210">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="8f39f-211">O ícone especificado é exibido na página da Galeria da Web para o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-211">The specified icon is displayed on the gallery web page for the module.</span></span>

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

### <span data-ttu-id="8f39f-212">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="8f39f-212">-LicenseUri</span></span>

<span data-ttu-id="8f39f-213">Especifica a URL dos termos de licenciamento do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-213">Specifies the URL of licensing terms for the module.</span></span>

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

### <span data-ttu-id="8f39f-214">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="8f39f-214">-ModuleList</span></span>

<span data-ttu-id="8f39f-215">Lista todos os módulos incluídos neste módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-215">Lists all modules that are included in this module.</span></span>

<span data-ttu-id="8f39f-216">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-216">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="8f39f-217">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="8f39f-217">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="8f39f-218">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f39f-218">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="8f39f-219">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-219">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="8f39f-220">Os módulos listados no valor dessa chave não são processados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f39f-220">The modules that are listed in the value of this key aren't automatically processed.</span></span>

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

### <span data-ttu-id="8f39f-221">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="8f39f-221">-ModuleVersion</span></span>

<span data-ttu-id="8f39f-222">Especifica a versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-222">Specifies the module's version.</span></span>

<span data-ttu-id="8f39f-223">Esse parâmetro não é necessário, mas uma chave **ModuleVersion** é necessária no manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-223">This parameter isn't required, but a **ModuleVersion** key is required in the manifest.</span></span> <span data-ttu-id="8f39f-224">Se você omitir esse parâmetro, o `New-ModuleManifest` criará uma chave **ModuleVersion** com um valor de 1,0.</span><span class="sxs-lookup"><span data-stu-id="8f39f-224">If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion** key with a value of 1.0.</span></span>

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

### <span data-ttu-id="8f39f-225">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="8f39f-225">-NestedModules</span></span>

<span data-ttu-id="8f39f-226">Especifica módulos de script ( `.psm1` ) e módulos binários ( `.dll` ) que são importados para o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-226">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="8f39f-227">Os arquivos na chave **NestedModules** são executados na ordem em que estão listados no valor.</span><span class="sxs-lookup"><span data-stu-id="8f39f-227">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="8f39f-228">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-228">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="8f39f-229">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="8f39f-229">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="8f39f-230">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f39f-230">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="8f39f-231">Normalmente, módulos aninhados contêm comandos que o módulo raiz precisa para seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="8f39f-231">Typically, nested modules contain commands that the root module needs for its internal processing.</span></span>
<span data-ttu-id="8f39f-232">Por padrão, os comandos em módulos aninhados são exportados do estado de sessão do módulo para o estado de sessão do chamador, mas o módulo raiz pode restringir os comandos que ele exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-232">By default, the commands in nested modules are exported from the module's session state into the caller's session state, but the root module can restrict the commands that it exports.</span></span> <span data-ttu-id="8f39f-233">Por exemplo, usando um `Export-ModuleMember` comando.</span><span class="sxs-lookup"><span data-stu-id="8f39f-233">For example, by using an `Export-ModuleMember` command.</span></span>

<span data-ttu-id="8f39f-234">Os módulos aninhados no estado de sessão do módulo estão disponíveis para o módulo raiz, mas não são retornados por um `Get-Module` comando no estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="8f39f-234">Nested modules in the module session state are available to the root module, but they aren't returned by a `Get-Module` command in the caller's session state.</span></span>

<span data-ttu-id="8f39f-235">Os scripts ( `.ps1` ) listados na chave **NestedModules** são executados no estado de sessão do módulo, não no estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="8f39f-235">Scripts (`.ps1`) that are listed in the **NestedModules** key are run in the module's session state, not in the caller's session state.</span></span> <span data-ttu-id="8f39f-236">Para executar um script no estado de sessão do chamador, liste o nome do arquivo de script no valor da chave **ScriptsToProcess** do manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-236">To run a script in the caller's session state, list the script file name in the value of the **ScriptsToProcess** key in the manifest.</span></span>

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

### <span data-ttu-id="8f39f-237">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8f39f-237">-PassThru</span></span>

<span data-ttu-id="8f39f-238">Grava o manifesto do módulo resultante no console e cria um `.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-238">Writes the resulting module manifest to the console and creates a `.psd1` file.</span></span> <span data-ttu-id="8f39f-239">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="8f39f-239">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="8f39f-240">-Path</span><span class="sxs-lookup"><span data-stu-id="8f39f-240">-Path</span></span>

<span data-ttu-id="8f39f-241">Especifica o caminho e o nome de arquivo do novo manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-241">Specifies the path and file name of the new module manifest.</span></span> <span data-ttu-id="8f39f-242">Insira um caminho e um nome de arquivo com uma `.psd1` extensão de nome de arquivo, como `$pshome\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="8f39f-242">Enter a path and file name with a `.psd1` file name extension, such as `$pshome\Modules\MyModule\MyModule.psd1`.</span></span> <span data-ttu-id="8f39f-243">O parâmetro **path** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8f39f-243">The **Path** parameter is required.</span></span>

<span data-ttu-id="8f39f-244">Se você especificar o caminho para um arquivo existente, `New-ModuleManifest` o substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8f39f-244">If you specify the path to an existing file, `New-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="8f39f-245">O manifesto deve estar localizado no diretório do módulo e o nome do arquivo de manifesto deve ser o mesmo que o nome do diretório do módulo, mas com uma `.psd1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-245">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` file name extension.</span></span>

> [!NOTE]
> <span data-ttu-id="8f39f-246">Você não pode usar variáveis, como `$PSHOME` ou `$HOME` , em resposta a um prompt para um valor de parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-246">You cannot use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="8f39f-247">Para usar uma variável, inclua o parâmetro **Path** no comando.</span><span class="sxs-lookup"><span data-stu-id="8f39f-247">To use a variable, include the **Path** parameter in the command.</span></span>

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

### <span data-ttu-id="8f39f-248">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="8f39f-248">-PowerShellHostName</span></span>

<span data-ttu-id="8f39f-249">Especifica o nome do programa de host do PowerShell que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="8f39f-249">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="8f39f-250">Insira o nome do programa host, como **ISE do Windows PowerShell host** ou **ConsoleHost**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-250">Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost**.</span></span> <span data-ttu-id="8f39f-251">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-251">Wildcards aren't permitted.</span></span>

<span data-ttu-id="8f39f-252">Para localizar o nome de um programa de host, no programa, digite `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="8f39f-252">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="8f39f-253">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="8f39f-253">-PowerShellHostVersion</span></span>

<span data-ttu-id="8f39f-254">Especifica a versão mínima do programa de host do PowerShell que funciona com o módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-254">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="8f39f-255">Insira um número de versão, como 1.1.</span><span class="sxs-lookup"><span data-stu-id="8f39f-255">Enter a version number, such as 1.1.</span></span>

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

### <span data-ttu-id="8f39f-256">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="8f39f-256">-PowerShellVersion</span></span>

<span data-ttu-id="8f39f-257">Especifica a versão mínima do PowerShell que funciona com este módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-257">Specifies the minimum version of PowerShell that works with this module.</span></span> <span data-ttu-id="8f39f-258">Por exemplo, você pode inserir 1,0, 2,0 ou 3,0 como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f39f-258">For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value.</span></span>

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

### <span data-ttu-id="8f39f-259">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="8f39f-259">-PrivateData</span></span>

<span data-ttu-id="8f39f-260">Especifica os dados que são passados para o módulo quando ele é importado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-260">Specifies data that is passed to the module when it's imported.</span></span>

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

### <span data-ttu-id="8f39f-261">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="8f39f-261">-ProcessorArchitecture</span></span>

<span data-ttu-id="8f39f-262">Especifica a arquitetura do processador que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="8f39f-262">Specifies the processor architecture that the module requires.</span></span> <span data-ttu-id="8f39f-263">Os valores válidos são x86, AMD64, IA64, MSIL e nenhum (desconhecido ou não especificado).</span><span class="sxs-lookup"><span data-stu-id="8f39f-263">Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified).</span></span>

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

### <span data-ttu-id="8f39f-264">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="8f39f-264">-ProjectUri</span></span>

<span data-ttu-id="8f39f-265">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-265">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="8f39f-266">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="8f39f-266">-ReleaseNotes</span></span>

<span data-ttu-id="8f39f-267">Especifica notas de versão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-267">Specifies release notes.</span></span>

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

### <span data-ttu-id="8f39f-268">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="8f39f-268">-RequiredAssemblies</span></span>

<span data-ttu-id="8f39f-269">Especifica os arquivos de assembly ( `.dll` ) que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="8f39f-269">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="8f39f-270">Digite os nomes de arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="8f39f-270">Enter the assembly file names.</span></span>
<span data-ttu-id="8f39f-271">O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-271">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="8f39f-272">Use esse parâmetro para listar todos os assemblies exigidos pelo módulo, incluindo assemblies que devem ser carregados para atualizar quaisquer formatações ou arquivos de tipo listados nas chaves **FormatsToProcess** ou **TypesToProcess** , mesmo se esses assemblies também estiverem listados como módulos binários na chave **NestedModules**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-272">Use this parameter to list all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="8f39f-273">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="8f39f-273">-RequiredModules</span></span>

<span data-ttu-id="8f39f-274">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="8f39f-274">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="8f39f-275">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="8f39f-275">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="8f39f-276">Se os módulos necessários não estiverem disponíveis, o `Import-Module` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="8f39f-276">If the required modules aren't available, the `Import-Module` command fails.</span></span>

<span data-ttu-id="8f39f-277">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-277">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="8f39f-278">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="8f39f-278">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="8f39f-279">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f39f-279">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="8f39f-280">No PowerShell 2,0, o `Import-Module` não importa os módulos necessários automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f39f-280">In PowerShell 2.0, `Import-Module` doesn't import required modules automatically.</span></span> <span data-ttu-id="8f39f-281">Ele apenas verifica se os módulos necessários estão no estado da sessão global.</span><span class="sxs-lookup"><span data-stu-id="8f39f-281">It just verifies that the required modules are in the global session state.</span></span>

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

### <span data-ttu-id="8f39f-282">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="8f39f-282">-ScriptsToProcess</span></span>

<span data-ttu-id="8f39f-283">Especifica os arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-283">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="8f39f-284">Você pode usar esses scripts para preparar um ambiente, assim como você pode usar um script de logon.</span><span class="sxs-lookup"><span data-stu-id="8f39f-284">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="8f39f-285">Para especificar scripts que são executados no estado de sessão do módulo, use a chave **NestedModules**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-285">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="8f39f-286">-Marcas</span><span class="sxs-lookup"><span data-stu-id="8f39f-286">-Tags</span></span>

<span data-ttu-id="8f39f-287">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="8f39f-287">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="8f39f-288">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="8f39f-288">-TypesToProcess</span></span>

<span data-ttu-id="8f39f-289">Especifica os arquivos de tipo ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-289">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="8f39f-290">Quando você importa o módulo, o PowerShell executa o `Update-TypeData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="8f39f-290">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="8f39f-291">Como os arquivos de tipo não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-291">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="8f39f-292">-VariablesToExport</span><span class="sxs-lookup"><span data-stu-id="8f39f-292">-VariablesToExport</span></span>

<span data-ttu-id="8f39f-293">Especifica as variáveis que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="8f39f-293">Specifies the variables that the module exports.</span></span> <span data-ttu-id="8f39f-294">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f39f-294">Wildcards are permitted.</span></span>

<span data-ttu-id="8f39f-295">Você pode usar esse parâmetro para restringir as variáveis exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-295">You can use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="8f39f-296">Ele pode remover variáveis da lista de variáveis exportadas, mas não pode adicionar variáveis à lista.</span><span class="sxs-lookup"><span data-stu-id="8f39f-296">It can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

<span data-ttu-id="8f39f-297">Se você omitir esse parâmetro, `New-ModuleManifest` o criará uma chave **VariablesToExport** com um valor de `*` (All), o que significa que todas as variáveis definidas no módulo serão exportadas pelo manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-297">If you omit this parameter, `New-ModuleManifest` creates a **VariablesToExport** key with a value of `*` (all), meaning that all variables defined in the module are exported by the manifest.</span></span>

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

### <span data-ttu-id="8f39f-298">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="8f39f-298">-DefaultCommandPrefix</span></span>

<span data-ttu-id="8f39f-299">Especifica um prefixo que é anexado aos substantivos de todos os comandos no módulo quando eles são importados para uma sessão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-299">Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session.</span></span> <span data-ttu-id="8f39f-300">Insira uma cadeia de caracteres de prefixo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-300">Enter a prefix string.</span></span> <span data-ttu-id="8f39f-301">Prefixos evitam conflitos de nomes de comando em uma sessão de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f39f-301">Prefixes prevent command name conflicts in a user's session.</span></span>

<span data-ttu-id="8f39f-302">Os usuários do módulo podem substituir esse prefixo especificando o parâmetro de **prefixo** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f39f-302">Module users can override this prefix by specifying the **Prefix** parameter of the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="8f39f-303">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8f39f-303">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8f39f-304">-RootModule</span><span class="sxs-lookup"><span data-stu-id="8f39f-304">-RootModule</span></span>

<span data-ttu-id="8f39f-305">Especifica o arquivo primário ou raiz do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-305">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="8f39f-306">Insira o nome de arquivo de um script ( `.ps1` ), um módulo de script ( `.psm1` ), um manifesto de módulo ( `.psd1` ), um assembly ( `.dll` ), um arquivo XML de definição de cmdlet ( `.cdxml` ) ou um fluxo de trabalho ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="8f39f-306">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="8f39f-307">Quando o módulo é importado, os membros que são exportados do arquivo do módulo raiz são importados para o estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="8f39f-307">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="8f39f-308">Se um módulo tiver um arquivo de manifesto e nenhum arquivo raiz tiver sido designado na chave **RootModule** , o manifesto se tornará o arquivo primário do módulo e o módulo se tornará um módulo de manifesto (módulotype = manifesto).</span><span class="sxs-lookup"><span data-stu-id="8f39f-308">If a module has a manifest file and no root file was designated in the **RootModule** key, the manifest becomes the primary file for the module, and the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="8f39f-309">Para exportar membros de `.psm1` ou `.dll` arquivos em um módulo que tenha um manifesto, os nomes desses arquivos devem ser especificados nos valores das chaves **RootModule** ou **NestedModules** no manifesto.</span><span class="sxs-lookup"><span data-stu-id="8f39f-309">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="8f39f-310">Caso contrário, seus membros não serão exportados.</span><span class="sxs-lookup"><span data-stu-id="8f39f-310">Otherwise, their members aren't exported.</span></span>

> [!NOTE]
> <span data-ttu-id="8f39f-311">No PowerShell 2,0, essa chave foi chamada de **ModuleToProcess**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-311">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span> <span data-ttu-id="8f39f-312">Você pode usar o nome do parâmetro **RootModule** ou seu alias **ModuleToProcess** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-312">You can use the **RootModule** parameter name or its **ModuleToProcess** alias.</span></span>

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

### <span data-ttu-id="8f39f-313">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8f39f-313">-WhatIf</span></span>

<span data-ttu-id="8f39f-314">Mostra o que aconteceria se `New-ModuleManifest` for executado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-314">Shows what would happen if `New-ModuleManifest` runs.</span></span> <span data-ttu-id="8f39f-315">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-315">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8f39f-316">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8f39f-316">CommonParameters</span></span>

<span data-ttu-id="8f39f-317">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f39f-317">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f39f-318">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f39f-318">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f39f-319">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8f39f-319">INPUTS</span></span>

### <span data-ttu-id="8f39f-320">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8f39f-320">None</span></span>

<span data-ttu-id="8f39f-321">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f39f-321">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8f39f-322">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8f39f-322">OUTPUTS</span></span>

### <span data-ttu-id="8f39f-323">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="8f39f-323">None or System.String</span></span>

<span data-ttu-id="8f39f-324">Por padrão, o `New-ModuleManifest` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="8f39f-324">By default, `New-ModuleManifest` doesn't generate any output.</span></span> <span data-ttu-id="8f39f-325">No entanto, se você usar o parâmetro **PassThru** , ele gerará um objeto **System. String** que representa o manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-325">However, if you use the **PassThru** parameter, it generates a **System.String** object representing the module manifest.</span></span>

## <span data-ttu-id="8f39f-326">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8f39f-326">NOTES</span></span>

<span data-ttu-id="8f39f-327">`New-ModuleManifest` cria arquivos manifest ( `.psd1` ) de módulo codificados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8f39f-327">`New-ModuleManifest` creates module manifest (`.psd1`) files encoded as follows:</span></span>

- <span data-ttu-id="8f39f-328">O PowerShell 6,0 em execução no Windows usa **UTF16**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-328">PowerShell 6.0 running on Windows uses **UTF16**.</span></span>
- <span data-ttu-id="8f39f-329">O PowerShell 6,0 em execução em plataformas que não são do Windows usa **UTF8NoBOM**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-329">PowerShell 6.0 running on non-Windows platforms uses **UTF8NoBOM**.</span></span>
- <span data-ttu-id="8f39f-330">O PowerShell 6,1 e posterior em execução em plataformas Windows e não Windows usam **UTF8NoBOM**.</span><span class="sxs-lookup"><span data-stu-id="8f39f-330">PowerShell 6.1 and higher running on Windows and non-Windows platforms uses **UTF8NoBOM**.</span></span>

<span data-ttu-id="8f39f-331">Manifestos de módulo são geralmente opcionais.</span><span class="sxs-lookup"><span data-stu-id="8f39f-331">Module manifests are usually optional.</span></span> <span data-ttu-id="8f39f-332">No entanto, um manifesto de módulo é necessária para exportar um assembly instalado no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="8f39f-332">However, a module manifest is required to export an assembly that is installed in the global assembly cache.</span></span>

<span data-ttu-id="8f39f-333">Para adicionar ou alterar arquivos no `$pshome\Modules` diretório, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="8f39f-333">To add or change files in the `$pshome\Modules` directory, start PowerShell with the **Run as administrator** option.</span></span>

> [!NOTE]
> <span data-ttu-id="8f39f-334">A partir do PowerShell 6,2, o PowerShell tenta carregar todos os arquivos DLL listados na propriedade **FileList** do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-334">Beginning in PowerShell 6.2, PowerShell attempts to load all the DLL files listed in **FileList** property of the module manifest.</span></span> <span data-ttu-id="8f39f-335">As DLLs nativas estão no **FileList** falha ao carregar no processo e o erro é ignorado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-335">Native DLLs is in the **FileList** fail to load in the process and the error is ignored.</span></span> <span data-ttu-id="8f39f-336">Todas as DLLs gerenciadas são carregadas no processo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-336">All managed DLLs are loaded in the process.</span></span> <span data-ttu-id="8f39f-337">Esse comportamento foi removido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="8f39f-337">This behavior was removed in PowerShell 7.1.</span></span>

<span data-ttu-id="8f39f-338">No PowerShell 2,0, muitos parâmetros de `New-ModuleManifest` eram obrigatórios, embora não sejam necessários em um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-338">In PowerShell 2.0, many parameters of `New-ModuleManifest` were mandatory, even though they weren't required in a module manifest.</span></span> <span data-ttu-id="8f39f-339">A partir do PowerShell 3,0, somente o parâmetro **path** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8f39f-339">Beginning in PowerShell 3.0, only the **Path** parameter is mandatory.</span></span>

<span data-ttu-id="8f39f-340">Uma sessão é uma instância do ambiente de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f39f-340">A session is an instance of the PowerShell execution environment.</span></span> <span data-ttu-id="8f39f-341">Uma sessão pode ter um ou mais estados de sessão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-341">A session can have one or more session states.</span></span> <span data-ttu-id="8f39f-342">Por padrão, uma sessão tem apenas um estado de sessão global, mas cada módulo importado tem seu próprio estado de sessão.</span><span class="sxs-lookup"><span data-stu-id="8f39f-342">By default, a session has only a global session state, but each imported module has its own session state.</span></span> <span data-ttu-id="8f39f-343">Estados de sessão permitem que os comandos em um módulo sejam executados sem afetar o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="8f39f-343">Session states allow the commands in a module to run without affecting the global session state.</span></span>

<span data-ttu-id="8f39f-344">O estado de sessão do chamador é o estado da sessão no qual um módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="8f39f-344">The caller's session state is the session state into which a module is imported.</span></span> <span data-ttu-id="8f39f-345">Normalmente, ele se refere ao estado de sessão global, mas quando um módulo importa módulos aninhados, o chamador é o módulo e o estado de sessão do chamador é o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="8f39f-345">Typically, it refers to the global session state, but when a module imports nested modules, the caller is the module and the caller's session state is the module's session state.</span></span>

## <span data-ttu-id="8f39f-346">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8f39f-346">RELATED LINKS</span></span>

[<span data-ttu-id="8f39f-347">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="8f39f-347">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="8f39f-348">Get-Module</span><span class="sxs-lookup"><span data-stu-id="8f39f-348">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="8f39f-349">Import-Module</span><span class="sxs-lookup"><span data-stu-id="8f39f-349">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="8f39f-350">New-Module</span><span class="sxs-lookup"><span data-stu-id="8f39f-350">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="8f39f-351">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="8f39f-351">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="8f39f-352">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="8f39f-352">Test-ModuleManifest</span></span>](Test-ModuleManifest.md)

[<span data-ttu-id="8f39f-353">about_Modules</span><span class="sxs-lookup"><span data-stu-id="8f39f-353">about_Modules</span></span>](./About/about_Modules.md)
