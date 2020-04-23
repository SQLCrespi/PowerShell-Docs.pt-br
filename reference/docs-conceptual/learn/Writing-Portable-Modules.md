---
ms.date: 01/10/2020
keywords: powershell, cmdlet
title: Gravação de módulos portáteis
ms.openlocfilehash: 124e6efadfd07b8c5214a5c0446b1589f7142388
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "76022250"
---
# <a name="portable-modules"></a><span data-ttu-id="48c3a-103">Módulos portáteis</span><span class="sxs-lookup"><span data-stu-id="48c3a-103">Portable Modules</span></span>

<span data-ttu-id="48c3a-104">O Windows PowerShell é escrito para [.NET Framework][] enquanto o PowerShell Core é escrito para [.NET Core][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-104">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="48c3a-105">Os módulos portáteis são módulos que funcionam no Windows PowerShell e no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="48c3a-105">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="48c3a-106">Embora o .NET Framework e .NET Core sejam altamente compatíveis, há diferenças entre os dois nas APIs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="48c3a-106">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="48c3a-107">Também há diferenças nas APIs disponíveis no Windows PowerShell e PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="48c3a-107">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="48c3a-108">Os módulos destinados ao uso em ambos os ambientes precisam levar essas diferenças em consideração.</span><span class="sxs-lookup"><span data-stu-id="48c3a-108">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="48c3a-109">Fazendo a portabilidade de um módulo existente</span><span class="sxs-lookup"><span data-stu-id="48c3a-109">Porting an Existing Module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="48c3a-110">Fazendo a portabilidade de um PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="48c3a-110">Porting a PSSnapIn</span></span>

<span data-ttu-id="48c3a-111">Os PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) não são aceitos no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="48c3a-111">PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="48c3a-112">No entanto, é comum converter um PSSnapIn em um módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48c3a-112">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="48c3a-113">Normalmente, o código de registro do PSSnapIn está em um único arquivo de origem de uma classe que deriva de [PSSnapIn][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-113">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span>
<span data-ttu-id="48c3a-114">Remova esse arquivo de origem do build; ele não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="48c3a-114">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="48c3a-115">Use [New-ModuleManifest][] para criar um novo manifesto de módulo que substitui a necessidade do código de registro do PSSnapIn.</span><span class="sxs-lookup"><span data-stu-id="48c3a-115">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="48c3a-116">Alguns dos valores do **PSSnapIn** (como **Descrição**) podem ser reutilizados no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="48c3a-116">Some of the values from the **PSSnapIn** (such as **Description**) can be reused within the module manifest.</span></span>

