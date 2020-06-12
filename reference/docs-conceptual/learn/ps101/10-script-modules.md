---
title: Script modules (Módulos de script)
description: Os módulos de script são um modo fácil de empacotar scripts e funções em uma ferramenta reutilizável.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 661ba725764e1f31df628f6c5f2d58d760656e37
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438277"
---
# <a name="chapter-10---script-modules"></a><span data-ttu-id="d0597-103">Capítulo 10 – Módulos de script</span><span class="sxs-lookup"><span data-stu-id="d0597-103">Chapter 10 - Script modules</span></span>

<span data-ttu-id="d0597-104">Transformar seus scripts e uma linha no PowerShell em ferramentas reutilizáveis torna-se ainda mais importante se é algo que você pretende usar com frequência.</span><span class="sxs-lookup"><span data-stu-id="d0597-104">Turning your one-liners and scripts in PowerShell into reusable tools becomes even more important if it's something that you're going to use frequently.</span></span> <span data-ttu-id="d0597-105">O empacotamento de suas funções em um módulo de script faz com que elas pareçam mais profissionais e facilitam o compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="d0597-105">Packaging your functions in a script module makes them look and feel more professional and makes them easier to share.</span></span>

## <a name="dot-sourcing-functions"></a><span data-ttu-id="d0597-106">Funções de fornecimento de ponto</span><span class="sxs-lookup"><span data-stu-id="d0597-106">Dot-Sourcing Functions</span></span>

<span data-ttu-id="d0597-107">Um assunto que não abordamos no capítulo anterior é funções de fornecimento de ponto.</span><span class="sxs-lookup"><span data-stu-id="d0597-107">Something that we didn't talk about in the previous chapter is dot-sourcing functions.</span></span> <span data-ttu-id="d0597-108">Quando uma função em um script não faz parte de um módulo, a única maneira de carregá-la na memória é a origem de ponto do arquivo `.PS1` em que ela foi salva.</span><span class="sxs-lookup"><span data-stu-id="d0597-108">When a function in a script isn't part of a module, the only way to load it into memory is to dot-source the `.PS1` file that it's saved in.</span></span>

<span data-ttu-id="d0597-109">A função a seguir foi salva como `Get-MrPSVersion.ps1`.</span><span class="sxs-lookup"><span data-stu-id="d0597-109">The following function has been saved as `Get-MrPSVersion.ps1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}
```

<span data-ttu-id="d0597-110">Quando você executa o script, nada acontece.</span><span class="sxs-lookup"><span data-stu-id="d0597-110">When you run the script, nothing happens.</span></span>

```powershell
.\Get-MrPSVersion.ps1
```

<span data-ttu-id="d0597-111">Se você tentar chamar a função, ela vai gerar uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="d0597-111">If you try to call the function, it generates an error message.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Get-MrPSVersion : The term 'Get-MrPSVersion' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [], CommandNotFou
   ndException
    + FullyQualifiedErrorId : CommandNotFoundException

```

<span data-ttu-id="d0597-112">Você pode determinar se as funções são carregadas na memória verificando se elas existem na PSDrive **Function**.</span><span class="sxs-lookup"><span data-stu-id="d0597-112">You can determine if functions are loaded into memory by checking to see if they exist on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
Get-ChildItem : Cannot find path 'Get-MrPSVersion' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path Function:\Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [Get-ChildItem],
   ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
```

<span data-ttu-id="d0597-113">O problema de chamar o script que contém a função é que as funções são carregadas no escopo de _Script_.</span><span class="sxs-lookup"><span data-stu-id="d0597-113">The problem with calling the script that contains the function is that the functions are loaded in the _Script_ scope.</span></span> <span data-ttu-id="d0597-114">Quando o script for concluído, esse escopo será removido e a função será removida com ele.</span><span class="sxs-lookup"><span data-stu-id="d0597-114">When the script completes, that scope is removed and the function is removed with it.</span></span>

<span data-ttu-id="d0597-115">A função precisa ser carregada no escopo _Global_.</span><span class="sxs-lookup"><span data-stu-id="d0597-115">The function needs to be loaded into the _Global_ scope.</span></span> <span data-ttu-id="d0597-116">Isso pode ser feito adquirindo o ponto do script que contém a função.</span><span class="sxs-lookup"><span data-stu-id="d0597-116">That can be accomplished by dot-sourcing the script that contains the function.</span></span> <span data-ttu-id="d0597-117">O caminho relativo pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="d0597-117">The relative path can be used.</span></span>

