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
# <a name="modules-with-compatible-powershell-editions"></a>Módulos com as edições compatíveis do PowerShell

Da versão 5.1 em diante, o PowerShell está disponível em diferentes edições, que denotam diferentes conjuntos de recursos e compatibilidades de plataforma.

- **Desktop Edition:** Baseado no .NET Framework, aplica-se ao Windows PowerShell v4.0 e anteriores, bem como o Windows PowerShell 5.1 na área de trabalho do Windows, Windows Server, Windows Server Core e a maioria das outras edições do Windows.
- **Core Edition:** Baseado no .NET Core, aplica-se ao PowerShell Core 6.0 e posteriores, bem como ao Windows PowerShell 5.1 no volume de memória reduzido das edições do Windows, como Windows IoT e Windows Nanoserver.

Para saber mais sobre as edições do PowerShell, confira [about_PowerShell_Editions][].

## <a name="declaring-compatible-editions"></a>Declaração de edições compatíveis

Os autores de módulo podem declarar os módulos como compatíveis com uma ou mais edições do PowerShell usando a chave de manifesto do módulo `CompatiblePSEditions`. Essa chave só tem suporte no PowerShell 5.1 ou posterior.

> [!NOTE]
> Quando um manifesto de módulo é especificado com a chave `CompatiblePSEditions` ou usa a variável `$PSEdition`, ele não pode ser importado no PowerShell v4 ou inferior.

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

Ao obter uma lista de módulos disponíveis, você pode filtrar a lista por edição do PowerShell.

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

Do PowerShell 6 em diante, o valor de `CompatiblePSEditions` é usado para decidir se um módulo é compatível quando os módulos são importados de `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.
Esse comportamento aplica-se somente ao Windows. Fora desse cenário, o valor é usado somente como metadados.

## <a name="finding-compatible-modules"></a>Como localizar módulos compatíveis

Os usuários da Galeria do PowerShell podem encontrar a lista de módulos com suporte em uma Edição do PowerShell específica usando as marcas **PSEdition_Desktop** e **PSEdition_Core**.

Considera-se que os módulos sem as marcas **PSEdition_Desktop** e **PSEdition_Core** funcionam bem nas edições do PowerShell Desktop.

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a>Direcionamento para várias edições

Os autores de módulo podem publicar um único módulo destinado a uma ou ambas as edições do PowerShell (Desktop e Core).

Um único módulo pode funcionar nas edições Desktop e Core e, nesse módulo, o autor precisa adicionar a lógica necessária no RootModule ou no manifesto do módulo usando a variável `$PSEdition`. Os módulos podem ter dois conjuntos de DLLs compiladas direcionadas para **CoreCLR** e **FullCLR**. Aqui estão as opções de empacotamento com lógica para carregar as DLLs apropriadas.

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a>Opção 1: empacotando um módulo para o direcionamento de várias versões e várias edições do PowerShell

Conteúdo de Pastas do Módulo

- Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- PSScriptAnalyzer.psd1
- PSScriptAnalyzer.psm1
- ScriptAnalyzer.format.ps1xml
- ScriptAnalyzer.types.ps1xml
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- en-US\about_PSScriptAnalyzer.help.txt
- en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- Settings\CmdletDesign.psd1
- Settings\DSC.psd1
- Settings\ScriptFunctions.psd1
- Settings\ScriptingStyle.psd1
- Settings\ScriptSecurity.psd1

Conteúdo do arquivo `PSScriptAnalyzer.psd1`

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

Abaixo, a lógica carrega os assemblies necessários, dependendo da edição atual ou da versão.

Conteúdo do arquivo `PSScriptAnalyzer.psm1`:

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

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a>Opção 2: usar a variável $PSEdition no arquivo PSD1 para carregar as DLLs apropriadas

No PS 5.1 ou mais recente, a variável global `$PSEdition` é permitida no arquivo de manifesto do módulo. Usando essa variável, autor de módulo pode especificar os valores condicionais no arquivo de manifesto de módulo. A variável `$PSEdition` pode ser referenciada no modo de linguagem restrita ou em uma seção de Dados.

Arquivo de manifesto de módulo de exemplo com a chave `CompatiblePSEditions`.

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

Conteúdos do módulo

- ModuleWithEditions\ModuleWithEditions.psd1
- ModuleWithEditions\clr\MyFullClrNM1.dll
- ModuleWithEditions\clr\MyFullClrNM2.dll
- ModuleWithEditions\clr\MyFullClrRM.dll
- ModuleWithEditions\coreclr\MyCoreClrNM1.dll
- ModuleWithEditions\coreclr\MyCoreClrNM2.dll
- ModuleWithEditions\coreclr\MyCoreClrRM.dll

## <a name="more-details"></a>Mais detalhes

[Scripts com PSEditions](script-psedition-support.md)

[Suporte do PSEditions na PowerShellGallery](../how-to/finding-packages/searching-by-compatibility.md)

[Atualizar o manifesto de módulo](/powershell/module/powershellget/update-modulemanifest)

[about_PowerShell_Editions][]

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
