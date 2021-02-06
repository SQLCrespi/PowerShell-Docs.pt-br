---
description: Edições diferentes do PowerShell são executadas em diferentes tempos de execução subjacentes.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 3b1b938874b36919a1a0627f3b492cbc961e4a2f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595375"
---
# <a name="about-powershell-editions"></a><span data-ttu-id="411cf-103">Sobre as edições do PowerShell</span><span class="sxs-lookup"><span data-stu-id="411cf-103">About PowerShell Editions</span></span>

## <a name="short-description"></a><span data-ttu-id="411cf-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="411cf-104">Short Description</span></span>
<span data-ttu-id="411cf-105">Edições diferentes do PowerShell são executadas em diferentes tempos de execução subjacentes.</span><span class="sxs-lookup"><span data-stu-id="411cf-105">Different editions of PowerShell run on different underlying runtimes.</span></span>

## <a name="long-description"></a><span data-ttu-id="411cf-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="411cf-106">Long Description</span></span>

<span data-ttu-id="411cf-107">Do PowerShell 5,1, há várias *edições* do PowerShell que são executadas em um tempo de execução do .net diferente.</span><span class="sxs-lookup"><span data-stu-id="411cf-107">From PowerShell 5.1, there are multiple *editions* of PowerShell that each run on a different .NET runtime.</span></span> <span data-ttu-id="411cf-108">A partir do PowerShell 6,2, há duas edições do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="411cf-108">As of PowerShell 6.2 there are two editions of PowerShell:</span></span>

- <span data-ttu-id="411cf-109">**Desktop**, que é executado em .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="411cf-109">**Desktop**, which runs on .NET Framework.</span></span> <span data-ttu-id="411cf-110">O PowerShell 4 e inferior, bem como o PowerShell 5,1 em edições completas do Windows, como Windows desktop, Windows Server, Windows Server Core e a maioria dos outros sistemas operacionais Windows são Desktop Edition.</span><span class="sxs-lookup"><span data-stu-id="411cf-110">PowerShell 4 and below, as well as PowerShell 5.1 on full-featured Windows editions like Windows Desktop, Windows Server, Windows Server Core and most other Windows operating systems are Desktop edition.</span></span>
  <span data-ttu-id="411cf-111">Esta é a edição original do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="411cf-111">This is the original PowerShell edition.</span></span>
- <span data-ttu-id="411cf-112">**Núcleo**, que é executado no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="411cf-112">**Core**, which runs on .NET Core.</span></span> <span data-ttu-id="411cf-113">PowerShell 6,0 e superior, bem como o PowerShell 5,1 em algumas edições de superfície reduzida do Windows, como o Windows nano Server e o Windows IoT, onde .NET Framework não está disponível.</span><span class="sxs-lookup"><span data-stu-id="411cf-113">PowerShell 6.0 and above, as well as PowerShell 5.1 on some reduced-footprint Windows editions such as Windows Nano Server and Windows IoT where .NET Framework is unavailable.</span></span>

<span data-ttu-id="411cf-114">Como a edição do PowerShell corresponde a seu tempo de execução do .NET, é o principal indicador da API do .NET e da compatibilidade do módulo do PowerShell; algumas APIs, tipos ou métodos do .NET não estão disponíveis em tempos de execução do .NET e isso afeta scripts e módulos do PowerShell que dependem deles.</span><span class="sxs-lookup"><span data-stu-id="411cf-114">Because the edition of PowerShell corresponds to its .NET runtime, it is the primary indicator of .NET API and PowerShell module compatibility; some .NET APIs, types or methods are not available in both .NET runtimes and this affects PowerShell scripts and modules that depend on them.</span></span>

## <a name="the-psedition-automatic-variable"></a><span data-ttu-id="411cf-115">A `$PSEdition` variável automática</span><span class="sxs-lookup"><span data-stu-id="411cf-115">The `$PSEdition` automatic variable</span></span>

<span data-ttu-id="411cf-116">No PowerShell 5,1 e superior, você pode descobrir qual edição está executando com a `$PSEdition` variável automática:</span><span class="sxs-lookup"><span data-stu-id="411cf-116">In PowerShell 5.1 and above, you can find out what edition you are running with the `$PSEdition` automatic variable:</span></span>

```powershell
$PSEdition
```

```Output
Core
```