```powershell
. .\Get-MrPSVersion.ps1
```

<span data-ttu-id="d0597-118">O caminho totalmente qualificado também pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="d0597-118">The fully qualified path can also be used.</span></span>

```powershell
. C:\Demo\Get-MrPSVersion.ps1
```

<span data-ttu-id="d0597-119">Se uma parte do caminho for armazenada em uma variável, ela poderá ser combinada com o restante do caminho.</span><span class="sxs-lookup"><span data-stu-id="d0597-119">If a portion of the path is stored in a variable, it can be combined with the remainder of the path.</span></span>
<span data-ttu-id="d0597-120">Não há motivo para usar a concatenação de cadeia de caracteres para combinar a variável junto com o restante do caminho.</span><span class="sxs-lookup"><span data-stu-id="d0597-120">There's no reason to use string concatenation to combine the variable together with the remainder of the path.</span></span>

```powershell
$Path = 'C:\'
. $Path\Get-MrPSVersion.ps1
```

<span data-ttu-id="d0597-121">Agora, quando verifico a PSDrive **Function**, a função `Get-MrPSVersion` existe.</span><span class="sxs-lookup"><span data-stu-id="d0597-121">Now when I check the **Function** PSDrive, the `Get-MrPSVersion` function exists.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-MrPSVersion
```

## <a name="script-modules"></a><span data-ttu-id="d0597-122">Módulos de script</span><span class="sxs-lookup"><span data-stu-id="d0597-122">Script Modules</span></span>

<span data-ttu-id="d0597-123">Um módulo de script no PowerShell é simplesmente um arquivo que contém uma ou mais funções que são salvas como um arquivo de `.PSM1` em vez de um arquivo de `.PS1`.</span><span class="sxs-lookup"><span data-stu-id="d0597-123">A script module in PowerShell is simply a file containing one or more functions that's saved as a `.PSM1` file instead of a `.PS1` file.</span></span>

<span data-ttu-id="d0597-124">Como criar um módulo de script?</span><span class="sxs-lookup"><span data-stu-id="d0597-124">How do you create a script module?</span></span> <span data-ttu-id="d0597-125">Provavelmente, você está supondo com um comando chamado algo como `New-Module`.</span><span class="sxs-lookup"><span data-stu-id="d0597-125">You're probably guessing with a command named something like `New-Module`.</span></span> <span data-ttu-id="d0597-126">Sua suposição está incorreta.</span><span class="sxs-lookup"><span data-stu-id="d0597-126">Your assumption would be wrong.</span></span> <span data-ttu-id="d0597-127">Embora haja um comando no PowerShell chamado `New-Module`, esse comando cria um módulo dinâmico, não um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="d0597-127">While there is a command in PowerShell named `New-Module`, that command creates a dynamic module, not a script module.</span></span> <span data-ttu-id="d0597-128">Sempre leia a ajuda para um comando mesmo quando você acreditar que encontrou o comando de que precisa.</span><span class="sxs-lookup"><span data-stu-id="d0597-128">Always be sure to read the help for a command even when you think you've found the command you need.</span></span>

```powershell
help New-Module
```

```Output
NAME
    New-Module

SYNOPSIS
    Creates a new dynamic module that exists only in memory.

SYNTAX
    New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-ArgumentList <Object[]>]
    [-AsCustomObject] [-Cmdlet <String[]>] [-Function <String[]>] [-ReturnResult]
    [<CommonParameters>]

DESCRIPTION
    The New-Module cmdlet creates a dynamic module from a script block. The members of
    the dynamic module, such as functions and variables, are immediately available in
    the session and remain available until you close the session.

    Like static modules, by default, the cmdlets and functions in a dynamic module are
    exported and the variables and aliases are not. However, you can use the
    Export-ModuleMember cmdlet and the parameters of New-Module to override the defaults.

    You can also use the AsCustomObject parameter of New-Module to return the dynamic
    module as a custom object. The members of the modules, such as functions, are
    implemented as script methods of the custom object instead of being imported into
    the session.

    Dynamic modules exist only in memory, not on disk. Like all modules, the members of
    dynamic modules run in a private module scope that is a child of the global scope.
    Get-Module cannot get a dynamic module, but Get-Command can get the exported members.

    To make a dynamic module available to Get-Module , pipe a New-Module command to
    Import-Module, or pipe the module object that New-Module returns to Import-Module .
    This action adds the dynamic module to the Get-Module list, but it does not save the
    module to disk or make it persistent.

RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821495
    Export-ModuleMember
    Get-Module
    Import-Module
    Remove-Module

REMARKS
    To see the examples, type: "get-help New-Module -examples".
    For more information, type: "get-help New-Module -detailed".
    For technical information, type: "get-help New-Module -full".
    For online help, type: "get-help New-Module -online"
```

<span data-ttu-id="d0597-129">No capítulo anterior, mencionei que as funções devem usar verbos aprovados, caso contrário, gerarão uma mensagem de aviso quando o módulo for importado.</span><span class="sxs-lookup"><span data-stu-id="d0597-129">In the previous chapter, I mentioned that functions should use approved verbs otherwise they'll generate a warning message when the module is imported.</span></span> <span data-ttu-id="d0597-130">O código a seguir usa o cmdlet `New-Module` para criar um módulo dinâmico na memória.</span><span class="sxs-lookup"><span data-stu-id="d0597-130">The following code uses the `New-Module` cmdlet to create a dynamic module in memory.</span></span> <span data-ttu-id="d0597-131">Este módulo demonstra o aviso de verbo não aprovado.</span><span class="sxs-lookup"><span data-stu-id="d0597-131">This module demonstrates the unapproved verb warning.</span></span>

```powershell
New-Module -Name MyModule -ScriptBlock {

    function Return-MrOsVersion {
        Get-CimInstance -ClassName Win32_OperatingSystem |
        Select-Object -Property @{label='OperatingSystem';expression={$_.Caption}}
    }

    Export-ModuleMember -Function Return-MrOsVersion

} | Import-Module
```

```Output
WARNING: The names of some imported commands from the module 'MyModule' include
unapproved verbs that might make them less discoverable. To find the commands with
unapproved verbs, run the Import-Module command again with the Verbose parameter. For a
list of approved verbs, type Get-Verb.
```

<span data-ttu-id="d0597-132">Apenas para reiterar, embora o cmdlet `New-Module` tenha sido usado no exemplo anterior, esse não é o comando para a criação de módulos de script no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0597-132">Just to reiterate, although the `New-Module` cmdlet was used in the previous example, that's not the command for creating script modules in PowerShell.</span></span>

<span data-ttu-id="d0597-133">Salve as duas funções a seguir em um arquivo chamado `MyScriptModule.psm1`.</span><span class="sxs-lookup"><span data-stu-id="d0597-133">Save the following two functions in a file named `MyScriptModule.psm1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}
```

<span data-ttu-id="d0597-134">Tente chamar uma das funções.</span><span class="sxs-lookup"><span data-stu-id="d0597-134">Try to call one of the functions.</span></span>

```powershell
Get-MrComputerName
```

```Output
Get-MrComputerName : The term 'Get-MrComputerName' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrComputerName
    + CategoryInfo          : ObjectNotFound: (Get-MrComputerName:String) [], CommandNot
   FoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="d0597-135">Uma mensagem de erro é gerada dizendo que a função não pode ser encontrada.</span><span class="sxs-lookup"><span data-stu-id="d0597-135">An error message is generated saying the function can't be found.</span></span> <span data-ttu-id="d0597-136">Você também pode verificar a PSDrive **Function** da mesma forma que antes e descobrirá que ela não existe.</span><span class="sxs-lookup"><span data-stu-id="d0597-136">You could also check the **Function** PSDrive just like before and you'll find that it doesn't exist there either.</span></span>

<span data-ttu-id="d0597-137">Você pode importar manualmente o arquivo com o cmdlet `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="d0597-137">You could manually import the file with the `Import-Module` cmdlet.</span></span>

```powershell
Import-Module C:\MyScriptModule.psm1
```

<span data-ttu-id="d0597-138">O recurso de carregamento automático do módulo foi introduzido no PowerShell versão 3.</span><span class="sxs-lookup"><span data-stu-id="d0597-138">The module autoloading feature was introduced in PowerShell version 3.</span></span> <span data-ttu-id="d0597-139">Para aproveitar o carregamento automático de módulo, um módulo de script precisa ser salvo em uma pasta com o mesmo nome de base que o arquivo de `.PSM1` e em um local especificado em `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="d0597-139">To take advantage of module autoloading, a script module needs to be saved in a folder with the same base name as the `.PSM1` file and in a location specified in `$env:PSModulePath`.</span></span>

