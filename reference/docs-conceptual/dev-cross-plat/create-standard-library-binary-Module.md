---
title: Como criar um módulo binário da Biblioteca do PowerShell Standard
description: A Biblioteca do PowerShell Standard nos permite criar módulos de plataforma cruzada que funcionam no PowerShell Core e com o Windows PowerShell 5.1.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 51734fd9232e7c33b11c6c5a6abddbcc1f28413c
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149409"
---
# <a name="how-to-create-a-standard-library-binary-module"></a><span data-ttu-id="c8692-103">Como criar um módulo binário da Biblioteca do PowerShell Standard</span><span class="sxs-lookup"><span data-stu-id="c8692-103">How to create a Standard Library binary module</span></span>

<span data-ttu-id="c8692-104">Recentemente, eu tinha uma ideia do módulo que queria implementar como módulo binário.</span><span class="sxs-lookup"><span data-stu-id="c8692-104">I recently had an idea for module that I wanted to implement as a binary module.</span></span> <span data-ttu-id="c8692-105">Eu ainda preciso criar um usando a biblioteca do [Biblioteca do PowerShell Standard][], então achei que era uma boa oportunidade.</span><span class="sxs-lookup"><span data-stu-id="c8692-105">I have yet to create one using the [PowerShell Standard Library][] so this felt like a good opportunity.</span></span> <span data-ttu-id="c8692-106">Usei o guia [Como criar um módulo binário multiplataforma][] para criar esse módulo sem qualquer obstáculo.</span><span class="sxs-lookup"><span data-stu-id="c8692-106">I used the [Creating a cross-platform binary module][] guide to create this module without any roadblocks.</span></span>
<span data-ttu-id="c8692-107">Vamos examinar esse mesmo processo e eu farei alguns comentários extras ao longo do percurso.</span><span class="sxs-lookup"><span data-stu-id="c8692-107">We're going to walk that same process and I'll add a little extra commentary along the way.</span></span>

> [!NOTE]
> <span data-ttu-id="c8692-108">A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="c8692-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="c8692-109">A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="c8692-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="c8692-110">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="c8692-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-the-powershell-standard-library"></a><span data-ttu-id="c8692-111">O que é a Biblioteca do PowerShell Standard?</span><span class="sxs-lookup"><span data-stu-id="c8692-111">What is the PowerShell Standard Library?</span></span>

<span data-ttu-id="c8692-112">A Biblioteca do PowerShell Standard nos permite criar módulos de plataforma cruzada que funcionam no PowerShell Core e com o Windows PowerShell 5.1 (ou 3.0).</span><span class="sxs-lookup"><span data-stu-id="c8692-112">The PowerShell Standard Library allows us to create cross platform modules that work in both PowerShell Core and with Windows PowerShell 5.1 (or 3.0).</span></span>

## <a name="planning-our-module"></a><span data-ttu-id="c8692-113">Como planejar nosso módulo</span><span class="sxs-lookup"><span data-stu-id="c8692-113">Planning our module</span></span>

<span data-ttu-id="c8692-114">O plano para esse módulo é criar uma pasta `src` para o C# código e estruturar o restante da maneira que eu faria para um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="c8692-114">The plan for this module is to create a `src` folder for the C# code and structure the rest like I would for a script module.</span></span> <span data-ttu-id="c8692-115">Isso inclui usar um script de build para compilar tudo em uma pasta `output`.</span><span class="sxs-lookup"><span data-stu-id="c8692-115">This includes using a build script to compile everything into an `output` folder.</span></span> <span data-ttu-id="c8692-116">A estrutura de pastas tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="c8692-116">The folder structure looks like this:</span></span>

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a><span data-ttu-id="c8692-117">Introdução</span><span class="sxs-lookup"><span data-stu-id="c8692-117">Getting Started</span></span>

<span data-ttu-id="c8692-118">Normalmente, uso um modelo Plaster, mas meu modelo atual ainda não tem nenhum suporte de módulo binário.</span><span class="sxs-lookup"><span data-stu-id="c8692-118">I normally use a Plaster template but my current template doesn't have any binary module support yet.</span></span> <span data-ttu-id="c8692-119">Não é nada demais.</span><span class="sxs-lookup"><span data-stu-id="c8692-119">Not a big deal.</span></span> <span data-ttu-id="c8692-120">Vou criá-la manualmente dessa vez.</span><span class="sxs-lookup"><span data-stu-id="c8692-120">I'll create this one by hand this time.</span></span>

