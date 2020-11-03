---
description: Descreve como o PowerShell determina qual comando executar.
keywords: powershell, cmdlet
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: f777d8b627288dff37a166f6819d36d10ed5db37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195776"
---
# <a name="about-command-precedence"></a><span data-ttu-id="13a14-104">Sobre a precedência de comando</span><span class="sxs-lookup"><span data-stu-id="13a14-104">About Command Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="13a14-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="13a14-105">Short description</span></span>
<span data-ttu-id="13a14-106">Descreve como o PowerShell determina qual comando executar.</span><span class="sxs-lookup"><span data-stu-id="13a14-106">Describes how PowerShell determines which command to run.</span></span>

## <a name="long-description"></a><span data-ttu-id="13a14-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="13a14-107">Long description</span></span>

<span data-ttu-id="13a14-108">Precedência de comando descreve como o PowerShell determina qual comando deve ser executado quando uma sessão contém mais de um comando com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-108">Command precedence describes how PowerShell determines which command to run when a session contains more than one command with the same name.</span></span> <span data-ttu-id="13a14-109">Os comandos dentro de uma sessão podem ser ocultados ou substituídos por comandos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-109">Commands within a session can be hidden or replaced by commands with the same name.</span></span> <span data-ttu-id="13a14-110">Este artigo mostra como executar comandos ocultos e como evitar conflitos de nome de comando.</span><span class="sxs-lookup"><span data-stu-id="13a14-110">This article shows you how to run hidden commands and how to avoid command-name conflicts.</span></span>

## <a name="command-precedence"></a><span data-ttu-id="13a14-111">Precedência de comando</span><span class="sxs-lookup"><span data-stu-id="13a14-111">Command precedence</span></span>

<span data-ttu-id="13a14-112">Quando uma sessão do PowerShell inclui mais de um comando que tem o mesmo nome, o PowerShell determina qual comando deve ser executado usando as regras a seguir.</span><span class="sxs-lookup"><span data-stu-id="13a14-112">When a PowerShell session includes more than one command that has the same name, PowerShell determines which command to run by using the following rules.</span></span>

<span data-ttu-id="13a14-113">Se você especificar o caminho para um comando, o PowerShell executará o comando no local especificado pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="13a14-113">If you specify the path to a command, PowerShell runs the command at the location specified by the path.</span></span>

<span data-ttu-id="13a14-114">Por exemplo, o comando a seguir executa o script FindDocs.ps1 no diretório "C: \\ TechDocs":</span><span class="sxs-lookup"><span data-stu-id="13a14-114">For example, the following command runs the FindDocs.ps1 script in the "C:\\TechDocs" directory:</span></span>

```
C:\TechDocs\FindDocs.ps1
```

<span data-ttu-id="13a14-115">Como um recurso de segurança, o PowerShell não executa comandos executáveis (nativos), incluindo scripts do PowerShell, a menos que o comando esteja localizado em um caminho listado na variável de ambiente PATH `$env:path` ou a menos que você especifique o caminho para o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="13a14-115">As a security feature, PowerShell does not run executable (native) commands, including PowerShell scripts, unless the command is located in a path that is listed in the Path environment variable `$env:path` or unless you specify the path to the script file.</span></span>

