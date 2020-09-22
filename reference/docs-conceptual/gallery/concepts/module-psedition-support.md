---
ms.date: 06/10/2020
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Módulos com as edições compatíveis do PowerShell
ms.openlocfilehash: 522493714916e9fd21f67a6e7bc2cfb165041807
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671403"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="11987-103">Módulos com as edições compatíveis do PowerShell</span><span class="sxs-lookup"><span data-stu-id="11987-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="11987-104">Da versão 5.1 em diante, o PowerShell está disponível em diferentes edições, que denotam diferentes conjuntos de recursos e compatibilidades de plataforma.</span><span class="sxs-lookup"><span data-stu-id="11987-104">Starting with version 5.1, PowerShell is available in different editions, which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="11987-105">**Desktop Edition:** Baseado no .NET Framework, aplica-se ao Windows PowerShell v4.0 e anteriores, bem como o Windows PowerShell 5.1 na área de trabalho do Windows, Windows Server, Windows Server Core e a maioria das outras edições do Windows.</span><span class="sxs-lookup"><span data-stu-id="11987-105">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell v4.0 and below as well as Windows PowerShell 5.1 on Windows Desktop, Windows Server, Windows Server Core and most other Windows editions.</span></span>
- <span data-ttu-id="11987-106">**Core Edition:** Baseado no .NET Core, aplica-se ao PowerShell Core 6.0 e posteriores, bem como ao Windows PowerShell 5.1 no volume de memória reduzido das edições do Windows, como Windows IoT e Windows Nanoserver.</span><span class="sxs-lookup"><span data-stu-id="11987-106">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above as well as Windows PowerShell 5.1 on reduced footprint Windows Editions such as Windows IoT and Windows Nanoserver.</span></span>

<span data-ttu-id="11987-107">Para saber mais sobre as edições do PowerShell, confira [about_PowerShell_Editions][].</span><span class="sxs-lookup"><span data-stu-id="11987-107">For more information on PowerShell editions, see [about_PowerShell_Editions][].</span></span>

## <a name="declaring-compatible-editions"></a><span data-ttu-id="11987-108">Declaração de edições compatíveis</span><span class="sxs-lookup"><span data-stu-id="11987-108">Declaring compatible editions</span></span>

<span data-ttu-id="11987-109">Os autores de módulo podem declarar os módulos como compatíveis com uma ou mais edições do PowerShell usando a chave de manifesto do módulo `CompatiblePSEditions`.</span><span class="sxs-lookup"><span data-stu-id="11987-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the `CompatiblePSEditions` module manifest key.</span></span> <span data-ttu-id="11987-110">Essa chave só tem suporte no PowerShell 5.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="11987-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="11987-111">Quando um manifesto de módulo é especificado com a chave `CompatiblePSEditions` ou usa a variável `$PSEdition`, ele não pode ser importado no PowerShell v4 ou inferior.</span><span class="sxs-lookup"><span data-stu-id="11987-111">Once a module manifest is specified with the `CompatiblePSEditions` key or uses the `$PSEdition` variable, it can not be imported on PowerShell v4 or lower.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```Output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="11987-112">Ao obter uma lista de módulos disponíveis, você pode filtrar a lista por edição do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11987-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules

ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```Output
Desktop
Core
```

<span data-ttu-id="11987-113">Do PowerShell 6 em diante, o valor de `CompatiblePSEditions` é usado para decidir se um módulo é compatível quando os módulos são importados de `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span><span class="sxs-lookup"><span data-stu-id="11987-113">Beginning in PowerShell 6, the `CompatiblePSEditions` value is used to decide if a module is compatible when modules are imported from `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span></span>
<span data-ttu-id="11987-114">Esse comportamento aplica-se somente ao Windows.</span><span class="sxs-lookup"><span data-stu-id="11987-114">This behavior only applies to Windows.</span></span> <span data-ttu-id="11987-115">Fora desse cenário, o valor é usado somente como metadados.</span><span class="sxs-lookup"><span data-stu-id="11987-115">Outside of this scenario, the value is only used as metadata.</span></span>

## <a name="finding-compatible-modules"></a><span data-ttu-id="11987-116">Como localizar módulos compatíveis</span><span class="sxs-lookup"><span data-stu-id="11987-116">Finding compatible modules</span></span>

<span data-ttu-id="11987-117">Os usuários da Galeria do PowerShell podem encontrar a lista de módulos com suporte em uma Edição do PowerShell específica usando as marcas **PSEdition_Desktop** e **PSEdition_Core**.</span><span class="sxs-lookup"><span data-stu-id="11987-117">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags **PSEdition_Desktop** and **PSEdition_Core**.</span></span>

<span data-ttu-id="11987-118">Considera-se que os módulos sem as marcas **PSEdition_Desktop** e **PSEdition_Core** funcionam bem nas edições do PowerShell Desktop.</span><span class="sxs-lookup"><span data-stu-id="11987-118">Modules without **PSEdition_Desktop** and **PSEdition_Core** tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="11987-119">Direcionamento para várias edições</span><span class="sxs-lookup"><span data-stu-id="11987-119">Targeting multiple editions</span></span>

<span data-ttu-id="11987-120">Os autores de módulo podem publicar um único módulo destinado a uma ou ambas as edições do PowerShell (Desktop e Core).</span><span class="sxs-lookup"><span data-stu-id="11987-120">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="11987-121">Um único módulo pode funcionar nas edições Desktop e Core e, nesse módulo, o autor precisa adicionar a lógica necessária no RootModule ou no manifesto do módulo usando a variável `$PSEdition`.</span><span class="sxs-lookup"><span data-stu-id="11987-121">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using `$PSEdition` variable.</span></span> <span data-ttu-id="11987-122">Os módulos podem ter dois conjuntos de DLLs compiladas direcionadas para **CoreCLR** e **FullCLR**.</span><span class="sxs-lookup"><span data-stu-id="11987-122">Modules can have two sets of compiled DLLs targeting both **CoreCLR** and **FullCLR**.</span></span> <span data-ttu-id="11987-123">Aqui estão as opções de empacotamento com lógica para carregar as DLLs apropriadas.</span><span class="sxs-lookup"><span data-stu-id="11987-123">Here are the packaging options with logic for loading proper DLLs.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="11987-124">Opção 1: empacotando um módulo para o direcionamento de várias versões e várias edições do PowerShell</span><span class="sxs-lookup"><span data-stu-id="11987-124">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="11987-125">Conteúdo de Pastas do Módulo</span><span class="sxs-lookup"><span data-stu-id="11987-125">Module folder contents</span></span>

- <span data-ttu-id="11987-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="11987-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="11987-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="11987-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="11987-128">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-128">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="11987-129">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="11987-129">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="11987-130">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="11987-130">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="11987-131">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="11987-131">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="11987-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="11987-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="11987-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="11987-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="11987-134">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="11987-134">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="11987-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="11987-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="11987-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="11987-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="11987-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="11987-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="11987-138">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-138">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="11987-139">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-139">Settings\DSC.psd1</span></span>
- <span data-ttu-id="11987-140">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-140">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="11987-141">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-141">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="11987-142">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-142">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="11987-143">Conteúdo do arquivo `PSScriptAnalyzer.psd1`</span><span class="sxs-lookup"><span data-stu-id="11987-143">Contents of `PSScriptAnalyzer.psd1` file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

<span data-ttu-id="11987-144">Abaixo, a lógica carrega os assemblies necessários, dependendo da edição atual ou da versão.</span><span class="sxs-lookup"><span data-stu-id="11987-144">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="11987-145">Conteúdo do arquivo `PSScriptAnalyzer.psm1`:</span><span class="sxs-lookup"><span data-stu-id="11987-145">Contents of `PSScriptAnalyzer.psm1` file:</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0')
    {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}
```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a><span data-ttu-id="11987-146">Opção 2: usar a variável $PSEdition no arquivo PSD1 para carregar as DLLs apropriadas</span><span class="sxs-lookup"><span data-stu-id="11987-146">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs</span></span>

