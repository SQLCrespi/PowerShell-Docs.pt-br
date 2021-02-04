---
description: Descreve os parâmetros que podem ser usados com qualquer cmdlet.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 898f0897638523291751ce75db1c6a6b4628e778
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860672"
---
# <a name="about-commonparameters"></a><span data-ttu-id="e61b2-104">Sobre CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e61b2-104">About CommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="e61b2-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="e61b2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e61b2-106">Descreve os parâmetros que podem ser usados com qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-106">Describes the parameters that can be used with any cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="e61b2-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="e61b2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e61b2-108">Os parâmetros comuns são um conjunto de parâmetros de cmdlet que você pode usar com qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-108">The common parameters are a set of cmdlet parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="e61b2-109">Eles são implementados pelo PowerShell, não pelo desenvolvedor de cmdlets e estão automaticamente disponíveis para qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-109">They're implemented by PowerShell, not by the cmdlet developer, and they're automatically available to any cmdlet.</span></span>

<span data-ttu-id="e61b2-110">Você pode usar os parâmetros comuns com qualquer cmdlet, mas eles podem não ter um efeito sobre todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e61b2-110">You can use the common parameters with any cmdlet, but they might not have an effect on all cmdlets.</span></span> <span data-ttu-id="e61b2-111">Por exemplo, se um cmdlet não gerar nenhuma saída detalhada, o uso do parâmetro comum **Verbose** não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="e61b2-111">For example, if a cmdlet doesn't generate any verbose output, using the **Verbose** common parameter has no effect.</span></span>

<span data-ttu-id="e61b2-112">Os parâmetros comuns também estão disponíveis em funções avançadas que usam o atributo **CmdletBinding** ou o atributo de **parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-112">The common parameters are also available on advanced functions that use the **CmdletBinding** attribute or the **Parameter** attribute.</span></span>

<span data-ttu-id="e61b2-113">Vários parâmetros comuns substituem os padrões ou as preferências do sistema que você define usando as variáveis de preferência do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e61b2-113">Several common parameters override system defaults or preferences that you set by using the PowerShell preference variables.</span></span> <span data-ttu-id="e61b2-114">Ao contrário das variáveis de preferência, os parâmetros comuns afetam apenas os comandos nos quais eles são usados.</span><span class="sxs-lookup"><span data-stu-id="e61b2-114">Unlike the preference variables, the common parameters affect only the commands in which they're used.</span></span>