```powershell
$env:PSModulePath
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\
Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsof
t SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="d0597-140">Os resultados são difíceis de ler.</span><span class="sxs-lookup"><span data-stu-id="d0597-140">The results are difficult to read.</span></span> <span data-ttu-id="d0597-141">Como os caminhos são separados por ponto e vírgula, você pode dividir os resultados para retornar cada caminho em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="d0597-141">Since the paths are separated by a semicolon, you can split the results to return each path on a separate line.</span></span> <span data-ttu-id="d0597-142">Isso facilita a leitura.</span><span class="sxs-lookup"><span data-stu-id="d0597-142">This makes them easier to read.</span></span>

```powershell
$env:PSModulePath -split ';'
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\Windows\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="d0597-143">Os três primeiros caminhos da lista são o padrão.</span><span class="sxs-lookup"><span data-stu-id="d0597-143">The first three paths in the list are the default.</span></span> <span data-ttu-id="d0597-144">Quando o SQL Server Management Studio foi instalado, ele adicionou o último caminho.</span><span class="sxs-lookup"><span data-stu-id="d0597-144">When SQL Server Management Studio was installed, it added the last path.</span></span> <span data-ttu-id="d0597-145">Para que o carregamento automático de módulo funcione, o arquivo de `MyScriptModule.psm1` precisa estar localizado em uma pasta chamada `MyScriptModule` diretamente dentro de um desses caminhos.</span><span class="sxs-lookup"><span data-stu-id="d0597-145">For module autoloading to work, the `MyScriptModule.psm1` file needs to be located in a folder named `MyScriptModule` directly inside one of those paths.</span></span>

<span data-ttu-id="d0597-146">Não tão rápido.</span><span class="sxs-lookup"><span data-stu-id="d0597-146">Not so fast.</span></span> <span data-ttu-id="d0597-147">Para mim, meu caminho de usuário atual não é o primeiro da lista.</span><span class="sxs-lookup"><span data-stu-id="d0597-147">For me, my current user path isn't the first one in the list.</span></span> <span data-ttu-id="d0597-148">Eu quase nunca uso esse caminho, pois eu faço logon no Windows com um usuário diferente daquele que eu uso para executar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0597-148">I almost never use that path since I log into Windows with a different user than the one I use to run PowerShell.</span></span> <span data-ttu-id="d0597-149">Isso significa que ele não está localizado na pasta meus documentos normais.</span><span class="sxs-lookup"><span data-stu-id="d0597-149">That means it's not located in my normal Documents folder.</span></span>

<span data-ttu-id="d0597-150">O segundo caminho é o caminho **AllUsers**.</span><span class="sxs-lookup"><span data-stu-id="d0597-150">The second path is the **AllUsers** path.</span></span> <span data-ttu-id="d0597-151">Esse é o local em que eu armazeno todos os meus módulos.</span><span class="sxs-lookup"><span data-stu-id="d0597-151">This is the location where I store all of my modules.</span></span>

<span data-ttu-id="d0597-152">O terceiro caminho está abaixo de `C:\Windows\System32`.</span><span class="sxs-lookup"><span data-stu-id="d0597-152">The third path is underneath `C:\Windows\System32`.</span></span> <span data-ttu-id="d0597-153">Somente a Microsoft deve armazenar módulos nesse local, pois ele reside na pasta de sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="d0597-153">Only Microsoft should be storing modules in that location since it resides within the operating systems folder.</span></span>

<span data-ttu-id="d0597-154">Depois que o arquivo de `.PSM1` estiver localizado no caminho correto, o módulo será carregado automaticamente quando um de seus comandos for chamado.</span><span class="sxs-lookup"><span data-stu-id="d0597-154">Once the `.PSM1` file is located in the correct path, the module will load automatically when one of its commands is called.</span></span>

## <a name="module-manifests"></a><span data-ttu-id="d0597-155">Manifestos de módulo</span><span class="sxs-lookup"><span data-stu-id="d0597-155">Module Manifests</span></span>