<span data-ttu-id="c8692-121">Primeiro, preciso criar a pasta e o repositório git.</span><span class="sxs-lookup"><span data-stu-id="c8692-121">First I need to create the folder and create the git repo.</span></span> <span data-ttu-id="c8692-122">Estou usando `$module` como um espaço reservado para o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="c8692-122">I'm using `$module` as a placeholder for the module name.</span></span> <span data-ttu-id="c8692-123">Isso deve facilitar a reutilização desses exemplos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c8692-123">This should make it easier for you to reuse these examples if needed.</span></span>

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

<span data-ttu-id="c8692-124">Em seguida, crio as pastas do nível raiz.</span><span class="sxs-lookup"><span data-stu-id="c8692-124">Then create the root level folders.</span></span>

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a><span data-ttu-id="c8692-125">Configuração do módulo binário</span><span class="sxs-lookup"><span data-stu-id="c8692-125">Binary module setup</span></span>

<span data-ttu-id="c8692-126">O fodo deste artigo é o módulo binário, portanto, vamos começar.</span><span class="sxs-lookup"><span data-stu-id="c8692-126">This article os focused on the binary module so that is where we'll start.</span></span> <span data-ttu-id="c8692-127">Esta seção usa exemplos retirados do guia [Como criar um módulo binário multiplataforma][].</span><span class="sxs-lookup"><span data-stu-id="c8692-127">This section pulls examples from the [Creating a cross-platform binary module][] guide.</span></span> <span data-ttu-id="c8692-128">Examine esse guia se precisar de mais detalhes ou tiver problemas.</span><span class="sxs-lookup"><span data-stu-id="c8692-128">Review that guide if you need more details or have any issues.</span></span>

<span data-ttu-id="c8692-129">A primeira coisa que precisamos fazer é verificar a versão do [SDK do .NET Core][] que instalamos.</span><span class="sxs-lookup"><span data-stu-id="c8692-129">First thing we want to do is check the version of the [dotnet core SDK][] that we installed.</span></span> <span data-ttu-id="c8692-130">Estou usando a versão 2.1.4, mas você precisa da versão 2.0.0 ou posterior para continuar.</span><span class="sxs-lookup"><span data-stu-id="c8692-130">I'm using 2.1.4, but you should have 2.0.0 or newer before continuing.</span></span>

```powershell
PS> dotnet --version
2.1.4
```

<span data-ttu-id="c8692-131">Estou trabalhando fora da pasta `src` nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c8692-131">I'm working out of the `src` folder for this section.</span></span>

```powershell
Set-Location 'src'
```

<span data-ttu-id="c8692-132">Usando o comando dotnet, crie uma nova biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="c8692-132">Using the dotnet command, create a new class library.</span></span>

```powershell
dotnet new classlib --name $module
```

<span data-ttu-id="c8692-133">Isso criou o projeto de biblioteca em uma subpasta, mas não quero esse nível extra de aninhamento.</span><span class="sxs-lookup"><span data-stu-id="c8692-133">This created the library project in a subfolder but I don't want that extra level of nesting.</span></span> <span data-ttu-id="c8692-134">Vou mover esses arquivos para um nível acima.</span><span class="sxs-lookup"><span data-stu-id="c8692-134">I'm going to move those files up a level.</span></span>

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

<span data-ttu-id="c8692-135">Defina a versão do SDK do .NET Core para o projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-135">Set the .NET core SDK version for the project.</span></span> <span data-ttu-id="c8692-136">Tenho o SDK 2.1, portanto, vou especificar 2.1.0.</span><span class="sxs-lookup"><span data-stu-id="c8692-136">I have the 2.1 SDK so I'm going to specify 2.1.0.</span></span>
<span data-ttu-id="c8692-137">Especifique 2.0.0 se você estiver usando o SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="c8692-137">Use 2.0.0 if you're using the 2.0 SDK.</span></span>

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

