---
title: Novidades no PowerShell 7.0
description: Novos recursos e alterações lançados no PowerShell 7.0
ms.date: 03/04/2020
ms.openlocfilehash: 6915bb70d6e54da86d2b935e3feed8d7f3770ba9
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78404990"
---
# <a name="whats-new-in-powershell-70"></a><span data-ttu-id="1e5ae-103">Novidades no PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="1e5ae-103">What's New in PowerShell 7.0</span></span>

<span data-ttu-id="1e5ae-104">O PowerShell 7.0 é uma edição do PowerShell que é open-source, multiplataforma (Windows, macOS e Linux) e criada para ambientes heterogêneos e nuvem híbrida.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-104">PowerShell 7.0 is an open-source, cross-platform (Windows, macOS, and Linux) edition of PowerShell, built to manage heterogeneous environments and hybrid cloud.</span></span>

<span data-ttu-id="1e5ae-105">Nessa versão, apresentamos uma série de novos recursos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-105">In this release, we're introducing a number of new features, including:</span></span>

- <span data-ttu-id="1e5ae-106">Paralelização de pipeline com `ForEach-Object -Parallel`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-106">Pipeline parallelization with `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="1e5ae-107">Novos operadores:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-107">New operators:</span></span>
  - <span data-ttu-id="1e5ae-108">Operador ternário: `a ? b : c`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-108">Ternary operator: `a ? b : c`</span></span>
  - <span data-ttu-id="1e5ae-109">Operadores de cadeia de pipeline: `||` e `&&`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-109">Pipeline chain operators: `||` and `&&`</span></span>
  - <span data-ttu-id="1e5ae-110">Operadores condicionais nulos: `??` e `??=`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-110">Null conditional operators: `??` and `??=`</span></span>
- <span data-ttu-id="1e5ae-111">Uma exibição de erro simplificada e dinâmica e cmdlet `Get-Error` para facilitar a investigação de erros</span><span class="sxs-lookup"><span data-stu-id="1e5ae-111">A simplified and dynamic error view and `Get-Error` cmdlet for easier investigation of errors</span></span>
- <span data-ttu-id="1e5ae-112">Uma camada de compatibilidade que permite aos usuários importar módulos em uma sessão implícita do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e5ae-112">A compatibility layer that enables users to import modules in an implicit Windows PowerShell session</span></span>
- <span data-ttu-id="1e5ae-113">Notificações automáticas de nova versão</span><span class="sxs-lookup"><span data-stu-id="1e5ae-113">Automatic new version notifications</span></span>
- <span data-ttu-id="1e5ae-114">A capacidade de invocar recursos de DSC diretamente do PowerShell 7 (experimental)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-114">The ability to invoke DSC resources directly from PowerShell 7 (experimental)</span></span>