<span data-ttu-id="13a14-116">Para executar um script que está no diretório atual, especifique o caminho completo ou digite um ponto `.\` para representar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="13a14-116">To run a script that is in the current directory, specify the full path, or type a dot `.\` to represent the current directory.</span></span>

<span data-ttu-id="13a14-117">Por exemplo, para executar o arquivo de FindDocs.ps1 no diretório atual, digite:</span><span class="sxs-lookup"><span data-stu-id="13a14-117">For example, to run the FindDocs.ps1 file in the current directory, type:</span></span>

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a><span data-ttu-id="13a14-118">Usando curingas na execução</span><span class="sxs-lookup"><span data-stu-id="13a14-118">Using wildcards in execution</span></span>

<span data-ttu-id="13a14-119">Você pode usar curingas na execução do comando.</span><span class="sxs-lookup"><span data-stu-id="13a14-119">You may use wildcards in command execution.</span></span> <span data-ttu-id="13a14-120">O uso de caracteres curinga também é conhecido como *mascaramento* .</span><span class="sxs-lookup"><span data-stu-id="13a14-120">Using wildcard characters is also known as *globbing* .</span></span>

<span data-ttu-id="13a14-121">O PowerShell executa um arquivo que tem uma correspondência de curinga, antes de uma correspondência literal.</span><span class="sxs-lookup"><span data-stu-id="13a14-121">PowerShell executes a file that has a wildcard match, before a literal match.</span></span>

<span data-ttu-id="13a14-122">Por exemplo, considere um diretório com os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="13a14-122">For example, consider a directory with the following files:</span></span>

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

<span data-ttu-id="13a14-123">Ambos os arquivos de script têm o mesmo conteúdo: `$MyInvocation.MyCommand.Path` .</span><span class="sxs-lookup"><span data-stu-id="13a14-123">Both script files have the same content: `$MyInvocation.MyCommand.Path`.</span></span>
<span data-ttu-id="13a14-124">Esse comando exibe o nome do script que é invocado.</span><span class="sxs-lookup"><span data-stu-id="13a14-124">This command displays the name of the script that is invoked.</span></span>

<span data-ttu-id="13a14-125">Quando você executa `[a1].ps1` o, o arquivo `a.ps1` é executado, embora o arquivo `[a1].ps1` seja uma correspondência literal.</span><span class="sxs-lookup"><span data-stu-id="13a14-125">When you run `[a1].ps1`, the file `a.ps1` is executed even though the file `[a1].ps1` is a literal match.</span></span>

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

<span data-ttu-id="13a14-126">Agora, vamos excluir o `a.ps1` arquivo e tentar executá-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="13a14-126">Now let's delete the `a.ps1` file and attempt to run it again.</span></span>

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

<span data-ttu-id="13a14-127">Você pode ver na saída que `[a1].ps1` é executada desta vez porque a correspondência literal é a única correspondência de arquivo para esse padrão de curinga.</span><span class="sxs-lookup"><span data-stu-id="13a14-127">You can see from the output that `[a1].ps1` runs this time because the literal match is the only file match for that wildcard pattern.</span></span>

<span data-ttu-id="13a14-128">Para obter mais informações sobre como o PowerShell usa curingas, consulte [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="13a14-128">For more information about how PowerShell uses wildcards, see [about_Wildcards](about_Wildcards.md).</span></span>

> [!NOTE]
> <span data-ttu-id="13a14-129">Para limitar a pesquisa a um caminho relativo, você deve prefixar o nome do script com o `.\` caminho.</span><span class="sxs-lookup"><span data-stu-id="13a14-129">To limit the search to a relative path, you must prefix the script name with the `.\` path.</span></span> <span data-ttu-id="13a14-130">Isso limita a pesquisa de comandos para arquivos nesse caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="13a14-130">This limits the search for commands to files in that relative path.</span></span> <span data-ttu-id="13a14-131">Sem esse prefixo, outra sintaxe do PowerShell pode entrar em conflito e há algumas garantias de que o arquivo será encontrado.</span><span class="sxs-lookup"><span data-stu-id="13a14-131">Without this prefix, other PowerShell syntax may conflict and there are few guarantees that the file will be found.</span></span>

<span data-ttu-id="13a14-132">Se você não especificar um caminho, o PowerShell usará a seguinte ordem de precedência quando executar comandos para todos os itens carregados na sessão atual:</span><span class="sxs-lookup"><span data-stu-id="13a14-132">If you do not specify a path, PowerShell uses the following precedence order when it runs commands for all items loaded in the current session:</span></span>

  1. <span data-ttu-id="13a14-133">Alias</span><span class="sxs-lookup"><span data-stu-id="13a14-133">Alias</span></span>
  2. <span data-ttu-id="13a14-134">Função</span><span class="sxs-lookup"><span data-stu-id="13a14-134">Function</span></span>
  3. <span data-ttu-id="13a14-135">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="13a14-135">Cmdlet</span></span>
  4. <span data-ttu-id="13a14-136">Arquivos executáveis externos (programas e scripts não PowerShell)</span><span class="sxs-lookup"><span data-stu-id="13a14-136">External executable files (programs and non-PowerShell scripts)</span></span>

<span data-ttu-id="13a14-137">Portanto, se você digitar "Help", o PowerShell primeiro procura um alias chamado `help` , depois uma função chamada `Help` e, finalmente, um cmdlet chamado `Help` .</span><span class="sxs-lookup"><span data-stu-id="13a14-137">Therefore, if you type "help", PowerShell first looks for an alias named `help`, then a function named `Help`, and finally a cmdlet named `Help`.</span></span> <span data-ttu-id="13a14-138">Ele executa o primeiro `help` item que encontra.</span><span class="sxs-lookup"><span data-stu-id="13a14-138">It runs the first `help` item that it finds.</span></span>

<span data-ttu-id="13a14-139">Por exemplo, se sua sessão contiver um cmdlet e uma função, ambos nomeados `Get-Map` , quando você digitar `Get-Map` , o PowerShell executará a função.</span><span class="sxs-lookup"><span data-stu-id="13a14-139">For example, if your session contains a cmdlet and a function, both named `Get-Map`, when you type `Get-Map`, PowerShell runs the function.</span></span>

> [!NOTE]
> <span data-ttu-id="13a14-140">Isso se aplica somente a comandos carregados.</span><span class="sxs-lookup"><span data-stu-id="13a14-140">This only applies to loaded commands.</span></span> <span data-ttu-id="13a14-141">Se houver um `build` executável e um alias `build` para uma função com o nome de `Invoke-Build` dentro de um módulo que não é carregado na sessão atual, o PowerShell executará o `build` executável em vez disso.</span><span class="sxs-lookup"><span data-stu-id="13a14-141">If there is a `build` executable and an Alias `build` for a function with the name of `Invoke-Build` inside a module that is not loaded into the current session, PowerShell runs the `build` executable instead.</span></span> <span data-ttu-id="13a14-142">Ele não carregará os módulos automaticamente se encontrar o executável externo nesse caso.</span><span class="sxs-lookup"><span data-stu-id="13a14-142">It does not auto-load modules if it finds the external executable in this case.</span></span> <span data-ttu-id="13a14-143">Só quando nenhum executável externo é encontrado, um alias, uma função ou um cmdlet com o nome fornecido é invocado, disparando assim o carregamento automático de seu módulo.</span><span class="sxs-lookup"><span data-stu-id="13a14-143">It is only when no external executable is found that an alias, function, or cmdlet with the given name is invoked, thereby triggering auto-loading of its module.</span></span>

<span data-ttu-id="13a14-144">Quando a sessão contém itens do mesmo tipo que têm o mesmo nome, o PowerShell executa o item mais recente.</span><span class="sxs-lookup"><span data-stu-id="13a14-144">When the session contains items of the same type that have the same name, PowerShell runs the newer item.</span></span>

<span data-ttu-id="13a14-145">Por exemplo, se você importar outro `Get-Date` cmdlet de um módulo, ao digitar `Get-Date` , o PowerShell executará a versão importada no nativo.</span><span class="sxs-lookup"><span data-stu-id="13a14-145">For example, if you import another `Get-Date` cmdlet from a module, when you type `Get-Date`, PowerShell runs the imported version over the native one.</span></span>

## <a name="hidden-and-replaced-items"></a><span data-ttu-id="13a14-146">Itens ocultos e substituídos</span><span class="sxs-lookup"><span data-stu-id="13a14-146">Hidden and replaced items</span></span>

<span data-ttu-id="13a14-147">Como resultado dessas regras, os itens podem ser substituídos ou ocultados por itens com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-147">As a result of these rules, items can be replaced or hidden by items with the same name.</span></span>

<span data-ttu-id="13a14-148">Os itens serão "ocultos" ou "sombreados" se você ainda puder acessar o item original, como qualificando o nome do item com um módulo ou nome de snap-in.</span><span class="sxs-lookup"><span data-stu-id="13a14-148">Items are "hidden" or "shadowed" if you can still access the original item, such as by qualifying the item name with a module or snap-in name.</span></span>

<span data-ttu-id="13a14-149">Por exemplo, se você importar uma função que tem o mesmo nome de um cmdlet na sessão, o cmdlet será oculto (mas não substituído) porque foi importado de um snap-in ou módulo.</span><span class="sxs-lookup"><span data-stu-id="13a14-149">For example, if you import a function that has the same name as a cmdlet in the session, the cmdlet is hidden (but not replaced) because it was imported from a snap-in or module.</span></span>

<span data-ttu-id="13a14-150">Os itens são "substituídos" ou "sobrescritos" se você não puder mais acessar o item original.</span><span class="sxs-lookup"><span data-stu-id="13a14-150">Items are "replaced" or "overwritten" if you can no longer access the original item.</span></span>

<span data-ttu-id="13a14-151">Por exemplo, se você importar uma variável que tem o mesmo nome de uma variável na sessão, a variável original será substituída e não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="13a14-151">For example, if you import a variable that has the same name as a variable in the session, the original variable is replaced and is no longer accessible.</span></span>
<span data-ttu-id="13a14-152">Você não pode qualificar uma variável com um nome de módulo.</span><span class="sxs-lookup"><span data-stu-id="13a14-152">You cannot qualify a variable with a module name.</span></span>

<span data-ttu-id="13a14-153">Além disso, se você digitar uma função na linha de comando e, em seguida, importar uma função com o mesmo nome, a função original será substituída e não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="13a14-153">Also, if you type a function at the command line and then import a function with the same name, the original function is replaced and is no longer accessible.</span></span>

### <a name="finding-hidden-commands"></a><span data-ttu-id="13a14-154">Localizando comandos ocultos</span><span class="sxs-lookup"><span data-stu-id="13a14-154">Finding hidden commands</span></span>

<span data-ttu-id="13a14-155">O parâmetro **All** do cmdlet [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) Obtém todos os comandos com o nome especificado, mesmo se eles estiverem ocultos ou substituídos.</span><span class="sxs-lookup"><span data-stu-id="13a14-155">The **All** parameter of the [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlet gets all commands with the specified name, even if they are hidden or replaced.</span></span> <span data-ttu-id="13a14-156">A partir do PowerShell 3,0, por padrão, `Get-Command` obtém somente os comandos que são executados quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="13a14-156">Beginning in PowerShell 3.0, by default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="13a14-157">Nos exemplos a seguir, a sessão inclui uma `Get-Date` função e um cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) .</span><span class="sxs-lookup"><span data-stu-id="13a14-157">In the following examples, the session includes a `Get-Date` function and a [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet.</span></span>

<span data-ttu-id="13a14-158">O comando a seguir obtém o `Get-Date` comando que é executado quando você digita `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="13a14-158">The following command gets the `Get-Date` command that runs when you type `Get-Date`.</span></span>

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