<span data-ttu-id="411cf-117">No PowerShell 4 e abaixo, essa variável não existe.</span><span class="sxs-lookup"><span data-stu-id="411cf-117">In PowerShell 4 and below, this variable does not exist.</span></span> <span data-ttu-id="411cf-118">`$PSEdition` ser nulo deve ser tratado da mesma forma que o valor `Desktop` .</span><span class="sxs-lookup"><span data-stu-id="411cf-118">`$PSEdition` being null should be treated as the same as having the value `Desktop`.</span></span>

### <a name="edition-in-psversiontable"></a><span data-ttu-id="411cf-119">Edição no `$PSVersionTable`</span><span class="sxs-lookup"><span data-stu-id="411cf-119">Edition in `$PSVersionTable`</span></span>

<span data-ttu-id="411cf-120">A `$PSVersionTable` variável automática também tem informações de edição no PowerShell 5,1 e superior:</span><span class="sxs-lookup"><span data-stu-id="411cf-120">The `$PSVersionTable` automatic variable also has edition information in PowerShell 5.1 and above:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

<span data-ttu-id="411cf-121">O `PSEdition` campo terá o mesmo valor que a `$PSEdition` variável automática.</span><span class="sxs-lookup"><span data-stu-id="411cf-121">The `PSEdition` field will have the same value as the `$PSEdition` automatic variable.</span></span>

## <a name="the-compatiblepseditions-module-manifest-field"></a><span data-ttu-id="411cf-122">O `CompatiblePSEditions` campo manifesto do módulo</span><span class="sxs-lookup"><span data-stu-id="411cf-122">The `CompatiblePSEditions` module manifest field</span></span>

<span data-ttu-id="411cf-123">Os módulos do PowerShell podem declarar em quais edições do PowerShell eles são compatíveis usando o `CompatiblePSEditions` campo do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="411cf-123">PowerShell modules can declare what editions of PowerShell they are compatible with using the `CompatiblePSEditions` field of the module manifest.</span></span>

<span data-ttu-id="411cf-124">Por exemplo, um manifesto de módulo declarando a compatibilidade com as `Desktop` `Core` edições e do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="411cf-124">For example, a module manifest declaring compatibility with both `Desktop` and `Core` editions of PowerShell:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

<span data-ttu-id="411cf-125">Um exemplo de um manifesto de módulo com apenas `Desktop` compatibilidade:</span><span class="sxs-lookup"><span data-stu-id="411cf-125">An example of a module manifest with only `Desktop` compatibility:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

<span data-ttu-id="411cf-126">Omitir o `CompatiblePSEditions` campo de um manifesto de módulo terá o mesmo efeito que defini-lo como `Desktop` , já que os módulos criados antes desse campo foi introduzido foram gravados implicitamente para esta edição.</span><span class="sxs-lookup"><span data-stu-id="411cf-126">Omitting the `CompatiblePSEditions` field from a module manifest will have the same effect as setting it to `Desktop`, since modules created before this field was introduced were implicitly written for this edition.</span></span>

<span data-ttu-id="411cf-127">Para módulos não fornecidos como parte do Windows (ou seja, módulos que você escreve ou instala da Galeria), esse campo é apenas informativo; O PowerShell não altera o comportamento com base no `CompatiblePSEditions` campo, mas o expõe no `PSModuleInfo` objeto (retornado por `Get-Module` ) para sua própria lógica:</span><span class="sxs-lookup"><span data-stu-id="411cf-127">For modules not shipped as part of Windows (i.e. modules you write or install from the gallery), this field is informational only; PowerShell does not change behavior based on the `CompatiblePSEditions` field, but does expose it on the `PSModuleInfo` object (returned by `Get-Module`) for your own logic:</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> <span data-ttu-id="411cf-128">O `CompatiblePSEditions` campo de módulo só é compatível com o PowerShell 5,1 e superior.</span><span class="sxs-lookup"><span data-stu-id="411cf-128">The `CompatiblePSEditions` module field is only compatible with PowerShell 5.1 and above.</span></span>
> <span data-ttu-id="411cf-129">A inclusão deste campo fará com que um módulo seja incompatível com o PowerShell 4 e inferior.</span><span class="sxs-lookup"><span data-stu-id="411cf-129">Including this field will cause a module to be incompatible with PowerShell 4 and below.</span></span>
> <span data-ttu-id="411cf-130">Como o campo é puramente informativo, ele pode ser omitido com segurança em versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="411cf-130">Since the field is purely informational, it can be safely omitted in later PowerShell versions.</span></span>