<span data-ttu-id="1e5ae-115">Para ver uma lista completa de recursos e correções, confira os [logs de alterações](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-115">To see a full list of features and fixes, see the [changelogs](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span></span>

## <a name="where-can-i-install-powershell"></a><span data-ttu-id="1e5ae-116">Onde posso instalar o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1e5ae-116">Where can I install PowerShell?</span></span>

<span data-ttu-id="1e5ae-117">Atualmente, o PowerShell 7 dá suporte aos seguintes sistemas operacionais em x64, incluindo:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-117">PowerShell 7 currently supports the following operating systems on x64, including:</span></span>

- <span data-ttu-id="1e5ae-118">Windows 8.1 e 10</span><span class="sxs-lookup"><span data-stu-id="1e5ae-118">Windows 8.1, and 10</span></span>
- <span data-ttu-id="1e5ae-119">Windows Server 2012, 2012 R2, 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="1e5ae-119">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>
- <span data-ttu-id="1e5ae-120">macOS 10.13 ou posterior</span><span class="sxs-lookup"><span data-stu-id="1e5ae-120">macOS 10.13+</span></span>
- <span data-ttu-id="1e5ae-121">RHEL (Red Hat Enterprise Linux) / CentOS 7</span><span class="sxs-lookup"><span data-stu-id="1e5ae-121">Red Hat Enterprise Linux (RHEL) / CentOS 7</span></span>
- <span data-ttu-id="1e5ae-122">Fedora 30 ou posterior</span><span class="sxs-lookup"><span data-stu-id="1e5ae-122">Fedora 30+</span></span>
- <span data-ttu-id="1e5ae-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="1e5ae-123">Debian 9</span></span>
- <span data-ttu-id="1e5ae-124">Ubuntu LTS 16.04 ou posterior</span><span class="sxs-lookup"><span data-stu-id="1e5ae-124">Ubuntu LTS 16.04+</span></span>
- <span data-ttu-id="1e5ae-125">Alpine Linux 3.8 ou posterior</span><span class="sxs-lookup"><span data-stu-id="1e5ae-125">Alpine Linux 3.8+</span></span>

<span data-ttu-id="1e5ae-126">Além disso, o PowerShell 7.0 oferece suporte às variantes ARM32 e ARM64 do Debian, Ubuntu e ARM64 Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-126">Additionally, PowerShell 7.0 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="1e5ae-127">Confira as instruções de instalação do seu sistema operacional preferencial [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7) ou [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-127">Check the installation instructions for your preferred operating system [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7), or [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7).</span></span>

<span data-ttu-id="1e5ae-128">Embora não tenha suporte oficial, a comunidade também forneceu pacotes para o [Arch](https://aur.archlinux.org/packages/powershell/) e o Kali Linux.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-128">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-129">Atualmente, o Debian 10 e o CentOS 8 não dão suporte à comunicação remota do WinRM.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-129">Debian 10 and CentOS 8 currently do not support WinRM remoting.</span></span> <span data-ttu-id="1e5ae-130">Para obter detalhes sobre como configurar a comunicação remota baseada em SSH, confira [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-130">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7).</span></span>

<span data-ttu-id="1e5ae-131">Para obter informações mais atualizadas sobre os sistemas operacionais com suporte e o ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-131">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle?view=powershell-7).</span></span>

## <a name="running-powershell-7"></a><span data-ttu-id="1e5ae-132">Executar o PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="1e5ae-132">Running PowerShell 7</span></span>

<span data-ttu-id="1e5ae-133">O PowerShell 7 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-133">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e5ae-134">Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-134">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>

- <span data-ttu-id="1e5ae-135">O PowerShell 7 é instalado em `%programfiles%\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-135">PowerShell 7 is installed to `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="1e5ae-136">A pasta `%programfiles%\PowerShell\7` é adicionada ao `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-136">The `%programfiles%\PowerShell\7` folder is added to `$env:PATH`</span></span>

<span data-ttu-id="1e5ae-137">Os pacotes do instalador do PowerShell 7 atualizam versões anteriores do PowerShell Core 6.x:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-137">The PowerShell 7 installer packages upgrade previous versions of PowerShell Core 6.x:</span></span>

- <span data-ttu-id="1e5ae-138">PowerShell Core 6.x no Windows: `%programfiles%\PowerShell\6` é substituído por `%programfiles%\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-138">PowerShell Core 6.x on Windows: `%programfiles%\PowerShell\6` is replaced by `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="1e5ae-139">Linux: `/opt/microsoft/powershell/6` é substituído por `/opt/microsoft/powershell/7`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-139">Linux: `/opt/microsoft/powershell/6` is replaced by `/opt/microsoft/powershell/7`</span></span>
- <span data-ttu-id="1e5ae-140">macOS: `/usr/local/microsoft/powershell/6` é substituído por `/usr/local/microsoft/powershell/7`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-140">macOS: `/usr/local/microsoft/powershell/6` is replaced by `/usr/local/microsoft/powershell/7`</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-141">No Windows PowerShell, o executável para iniciar o PowerShell é denominado `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-141">In Windows PowerShell, the executable to launch PowerShell is named `powershell.exe`.</span></span> <span data-ttu-id="1e5ae-142">Na versão 6 e posterior, o executável é alterado para dar suporte à execução lado a lado.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-142">In version 6 and above, the executable is changed to support side-by-side execution.</span></span> <span data-ttu-id="1e5ae-143">O novo executável para iniciar o PowerShell 7 é `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-143">The new executable to launch PowerShell 7 is `pwsh.exe`.</span></span> <span data-ttu-id="1e5ae-144">Os builds de versão prévia permanecerão no local como `pwsh-preview` em vez de `pwsh` no diretório 7-preview.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-144">Preview builds will remain in-place as `pwsh-preview` instead of `pwsh` under the 7-preview directory.</span></span>

## <a name="improved-backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="1e5ae-145">Melhor compatibilidade com versões anteriores do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e5ae-145">Improved backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="1e5ae-146">O PowerShell 7.0 marca uma mudança para o .NET Core 3.1, permitindo significativamente mais compatibilidade com os módulos existentes do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-146">PowerShell 7.0 marks a move a to .NET Core 3.1, enabling significantly more backwards compatibility with existing Windows PowerShell modules.</span></span> <span data-ttu-id="1e5ae-147">Isso inclui muitos módulos no Windows que exigem funcionalidade da GUI, como `Out-GridView` e `Show-Command`, bem como muitos módulos de gerenciamento de funções fornecidos como parte do Windows.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-147">This includes many modules on Windows that require GUI functionality like `Out-GridView` and `Show-Command`, as well as many role management modules that ship as part of Windows.</span></span>

<span data-ttu-id="1e5ae-148">Para o Windows, um novo parâmetro de opção **UseWindowsPowerShell** é adicionado ao `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-148">For Windows, a new switch parameter **UseWindowsPowerShell** is added to `Import-Module`.</span></span> <span data-ttu-id="1e5ae-149">Essa opção cria um módulo proxy no PowerShell 7 que usa um processo local do Windows PowerShell para executar implicitamente todos os cmdlets contidos nesse módulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-149">This switch creates a proxy module in PowerShell 7 that uses a local Windows PowerShell process to implicitly run any cmdlets contained in that module.</span></span> <span data-ttu-id="1e5ae-150">Saiba mais informações sobre [ Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-150">For more information on [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7).</span></span>

<span data-ttu-id="1e5ae-151">Para obter mais informações sobre quais módulos da Microsoft funcionam com o PowerShell 7.0, confira a [Tabela de Compatibilidade de Módulos](https://aka.ms/PSModuleCompat).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-151">For more information on which Microsoft modules work with PowerShell 7.0, see the [Module Compatibility Table](https://aka.ms/PSModuleCompat).</span></span>

## <a name="parallel-execution-added-to-foreach-object"></a><span data-ttu-id="1e5ae-152">Execução paralela adicionada ao ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="1e5ae-152">Parallel execution added to ForEach-Object</span></span>

<span data-ttu-id="1e5ae-153">O cmdlet `ForEach-Object`, que itera itens em uma coleção, agora possui paralelismo interno com o novo parâmetro **Parallel**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-153">The `ForEach-Object` cmdlet, which iterates items in a collection, now has built-in parallelism with the new **Parallel** parameter.</span></span>

<span data-ttu-id="1e5ae-154">Por padrão, os blocos de script paralelos usam o diretório de trabalho atual do chamador que iniciou as tarefas paralelas.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-154">By default, parallel script blocks use the current working directory of the caller that started the parallel tasks.</span></span>

<span data-ttu-id="1e5ae-155">Este exemplo recupera 50.000 entradas de log de 5 logs do sistema em um computador Windows local:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-155">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine:</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count

50000
```

<span data-ttu-id="1e5ae-156">O parâmetro **Parallel** especifica o bloco de script que é executado em paralelo para cada nome de log de entrada.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-156">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span>

<span data-ttu-id="1e5ae-157">O novo parâmetro **ThrottleLimit** limita o número de blocos de script em execução paralelamente em determinado momento.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-157">The new **ThrottleLimit** parameter limits the number of script blocks running in parallel at a given time.</span></span> <span data-ttu-id="1e5ae-158">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-158">The default is 5.</span></span>

<span data-ttu-id="1e5ae-159">Use a variável `$_` para representar o objeto de entrada atual no bloco de script.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-159">Use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="1e5ae-160">Use o escopo `$using:` para passar referências de variáveis ao bloco de script em execução.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-160">Use the `$using:` scope to pass variable references to the running script block.</span></span>

<span data-ttu-id="1e5ae-161">Saiba mais informações sobre [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-161">For more information about [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7).</span></span>

## <a name="ternary-operator"></a><span data-ttu-id="1e5ae-162">Operador ternário</span><span class="sxs-lookup"><span data-stu-id="1e5ae-162">Ternary operator</span></span>

<span data-ttu-id="1e5ae-163">O PowerShell 7.0 apresenta um operador ternário que se comporta como uma instrução simplificada `if-else`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-163">PowerShell 7.0 introduces a ternary operator which behaves like a simplified `if-else` statement.</span></span>
<span data-ttu-id="1e5ae-164">O operador ternário do PowerShell é modelado de perto a partir da sintaxe do operador ternário em C#:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-164">PowerShell's ternary operator is closely modeled from the C# ternary operator syntax:</span></span>

```
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="1e5ae-165">A expressão de condição é sempre avaliada, e seu resultado é convertido em um **booliano** para determinar qual branch é avaliado a seguir:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-165">The condition-expression is always evaluated and its result converted to a **Boolean** to determine which branch is evaluated next:</span></span>

- <span data-ttu-id="1e5ae-166">A expressão `<if-true>` será executada se a expressão `<condition>` for verdadeira</span><span class="sxs-lookup"><span data-stu-id="1e5ae-166">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="1e5ae-167">A expressão `<if-false>` será executada se a expressão `<condition>` for falsa</span><span class="sxs-lookup"><span data-stu-id="1e5ae-167">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="1e5ae-168">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-168">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="1e5ae-169">Nesse exemplo, se o caminho existir, **Caminho existente** será exibido.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-169">In this example, if the path exists, then **Path exists** is displayed.</span></span> <span data-ttu-id="1e5ae-170">Se o caminho não existir, **Caminho não encontrado** será exibido.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-170">If the path does not exist, then **Path not found** is displayed.</span></span>

<span data-ttu-id="1e5ae-171">Saiba mais informações sobre [About If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-171">For more information [About If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7).</span></span>

## <a name="pipeline-chain-operators"></a><span data-ttu-id="1e5ae-172">Operadores de cadeia de pipeline</span><span class="sxs-lookup"><span data-stu-id="1e5ae-172">Pipeline chain operators</span></span>

<span data-ttu-id="1e5ae-173">O PowerShell 7 implementa os operadores `&&` e `||` para encadear pipelines condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-173">PowerShell 7 implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="1e5ae-174">Esses operadores são conhecidos no PowerShell como "operadores de cadeia de pipeline" e são semelhantes às listas AND e OR em shells como **Bash** e **Zsh**, além de símbolos de processamento condicional no Shell de Comando do Windows (**cmd.exe**).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-174">These operators are known in PowerShell as "pipeline chain operators", and are similar to AND and OR lists in shells like **Bash** and **Zsh**, as well as conditional processing symbols in the Windows Command Shell (**cmd.exe**).</span></span>

<span data-ttu-id="1e5ae-175">O operador `&&` executa o pipeline à direita, se o pipeline à esquerda foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-175">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="1e5ae-176">Por outro lado, o operador `||` executa o pipeline à direita, se o pipeline à esquerda falhou.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-176">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-177">Esses operadores usam as variáveis `$?` e `$LASTEXITCODE` para determinar se um pipeline falhou.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-177">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="1e5ae-178">Isso permite que você os utilize com comandos nativos, e não apenas com cmdlets ou funções.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-178">This allows you to use them with native commands and not just with cmdlets or functions.</span></span>

<span data-ttu-id="1e5ae-179">Aqui, o primeiro comando é bem-sucedido, e o segundo comando é executado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-179">Here, the first command succeeds and the second command is executed:</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

<span data-ttu-id="1e5ae-180">Aqui, o primeiro comando falha, o segundo não é executado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-180">Here, the first command fails, the second is not executed:</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

<span data-ttu-id="1e5ae-181">Aqui, o primeiro comando é bem-sucedido, o segundo comando não é executado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-181">Here, the first command succeeds, the second command is not executed:</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

<span data-ttu-id="1e5ae-182">Aqui, o primeiro comando falha, então o segundo comando é executado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-182">Here, the first command fails, so the second command is executed:</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error 'Bad'
Second
```

<span data-ttu-id="1e5ae-183">Saiba mais informações [Sobre operadores de cadeia de pipeline](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-183">For more information [About Pipeline Chain Operators](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7).</span></span>

## <a name="null-coalescing-assignment-and-conditional-operators"></a><span data-ttu-id="1e5ae-184">Operadores de avaliação de nulo, de atribuição e condicionais</span><span class="sxs-lookup"><span data-stu-id="1e5ae-184">Null-coalescing, assignment, and conditional operators</span></span>

<span data-ttu-id="1e5ae-185">O PowerShell 7 inclui o operador de avaliação de nulo `??`, atribuição condicional nula `??=` e operadores de acesso de membro condicional nulo `?.` e `?[]`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-185">PowerShell 7 includes Null coalescing operator `??`, Null conditional assignment `??=`, and Null conditional member access operators `?.` and `?[]`.</span></span>

### <a name="null-coalescing-operator-"></a><span data-ttu-id="1e5ae-186">Operador de avaliação de nulo??</span><span class="sxs-lookup"><span data-stu-id="1e5ae-186">Null-coalescing Operator ??</span></span>

<span data-ttu-id="1e5ae-187">O operador de avaliação de nulo `??` retorna o valor do seu operando esquerdo caso não seja nulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-187">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span>
<span data-ttu-id="1e5ae-188">Caso contrário, ele avalia o operando do lado direito e retorna seu resultado.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-188">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="1e5ae-189">O operador `??` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-189">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
100
```

<span data-ttu-id="1e5ae-190">No seguinte exemplo, o operando à direita não será avaliado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-190">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-assignment-operator-"></a><span data-ttu-id="1e5ae-191">Operador de atribuição condicional nula ?? =</span><span class="sxs-lookup"><span data-stu-id="1e5ae-191">Null conditional assignment operator ??=</span></span>

<span data-ttu-id="1e5ae-192">O operador de atribuição condicional nula `??=` atribuirá o valor de seu operando do lado direito para seu operando esquerdo somente se o operando esquerdo for avaliado como nulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-192">The null conditional assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="1e5ae-193">O operador `??=` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-193">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
100
```

<span data-ttu-id="1e5ae-194">No seguinte exemplo, o operando à direita não será avaliado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-194">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-member-access-operators--and--experimental"></a><span data-ttu-id="1e5ae-195">Operadores de acesso de membro condicional nulo ?.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-195">Null conditional member access operators ?.</span></span> <span data-ttu-id="1e5ae-196">e ?[] (Experimental)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-196">and ?[] (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-197">Este é um recurso experimental chamado **PSNullConditionalOperators**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-197">This is an experimental feature named **PSNullConditionalOperators**.</span></span> <span data-ttu-id="1e5ae-198">Saiba mais [Sobre os recursos experimentais](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-198">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="1e5ae-199">Um operador condicional nulo permitirá acesso de membro `?.` ou acesso de elemento `?[]` ao seu operando somente se esse operando for avaliado como não nulo; caso contrário, ele retornará nulo.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-199">A null conditional operator permits member access, `?.`, or element access, `?[]`, to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-200">Como o PowerShell permite que `?` faça parte do nome da variável, é necessária uma especificação formal do nome da variável para usar esses operadores.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-200">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="1e5ae-201">Portanto, é necessário usar `{}` em torno dos nomes de variáveis, como `${a}` ou quando `?` faz parte do nome da variável `${a?}`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-201">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="1e5ae-202">No seguinte exemplo, o valor da propriedade membro **Status** é retornado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-202">In the following example, the value of the member property **Status** is returned:</span></span>

```powershell
$Service = Get-Service -Name 'bits'
${Service}?.status
Stopped
```

<span data-ttu-id="1e5ae-203">O seguinte exemplo retornará nulo, sem tentar acessar o nome do membro **Status**:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-203">The following example will return null, without trying to access the member name **Status**:</span></span>

```powershell
$service = $Null
${Service}?.status
```

<span data-ttu-id="1e5ae-204">Da mesma forma, usando `?[]`, o valor do elemento será retornado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-204">Similarly, using `?[]`, the value of the element will be returned:</span></span>

```powershell
$a = 1..10
${a}?[0]
1
```

<span data-ttu-id="1e5ae-205">Quando o operando é nulo, o elemento não é acessado, e nulo é retornado:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-205">And when the operand is null, the element isn't accessed and null is returned:</span></span>

```powershell
$a = $null
${a}?[0]
```

<span data-ttu-id="1e5ae-206">Saiba mais informações [Sobre operadores](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-206">For more information [About_Operators](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7).</span></span>

## <a name="new-view-conciseview-and-cmdlet-get-error"></a><span data-ttu-id="1e5ae-207">Novo modo de exibição ConciseView e cmdlet Get-Error</span><span class="sxs-lookup"><span data-stu-id="1e5ae-207">New view ConciseView and cmdlet Get-Error</span></span>

<span data-ttu-id="1e5ae-208">A exibição das mensagens de erro foi aprimorada para melhorar a legibilidade dos erros interativos e de script com um novo modo de exibição padrão **ConciseView**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-208">The display of error messages has been improved to enhance the readability of interactive and script errors with a new default view **ConciseView**.</span></span> <span data-ttu-id="1e5ae-209">Os modos de exibição são selecionáveis pelo usuário por meio da variável de preferência `$ErrorView`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-209">The views are user-selectable through the preference variable `$ErrorView`.</span></span>

<span data-ttu-id="1e5ae-210">Com **ConciseView**, se um erro não for de script ou do analisador, será exibida uma mensagem de erro de linha única:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-210">With **ConciseView**, if an error is not from a script or parser error, then it's a single line error message:</span></span>

```powershell
Get-Childitem -Path c:\NotReal
```

```Output
Get-ChildItem: Cannot find path 'C:\NotReal' because it does not exist
```

<span data-ttu-id="1e5ae-211">Se o erro ocorrer durante a execução do script ou for um erro de análise, o PowerShell retornará uma mensagem de erro de várias linhas que contém o erro, um ponteiro e uma mensagem mostrando onde o erro está nessa linha.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-211">If the error occurs during script execution or is a parsing error, PowerShell returns a multiline error message that contains the error, a pointer and error message showing where the error is in that line.</span></span> <span data-ttu-id="1e5ae-212">Se o terminal não oferecer suporte a sequências de escape de cor ANSI (VT100), as cores não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-212">If the terminal doesn't support ANSI color escape sequences (VT100), then colors are not displayed.</span></span>

![Exibição de erro de um script](./media/What-s-New-in-PowerShell-70/myscript-error.png)

<span data-ttu-id="1e5ae-214">O modo de exibição padrão no PowerShell 7 é **ConciseView**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-214">The default view in PowerShell 7 is **ConciseView**.</span></span> <span data-ttu-id="1e5ae-215">O modo de exibição padrão anterior era  **NormalView**, selecionável pelo usuário ao definir a variável de preferência `$ErrorView`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-215">The previous default view was **NormalView** and is user selectable by setting the preference variable `$ErrorView`.</span></span>

```powershell
$ErrorView = 'NormalView' # Sets the error view to NormalView
$ErrorView = 'ConciseView' # Sets the error view to ConciseView
```

> [!NOTE]
> <span data-ttu-id="1e5ae-216">Uma nova propriedade **ErrorAccentColor** é adicionada a `$Host.PrivateData` para dar suporte à alteração da cor de destaque da mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-216">A new property **ErrorAccentColor** is added to `$Host.PrivateData` to support changing the accent color of the error message.</span></span>

<span data-ttu-id="1e5ae-217">Um novo cmdlet `Get-Error` fornece uma exibição detalhada completa do erro totalmente qualificado quando desejado.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-217">A new cmdlet `Get-Error` provides complete detailed view of the fully qualified error when desired.</span></span>
<span data-ttu-id="1e5ae-218">Por padrão, o cmdlet exibe os detalhes completos, incluindo as exceções internas, do último erro que ocorreu.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-218">By default the cmdlet displays the full details, including inner exceptions, of the last error that occurred.</span></span>

![Exibir de Get-Error](./media/What-s-New-in-PowerShell-70/myscript-geterror.png)

<span data-ttu-id="1e5ae-220">O cmdlet `Get-Error` dá suporte à entrada do pipeline usando a variável interna `$Error`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-220">The `Get-Error` cmdlet supports input from the pipeline using the built-in variable `$Error`.</span></span>
<span data-ttu-id="1e5ae-221">`Get-Error` exibe todos os erros direcionados.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-221">`Get-Error` displays all piped errors.</span></span>

```powershell
$Error | Get-Error
```

<span data-ttu-id="1e5ae-222">O cmdlet `Get-Error` dá suporte ao parâmetro **Newest**, permitindo especificar quantos erros da sessão atual você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-222">The `Get-Error` cmdlet supports the **Newest** parameter, allowing you to specify how many errors from the current session you wish displayed.</span></span>

```powershell
Get-Error -Newest 3 # Displays the lst three errors that occurred in the session
```

<span data-ttu-id="1e5ae-223">Saiba mais informações sobre [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-223">For more information about [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7).</span></span>

## <a name="new-version-notification"></a><span data-ttu-id="1e5ae-224">Notificação de nova versão</span><span class="sxs-lookup"><span data-stu-id="1e5ae-224">New version notification</span></span>

<span data-ttu-id="1e5ae-225">O PowerShell 7 usa notificações de atualização para alertar os usuários sobre a existência de atualizações no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-225">PowerShell 7 uses update notifications to alert users to the existence of updates to PowerShell.</span></span>
<span data-ttu-id="1e5ae-226">Uma vez por dia, o PowerShell consulta um serviço online para determinar se uma versão mais recente está disponível.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-226">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-227">A verificação de atualização ocorre durante a primeira sessão em determinado período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-227">The update check happens during the first session in a given 24-hour period.</span></span> <span data-ttu-id="1e5ae-228">Por motivos de desempenho, a verificação de atualização é iniciada três segundos após o início da sessão.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-228">For performance reasons, the update check starts 3 seconds after the session begins.</span></span> <span data-ttu-id="1e5ae-229">A notificação é mostrada apenas no início das sessões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-229">The notification is shown only on the start of subsequent sessions.</span></span>

<span data-ttu-id="1e5ae-230">Por padrão, o PowerShell assina um dos dois canais de notificação diferentes dependendo de sua versão/branch.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-230">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="1e5ae-231">As versões GA (em disponibilidade geral) com suporte do PowerShell retornam apenas notificações para versões GA atualizadas.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-231">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="1e5ae-232">As versões RC (Release Candidate) e Versão prévia notificam atualizações para RC, GA e versão prévia.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-232">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="1e5ae-233">O comportamento da notificação de atualização pode ser alterado usando a variável de ambiente `$Env:POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-233">The update notification behavior can be changed using the `$Env:POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="1e5ae-234">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-234">The following values are supported:</span></span>

- <span data-ttu-id="1e5ae-235">**Padrão** é o mesmo que não definir `$Env:POWERSHELL_UPDATECHECK`</span><span class="sxs-lookup"><span data-stu-id="1e5ae-235">**Default** is the same as not defining `$Env:POWERSHELL_UPDATECHECK`</span></span>
  - <span data-ttu-id="1e5ae-236">As versões GA notificam atualizações de versões GA</span><span class="sxs-lookup"><span data-stu-id="1e5ae-236">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="1e5ae-237">As versões RC/Versão prévia notificam atualizações de GA e versão prévia</span><span class="sxs-lookup"><span data-stu-id="1e5ae-237">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="1e5ae-238">**Desativar** desativa o recurso de notificação de atualização</span><span class="sxs-lookup"><span data-stu-id="1e5ae-238">**Off** turns off the update notification feature</span></span>
- <span data-ttu-id="1e5ae-239">**LTS** notifica apenas sobre atualizações de versões GA de LTS (manutenção em longo prazo)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-239">**LTS** only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-240">A variável de ambiente `$Env:POWERSHELL_UPDATECHECK` não existe até que seja definida pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-240">The environment variable `$Env:POWERSHELL_UPDATECHECK` does not exist until it is set for the first time.</span></span>

<span data-ttu-id="1e5ae-241">Para definir a notificação de versão apenas para versões `LTS`:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-241">To set the version notification for `LTS` releases only:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'LTS'
```

<span data-ttu-id="1e5ae-242">Para definir a notificação de versão para o comportamento `Default`:</span><span class="sxs-lookup"><span data-stu-id="1e5ae-242">To set the version notification to the `Default` behavior:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'Default'
```

<span data-ttu-id="1e5ae-243">Saiba mais informações [Sobre notificações de atualização](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-243">For more information [About Update Notifications](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7).</span></span>

## <a name="new-dsc-resource-support-with-invoke-dscresource-experimental"></a><span data-ttu-id="1e5ae-244">Novo suporte a recursos DSC com Invoke-DSCResource (experimental)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-244">New DSC Resource support with Invoke-DSCResource (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ae-245">Este é um recurso experimental chamado **PSDesiredStateConfiguration.InvokeDscResource**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-245">This is an experimental feature named **PSDesiredStateConfiguration.InvokeDscResource**.</span></span> <span data-ttu-id="1e5ae-246">Saiba mais [Sobre os recursos experimentais](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-246">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="1e5ae-247">O cmdlet `Invoke-DscResource` executa um método de um recurso de DSC (Desired State Configuration) do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-247">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="1e5ae-248">Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-248">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="1e5ae-249">Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows ou o Linux usando recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-249">Using this cmdlet, configuration management products can manage Windows or Linux by using DSC resources.</span></span> <span data-ttu-id="1e5ae-250">Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC está em execução com a depuração habilitada.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-250">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

<span data-ttu-id="1e5ae-251">Esse comando invoca o método **Set** de um recurso chamado log e especifica uma propriedade **Message**.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-251">This command invokes the **Set** method of a resource named Log and specifies a **Message** property.</span></span>

```powershell
Invoke-DscResource -Name Log -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Message = 'Hello World'
}
```

<span data-ttu-id="1e5ae-252">Saiba mais informações sobre [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="1e5ae-252">For more information about [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7).</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="1e5ae-253">Alterações de falha e melhorias</span><span class="sxs-lookup"><span data-stu-id="1e5ae-253">Breaking Changes and Improvements</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="1e5ae-254">Alterações de quebra</span><span class="sxs-lookup"><span data-stu-id="1e5ae-254">Breaking Changes</span></span>

- <span data-ttu-id="1e5ae-255">Dar suporte à notificação de atualização para canais padrão e LTS (nº 11132)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-255">Make update notification support LTS and default channels (#11132)</span></span>
- <span data-ttu-id="1e5ae-256">Atualizar Test-Connection para funcionar mais como a do Windows PowerShell (nº 10697) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-256">Update Test-Connection to work more like the one in Windows PowerShell (#10697) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-257">Preservar $?</span><span class="sxs-lookup"><span data-stu-id="1e5ae-257">Preserve $?</span></span> <span data-ttu-id="1e5ae-258">para ParenExpression, SubExpression e ArrayExpression (nº 11040)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-258">for ParenExpression, SubExpression and ArrayExpression (#11040)</span></span>
- <span data-ttu-id="1e5ae-259">Definir o diretório de trabalho para o diretório atual em Start-Job (nº 10920) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-259">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-260">Fazer $PSCulture refletir consistentemente as alterações de cultura na sessão (nº 10138) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-260">Make $PSCulture consistently reflect in-session culture changes (#10138) (Thanks @iSazonov!)</span></span>

### <a name="engine-updates-and-fixes"></a><span data-ttu-id="1e5ae-261">Atualizações e correções do mecanismo</span><span class="sxs-lookup"><span data-stu-id="1e5ae-261">Engine Updates and Fixes</span></span>

- <span data-ttu-id="1e5ae-262">Melhorias nas APIs de ponto de interrupção para cenários remotos (nº 11312)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-262">Improvements in breakpoint APIs for remote scenarios (#11312)</span></span>
- <span data-ttu-id="1e5ae-263">Corrigir vazamento de definição de classe do PowerShell em outro Runspace (nº 11273)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-263">Fix PowerShell class definition leaking into another Runspace (#11273)</span></span>
- <span data-ttu-id="1e5ae-264">Corrigir uma regressão na formatação causada pelo primitivo FirstOrDefault adicionado em 7.0.0-Preview1 (nº 11258)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-264">Fix a regression in formatting caused by the FirstOrDefault primitive added in 7.0.0-Preview1 (#11258)</span></span>
- <span data-ttu-id="1e5ae-265">Módulos adicionais da Microsoft para acompanhar na Telemetria PS7 (nº 10751)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-265">Additional Microsoft Modules to track in PS7 Telemetry (#10751)</span></span>
- <span data-ttu-id="1e5ae-266">Tornar os recursos aprovados não experimentais (nº 11303)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-266">Make approved features non-experimental (#11303)</span></span>
- <span data-ttu-id="1e5ae-267">Atualizar ConciseView para usar TargetObject se aplicável (nº 11075)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-267">Update ConciseView to use TargetObject if applicable (#11075)</span></span>
- <span data-ttu-id="1e5ae-268">Corrigir NullReferenceException em métodos públicos CompletionCompleters (nº 11274)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-268">Fix NullReferenceException in CompletionCompleters public methods (#11274)</span></span>
- <span data-ttu-id="1e5ae-269">Corrigir verificação do estado do thread apartment em plataformas não Windows (nº 11301)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-269">Fix apartment thread state check on non-Windows platforms (#11301)</span></span>
- <span data-ttu-id="1e5ae-270">Atualizar a configuração PSModulePath para concatenar as variáveis de ambiente de processo e computador (nº 11276)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-270">Update setting PSModulePath to concatenate the process and machine environment variables (#11276)</span></span>
- <span data-ttu-id="1e5ae-271">Elevar o .NET Core para 3.1.0 (nº 11260)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-271">Bump .NET Core to 3.1.0 (#11260)</span></span>
- <span data-ttu-id="1e5ae-272">Corrigir a detecção de $PSHOME na frente de $env:PATH (nº 11141)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-272">Fix detection of $PSHOME in front of $env:PATH (#11141)</span></span>
- <span data-ttu-id="1e5ae-273">Permitir que pwsh herde $env:P SModulePath e habilite powerShell.exe para ser iniciado corretamente (nº 11057)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-273">Allow pwsh to inherit $env:PSModulePath and enable powershell.exe to start correctly (#11057)</span></span>
- <span data-ttu-id="1e5ae-274">Mover para a versão prévia 1 do .NET Core 3.1 (nº 10798)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-274">Move to .NET Core 3.1 preview 1 (#10798)</span></span>
- <span data-ttu-id="1e5ae-275">Refatorar verificações de marcas de nova análise no provedor do sistema de arquivos (nº 10431) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-275">Refactor reparse tag checks in file system provider (#10431) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-276">Substituir CR e nova linha por um caractere 0x23CE no registro em log de scripts (nº 10616)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-276">Replace CR and new line with a 0x23CE character in script logging (#10616)</span></span>
- <span data-ttu-id="1e5ae-277">Corrigir um vazamento de recurso ao cancelar o registro do manipulador de eventos de AppDomain.CurrentDomain.ProcessExit (nº 10626)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-277">Fix a resource leak by unregistering the event handler from AppDomain.CurrentDomain.ProcessExit (#10626)</span></span>
- <span data-ttu-id="1e5ae-278">Adicionar suporte a ActionPreference.Break para entrar no depurador quando forem geradas mensagens de depuração, erro, informações, progresso, detalhadas ou de aviso (nº 8205) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-278">Add support to ActionPreference.Break to break into debugger when Debug, Error, Information, Progress, Verbose or Warning messages are generated (#8205) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-279">Habilitar os suplementos iniciais do painel de controle no PowerShell Core sem especificar a extensão .CPL.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-279">Enable starting control panel add-ins within PowerShell Core without specifying .CPL extension.</span></span> <span data-ttu-id="1e5ae-280">(nº 9828)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-280">(#9828)</span></span>

### <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="1e5ae-281">Atualizações e correções gerais do Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1e5ae-281">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="1e5ae-282">Correção do problema no Raspbian para definir a data das alterações de arquivo no recurso experimental do UnixStat (nº 11313)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-282">Fix for issue on Raspbian for setting date of file changes in UnixStat Experimental Feature (#11313)</span></span>
- <span data-ttu-id="1e5ae-283">Adicionar -AsPlainText a ConvertFrom-SecureString (nº 11142)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-283">Add -AsPlainText to ConvertFrom-SecureString (#11142)</span></span>
- <span data-ttu-id="1e5ae-284">Adicionada verificação de versão do WindowsPS para WinCompat (nº 11148)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-284">Added WindowsPS version check for WinCompat (#11148)</span></span>
- <span data-ttu-id="1e5ae-285">Corrigir relatório de erros em alguns cenários do WinCompat (nº 11259)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-285">Fix error-reporting in some WinCompat scenarios (#11259)</span></span>
- <span data-ttu-id="1e5ae-286">Adicionar resolvedor binário nativo (nº 11032) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-286">Add native binary resolver (#11032) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-287">Atualizar o cálculo da largura de caractere para respeitar caracteres CJK corretamente (nº 11262)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-287">Update calculation of char width to respect CJK chars correctly (#11262)</span></span>
- <span data-ttu-id="1e5ae-288">Adicionar arquivo de desbloqueio para macOS (nº 11137)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-288">Add Unblock-File for macOS (#11137)</span></span>
- <span data-ttu-id="1e5ae-289">Corrigir regressão no Get-PSCallStack (nº 11210) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-289">Fix regression in Get-PSCallStack (#11210) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-290">Remover o carregamento automático do módulo ScheduledJob ao usar cmdlets Job (nº 11194)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-290">Remove autoloading of the ScheduledJob module when using Job cmdlets (#11194)</span></span>
- <span data-ttu-id="1e5ae-291">Adicionar OutputType ao cmdlet Get-Error e preservar os nomes de tipos originais (nº 10856)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-291">Add OutputType to Get-Error cmdlet and preserve original typenames (#10856)</span></span>
- <span data-ttu-id="1e5ae-292">Corrigir a referência nula na propriedade SupportsVirtualTerminal (nº 11105)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-292">Fix null reference in SupportsVirtualTerminal property (#11105)</span></span>
- <span data-ttu-id="1e5ae-293">Adicionar verificação de limite em Get-WinEvent (nº 10648) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-293">Add limit check in Get-WinEvent (#10648) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-294">Corrigir o runtime do comando para que StopUpstreamCommandsException não seja preenchido em ErrorVariable (nº 10840)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-294">Fix command runtime so StopUpstreamCommandsException doesn't get populated in -ErrorVariable (#10840)</span></span>
- <span data-ttu-id="1e5ae-295">Definir a codificação de saída como [Console]::OutputEncoding para comandos nativos (nº 10824)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-295">Set the output encoding to [Console]::OutputEncoding for native commands (#10824)</span></span>
- <span data-ttu-id="1e5ae-296">Suporte a blocos de código de várias linhas nos exemplos (nº 10776) (Obrigado, @Greg-Smulko!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-296">Support multi-line code blocks in examples (#10776) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="1e5ae-297">Adicionar o parâmetro Culture ao cmdlet Select-String (nº 10943) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-297">Add Culture parameter to Select-String cmdlet (#10943) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-298">Corrigir o caminho do diretório de trabalho Start-Job com barra invertida (nº 11041)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-298">Fix Start-Job working directory path with trailing backslash (#11041)</span></span>
- <span data-ttu-id="1e5ae-299">ConvertFrom-Json: Desencapsular coleções por padrão (nº 10861) (Obrigado, @danstur!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-299">ConvertFrom-Json: Unwrap collections by default (#10861) (Thanks @danstur!)</span></span>
- <span data-ttu-id="1e5ae-300">Usar Hashtable que diferencia maiúsculas de minúsculas para o cmdlet Group-Object com opções -CaseSensitive e -AsHashTable (nº 11030) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-300">Use case-sensitive Hashtable for Group-Object cmdlet with -CaseSensitive and -AsHashtable switches (#11030) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-301">Tratar exceção se a enumeração de arquivos falhar ao recompilar o caminho para ter a capitalização correta (nº 11014)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-301">Handle exception if enumerating files fails when rebuilding path to have correct casing (#11014)</span></span>
- <span data-ttu-id="1e5ae-302">Corrigir ConciseView para mostrar Activity em vez de myCommand (nº 11007)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-302">Fix ConciseView to show Activity instead of myCommand (#11007)</span></span>
- <span data-ttu-id="1e5ae-303">Permitir que cmdlets da Web ignorem status de erro HTTP (nº 10466) (Obrigado, @vdamewood!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-303">Allow web cmdlets to ignore HTTP error statuses (#10466) (Thanks @vdamewood!)</span></span>
- <span data-ttu-id="1e5ae-304">Corrigir o direcionamento de mais de um CommandInfo para Get-Command (nº 10929)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-304">Fix piping of more than one CommandInfo to Get-Command (#10929)</span></span>
- <span data-ttu-id="1e5ae-305">Adicionar novamente o cmdlet Get-Counter para Windows (nº 10933)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-305">Add back Get-Counter cmdlet for Windows (#10933)</span></span>
- <span data-ttu-id="1e5ae-306">Fazer ConvertTo-JSON tratar [AutomationNull]::Value e [NullString]::Value como $null (nº 10957)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-306">Make ConvertTo-Json treat [AutomationNull]::Value and [NullString]::Value as $null (#10957)</span></span>
- <span data-ttu-id="1e5ae-307">Remover os colchetes do endereço ipv6 para a comunicação remota SSH (nº 10968)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-307">Remove brackets from ipv6 address for SSH remoting (#10968)</span></span>
- <span data-ttu-id="1e5ae-308">Corrigir a falha se o comando enviado ao pwsh for apenas espaço em branco (nº 10977)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-308">Fix crash if command sent to pwsh is just whitespace (#10977)</span></span>
- <span data-ttu-id="1e5ae-309">Adicionar Get-Clipboard e Set-Clipboard de plataforma cruzada (nº 10340)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-309">Added cross-platform Get-Clipboard and Set-Clipboard (#10340)</span></span>
- <span data-ttu-id="1e5ae-310">Corrigir a configuração do caminho original do objeto do sistema de arquivos para não ter barra final (nº 10959)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-310">Fix setting original path of filesystem object to not have extra trailing slash (#10959)</span></span>
- <span data-ttu-id="1e5ae-311">Suporte a $null para ConvertTo-Json (nº 10947)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-311">Support $null for ConvertTo-Json (#10947)</span></span>
- <span data-ttu-id="1e5ae-312">Adicionar novamente o comando Out-Printer no Windows (nº 10906)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-312">Add back Out-Printer command on Windows (#10906)</span></span>
- <span data-ttu-id="1e5ae-313">Corrigir Start-Job-WorkingDirectory com espaço em branco (nº 10951)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-313">Fix Start-Job -WorkingDirectory with whitespace (#10951)</span></span>
- <span data-ttu-id="1e5ae-314">Retornar o valor padrão ao obter nulo para uma configuração em PSConfiguration.cs (nº 10963) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-314">Return default value when getting null for a setting in PSConfiguration.cs (#10963) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-315">Manipular a exceção de E/S como não finalizável (nº 10950)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-315">Handle IO exception as non-terminating (#10950)</span></span>
- <span data-ttu-id="1e5ae-316">Adicionar o assembly GraphicalHost para habilitar Out-GridView, Show-Command e Get-Help -ShowWindow (nº 10899)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-316">Add GraphicalHost assembly to enable Out-GridView, Show-Command, and Get-Help -ShowWindow (#10899)</span></span>
- <span data-ttu-id="1e5ae-317">Colocar ComputerName via pipeline em Get-HotFix (nº 10852) (Obrigado, @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-317">Take ComputerName via pipeline in Get-HotFix (#10852) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="1e5ae-318">Corrigir o preenchimento da guia para parâmetros para que ele mostre parâmetros comuns conforme disponíveis (nº 10850)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-318">Fix tab completion for parameters so that it shows common parameters as available (#10850)</span></span>
- <span data-ttu-id="1e5ae-319">Corrigir GetCorrectCasedPath() para primeiro verificar se alguma entrada de arquivo do sistema é retornada antes de chamar First() (nº 10930)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-319">Fix GetCorrectCasedPath() to first check if any system file entries is returned before calling First() (#10930)</span></span>
- <span data-ttu-id="1e5ae-320">Definir o diretório de trabalho para o diretório atual em Start-Job (nº 10920) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-320">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-321">Alterar TabExpansion2 para não exigir -CursorColumn e tratar como $InputScript.Length (nº 10849)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-321">Change TabExpansion2 to not require -CursorColumn and treat as $InputScript.Length (#10849)</span></span>
- <span data-ttu-id="1e5ae-322">Manipular caso em que o host não pode retornar linhas ou colunas de tela (nº 10938)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-322">Handle case where Host may not return Rows or Columns of screen (#10938)</span></span>
- <span data-ttu-id="1e5ae-323">Corrigir o uso de cores de destaque para hosts que não dão suporte a elas (nº 10937)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-323">Fix use of accent colors for hosts that don't support them (#10937)</span></span>
- <span data-ttu-id="1e5ae-324">Adicionar novamente o comando Update-List (nº 10922)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-324">Add back Update-List command (#10922)</span></span>
- <span data-ttu-id="1e5ae-325">Atualizar FWLink Id para Clear-RecycleBin (nº 10925)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-325">Update FWLink Id for Clear-RecycleBin (#10925)</span></span>
- <span data-ttu-id="1e5ae-326">Durante o preenchimento da guia, ignorar arquivo se não for possível ler atributos de arquivo (nº 10910)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-326">During tab completion, skip file if can't read file attributes (#10910)</span></span>
- <span data-ttu-id="1e5ae-327">Adicionar novamente Clear-RecycleBin para Windows (nº 10909)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-327">Add back Clear-RecycleBin for Windows (#10909)</span></span>
- <span data-ttu-id="1e5ae-328">Adicionar `$env:__SuppressAnsiEscapeSequences` para controlar se a sequência de escape VT deve ser adicionada na saída (nº 10814)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-328">Add `$env:__SuppressAnsiEscapeSequences` to control whether to have VT escape sequence in output (#10814)</span></span>
- <span data-ttu-id="1e5ae-329">Adicionar parâmetro -NoEmphasize para colorir a saída de Select-String (nº 8963) (Obrigado, @derek-xia!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-329">Add -NoEmphasize parameter to colorize Select-String output (#8963) (Thanks @derek-xia!)</span></span>
- <span data-ttu-id="1e5ae-330">Adicionar novamente o cmdlet Get-HotFix (nº 10740)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-330">Add back Get-HotFix cmdlet (#10740)</span></span>
- <span data-ttu-id="1e5ae-331">Tornar Add-Type utilizável em aplicativos que hospedam o PowerShell (nº 10587)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-331">Make Add-Type usable in applications that host PowerShell (#10587)</span></span>
- <span data-ttu-id="1e5ae-332">Usar uma ordem de avaliação mais efetiva em LanguagePrimitives.IsNullLike () (nº 10781) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-332">Use more effective evaluation order in LanguagePrimitives.IsNullLike() (#10781) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-333">Melhorar o tratamento de entrada direcionada de coleção mista e fluxos de entrada direcionados de entradas em Format-Hex (nº 8674) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-333">Improve handling of mixed-collection piped input and piped streams of input in Format-Hex (#8674) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-334">Usar a conversão de tipo nas hashtables SSHConnection quando o valor não corresponder ao tipo esperado (nº 10720) (Obrigado, @SeeminglyScience!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-334">Use type conversion in SSHConnection hashtables when value doesn't match expected type (#10720) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="1e5ae-335">Corrigir o comportamento de Get-Content-ReadCount 0 quando -TotalCount for definido (nº 10749) (Obrigado, @eugenesmlv!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-335">Fix Get-Content -ReadCount 0 behavior when -TotalCount is set (#10749) (Thanks @eugenesmlv!)</span></span>
- <span data-ttu-id="1e5ae-336">Reescrever mensagem de erro de acesso negado em Get-WinEvent (nº 10639) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-336">Reword access denied error message in Get-WinEvent (#10639) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-337">Ativar preenchimento de guia para atribuição de variável com enumeração ou tipo restrito (nº 10646)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-337">Enable tab completion for variable assignment that is enum or type constrained (#10646)</span></span>
- <span data-ttu-id="1e5ae-338">Remover a propriedade de comunicação remota do SourceLength não utilizada que causa problemas de formatação (nº 10765)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-338">Remove unused SourceLength remoting property causing formatting issues (#10765)</span></span>
- <span data-ttu-id="1e5ae-339">Adicionar parâmetro -Delimiter a ConvertFrom-StringData (nº 10665) (Obrigado, @steviecoaster!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-339">Add -Delimiter parameter to ConvertFrom-StringData (#10665) (Thanks @steviecoaster!)</span></span>
- <span data-ttu-id="1e5ae-340">Adicionar parâmetro posicional para ScriptBlock ao usar Invoke-Command com SSH (nº 10721) (Obrigado, @machgo!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-340">Add positional parameter for ScriptBlock when using Invoke-Command with SSH (#10721) (Thanks @machgo!)</span></span>
- <span data-ttu-id="1e5ae-341">Mostrar informações de contexto de linha se houver várias linhas, mas nenhum nome de script para ConciseView (nº 10746)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-341">Show line context information if multiple lines but no script name for ConciseView (#10746)</span></span>
- <span data-ttu-id="1e5ae-342">Adicionar suporte aos caminhos \\wsl$\ para o provedor do sistema de arquivos (nº 10674)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-342">Add support for \\wsl$\ paths to file system provider (#10674)</span></span>
- <span data-ttu-id="1e5ae-343">Adicionar o texto do token ausente a TokenKind.Question Mark no analisador (nº 10706)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-343">Add the missing token text for TokenKind.QuestionMark in parser (#10706)</span></span>
- <span data-ttu-id="1e5ae-344">Definir o diretório de trabalho atual de cada script ForEach-Object-Parallel em execução no mesmo local que o script de chamada.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-344">Set current working directory of each ForEach-Object -Parallel running script to the same location as the calling script.</span></span> <span data-ttu-id="1e5ae-345">(nº 10672)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-345">(#10672)</span></span>
- <span data-ttu-id="1e5ae-346">Substituir api-ms-win-core-file-l1-2-2.dll por Kernel32.dll em APIs FindFirst Stream e FindNextStreamW (nº 10680) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-346">Replace api-ms-win-core-file-l1-2-2.dll with Kernell32.dll for FindFirstStreamW and FindNextStreamW APIs (#10680) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-347">Ajustar o script de formatação de ajuda para ser mais tolerante ao StrictMode (nº 10563)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-347">Tweak help formatting script to be more StrictMode tolerant (#10563)</span></span>
- <span data-ttu-id="1e5ae-348">Adicionar parâmetro -SecurityDescriptorSDDL a New-Service (nº 10483) (Obrigado, @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-348">Add -SecurityDescriptorSDDL parameter to New-Service (#10483) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="1e5ae-349">Remover saída informativa, consolidar o uso de ping em Test-Connection (nº 10478) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-349">Remove informational output, consolidate ping usage in Test-Connection (#10478) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-350">Ler pontos de nova análise especiais sem acessá-los (nº 10662) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-350">Read special reparse points without accessing them (#10662) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-351">Direcionar saída Clear-Host para terminal (nº 10681) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-351">Direct Clear-Host output to terminal (#10681) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-352">Adicionar nova linha de volta para agrupar com Format-Table e -Property (nº 10653)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-352">Add back newline for grouping with Format-Table and -Property (#10653)</span></span>
- <span data-ttu-id="1e5ae-353">Remover [ValidateNotNullOrEmpty] de -InputObject em Get-Random para permitir cadeia de caracteres vazia (nº 10644)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-353">Remove [ValidateNotNullOrEmpty] from -InputObject on Get-Random to allow empty string (#10644)</span></span>
- <span data-ttu-id="1e5ae-354">Fazer com que o algoritmo de distância da string do sistema de sugestões não diferencie maiúsculas de minúsculas (nº 10549) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-354">Make suggestion system string distance algorithm case-insensitive (#10549) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-355">Corrigir exceção de referência nula no processamento de entrada de ForEach-Object -Parallel (nº 10577)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-355">Fix null reference exception in ForEach-Object -Parallel input processing (#10577)</span></span>
- <span data-ttu-id="1e5ae-356">Adicionar definições de política de grupo do PowerShell Core (nº 10468)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-356">Add PowerShell Core group policy definitions (#10468)</span></span>
- <span data-ttu-id="1e5ae-357">Atualizar o host do console para dar suporte às sequências de controle XTPUSHSGR/XTPOPSGR VT usadas em cenários de composição.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-357">Update console host to support XTPUSHSGR/XTPOPSGR VT control sequences that are used in composability scenarios.</span></span> <span data-ttu-id="1e5ae-358">(nº 10208)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-358">(#10208)</span></span>
- <span data-ttu-id="1e5ae-359">Adicionar o parâmetro WorkingDirectory a Start-Job (nº 10324) (Obrigado, @davinci26!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-359">Add WorkingDirectory parameter to Start-Job (#10324) (Thanks @davinci26!)</span></span>
- <span data-ttu-id="1e5ae-360">Remover o manipulador de eventos que estava fazendo com que as alterações no ponto de interrupção fossem replicadas erroneamente no depurador de runtime do host (nº 10503) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-360">Remove the event handler that was causing breakpoint changes to be erroneously replicated to the host runspace debugger (#10503) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-361">Substituir api-ms-win-core-job-12-1-0.dll por Kernell32.dll na API Microsoft.PowerShell.Commands.NativeMethods P/Invoke (nº 10417) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-361">Replace api-ms-win-core-job-12-1-0.dll with Kernell32.dll in Microsoft.PowerShell.Commands.NativeMethods P/Invoke API(#10417) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-362">Corrigir a saída errada para New-Service em atribuição de variável e -OutVariable (nº 10444) (Obrigado, @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-362">Fix wrong output for New-Service in variable assignment and -OutVariable (#10444) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="1e5ae-363">Corrigir problemas de ferramenta global em torno do código de saída, parâmetros de linha de comando e caminho com espaços (nº 10461)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-363">Fix global tool issues around exit code, command line parameters and path with spaces (#10461)</span></span>
- <span data-ttu-id="1e5ae-364">Corrigir recursão no OneDrive -change FindFirstFileEx() para usar o tipo SafeFindHandle (nº 10405)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-364">Fix recursion into OneDrive - change FindFirstFileEx() to use SafeFindHandle type (#10405)</span></span>
- <span data-ttu-id="1e5ae-365">Ignorar o PSReadLine de carregamento automático no Windows se o leitor de tela NVDA estiver ativo (nº 10385)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-365">Skip auto-loading PSReadLine on Windows if the NVDA screen reader is active (#10385)</span></span>
- <span data-ttu-id="1e5ae-366">Elevar as versões de módulos feitos com PowerShell para 7.0.0.0 (nº 10356)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-366">Increase built-with-PowerShell module versions to 7.0.0.0 (#10356)</span></span>
- <span data-ttu-id="1e5ae-367">Adicionar um erro no Add-Type se já existir um tipo com o mesmo nome (nº 9609) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-367">Add throwing an error in Add-Type if a type with the same name already exists (#9609) (Thanks @iSazonov!)</span></span>

### <a name="performance"></a><span data-ttu-id="1e5ae-368">Desempenho</span><span class="sxs-lookup"><span data-stu-id="1e5ae-368">Performance</span></span>

- <span data-ttu-id="1e5ae-369">Evitar o uso de fechamento em Parser.SaveError (nº 11006)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-369">Avoid using closure in Parser.SaveError (#11006)</span></span>
- <span data-ttu-id="1e5ae-370">Melhorar o cache ao criar novas instâncias de Regex (nº 10657) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-370">Improve the caching when creating new Regex instances (#10657) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-371">Melhorar o processamento dos dados de tipo interno do PowerShell de types.ps1xml, typesV3.ps1xml e GetEvent.types.ps1xml (nº 10898)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-371">Improve processing of the PowerShell built-in type data from types.ps1xml, typesV3.ps1xml and GetEvent.types.ps1xml (#10898)</span></span>
- <span data-ttu-id="1e5ae-372">Atualizar o PSConfiguration.ReadValueFromFile para torná-lo mais rápido e mais eficiente no uso de memória (nº 10839)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-372">Update PSConfiguration.ReadValueFromFile to make it faster and more memory efficient (#10839)</span></span>
- <span data-ttu-id="1e5ae-373">Adicionar pequenas melhorias de desempenho para a inicialização do runspace (nº 10569) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-373">Add minor performance improvements for runspace initialization (#10569) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-374">Tornar ForEach-Object mais rápido em seus cenários mais usados (nº 10454) e corrigir o problema de desempenho de ForEach-Object-Parallel com muitos runspaces (nº 10455)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-374">Make ForEach-Object faster for its commonly used scenarios (#10454) and fix ForEach-Object -Parallel performance problem with many runspaces (#10455)</span></span>

### <a name="code-cleanup"></a><span data-ttu-id="1e5ae-375">Limpeza de código</span><span class="sxs-lookup"><span data-stu-id="1e5ae-375">Code Cleanup</span></span>

- <span data-ttu-id="1e5ae-376">Alterar o comentário e o texto do elemento para atender aos padrões da Microsoft (nº 11304)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-376">Change comment and element text to meet Microsoft standards (#11304)</span></span>
- <span data-ttu-id="1e5ae-377">Limpar problemas de estilo no Compiler.cs (nº 10368) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-377">Cleanup style issues in Compiler.cs (#10368) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-378">Remover o conversor de tipo não utilizado para CommaDelimitedStringCollection (nº 11000) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-378">Remove the unused type converter for CommaDelimitedStringCollection (#11000) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-379">Limpar o estilo em InitialSessionState.cs (nº 10865) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-379">Cleanup style in InitialSessionState.cs (#10865) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-380">Limpeza de código para classe PSSession (nº 11001)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-380">Code clean up for PSSession class (#11001)</span></span>
- <span data-ttu-id="1e5ae-381">Remover o recurso "executar Update-Help de Get-Help quando Get-Help for executado pela primera vez", que não funciona (nº 10974)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-381">Remove the not-working 'run Update-Help from Get-Help when Get-Help runs for the first time' feature (#10974)</span></span>
- <span data-ttu-id="1e5ae-382">Corrigir problemas de estilo (nº 10998) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-382">Fix style issues (#10998) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-383">Limpeza: usar o alias de tipo interno (nº 10882) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-383">Cleanup: use the built-in type alias (#10882) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-384">Remover a chave de configuração não utilizada ConsolePrompting e evitar a criação desnecessária de cadeia de caracteres ao consultar a configuração ExecutionPolicy (nº 10985)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-384">Remove the unused setting key ConsolePrompting and avoid unnecessary string creation when querying ExecutionPolicy setting (#10985)</span></span>
- <span data-ttu-id="1e5ae-385">Desabilitar a verificação de notificação de atualização para builds diários (nº 10903) (Obrigado, @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-385">Disable update notification check for daily builds (#10903) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="1e5ae-386">Restabelecer API de depuração perdida em nº 10338 (nº 10808)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-386">Reinstate debugging API lost in #10338 (#10808)</span></span>
- <span data-ttu-id="1e5ae-387">Remover a referência de WorkflowJobSourceAdapter que não é mais usada (nº 10326) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-387">Remove WorkflowJobSourceAdapter reference that is no longer used (#10326) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-388">Limpar interfaces COM no código de lista de atalhos corrigindo atributos PreserveSig (nº 9899) (Obrigado, @weltkante!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-388">Cleanup COM interfaces in jump list code by fixing PreserveSig attributes (#9899) (Thanks @weltkante!)</span></span>
- <span data-ttu-id="1e5ae-389">Adicionar um comentário que descreve por que -ia não é o alias para o parâmetro comum -Informationaction (nº 10703) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-389">Add a comment describing why -ia is not the alias for -InformationAction common parameter (#10703) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-390">Renomear InvokeCommandCmdlet.cs para InvokeExpressionCommand.cs (nº 10659) (Obrigado, @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-390">Rename InvokeCommandCmdlet.cs to InvokeExpressionCommand.cs (#10659) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="1e5ae-391">Adicionar limpezas de código secundárias relacionadas às notificações de atualização (nº 10698)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-391">Add minor code cleanups related to update notifications (#10698)</span></span>
- <span data-ttu-id="1e5ae-392">Remover a lógica de fluxo de trabalho preterida dos scripts de configuração de comunicação remota (nº 10320) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-392">Remove deprecated workflow logic from the remoting setup scripts (#10320) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-393">Atualizar o formato de ajuda para usar maiúsculas e minúsculas corretamente (nº 10678) (Obrigado, @tnieto88!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-393">Update help format to use proper case (#10678) (Thanks @tnieto88!)</span></span>
- <span data-ttu-id="1e5ae-394">Limpar problemas de estilo de CodeFactor provenientes de commits no último mês (nº 10591) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-394">Clean up CodeFactor style issues coming in commits for the last month (#10591) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-395">Corrigir erro de digitação na descrição do recurso experimental PSTernaryOperator (nº 10586) (Obrigado, @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-395">Fix typo in description of PSTernaryOperator experimental feature (#10586) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="1e5ae-396">Converter o valor de enumeração ActionPreference.Suspend em um estado reservado sem suporte e remover a restrição do uso de ActionPreference.Ignore nas variáveis de preferência (nº 10317) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-396">Convert ActionPreference.Suspend enumeration value into a non-supported, reserved state, and remove restriction on using ActionPreference.Ignore in preference variables (#10317) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-397">Substituir ArrayList por List<T> para obter um código mais legível e confiável sem alterar a funcionalidade (nº 10333) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-397">Replace ArrayList with List<T> to get more readable and reliable code without changing functionality (#10333) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-398">Fazer correções de estilo de código em TestConnectionCommand (nº 10439) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-398">Make code style fixes to TestConnectionCommand (#10439) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-399">Limpar AutomationEngine e remover a chamada de método extra SetSessionStateDrive (nº 10416) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-399">Cleanup AutomationEngine and remove extra SetSessionStateDrive method call (#10416) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-400">Renomear ParameterSetName padrão de volta para Delimiter em ConvertTo-Csv e ConvertFrom-Csv (nº 10425)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-400">Rename default ParameterSetName back to Delimiter for ConvertTo-Csv and ConvertFrom-Csv (#10425)</span></span>

### <a name="tools"></a><span data-ttu-id="1e5ae-401">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="1e5ae-401">Tools</span></span>

- <span data-ttu-id="1e5ae-402">Adicionar a configuração padrão à propriedade SDKToUse para que ela seja criada no VS (nº 11085)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-402">Add default setting for the SDKToUse property so that it builds in VS (#11085)</span></span>
- <span data-ttu-id="1e5ae-403">Install-Powershell.ps1: Adicionar parâmetro para usar a instalação do MSI (nº 10921) (Obrigado, @MJECloud!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-403">Install-Powershell.ps1: Add parameter to use MSI installation (#10921) (Thanks @MJECloud!)</span></span>
- <span data-ttu-id="1e5ae-404">Adicionar exemplos básicos para install-powershell.ps1 (nº 10914) (Obrigado, @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-404">Add basic examples for install-powershell.ps1 (#10914) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="1e5ae-405">Fazer Install-PowerShellRemoting. ps1 manipular uma cadeia de caracteres vazia no parâmetro PowerShellHome (nº 10526) (Obrigado, @Orca88!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-405">Make Install-PowerShellRemoting.ps1 handle empty string in PowerShellHome parameter (#10526) (Thanks @Orca88!)</span></span>
- <span data-ttu-id="1e5ae-406">Alternar de /etc/lsb-release para /etc/os-release em install-powershell.sh (nº 10773) (Obrigado, @Himura2la!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-406">Switch from /etc/lsb-release to /etc/os-release in install-powershell.sh (#10773) (Thanks @Himura2la!)</span></span>
- <span data-ttu-id="1e5ae-407">Verificar pwsh. exe e pwsh na versão diária no Windows (nº 10738) (Obrigado, @centreboard!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-407">Check pwsh.exe and pwsh in daily version on Windows (#10738) (Thanks @centreboard!)</span></span>
- <span data-ttu-id="1e5ae-408">Remover toque desnecessário em installpsh-osx.sh (nº 10752)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-408">Remove unneeded tap in installpsh-osx.sh (#10752)</span></span>
- <span data-ttu-id="1e5ae-409">Atualize install-powershell.ps1 para verificar build diário já instalado (nº 10489)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-409">Update install-powershell.ps1 to check for already installed daily build (#10489)</span></span>

### <a name="tests"></a><span data-ttu-id="1e5ae-410">Testes</span><span class="sxs-lookup"><span data-stu-id="1e5ae-410">Tests</span></span>

- <span data-ttu-id="1e5ae-411">Tornar o teste de DSC não confiável pendente (nº 11131)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-411">Make unreliable DSC test pending (#11131)</span></span>
- <span data-ttu-id="1e5ae-412">Corrigir o teste de stringdata para validar corretamente as chaves das hashtables (nº 10810)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-412">Fix stringdata test to correctly validate keys of hashtables (#10810)</span></span>
- <span data-ttu-id="1e5ae-413">Descarregar módulos de teste (nº 11061) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-413">Unload test modules (#11061) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-414">Aumentar o tempo entre novas tentativas de teste de URL (nº 11015)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-414">Increase time between retries of testing URL (#11015)</span></span>
- <span data-ttu-id="1e5ae-415">Atualizar testes para descrever as ações de teste com precisão.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-415">Update tests to accurately describe test actions.</span></span> <span data-ttu-id="1e5ae-416">(nº 10928) (Obrigado, @romero126!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-416">(#10928) (Thanks @romero126!)</span></span>
- <span data-ttu-id="1e5ae-417">Pular temporariamente o teste instável TestAppDomainProcessExitEvenHandlerNotLeaking (nº 10827)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-417">Temporary skip the flaky test TestAppDomainProcessExitEvenHandlerNotLeaking (#10827)</span></span>
- <span data-ttu-id="1e5ae-418">Tornar estável o teste de vazamento do manipulador de eventos (nº 10790)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-418">Make the event handler leaking test stable (#10790)</span></span>
- <span data-ttu-id="1e5ae-419">Sincronizar o uso de maiúsculas no CI YAML (nº 10767) (Obrigado, @RDIL!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-419">Sync capitalization in CI YAML (#10767) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="1e5ae-420">Adicionar teste para a correção de vazamento do manipulador de eventos (nº 10768)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-420">Add test for the event handler leaking fix (#10768)</span></span>
- <span data-ttu-id="1e5ae-421">Adicionar teste Get-ChildItem (nº 10507) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-421">Add Get-ChildItem test (#10507) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-422">Substituir linguagem ambígua nos testes de opção para parâmetro para fins de precisão (nº 10666) (Obrigado, @romero126!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-422">Replace ambiguous language for tests from switch to parameter for accuracy (#10666) (Thanks @romero126!)</span></span>
- <span data-ttu-id="1e5ae-423">Adicionar verificação experimental a testes ForEach-Object -Parallel (nº 10354) (Obrigado, @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-423">Add experimental check to ForEach-Object -Parallel tests (#10354) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="1e5ae-424">Atualizar testes para a validação Alpine (nº 10428)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-424">Update tests for Alpine validation (#10428)</span></span>

### <a name="build-and-package-improvements"></a><span data-ttu-id="1e5ae-425">Melhorias de build e pacote</span><span class="sxs-lookup"><span data-stu-id="1e5ae-425">Build and Package Improvements</span></span>

- <span data-ttu-id="1e5ae-426">Corrigir assinatura de pacote Nuget para build de Pacote Coordenado (nº 11316)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-426">Fix Nuget package signing for Coordinated Package build (#11316)</span></span>
- <span data-ttu-id="1e5ae-427">Atualizar dependências da Galeria do PowerShell e NuGet (nº 11323)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-427">Update dependencies from PowerShell Gallery and NuGet (#11323)</span></span>
- <span data-ttu-id="1e5ae-428">Elevar Microsoft.ApplicationInsights de 2.11.0 para 2.12.0 (nº 11305)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-428">Bump Microsoft.ApplicationInsights from 2.11.0 to 2.12.0 (#11305)</span></span>
- <span data-ttu-id="1e5ae-429">Elevar Microsoft.CodeAnalysis.CSharp de 3.3.1 para 3.4.0 (nº 11265)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-429">Bump Microsoft.CodeAnalysis.CSharp from 3.3.1 to 3.4.0 (#11265)</span></span>
- <span data-ttu-id="1e5ae-430">Atualizar pacotes para Debian 10 e 11 (nº 11236)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-430">Updates packages for Debian 10 and 11 (#11236)</span></span>
- <span data-ttu-id="1e5ae-431">Habilitar apenas os recursos experimentais anteriores à versão RC (nº 11162)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-431">Only enable experimental features prior to RC (#11162)</span></span>
- <span data-ttu-id="1e5ae-432">Atualizar a versão mínima do macOS (nº 11163)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-432">Update macOS minimum version (#11163)</span></span>
- <span data-ttu-id="1e5ae-433">Elevar NJsonSchema de 10.0.27 para 10.0.28 (nº 11170)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-433">Bump NJsonSchema from 10.0.27 to 10.0.28 (#11170)</span></span>
- <span data-ttu-id="1e5ae-434">Atualizar links em README.md e metadata.json para Preview.5 (nº 10854)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-434">Updating links in README.md and metadata.json for Preview.5 (#10854)</span></span>
- <span data-ttu-id="1e5ae-435">Selecionar os arquivos para testes de conformidade que são de propriedade do PowerShell (nº 10837)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-435">Select the files for compliance tests which are owned by PowerShell (#10837)</span></span>
- <span data-ttu-id="1e5ae-436">Permitir que o pacote win7x86 msix seja compilado.</span><span class="sxs-lookup"><span data-stu-id="1e5ae-436">Allow win7x86 msix package to build.</span></span> <span data-ttu-id="1e5ae-437">(interno 10515)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-437">(Internal 10515)</span></span>
- <span data-ttu-id="1e5ae-438">Permitir que versões semânticas sejam passadas para a função NormalizeVersion (nº 11087)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-438">Allow semantic versions to be passed to NormalizeVersion function (#11087)</span></span>
- <span data-ttu-id="1e5ae-439">Elevar a estrutura do .NET Core para 3.1-preview.3 (nº 11079)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-439">Bump .NET core framework to 3.1-preview.3 (#11079)</span></span>
- <span data-ttu-id="1e5ae-440">Elevar PSReadLine de 2.0.0-beta5 para 2.0.0-beta6 in /src/Modules (nº 11078)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-440">Bump PSReadLine from 2.0.0-beta5 to 2.0.0-beta6 in /src/Modules (#11078)</span></span>
- <span data-ttu-id="1e5ae-441">Elevar Newparansoft.Json de 12.0.2 para 12.0.3 (nº 11037) (nº 11038)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-441">Bump Newtonsoft.Json from 12.0.2 to 12.0.3 (#11037) (#11038)</span></span>
- <span data-ttu-id="1e5ae-442">Adicionar pacotes Debian 10, 11 e CentOS 8 (nº 11028)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-442">Add Debian 10, 11 and CentOS 8 packages (#11028)</span></span>
- <span data-ttu-id="1e5ae-443">Carregar arquivo JSON Build-Info com o campo ReleaseDate (nº 10986)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-443">Upload Build-Info Json file with the ReleaseDate field (#10986)</span></span>
- <span data-ttu-id="1e5ae-444">Elevar estrutura do .NET Core para 3.1-preview.2 (nº 10993)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-444">Bump .NET core framework to 3.1-preview.2 (#10993)</span></span>
- <span data-ttu-id="1e5ae-445">Habilitar build do pacote MSIX x86 (nº 10934)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-445">Enable build of x86 MSIX package (#10934)</span></span>
- <span data-ttu-id="1e5ae-446">Atualizar a URL do script de instalação do dotnet SDK em build.psm1 (nº 10927)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-446">Update the dotnet SDK install script URL in build.psm1 (#10927)</span></span>
- <span data-ttu-id="1e5ae-447">Elevar Markdig.Signed de 0.17.1 para 0.18.0 (nº 10887)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-447">Bump Markdig.Signed from 0.17.1 to 0.18.0 (#10887)</span></span>
- <span data-ttu-id="1e5ae-448">Elevar ThreadJob de 2.0.1 para 2.0.2 (nº 10886)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-448">Bump ThreadJob from 2.0.1 to 2.0.2 (#10886)</span></span>
- <span data-ttu-id="1e5ae-449">Atualizar o módulo AppX Manifest and Packaging para ficar em conformidade com os requisitos da MS Store (nº 10878)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-449">Update AppX Manifest and Packaging module to conform to MS Store requirements (#10878)</span></span>
- <span data-ttu-id="1e5ae-450">Atualizar referência do pacote do PowerShell SDK para preview.5 (interno 10295)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-450">Update package reference for PowerShell SDK to preview.5 (Internal 10295)</span></span>
- <span data-ttu-id="1e5ae-451">Atualizar ThirdPartyNotices.txt (nº 10834)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-451">Update ThirdPartyNotices.txt (#10834)</span></span>
- <span data-ttu-id="1e5ae-452">Elevar Microsoft.PowerShell.Native para 7.0.0-preview.3 (nº 10826)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-452">Bump Microsoft.PowerShell.Native to 7.0.0-preview.3 (#10826)</span></span>
- <span data-ttu-id="1e5ae-453">Elevar Microsoft.ApplicationInsights de 2.10.0 para 2.11.0 (nº 10608)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-453">Bump Microsoft.ApplicationInsights from 2.10.0 to 2.11.0 (#10608)</span></span>
- <span data-ttu-id="1e5ae-454">Elevar NJsonSchema de 10.0.24 para 10.0.27 (nº 10756)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-454">Bump NJsonSchema from 10.0.24 to 10.0.27 (#10756)</span></span>
- <span data-ttu-id="1e5ae-455">Adicionar suporte a MacPorts ao sistema de build (nº 10736) (Obrigado, @Lucius-Q-User!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-455">Add MacPorts support to the build system (#10736) (Thanks @Lucius-Q-User!)</span></span>
- <span data-ttu-id="1e5ae-456">Elevar PackageManagement de 1.4.4 para 1.4.5 (nº 10728)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-456">Bump PackageManagement from 1.4.4 to 1.4.5 (#10728)</span></span>
- <span data-ttu-id="1e5ae-457">Elevar NJsonSchema de 10.0.23 para 10.0.24 (nº 10635)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-457">Bump NJsonSchema from 10.0.23 to 10.0.24 (#10635)</span></span>
- <span data-ttu-id="1e5ae-458">Adicionar variável de ambiente para diferenciar a telemetria de cliente/servidor no MSI (nº 10612)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-458">Add environment variable to differentiate client/server telemetry in MSI (#10612)</span></span>
- <span data-ttu-id="1e5ae-459">Elevar PSDesiredStateConfiguration de 2.0.3 para 2.0.4 (nº 10603)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-459">Bump PSDesiredStateConfiguration from 2.0.3 to 2.0.4 (#10603)</span></span>
- <span data-ttu-id="1e5ae-460">Elevar Microsoft.CodeAnalysis.CSharp de 3.2.1 para 3.3.1 (nº 10607)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-460">Bump Microsoft.CodeAnalysis.CSharp from 3.2.1 to 3.3.1 (#10607)</span></span>
- <span data-ttu-id="1e5ae-461">Atualizar para .Net Core 3.0 RTM (nº 10604) (Obrigado, @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-461">Update to .Net Core 3.0 RTM (#10604) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="1e5ae-462">Atualizar o pacote MSIX para que a versão atenda aos requisitos da Windows Store (nº 10588)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-462">Update MSIX packaging so the version to Windows Store requirements (#10588)</span></span>
- <span data-ttu-id="1e5ae-463">Elevar PowerShellGet de 2.2 para 2.2.1 (nº 10382)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-463">Bump PowerShellGet version from 2.2 to 2.2.1 (#10382)</span></span>
- <span data-ttu-id="1e5ae-464">Elevar PackageManagement de 1.4.3 para 1.4.4 (nº 10383)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-464">Bump PackageManagement version from 1.4.3 to 1.4.4 (#10383)</span></span>
- <span data-ttu-id="1e5ae-465">Atualizar README.md e metadata.json para 7.0.0-preview.4 (nº 10011)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-465">Update README.md and metadata.json for 7.0.0-preview.4 (Internal 10011)</span></span>
- <span data-ttu-id="1e5ae-466">Atualizar .Net Core versão 3.0 da Versão prévia 9 para a RC1 (nº 10552) (Obrigado, @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-466">Upgrade .Net Core 3.0 version from Preview 9 to RC1 (#10552) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="1e5ae-467">Corrigir a geração da lista ExperimentalFeature (Internal 9996)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-467">Fix ExperimentalFeature list generation (Internal 9996)</span></span>
- <span data-ttu-id="1e5ae-468">Elevar PSReadLine de 2.0.0-beta4 para 2.0.0-beta5 (nº 10536)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-468">Bump PSReadLine version from 2.0.0-beta4 to 2.0.0-beta5 (#10536)</span></span>
- <span data-ttu-id="1e5ae-469">Corrigir script de build da versão para definir a marca de versão</span><span class="sxs-lookup"><span data-stu-id="1e5ae-469">Fix release build script to set release tag</span></span>
- <span data-ttu-id="1e5ae-470">Atualizar versão do Microsoft.PowerShell.Native para 7.0.0-preview.2 (nº 10519)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-470">Update version of Microsoft.PowerShell.Native to 7.0.0-preview.2 (#10519)</span></span>
- <span data-ttu-id="1e5ae-471">Atualizar para Netcoreapp 3.0 versão prévia 9 (nº 10484) (Obrigado, @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-471">Upgrade to Netcoreapp3.0 preview9 (#10484) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="1e5ae-472">Verificar se o build coordenado diário sabe que é um build diário (nº 10464)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-472">Make sure the daily coordinated build, knows it is a daily build (#10464)</span></span>
- <span data-ttu-id="1e5ae-473">Atualizar o build do pacote combinado para liberar os builds diários (nº 10449)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-473">Update the combined package build to release the daily builds (#10449)</span></span>
- <span data-ttu-id="1e5ae-474">Remover referência de appveyor (nº 10445) (Obrigado, @RDIL!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-474">Remove appveyor reference (#10445) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="1e5ae-475">Elevar NJsonSchema de 10.0.22 para 10.0.23 (nº 10421)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-475">Bump NJsonSchema version from 10.0.22 to 10.0.23 (#10421)</span></span>
- <span data-ttu-id="1e5ae-476">Remover a exclusão da pasta de builds do Linux-x64 porque algumas dependências do Alpine precisam dela (nº 10407)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-476">Remove the deletion of linux-x64 build folder because some dependencies for Alpine need it (#10407)</span></span>

### <a name="documentation-and-help-content"></a><span data-ttu-id="1e5ae-477">Documentação e conteúdo da ajuda</span><span class="sxs-lookup"><span data-stu-id="1e5ae-477">Documentation and Help Content</span></span>

- <span data-ttu-id="1e5ae-478">Refatorar logs de alterações em um log por versão (nº 11165)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-478">Refactor change logs into one log per release (#11165)</span></span>
- <span data-ttu-id="1e5ae-479">Corrigir os documentos de ajuda online do FWLinks para PowerShell 7 (nº 11071)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-479">Fix FWLinks for PowerShell 7 online help documents (#11071)</span></span>
- <span data-ttu-id="1e5ae-480">Atualizar CONTRIBUTING.md (nº 11096) (Obrigado, @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-480">Update CONTRIBUTING.md (#11096) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="1e5ae-481">Corrigir os links do documento de instalação no README.md (nº 11083)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-481">Fix installation doc links in README.md (#11083)</span></span>
- <span data-ttu-id="1e5ae-482">Adicionar exemplos ao script install-powershell.ps1 (nº 11024) (Obrigado, @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-482">Adds examples to install-powershell.ps1 script (#11024) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="1e5ae-483">Corrigir a ênfase de Select-String e Import-DscResource em CHANGELOG.md (nº 10890)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-483">Fix to Select-String emphasis and Import-DscResource in CHANGELOG.md (#10890)</span></span>
- <span data-ttu-id="1e5ae-484">Remover o link obsoleto de powershell-beginners-guide.md (nº 10926)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-484">Remove the stale link from powershell-beginners-guide.md (#10926)</span></span>
- <span data-ttu-id="1e5ae-485">Mesclar logs de alterações estáveis e de manutenção (nº 10527)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-485">Merge stable and servicing change logs (#10527)</span></span>
- <span data-ttu-id="1e5ae-486">Atualizar versão .NET usada em documentos de build (nº 10775) (Obrigado, @Greg-Smulko!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-486">Update used .NET version in build docs (#10775) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="1e5ae-487">Substituir os links do MSDN para docs.microsoft.com em powershell-beginners-guide.md (nº 10778) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-487">Replace links from MSDN to docs.microsoft.com in powershell-beginners-guide.md (#10778) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="1e5ae-488">Corrigir link desfeito da visão geral do DSC (nº 10702)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-488">Fix broken DSC overview link (#10702)</span></span>
- <span data-ttu-id="1e5ae-489">Atualizar Support_Question.md para vincular ao Stack Overflow como outro recurso da comunidade (nº 10638) (Obrigado, @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-489">Update Support_Question.md to link to Stack Overflow as another community resource (#10638) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="1e5ae-490">Adicionar arquitetura de processador ao modelo de solicitação de distribuição (nº 10661)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-490">Add processor architecture to distribution request template (#10661)</span></span>
- <span data-ttu-id="1e5ae-491">Adicionar novo livro sobre MoL do PowerShell a documentos de aprendizagem do PowerShell (nº 10602)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-491">Add new PowerShell MoL book to learning PowerShell docs (#10602)</span></span>
- <span data-ttu-id="1e5ae-492">Atualizar README.md e metadados para as versões v6.1.6 e v6.2.3 (nº 10523)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-492">Update README.md and metadata for v6.1.6 and v6.2.3 releases (#10523)</span></span>
- <span data-ttu-id="1e5ae-493">Corrigir um erro de digitação no arquivo README.md (nº 10465) (Obrigado, @vedhasp!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-493">Fix a typo in README.md (#10465) (Thanks @vedhasp!)</span></span>
- <span data-ttu-id="1e5ae-494">Adicionar uma referência ao módulo PSKoans à documentação de Recursos de aprendizagem (nº 10369) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-494">Add a reference to PSKoans module to Learning Resources documentation (#10369) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="1e5ae-495">Atualizar README.md e metadata.json para 7.0.0-preview.3 (nº 10393)</span><span class="sxs-lookup"><span data-stu-id="1e5ae-495">Update README.md and metadata.json for 7.0.0-preview.3 (#10393)</span></span>