<span data-ttu-id="48c3a-117">A propriedade **RootModule** no manifesto do módulo deve ser definida como o nome do assembly (dll) que implementa os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="48c3a-117">The **RootModule** property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="48c3a-118">.NET Portability Analyzer (também conhecido como APIPort)</span><span class="sxs-lookup"><span data-stu-id="48c3a-118">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="48c3a-119">Para fazer a portabilidade de módulos escritos para o Windows PowerShell de modo que funcionem com o PowerShell Core, comece com o [.NET Portability Analyzer][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-119">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="48c3a-120">Execute essa ferramenta em seu assembly compilado para determinar se as APIs do .NET usadas no módulo são compatíveis com o .NET Framework, o .NET Core e outros runtimes do .NET.</span><span class="sxs-lookup"><span data-stu-id="48c3a-120">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="48c3a-121">A ferramenta sugere APIs alternativas, se houver.</span><span class="sxs-lookup"><span data-stu-id="48c3a-121">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="48c3a-122">Caso contrário, talvez você precise adicionar [verificações de runtime][] e restringir recursos não disponíveis em runtimes específicos.</span><span class="sxs-lookup"><span data-stu-id="48c3a-122">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="48c3a-123">Criando um novo módulo</span><span class="sxs-lookup"><span data-stu-id="48c3a-123">Creating a New Module</span></span>

<span data-ttu-id="48c3a-124">Se estiver criando um novo módulo, a recomendação é usar a [CLI do .NET][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-124">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="48c3a-125">Instalando o modelo de módulo padrão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="48c3a-125">Installing the PowerShell Standard Module Template</span></span>

<span data-ttu-id="48c3a-126">Depois que a CLI do .NET for instalada, instale uma biblioteca de modelos para gerar um módulo simples do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48c3a-126">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="48c3a-127">O módulo será compatível com Windows PowerShell, PowerShell Core, Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="48c3a-127">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="48c3a-128">O exemplo a seguir mostra como instalar o modelo:</span><span class="sxs-lookup"><span data-stu-id="48c3a-128">The following example shows how to install the template:</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                                         Short Name         Language          Tags
----------------------------------------------------------------------------------------------------------------------------
Console Application                               console            [C#], F#, VB      Common/Console
Class library                                     classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module                        psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a><span data-ttu-id="48c3a-129">Criando um novo projeto de módulo</span><span class="sxs-lookup"><span data-stu-id="48c3a-129">Creating a New Module Project</span></span>

<span data-ttu-id="48c3a-130">Depois que o modelo for instalado, é possível criar um novo projeto de módulo do PowerShell usando esse modelo.</span><span class="sxs-lookup"><span data-stu-id="48c3a-130">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="48c3a-131">Neste exemplo, o módulo de exemplo é chamado de 'myModule'.</span><span class="sxs-lookup"><span data-stu-id="48c3a-131">In this example, the sample module is called 'myModule'.</span></span>

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a><span data-ttu-id="48c3a-132">Criando o módulo</span><span class="sxs-lookup"><span data-stu-id="48c3a-132">Building the Module</span></span>

<span data-ttu-id="48c3a-133">Use comandos padrão da CLI do .NET para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="48c3a-133">Use standard .NET CLI commands to build the project.</span></span>

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a><span data-ttu-id="48c3a-134">Testando o módulo</span><span class="sxs-lookup"><span data-stu-id="48c3a-134">Testing the Module</span></span>

<span data-ttu-id="48c3a-135">Depois de criar o módulo, é possível importá-lo e executar o cmdlet de exemplo.</span><span class="sxs-lookup"><span data-stu-id="48c3a-135">After building the module, you can import it and execute the sample cmdlet.</span></span>

```powershell
ipmo .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
PS C:\Users\Steve\myModule> ipmo .\bin\Debug\netstandard2.0\myModule.dll
PS C:\Users\Steve\myModule> Test-SampleCmdlet -?

NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


PS C:\Users\Steve\myModule> Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat

FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

<span data-ttu-id="48c3a-136">As seções a seguir descrevem algumas das tecnologias usadas por esse modelo em detalhes.</span><span class="sxs-lookup"><span data-stu-id="48c3a-136">The following sections describe in detail some of the technologies used by this template.</span></span>

## <a name="net-standard-library"></a><span data-ttu-id="48c3a-137">Biblioteca .NET Standard</span><span class="sxs-lookup"><span data-stu-id="48c3a-137">.NET Standard Library</span></span>

<span data-ttu-id="48c3a-138">[.NET Standard][] é uma especificação formal de APIs do .NET que estão disponíveis em todas as implementações do .NET.</span><span class="sxs-lookup"><span data-stu-id="48c3a-138">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="48c3a-139">O código gerenciado que se destina ao .NET Standard funciona com as versões do .NET Framework e .NET Core compatíveis com essa versão do .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="48c3a-139">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="48c3a-140">Embora possa existir uma API no .NET Standard, a implementação da API no .NET Core pode gerar uma `PlatformNotSupportedException` no runtime. Portanto, para verificar a compatibilidade com o Windows PowerShell e o PowerShell Core, a prática recomendada é executar testes para seu módulo em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="48c3a-140">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="48c3a-141">Execute testes também no Linux e macOS se deseja usar seu módulo em mais de uma plataforma.</span><span class="sxs-lookup"><span data-stu-id="48c3a-141">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="48c3a-142">O direcionamento do .NET Standard ajuda a garantir que, à medida que o módulo evolui, as APIs incompatíveis não sejam acidentalmente introduzidas no módulo.</span><span class="sxs-lookup"><span data-stu-id="48c3a-142">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="48c3a-143">As incompatibilidades são descobertas no tempo de compilação, e não no de execução.</span><span class="sxs-lookup"><span data-stu-id="48c3a-143">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="48c3a-144">No entanto, não é obrigatório direcionar o .NET Standard para que um módulo funcione com o Windows PowerShell e o PowerShell Core, desde que você use APIs compatíveis.</span><span class="sxs-lookup"><span data-stu-id="48c3a-144">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="48c3a-145">A Linguagem Intermediária (IL) é compatível entre os dois runtimes.</span><span class="sxs-lookup"><span data-stu-id="48c3a-145">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="48c3a-146">Você pode visar o .NET Framework 4.6.1, que é compatível com o .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="48c3a-146">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="48c3a-147">Se você não usar APIs fora do .NET Standard 2.0, seu módulo funcionará com o PowerShell Core 6 sem recompilação.</span><span class="sxs-lookup"><span data-stu-id="48c3a-147">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

## <a name="powershell-standard-library"></a><span data-ttu-id="48c3a-148">Biblioteca Padrão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="48c3a-148">PowerShell Standard Library</span></span>

<span data-ttu-id="48c3a-149">A biblioteca [Padrão do PowerShell][] é uma especificação formal das APIs do PowerShell disponíveis em todas as versões superiores ou iguais à versão desse padrão.</span><span class="sxs-lookup"><span data-stu-id="48c3a-149">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="48c3a-150">Por exemplo, o [Padrão 5.1 do PowerShell][] é compatível com o Windows PowerShell 5.1 e PowerShell Core 6.0 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="48c3a-150">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="48c3a-151">É recomendável compilar seu módulo usando a Biblioteca Padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48c3a-151">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="48c3a-152">A biblioteca garante que as APIs estejam disponíveis e sejam implementadas no Windows PowerShell e no PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="48c3a-152">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="48c3a-153">O Padrão do PowerShell destina-se a sempre ser compatível com versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="48c3a-153">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="48c3a-154">Um módulo compilado com a Biblioteca Padrão 5.1 do PowerShell sempre será compatível com versões futuras do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48c3a-154">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

## <a name="module-manifest"></a><span data-ttu-id="48c3a-155">Manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="48c3a-155">Module Manifest</span></span>

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="48c3a-156">Indicando compatibilidade com o Windows PowerShell e o PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="48c3a-156">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="48c3a-157">Depois de confirmar que o módulo funciona com o Windows PowerShell e o PowerShell Core, o manifesto do módulo deve indicar explicitamente a compatibilidade usando a propriedade [CompatiblePSEditions][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-157">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="48c3a-158">Um valor `Desktop` significa que o módulo é compatível com o Windows PowerShell, enquanto um valor `Core` significa compatibilidade com o PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="48c3a-158">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="48c3a-159">Incluir `Desktop` e `Core` significa que o módulo é compatível com o Windows PowerShell e o PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="48c3a-159">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="48c3a-160">`Core` não significa automaticamente que o módulo é compatível com Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="48c3a-160">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="48c3a-161">A propriedade **CompatiblePSEditions** foi introduzida no PowerShell v5.</span><span class="sxs-lookup"><span data-stu-id="48c3a-161">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="48c3a-162">Os manifestos do módulo que usam a propriedade **CompatiblePSEditions** falham ao carregar em versões anteriores ao PowerShell v5.</span><span class="sxs-lookup"><span data-stu-id="48c3a-162">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="48c3a-163">Indicando a compatibilidade de SO</span><span class="sxs-lookup"><span data-stu-id="48c3a-163">Indicating OS Compatibility</span></span>

<span data-ttu-id="48c3a-164">Primeiramente, confirme se o módulo funciona no Linux e no macOS.</span><span class="sxs-lookup"><span data-stu-id="48c3a-164">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="48c3a-165">Em seguida, indique compatibilidade com esses sistemas operacionais no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="48c3a-165">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="48c3a-166">Isso facilita para que os usuários encontrem o seu módulo para o sistema operacional deles após a publicação na [Galeria do PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-166">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="48c3a-167">No manifesto do módulo, a propriedade `PrivateData` tem uma subpropriedade `PSData`.</span><span class="sxs-lookup"><span data-stu-id="48c3a-167">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="48c3a-168">A propriedade `Tags` opcional de `PSData` usa uma matriz de valores que é exibida na Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48c3a-168">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="48c3a-169">A Galeria do PowerShell aceita os seguintes valores de compatibilidade:</span><span class="sxs-lookup"><span data-stu-id="48c3a-169">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="48c3a-170">Marca</span><span class="sxs-lookup"><span data-stu-id="48c3a-170">Tag</span></span>               | <span data-ttu-id="48c3a-171">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="48c3a-171">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="48c3a-172">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="48c3a-172">PSEdition_Core</span></span>    | <span data-ttu-id="48c3a-173">Compatível com o PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="48c3a-173">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="48c3a-174">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="48c3a-174">PSEdition_Desktop</span></span> | <span data-ttu-id="48c3a-175">Compatível com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48c3a-175">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="48c3a-176">Windows</span><span class="sxs-lookup"><span data-stu-id="48c3a-176">Windows</span></span>           | <span data-ttu-id="48c3a-177">Compatível com Windows</span><span class="sxs-lookup"><span data-stu-id="48c3a-177">Compatible with Windows</span></span>                    |
| <span data-ttu-id="48c3a-178">Linux</span><span class="sxs-lookup"><span data-stu-id="48c3a-178">Linux</span></span>             | <span data-ttu-id="48c3a-179">Compatível com Linux (nenhuma distribuição específica)</span><span class="sxs-lookup"><span data-stu-id="48c3a-179">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="48c3a-180">macOS</span><span class="sxs-lookup"><span data-stu-id="48c3a-180">macOS</span></span>             | <span data-ttu-id="48c3a-181">Compatível com macOS</span><span class="sxs-lookup"><span data-stu-id="48c3a-181">Compatible with macOS</span></span>                      |

<span data-ttu-id="48c3a-182">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="48c3a-182">Example:</span></span>

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

## <a name="dependency-on-native-libraries"></a><span data-ttu-id="48c3a-183">Dependência em bibliotecas nativas</span><span class="sxs-lookup"><span data-stu-id="48c3a-183">Dependency on Native Libraries</span></span>

<span data-ttu-id="48c3a-184">Os módulos destinados ao uso em diferentes sistemas operacionais ou arquiteturas de processadores podem depender de uma biblioteca gerenciada que, por sua vez, depende de algumas bibliotecas nativas.</span><span class="sxs-lookup"><span data-stu-id="48c3a-184">Modules intended for use across different operating systems or processor architectures may depend on a managed library that itself depends on some native libraries.</span></span>

<span data-ttu-id="48c3a-185">Antes do PowerShell 7, era necessário ter um código personalizado para carregar a dll nativa adequada para que a biblioteca gerenciada pudesse encontrá-la corretamente.</span><span class="sxs-lookup"><span data-stu-id="48c3a-185">Prior to PowerShell 7, one would have to have custom code to load the appropriate native dll so that the managed library can find it correctly.</span></span>

<span data-ttu-id="48c3a-186">Com o PowerShell 7, os binários nativos que serão carregados são pesquisados em subpastas no local da biblioteca gerenciada após um subconjunto da notação do [Catálogo de RIDs do .NET][].</span><span class="sxs-lookup"><span data-stu-id="48c3a-186">With PowerShell 7, native binaries to load are searched in sub-folders within the managed library's location following a subset of the [.NET RID Catalog][] notation.</span></span>

```
managed.dll folder
                |
                |--- 'win-x64' folder
                |       |--- native.dll
                |
                |--- 'win-x86' folder
                |       |--- native.dll
                |
                |--- 'win-arm' folder
                |       |--- native.dll
                |
                |--- 'win-arm64' folder
                |       |--- native.dll
                |
                |--- 'linux-x64' folder
                |       |--- native.so
                |
                |--- 'linux-x86' folder
                |       |--- native.so
                |
                |--- 'linux-arm' folder
                |       |--- native.so
                |
                |--- 'linux-arm64' folder
                |       |--- native.so
                |
                |--- 'osx-x64' folder
                |       |--- native.dylib
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[verificações de runtime]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[runtime checks]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[CLI do .NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[Padrão do PowerShell]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[Padrão 5.1 do PowerShell]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Galeria do PowerShell]: https://www.powershellgallery.com
[PowerShell Gallery]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
[Catálogo de RIDs do .NET]: https://docs.microsoft.com/dotnet/core/rid-catalog
[.NET RID Catalog]: https://docs.microsoft.com/dotnet/core/rid-catalog
