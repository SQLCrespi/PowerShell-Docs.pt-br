---
description: Descreve o depurador do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: c53229752a26428ff4bc47fd5cecf039bdef7275
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196307"
---
# <a name="about-debuggers"></a><span data-ttu-id="cf0fa-104">Sobre os depuradores</span><span class="sxs-lookup"><span data-stu-id="cf0fa-104">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="cf0fa-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="cf0fa-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="cf0fa-106">Descreve o depurador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-106">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="cf0fa-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="cf0fa-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="cf0fa-108">A depuração é o processo de examinar um script enquanto ele está em execução para identificar e corrigir erros nas instruções do script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-108">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="cf0fa-109">O depurador do PowerShell pode ajudá-lo a examinar e identificar erros e ineficiências em seus scripts, funções, comandos, configurações de DSC (configuração de estado desejado) do PowerShell ou expressões.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-109">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="cf0fa-110">A partir do PowerShell 5,0, o depurador do PowerShell foi atualizado para depurar scripts, funções, comandos, configurações ou expressões que estão sendo executadas no console do ou ISE do Windows PowerShell em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-110">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="cf0fa-111">Você pode executar `Enter-PSSession` o para iniciar uma sessão interativa do PowerShell remoto, na qual é possível definir pontos de interrupção e depurar arquivos de script e comandos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-111">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="cf0fa-112">`Enter-PSSession` a funcionalidade foi atualizada para permitir que você se reconecte e insira uma sessão desconectada que esteja executando um script ou comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-112">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="cf0fa-113">Se o script em execução atingir um ponto de interrupção, a sessão do cliente iniciará automaticamente o depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-113">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="cf0fa-114">Se a sessão desconectada que está executando um script já tiver atingido um ponto de interrupção e for interrompida no ponto de interrupção, `Enter-PSSession` o iniciará automaticamente o depurador de linha de comando, depois que você se reconectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-114">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="cf0fa-115">Você pode usar os recursos do depurador do PowerShell para examinar um script, função, comando ou expressão do PowerShell enquanto ele está em execução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-115">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, or expression while it is running.</span></span> <span data-ttu-id="cf0fa-116">O depurador do PowerShell inclui um conjunto de cmdlets que permitem definir pontos de interrupção, gerenciar pontos de interrupção e exibir a pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-116">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="cf0fa-117">Cmdlets do depurador</span><span class="sxs-lookup"><span data-stu-id="cf0fa-117">Debugger Cmdlets</span></span>

<span data-ttu-id="cf0fa-118">O depurador do PowerShell inclui o seguinte conjunto de cmdlets:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-118">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="cf0fa-119">`Set-PSBreakpoint`: Define pontos de interrupção em linhas, variáveis e comandos.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-119">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="cf0fa-120">`Get-PSBreakpoint`: Obtém pontos de interrupção na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-120">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="cf0fa-121">`Disable-PSBreakpoint`: Desativa os pontos de interrupção na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-121">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="cf0fa-122">`Enable-PSBreakpoint`: Habilita novamente os pontos de interrupção na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-122">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="cf0fa-123">`Remove-PSBreakpoint`: Exclui pontos de interrupção da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-123">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="cf0fa-124">`Get-PSCallStack`: Exibe a pilha de chamadas atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-124">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="cf0fa-125">Iniciando e parando o depurador</span><span class="sxs-lookup"><span data-stu-id="cf0fa-125">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="cf0fa-126">Para iniciar o depurador, defina um ou mais pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-126">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="cf0fa-127">Em seguida, execute o script, comando ou função que você deseja depurar.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-127">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="cf0fa-128">Quando você atinge um ponto de interrupção, a execução é interrompida e o controle é ativado para o depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-128">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="cf0fa-129">Para interromper o depurador, execute o script, comando ou função até que ele seja concluído.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-129">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="cf0fa-130">Ou digite `stop` ou `t` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-130">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="cf0fa-131">Comandos do depurador</span><span class="sxs-lookup"><span data-stu-id="cf0fa-131">Debugger Commands</span></span>