<span data-ttu-id="d0597-156">Todos os módulos devem ter um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-156">All modules should have a module manifest.</span></span> <span data-ttu-id="d0597-157">Um manifesto de módulo contém metadados sobre seu módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-157">A module manifest contains metadata about your module.</span></span>
<span data-ttu-id="d0597-158">A extensão de arquivo para um arquivo de manifesto de módulo é `.PSD1`.</span><span class="sxs-lookup"><span data-stu-id="d0597-158">The file extension for a module manifest file is `.PSD1`.</span></span> <span data-ttu-id="d0597-159">Nem todos os arquivos com uma extensão `.PSD1` são manifestos de módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-159">Not all files with a `.PSD1` extension are module manifests.</span></span> <span data-ttu-id="d0597-160">Eles também podem ser usados para armazenar a parte ambiental de uma configuração DSC, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="d0597-160">They can also be used for things such as storing the environmental portion of a DSC configuration.</span></span> <span data-ttu-id="d0597-161">`New-ModuleManifest` é usado para criar um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-161">`New-ModuleManifest` is used to create a module manifest.</span></span> <span data-ttu-id="d0597-162">**Path** é o único valor obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d0597-162">**Path** is the only value that's required.</span></span> <span data-ttu-id="d0597-163">No entanto, o módulo não funcionará se **RootModule** não for especificado.</span><span class="sxs-lookup"><span data-stu-id="d0597-163">However, the module won't work if **RootModule** isn't specified.</span></span> <span data-ttu-id="d0597-164">É uma boa ideia especificar o **Autor** e a **Descrição**, caso você decida carregar seu módulo para um repositório do NuGet com PowerShellGet, já que esses valores são necessários nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="d0597-164">It's a good idea to specify **Author** and **Description** in case you decide to upload your module to a NuGet repository with PowerShellGet since those values are required in that scenario.</span></span>

<span data-ttu-id="d0597-165">A versão de um módulo sem um manifesto é 0.0.</span><span class="sxs-lookup"><span data-stu-id="d0597-165">The version of a module without a manifest is 0.0.</span></span> <span data-ttu-id="d0597-166">Esse é um indício de que o módulo não tem um manifesto.</span><span class="sxs-lookup"><span data-stu-id="d0597-166">This is a dead giveaway that the module doesn't have a manifest.</span></span>

```powershell
Get-Module -Name MyScriptModule
```

```Output
ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Script     0.0        myscriptmodule                      {Get-MrComputerName, Get-MrP...
```

<span data-ttu-id="d0597-167">O manifesto do módulo pode ser criado com todas as informações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="d0597-167">The module manifest can be created with all of the recommended information.</span></span>

```powershell
New-ModuleManifest -Path $env:ProgramFiles\WindowsPowerShell\Modules\MyScriptModule\MyScriptModule.psd1 -RootModule MyScriptModule -Author 'Mike F Robbins' -Description 'MyScriptModule' -CompanyName 'mikefrobbins.com'
```

<span data-ttu-id="d0597-168">Se qualquer uma dessas informações for perdida durante a criação inicial do manifesto do módulo, ela poderá ser adicionada ou atualizada posteriormente usando `Update-ModuleManifest`.</span><span class="sxs-lookup"><span data-stu-id="d0597-168">If any of this information is missed during the initial creation of the module manifest, it can be added or updated later using `Update-ModuleManifest`.</span></span> <span data-ttu-id="d0597-169">Não recrie o manifesto usando `New-ModuleManifest` depois que ele já estiver criado, pois o GUID será alterado.</span><span class="sxs-lookup"><span data-stu-id="d0597-169">Don't recreate the manifest using `New-ModuleManifest` once it's already created because the GUID will change.</span></span>

## <a name="defining-public-and-private-functions"></a><span data-ttu-id="d0597-170">Como definir funções públicas e privadas</span><span class="sxs-lookup"><span data-stu-id="d0597-170">Defining Public and Private Functions</span></span>

<span data-ttu-id="d0597-171">Você pode ter funções auxiliares que talvez queira que sejam privadas e estejam acessíveis somente a outras funções dentro do módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-171">You may have helper functions that you may want to be private and only accessible by other functions within the module.</span></span> <span data-ttu-id="d0597-172">Elas não devem estar acessíveis aos usuários do seu módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-172">They are not intended to be accessible to users of your module.</span></span> <span data-ttu-id="d0597-173">Há algumas maneiras de fazer isso.</span><span class="sxs-lookup"><span data-stu-id="d0597-173">There are a couple of different ways to accomplish this.</span></span>

<span data-ttu-id="d0597-174">Se você não estiver seguindo as melhores práticas e tiver apenas um arquivo `.PSM1`, sua única opção será usar o cmdlet `Export-ModuleMember`.</span><span class="sxs-lookup"><span data-stu-id="d0597-174">If you're not following the best practices and only have a `.PSM1` file, then your only option is to use the `Export-ModuleMember` cmdlet.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}