<span data-ttu-id="11987-147">No PS 5.1 ou mais recente, a variável global `$PSEdition` é permitida no arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="11987-147">In PS 5.1 or newer, `$PSEdition` global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="11987-148">Usando essa variável, autor de módulo pode especificar os valores condicionais no arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="11987-148">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="11987-149">A variável `$PSEdition` pode ser referenciada no modo de linguagem restrita ou em uma seção de Dados.</span><span class="sxs-lookup"><span data-stu-id="11987-149">`$PSEdition` variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="11987-150">Arquivo de manifesto de módulo de exemplo com a chave `CompatiblePSEditions`.</span><span class="sxs-lookup"><span data-stu-id="11987-150">Sample module manifest file with `CompatiblePSEditions` key.</span></span>

```powershell
@{
    # Script module or binary module file associated with this manifest.
    RootModule = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrRM.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrRM.dll'
    }

    # Supported PSEditions
    CompatiblePSEditions = 'Desktop', 'Core'

    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
    NestedModules = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrNM1.dll',
        'coreclr\MyCoreClrNM2.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrNM1.dll',
        'clr\MyFullClrNM2.dll'
    }
}
```

<span data-ttu-id="11987-151">Conteúdos do módulo</span><span class="sxs-lookup"><span data-stu-id="11987-151">Module contents</span></span>

- <span data-ttu-id="11987-152">ModuleWithEditions\ModuleWithEditions.psd1</span><span class="sxs-lookup"><span data-stu-id="11987-152">ModuleWithEditions\ModuleWithEditions.psd1</span></span>
- <span data-ttu-id="11987-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="11987-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span></span>
- <span data-ttu-id="11987-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="11987-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span></span>
- <span data-ttu-id="11987-155">ModuleWithEditions\clr\MyFullClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="11987-155">ModuleWithEditions\clr\MyFullClrRM.dll</span></span>
- <span data-ttu-id="11987-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="11987-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span></span>
- <span data-ttu-id="11987-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="11987-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span></span>
- <span data-ttu-id="11987-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="11987-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span></span>

## <a name="more-details"></a><span data-ttu-id="11987-159">Mais detalhes</span><span class="sxs-lookup"><span data-stu-id="11987-159">More details</span></span>

[<span data-ttu-id="11987-160">Scripts com PSEditions</span><span class="sxs-lookup"><span data-stu-id="11987-160">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="11987-161">Suporte do PSEditions na PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="11987-161">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="11987-162">Atualizar o manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="11987-162">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)

<span data-ttu-id="11987-163">[about_PowerShell_Editions][]</span><span class="sxs-lookup"><span data-stu-id="11987-163">[about_PowerShell_Editions][]</span></span>

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