<span data-ttu-id="c8692-138">Adicione o [pacote NuGet][] da Biblioteca do PowerShell Standard ao projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-138">Add the PowerShell Standard Library [NuGet package][] to the project.</span></span> <span data-ttu-id="c8692-139">Lembre-se de usar a versão mais recente disponível para o nível de compatibilidade de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="c8692-139">Make sure you use the most recent version available for the level of compatibility that you need.</span></span> <span data-ttu-id="c8692-140">Eu usaria como padrão a versão mais recente, mas não acho que este módulo use recursos mais recentes do que o PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c8692-140">I would default to the latest version but I don't think this module leverages any features newer than PowerShell 3.0.</span></span>

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

<span data-ttu-id="c8692-141">Devemos ter uma pasta src parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="c8692-141">We should have a src folder that looks like this:</span></span>

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

<span data-ttu-id="c8692-142">Agora estamos prontos para adicionar nosso próprio código ao projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-142">Now we're ready to add our own code to the project.</span></span>

### <a name="building-a-binary-cmdlet"></a><span data-ttu-id="c8692-143">Como criar um cmdlet binário</span><span class="sxs-lookup"><span data-stu-id="c8692-143">Building a binary cmdlet</span></span>

<span data-ttu-id="c8692-144">Precisamos atualizar a `src\Class1.cs` para conter este cmdlet inicial:</span><span class="sxs-lookup"><span data-stu-id="c8692-144">We need to update the `src\Class1.cs` to contain this starter cmdlet:</span></span>

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

<span data-ttu-id="c8692-145">Renomeie o arquivo para corresponder ao nome de classe.</span><span class="sxs-lookup"><span data-stu-id="c8692-145">Rename the file to match the class name.</span></span>

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

<span data-ttu-id="c8692-146">Em seguida, podemos criar nosso módulo.</span><span class="sxs-lookup"><span data-stu-id="c8692-146">Then we can build our module.</span></span>

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

<span data-ttu-id="c8692-147">Podemos chamar `Import-Module` na nova dll para carregar nosso novo CMDlet.</span><span class="sxs-lookup"><span data-stu-id="c8692-147">We can call `Import-Module` on the new dll to load our new CMDlet.</span></span>

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

<span data-ttu-id="c8692-148">Se a importação falhar no sistema, tente atualizar o .NET para a versão 4.7.1 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="c8692-148">If the import fails on your system, try updating .NET to 4.7.1 or newer.</span></span> <span data-ttu-id="c8692-149">O guia [Como criar um módulo binário multiplataforma][] fornece mais detalhes sobre o suporte e a compatibilidade para versões mais antigas do .NET.</span><span class="sxs-lookup"><span data-stu-id="c8692-149">The [Creating a cross-platform binary module][] guide goes into more details on .NET support and compatibility for older versions of .NET.</span></span>

### <a name="module-manifest"></a><span data-ttu-id="c8692-150">Manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="c8692-150">Module manifest</span></span>

<span data-ttu-id="c8692-151">Acho ótimo que possamos importar a dll e ter um módulo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c8692-151">It's cool that we can import the dll and have a working module.</span></span> <span data-ttu-id="c8692-152">Gosto de mantê-lo e criar um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="c8692-152">I like to keep going with it and create a module manifest.</span></span> <span data-ttu-id="c8692-153">Precisaremos do manifesto se quisermos publicar no PSGallery mais tarde.</span><span class="sxs-lookup"><span data-stu-id="c8692-153">We need the manifest if we want to publish to the PSGallery later.</span></span>

<span data-ttu-id="c8692-154">Da raiz do nosso projeto, podemos executar esse comando para criar o manifesto do módulo que precisamos.</span><span class="sxs-lookup"><span data-stu-id="c8692-154">From the root of our project, we can run this command to create the module manifest that we need.</span></span>

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

<span data-ttu-id="c8692-155">Também vou criar um módulo raiz vazio para funções do PowerShell futuras.</span><span class="sxs-lookup"><span data-stu-id="c8692-155">I'm also going to create an empty root module for future PowerShell functions.</span></span>

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

<span data-ttu-id="c8692-156">Isso me permite combinar tanto funções normais PowerShell, quanto Cmdlets binários no mesmo projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-156">This allows me to mix both normal PowerShell functions and binary Cmdlets in the same project.</span></span>

### <a name="building-the-full-module"></a><span data-ttu-id="c8692-157">Como criar o módulo completo</span><span class="sxs-lookup"><span data-stu-id="c8692-157">Building the full module</span></span>