Export-ModuleMember -Function Get-MrPSVersion
```

<span data-ttu-id="d0597-175">No exemplo anterior, somente a função `Get-MrPSVersion` está disponível para os usuários do seu módulo, mas a função `Get-MrComputerName` está disponível para outras funções dentro do próprio módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-175">In the previous example, only the `Get-MrPSVersion` function is available to the users of your module, but the `Get-MrComputerName` function is available to other functions within the module itself.</span></span>

```powershell
Get-Command -Module MyScriptModule

CommandType     Name                        Version    Source
-----------     ----                        -------    ------
Function        Get-MrPSVersion             1.0        MyScript...
```

<span data-ttu-id="d0597-176">Se você tiver adicionado um manifesto de módulo ao seu módulo (e você deve fazer isso), recomendo especificar as funções individuais que deseja exportar na seção **FunctionsToExport** do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-176">If you've added a module manifest to your module (and you should), then I recommend specifying the individual functions you want to export in the **FunctionsToExport** section of the module manifest.</span></span>

```powershell
FunctionsToExport = 'Get-MrPSVersion'
```

<span data-ttu-id="d0597-177">Não é necessário usar tanto `Export-ModuleMember` no arquivo `.PSM1` quanto a seção **FunctionsToExport** do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="d0597-177">It's not necessary to use both `Export-ModuleMember` in the `.PSM1` file and the **FunctionsToExport** section of the module manifest.</span></span> <span data-ttu-id="d0597-178">Um ou outro é suficiente.</span><span class="sxs-lookup"><span data-stu-id="d0597-178">One or the other is sufficient.</span></span>

## <a name="summary"></a><span data-ttu-id="d0597-179">Resumo</span><span class="sxs-lookup"><span data-stu-id="d0597-179">Summary</span></span>

<span data-ttu-id="d0597-180">Neste capítulo, você aprendeu a transformar suas funções em um módulo de script no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0597-180">In this chapter you've learned how to turn your functions into a script module in PowerShell.</span></span> <span data-ttu-id="d0597-181">Você também aprendeu algumas das práticas recomendadas para a criação de módulos de script, como a criação de um manifesto de módulo para o módulo de script.</span><span class="sxs-lookup"><span data-stu-id="d0597-181">You've also leaned some of the best practices for creating script modules such as creating a module manifest for your script module.</span></span>

## <a name="review"></a><span data-ttu-id="d0597-182">Revisão</span><span class="sxs-lookup"><span data-stu-id="d0597-182">Review</span></span>

1. <span data-ttu-id="d0597-183">Como criar um módulo de script no PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d0597-183">How do you create a script module in PowerShell?</span></span>
1. <span data-ttu-id="d0597-184">Por que é importante que suas funções usem um verbo aprovado?</span><span class="sxs-lookup"><span data-stu-id="d0597-184">Why is it important for your functions to use an approved verb?</span></span>
1. <span data-ttu-id="d0597-185">Como criar um manifesto de módulo no PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d0597-185">How do you create a module manifest in PowerShell?</span></span>
1. <span data-ttu-id="d0597-186">Quais são as duas opções para exportar apenas determinadas funções do seu módulo?</span><span class="sxs-lookup"><span data-stu-id="d0597-186">What are the two options for exporting only certain functions from your module?</span></span>
1. <span data-ttu-id="d0597-187">O que é necessário para que os módulos sejam carregados automaticamente quando um comando é chamado?</span><span class="sxs-lookup"><span data-stu-id="d0597-187">What is required for your modules to load automatically when a command is called?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="d0597-188">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="d0597-188">Recommended Reading</span></span>

- <span data-ttu-id="d0597-189">[Como criar módulos de script do PowerShell e manifestos de módulo][]</span><span class="sxs-lookup"><span data-stu-id="d0597-189">[How to Create PowerShell Script Modules and Module Manifests][]</span></span>
- <span data-ttu-id="d0597-190">[about_Modules][]</span><span class="sxs-lookup"><span data-stu-id="d0597-190">[about_Modules][]</span></span>
- <span data-ttu-id="d0597-191">[New-ModuleManifest][]</span><span class="sxs-lookup"><span data-stu-id="d0597-191">[New-ModuleManifest][]</span></span>
- <span data-ttu-id="d0597-192">[Export-ModuleMember][]</span><span class="sxs-lookup"><span data-stu-id="d0597-192">[Export-ModuleMember][]</span></span>

<!-- link references -->
[Como criar módulos de script do PowerShell e manifestos de módulo]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[How to Create PowerShell Script Modules and Module Manifests]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Export-ModuleMember]: /powershell/module/microsoft.powershell.core/export-modulemember