<span data-ttu-id="13a14-159">O comando a seguir usa o parâmetro **All** para obter todos os `Get-Date` comandos.</span><span class="sxs-lookup"><span data-stu-id="13a14-159">The following command uses the **All** parameter to get all `Get-Date` commands.</span></span>

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a><span data-ttu-id="13a14-160">Executando comandos ocultos</span><span class="sxs-lookup"><span data-stu-id="13a14-160">Running hidden commands</span></span>

<span data-ttu-id="13a14-161">Você pode executar comandos específicos especificando propriedades de item que distinguem o comando de outros comandos que podem ter o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-161">You can run particular commands by specifying item properties that distinguish the command from other commands that might have the same name.</span></span> <span data-ttu-id="13a14-162">Você pode usar esse método para executar qualquer comando, mas ele é especialmente útil para executar comandos ocultos.</span><span class="sxs-lookup"><span data-stu-id="13a14-162">You can use this method to run any command, but it is especially useful for running hidden commands.</span></span>

#### <a name="qualified-names"></a><span data-ttu-id="13a14-163">Nomes qualificados</span><span class="sxs-lookup"><span data-stu-id="13a14-163">Qualified names</span></span>

<span data-ttu-id="13a14-164">O uso do nome qualificado por módulo de um cmdlet permite que você execute comandos ocultos por um item com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-164">Using the module-qualified name of a cmdlet allows you to run commands hidden by an item with the same name.</span></span> <span data-ttu-id="13a14-165">Por exemplo, você pode executar o `Get-Date` cmdlet qualificando-o com seu nome de módulo **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="13a14-165">For example, you can run the `Get-Date` cmdlet by qualifying it with its module name **Microsoft.PowerShell.Utility** .</span></span>