<span data-ttu-id="411cf-131">No PowerShell 6,1, `Get-Module -ListAvailable` o formatador foi atualizado para exibir a compatibilidade de edição de cada módulo:</span><span class="sxs-lookup"><span data-stu-id="411cf-131">In PowerShell 6.1, `Get-Module -ListAvailable` has had its formatter updated to display the edition-compatibility of each module:</span></span>

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Script     1.4.0      Az                                  Core,Desk
Script     1.3.1      Az.Accounts                         Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                              Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                              Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer                    Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility                Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a><span data-ttu-id="411cf-132">Edição-compatibilidade para módulos que são fornecidos como parte do Windows</span><span class="sxs-lookup"><span data-stu-id="411cf-132">Edition-compatibility for modules that ship as part of Windows</span></span>

<span data-ttu-id="411cf-133">Para módulos que são fornecidos como parte do Windows (ou são instalados como parte de uma função ou recurso), o PowerShell 6,1 e superior tratam o `CompatiblePSEditions` campo de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="411cf-133">For modules that come as part of Windows (or are installed as part of a role or feature), PowerShell 6.1 and above treat the `CompatiblePSEditions` field differently.</span></span> <span data-ttu-id="411cf-134">Esses módulos são encontrados no diretório de módulos do sistema do Windows PowerShell ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).</span><span class="sxs-lookup"><span data-stu-id="411cf-134">Such modules are found in the Windows PowerShell system modules directory (`%windir%\System\WindowsPowerShell\v1.0\Modules`).</span></span>

<span data-ttu-id="411cf-135">Para módulos carregados de ou encontrados neste diretório, o PowerShell 6,1 e superior usa o `CompatiblePSEditions` campo para determinar se o módulo será compatível com a sessão atual e se comporta de acordo.</span><span class="sxs-lookup"><span data-stu-id="411cf-135">For modules loaded from or found in this directory, PowerShell 6.1 and above uses the `CompatiblePSEditions` field to determine whether the module will be compatible with the current session and behaves accordingly.</span></span>

<span data-ttu-id="411cf-136">Quando `Import-Module` for usado, um módulo sem `Core` no `CompatiblePSEditions` não será importado e um erro será exibido:</span><span class="sxs-lookup"><span data-stu-id="411cf-136">When `Import-Module` is used, a module without `Core` in `CompatiblePSEditions` will not be imported and an error will be displayed:</span></span>

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'. Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to ignore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsTransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Commands.ImportModuleCommand
```

<span data-ttu-id="411cf-137">Quando `Get-Module -ListAvailable` é usado, os módulos sem `Core` no `CompatiblePSEditions` não serão exibidos:</span><span class="sxs-lookup"><span data-stu-id="411cf-137">When `Get-Module -ListAvailable` is used, modules without `Core` in `CompatiblePSEditions` will not be displayed:</span></span>

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

<span data-ttu-id="411cf-138">Em ambos os casos, o `-SkipEditionCheck` parâmetro switch pode ser usado para substituir esse comportamento:</span><span class="sxs-lookup"><span data-stu-id="411cf-138">In both cases, the `-SkipEditionCheck` switch parameter can be used to override this behavior:</span></span>

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.0.0    BitsTransfer                        Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...

```

> [!WARNING]
> <span data-ttu-id="411cf-139">`Import-Module -SkipEditionCheck` pode parecer ter sucesso para um módulo, mas usar esse módulo executa o risco de encontrar uma incompatibilidade posteriormente; ao carregar o módulo inicialmente, um comando pode chamar uma API incompatível e fazer uma falha espontaneamente.</span><span class="sxs-lookup"><span data-stu-id="411cf-139">`Import-Module -SkipEditionCheck` may appear to succeed for a module, but using that module runs the risk of encountering an incompatibility later on; while loading the module initially succeeds, a command may later call an incompatible API and fail spontaneously.</span></span>

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a><span data-ttu-id="411cf-140">Criando módulos do PowerShell para compatibilidade cruzada de edição</span><span class="sxs-lookup"><span data-stu-id="411cf-140">Authoring PowerShell modules for edition cross-compatibility</span></span>

<span data-ttu-id="411cf-141">Ao gravar um módulo do PowerShell para direcionar as duas `Desktop` `Core` edições do PowerShell, há coisas que você pode fazer para garantir a compatibilidade entre as edições.</span><span class="sxs-lookup"><span data-stu-id="411cf-141">When writing a PowerShell module to target both `Desktop` and `Core` editions of PowerShell, there are things you can do to ensure cross-edition compatibility.</span></span>

