---
ms.date: 05/22/2020
keywords: powershell, cmdlet
title: O que é o PowerShell?
ms.openlocfilehash: 267b2938a0892c99c3a961bc7107f573df40a683
ms.sourcegitcommit: 38215ad49e237b219e62bb5a5f0eb3b6b048df1e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "83868472"
---
# <a name="what-is-powershell"></a><span data-ttu-id="e89c3-103">O que é o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e89c3-103">What is PowerShell?</span></span>

<span data-ttu-id="e89c3-104">O PowerShell é uma estrutura multiplataforma de gerenciamento de configuração e de automação de tarefas, que consiste em um shell de linha de comando e em uma linguagem de script.</span><span class="sxs-lookup"><span data-stu-id="e89c3-104">PowerShell is a cross-platform task automation and configuration management framework, consisting of a command-line shell and scripting language.</span></span> <span data-ttu-id="e89c3-105">Ao contrário da maioria dos shells, que aceitam e retornam texto, o PowerShell é criado com base no CLR (Common Language Runtime) do .NET e aceita e retorna objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="e89c3-105">Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.</span></span> <span data-ttu-id="e89c3-106">Essa mudança fundamental traz ferramentas e métodos totalmente novos para a automação.</span><span class="sxs-lookup"><span data-stu-id="e89c3-106">This fundamental change brings entirely new tools and methods for automation.</span></span>

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a><span data-ttu-id="e89c3-107">A saída é baseada em objeto</span><span class="sxs-lookup"><span data-stu-id="e89c3-107">Output is object-based</span></span>

<span data-ttu-id="e89c3-108">Ao contrário de interfaces de linha de comando tradicionais, os cmdlets do PowerShell são projetados para lidar com objetos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-108">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="e89c3-109">Um objeto representa informações estruturadas que vão além da uma cadeia de caracteres exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="e89c3-109">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="e89c3-110">A saída do comando sempre acompanha informações extras que poderão ser usadas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="e89c3-110">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="e89c3-111">Se você já usou ferramentas de processamento de texto para processar dados, perceberá que elas se comportam de maneira diferente quando usadas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-111">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="e89c3-112">Na maioria dos casos, você não precisa de ferramentas de processamento de texto para extrair informações específicas.</span><span class="sxs-lookup"><span data-stu-id="e89c3-112">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="e89c3-113">Você acessa diretamente partes dos dados usando a sintaxe de objeto padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-113">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="e89c3-114">A família de comandos é extensível</span><span class="sxs-lookup"><span data-stu-id="e89c3-114">The command family is extensible</span></span>

<span data-ttu-id="e89c3-115">Interfaces como a do `cmd.exe` não fornecem uma forma de estender diretamente o conjunto de comandos internos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-115">Interfaces such as `cmd.exe` don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="e89c3-116">Você pode criar ferramentas de linha de comando externas que são executadas no `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-116">You can create external command-line tools that run in `cmd.exe`.</span></span> <span data-ttu-id="e89c3-117">Mas essas ferramentas externas não têm serviços, como a integração com a Ajuda.</span><span class="sxs-lookup"><span data-stu-id="e89c3-117">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="e89c3-118">O `cmd.exe` não sabe automaticamente que essas ferramentas externas são comandos válidos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-118">`cmd.exe` doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="e89c3-119">Os comandos no PowerShell são conhecidos como _cmdlets_.</span><span class="sxs-lookup"><span data-stu-id="e89c3-119">The commands in PowerShell are known as _cmdlets_.</span></span> <span data-ttu-id="e89c3-120">Você pode usar cada cmdlet separadamente, mas o potencial deles é atingido quando você os combina para executar tarefas complexas.</span><span class="sxs-lookup"><span data-stu-id="e89c3-120">You can use each cmdlet separately, but their power is realized when you combine them to perform complex tasks.</span></span> <span data-ttu-id="e89c3-121">Como muitos shells, o PowerShell fornece acesso ao sistema de arquivos no computador.</span><span class="sxs-lookup"><span data-stu-id="e89c3-121">Like many shells, PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="e89c3-122">Os _provedores_ do PowerShell permitem que você acesse outros armazenamentos de dados, como o Registro e os repositórios de certificados, com tanta facilidade quanto o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-122">PowerShell _providers_ enable you to access other data stores, such as the registry and the certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="e89c3-123">Você pode criar módulos de cmdlet e de função usando código compilado ou scripts.</span><span class="sxs-lookup"><span data-stu-id="e89c3-123">You can create your own cmdlet and function modules using compiled code or scripts.</span></span> <span data-ttu-id="e89c3-124">Os módulos podem adicionar cmdlets e provedores ao shell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-124">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="e89c3-125">O PowerShell também dá suporte a scripts que são análogos aos scripts de shell do UNIX e aos arquivos em lotes do `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-125">PowerShell also supports scripts that are analogous to UNIX shell scripts and `cmd.exe` batch files.</span></span>