<span data-ttu-id="13a14-166">Use esse método preferido ao escrever scripts que você pretende distribuir.</span><span class="sxs-lookup"><span data-stu-id="13a14-166">Use this preferred method when writing scripts that you intend to distribute.</span></span> <span data-ttu-id="13a14-167">Você não pode prever quais comandos podem estar presentes na sessão em que o script é executado.</span><span class="sxs-lookup"><span data-stu-id="13a14-167">You cannot predict which commands might be present in the session in which the script runs.</span></span>

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

<span data-ttu-id="13a14-168">Para executar um `New-Map` comando que foi adicionado pelo `MapFunctions` módulo, use o nome qualificado do módulo:</span><span class="sxs-lookup"><span data-stu-id="13a14-168">To run a `New-Map` command that was added by the `MapFunctions` module, use its module-qualified name:</span></span>

```powershell
MapFunctions\New-Map
```

<span data-ttu-id="13a14-169">Para localizar o módulo do qual um comando foi importado, use a propriedade **ModuleName** de comandos.</span><span class="sxs-lookup"><span data-stu-id="13a14-169">To find the module from which a command was imported, use the **ModuleName** property of commands.</span></span>

```
(Get-Command <command-name>).ModuleName
```

<span data-ttu-id="13a14-170">Por exemplo, para localizar a origem do `Get-Date` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="13a14-170">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> <span data-ttu-id="13a14-171">Você não pode qualificar variáveis ou aliases.</span><span class="sxs-lookup"><span data-stu-id="13a14-171">You cannot qualify variables or aliases.</span></span>