<span data-ttu-id="411cf-142">A única maneira verdadeira de confirmar e validar continuamente a compatibilidade no entanto é gravar testes para seu script ou módulo e executá-los em todas as versões e edições do PowerShell com as quais você precisa de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="411cf-142">The only true way to confirm and continually validate compatibility however is to write tests for your script or module and run them on all versions and editions of PowerShell you need compatibility with.</span></span> <span data-ttu-id="411cf-143">Uma estrutura de teste recomendada para isso é [Pester][].</span><span class="sxs-lookup"><span data-stu-id="411cf-143">A recommended testing framework for this is [Pester][].</span></span>

### <a name="powershell-script"></a><span data-ttu-id="411cf-144">Script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="411cf-144">PowerShell script</span></span>

<span data-ttu-id="411cf-145">Como uma linguagem, o PowerShell funciona da mesma forma entre edições; são os cmdlets, módulos e APIs do .NET que você usa que são afetados pela compatibilidade de edição.</span><span class="sxs-lookup"><span data-stu-id="411cf-145">As a language, PowerShell works the same between editions; it is the cmdlets, modules and .NET APIs you use that are affected by edition compatibility.</span></span>

<span data-ttu-id="411cf-146">Em geral, os scripts que funcionam no PowerShell 6,1 e acima funcionarão com o Windows PowerShell 5,1, mas há algumas exceções.</span><span class="sxs-lookup"><span data-stu-id="411cf-146">Generally, scripts that work in PowerShell 6.1 and above will work with Windows PowerShell 5.1, but there are some exceptions.</span></span>

<span data-ttu-id="411cf-147">A versão 1.18.0 módulo [PSScriptAnalyzer][] tem regras como [`PSUseCompatibleCommands`][] e [`PSUseCompatibleTypes`][] que são capazes de detectar o uso possivelmente incompatível de comandos e APIs .net em scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="411cf-147">Version 1.18.0 [PSScriptAnalyzer][] module has rules like [`PSUseCompatibleCommands`][] and [`PSUseCompatibleTypes`][] that are able to detect possibly incompatible usage of commands and .NET APIs in PowerShell scripts.</span></span>

### <a name="net-assemblies"></a><span data-ttu-id="411cf-148">Assemblies .NET</span><span class="sxs-lookup"><span data-stu-id="411cf-148">.NET assemblies</span></span>

<span data-ttu-id="411cf-149">Se você estiver escrevendo um módulo binário ou um módulo que incorpora os assemblies (DLLs) do .NET gerados a partir do código-fonte, você deve compilar em relação ao [.net Standard][] e ao [PowerShell Standard][] para validação de compatibilidade de tempo de compilação do .net e da compatibilidade de API do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="411cf-149">If you are writing a binary module or a module that incorporates .NET assemblies (DLLs) generated from source code, you should compile against [.NET Standard][] and [PowerShell Standard][] for compile-time compatibility validation of .NET and PowerShell API compatibility.</span></span>

<span data-ttu-id="411cf-150">Embora essas bibliotecas possam verificar alguma compatibilidade no tempo de compilação, elas não poderão capturar possíveis diferenças comportamentais entre as edições.</span><span class="sxs-lookup"><span data-stu-id="411cf-150">Although these libraries are able to check some compatibility at compile time, they won't be able to catch possible behavioral differences between editions.</span></span> <span data-ttu-id="411cf-151">Para isso, você ainda deve escrever testes.</span><span class="sxs-lookup"><span data-stu-id="411cf-151">For this you must still write tests.</span></span>

## <a name="see-also"></a><span data-ttu-id="411cf-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="411cf-152">See also</span></span>

- [<span data-ttu-id="411cf-153">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="411cf-153">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="411cf-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="411cf-154">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="411cf-155">Get-Module</span><span class="sxs-lookup"><span data-stu-id="411cf-155">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)
- [<span data-ttu-id="411cf-156">Módulos com as edições compatíveis do PowerShell</span><span class="sxs-lookup"><span data-stu-id="411cf-156">Modules with compatible PowerShell Editions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
['PSUseCompatibleCommands']: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[`PSUseCompatibleCommands`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
['PSUseCompatibleTypes']: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[`PSUseCompatibleTypes`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[Padrão do PowerShell]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