<span data-ttu-id="c8692-158">Eu compilo tudo junto em uma pasta de saída.</span><span class="sxs-lookup"><span data-stu-id="c8692-158">I compile everything together into an output folder.</span></span> <span data-ttu-id="c8692-159">Precisamos criar um script de build para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="c8692-159">We need to create a build script to do that.</span></span> <span data-ttu-id="c8692-160">Normalmente, eu o adicionaria a um script `Invoke-Build`, mas vamos manter este exemplo simples.</span><span class="sxs-lookup"><span data-stu-id="c8692-160">I would normally add this to an `Invoke-Build` script, but we can keep it simple for this example.</span></span> <span data-ttu-id="c8692-161">Adicione isso a um `build.ps1` na raiz do projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-161">Add this to a `build.ps1` at the root of the project.</span></span>

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

<span data-ttu-id="c8692-162">Esses comandos compilam nossa DLL e a colocam em nossa pasta `output\$module\bin`.</span><span class="sxs-lookup"><span data-stu-id="c8692-162">These commands build our DLL and place it into our `output\$module\bin` folder.</span></span> <span data-ttu-id="c8692-163">Em seguida, ele copia os outros arquivos do módulo para o local.</span><span class="sxs-lookup"><span data-stu-id="c8692-163">It then copies the other module files into place.</span></span>

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

<span data-ttu-id="c8692-164">A essa altura, podemos importar nosso módulo com o arquivo psd1.</span><span class="sxs-lookup"><span data-stu-id="c8692-164">At this point, we can import our module with the psd1 file.</span></span>

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

<span data-ttu-id="c8692-165">Partindo daqui, podemos soltar a pasta `.\Output\$module` em nosso diretório `$env:PSModulePath` e ela carregará nosso comando automaticamente sempre que precisarmos.</span><span class="sxs-lookup"><span data-stu-id="c8692-165">From here, we can drop the `.\Output\$module` folder into our `$env:PSModulePath` directory and it autoloads our command whenever we need it.</span></span>

### <a name="update-dotnet-new-psmodule"></a><span data-ttu-id="c8692-166">Atualização: novo PSModule do .NET</span><span class="sxs-lookup"><span data-stu-id="c8692-166">Update: dotnet new PSModule</span></span>

<span data-ttu-id="c8692-167">Aprendi que a ferramenta de `dotnet` tem um modelo de `PSModule`.</span><span class="sxs-lookup"><span data-stu-id="c8692-167">I learned that the `dotnet` tool has a `PSModule` template.</span></span>

<span data-ttu-id="c8692-168">Todas as etapas descritas acima ainda são válidas, mas esse modelo elimina muitas delas. É um modelo bastante novo e que ainda está sendo aprimorado.</span><span class="sxs-lookup"><span data-stu-id="c8692-168">All the steps that I outlined above are still valid, but this template cuts many pf them out. It's still a fairly new template that is still getting some polish placed on it.</span></span> <span data-ttu-id="c8692-169">Pode acreditar que ele vai continuar melhorando.</span><span class="sxs-lookup"><span data-stu-id="c8692-169">Expect it to keep getting better from here.</span></span>

<span data-ttu-id="c8692-170">É assim que você usa install e modelo do PSModule.</span><span class="sxs-lookup"><span data-stu-id="c8692-170">This is how you use install and use the PSModule template.</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

<span data-ttu-id="c8692-171">Esse modelo minimamente viável se encarrega da adição do SDK do .NET, da Biblioteca do PowerShell Standard e cria uma classe de exemplo no projeto.</span><span class="sxs-lookup"><span data-stu-id="c8692-171">This minimally-viable template takes care of adding the .NET SDK, PowerShell Standard Library, and creates an example class in the project.</span></span> <span data-ttu-id="c8692-172">Você pode compilá-lo e executá-lo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c8692-172">You can build it and run it right away.</span></span>

## <a name="important-details"></a><span data-ttu-id="c8692-173">Detalhes importantes</span><span class="sxs-lookup"><span data-stu-id="c8692-173">Important details</span></span>

<span data-ttu-id="c8692-174">Antes de encerrar este artigo, aqui estão alguns detalhes que vale a pena comentar.</span><span class="sxs-lookup"><span data-stu-id="c8692-174">Before we end this article, here are a few other details worth mentioning.</span></span>