#### <a name="call-operator"></a><span data-ttu-id="13a14-172">Operador de chamada</span><span class="sxs-lookup"><span data-stu-id="13a14-172">Call operator</span></span>

<span data-ttu-id="13a14-173">Você também pode usar o `Call` operador `&` para executar comandos ocultos, combinando-o com uma chamada para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (o alias é "dir") `Get-Command` ou [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="13a14-173">You can also use the `Call` operator `&` to run hidden commands by combining it with a call to [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (the alias is "dir"), `Get-Command` or [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

<span data-ttu-id="13a14-174">O operador de chamada executa cadeias de caracteres e blocos de script em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="13a14-174">The call operator executes strings and script blocks in a child scope.</span></span> <span data-ttu-id="13a14-175">Para obter mais informações, consulte [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="13a14-175">For more information, see [about_Operators](about_Operators.md).</span></span>

<span data-ttu-id="13a14-176">Por exemplo, se você tiver uma função chamada `Map` que é ocultada por um alias chamado `Map` , use o comando a seguir para executar a função.</span><span class="sxs-lookup"><span data-stu-id="13a14-176">For example, if you have a function named `Map` that is hidden by an alias named `Map`, use the following command to run the function.</span></span>

```powershell
&(Get-Command -Name Map -CommandType Function)
```

<span data-ttu-id="13a14-177">ou</span><span class="sxs-lookup"><span data-stu-id="13a14-177">or</span></span>

```powershell
&(dir Function:\map)
```

<span data-ttu-id="13a14-178">Você também pode salvar o comando oculto em uma variável para facilitar a execução.</span><span class="sxs-lookup"><span data-stu-id="13a14-178">You can also save your hidden command in a variable to make it easier to run.</span></span>

<span data-ttu-id="13a14-179">Por exemplo, o comando a seguir salva a `Map` função na `$myMap` variável e, em seguida, usa o `Call` operador para executá-la.</span><span class="sxs-lookup"><span data-stu-id="13a14-179">For example, the following command saves the `Map` function in the `$myMap` variable and then uses the `Call` operator to run it.</span></span>

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a><span data-ttu-id="13a14-180">Itens substituídos</span><span class="sxs-lookup"><span data-stu-id="13a14-180">Replaced items</span></span>

<span data-ttu-id="13a14-181">Um item "substituído" é aquele que você não pode mais acessar.</span><span class="sxs-lookup"><span data-stu-id="13a14-181">A "replaced" item is one that you can no longer access.</span></span> <span data-ttu-id="13a14-182">Você pode substituir itens Importando itens de mesmo nome de um módulo ou snap-in.</span><span class="sxs-lookup"><span data-stu-id="13a14-182">You can replace items by importing items of the same name from a module or snap-in.</span></span>

<span data-ttu-id="13a14-183">Por exemplo, se você digitar uma `Get-Map` função em sua sessão e importar uma função chamada `Get-Map` , ela substituirá a função original.</span><span class="sxs-lookup"><span data-stu-id="13a14-183">For example, if you type a `Get-Map` function in your session, and you import a function called `Get-Map`, it replaces the original function.</span></span> <span data-ttu-id="13a14-184">Você não pode recuperá-lo na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="13a14-184">You cannot retrieve it in the current session.</span></span>

<span data-ttu-id="13a14-185">Variáveis e aliases não podem ser ocultados porque você não pode usar um operador de chamada ou um nome qualificado para executá-los.</span><span class="sxs-lookup"><span data-stu-id="13a14-185">Variables and aliases cannot be hidden because you cannot use a call operator or a qualified name to run them.</span></span> <span data-ttu-id="13a14-186">Quando você importa variáveis e aliases de um módulo ou snap-in, eles substituem variáveis na sessão com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="13a14-186">When you import variables and aliases from a module or snap-in, they replace variables in the session with the same name.</span></span>

### <a name="avoiding-name-conflicts"></a><span data-ttu-id="13a14-187">Evitando conflitos de nome</span><span class="sxs-lookup"><span data-stu-id="13a14-187">Avoiding name conflicts</span></span>

<span data-ttu-id="13a14-188">A melhor maneira de gerenciar conflitos de nome de comando é impedi-los.</span><span class="sxs-lookup"><span data-stu-id="13a14-188">The best way to manage command name conflicts is to prevent them.</span></span> <span data-ttu-id="13a14-189">Ao nomear seus comandos, use um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="13a14-189">When you name your commands, use a unique name.</span></span> <span data-ttu-id="13a14-190">Por exemplo, adicione as iniciais ou o acrônimo de nome da empresa aos substantivos em seus comandos.</span><span class="sxs-lookup"><span data-stu-id="13a14-190">For example, add your initials or company name acronym to the nouns in your commands.</span></span>

<span data-ttu-id="13a14-191">Além disso, quando você importa comandos para a sessão de um módulo do PowerShell ou de outra sessão, use o `Prefix` parâmetro do [módulo importar/](xref:Microsoft.PowerShell.Core.Import-Module) ou</span><span class="sxs-lookup"><span data-stu-id="13a14-191">Also, when you import commands into your session from a PowerShell module or from another session, use the `Prefix` parameter of the [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) or</span></span>

<span data-ttu-id="13a14-192">Cmdlet [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) para adicionar um prefixo aos substantivos nos nomes de comandos.</span><span class="sxs-lookup"><span data-stu-id="13a14-192">[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) cmdlet to add a prefix to the nouns in the names of commands.</span></span>

<span data-ttu-id="13a14-193">Por exemplo, o comando a seguir evita qualquer conflito com os `Get-Date` `Set-Date` cmdlets e que acompanham o PowerShell quando você importa o `DateFunctions` módulo.</span><span class="sxs-lookup"><span data-stu-id="13a14-193">For example, the following command avoids any conflict with the `Get-Date` and `Set-Date` cmdlets that come with PowerShell when you import the `DateFunctions` module.</span></span>

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

<span data-ttu-id="13a14-194">Para obter mais informações, consulte `Import-Module` e `Import-PSSession` abaixo.</span><span class="sxs-lookup"><span data-stu-id="13a14-194">For more information, see `Import-Module` and `Import-PSSession` below.</span></span>

## <a name="see-also"></a><span data-ttu-id="13a14-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="13a14-195">See also</span></span>

- [<span data-ttu-id="13a14-196">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="13a14-196">about_Path_Syntax</span></span>](about_Path_Syntax.md)
- [<span data-ttu-id="13a14-197">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="13a14-197">about_Aliases</span></span>](about_Aliases.md)
- [<span data-ttu-id="13a14-198">about_Functions</span><span class="sxs-lookup"><span data-stu-id="13a14-198">about_Functions</span></span>](about_Functions.md)
- [<span data-ttu-id="13a14-199">Alias-Provider</span><span class="sxs-lookup"><span data-stu-id="13a14-199">Alias-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [<span data-ttu-id="13a14-200">Function-Provider</span><span class="sxs-lookup"><span data-stu-id="13a14-200">Function-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [<span data-ttu-id="13a14-201">Get-Command</span><span class="sxs-lookup"><span data-stu-id="13a14-201">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="13a14-202">Import-Module</span><span class="sxs-lookup"><span data-stu-id="13a14-202">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="13a14-203">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="13a14-203">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)