## <a name="support-for-command-aliases"></a><span data-ttu-id="e89c3-126">Suporte para aliases de comando</span><span class="sxs-lookup"><span data-stu-id="e89c3-126">Support for command aliases</span></span>

<span data-ttu-id="e89c3-127">O PowerShell dá suporte a aliases para se referir aos comandos por nomes alternativos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-127">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="e89c3-128">Usar alias permite que usuários com experiência em outros shells utilizem nomes de comando comuns que já conhecem para operações semelhantes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-128">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="e89c3-129">O alias associa um novo nome a outro comando.</span><span class="sxs-lookup"><span data-stu-id="e89c3-129">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="e89c3-130">Por exemplo, o PowerShell tem uma função interna denominada `Clear-Host` que limpa a janela de saída.</span><span class="sxs-lookup"><span data-stu-id="e89c3-130">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="e89c3-131">Você pode digitar o alias `cls` ou `clear` em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e89c3-131">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="e89c3-132">O PowerShell interpreta esses aliases e executa a função `Clear-Host`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-132">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="e89c3-133">Esse recurso ajuda os usuários a aprender sobre o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-133">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="e89c3-134">Primeiro, a maioria dos usuários do `cmd.exe` e do UNIX tem um grande repertório de comandos conhecidos por nome.</span><span class="sxs-lookup"><span data-stu-id="e89c3-134">First, most `cmd.exe` and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="e89c3-135">Talvez os equivalentes do PowerShell não produzam resultados idênticos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-135">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="e89c3-136">No entanto, os resultados são bem parecidos, e os usuários podem fazer o trabalho sem conhecer o nome de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-136">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="e89c3-137">A "memória muscular" é outra grande fonte de frustração ao aprender um novo shell de comando.</span><span class="sxs-lookup"><span data-stu-id="e89c3-137">"Muscle memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="e89c3-138">Caso você use o `cmd.exe` há anos, é possível que você digite inconscientemente o comando `cls` para limpar a tela.</span><span class="sxs-lookup"><span data-stu-id="e89c3-138">If you have used `cmd.exe` for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="e89c3-139">Sem o alias para `Clear-Host`, você receberá uma mensagem de erro e não saberá o que fazer para limpar a saída.</span><span class="sxs-lookup"><span data-stu-id="e89c3-139">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="e89c3-140">O PowerShell manipula a exibição e a entrada do console</span><span class="sxs-lookup"><span data-stu-id="e89c3-140">PowerShell handles console input and display</span></span>

<span data-ttu-id="e89c3-141">Quando você digita um comando, o PowerShell sempre processa a linha de comando de entrada diretamente.</span><span class="sxs-lookup"><span data-stu-id="e89c3-141">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="e89c3-142">O PowerShell também formata a saída exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="e89c3-142">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="e89c3-143">Essa diferença é considerável porque reduz o trabalho necessário em cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e89c3-143">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="e89c3-144">Isso garante que você possa fazer as coisas sempre da mesma maneira com qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e89c3-144">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="e89c3-145">Os desenvolvedores de cmdlet não precisam escrever códigos para analisar os argumentos de linha de comando ou formatar a saída.</span><span class="sxs-lookup"><span data-stu-id="e89c3-145">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="e89c3-146">Ferramentas de linha de comando tradicionais têm seus próprios esquemas para solicitar e exibir a Ajuda.</span><span class="sxs-lookup"><span data-stu-id="e89c3-146">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="e89c3-147">Algumas ferramentas de linha de comando usam `/?` para disparar a exibição da Ajuda; outras usam `-?`, `/H` ou até mesmo `//`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-147">Some command-line tools use `/?` to trigger the Help display; others use `-?`, `/H`, or even `//`.</span></span> <span data-ttu-id="e89c3-148">Algumas delas exibem a Ajuda em uma janela GUI em vez de na exibição do console.</span><span class="sxs-lookup"><span data-stu-id="e89c3-148">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="e89c3-149">Se você usar o parâmetro errado, a ferramenta poderá ignorar o que você digitou e começar a executar uma tarefa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e89c3-149">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="e89c3-150">Como o PowerShell analisa e processa a linha de comando automaticamente, o parâmetro `-?` sempre significa "mostre-me a Ajuda para este comando".</span><span class="sxs-lookup"><span data-stu-id="e89c3-150">Since PowerShell automatically parses and processes the command line, the `-?` parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="e89c3-151">Se você executar um aplicativo gráfico no PowerShell, a janela do aplicativo se abrirá.</span><span class="sxs-lookup"><span data-stu-id="e89c3-151">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="e89c3-152">O PowerShell intervém apenas no processamento da entrada da linha de comando que você fornece ou quando a saída do aplicativo retorna para a janela do console.</span><span class="sxs-lookup"><span data-stu-id="e89c3-152">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="e89c3-153">Ele não afeta a maneira como o aplicativo funciona internamente.</span><span class="sxs-lookup"><span data-stu-id="e89c3-153">It does not affect how the application works internally.</span></span>