### <a name="unloading-dlls"></a><span data-ttu-id="c8692-175">Como descarregar DLLs</span><span class="sxs-lookup"><span data-stu-id="c8692-175">Unloading DLLs</span></span>

<span data-ttu-id="c8692-176">Uma vez que um módulo binário é carregado, você não pode descarregá-lo realmente.</span><span class="sxs-lookup"><span data-stu-id="c8692-176">Once a binary module is loaded, you can't really unload it.</span></span> <span data-ttu-id="c8692-177">O arquivo DLL é bloqueado até que você o descarregue.</span><span class="sxs-lookup"><span data-stu-id="c8692-177">The DLL file is locked until you unload it.</span></span> <span data-ttu-id="c8692-178">Isso pode ser irritante durante o desenvolvimento, porque quase toda vez que você quiser compilar uma alteração que tenha feito, o arquivo será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c8692-178">This can be annoying when developing because every time you make a change and want to build it, the file is often locked.</span></span> <span data-ttu-id="c8692-179">A única maneira confiável de resolver isso é fechar a sessão do PowerShell que carregou a DLL.</span><span class="sxs-lookup"><span data-stu-id="c8692-179">The only reliable way to resolve this is to close the PowerShell session that loaded the DLL.</span></span>

### <a name="vs-code-reload-window-action"></a><span data-ttu-id="c8692-180">Ação recarregar janela no VS Code</span><span class="sxs-lookup"><span data-stu-id="c8692-180">VS Code reload window action</span></span>

<span data-ttu-id="c8692-181">Eu faço a maior parte do meu trabalho de desenvolvimento do PowerShell no [Código do VS][].</span><span class="sxs-lookup"><span data-stu-id="c8692-181">I do most of my PowerShell dev work in [VS Code][].</span></span> <span data-ttu-id="c8692-182">Quando estou trabalhando em um módulo binário (ou um módulo com classes), tenho o hábito de recarregar o VS Code toda vez que compilo.</span><span class="sxs-lookup"><span data-stu-id="c8692-182">When I'm working on a binary module (or a module with classes), I've gotten into the habit of reloading VS Code every time I build.</span></span>
<span data-ttu-id="c8692-183"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> abre a janela Comando e `Reload Window` está sempre na parte superior da minha lista.</span><span class="sxs-lookup"><span data-stu-id="c8692-183"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> pops the command window and `Reload Window` is always at the top of my list.</span></span>

### <a name="nested-powershell-sessions"></a><span data-ttu-id="c8692-184">Sessões aninhadas do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8692-184">Nested PowerShell sessions</span></span>

<span data-ttu-id="c8692-185">Outra opção é ter uma boa cobertura de teste do Pester.</span><span class="sxs-lookup"><span data-stu-id="c8692-185">One other option is to have good Pester test coverage.</span></span> <span data-ttu-id="c8692-186">Em seguida, você pode ajustar o script build.ps1 para iniciar uma nova sessão do PowerShell, executar a compilação, executar os testes e fechar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8692-186">Then you can adjust the build.ps1 script to start a new PowerShell session, perform the build, run the tests, and close the session.</span></span>

### <a name="updating-installed-modules"></a><span data-ttu-id="c8692-187">Como atualizar os módulos instalados</span><span class="sxs-lookup"><span data-stu-id="c8692-187">Updating installed modules</span></span>

<span data-ttu-id="c8692-188">Esse bloqueio pode incomodar ao tentar atualizar o módulo instalado localmente.</span><span class="sxs-lookup"><span data-stu-id="c8692-188">This locking can be annoying when trying to update your locally installed module.</span></span> <span data-ttu-id="c8692-189">Caso alguma sessão o tenha carregado, você precisará encontrá-lo e fechá-lo.</span><span class="sxs-lookup"><span data-stu-id="c8692-189">If any session has it loaded, you have to go hunt it down and close it.</span></span> <span data-ttu-id="c8692-190">Isso não é tão problemático ao fazer a instalação de uma PSGallery, porque o controle de versão do módulo coloca o novo módulo em uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="c8692-190">This is less of an issue when installing from a PSGallery because module versioning places the new one in a different folder.</span></span>