<span data-ttu-id="e61b2-115">Para obter mais informações, consulte [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e61b2-115">For more information, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

<span data-ttu-id="e61b2-116">A lista a seguir exibe os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="e61b2-116">The following list displays the common parameters.</span></span> <span data-ttu-id="e61b2-117">Seus aliases são listados entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="e61b2-117">Their aliases are listed in parentheses.</span></span>

- <span data-ttu-id="e61b2-118">**Debug** (db)</span><span class="sxs-lookup"><span data-stu-id="e61b2-118">**Debug** (db)</span></span>
- <span data-ttu-id="e61b2-119">**Erroaction** (ea)</span><span class="sxs-lookup"><span data-stu-id="e61b2-119">**ErrorAction** (ea)</span></span>
- <span data-ttu-id="e61b2-120">**ErrorVariable** (EV)</span><span class="sxs-lookup"><span data-stu-id="e61b2-120">**ErrorVariable** (ev)</span></span>
- <span data-ttu-id="e61b2-121">**Informationaction** (infa)</span><span class="sxs-lookup"><span data-stu-id="e61b2-121">**InformationAction** (infa)</span></span>
- <span data-ttu-id="e61b2-122">**InformationVariable** (IV)</span><span class="sxs-lookup"><span data-stu-id="e61b2-122">**InformationVariable** (iv)</span></span>
- <span data-ttu-id="e61b2-123">**Outvariance** (OV)</span><span class="sxs-lookup"><span data-stu-id="e61b2-123">**OutVariable** (ov)</span></span>
- <span data-ttu-id="e61b2-124">**OutBuffer** (OB)</span><span class="sxs-lookup"><span data-stu-id="e61b2-124">**OutBuffer** (ob)</span></span>
- <span data-ttu-id="e61b2-125">**PipelineVariable** (PV)</span><span class="sxs-lookup"><span data-stu-id="e61b2-125">**PipelineVariable** (pv)</span></span>
- <span data-ttu-id="e61b2-126">**Detalhado** (VB)</span><span class="sxs-lookup"><span data-stu-id="e61b2-126">**Verbose** (vb)</span></span>
- <span data-ttu-id="e61b2-127">**Avisoaction** (WA)</span><span class="sxs-lookup"><span data-stu-id="e61b2-127">**WarningAction** (wa)</span></span>
- <span data-ttu-id="e61b2-128">**WarningVariable** (WV)</span><span class="sxs-lookup"><span data-stu-id="e61b2-128">**WarningVariable** (wv)</span></span>

<span data-ttu-id="e61b2-129">Os parâmetros de **ação** são valores de tipo **preferência** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-129">The **Action** parameters are **ActionPreference** type values.</span></span>
<span data-ttu-id="e61b2-130">**Preferência** é uma enumeração com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e61b2-130">**ActionPreference** is an enumeration with the following values:</span></span>

| <span data-ttu-id="e61b2-131">Nome</span><span class="sxs-lookup"><span data-stu-id="e61b2-131">Name</span></span>             | <span data-ttu-id="e61b2-132">Valor</span><span class="sxs-lookup"><span data-stu-id="e61b2-132">Value</span></span> |
|------------------|-------|
| <span data-ttu-id="e61b2-133">Suspend</span><span class="sxs-lookup"><span data-stu-id="e61b2-133">Suspend</span></span>          | <span data-ttu-id="e61b2-134">5</span><span class="sxs-lookup"><span data-stu-id="e61b2-134">5</span></span>     |
| <span data-ttu-id="e61b2-135">Ignorar</span><span class="sxs-lookup"><span data-stu-id="e61b2-135">Ignore</span></span>           | <span data-ttu-id="e61b2-136">4</span><span class="sxs-lookup"><span data-stu-id="e61b2-136">4</span></span>     |
| <span data-ttu-id="e61b2-137">Consultar</span><span class="sxs-lookup"><span data-stu-id="e61b2-137">Inquire</span></span>          | <span data-ttu-id="e61b2-138">3</span><span class="sxs-lookup"><span data-stu-id="e61b2-138">3</span></span>     |
| <span data-ttu-id="e61b2-139">Continuar</span><span class="sxs-lookup"><span data-stu-id="e61b2-139">Continue</span></span>         | <span data-ttu-id="e61b2-140">2</span><span class="sxs-lookup"><span data-stu-id="e61b2-140">2</span></span>     |
| <span data-ttu-id="e61b2-141">Parar</span><span class="sxs-lookup"><span data-stu-id="e61b2-141">Stop</span></span>             | <span data-ttu-id="e61b2-142">1</span><span class="sxs-lookup"><span data-stu-id="e61b2-142">1</span></span>     |
| <span data-ttu-id="e61b2-143">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="e61b2-143">SilentlyContinue</span></span> | <span data-ttu-id="e61b2-144">0</span><span class="sxs-lookup"><span data-stu-id="e61b2-144">0</span></span>     |

<span data-ttu-id="e61b2-145">Você pode usar o nome ou o valor com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e61b2-145">You may use the name or the value with the parameter.</span></span>

<span data-ttu-id="e61b2-146">Além dos parâmetros comuns, muitos cmdlets oferecem parâmetros de mitigação de risco.</span><span class="sxs-lookup"><span data-stu-id="e61b2-146">In addition to the common parameters, many cmdlets offer risk mitigation parameters.</span></span> <span data-ttu-id="e61b2-147">Os cmdlets que envolvem o risco para o sistema ou para os dados do usuário geralmente oferecem esses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e61b2-147">Cmdlets that involve risk to the system or to user data usually offer these parameters.</span></span>

<span data-ttu-id="e61b2-148">Os parâmetros de mitigação de risco são:</span><span class="sxs-lookup"><span data-stu-id="e61b2-148">The risk mitigation parameters are:</span></span>

- <span data-ttu-id="e61b2-149">**WhatIf** (Wi)</span><span class="sxs-lookup"><span data-stu-id="e61b2-149">**WhatIf** (wi)</span></span>
- <span data-ttu-id="e61b2-150">**Confirmar** (CF)</span><span class="sxs-lookup"><span data-stu-id="e61b2-150">**Confirm** (cf)</span></span>

### <a name="common-parameter-descriptions"></a><span data-ttu-id="e61b2-151">DESCRIÇÕES DE PARÂMETROS COMUNS</span><span class="sxs-lookup"><span data-stu-id="e61b2-151">COMMON PARAMETER DESCRIPTIONS</span></span>

#### <a name="debug"></a><span data-ttu-id="e61b2-152">Depurar</span><span class="sxs-lookup"><span data-stu-id="e61b2-152">Debug</span></span>

<span data-ttu-id="e61b2-153">Exibe detalhes no nível do programador sobre a operação feita pelo comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-153">Displays programmer-level detail about the operation done by the command.</span></span> <span data-ttu-id="e61b2-154">Esse parâmetro funciona somente quando o comando gera uma mensagem de depuração.</span><span class="sxs-lookup"><span data-stu-id="e61b2-154">This parameter works only when the command generates a debugging message.</span></span> <span data-ttu-id="e61b2-155">Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Debug` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-155">For example, this parameter works when a command contains the `Write-Debug` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-156">Por padrão, as mensagens de depuração não são exibidas porque o valor da `$DebugPreference` variável é **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-156">By default, debugging messages aren't displayed because the value of the `$DebugPreference` variable is **SilentlyContinue**.</span></span>

<span data-ttu-id="e61b2-157">No modo interativo, o parâmetro **debug** substitui o valor da `$DebugPreference` variável para o comando atual, definindo o valor de `$DebugPreference` para **inquire**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-157">In interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Inquire**.</span></span>

<span data-ttu-id="e61b2-158">No modo não interativo, o parâmetro de **depuração** substitui o valor da `$DebugPreference` variável para o comando atual, definindo o valor de `$DebugPreference` para **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-158">In non-interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Continue**.</span></span>

<span data-ttu-id="e61b2-159">`-Debug:$true` tem o mesmo efeito que `-Debug` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-159">`-Debug:$true` has the same effect as `-Debug`.</span></span> <span data-ttu-id="e61b2-160">Use `-Debug:$false` para suprimir a exibição de mensagens de depuração quando `$DebugPreference` não for **SilentlyContinue**, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-160">Use `-Debug:$false` to suppress the display of debugging messages when `$DebugPreference` isn't **SilentlyContinue**, which is the default.</span></span>

#### <a name="erroraction"></a><span data-ttu-id="e61b2-161">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="e61b2-161">ErrorAction</span></span>

<span data-ttu-id="e61b2-162">Determina como o cmdlet responde a um erro de não finalização do comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-162">Determines how the cmdlet responds to a non-terminating error from the command.</span></span>
<span data-ttu-id="e61b2-163">Esse parâmetro funciona somente quando o comando gera um erro de não finalização, como os do `Write-Error` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-163">This parameter works only when the command generates a non-terminating error, such as those from the `Write-Error` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-164">O parâmetro **ErrorAction** substitui o valor da `$ErrorActionPreference` variável para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="e61b2-164">The **ErrorAction** parameter overrides the value of the `$ErrorActionPreference` variable for the current command.</span></span> <span data-ttu-id="e61b2-165">Como o valor padrão da `$ErrorActionPreference` variável é **continue**, as mensagens de erro são exibidas e a execução continua, a menos que você use o parâmetro **ErrorAction** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-165">Because the default value of the `$ErrorActionPreference` variable is **Continue**, error messages are displayed and execution continues unless you use the **ErrorAction** parameter.</span></span>

<span data-ttu-id="e61b2-166">O parâmetro **ErrorAction** não tem nenhum efeito sobre erros de encerramento (como dados ausentes, parâmetros que não são válidos ou permissões insuficientes) que impedem que um comando seja concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="e61b2-166">The **ErrorAction** parameter has no effect on terminating errors (such as missing data, parameters that aren't valid, or insufficient permissions) that prevent a command from completing successfully.</span></span>

<span data-ttu-id="e61b2-167">`-ErrorAction:Continue` Exiba a mensagem de erro e continue executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-167">`-ErrorAction:Continue` display the error message and continues executing the command.</span></span> <span data-ttu-id="e61b2-168">`Continue` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-168">`Continue` is the default.</span></span>

<span data-ttu-id="e61b2-169">`-ErrorAction:Ignore` suprime a mensagem de erro e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-169">`-ErrorAction:Ignore` suppresses the error message and continues executing the command.</span></span> <span data-ttu-id="e61b2-170">Ao contrário de **SilentlyContinue**, **ignorar** não adiciona a mensagem de erro à `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="e61b2-170">Unlike **SilentlyContinue**, **Ignore** doesn't add the error message to the `$Error` automatic variable.</span></span> <span data-ttu-id="e61b2-171">O valor de **ignorar** é introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e61b2-171">The **Ignore** value is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="e61b2-172">`-ErrorAction:Inquire` exibe a mensagem de erro e solicita a confirmação antes de continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="e61b2-172">`-ErrorAction:Inquire` displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="e61b2-173">Esse valor raramente é usado.</span><span class="sxs-lookup"><span data-stu-id="e61b2-173">This value is rarely used.</span></span>

<span data-ttu-id="e61b2-174">`-ErrorAction:SilentlyContinue` suprime a mensagem de erro e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-174">`-ErrorAction:SilentlyContinue` suppresses the error message and continues executing the command.</span></span>

<span data-ttu-id="e61b2-175">`-ErrorAction:Stop` exibe a mensagem de erro e para a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-175">`-ErrorAction:Stop` displays the error message and stops executing the command.</span></span>

<span data-ttu-id="e61b2-176">`-ErrorAction:Suspend` Só está disponível para fluxos de trabalho que não têm suporte no PowerShell 6 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="e61b2-176">`-ErrorAction:Suspend` is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-177">O parâmetro **ErrorAction** substitui, mas não substitui o valor da variável de `$ErrorAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="e61b2-177">The **ErrorAction** parameter overrides, but does not replace the value of the `$ErrorAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="errorvariable"></a><span data-ttu-id="e61b2-178">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="e61b2-178">ErrorVariable</span></span>

<span data-ttu-id="e61b2-179">O **ErrorVariable** armazena mensagens de erro sobre o comando na variável especificada e na `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="e61b2-179">**ErrorVariable** stores error messages about the command in the specified variable and in the `$Error` automatic variable.</span></span> <span data-ttu-id="e61b2-180">Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="e61b2-180">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md)</span></span>

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-181">Por padrão, novas mensagens de erro substituem mensagens de erro que já estão armazenadas na variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-181">By default, new error messages overwrite error messages that are already stored in the variable.</span></span> <span data-ttu-id="e61b2-182">Para acrescentar a mensagem de erro ao conteúdo da variável, digite um sinal de adição ( `+` ) antes do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-182">To append the error message to the variable content, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="e61b2-183">Por exemplo, o comando a seguir cria a `$a` variável e, em seguida, armazena todos os erros nela:</span><span class="sxs-lookup"><span data-stu-id="e61b2-183">For example, the following command creates the `$a` variable and then stores any errors in it:</span></span>

```powershell
Get-Process -Id 6 -ErrorVariable a
```

<span data-ttu-id="e61b2-184">O comando a seguir adiciona todas as mensagens de erro à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="e61b2-184">The following command adds any error messages to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

<span data-ttu-id="e61b2-185">O comando a seguir exibe o conteúdo de `$a` :</span><span class="sxs-lookup"><span data-stu-id="e61b2-185">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="e61b2-186">Você pode usar esse parâmetro para criar uma variável que contém apenas mensagens de erro de comandos específicos e não afeta o comportamento da `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="e61b2-186">You can use this parameter to create a variable that contains only error messages from specific commands and does not affect the behavior of the `$Error` automatic variable.</span></span> <span data-ttu-id="e61b2-187">A `$Error` variável automática contém mensagens de erro de todos os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-187">The `$Error` automatic variable contains error messages from all the commands in the session.</span></span> <span data-ttu-id="e61b2-188">Você pode usar a notação de matriz, como `$a[0]` ou `$error[1,2]` para se referir a erros específicos armazenados nas variáveis.</span><span class="sxs-lookup"><span data-stu-id="e61b2-188">You can use array notation, such as `$a[0]` or `$error[1,2]` to refer to specific errors stored in the variables.</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-189">A variável de erro personalizada contém todos os erros gerados pelo comando, incluindo erros de chamadas para funções aninhadas ou scripts.</span><span class="sxs-lookup"><span data-stu-id="e61b2-189">The custom error variable contains all errors generated by the command, including errors from calls to nested functions or scripts.</span></span>

#### <a name="informationaction"></a><span data-ttu-id="e61b2-190">InformationAction</span><span class="sxs-lookup"><span data-stu-id="e61b2-190">InformationAction</span></span>

<span data-ttu-id="e61b2-191">Introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="e61b2-191">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="e61b2-192">No comando ou script em que é usado, o parâmetro Common **informationaction** substitui o valor da `$InformationPreference` variável de preferência, que por padrão é definido como **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-192">Within the command or script in which it's used, the **InformationAction** common parameter overrides the value of the `$InformationPreference` preference variable, which by default is set to **SilentlyContinue**.</span></span> <span data-ttu-id="e61b2-193">Quando você usa o `Write-Information` em um script com **informationaction**, `Write-Information` os valores são mostrados dependendo do valor do parâmetro **informationaction** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-193">When you use `Write-Information` in a script with **InformationAction**, `Write-Information` values are shown depending on the value of the **InformationAction** parameter.</span></span> <span data-ttu-id="e61b2-194">Para obter mais informações sobre o `$InformationPreference` , consulte [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e61b2-194">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-195">`-InformationAction:Stop` interrompe um comando ou script em uma ocorrência do `Write-Information` comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-195">`-InformationAction:Stop` stops a command or script at an occurrence of the `Write-Information` command.</span></span>

<span data-ttu-id="e61b2-196">`-InformationAction:Ignore` suprime a mensagem informativa e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-196">`-InformationAction:Ignore` suppresses the informational message and continues running the command.</span></span> <span data-ttu-id="e61b2-197">Ao contrário de **SilentlyContinue**, **ignorar** se esquece completamente da mensagem informativa; Ele não adiciona a mensagem informativa ao fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="e61b2-197">Unlike **SilentlyContinue**, **Ignore** completely forgets the informational message; it doesn't add the informational message to the information stream.</span></span>

<span data-ttu-id="e61b2-198">`-InformationAction:Inquire` exibe a mensagem informativa que você especifica em um `Write-Information` comando e pergunta se deseja continuar.</span><span class="sxs-lookup"><span data-stu-id="e61b2-198">`-InformationAction:Inquire` displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>

<span data-ttu-id="e61b2-199">`-InformationAction:Continue` exibe a mensagem informativa e continua em execução.</span><span class="sxs-lookup"><span data-stu-id="e61b2-199">`-InformationAction:Continue` displays the informational message, and continues running.</span></span>

<span data-ttu-id="e61b2-200">`-InformationAction:Suspend` Não tem suporte no PowerShell Core porque ele só está disponível para fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e61b2-200">`-InformationAction:Suspend` isn't supported on PowerShell Core as it is only available for workflows.</span></span>

<span data-ttu-id="e61b2-201">`-InformationAction:SilentlyContinue` nenhum efeito, pois a mensagem informativa não é exibida (padrão) e o script continua sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="e61b2-201">`-InformationAction:SilentlyContinue` no effect as the informational message aren't (Default) displayed, and the script continues without interruption.</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-202">O parâmetro **informationaction** substitui, mas não substitui o valor da variável de `$InformationAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="e61b2-202">The **InformationAction** parameter overrides, but does not replace the value of the `$InformationAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="informationvariable"></a><span data-ttu-id="e61b2-203">InformationVariable</span><span class="sxs-lookup"><span data-stu-id="e61b2-203">InformationVariable</span></span>

<span data-ttu-id="e61b2-204">Introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="e61b2-204">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="e61b2-205">No comando ou script em que é usado, o parâmetro comum **InformationVariable** armazena em uma variável uma cadeia de caracteres que você especifica adicionando o `Write-Information` comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-205">Within the command or script in which it's used, the **InformationVariable** common parameter stores in a variable a string that you specify by adding the `Write-Information` command.</span></span> <span data-ttu-id="e61b2-206">`Write-Information` os valores são mostrados dependendo do valor do parâmetro de **informationaction** comum; Se você não adicionar o parâmetro Common **Reinformationaction** , as `Write-Information` cadeias de caracteres serão mostradas dependendo do valor da `$InformationPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="e61b2-206">`Write-Information` values are shown depending on the value of the **InformationAction** common parameter; if you don't add the **InformationAction** common parameter, `Write-Information` strings are shown depending on the value of the `$InformationPreference` preference variable.</span></span> <span data-ttu-id="e61b2-207">Para obter mais informações sobre o `$InformationPreference` , consulte [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e61b2-207">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-208">A variável Information contém todas as mensagens de informações geradas pelo comando, incluindo mensagens de informações de chamadas para funções aninhadas ou scripts.</span><span class="sxs-lookup"><span data-stu-id="e61b2-208">The information variable contains all information messages generated by the command, including information messages from calls to nested functions or scripts.</span></span>

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a><span data-ttu-id="e61b2-209">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="e61b2-209">OutBuffer</span></span>

<span data-ttu-id="e61b2-210">Determina o número de objetos a serem acumulados em um buffer antes que qualquer objeto seja enviado por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="e61b2-210">Determines the number of objects to accumulate in a buffer before any objects are sent through the pipeline.</span></span> <span data-ttu-id="e61b2-211">Se você omitir esse parâmetro, os objetos serão enviados conforme eles forem gerados.</span><span class="sxs-lookup"><span data-stu-id="e61b2-211">If you omit this parameter, objects are sent as they're generated.</span></span>

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-212">Esse parâmetro de gerenciamento de recursos foi projetado para usuários avançados.</span><span class="sxs-lookup"><span data-stu-id="e61b2-212">This resource management parameter is designed for advanced users.</span></span> <span data-ttu-id="e61b2-213">Quando você usa esse parâmetro, o PowerShell envia dados para o próximo cmdlet em lotes de `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-213">When you use this parameter, PowerShell sends data to the next cmdlet in batches of `OutBuffer + 1`.</span></span>

<span data-ttu-id="e61b2-214">As alternativas de exemplo a seguir são exibidas entre `ForEach-Object` os blocos de processo que usam o `Write-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-214">The following example alternates displays between to `ForEach-Object` process blocks that use the `Write-Host` cmdlet.</span></span> <span data-ttu-id="e61b2-215">As alternativas de exibição em lotes de 2 ou `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-215">The display alternates in batches of 2 or `OutBuffer + 1`.</span></span>

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a><span data-ttu-id="e61b2-216">OutVariable</span><span class="sxs-lookup"><span data-stu-id="e61b2-216">OutVariable</span></span>

<span data-ttu-id="e61b2-217">Armazena objetos de saída do comando na variável especificada, além de enviar a saída ao longo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="e61b2-217">Stores output objects from the command in the specified variable in addition to sending the output along the pipeline.</span></span>

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-218">Para adicionar a saída à variável, em vez de substituir qualquer saída que já possa estar armazenada lá, digite um sinal de adição ( `+` ) antes do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-218">To add the output to the variable, instead of replacing any output that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="e61b2-219">Por exemplo, o comando a seguir cria a `$out` variável e armazena o objeto de processo nele:</span><span class="sxs-lookup"><span data-stu-id="e61b2-219">For example, the following command creates the `$out` variable and stores the process object in it:</span></span>

```powershell
Get-Process PowerShell -OutVariable out
```

<span data-ttu-id="e61b2-220">O comando a seguir adiciona o objeto de processo à `$out` variável:</span><span class="sxs-lookup"><span data-stu-id="e61b2-220">The following command adds the process object to the `$out` variable:</span></span>

```powershell
Get-Process iexplore -OutVariable +out
```

<span data-ttu-id="e61b2-221">O comando a seguir exibe o conteúdo da `$out` variável:</span><span class="sxs-lookup"><span data-stu-id="e61b2-221">The following command displays the contents of the `$out` variable:</span></span>

```powershell
$out
```

> [!NOTE]
> <span data-ttu-id="e61b2-222">A variável criada pelo parâmetro **Outvariance** é um `[System.Collections.ArrayList]` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-222">The variable created by the **OutVariable** parameter is a `[System.Collections.ArrayList]`.</span></span>

#### <a name="pipelinevariable"></a><span data-ttu-id="e61b2-223">PipelineVariable</span><span class="sxs-lookup"><span data-stu-id="e61b2-223">PipelineVariable</span></span>

<span data-ttu-id="e61b2-224">**PipelineVariable** armazena o valor do elemento de pipeline atual como uma variável, para qualquer comando nomeado conforme ele flui pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="e61b2-224">**PipelineVariable** stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.</span></span>

>[!NOTE]
> <span data-ttu-id="e61b2-225">As funções avançadas podem ter até três blocos de script: `begin` , `process` e `end` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-225">Advanced functions can have up to three script blocks: `begin`, `process`, and `end`.</span></span> <span data-ttu-id="e61b2-226">Ao usar o parâmetro **PipelineVariable** com funções avançadas, somente os valores do primeiro bloco de script definido são atribuídos à variável à medida que a função é executada.</span><span class="sxs-lookup"><span data-stu-id="e61b2-226">When using the **PipelineVariable** parameter with advanced functions, only values from the first defined script block are assigned to the variable as the function runs.</span></span> <span data-ttu-id="e61b2-227">Para obter mais informações, consulte [Advanced Functions](./about_functions_advanced.md).</span><span class="sxs-lookup"><span data-stu-id="e61b2-227">For more information, see [Advanced functions](./about_functions_advanced.md).</span></span>
> <span data-ttu-id="e61b2-228">O PowerShell 7,2 corrige esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="e61b2-228">PowerShell 7.2 corrects this behavior.</span></span>

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-229">Os valores válidos são cadeias de caracteres, o mesmo que para qualquer nome de variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-229">Valid values are strings, the same as for any variable names.</span></span>

<span data-ttu-id="e61b2-230">Veja a seguir um exemplo de como o **PipelineVariable** funciona.</span><span class="sxs-lookup"><span data-stu-id="e61b2-230">The following is an example of how **PipelineVariable** works.</span></span> <span data-ttu-id="e61b2-231">Neste exemplo, o parâmetro **PipelineVariable** é adicionado a um `Foreach-Object` comando para armazenar os resultados do comando em variáveis.</span><span class="sxs-lookup"><span data-stu-id="e61b2-231">In this example, the **PipelineVariable** parameter is added to a `Foreach-Object` command to store the results of the command in variables.</span></span> <span data-ttu-id="e61b2-232">Um intervalo de números, de 1 a 10, são canalizados para o primeiro `Foreach-Object` comando, os resultados dos quais são armazenados em uma variável chamada **Left**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-232">A range of numbers, 1 to 10, are piped into the first `Foreach-Object` command, the results of which are stored in a variable named **Left**.</span></span>

<span data-ttu-id="e61b2-233">Os resultados do primeiro `Foreach-Object` comando são canalizados para um segundo `Foreach-Object` comando, que filtra os objetos retornados pelo primeiro `Foreach-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-233">The results of the first `Foreach-Object` command are piped into a second `Foreach-Object` command, which filters the objects returned by the first `Foreach-Object` command.</span></span> <span data-ttu-id="e61b2-234">Os resultados do segundo comando são armazenados em uma variável chamada **Right**.</span><span class="sxs-lookup"><span data-stu-id="e61b2-234">The results of the second command are stored in a variable named **Right**.</span></span>

<span data-ttu-id="e61b2-235">No terceiro `Foreach-Object` comando, os resultados dos dois primeiros `Foreach-Object` comandos canalizados, representados pelas variáveis **Left** e **Right**, são processados usando um operador de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="e61b2-235">In the third `Foreach-Object` command, the results of the first two `Foreach-Object` piped commands, represented by the variables **Left** and **Right**, are processed by using a multiplication operator.</span></span> <span data-ttu-id="e61b2-236">O comando instrui os objetos armazenados nas variáveis **esquerda** e **direita** a serem multiplicados e especifica que os resultados devem ser exibidos como "membro do intervalo esquerdo \* membro do intervalo direito = produto".</span><span class="sxs-lookup"><span data-stu-id="e61b2-236">The command instructs objects stored in the **Left** and **Right** variables to be multiplied, and specifies that the results should be displayed as "Left range member \* Right range member = product".</span></span>

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a><span data-ttu-id="e61b2-237">Detalhado</span><span class="sxs-lookup"><span data-stu-id="e61b2-237">Verbose</span></span>

<span data-ttu-id="e61b2-238">Exibe informações detalhadas sobre a operação feita pelo comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-238">Displays detailed information about the operation done by the command.</span></span> <span data-ttu-id="e61b2-239">Essas informações se assemelham às informações em um rastreamento ou em um log de transações.</span><span class="sxs-lookup"><span data-stu-id="e61b2-239">This information resembles the information in a trace or in a transaction log.</span></span> <span data-ttu-id="e61b2-240">Esse parâmetro funciona somente quando o comando gera uma mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="e61b2-240">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="e61b2-241">Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-241">For example, this parameter works when a command contains the `Write-Verbose` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-242">O parâmetro **Verbose** substitui o valor da `$VerbosePreference` variável para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="e61b2-242">The **Verbose** parameter overrides the value of the `$VerbosePreference` variable for the current command.</span></span> <span data-ttu-id="e61b2-243">Como o valor padrão da `$VerbosePreference` variável é **SilentlyContinue**, as mensagens detalhadas não são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-243">Because the default value of the `$VerbosePreference` variable is **SilentlyContinue**, verbose messages aren't displayed by default.</span></span>

<span data-ttu-id="e61b2-244">`-Verbose:$true` tem o mesmo efeito que `-Verbose`</span><span class="sxs-lookup"><span data-stu-id="e61b2-244">`-Verbose:$true` has the same effect as `-Verbose`</span></span>

<span data-ttu-id="e61b2-245">`-Verbose:$false` suprime a exibição de mensagens detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e61b2-245">`-Verbose:$false` suppresses the display of verbose messages.</span></span> <span data-ttu-id="e61b2-246">Use esse parâmetro quando o valor de `$VerbosePreference` não for **SilentlyContinue** (o padrão).</span><span class="sxs-lookup"><span data-stu-id="e61b2-246">Use this parameter when the value of `$VerbosePreference` isn't **SilentlyContinue** (the default).</span></span>

#### <a name="warningaction"></a><span data-ttu-id="e61b2-247">WarningAction</span><span class="sxs-lookup"><span data-stu-id="e61b2-247">WarningAction</span></span>

<span data-ttu-id="e61b2-248">Determina como o cmdlet responde a um aviso do comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-248">Determines how the cmdlet responds to a warning from the command.</span></span> <span data-ttu-id="e61b2-249">**Continue** é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-249">**Continue** is the default value.</span></span> <span data-ttu-id="e61b2-250">Esse parâmetro funciona somente quando o comando gera uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="e61b2-250">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="e61b2-251">Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Warning` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-251">For example, this parameter works when a command contains the `Write-Warning` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-252">O parâmetro **WarningAction** substitui o valor da `$WarningPreference` variável para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="e61b2-252">The **WarningAction** parameter overrides the value of the `$WarningPreference` variable for the current command.</span></span> <span data-ttu-id="e61b2-253">Como o valor padrão da `$WarningPreference` variável é **continue**, os avisos são exibidos e a execução continua, a menos que você use o parâmetro **WarningAction** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-253">Because the default value of the `$WarningPreference` variable is **Continue**, warnings are displayed and execution continues unless you use the **WarningAction** parameter.</span></span>

<span data-ttu-id="e61b2-254">`-WarningAction:Continue` exibe as mensagens de aviso e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-254">`-WarningAction:Continue` displays the warning messages and continues executing the command.</span></span> <span data-ttu-id="e61b2-255">`Continue` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e61b2-255">`Continue` is the default.</span></span>

<span data-ttu-id="e61b2-256">`-WarningAction:Inquire` exibe a mensagem de aviso e solicita sua confirmação antes de continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="e61b2-256">`-WarningAction:Inquire` displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="e61b2-257">Esse valor raramente é usado.</span><span class="sxs-lookup"><span data-stu-id="e61b2-257">This value is rarely used.</span></span>

<span data-ttu-id="e61b2-258">`-WarningAction:SilentlyContinue` suprime a mensagem de aviso e continua executando o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-258">`-WarningAction:SilentlyContinue` suppresses the warning message and continues executing the command.</span></span>

<span data-ttu-id="e61b2-259">`-WarningAction:Stop` exibe a mensagem de aviso e para a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-259">`-WarningAction:Stop` displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-260">O parâmetro **WarningAction** substitui, mas não substitui o valor da variável de `$WarningAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="e61b2-260">The **WarningAction** parameter overrides, but does not replace the value of the `$WarningAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="warningvariable"></a><span data-ttu-id="e61b2-261">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="e61b2-261">WarningVariable</span></span>

<span data-ttu-id="e61b2-262">Armazena avisos sobre o comando na variável especificada.</span><span class="sxs-lookup"><span data-stu-id="e61b2-262">Stores warnings about the command in the specified variable.</span></span>

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-263">Todos os avisos gerados são salvos na variável, mesmo se os avisos não forem exibidos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e61b2-263">All generated warnings are saved in the variable even if the warnings aren't displayed to the user.</span></span>

<span data-ttu-id="e61b2-264">Para acrescentar os avisos ao conteúdo da variável, em vez de substituir os avisos que já podem estar armazenados lá, digite um sinal de adição ( `+` ) antes do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-264">To append the warnings to the variable content, instead of replacing any warnings that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="e61b2-265">Por exemplo, o comando a seguir cria a `$a` variável e, em seguida, armazena todos os avisos nela:</span><span class="sxs-lookup"><span data-stu-id="e61b2-265">For example, the following command creates the `$a` variable and then stores any warnings in it:</span></span>

```powershell
Get-Process -Id 6 -WarningVariable a
```

<span data-ttu-id="e61b2-266">O comando a seguir adiciona quaisquer avisos à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="e61b2-266">The following command adds any warnings to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -WarningVariable +a
```

<span data-ttu-id="e61b2-267">O comando a seguir exibe o conteúdo de `$a` :</span><span class="sxs-lookup"><span data-stu-id="e61b2-267">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="e61b2-268">Você pode usar esse parâmetro para criar uma variável que contém apenas avisos de comandos específicos.</span><span class="sxs-lookup"><span data-stu-id="e61b2-268">You can use this parameter to create a variable that contains only warnings from specific commands.</span></span> <span data-ttu-id="e61b2-269">Você pode usar a notação de matriz, como `$a[0]` ou `$warning[1,2]` para se referir a avisos específicos armazenados na variável.</span><span class="sxs-lookup"><span data-stu-id="e61b2-269">You can use array notation, such as `$a[0]` or `$warning[1,2]` to refer to specific warnings stored in the variable.</span></span>

> [!NOTE]
> <span data-ttu-id="e61b2-270">A variável de aviso contém todos os avisos gerados pelo comando, incluindo avisos de chamadas para funções aninhadas ou scripts.</span><span class="sxs-lookup"><span data-stu-id="e61b2-270">The warning variable contains all warnings generated by the command, including warnings from calls to nested functions or scripts.</span></span>
### <a name="risk-management-parameter-descriptions"></a><span data-ttu-id="e61b2-271">Descrições de parâmetros de gerenciamento de riscos</span><span class="sxs-lookup"><span data-stu-id="e61b2-271">Risk Management Parameter Descriptions</span></span>

#### <a name="whatif"></a><span data-ttu-id="e61b2-272">WhatIf</span><span class="sxs-lookup"><span data-stu-id="e61b2-272">WhatIf</span></span>

<span data-ttu-id="e61b2-273">Exibe uma mensagem que descreve o efeito do comando, em vez de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-273">Displays a message that describes the effect of the command, instead of executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-274">O parâmetro **WhatIf** substitui o valor da `$WhatIfPreference` variável para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="e61b2-274">The **WhatIf** parameter overrides the value of the `$WhatIfPreference` variable for the current command.</span></span> <span data-ttu-id="e61b2-275">Como o valor padrão da `$WhatIfPreference` variável é 0 (desabilitado), o comportamento de **WhatIf** não é feito sem o parâmetro **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-275">Because the default value of the `$WhatIfPreference` variable is 0 (disabled), **WhatIf** behavior isn't done without the **WhatIf** parameter.</span></span> <span data-ttu-id="e61b2-276">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="e61b2-276">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="e61b2-277">`-WhatIf:$true` tem o mesmo efeito que `-WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-277">`-WhatIf:$true` has the same effect as `-WhatIf`.</span></span>

<span data-ttu-id="e61b2-278">`-WhatIf:$false` suprime o comportamento de WhatIf automático que resulta quando o valor da `$WhatIfPreference` variável é 1.</span><span class="sxs-lookup"><span data-stu-id="e61b2-278">`-WhatIf:$false` suppresses the automatic WhatIf behavior that results when the value of the `$WhatIfPreference` variable is 1.</span></span>

<span data-ttu-id="e61b2-279">Por exemplo, o comando a seguir usa o `-WhatIf` parâmetro em um `Remove-Item` comando:</span><span class="sxs-lookup"><span data-stu-id="e61b2-279">For example, the following command uses the `-WhatIf` parameter in a `Remove-Item` command:</span></span>

```powershell
Remove-Item Date.csv -WhatIf
```

<span data-ttu-id="e61b2-280">Em vez de remover o item, o PowerShell lista as operações que ele faria e os itens que seriam afetados.</span><span class="sxs-lookup"><span data-stu-id="e61b2-280">Instead of removing the item, PowerShell lists the operations it would do and the items that would be affected.</span></span> <span data-ttu-id="e61b2-281">Esse comando gera a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="e61b2-281">This command produces the following output:</span></span>

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a><span data-ttu-id="e61b2-282">Confirmar</span><span class="sxs-lookup"><span data-stu-id="e61b2-282">Confirm</span></span>

<span data-ttu-id="e61b2-283">Solicita sua confirmação antes de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-283">Prompts you for confirmation before executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="e61b2-284">O parâmetro **Confirm** substitui o valor da `$ConfirmPreference` variável para o comando atual.</span><span class="sxs-lookup"><span data-stu-id="e61b2-284">The **Confirm** parameter overrides the value of the `$ConfirmPreference` variable for the current command.</span></span> <span data-ttu-id="e61b2-285">O valor padrão é true.</span><span class="sxs-lookup"><span data-stu-id="e61b2-285">The default value is true.</span></span> <span data-ttu-id="e61b2-286">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="e61b2-286">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="e61b2-287">`-Confirm:$true` tem o mesmo efeito que `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="e61b2-287">`-Confirm:$true` has the same effect as `-Confirm`.</span></span>

<span data-ttu-id="e61b2-288">`-Confirm:$false` suprime a confirmação automática, que ocorre quando o valor de `$ConfirmPreference` é menor ou igual ao risco estimado do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e61b2-288">`-Confirm:$false` suppresses automatic confirmation, which occurs when the value of `$ConfirmPreference` is less than or equal to the estimated risk of the cmdlet.</span></span>

<span data-ttu-id="e61b2-289">Por exemplo, o comando a seguir usa o parâmetro **Confirm** com um `Remove-Item` comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-289">For example, the following command uses the **Confirm** parameter with a `Remove-Item` command.</span></span> <span data-ttu-id="e61b2-290">Antes de remover o item, o PowerShell lista as operações que ele faria e os itens que seriam afetados e solicita aprovação.</span><span class="sxs-lookup"><span data-stu-id="e61b2-290">Before removing the item, PowerShell lists the operations it would do and the items that would be affected, and asks for approval.</span></span>

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="e61b2-291">As opções de confirmação de resposta são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e61b2-291">The Confirm response options are as follows:</span></span>

|<span data-ttu-id="e61b2-292">Resposta</span><span class="sxs-lookup"><span data-stu-id="e61b2-292">Response</span></span>       |<span data-ttu-id="e61b2-293">Result</span><span class="sxs-lookup"><span data-stu-id="e61b2-293">Result</span></span>                                                     |
|---------------|-----------------------------------------------------------|
|<span data-ttu-id="e61b2-294">Sim (Y)</span><span class="sxs-lookup"><span data-stu-id="e61b2-294">Yes (Y)</span></span>        |<span data-ttu-id="e61b2-295">Execute a ação.</span><span class="sxs-lookup"><span data-stu-id="e61b2-295">Perform the action.</span></span>                                        |
|<span data-ttu-id="e61b2-296">Sim para todos (A)</span><span class="sxs-lookup"><span data-stu-id="e61b2-296">Yes to All (A)</span></span> |<span data-ttu-id="e61b2-297">Executar todas as ações e suprimir consultas de confirmação subsequentes</span><span class="sxs-lookup"><span data-stu-id="e61b2-297">Perform all actions and suppress subsequent Confirm queries</span></span>|
|               |<span data-ttu-id="e61b2-298">para este comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-298">for this command.</span></span>                                          |
|<span data-ttu-id="e61b2-299">Não (N):</span><span class="sxs-lookup"><span data-stu-id="e61b2-299">No (N):</span></span>        |<span data-ttu-id="e61b2-300">Não execute a ação.</span><span class="sxs-lookup"><span data-stu-id="e61b2-300">Do not perform the action.</span></span>                                 |
|<span data-ttu-id="e61b2-301">Não para todos (L):</span><span class="sxs-lookup"><span data-stu-id="e61b2-301">No to All (L):</span></span> |<span data-ttu-id="e61b2-302">Não executar nenhuma ação e suprimir a confirmação subsequente</span><span class="sxs-lookup"><span data-stu-id="e61b2-302">Do not perform any actions and suppress subsequent Confirm</span></span> |
|               |<span data-ttu-id="e61b2-303">consultas para este comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-303">queries for this command.</span></span>                                  |
|<span data-ttu-id="e61b2-304">Suspender (S):</span><span class="sxs-lookup"><span data-stu-id="e61b2-304">Suspend (S):</span></span>   |<span data-ttu-id="e61b2-305">Pause o comando e crie uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="e61b2-305">Pause the command and create a temporary session.</span></span>          |
|<span data-ttu-id="e61b2-306">Ajuda (?)</span><span class="sxs-lookup"><span data-stu-id="e61b2-306">Help (?)</span></span>       |<span data-ttu-id="e61b2-307">Exibir a ajuda para essas opções.</span><span class="sxs-lookup"><span data-stu-id="e61b2-307">Display help for these options.</span></span>                            |

<span data-ttu-id="e61b2-308">A opção **suspender** coloca o comando em espera e cria uma sessão aninhada temporária na qual você pode trabalhar até que você esteja pronto para escolher uma opção de **confirmação** .</span><span class="sxs-lookup"><span data-stu-id="e61b2-308">The **Suspend** option places the command on hold and creates a temporary nested session in which you can work until you're ready to choose a **Confirm** option.</span></span> <span data-ttu-id="e61b2-309">O prompt de comando para a sessão aninhada tem dois acentos extras (>>) para indicar que é uma operação filho do comando pai original.</span><span class="sxs-lookup"><span data-stu-id="e61b2-309">The command prompt for the nested session has two extra carets (>>) to indicate that it's a child operation of the original parent command.</span></span> <span data-ttu-id="e61b2-310">Você pode executar comandos e scripts na sessão aninhada.</span><span class="sxs-lookup"><span data-stu-id="e61b2-310">You can run commands and scripts in the nested session.</span></span> <span data-ttu-id="e61b2-311">Para encerrar a sessão aninhada e retornar às opções de confirmação do comando original, digite "Exit".</span><span class="sxs-lookup"><span data-stu-id="e61b2-311">To end the nested session and return to the Confirm options for the original command, type "exit".</span></span>

<span data-ttu-id="e61b2-312">No exemplo a seguir, as opções de **suspensão** são usadas para interromper um comando temporariamente enquanto o usuário verifica a ajuda de um parâmetro de comando.</span><span class="sxs-lookup"><span data-stu-id="e61b2-312">In the following example, the **Suspend** option (S) is used to halt a command temporarily while the user checks the help for a command parameter.</span></span> <span data-ttu-id="e61b2-313">Depois de obter as informações necessárias, o usuário digita "Exit" para finalizar o prompt aninhado e, em seguida, seleciona a resposta Sim (y) à consulta confirmar.</span><span class="sxs-lookup"><span data-stu-id="e61b2-313">After obtaining the needed information, the user types "exit" to end the nested prompt and then selects the Yes (y) response to the Confirm query.</span></span>

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a><span data-ttu-id="e61b2-314">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e61b2-314">KEYWORDS</span></span>

<span data-ttu-id="e61b2-315">about_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="e61b2-315">about_Common_Parameters</span></span>

## <a name="see-also"></a><span data-ttu-id="e61b2-316">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="e61b2-316">SEE ALSO</span></span>

[<span data-ttu-id="e61b2-317">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="e61b2-317">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="e61b2-318">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="e61b2-318">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)

[<span data-ttu-id="e61b2-319">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="e61b2-319">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)

[<span data-ttu-id="e61b2-320">Write-Error</span><span class="sxs-lookup"><span data-stu-id="e61b2-320">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)

[<span data-ttu-id="e61b2-321">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="e61b2-321">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
