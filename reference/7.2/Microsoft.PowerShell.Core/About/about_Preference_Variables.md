---
description: Variáveis que personalizam o comportamento do PowerShell.
Locale: en-US
ms.date: 04/12/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: ffd640f7eac8b27cabce345f11da728945043e46
ms.sourcegitcommit: 74270273e9097352dab174c08123b82063225e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "107297190"
---
# <a name="about-preference-variables"></a><span data-ttu-id="69ea2-103">Sobre variáveis de preferência</span><span class="sxs-lookup"><span data-stu-id="69ea2-103">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="69ea2-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="69ea2-104">Short description</span></span>

<span data-ttu-id="69ea2-105">Variáveis que personalizam o comportamento do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-105">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="69ea2-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="69ea2-106">Long description</span></span>

<span data-ttu-id="69ea2-107">O PowerShell inclui um conjunto de variáveis que permitem que você personalize seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="69ea2-107">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="69ea2-108">Essas variáveis de preferência funcionam como as opções em sistemas baseados em GUI.</span><span class="sxs-lookup"><span data-stu-id="69ea2-108">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="69ea2-109">As variáveis de preferência afetam o ambiente operacional do PowerShell e todos os comandos executados no ambiente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-109">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="69ea2-110">Em muitos casos, os cmdlets têm parâmetros que você pode usar para substituir o comportamento de preferência para um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-110">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="69ea2-111">A tabela a seguir lista as variáveis de preferência e seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-111">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="69ea2-112">Variável</span><span class="sxs-lookup"><span data-stu-id="69ea2-112">Variable</span></span>             |       <span data-ttu-id="69ea2-113">Valor Padrão</span><span class="sxs-lookup"><span data-stu-id="69ea2-113">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="69ea2-114">Alto</span><span class="sxs-lookup"><span data-stu-id="69ea2-114">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="69ea2-115">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="69ea2-115">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="69ea2-116">Continue</span><span class="sxs-lookup"><span data-stu-id="69ea2-116">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="69ea2-117">ConciseView</span><span class="sxs-lookup"><span data-stu-id="69ea2-117">ConciseView</span></span>               |
| `$FormatEnumerationLimit`        | <span data-ttu-id="69ea2-118">4</span><span class="sxs-lookup"><span data-stu-id="69ea2-118">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="69ea2-119">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="69ea2-119">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="69ea2-120">False (não registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-120">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="69ea2-121">False (não registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-121">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="69ea2-122">Verdadeiro (registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-122">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="69ea2-123">Verdadeiro (registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-123">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="69ea2-124">Verdadeiro (registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-124">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="69ea2-125">Verdadeiro (registrado)</span><span class="sxs-lookup"><span data-stu-id="69ea2-125">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="69ea2-126">4096</span><span class="sxs-lookup"><span data-stu-id="69ea2-126">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="69ea2-127">(Caractere de espaço ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="69ea2-127">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="69ea2-128">Objeto UTF8Encoding</span><span class="sxs-lookup"><span data-stu-id="69ea2-128">UTF8Encoding object</span></span>       |
| `$ProgressPreference`            | <span data-ttu-id="69ea2-129">Continuar</span><span class="sxs-lookup"><span data-stu-id="69ea2-129">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="69ea2-130">(Nenhum-tabela de hash vazia)</span><span class="sxs-lookup"><span data-stu-id="69ea2-130">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="69ea2-131">(Nenhuma)</span><span class="sxs-lookup"><span data-stu-id="69ea2-131">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="69ea2-132">Tudo</span><span class="sxs-lookup"><span data-stu-id="69ea2-132">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="69ea2-133">wsman</span><span class="sxs-lookup"><span data-stu-id="69ea2-133">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="69ea2-134">Consulte [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="69ea2-134">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="69ea2-135">(nenhum)</span><span class="sxs-lookup"><span data-stu-id="69ea2-135">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="69ea2-136">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="69ea2-136">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="69ea2-137">Continue</span><span class="sxs-lookup"><span data-stu-id="69ea2-137">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="69ea2-138">Falso</span><span class="sxs-lookup"><span data-stu-id="69ea2-138">False</span></span>                     |

<span data-ttu-id="69ea2-139">O PowerShell inclui as seguintes variáveis de ambiente que armazenam as preferências do usuário.</span><span class="sxs-lookup"><span data-stu-id="69ea2-139">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="69ea2-140">Para obter mais informações sobre essas variáveis de ambiente, consulte [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-140">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="69ea2-141">As alterações na variável de preferência só entram em vigor em scripts e funções se esses scripts ou funções estiverem definidos no mesmo escopo que o escopo no qual a preferência foi usada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-141">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="69ea2-142">Para obter mais informações, consulte [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-142">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="69ea2-143">Trabalhando com variáveis de preferência</span><span class="sxs-lookup"><span data-stu-id="69ea2-143">Working with preference variables</span></span>

<span data-ttu-id="69ea2-144">Este documento descreve cada uma das variáveis de preferência.</span><span class="sxs-lookup"><span data-stu-id="69ea2-144">This document describes each of the preference variables.</span></span>

<span data-ttu-id="69ea2-145">Para exibir o valor atual de uma variável de preferência específica, digite o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-145">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="69ea2-146">Por exemplo, o comando a seguir exibe o `$ConfirmPreference` valor da variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-146">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="69ea2-147">Para alterar o valor de uma variável, use uma instrução de atribuição.</span><span class="sxs-lookup"><span data-stu-id="69ea2-147">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="69ea2-148">Por exemplo, a instrução a seguir altera o `$ConfirmPreference` valor do parâmetro para **médio**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-148">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="69ea2-149">Os valores que você define são específicos para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-149">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="69ea2-150">Para tornar as variáveis efetivas em todas as sessões do PowerShell, adicione-as ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-150">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="69ea2-151">Para obter mais informações, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-151">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="69ea2-152">Trabalhando remotamente</span><span class="sxs-lookup"><span data-stu-id="69ea2-152">Working remotely</span></span>

<span data-ttu-id="69ea2-153">Quando você executa comandos em um computador remoto, os comandos remotos só estão sujeitos às preferências definidas no cliente PowerShell do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-153">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="69ea2-154">Por exemplo, quando você executa um comando remoto, o valor da variável do computador remoto `$DebugPreference` determina como o PowerShell responde às mensagens de depuração.</span><span class="sxs-lookup"><span data-stu-id="69ea2-154">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="69ea2-155">Para obter mais informações sobre comandos remotos, consulte [about_Remote](about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-155">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="69ea2-156">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-156">\$ConfirmPreference</span></span>

<span data-ttu-id="69ea2-157">Determina se o PowerShell solicita automaticamente a confirmação antes de executar um cmdlet ou uma função.</span><span class="sxs-lookup"><span data-stu-id="69ea2-157">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="69ea2-158">Os `$ConfirmPreference` valores válidos da variável são **High**, **Medium** ou **Low**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-158">The `$ConfirmPreference` variable's valid values are **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="69ea2-159">Os cmdlets e funções são atribuídos a um risco de **alta**, **média** ou **baixa**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-159">Cmdlets and functions are assigned a risk of **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="69ea2-160">Quando o valor da `$ConfirmPreference` variável for menor ou igual ao risco atribuído a um cmdlet ou função, o PowerShell solicitará automaticamente a confirmação antes de executar o cmdlet ou a função.</span><span class="sxs-lookup"><span data-stu-id="69ea2-160">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="69ea2-161">Se o valor da `$ConfirmPreference` variável for **None**, o PowerShell nunca o solicitará automaticamente antes de executar um cmdlet ou uma função.</span><span class="sxs-lookup"><span data-stu-id="69ea2-161">If the value of the `$ConfirmPreference` variable is **None**, PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="69ea2-162">Para alterar o comportamento de confirmação de todos os cmdlets e funções na sessão, altere o `$ConfirmPreference` valor da variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-162">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="69ea2-163">Para substituir o `$ConfirmPreference` para um único comando, use o parâmetro **Confirm** de um cmdlet ou de uma função.</span><span class="sxs-lookup"><span data-stu-id="69ea2-163">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="69ea2-164">Para solicitar confirmação, use `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-164">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="69ea2-165">Para suprimir a confirmação, use `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-165">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="69ea2-166">Valores válidos de `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="69ea2-166">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="69ea2-167">**Nenhum**: o PowerShell não é solicitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-167">**None**: PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="69ea2-168">Para solicitar a confirmação de um comando específico, use o parâmetro **Confirm** do cmdlet ou da função.</span><span class="sxs-lookup"><span data-stu-id="69ea2-168">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="69ea2-169">**Baixo**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um risco baixo, médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-169">**Low**: PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="69ea2-170">**Médio**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um médio ou alto risco.</span><span class="sxs-lookup"><span data-stu-id="69ea2-170">**Medium**: PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="69ea2-171">**Alta**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um risco alto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-171">**High**: PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="69ea2-172">Explicação detalhada</span><span class="sxs-lookup"><span data-stu-id="69ea2-172">Detailed explanation</span></span>

<span data-ttu-id="69ea2-173">O PowerShell pode solicitar automaticamente a confirmação antes de realizar uma ação.</span><span class="sxs-lookup"><span data-stu-id="69ea2-173">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="69ea2-174">Por exemplo, quando o cmdlet ou a função afeta significativamente o sistema para excluir dados ou usar uma quantidade significativa de recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="69ea2-174">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-175">A estimativa do risco é um atributo do cmdlet ou da função conhecida como seu **ConfirmImpact**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-175">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="69ea2-176">Os usuários não podem alterá-la.</span><span class="sxs-lookup"><span data-stu-id="69ea2-176">Users can't change it.</span></span>

<span data-ttu-id="69ea2-177">Os cmdlets e funções que podem representar um risco para o sistema têm um parâmetro **Confirm** que você pode usar para solicitar ou suprimir a confirmação de um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-177">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="69ea2-178">Como a maioria dos cmdlets e funções usa o valor de risco padrão, **ConfirmImpact**, de **Medium** e o valor padrão de `$ConfirmPreference` é **alta**, a confirmação automática raramente ocorre.</span><span class="sxs-lookup"><span data-stu-id="69ea2-178">Because most cmdlets and functions use the default risk value, **ConfirmImpact**, of **Medium**, and the default value of `$ConfirmPreference` is **High**, automatic confirmation rarely occurs.</span></span> <span data-ttu-id="69ea2-179">No entanto, você pode ativar a confirmação automática alterando o valor de `$ConfirmPreference` para **médio** ou **baixo**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-179">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-180">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-180">Examples</span></span>

<span data-ttu-id="69ea2-181">Este exemplo mostra o efeito do `$ConfirmPreference` valor padrão da variável, **alto**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-181">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="69ea2-182">O valor **alto** só confirma cmdlets e funções de alto risco.</span><span class="sxs-lookup"><span data-stu-id="69ea2-182">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="69ea2-183">Como a maioria dos cmdlets e funções são de risco médio, eles não são automaticamente confirmados e `Remove-Item` excluem o arquivo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-183">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="69ea2-184">Adicionar `-Confirm` ao comando solicita ao usuário a confirmação.</span><span class="sxs-lookup"><span data-stu-id="69ea2-184">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="69ea2-185">Use `-Confirm` para solicitar confirmação.</span><span class="sxs-lookup"><span data-stu-id="69ea2-185">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-186">O exemplo a seguir mostra o efeito de alterar o valor de `$ConfirmPreference` para **médio**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-186">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="69ea2-187">Como a maioria dos cmdlets e funções são de risco médio, elas são automaticamente confirmadas.</span><span class="sxs-lookup"><span data-stu-id="69ea2-187">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="69ea2-188">Para suprimir o prompt de confirmação de um único comando, use o parâmetro **Confirm** com um valor de `$false` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-188">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="69ea2-189">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-189">\$DebugPreference</span></span>

<span data-ttu-id="69ea2-190">Determina como o PowerShell responde a mensagens de depuração geradas por um script, um cmdlet ou um provedor ou por um `Write-Debug` comando na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-190">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="69ea2-191">Alguns cmdlets exibem mensagens de depuração, que normalmente são mensagens técnicas projetadas para programadores e profissionais de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-191">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="69ea2-192">Por padrão, as mensagens de depuração não são exibidas, mas você pode exibir mensagens de depuração alterando o valor de `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-192">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="69ea2-193">Você pode usar o parâmetro comum de **depuração** de um cmdlet para exibir ou ocultar as mensagens de depuração para um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-193">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="69ea2-194">Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-194">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="69ea2-195">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-195">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-196">**Parar**: exibe a mensagem de depuração e para a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-196">**Stop**: Displays the debug message and stops executing.</span></span> <span data-ttu-id="69ea2-197">Grava um erro no console.</span><span class="sxs-lookup"><span data-stu-id="69ea2-197">Writes an error to the console.</span></span>
- <span data-ttu-id="69ea2-198">**Consultar**: exibe a mensagem de depuração e pergunta se você deseja continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-198">**Inquire**: Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="69ea2-199">Adicionar o parâmetro de **depuração** comum a um comando, quando o comando é configurado para gerar uma mensagem de depuração, altera o valor da `$DebugPreference` variável para **consulta**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-199">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="69ea2-200">**Continuar**: exibe a mensagem de depuração e continua com a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-200">**Continue**: Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="69ea2-201">**SilentlyContinue**: (padrão) sem efeito.</span><span class="sxs-lookup"><span data-stu-id="69ea2-201">**SilentlyContinue**: (Default) No effect.</span></span> <span data-ttu-id="69ea2-202">A mensagem de depuração não é exibida e a execução continua sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="69ea2-202">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-203">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-203">Examples</span></span>

<span data-ttu-id="69ea2-204">Os exemplos a seguir mostram o efeito de alterar os valores de `$DebugPreference` quando um `Write-Debug` comando é inserido na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-204">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="69ea2-205">A alteração afeta todas as mensagens de depuração, incluindo as mensagens geradas por cmdlets e scripts.</span><span class="sxs-lookup"><span data-stu-id="69ea2-205">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="69ea2-206">Os exemplos mostram o parâmetro **debug** , que exibe ou oculta as mensagens de depuração relacionadas a um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-206">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="69ea2-207">Este exemplo mostra o efeito do `$DebugPreference` valor padrão da variável, **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-207">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="69ea2-208">Por padrão, a `Write-Debug` mensagem de depuração do cmdlet não é exibida e o processamento continua.</span><span class="sxs-lookup"><span data-stu-id="69ea2-208">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="69ea2-209">Quando o parâmetro de **depuração** é usado, ele substitui a preferência por um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-209">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="69ea2-210">A mensagem de depuração é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-210">The debug message is displayed.</span></span>

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="69ea2-211">Este exemplo mostra o efeito de `$DebugPreference` com o valor de **continue** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-211">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="69ea2-212">A mensagem de depuração é exibida e o comando continua a processar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-212">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="69ea2-213">Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-213">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="69ea2-214">A mensagem de depuração não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-214">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="69ea2-215">Este exemplo mostra o efeito de `$DebugPreference` ser definido como o valor de **parada** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-215">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="69ea2-216">A mensagem de depuração é exibida e o comando é interrompido.</span><span class="sxs-lookup"><span data-stu-id="69ea2-216">The debug message is displayed and the command is stopped.</span></span>

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

<span data-ttu-id="69ea2-217">Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-217">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="69ea2-218">A mensagem de depuração não é exibida e o processamento não é interrompido.</span><span class="sxs-lookup"><span data-stu-id="69ea2-218">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="69ea2-219">Este exemplo mostra o efeito de `$DebugPreference` ser definido como o valor de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-219">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="69ea2-220">A mensagem de depuração é exibida e a confirmação do usuário é solicitada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-220">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-221">Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-221">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="69ea2-222">A mensagem de depuração não é exibida e o processamento continua.</span><span class="sxs-lookup"><span data-stu-id="69ea2-222">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="69ea2-223">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-223">\$ErrorActionPreference</span></span>

<span data-ttu-id="69ea2-224">Determina como o PowerShell responde a um erro de não encerramento, um erro que não interrompe o processamento do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-224">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="69ea2-225">Por exemplo, na linha de comando ou em um script, cmdlet ou provedor, como os erros gerados pelo `Write-Error` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-225">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="69ea2-226">Você pode usar um parâmetro comum **ErrorAction** de um cmdlet para substituir a preferência para um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-226">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="69ea2-227">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-227">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-228">**Quebra** – Insira o depurador quando ocorrer um erro ou quando uma exceção for gerada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-228">**Break** - Enter the debugger when an error occurs or when an exception is raised.</span></span>
- <span data-ttu-id="69ea2-229">**Continuar**: (padrão) exibe a mensagem de erro e continua em execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-229">**Continue**: (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="69ea2-230">**Ignorar**: suprime a mensagem de erro e continua a executar o comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-230">**Ignore**: Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="69ea2-231">O valor de **ignorar** destina-se ao uso por comando, não para uso como preferência salva.</span><span class="sxs-lookup"><span data-stu-id="69ea2-231">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="69ea2-232">**Ignore** não é um valor válido para a `$ErrorActionPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-232">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="69ea2-233">**Consultar**: exibe a mensagem de erro e pergunta se você deseja continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-233">**Inquire**: Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="69ea2-234">**SilentlyContinue**: nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="69ea2-234">**SilentlyContinue**: No effect.</span></span> <span data-ttu-id="69ea2-235">A mensagem de erro não é exibida e a execução continua sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="69ea2-235">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="69ea2-236">**Parar**: exibe a mensagem de erro e para a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-236">**Stop**: Displays the error message and stops executing.</span></span> <span data-ttu-id="69ea2-237">Além do erro gerado, o valor de **parada** gera um objeto ActionPreferenceStopException para o fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="69ea2-237">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="69ea2-238">fluxo</span><span class="sxs-lookup"><span data-stu-id="69ea2-238">stream</span></span>
- <span data-ttu-id="69ea2-239">**Suspender**: suspende automaticamente uma tarefa de fluxo de trabalho para permitir uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="69ea2-239">**Suspend**: Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="69ea2-240">Após a investigação, o fluxo de trabalho pode ser retomado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-240">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="69ea2-241">O valor de **suspensão** destina-se ao uso por comando, não para uso como preferência salva.</span><span class="sxs-lookup"><span data-stu-id="69ea2-241">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="69ea2-242">**Suspend** não é um valor válido para a `$ErrorActionPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-242">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="69ea2-243">`$ErrorActionPreference` e o parâmetro **ErrorAction** não afeta como o PowerShell responde a erros de encerramento que param o processamento do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-243">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="69ea2-244">Para obter mais informações sobre o parâmetro comum **ErrorAction** , consulte [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-244">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-245">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-245">Examples</span></span>

<span data-ttu-id="69ea2-246">Esses exemplos mostram o efeito dos diferentes valores da `$ErrorActionPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-246">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="69ea2-247">O parâmetro **ErrorAction** é usado para substituir o `$ErrorActionPreference` valor.</span><span class="sxs-lookup"><span data-stu-id="69ea2-247">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="69ea2-248">Este exemplo mostra o `$ErrorActionPreference` valor padrão, **continue**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-248">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="69ea2-249">Um erro de não finalização é gerado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-249">A non-terminating error is generated.</span></span> <span data-ttu-id="69ea2-250">A mensagem é exibida e o processamento continua.</span><span class="sxs-lookup"><span data-stu-id="69ea2-250">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

<span data-ttu-id="69ea2-251">Este exemplo mostra o `$ErrorActionPreference` valor padrão, **inquire**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-251">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="69ea2-252">Um erro é gerado e um prompt de ação é mostrado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-252">An error is generated and a prompt for action is shown.</span></span>

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-253">Este exemplo mostra o `$ErrorActionPreference` conjunto como **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-253">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="69ea2-254">A mensagem de erro é suprimida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-254">The error message is suppressed.</span></span>

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

<span data-ttu-id="69ea2-255">Este exemplo mostra o `$ErrorActionPreference` conjunto a ser **interrompido**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-255">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="69ea2-256">Ele também mostra o objeto extra gerado para a `$Error` variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-256">It also shows the extra object generated to the `$Error` variable.</span></span>

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a><span data-ttu-id="69ea2-257">\$ErrorView</span><span class="sxs-lookup"><span data-stu-id="69ea2-257">\$ErrorView</span></span>

<span data-ttu-id="69ea2-258">Determina o formato de exibição das mensagens de erro no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-258">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="69ea2-259">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-259">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-260">**ConciseView**: (padrão) fornece uma mensagem de erro concisa e uma exibição Refatorada para construtores de módulo avançados.</span><span class="sxs-lookup"><span data-stu-id="69ea2-260">**ConciseView**: (Default) Provides a concise error message and a refactored view for advanced module builders.</span></span> <span data-ttu-id="69ea2-261">A partir do PowerShell 7,2, se o erro for da linha de comando ou de um módulo de script, a saída será uma mensagem de erro de linha única.</span><span class="sxs-lookup"><span data-stu-id="69ea2-261">As of PowerShell 7.2, if the error is from the command line or a script module the output is a single line error message.</span></span> <span data-ttu-id="69ea2-262">Caso contrário, você receberá uma mensagem de erro de várias linhas que contém o erro e um ponteiro para o erro mostrando onde ele ocorre nessa linha.</span><span class="sxs-lookup"><span data-stu-id="69ea2-262">Otherwise, you receive a multiline error message that contains the error and a pointer to the error showing where it occurs in that line.</span></span> <span data-ttu-id="69ea2-263">Se o terminal der suporte ao terminal virtual, os códigos de cor ANSI serão usados para fornecer acentos de cor.</span><span class="sxs-lookup"><span data-stu-id="69ea2-263">If the terminal supports Virtual Terminal, then ANSI color codes are used to provide color accent.</span></span> <span data-ttu-id="69ea2-264">A cor de destaque pode ser alterada em `$Host.PrivateData.ErrorAccentColor` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-264">The Accent color can be changed at `$Host.PrivateData.ErrorAccentColor`.</span></span> <span data-ttu-id="69ea2-265">Use `Get-Error` o cmdlet para uma exibição detalhada abrangente do erro totalmente qualificado, incluindo as exceções internas.</span><span class="sxs-lookup"><span data-stu-id="69ea2-265">Use `Get-Error` cmdlet for a comprehensive detailed view of the fully qualified error, including inner exceptions.</span></span>

  <span data-ttu-id="69ea2-266">**ConciseView** foi adicionado no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="69ea2-266">**ConciseView** was added in PowerShell 7.</span></span>

- <span data-ttu-id="69ea2-267">**NormalView**: uma exibição detalhada projetada para a maioria dos usuários.</span><span class="sxs-lookup"><span data-stu-id="69ea2-267">**NormalView**: A detailed view designed for most users.</span></span> <span data-ttu-id="69ea2-268">Consiste em uma descrição do erro e no nome do objeto envolvido no erro.</span><span class="sxs-lookup"><span data-stu-id="69ea2-268">Consists of a description of the error and the name of the object involved in the error.</span></span>

- <span data-ttu-id="69ea2-269">**CategoryView**: um modo de exibição sucinta e estruturado projetado para ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="69ea2-269">**CategoryView**: A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="69ea2-270">O formato é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69ea2-270">The format is as follows:</span></span>

  <span data-ttu-id="69ea2-271">{Category}: ({TargetName}: {TargetType}): [{atividade}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="69ea2-271">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="69ea2-272">Para obter mais informações sobre os campos em **CategoryView**, consulte classe [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-272">For more information about the fields in **CategoryView**, see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-273">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-273">Examples</span></span>

<span data-ttu-id="69ea2-274">Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é o padrão, **ConciseView**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-274">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="69ea2-275">`Get-ChildItem` é usado para localizar um diretório não existente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-275">`Get-ChildItem` is used to find a non-existent directory.</span></span>

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

<span data-ttu-id="69ea2-276">Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é o padrão, **ConciseView**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-276">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="69ea2-277">`Script.ps1` é executado e gera um erro da `Get-Item` instrução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-277">`Script.ps1` is run and throws an error from `Get-Item` statement.</span></span>

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

<span data-ttu-id="69ea2-278">Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é alterado para **NormalView**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-278">This example shows how an error appears when the value of `$ErrorView` is changed to **NormalView**.</span></span> <span data-ttu-id="69ea2-279">`Get-ChildItem` é usado para localizar um arquivo não existente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-279">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="69ea2-280">Este exemplo mostra como o mesmo erro aparece quando o valor de `$ErrorView` é alterado para **CategoryView**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-280">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="69ea2-281">Este exemplo demonstra que o valor de `$ErrorView` afeta apenas a exibição do erro.</span><span class="sxs-lookup"><span data-stu-id="69ea2-281">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="69ea2-282">Ele não altera a estrutura do objeto de erro que está armazenado na `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="69ea2-282">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="69ea2-283">Para obter informações sobre a `$Error` variável automática, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-283">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="69ea2-284">O comando a seguir usa o objeto **ErrorRecord** associado ao erro mais recente na matriz de erros, o **elemento 0**, e formata todas as propriedades do objeto de erro em uma lista.</span><span class="sxs-lookup"><span data-stu-id="69ea2-284">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0**, and formats all the error object's properties in a list.</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a><span data-ttu-id="69ea2-285">\$FormatEnumerationLimit</span><span class="sxs-lookup"><span data-stu-id="69ea2-285">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="69ea2-286">Determina quantos itens enumerados são incluídos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="69ea2-286">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="69ea2-287">Essa variável não afeta os objetos subjacentes, apenas a exibição.</span><span class="sxs-lookup"><span data-stu-id="69ea2-287">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="69ea2-288">Quando o valor de `$FormatEnumerationLimit` for menor que o número de itens enumerados, o PowerShell adicionará reticências ( `...` ) para indicar itens não mostrados.</span><span class="sxs-lookup"><span data-stu-id="69ea2-288">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="69ea2-289">**Valores válidos**: inteiros ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="69ea2-289">**Valid values**: Integers (`Int32`)</span></span>

<span data-ttu-id="69ea2-290">**Valor padrão**: 4</span><span class="sxs-lookup"><span data-stu-id="69ea2-290">**Default value**: 4</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-291">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-291">Examples</span></span>

<span data-ttu-id="69ea2-292">Este exemplo mostra como usar a `$FormatEnumerationLimit` variável para melhorar a exibição de itens enumerados.</span><span class="sxs-lookup"><span data-stu-id="69ea2-292">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="69ea2-293">O comando neste exemplo gera uma tabela que lista todos os serviços em execução no computador em dois grupos: um para a **execução** de serviços e outro para serviços **interrompidos** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-293">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="69ea2-294">Ele usa um `Get-Service` comando para obter todos os serviços e, em seguida, envia os resultados por meio do pipeline para o `Group-Object` cmdlet, que agrupa os resultados pelo status do serviço.</span><span class="sxs-lookup"><span data-stu-id="69ea2-294">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="69ea2-295">O resultado é uma tabela que lista o status na coluna **nome** e os processos na coluna **grupo** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-295">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="69ea2-296">Para alterar os rótulos de coluna, use uma tabela de hash, consulte [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-296">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="69ea2-297">Para obter mais informações, consulte os exemplos em [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="69ea2-297">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="69ea2-298">Localize o valor atual de `$FormatEnumerationLimit` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-298">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="69ea2-299">Lista todos os serviços agrupados por **status**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-299">List all services grouped by **Status**.</span></span> <span data-ttu-id="69ea2-300">Há um máximo de quatro serviços listados na coluna **grupo** para cada status, pois `$FormatEnumerationLimit` o tem um valor de **4**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-300">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="69ea2-301">Para aumentar o número de itens listados, aumente o valor de `$FormatEnumerationLimit` para **1000**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-301">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="69ea2-302">Use `Get-Service` e `Group-Object` para exibir os serviços.</span><span class="sxs-lookup"><span data-stu-id="69ea2-302">Use `Get-Service` and `Group-Object` to display the services.</span></span>

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

<span data-ttu-id="69ea2-303">Use `Format-Table` com o parâmetro **Wrap** para exibir a lista de serviços.</span><span class="sxs-lookup"><span data-stu-id="69ea2-303">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a><span data-ttu-id="69ea2-304">\$InformationPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-304">\$InformationPreference</span></span>

<span data-ttu-id="69ea2-305">A `$InformationPreference` variável permite definir as preferências de fluxo de informações que você deseja exibir aos usuários.</span><span class="sxs-lookup"><span data-stu-id="69ea2-305">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="69ea2-306">Especificamente, as mensagens informativas que você adicionou a comandos ou scripts adicionando o cmdlet [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-306">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="69ea2-307">Se o parâmetro **informationaction** for usado, seu valor substituirá o valor da `$InformationPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-307">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="69ea2-308">`Write-Information` foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="69ea2-308">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="69ea2-309">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-309">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-310">**Stop**: interrompe um comando ou script em uma ocorrência do `Write-Information` comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-310">**Stop**: Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="69ea2-311">**Consultar**: exibe a mensagem informativa que você especifica em um `Write-Information` comando e pergunta se deseja continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-311">**Inquire**: Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="69ea2-312">**Continuar**: exibe a mensagem informativa e continua em execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-312">**Continue**: Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="69ea2-313">A **suspensão** está disponível somente para fluxos de trabalho que não têm suporte no PowerShell 6 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="69ea2-313">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="69ea2-314">**SilentlyContinue**: (padrão) sem efeito.</span><span class="sxs-lookup"><span data-stu-id="69ea2-314">**SilentlyContinue**: (Default) No effect.</span></span> <span data-ttu-id="69ea2-315">As mensagens informativas não são exibidas e o script continua sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="69ea2-315">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="69ea2-316">\$Evento log \*</span><span class="sxs-lookup"><span data-stu-id="69ea2-316">\$Log\*Event</span></span>

<span data-ttu-id="69ea2-317">As variáveis de preferência de \*\*evento log \*\*\* determinam quais tipos de eventos são gravados no log de eventos do PowerShell em Visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="69ea2-317">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="69ea2-318">Por padrão, somente os eventos de mecanismo e provedor são registrados em log.</span><span class="sxs-lookup"><span data-stu-id="69ea2-318">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="69ea2-319">Mas, você pode usar as variáveis de preferência de \*\*evento log \*\*\* para personalizar o log, como registrar eventos sobre comandos.</span><span class="sxs-lookup"><span data-stu-id="69ea2-319">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="69ea2-320">As variáveis de preferência de \*\*evento log \*\*\* são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-320">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="69ea2-321">`$LogCommandHealthEvent`: Registra erros e exceções na inicialização e no processamento do comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-321">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="69ea2-322">O padrão é `$false` (não registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-322">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="69ea2-323">`$LogCommandLifecycleEvent`: Registra o início e a interrupção de comandos e pipelines de comando e exceções de segurança na descoberta de comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-323">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="69ea2-324">O padrão é `$false` (não registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-324">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="69ea2-325">`$LogEngineHealthEvent`: Registra erros e falhas de sessões.</span><span class="sxs-lookup"><span data-stu-id="69ea2-325">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="69ea2-326">O padrão é `$true` (registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-326">The default is `$true` (logged).</span></span>
- <span data-ttu-id="69ea2-327">`$LogEngineLifecycleEvent`: Registra a abertura e o fechamento de sessões.</span><span class="sxs-lookup"><span data-stu-id="69ea2-327">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="69ea2-328">O padrão é `$true` (registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-328">The default is `$true` (logged).</span></span>
- <span data-ttu-id="69ea2-329">`$LogProviderHealthEvent`: Registra erros do provedor, como erros de leitura e gravação, erros de pesquisa e erros de invocação.</span><span class="sxs-lookup"><span data-stu-id="69ea2-329">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="69ea2-330">O padrão é `$true` (registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-330">The default is `$true` (logged).</span></span>
- <span data-ttu-id="69ea2-331">`$LogProviderLifecycleEvent`: Logs adicionando e removendo provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-331">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="69ea2-332">O padrão é `$true` (registrado).</span><span class="sxs-lookup"><span data-stu-id="69ea2-332">The default is `$true` (logged).</span></span> <span data-ttu-id="69ea2-333">Para obter informações sobre provedores do PowerShell, consulte [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-333">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="69ea2-334">Para habilitar um \*\*evento log \*\*\*, digite a variável com um valor de `$true` , por exemplo:</span><span class="sxs-lookup"><span data-stu-id="69ea2-334">To enable a **Log\*Event**, type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="69ea2-335">Para desabilitar um tipo de evento, digite a variável com um valor de `$false` , por exemplo:</span><span class="sxs-lookup"><span data-stu-id="69ea2-335">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="69ea2-336">Os eventos que você habilita são efetivos apenas para o console atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-336">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="69ea2-337">Para aplicar a configuração a todos os consoles, salve as configurações de variável em seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-337">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="69ea2-338">Para obter mais informações, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-338">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="69ea2-339">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="69ea2-339">\$MaximumHistoryCount</span></span>

<span data-ttu-id="69ea2-340">Determina quantos comandos são salvos no histórico de comandos para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="69ea2-340">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="69ea2-341">**Valores válidos**: 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="69ea2-341">**Valid values**: 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="69ea2-342">**Padrão**: 4096</span><span class="sxs-lookup"><span data-stu-id="69ea2-342">**Default**: 4096</span></span>

<span data-ttu-id="69ea2-343">Para determinar o número de comandos salvos no momento no histórico de comandos, digite:</span><span class="sxs-lookup"><span data-stu-id="69ea2-343">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="69ea2-344">Para ver os comandos salvos em seu histórico de sessão, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-344">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="69ea2-345">Para obter mais informações, consulte [about_History](about_History.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-345">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="69ea2-346">\$OFS</span><span class="sxs-lookup"><span data-stu-id="69ea2-346">\$OFS</span></span>

<span data-ttu-id="69ea2-347">O separador de campo de saída (OFS) especifica o caractere que separa os elementos de uma matriz que é convertida em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69ea2-347">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="69ea2-348">**Valores válidos**: qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69ea2-348">**Valid values**: Any string.</span></span>

<span data-ttu-id="69ea2-349">**Padrão**: espaço</span><span class="sxs-lookup"><span data-stu-id="69ea2-349">**Default**: Space</span></span>

<span data-ttu-id="69ea2-350">Por padrão, a `$OFS` variável não existe e o separador de arquivo de saída é um espaço, mas você pode adicionar essa variável e defini-la como qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69ea2-350">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="69ea2-351">Você pode alterar o valor de `$OFS` em sua sessão, digitando `$OFS="<value>"` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-351">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="69ea2-352">Se você estiver esperando o valor padrão de um espaço ( `" "` ) em seu script, módulo ou saída de configuração, tenha cuidado para que o `$OFS` valor padrão não tenha sido alterado em outro lugar em seu código.</span><span class="sxs-lookup"><span data-stu-id="69ea2-352">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-353">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-353">Examples</span></span>

<span data-ttu-id="69ea2-354">Este exemplo mostra que um espaço é usado para separar os valores quando uma matriz é convertida em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69ea2-354">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="69ea2-355">Nesse caso, uma matriz de inteiros é armazenada em uma variável e, em seguida, a variável é convertida como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69ea2-355">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="69ea2-356">Para alterar o separador, adicione a `$OFS` variável atribuindo um valor a ela.</span><span class="sxs-lookup"><span data-stu-id="69ea2-356">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="69ea2-357">A variável deve ser nomeada `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-357">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="69ea2-358">Para restaurar o comportamento padrão, você pode atribuir um espaço ( `" "` ) ao valor `$OFS` ou excluir a variável.</span><span class="sxs-lookup"><span data-stu-id="69ea2-358">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="69ea2-359">Os comandos a seguir excluem a variável e, em seguida, verificam se o separador é um espaço.</span><span class="sxs-lookup"><span data-stu-id="69ea2-359">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="69ea2-360">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="69ea2-360">\$OutputEncoding</span></span>

<span data-ttu-id="69ea2-361">Determina o método de codificação de caracteres que o PowerShell usa quando envia texto para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="69ea2-361">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="69ea2-362">Por exemplo, se um aplicativo retornar cadeias de caracteres Unicode para o PowerShell, talvez seja necessário alterar o valor para **UnicodeEncoding** para enviar os caracteres corretamente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-362">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="69ea2-363">Os valores válidos são os seguintes: objetos derivados de uma classe de codificação, como **ASCIIEncoding**, **SBCSCodePageEncoding**, **UTF7Encoding**, **UTF8Encoding**, **UTF32Encoding** e **UnicodeEncoding**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-363">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding**, **SBCSCodePageEncoding**, **UTF7Encoding**, **UTF8Encoding**, **UTF32Encoding**, and **UnicodeEncoding**.</span></span>

<span data-ttu-id="69ea2-364">**Padrão**: objeto UTF8Encoding (System. Text. UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="69ea2-364">**Default**: UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-365">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-365">Examples</span></span>

<span data-ttu-id="69ea2-366">Este exemplo mostra como fazer com que o comando **findstr.exe** do Windows funcione no PowerShell em um computador localizado para um idioma que usa caracteres Unicode, como o chinês.</span><span class="sxs-lookup"><span data-stu-id="69ea2-366">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="69ea2-367">O primeiro comando localiza o valor de `$OutputEncoding` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-367">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="69ea2-368">Como o valor é um objeto de codificação, exiba somente sua propriedade **EncodingName** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-368">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="69ea2-369">Neste exemplo, um comando **findstr.exe** é usado para pesquisar dois caracteres chineses que estão presentes no `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-369">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="69ea2-370">Quando esse comando de **findstr.exe** é executado no prompt de comando do Windows (**cmd.exe**), **findstr.exe** localiza os caracteres no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-370">When this **findstr.exe** command is run in the Windows Command Prompt (**cmd.exe**), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="69ea2-371">No entanto, quando você executa o mesmo comando **findstr.exe** no PowerShell, os caracteres não são encontrados porque o PowerShell os envia para **findstr.exe** em texto ASCII, em vez de em texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="69ea2-371">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="69ea2-372">Para fazer com que o comando funcione no PowerShell, defina o valor de `$OutputEncoding` para o valor da propriedade **OutputEncoding** do console do, que se baseia na localidade selecionada para Windows.</span><span class="sxs-lookup"><span data-stu-id="69ea2-372">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="69ea2-373">Como **OutputEncoding** é uma propriedade estática do console, use dois-pontos duplos ( `::` ) no comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-373">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="69ea2-374">Após a alteração da codificação, o comando **findstr.exe** localiza os caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="69ea2-374">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="69ea2-375">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-375">\$ProgressPreference</span></span>

<span data-ttu-id="69ea2-376">Determina como o PowerShell responde a atualizações de progresso geradas por um script, um cmdlet ou um provedor, como as barras de progresso geradas pelo cmdlet [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-376">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="69ea2-377">O `Write-Progress` cmdlet cria barras de progresso que mostram o status de um comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-377">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="69ea2-378">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-378">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-379">**Parar**: não exibe a barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-379">**Stop**: Doesn't display the progress bar.</span></span> <span data-ttu-id="69ea2-380">Em vez disso, ele exibe uma mensagem de erro e para de executar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-380">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="69ea2-381">**Consultar**: não exibe a barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-381">**Inquire**: Doesn't display the progress bar.</span></span> <span data-ttu-id="69ea2-382">Solicita permissão para continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-382">Prompts for permission to continue.</span></span> <span data-ttu-id="69ea2-383">Se você responder com `Y` ou `A` , ele exibirá a barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-383">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="69ea2-384">**Continuar**: (padrão) exibe a barra de progresso e continua com a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-384">**Continue**: (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="69ea2-385">**SilentlyContinue**: executa o comando, mas não exibe a barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-385">**SilentlyContinue**: Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="69ea2-386">\$PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="69ea2-386">\$PSEmailServer</span></span>

<span data-ttu-id="69ea2-387">Especifica o servidor de email padrão que é usado para enviar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="69ea2-387">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="69ea2-388">Essa variável de preferência é usada por cmdlets que enviam email, como o cmdlet [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-388">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="69ea2-389">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="69ea2-389">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="69ea2-390">Especifica valores padrão para os parâmetros de cmdlets e funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="69ea2-390">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="69ea2-391">O valor de `$PSDefaultParameterValues` é uma tabela de hash em que a chave consiste no nome do cmdlet e no nome do parâmetro separados por dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="69ea2-391">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="69ea2-392">O valor é um valor padrão personalizado que você especifica.</span><span class="sxs-lookup"><span data-stu-id="69ea2-392">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="69ea2-393">`$PSDefaultParameterValues` foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="69ea2-393">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="69ea2-394">Para obter mais informações sobre essa variável de preferência, consulte [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-394">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="69ea2-395">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-395">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="69ea2-396">Habilita e desabilita a importação automática de módulos na sessão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-396">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="69ea2-397">**All** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-397">**All** is the default.</span></span> <span data-ttu-id="69ea2-398">Independentemente do valor da variável, você pode usar [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) para importar um módulo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-398">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="69ea2-399">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="69ea2-399">Valid values are:</span></span>

- <span data-ttu-id="69ea2-400">**Todos: os** módulos são importados automaticamente no primeiro uso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-400">**All**: Modules are imported automatically on first-use.</span></span> <span data-ttu-id="69ea2-401">Para importar um módulo, obtenha ou use qualquer comando no módulo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-401">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="69ea2-402">Por exemplo, use `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="69ea2-402">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="69ea2-403">**ModuleQualified**: os módulos são importados automaticamente somente quando um usuário usa o nome qualificado por módulo de um comando no módulo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-403">**ModuleQualified**: Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="69ea2-404">Por exemplo, se o usuário digitar `MyModule\MyCommand` , o PowerShell importará o módulo **MyModule** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-404">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="69ea2-405">**Nenhum**: a importação automática de módulos está desabilitada na sessão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-405">**None**: Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="69ea2-406">Para importar um módulo, use o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-406">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="69ea2-407">Para obter mais informações sobre a importação automática de módulos, consulte [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-407">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="69ea2-408">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="69ea2-408">\$PSSessionApplicationName</span></span>

<span data-ttu-id="69ea2-409">Especifica o nome do aplicativo padrão para um comando remoto que usa a tecnologia de serviços da Web para gerenciamento (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="69ea2-409">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="69ea2-410">Para obter mais informações, consulte [About gerenciamento remoto do Windows](/windows/win32/winrm/about-windows-remote-management).</span><span class="sxs-lookup"><span data-stu-id="69ea2-410">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="69ea2-411">O nome do aplicativo padrão do sistema é `WSMAN` , mas você pode usar essa variável de preferência para alterar o padrão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-411">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="69ea2-412">O nome do aplicativo é o último nó em um URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-412">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="69ea2-413">Por exemplo, o nome do aplicativo no exemplo de URI a seguir é `WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-413">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="69ea2-414">O nome do aplicativo padrão é usado quando o comando remoto não especifica um URI de conexão ou um nome de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-414">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="69ea2-415">O serviço **WinRM** usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-415">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="69ea2-416">O valor do parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-416">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="69ea2-417">Para substituir o padrão do sistema e o valor dessa variável e selecionar um nome de aplicativo diferente para uma sessão específica, use os parâmetros **conexãouri** ou **ApplicationName** dos cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)ou [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-417">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="69ea2-418">A `$PSSessionApplicationName` variável de preferência é definida no computador local, mas especifica um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-418">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="69ea2-419">Se o nome do aplicativo especificado não existir no computador remoto, o comando para estabelecer a sessão falhará.</span><span class="sxs-lookup"><span data-stu-id="69ea2-419">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="69ea2-420">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="69ea2-420">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="69ea2-421">Especifica a configuração de sessão padrão usada para **PSSessions** criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="69ea2-421">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="69ea2-422">Essa variável de preferência é definida no computador local, mas especifica uma configuração de sessão que está localizada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-422">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="69ea2-423">O valor da `$PSSessionConfigurationName` variável é um URI de recurso totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-423">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="69ea2-424">O valor padrão `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indica a configuração de sessão do **Microsoft. PowerShell** no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-424">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="69ea2-425">Se você especificar apenas um nome de configuração, o seguinte URI de esquema será anexado:</span><span class="sxs-lookup"><span data-stu-id="69ea2-425">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="69ea2-426">Você pode substituir o padrão e selecionar uma configuração de sessão diferente para uma sessão específica usando o parâmetro **ConfigurationName** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets, ou.</span><span class="sxs-lookup"><span data-stu-id="69ea2-426">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="69ea2-427">Você pode alterar o valor dessa variável a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="69ea2-427">You can change the value of this variable at any time.</span></span> <span data-ttu-id="69ea2-428">Quando você fizer isso, lembre-se de que a configuração de sessão selecionada deve existir no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="69ea2-428">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="69ea2-429">Caso contrário, o comando para criar uma sessão que usa a configuração de sessão falhará.</span><span class="sxs-lookup"><span data-stu-id="69ea2-429">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="69ea2-430">Essa variável de preferência não determina quais configurações de sessão local são usadas quando usuários remotos criam uma sessão que se conecta a este computador.</span><span class="sxs-lookup"><span data-stu-id="69ea2-430">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="69ea2-431">No entanto, você pode usar as permissões para as configurações de sessão local para determinar quais usuários podem usá-las.</span><span class="sxs-lookup"><span data-stu-id="69ea2-431">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="69ea2-432">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="69ea2-432">\$PSSessionOption</span></span>

<span data-ttu-id="69ea2-433">Estabelece os valores padrão para opções de usuário avançadas em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="69ea2-433">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="69ea2-434">Essas preferências de opção substituem os valores padrão do sistema para as opções de sessão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-434">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="69ea2-435">A `$PSSessionOption` variável contém um objeto **PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-435">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="69ea2-436">Para obter mais informações, consulte [System. Management. Automation. Remoting. PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span><span class="sxs-lookup"><span data-stu-id="69ea2-436">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="69ea2-437">Cada propriedade do objeto representa uma opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-437">Each property of the object represents a session option.</span></span> <span data-ttu-id="69ea2-438">Por exemplo, a propriedade **NoCompression** desativa a compactação de dados durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-438">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="69ea2-439">Por padrão, a `$PSSessionOption` variável contém um objeto **PSSessionOption** com os valores padrão para todas as opções, como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-439">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

<span data-ttu-id="69ea2-440">Para obter descrições dessas opções e mais informações, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="69ea2-440">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="69ea2-441">Para obter mais informações sobre comandos e sessões remotas, consulte [about_Remote](about_Remote.md) e [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-441">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="69ea2-442">Para alterar o valor da `$PSSessionOption` variável de preferência, use o `New-PSSessionOption` cmdlet para criar um objeto **PSSessionOption** com os valores de opção que você preferir.</span><span class="sxs-lookup"><span data-stu-id="69ea2-442">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="69ea2-443">Salve a saída em uma variável chamada `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-443">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="69ea2-444">Para usar a `$PSSessionOption` variável de preferência em cada sessão do PowerShell, adicione um `New-PSSessionOption` comando que cria a `$PSSessionOption` variável ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-444">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="69ea2-445">Para obter mais informações, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-445">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="69ea2-446">Você pode definir opções personalizadas para uma sessão remota específica.</span><span class="sxs-lookup"><span data-stu-id="69ea2-446">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="69ea2-447">As opções definidas têm precedência sobre os padrões do sistema e o valor da variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="69ea2-447">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="69ea2-448">Para definir opções de sessão personalizadas, use o `New-PSSessionOption` cmdlet para criar um objeto **PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-448">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="69ea2-449">Em seguida, use o objeto **PSSessionOption** como o valor do parâmetro **SessionOption** em cmdlets que criam uma sessão, como `New-PSSession` , `Enter-PSSession` e `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-449">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="69ea2-450">$Transcript</span><span class="sxs-lookup"><span data-stu-id="69ea2-450">$Transcript</span></span>

<span data-ttu-id="69ea2-451">Usado pelo `Start-Transcript` para especificar o nome e o local do arquivo de transcrição.</span><span class="sxs-lookup"><span data-stu-id="69ea2-451">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="69ea2-452">Se você não especificar um valor para o parâmetro **path** , o `Start-Transcript` usará o caminho no valor da `$Transcript` variável global.</span><span class="sxs-lookup"><span data-stu-id="69ea2-452">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="69ea2-453">Se você não tiver criado essa variável, `Start-Transcript` o armazenará as transcrições no `$Home\My Documents` diretório como `\PowerShell_transcript.<time-stamp>.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="69ea2-453">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="69ea2-454">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-454">\$VerbosePreference</span></span>

<span data-ttu-id="69ea2-455">Determina como o PowerShell responde a mensagens detalhadas geradas por um script, um cmdlet ou um provedor, como as mensagens geradas pelo cmdlet [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-455">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="69ea2-456">As mensagens detalhadas descrevem as ações executadas para executar um comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-456">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="69ea2-457">Por padrão, as mensagens detalhadas não são exibidas, mas você pode alterar esse comportamento alterando o valor de `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-457">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="69ea2-458">Você pode usar o parâmetro comum **detalhado** de um cmdlet para exibir ou ocultar as mensagens detalhadas de um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-458">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="69ea2-459">Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-459">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="69ea2-460">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-460">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-461">**Parar**: exibe a mensagem detalhada e uma mensagem de erro e, em seguida, interrompe a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-461">**Stop**: Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="69ea2-462">**Consultar**: exibe a mensagem detalhada e, em seguida, exibe um prompt que pergunta se você deseja continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-462">**Inquire**: Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="69ea2-463">**Continuar**: exibe a mensagem detalhada e continua com a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-463">**Continue**: Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="69ea2-464">**SilentlyContinue**: (padrão) não exibe a mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-464">**SilentlyContinue**: (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="69ea2-465">Continua em execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-465">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-466">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-466">Examples</span></span>

<span data-ttu-id="69ea2-467">Esses exemplos mostram o efeito dos diferentes valores de `$VerbosePreference` e o parâmetro **Verbose** para substituir o valor de preferência.</span><span class="sxs-lookup"><span data-stu-id="69ea2-467">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="69ea2-468">Este exemplo mostra o efeito do valor **SilentlyContinue** , que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="69ea2-468">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="69ea2-469">O comando usa o parâmetro **Message** , mas não grava uma mensagem no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ea2-469">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="69ea2-470">Quando o parâmetro **Verbose** é usado, a mensagem é gravada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-470">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="69ea2-471">Este exemplo mostra o efeito do valor de **continuação** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-471">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="69ea2-472">A `$VerbosePreference` variável é definida como **continuar** e a mensagem é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-472">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="69ea2-473">Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor **continue** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-473">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="69ea2-474">A mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-474">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="69ea2-475">Este exemplo mostra o efeito do valor de **parada** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-475">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="69ea2-476">A `$VerbosePreference` variável é definida como **parar** e a mensagem é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-476">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="69ea2-477">O comando é interrompido.</span><span class="sxs-lookup"><span data-stu-id="69ea2-477">The command is stopped.</span></span>

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="69ea2-478">Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor de **parada** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-478">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="69ea2-479">A mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-479">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="69ea2-480">Este exemplo mostra o efeito do valor de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-480">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="69ea2-481">A `$VerbosePreference` variável é definida como **inquire**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-481">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="69ea2-482">A mensagem é exibida e a confirmação do usuário é solicitada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-482">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-483">Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-483">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="69ea2-484">O usuário não é solicitado e a mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-484">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="69ea2-485">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-485">\$WarningPreference</span></span>

<span data-ttu-id="69ea2-486">Determina como o PowerShell responde a mensagens de aviso geradas por um script, um cmdlet ou um provedor, como as mensagens geradas pelo cmdlet [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) .</span><span class="sxs-lookup"><span data-stu-id="69ea2-486">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="69ea2-487">Por padrão, as mensagens de aviso são exibidas e a execução continua, mas você pode alterar esse comportamento alterando o valor de `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-487">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="69ea2-488">Você pode usar o parâmetro de **aviso** comum de um cmdlet para determinar como o PowerShell responde a avisos de um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-488">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="69ea2-489">Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="69ea2-489">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="69ea2-490">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-490">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-491">**Parar**: exibe a mensagem de aviso e uma mensagem de erro e, em seguida, interrompe a execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-491">**Stop**: Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="69ea2-492">**Consultar**: exibe a mensagem de aviso e solicita permissão para continuar.</span><span class="sxs-lookup"><span data-stu-id="69ea2-492">**Inquire**: Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="69ea2-493">**Continuar**: (padrão) exibe a mensagem de aviso e continua em execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-493">**Continue**: (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="69ea2-494">**SilentlyContinue**: não exibe a mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-494">**SilentlyContinue**: Doesn't display the warning message.</span></span> <span data-ttu-id="69ea2-495">Continua em execução.</span><span class="sxs-lookup"><span data-stu-id="69ea2-495">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-496">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-496">Examples</span></span>

<span data-ttu-id="69ea2-497">Esses exemplos mostram o efeito dos diferentes valores de `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-497">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="69ea2-498">O parâmetro **WarningAction** substitui o valor de preferência.</span><span class="sxs-lookup"><span data-stu-id="69ea2-498">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="69ea2-499">Este exemplo mostra o efeito do valor padrão, **continue**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-499">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="69ea2-500">Este exemplo usa o parâmetro **WarningAction** com o valor **SilentlyContinue** para suprimir o aviso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-500">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="69ea2-501">A mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-501">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="69ea2-502">Este exemplo altera a `$WarningPreference` variável para o valor **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-502">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="69ea2-503">A mensagem não é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-503">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="69ea2-504">Este exemplo usa o parâmetro **WarningAction** para parar quando um aviso é gerado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-504">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

<span data-ttu-id="69ea2-505">Este exemplo altera a `$WarningPreference` variável para o valor de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-505">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="69ea2-506">A confirmação do usuário é solicitada.</span><span class="sxs-lookup"><span data-stu-id="69ea2-506">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="69ea2-507">Este exemplo usa o parâmetro **WarningAction** com o valor **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-507">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="69ea2-508">O comando continua a ser executado e nenhuma mensagem é exibida.</span><span class="sxs-lookup"><span data-stu-id="69ea2-508">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="69ea2-509">Este exemplo altera o `$WarningPreference` valor para **parar**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-509">This example changes the `$WarningPreference` value to **Stop**.</span></span>

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

<span data-ttu-id="69ea2-510">Este exemplo usa o **avisoaction** com o valor de **consulta** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-510">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="69ea2-511">O usuário receberá uma solicitação quando ocorrer um aviso.</span><span class="sxs-lookup"><span data-stu-id="69ea2-511">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="69ea2-512">\$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="69ea2-512">\$WhatIfPreference</span></span>

<span data-ttu-id="69ea2-513">Determina se o **WhatIf** é habilitado automaticamente para cada comando que dá suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="69ea2-513">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="69ea2-514">Quando o **WhatIf** é habilitado, o cmdlet relata o efeito esperado do comando, mas não executa o comando.</span><span class="sxs-lookup"><span data-stu-id="69ea2-514">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="69ea2-515">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69ea2-515">The valid values are as follows:</span></span>

- <span data-ttu-id="69ea2-516">**False** (**0**, não habilitado): (padrão) **WhatIf** não é habilitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="69ea2-516">**False** (**0**, not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="69ea2-517">Para habilitá-lo manualmente, use o parâmetro **WhatIf** do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69ea2-517">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="69ea2-518">**True** (**1**, Enabled): **WhatIf** é habilitado automaticamente em qualquer comando que ofereça suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="69ea2-518">**True** (**1**, enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="69ea2-519">Os usuários podem usar o parâmetro **WhatIf** com um valor de **false** para desabilitá-lo manualmente, como `-WhatIf:$false` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-519">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="69ea2-520">Exemplos</span><span class="sxs-lookup"><span data-stu-id="69ea2-520">Examples</span></span>

<span data-ttu-id="69ea2-521">Esses exemplos mostram o efeito dos diferentes valores de `$WhatIfPreference` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-521">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="69ea2-522">Eles mostram como usar o parâmetro **WhatIf** para substituir o valor de preferência para um comando específico.</span><span class="sxs-lookup"><span data-stu-id="69ea2-522">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="69ea2-523">Este exemplo mostra o efeito da `$WhatIfPreference` variável definida como o valor padrão, **false**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-523">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="69ea2-524">Use `Get-ChildItem` para verificar se o arquivo existe.</span><span class="sxs-lookup"><span data-stu-id="69ea2-524">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="69ea2-525">`Remove-Item` exclui o arquivo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-525">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="69ea2-526">Depois que o arquivo for excluído, você poderá verificar a exclusão com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-526">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

<span data-ttu-id="69ea2-527">Este exemplo mostra o efeito de usar o parâmetro **WhatIf** quando o valor de `$WhatIfPreference` é **false**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-527">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="69ea2-528">Verifique se o arquivo existe.</span><span class="sxs-lookup"><span data-stu-id="69ea2-528">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="69ea2-529">Use o parâmetro **WhatIf** para determinar o resultado da tentativa de excluir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-529">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="69ea2-530">Verifique se o arquivo não foi excluído.</span><span class="sxs-lookup"><span data-stu-id="69ea2-530">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="69ea2-531">Este exemplo mostra o efeito da `$WhatIfPreference` variável definida como o valor, **true**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-531">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="69ea2-532">Quando você usa `Remove-Item` para excluir um arquivo, o caminho do arquivo é exibido, mas o arquivo não é excluído.</span><span class="sxs-lookup"><span data-stu-id="69ea2-532">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="69ea2-533">Tentativa de excluir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="69ea2-533">Attempt to delete a file.</span></span> <span data-ttu-id="69ea2-534">Uma mensagem é exibida sobre o que aconteceria se `Remove-Item` fosse executado, mas o arquivo não é excluído.</span><span class="sxs-lookup"><span data-stu-id="69ea2-534">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="69ea2-535">Use `Get-ChildItem` para verificar se o arquivo não foi excluído.</span><span class="sxs-lookup"><span data-stu-id="69ea2-535">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="69ea2-536">Este exemplo mostra como excluir um arquivo quando o valor de `$WhatIfPreference` for **true**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-536">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="69ea2-537">Ele usa o parâmetro **WhatIf** com um valor de `$false` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-537">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="69ea2-538">Use `Get-ChildItem` para verificar se o arquivo foi excluído.</span><span class="sxs-lookup"><span data-stu-id="69ea2-538">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="69ea2-539">Veja a seguir exemplos do `Get-Process` cmdlet que não dá suporte a **WhatIf** e `Stop-Process` que oferece suporte a **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-539">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="69ea2-540">O `$WhatIfPreference` valor da variável é **true**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-540">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="69ea2-541">`Get-Process` Não dá suporte a **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-541">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="69ea2-542">Quando o comando é executado, ele exibe o processo **Winword** .</span><span class="sxs-lookup"><span data-stu-id="69ea2-542">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="69ea2-543">`Stop-Process` o oferece suporte a **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="69ea2-543">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="69ea2-544">O processo de **Winword** não está parado.</span><span class="sxs-lookup"><span data-stu-id="69ea2-544">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="69ea2-545">Você pode substituir o `Stop-Process` comportamento de **WhatIf** usando o parâmetro **WhatIf** com um valor de `$false` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-545">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="69ea2-546">O processo de **Winword** foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="69ea2-546">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="69ea2-547">Para verificar se o processo de **Winword** foi interrompido, use `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="69ea2-547">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="69ea2-548">Confira também</span><span class="sxs-lookup"><span data-stu-id="69ea2-548">See also</span></span>

[<span data-ttu-id="69ea2-549">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="69ea2-549">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="69ea2-550">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="69ea2-550">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="69ea2-551">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="69ea2-551">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="69ea2-552">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="69ea2-552">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="69ea2-553">about_Remote</span><span class="sxs-lookup"><span data-stu-id="69ea2-553">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="69ea2-554">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="69ea2-554">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="69ea2-555">about_Variables</span><span class="sxs-lookup"><span data-stu-id="69ea2-555">about_Variables</span></span>](about_Variables.md)