<span data-ttu-id="c8692-191">Você pode configurar uma PSGallery local e publicá-la como parte de sua compilação.</span><span class="sxs-lookup"><span data-stu-id="c8692-191">You can set up a local PSGallery and publish to that as part of your build.</span></span> <span data-ttu-id="c8692-192">Em seguida, faça a instalação local por meio dessa PSGallery.</span><span class="sxs-lookup"><span data-stu-id="c8692-192">Then do your local install from that PSGallery.</span></span> <span data-ttu-id="c8692-193">Isso parece trabalhoso, mas pode ser tão simples quanto iniciar um contêiner do Docker.</span><span class="sxs-lookup"><span data-stu-id="c8692-193">This sounds like a lot of work, but this can be as simple as starting a docker container.</span></span> <span data-ttu-id="c8692-194">Eu abordei um jeito de fazer isso em minha postagem [Como usar um servidor NuGet para um PSRepository][].</span><span class="sxs-lookup"><span data-stu-id="c8692-194">I cover a way to do that in my post on [Using a NuGet server for a PSRepository][].</span></span>

## <a name="why-binary-modules"></a><span data-ttu-id="c8692-195">Por que módulos binários?</span><span class="sxs-lookup"><span data-stu-id="c8692-195">Why binary modules?</span></span>

<span data-ttu-id="c8692-196">Eu já comecei falando sobre como criar um módulo binário e nem comentei a razão pela qual seria interessante fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="c8692-196">I jumped right into how to make a binary module and didn't mention why you want to make one.</span></span> <span data-ttu-id="c8692-197">Na realidade, você está escrevendo C# e renunciando ao acesso fácil a Cmdlets e funções do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8692-197">In reality, you are writing C# and give up easy access to PowerShell Cmdlets and functions.</span></span> <span data-ttu-id="c8692-198">Esse é o principal motivo pelo qual não mudei para os módulos binários mais cedo.</span><span class="sxs-lookup"><span data-stu-id="c8692-198">That is the main reason why I have not shifted to binary modules sooner.</span></span>

<span data-ttu-id="c8692-199">Mas se você estiver criando um módulo que não dependa de muitos outros comandos do PowerShell, o benefício de desempenho poderá ser significativo.</span><span class="sxs-lookup"><span data-stu-id="c8692-199">But if you are creating a module that doesn't depend on a lot of other PowerShell commands, the performance benefit can be significant.</span></span> <span data-ttu-id="c8692-200">Ao colocar em C#, você consegue suprimir a sobrecarga adicionada pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8692-200">By dropping into C#, you get to shed the overhead added by PowerShell.</span></span> <span data-ttu-id="c8692-201">O PowerShell foi otimizado para o administrador, não para o computador, e isso adiciona uma pequena sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="c8692-201">PowerShell was optimized for the administrator, not the computer, and that adds a little overhead.</span></span>

<span data-ttu-id="c8692-202">No trabalho, temos um processo crítico que trabalha muito com JSON e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="c8692-202">At work, we have a critical process that does a lot of work with JSON and Hashtables.</span></span> <span data-ttu-id="c8692-203">Nós otimizamos o PowerShell tanto quanto foi possível, mas esse processo continuou executando por 12 minutos.</span><span class="sxs-lookup"><span data-stu-id="c8692-203">We optimized the PowerShell as much as we could but this process was still running for 12 minutes.</span></span> <span data-ttu-id="c8692-204">O módulo já continha muito PowerShell com o estilo do C#.</span><span class="sxs-lookup"><span data-stu-id="c8692-204">The module already contained a lot of C# style PowerShell.</span></span> <span data-ttu-id="c8692-205">Isso tornou a conversão para um módulo binário limpa e fácil de fazer.</span><span class="sxs-lookup"><span data-stu-id="c8692-205">This made the conversion to a binary module clean and easy to do.</span></span> <span data-ttu-id="c8692-206">Nossa conversão reduziu o processo de mais de 12 minutos para menos de 4 minutos.</span><span class="sxs-lookup"><span data-stu-id="c8692-206">Our conversion cut that process down from over 12 minutes to under four minutes.</span></span>

### <a name="hybrid-modules"></a><span data-ttu-id="c8692-207">Módulos híbridos</span><span class="sxs-lookup"><span data-stu-id="c8692-207">Hybrid modules</span></span>