## <a name="powershell-has-a-pipeline"></a><span data-ttu-id="e89c3-154">O PowerShell tem um pipeline</span><span class="sxs-lookup"><span data-stu-id="e89c3-154">PowerShell has a pipeline</span></span>

<span data-ttu-id="e89c3-155">Pipelines são possivelmente o conceito mais valioso usado nas interfaces de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e89c3-155">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="e89c3-156">Quando usados adequadamente, os pipelines facilitam o uso de comandos complexos e a visualização do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e89c3-156">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work.</span></span> <span data-ttu-id="e89c3-157">Cada comando em um pipeline passa sua saída, item por item, para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="e89c3-157">Each command in a pipeline passes its output, item by item, to the next command.</span></span> <span data-ttu-id="e89c3-158">Os comandos não precisam lidar com mais de um item por vez.</span><span class="sxs-lookup"><span data-stu-id="e89c3-158">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="e89c3-159">O resultado são o consumo reduzido de recursos e a capacidade de obter uma saída imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e89c3-159">The result is reduced resource consumption and the ability to get output immediately.</span></span>

<span data-ttu-id="e89c3-160">A notação usada para pipelines é semelhante à notação usada em outros shells.</span><span class="sxs-lookup"><span data-stu-id="e89c3-160">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="e89c3-161">À primeira vista, talvez seja aparente como os pipelines são diferentes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-161">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="e89c3-162">Embora você veja o texto na tela, o PowerShell redireciona objetos, e não o texto, entre comandos.</span><span class="sxs-lookup"><span data-stu-id="e89c3-162">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

<span data-ttu-id="e89c3-163">Por exemplo, se você usar o cmdlet `Out-Host` para forçar uma exibição de página a página da saída de outro comando, a saída parecerá ser apenas o texto normal exibido na tela, dividida em páginas:</span><span class="sxs-lookup"><span data-stu-id="e89c3-163">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="e89c3-164">A paginação também reduz a utilização da CPU, pois o processamento muda para o cmdlet `Out-Host` quando há uma página completa pronta para exibição.</span><span class="sxs-lookup"><span data-stu-id="e89c3-164">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="e89c3-165">Os cmdlets que a precedem no pipeline pausam a execução até que a próxima página de saída esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="e89c3-165">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

### <a name="objects-in-the-pipeline"></a><span data-ttu-id="e89c3-166">Objetos no pipeline</span><span class="sxs-lookup"><span data-stu-id="e89c3-166">Objects in the pipeline</span></span>

<span data-ttu-id="e89c3-167">Quando você executa um cmdlet no PowerShell, vê a saída de texto porque é necessário representar objetos como texto em uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="e89c3-167">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="e89c3-168">A saída de texto não pode exibir todas as propriedades do objeto mostrado.</span><span class="sxs-lookup"><span data-stu-id="e89c3-168">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="e89c3-169">Por exemplo, considere o cmdlet `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-169">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="e89c3-170">A saída de texto é um resumo das informações, não uma representação completa do objeto retornado por `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-170">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="e89c3-171">O título na saída é adicionado pelo processo que formata os dados para exibição na tela.</span><span class="sxs-lookup"><span data-stu-id="e89c3-171">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

```powershell
Get-Location
```

```Output
Path
----
C:\
```

<span data-ttu-id="e89c3-172">O redirecionamento da saída para o cmdlet `Get-Member` exibe informações sobre o objeto retornado por `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="e89c3-172">Piping the output to the `Get-Member` cmdlet displays information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="e89c3-173">`Get-Location` retorna um objeto **PathInfo** que contém o caminho atual e outras informações.</span><span class="sxs-lookup"><span data-stu-id="e89c3-173">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>

## <a name="built-in-help-system"></a><span data-ttu-id="e89c3-174">Sistema de ajuda interno</span><span class="sxs-lookup"><span data-stu-id="e89c3-174">Built-in help system</span></span>

<span data-ttu-id="e89c3-175">Semelhante às páginas `man` do UNIX, o PowerShell inclui artigos de ajuda detalhados que explicam os conceitos e a sintaxe de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-175">Similar to Unix `man` pages, PowerShell includes detailed help articles that explain PowerShell concepts and command syntax.</span></span> <span data-ttu-id="e89c3-176">Use o cmdlet [Get-Help][] para exibir esses artigos no prompt de comando ou confira as versões mais atualizadas deles na documentação online do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89c3-176">Use the [Get-Help][] cmdlet to display these articles at the command prompt or view the most recently updated versions of these articles in the PowerShell documentation online.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e89c3-177">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e89c3-177">Next steps</span></span>

<span data-ttu-id="e89c3-178">Para saber mais sobre o PowerShell, confira a seção **Aprendendo a usar o PowerShell** deste site.</span><span class="sxs-lookup"><span data-stu-id="e89c3-178">To learn more about PowerShell, see the **Learning PowerShell** section of this site.</span></span>

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