<span data-ttu-id="cf0fa-132">Ao usar o depurador no console do PowerShell, use os comandos a seguir para controlar a execução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-132">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="cf0fa-133">No ISE do Windows PowerShell, use os comandos no menu Depurar.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-133">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="cf0fa-134">Observação: para obter informações sobre como usar o depurador em outros aplicativos host, consulte a documentação do aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-134">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="cf0fa-135">`s`, `StepInto` : Executa a próxima instrução e, em seguida, para.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-135">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="cf0fa-136">`v`, `StepOver` : Executa a próxima instrução, mas ignora as funções e invocações.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-136">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="cf0fa-137">As instruções ignoradas são executadas, mas não percorridas.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-137">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="cf0fa-138">`Ctrl+Break`: (Interromper tudo no ISE) é dividido em um script em execução no console do PowerShell ou ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-138">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="cf0fa-139">Observe que <kbd>Ctrl</kbd> + <kbd>Break</kbd> no Windows PowerShell 2,0, 3,0 e 4,0 fecha o programa.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-139">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="cf0fa-140">Interromper tudo funciona em scripts locais e remotos de execução interativa.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-140">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="cf0fa-141">`o`, `StepOut` : Sai da função atual; um nível acima se estiver aninhado.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-141">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="cf0fa-142">Se estiver no corpo principal, ele continuará ao final ou ao próximo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-142">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="cf0fa-143">As instruções ignoradas são executadas, mas não percorridas.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-143">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="cf0fa-144">`c`, `Continue` : Continua a ser executado até que o script seja concluído ou até que o próximo ponto de interrupção seja atingido.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-144">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="cf0fa-145">As instruções ignoradas são executadas, mas não percorridas.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-145">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="cf0fa-146">`l`, `List` : Exibe a parte do script que está em execução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-146">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="cf0fa-147">Por padrão, ele exibe a linha atual, cinco linhas anteriores e 10 linhas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-147">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="cf0fa-148">Para continuar a listar o script, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-148">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="cf0fa-149">`l <m>`, `List` : Exibe 16 linhas do script começando com o número de linha especificado por `<m>` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-149">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="cf0fa-150">`l <m> <n>`, `List` : Exibe `<n>` linhas do script, começando com o número de linha especificado por `<m>` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-150">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="cf0fa-151">`q`, `Stop` , `Exit` : Interrompe a execução do script e sai do depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-151">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="cf0fa-152">Se você estiver depurando um trabalho executando o `Debug-Job` cmdlet, o `Exit` comando desanexará o depurador e permitirá que o trabalho continue em execução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-152">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="cf0fa-153">`k`, `Get-PsCallStack` : Exibe a pilha de chamadas atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-153">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="cf0fa-154">`<Enter>`: Repete o último comando se ele foi Step (s), StepOver (v) ou List (l).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-154">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="cf0fa-155">Caso contrário, representa uma ação de envio.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-155">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="cf0fa-156">`?`, `h` : Exibe a ajuda do comando do depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-156">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="cf0fa-157">Para sair do depurador, você pode usar Stop (q).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-157">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="cf0fa-158">A partir do PowerShell 5,0, você pode executar o comando Exit para sair de uma sessão de depuração aninhada que você iniciou executando o `Debug-Job` ou o `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-158">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="cf0fa-159">Usando esses comandos do depurador, você pode executar um script, parar em um ponto de preocupação, examinar os valores de variáveis e o estado do sistema e continuar executando o script até que você tenha identificado um problema.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-159">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="cf0fa-160">Observação: se você entrar em uma instrução com um operador de redirecionamento, como ">", o depurador do PowerShell percorre todas as instruções restantes no script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-160">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="cf0fa-161">Exibindo os valores das variáveis de script</span><span class="sxs-lookup"><span data-stu-id="cf0fa-161">Displaying the Values of script Variables</span></span>

<span data-ttu-id="cf0fa-162">Enquanto estiver no depurador, você também poderá inserir comandos, exibir o valor de variáveis, usar cmdlets e executar scripts na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-162">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="cf0fa-163">Você pode exibir o valor atual de todas as variáveis no script que está sendo depurado, exceto pelas seguintes variáveis automáticas:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-163">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="cf0fa-164">Se você tentar exibir o valor de qualquer uma dessas variáveis, obterá o valor dessa variável para em um pipeline interno usado pelo depurador, não o valor da variável no script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-164">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="cf0fa-165">Para exibir o valor dessas variáveis para o script que está sendo depurado, no script, atribua o valor da variável automática a uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-165">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="cf0fa-166">Em seguida, você pode exibir o valor da nova variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-166">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="cf0fa-167">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="cf0fa-167">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="cf0fa-168">No exemplo neste tópico, o valor da `$MyInvocation` variável é reatribuído da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-168">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="cf0fa-169">O ambiente do depurador</span><span class="sxs-lookup"><span data-stu-id="cf0fa-169">The Debugger Environment</span></span>

<span data-ttu-id="cf0fa-170">Ao alcançar um ponto de interrupção, você entra no ambiente do depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-170">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="cf0fa-171">O prompt de comando é alterado para que comece com "[DBG]:".</span><span class="sxs-lookup"><span data-stu-id="cf0fa-171">The command prompt changes so that it begins with "[DBG]:".</span></span>

<span data-ttu-id="cf0fa-172">Para obter mais informações sobre como personalizar o prompt, consulte [about_Prompts](about_prompts.md).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-172">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="cf0fa-173">Além disso, em alguns aplicativos host, como o console do PowerShell (mas não no Ambiente de Script Integrado do Windows PowerShell [ISE]), um prompt aninhado é aberto para depuração.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-173">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="cf0fa-174">Você pode detectar o prompt aninhado pelos caracteres de maior que repetições (ASCII 62) que aparecem no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-174">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="cf0fa-175">Por exemplo, o seguinte é o prompt de depuração padrão no console do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-175">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="cf0fa-176">Você pode encontrar o nível de aninhamento usando a `$NestedPromptLevel` variável automática.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-176">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="cf0fa-177">Além disso, uma variável automática, `$PSDebugContext` , é definida no escopo local.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-177">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="cf0fa-178">Você pode usar a presença da `$PsDebugContext` variável para determinar se está no depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-178">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="cf0fa-179">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-179">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="cf0fa-180">Você pode usar o valor da `$PSDebugContext` variável em sua depuração.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-180">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="cf0fa-181">Depuração e escopo</span><span class="sxs-lookup"><span data-stu-id="cf0fa-181">Debugging and Scope</span></span>

<span data-ttu-id="cf0fa-182">Interromper o depurador não altera o escopo no qual você está operando, mas quando você atinge um ponto de interrupção em um script, você passa para o escopo do script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-182">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="cf0fa-183">O escopo do script é um filho do escopo no qual você executou o depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-183">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="cf0fa-184">Para localizar as variáveis e os aliases definidos no escopo do script, use o parâmetro scope dos `Get-Alias` `Get-Variable` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-184">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="cf0fa-185">Por exemplo, o comando a seguir obtém as variáveis no escopo local (script):</span><span class="sxs-lookup"><span data-stu-id="cf0fa-185">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="cf0fa-186">Você pode abreviar o comando como:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-186">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="cf0fa-187">Essa é uma maneira útil de ver apenas as variáveis que você definiu no script e que você definiu durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-187">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="cf0fa-188">Depuração na linha de comando</span><span class="sxs-lookup"><span data-stu-id="cf0fa-188">Debugging at the Command Line</span></span>

<span data-ttu-id="cf0fa-189">Ao definir um ponto de interrupção de variável ou um ponto de interrupção de comando, você pode definir o ponto de interrupção somente em um arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-189">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="cf0fa-190">No entanto, por padrão, o ponto de interrupção é definido em qualquer coisa que seja executada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-190">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="cf0fa-191">Por exemplo, se você definir um ponto de interrupção na `$name` variável, o depurador interromperá qualquer `$name` variável em qualquer script, comando, função, cmdlet de script ou expressão que você executar até que você desabilite ou remova o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-191">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="cf0fa-192">Isso permite que você depure seus scripts em um contexto mais realista no qual eles podem ser afetados por funções, variáveis e outros scripts na sessão e no perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-192">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="cf0fa-193">Os pontos de interrupção de linha são específicos para arquivos de script, portanto, eles são definidos somente em arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-193">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-functions"></a><span data-ttu-id="cf0fa-194">Funções de depuração</span><span class="sxs-lookup"><span data-stu-id="cf0fa-194">Debugging Functions</span></span>

<span data-ttu-id="cf0fa-195">Quando você define um ponto de interrupção em uma função que tem `Begin` `Process` seções, e `End` , o depurador é interrompido na primeira linha de cada seção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-195">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="cf0fa-196">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-196">For example:</span></span>

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a><span data-ttu-id="cf0fa-197">Depuração de scripts remotos</span><span class="sxs-lookup"><span data-stu-id="cf0fa-197">Debugging Remote Scripts</span></span>

<span data-ttu-id="cf0fa-198">A partir do PowerShell 5,0, você pode executar o depurador do PowerShell em uma sessão remota, no console do ou ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-198">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="cf0fa-199">`Enter-PSSession` a funcionalidade foi atualizada para permitir que você se reconecte e insira uma sessão desconectada que está sendo executada em um computador remoto e que atualmente está executando um script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-199">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="cf0fa-200">Se o script em execução atingir um ponto de interrupção, a sessão do cliente iniciará automaticamente o depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-200">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="cf0fa-201">Veja a seguir um exemplo que mostra como isso funciona, com pontos de interrupção definidos em um script nas linhas 6, 11, 22 e 25.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-201">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="cf0fa-202">Observe que, no exemplo, quando o depurador é iniciado, há dois prompts de identificação: o nome do computador no qual a sessão está em execução e o prompt DBG que lhe permite saber se você está no modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-202">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a><span data-ttu-id="cf0fa-203">Exemplos</span><span class="sxs-lookup"><span data-stu-id="cf0fa-203">Examples</span></span>

<span data-ttu-id="cf0fa-204">Esse script de teste detecta a versão do sistema operacional e exibe uma mensagem apropriada do sistema.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-204">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="cf0fa-205">Ele inclui uma função, uma chamada de função e uma variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-205">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="cf0fa-206">O comando a seguir exibe o conteúdo do arquivo de script de teste:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-206">The following command displays the contents of the test script file:</span></span>

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

<span data-ttu-id="cf0fa-207">Para começar, defina um ponto de interrupção em um momento de interesse no script, como uma linha, comando, variável ou função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-207">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="cf0fa-208">Comece criando um ponto de interrupção de linha na primeira linha do script de Test.ps1 no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-208">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="cf0fa-209">Você pode abreviar esse comando como:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-209">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="cf0fa-210">O comando retorna um objeto de ponto de interrupção de linha ( **System. Management. Automation. LineBreakpoint** ).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-210">The command returns a line-breakpoint object ( **System.Management.Automation.LineBreakpoint** ).</span></span>

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

<span data-ttu-id="cf0fa-211">Agora, inicie o script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-211">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="cf0fa-212">Quando o script atinge o primeiro ponto de interrupção, a mensagem de ponto de interrupção indica que o depurador está ativo.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-212">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="cf0fa-213">Ele descreve o ponto de interrupção e a visualização da primeira linha do script, que é uma declaração de função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-213">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="cf0fa-214">O prompt de comando também é alterado para indicar que o depurador tem controle.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-214">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="cf0fa-215">A linha de visualização inclui o nome do script e o número de linha do comando visualizado.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-215">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="cf0fa-216">Use os comandos Step para executar a primeira instrução no script e visualizar a próxima instrução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-216">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="cf0fa-217">A próxima instrução usa a `$MyInvocation` variável automática para definir o valor da `$scriptName` variável como o caminho e o nome de arquivo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-217">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="cf0fa-218">Neste ponto, a `$scriptName` variável não é populada, mas você pode verificar o valor da variável exibindo seu valor.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-218">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="cf0fa-219">Nesse caso, o valor é `$null` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-219">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="cf0fa-220">Use outro comando Step para executar a instrução atual e visualizar a próxima instrução no script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-220">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="cf0fa-221">A próxima instrução chama a função PsVersion.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-221">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="cf0fa-222">Neste ponto, a `$scriptName` variável é populada, mas você verifica o valor da variável exibindo seu valor.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-222">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="cf0fa-223">Nesse caso, o valor é definido como o caminho do script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-223">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="cf0fa-224">Use outro comando Step para executar a chamada de função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-224">Use another Step command to execute the function call.</span></span> <span data-ttu-id="cf0fa-225">Pressione ENTER ou digite "s" para a etapa.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-225">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="cf0fa-226">A mensagem de depuração inclui uma visualização da instrução na função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-226">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="cf0fa-227">Para executar essa instrução e visualizar a próxima instrução na função, você pode usar um `Step` comando.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-227">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="cf0fa-228">Mas, nesse caso, use um comando StepOut (o).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-228">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="cf0fa-229">Ele conclui a execução da função (a menos que ela alcance um ponto de interrupção) e etapas para a próxima instrução no script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-229">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="cf0fa-230">Como estamos na última instrução do script, os comandos Step, StepOut e continue têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-230">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="cf0fa-231">Nesse caso, use o StepOut (o).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-231">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="cf0fa-232">O comando StepOut executa o último comando.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-232">The StepOut command executes the last command.</span></span> <span data-ttu-id="cf0fa-233">O prompt de comando padrão indica que o depurador saiu e retornou o controle para o processador de comando.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-233">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="cf0fa-234">Agora, execute o depurador novamente.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-234">Now, run the debugger again.</span></span> <span data-ttu-id="cf0fa-235">Primeiro, para excluir o ponto de interrupção atual, use os `Get-PsBreakpoint` `Remove-PsBreakpoint` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-235">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="cf0fa-236">(Se você considerar que pode reutilizar o ponto de interrupção, use o `Disable-PsBreakpoint` cmdlet em vez de `Remove-PsBreakpoint` .)</span><span class="sxs-lookup"><span data-stu-id="cf0fa-236">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="cf0fa-237">Você pode abreviar esse comando como:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-237">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="cf0fa-238">Ou execute o comando escrevendo uma função, como a seguinte função:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-238">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="cf0fa-239">Agora, crie um ponto de interrupção na `$scriptname` variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-239">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="cf0fa-240">Você pode abreviar o comando como:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-240">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="cf0fa-241">Agora, inicie o script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-241">Now, start the script.</span></span> <span data-ttu-id="cf0fa-242">O script atinge o ponto de interrupção da variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-242">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="cf0fa-243">O modo padrão é Write, portanto a execução é interrompida logo antes da instrução que altera o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-243">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="cf0fa-244">Exibe o valor atual da `$scriptName` variável, que é `$null` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-244">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="cf0fa-245">Use um ou mais comandos Step para executar a instrução que popula a variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-245">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="cf0fa-246">Em seguida, exiba o novo valor da `$scriptName` variável.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-246">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="cf0fa-247">A próxima instrução é uma chamada para a função PsVersion.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-247">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="cf0fa-248">Para ignorar a função, mas ainda executá-la, use um comando StepOver (v).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-248">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="cf0fa-249">Se você já estiver na função ao usar o StepOver, ele não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-249">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="cf0fa-250">A chamada de função é exibida, mas não é executada.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-250">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="cf0fa-251">O comando StepOver executa a função e visualiza a próxima instrução no script, que imprime a linha final.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-251">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="cf0fa-252">Use um comando de parada (t) para sair do depurador.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-252">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="cf0fa-253">O prompt de comando reverte para o prompt de comando padrão.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-253">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="cf0fa-254">Para excluir os pontos de interrupção, use `Get-PsBreakpoint` os `Remove-PsBreakpoint` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-254">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="cf0fa-255">Crie um novo ponto de interrupção de comando na função PsVersion.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-255">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="cf0fa-256">Você pode abreviar este comando para:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-256">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="cf0fa-257">Agora, execute o script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-257">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="cf0fa-258">O script atinge o ponto de interrupção na chamada de função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-258">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="cf0fa-259">Neste ponto, a função ainda não foi chamada.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-259">At this point, the function has not yet been called.</span></span> <span data-ttu-id="cf0fa-260">Isso lhe dá a oportunidade de usar o parâmetro Action do `Set-PSBreakpoint` para definir condições para a execução do ponto de interrupção ou para executar tarefas preparatórias ou de diagnóstico, como iniciar um log ou invocar um script de diagnóstico ou segurança.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-260">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="cf0fa-261">Para definir uma ação, use um comando Continue (c) para sair do script e um `Remove-PsBreakpoint` comando para excluir o ponto de interrupção atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-261">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="cf0fa-262">(Os pontos de interrupção são somente leitura, portanto, você não pode adicionar uma ação ao ponto de interrupção atual.)</span><span class="sxs-lookup"><span data-stu-id="cf0fa-262">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="cf0fa-263">Agora, crie um novo ponto de interrupção de comando com uma ação.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-263">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="cf0fa-264">O comando a seguir define um ponto de interrupção de comando com uma ação que registra o valor da `$scriptName` variável quando a função é chamada.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-264">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="cf0fa-265">Como a palavra-chave break não é usada na ação, a execução não é interrompida.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-265">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="cf0fa-266">(') É o caractere de continuação de linha.)</span><span class="sxs-lookup"><span data-stu-id="cf0fa-266">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="cf0fa-267">Você também pode adicionar ações que definem condições para o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-267">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="cf0fa-268">No comando a seguir, o ponto de interrupção do comando será executado somente se a política de execução estiver definida como RemoteSigned, a política mais restritiva que ainda permitirá executar scripts.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-268">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="cf0fa-269">(') É o caractere de continuação.)</span><span class="sxs-lookup"><span data-stu-id="cf0fa-269">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="cf0fa-270">A palavra-chave break na ação direciona o depurador para executar o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-270">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="cf0fa-271">Você também pode usar a palavra-chave continue para direcionar o depurador a ser executado sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-271">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="cf0fa-272">Como a palavra-chave default é Continue, você deve especificar Break para interromper a execução.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-272">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="cf0fa-273">Agora, execute o script.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-273">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="cf0fa-274">Como a política de execução é definida como **RemoteSigned** , a execução é interrompida na chamada de função.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-274">Because the execution policy is set to **RemoteSigned** , execution stops at the function call.</span></span>

<span data-ttu-id="cf0fa-275">Neste ponto, talvez você queira verificar a pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-275">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="cf0fa-276">Use o `Get-PsCallStack` cmdlet ou o `Get-PsCallStack` comando do depurador (k).</span><span class="sxs-lookup"><span data-stu-id="cf0fa-276">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="cf0fa-277">O comando a seguir obtém a pilha de chamadas atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-277">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="cf0fa-278">Este exemplo demonstra apenas algumas das muitas maneiras de usar o depurador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-278">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="cf0fa-279">Para obter mais informações sobre os cmdlets do depurador, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-279">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="cf0fa-280">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="cf0fa-280">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="cf0fa-281">Outros recursos de depuração no PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf0fa-281">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="cf0fa-282">Além do depurador do PowerShell, o PowerShell inclui vários outros recursos que você pode usar para depurar scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-282">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="cf0fa-283">O ISE do Windows PowerShell inclui um depurador gráfico interativo.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-283">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="cf0fa-284">Para obter mais informações, inicie ISE do Windows PowerShell e pressione F1.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-284">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="cf0fa-285">O `Set-PSDebug` cmdlet oferece recursos de depuração de script muito básicos, incluindo depuração e rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-285">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="cf0fa-286">Use o `Set-StrictMode` cmdlet para detectar referências a variáveis não inicializadas, para referências a Propriedades inexistentes de um objeto e para a sintaxe de função que não é válida.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-286">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="cf0fa-287">Adicione instruções de diagnóstico a um script, como instruções que exibem o valor de variáveis, instruções que lêem a entrada da linha de comando ou instruções que relatam a instrução atual.</span><span class="sxs-lookup"><span data-stu-id="cf0fa-287">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="cf0fa-288">Use os cmdlets que contêm o verbo de gravação para essa tarefa, como `Write-Host` , `Write-Debug` , `Write-Warning` e `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="cf0fa-288">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf0fa-289">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="cf0fa-289">SEE ALSO</span></span>

- [<span data-ttu-id="cf0fa-290">Desabilitar-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cf0fa-290">Disable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="cf0fa-291">Habilitar-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cf0fa-291">Enable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="cf0fa-292">Get-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cf0fa-292">Get-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="cf0fa-293">Get-PsCallStack</span><span class="sxs-lookup"><span data-stu-id="cf0fa-293">Get-PsCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="cf0fa-294">Remove-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cf0fa-294">Remove-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="cf0fa-295">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cf0fa-295">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="cf0fa-296">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="cf0fa-296">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="cf0fa-297">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="cf0fa-297">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