<span data-ttu-id="c8692-208">Você pode combinar Cmdlets binários com funções avançadas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8692-208">You can mix binary Cmdlets with PowerShell advanced functions.</span></span> <span data-ttu-id="c8692-209">É exatamente isso que estou fazendo nesse guia.</span><span class="sxs-lookup"><span data-stu-id="c8692-209">That is exactly what I'm doing in this guide.</span></span> <span data-ttu-id="c8692-210">Tudo o que você sabe sobre scripts de módulo será aplicável da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="c8692-210">You can take everything you know about script modules and it all applies the same way.</span></span>
<span data-ttu-id="c8692-211">O arquivo `psm1` vazio que eu criei hoje existe apenas para que você possa soltar outras funções do PowerShell mais tarde.</span><span class="sxs-lookup"><span data-stu-id="c8692-211">The empty `psm1` file that I created today is there just so you can drop in other PowerShell functions later.</span></span>

<span data-ttu-id="c8692-212">Quase todos os cmdlets compilados que criamos começaram como uma função do PowerShell antes.</span><span class="sxs-lookup"><span data-stu-id="c8692-212">Almost all of the compiled cmdlets that we created started out as a PowerShell function first.</span></span> <span data-ttu-id="c8692-213">Todos os nossos módulos binários são na verdade módulos híbridos.</span><span class="sxs-lookup"><span data-stu-id="c8692-213">All of our binary modules are really hybrid modules.</span></span>

### <a name="build-scripts"></a><span data-ttu-id="c8692-214">Scripts de build</span><span class="sxs-lookup"><span data-stu-id="c8692-214">Build scripts</span></span>

<span data-ttu-id="c8692-215">Eu mantive o script de build simples aqui.</span><span class="sxs-lookup"><span data-stu-id="c8692-215">I kept the build script simple here.</span></span> <span data-ttu-id="c8692-216">Eu geralmente uso um script de `Invoke-Build` grande como parte do meu pipeline de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="c8692-216">I generally use a large `Invoke-Build` script as part of my CI/CD pipeline.</span></span> <span data-ttu-id="c8692-217">Ele faz maravilhas como executar de testes de Pester, o PSScriptAnalyzer, gerenciar versões e a publicar no PSGallery.</span><span class="sxs-lookup"><span data-stu-id="c8692-217">It does more magic like running Pester tests, running PSScriptAnalyzer, managing versioning, and publishing to the PSGallery.</span></span> <span data-ttu-id="c8692-218">Depois que comecei a usar um script de build para os meus módulos, encontrei muitas coisas para adicionar a eles.</span><span class="sxs-lookup"><span data-stu-id="c8692-218">Once I started using a build script for my modules, I was able to find lots of things to add to it.</span></span>

## <a name="final-thoughts"></a><span data-ttu-id="c8692-219">Considerações finais</span><span class="sxs-lookup"><span data-stu-id="c8692-219">Final thoughts</span></span>

<span data-ttu-id="c8692-220">Os módulos binários são fáceis de criar.</span><span class="sxs-lookup"><span data-stu-id="c8692-220">Binary modules are easy to create.</span></span> <span data-ttu-id="c8692-221">Eu não mexi na sintaxe do C# para criar um cmdlet, mas há muitas documentações sobre isso [SDK do Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="c8692-221">I didn't touch on the C# syntax for creating a Cmdlet, but there is plenty of documentation on it in the [Windows PowerShell SDK][].</span></span> <span data-ttu-id="c8692-222">Definitivamente, é algo que vale a pena tentar como ponto de partida para um nível mais sério do C#.</span><span class="sxs-lookup"><span data-stu-id="c8692-222">It is definitely something worth experimenting with as a stepping stone into more serious C#.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[original version]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Biblioteca do PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard Library]: https://github.com/PowerShell/PowerShellStandard
[Como criar um módulo binário multiplataforma]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Creating a cross-platform binary module]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[SDK do .NET Core]: https://www.microsoft.com/net/download/core
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[Como usar um servidor NuGet para um PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Using a NuGet server for a PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[SDK do Windows PowerShell]: /powershell/scripting/developer/windows-powershell-reference
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[Código do VS]: https://code.visualstudio.com
[VS Code]: https://code.visualstudio.com
[Pacote NuGet]: https://www.nuget.org/packages/PowerShellStandard.Library/
[nuget package]: https://www.nuget.org/packages/PowerShellStandard.Library/
