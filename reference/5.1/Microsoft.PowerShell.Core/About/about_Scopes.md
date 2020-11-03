---
description: Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 8517a5c077aa8c5b769bc74e13bc56ef6a6bb355
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195971"
---
# <a name="about-scopes"></a><span data-ttu-id="de72a-104">Sobre escopos</span><span class="sxs-lookup"><span data-stu-id="de72a-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="de72a-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="de72a-105">Short description</span></span>
<span data-ttu-id="de72a-106">Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.</span><span class="sxs-lookup"><span data-stu-id="de72a-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="de72a-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="de72a-107">Long description</span></span>

<span data-ttu-id="de72a-108">O PowerShell protege o acesso a variáveis, aliases, funções e unidades do PowerShell (PSDrive) limitando o local em que eles podem ser lidos e alterados.</span><span class="sxs-lookup"><span data-stu-id="de72a-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="de72a-109">O PowerShell usa regras de escopo para garantir que você não altere inadvertidamente um item que não deva ser alterado.</span><span class="sxs-lookup"><span data-stu-id="de72a-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="de72a-110">A seguir estão as regras básicas de escopo:</span><span class="sxs-lookup"><span data-stu-id="de72a-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="de72a-111">Os escopos podem ser aninhados.</span><span class="sxs-lookup"><span data-stu-id="de72a-111">Scopes may nest.</span></span> <span data-ttu-id="de72a-112">Um escopo externo é conhecido como escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="de72a-113">Todos os escopos aninhados são escopos filho desse pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="de72a-114">Um item é visível no escopo no qual ele foi criado e em qualquer escopo filho, a menos que você o torne explicitamente privado.</span><span class="sxs-lookup"><span data-stu-id="de72a-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="de72a-115">Você pode inserir variáveis, aliases, funções ou unidades do PowerShell em um ou mais escopos.</span><span class="sxs-lookup"><span data-stu-id="de72a-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="de72a-116">Um item que você criou em um escopo pode ser alterado somente no escopo no qual ele foi criado, a menos que você especifique explicitamente um escopo diferente.</span><span class="sxs-lookup"><span data-stu-id="de72a-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="de72a-117">Se você criar um item em um escopo e o item compartilhar seu nome com um item em um escopo diferente, o item original poderá estar oculto no novo item, mas ele não será substituído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="de72a-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="de72a-118">Escopos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="de72a-118">PowerShell Scopes</span></span>

<span data-ttu-id="de72a-119">O PowerShell dá suporte aos seguintes escopos:</span><span class="sxs-lookup"><span data-stu-id="de72a-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="de72a-120">Global: o escopo que está em vigor quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="de72a-120">Global: The scope that is in effect when PowerShell starts.</span></span> <span data-ttu-id="de72a-121">Variáveis e funções que estão presentes quando o PowerShell é iniciado foram criadas no escopo global, como variáveis automáticas e variáveis de preferência.</span><span class="sxs-lookup"><span data-stu-id="de72a-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="de72a-122">As variáveis, os aliases e as funções nos perfis do PowerShell também são criados no escopo global.</span><span class="sxs-lookup"><span data-stu-id="de72a-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span>

- <span data-ttu-id="de72a-123">Local: o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-123">Local: The current scope.</span></span> <span data-ttu-id="de72a-124">O escopo local pode ser o escopo global ou qualquer outro escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-124">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="de72a-125">Script: o escopo que é criado enquanto um arquivo de script é executado.</span><span class="sxs-lookup"><span data-stu-id="de72a-125">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="de72a-126">Somente os comandos no script são executados no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="de72a-126">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="de72a-127">Para os comandos em um script, o escopo do script é o escopo local.</span><span class="sxs-lookup"><span data-stu-id="de72a-127">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="de72a-128">**Privado** não é um escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-128">**Private** is not a scope.</span></span> <span data-ttu-id="de72a-129">É uma [opção](#private-option) que altera a visibilidade de um item fora do escopo onde o item é definido.</span><span class="sxs-lookup"><span data-stu-id="de72a-129">It is an [option](#private-option) that changes the visibility of an item outside of the the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="de72a-130">Escopos pai e filho</span><span class="sxs-lookup"><span data-stu-id="de72a-130">Parent and Child Scopes</span></span>

<span data-ttu-id="de72a-131">Você pode criar um novo escopo executando um script ou uma função, criando uma sessão ou iniciando uma nova instância do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de72a-131">You can create a new scope by running a script or function, by creating a session, or by starting a new instance of PowerShell.</span></span> <span data-ttu-id="de72a-132">Quando você cria um novo escopo, o resultado é um escopo pai (o escopo original) e um escopo filho (o escopo que você criou).</span><span class="sxs-lookup"><span data-stu-id="de72a-132">When you create a new scope, the result is a parent scope (the original scope) and a child scope (the scope that you created).</span></span>

<span data-ttu-id="de72a-133">No PowerShell, todos os escopos são escopos filho do escopo global, mas você pode criar muitos escopos e muitos escopos recursivos.</span><span class="sxs-lookup"><span data-stu-id="de72a-133">In PowerShell, all scopes are child scopes of the global scope, but you can create many scopes and many recursive scopes.</span></span>

<span data-ttu-id="de72a-134">A menos que você explicitamente torne os itens particulares, os itens no escopo pai estão disponíveis para o escopo filho.</span><span class="sxs-lookup"><span data-stu-id="de72a-134">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="de72a-135">No entanto, os itens que você cria e alteram no escopo filho não afetam o escopo pai, a menos que você especifique explicitamente o escopo ao criar os itens.</span><span class="sxs-lookup"><span data-stu-id="de72a-135">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

## <a name="inheritance"></a><span data-ttu-id="de72a-136">Herança</span><span class="sxs-lookup"><span data-stu-id="de72a-136">Inheritance</span></span>

<span data-ttu-id="de72a-137">Um escopo filho não herda as variáveis, aliases e funções do escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-137">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="de72a-138">A menos que um item seja privado, o escopo filho pode exibir os itens no escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-138">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="de72a-139">E ele pode alterar os itens especificando explicitamente o escopo pai, mas os itens não fazem parte do escopo filho.</span><span class="sxs-lookup"><span data-stu-id="de72a-139">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="de72a-140">No entanto, um escopo filho é criado com um conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="de72a-140">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="de72a-141">Normalmente, inclui todos os aliases que têm a opção de **escopo** .</span><span class="sxs-lookup"><span data-stu-id="de72a-141">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="de72a-142">Essa opção será discutida posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="de72a-142">This option is discussed later in this article.</span></span> <span data-ttu-id="de72a-143">Ele inclui todas as variáveis que têm a opção de **escopo** , além de algumas variáveis automáticas.</span><span class="sxs-lookup"><span data-stu-id="de72a-143">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="de72a-144">Para localizar os itens em um escopo específico, use o parâmetro scope de `Get-Variable` ou `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="de72a-144">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="de72a-145">Por exemplo, para obter todas as variáveis no escopo local, digite:</span><span class="sxs-lookup"><span data-stu-id="de72a-145">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="de72a-146">Para obter todas as variáveis no escopo global, digite:</span><span class="sxs-lookup"><span data-stu-id="de72a-146">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="de72a-147">Modificadores de escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-147">Scope Modifiers</span></span>

<span data-ttu-id="de72a-148">Uma variável, alias ou nome de função pode incluir qualquer um dos seguintes modificadores de escopo opcionais:</span><span class="sxs-lookup"><span data-stu-id="de72a-148">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="de72a-149">`global:` -Especifica que o nome existe no escopo **global** .</span><span class="sxs-lookup"><span data-stu-id="de72a-149">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="de72a-150">`local:` -Especifica que o nome existe no escopo **local** .</span><span class="sxs-lookup"><span data-stu-id="de72a-150">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="de72a-151">O escopo atual é sempre o escopo **local** .</span><span class="sxs-lookup"><span data-stu-id="de72a-151">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="de72a-152">`private:` -Especifica que o nome é **privado** e visível somente para o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-152">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="de72a-153">`script:` -Especifica que o nome existe no escopo do **script** .</span><span class="sxs-lookup"><span data-stu-id="de72a-153">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="de72a-154">Escopo de **script** é o escopo do arquivo de script ancestral mais próximo ou **global** se não houver nenhum arquivo de script ancestral mais próximo.</span><span class="sxs-lookup"><span data-stu-id="de72a-154">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="de72a-155">`using:` -Usado para acessar variáveis definidas em outro escopo durante a execução de scripts por meio de cmdlets como `Start-Job` e `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="de72a-155">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="de72a-156">`workflow:` -Especifica que o nome existe em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="de72a-156">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="de72a-157">Observação: não há suporte para fluxos de trabalho no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="de72a-157">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="de72a-158">`<variable-namespace>` -Um modificador criado por um provedor PSDrive do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de72a-158">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="de72a-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="de72a-159">For example:</span></span>

  |  <span data-ttu-id="de72a-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="de72a-160">Namespace</span></span>  |                    <span data-ttu-id="de72a-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="de72a-161">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="de72a-162">Aliases definidos no escopo atual</span><span class="sxs-lookup"><span data-stu-id="de72a-162">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="de72a-163">Variáveis de ambiente definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="de72a-163">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="de72a-164">Funções definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="de72a-164">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="de72a-165">Variáveis definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="de72a-165">Variables defined in the current scope</span></span>             |

<span data-ttu-id="de72a-166">O escopo padrão para scripts é o escopo do script.</span><span class="sxs-lookup"><span data-stu-id="de72a-166">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="de72a-167">O escopo padrão para funções e aliases é o escopo local, mesmo se eles forem definidos em um script.</span><span class="sxs-lookup"><span data-stu-id="de72a-167">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="de72a-168">Usando modificadores de escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-168">Using scope modifiers</span></span>

<span data-ttu-id="de72a-169">Para especificar o escopo de uma nova variável, alias ou função, use um modificador de escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-169">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="de72a-170">A sintaxe para um modificador de escopo em uma variável é:</span><span class="sxs-lookup"><span data-stu-id="de72a-170">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="de72a-171">A sintaxe para um modificador de escopo em uma função é:</span><span class="sxs-lookup"><span data-stu-id="de72a-171">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="de72a-172">O comando a seguir, que não usa um modificador de escopo, cria uma variável no escopo atual ou **local** :</span><span class="sxs-lookup"><span data-stu-id="de72a-172">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="de72a-173">Para criar a mesma variável no escopo **global** , use o `global:` modificador de escopo:</span><span class="sxs-lookup"><span data-stu-id="de72a-173">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="de72a-174">Para criar a mesma variável no escopo do **script** , use o `script:` modificador de escopo:</span><span class="sxs-lookup"><span data-stu-id="de72a-174">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="de72a-175">Você também pode usar um modificador de escopo com funções.</span><span class="sxs-lookup"><span data-stu-id="de72a-175">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="de72a-176">A definição de função a seguir cria uma função no escopo **global** :</span><span class="sxs-lookup"><span data-stu-id="de72a-176">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="de72a-177">Você também pode usar modificadores de escopo para se referir a uma variável em um escopo diferente.</span><span class="sxs-lookup"><span data-stu-id="de72a-177">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="de72a-178">O comando a seguir refere-se à `$test` variável, primeiro no escopo local e, em seguida, no escopo global:</span><span class="sxs-lookup"><span data-stu-id="de72a-178">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="de72a-179">O `Using:` modificador de escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-179">The `Using:` scope modifier</span></span>

<span data-ttu-id="de72a-180">Using é um modificador de escopo especial que identifica uma variável local em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="de72a-180">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="de72a-181">Sem um modificador, o PowerShell espera que as variáveis em comandos remotos sejam definidas na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="de72a-181">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="de72a-182">O `Using` modificador de escopo é introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de72a-182">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="de72a-183">Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los.</span><span class="sxs-lookup"><span data-stu-id="de72a-183">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="de72a-184">O `Using` modificador de escopo tem suporte nos seguintes contextos:</span><span class="sxs-lookup"><span data-stu-id="de72a-184">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="de72a-185">Comandos executados remotamente, iniciados com `Invoke-Command` o uso do parâmetro **ComputerName** ou **Session** (sessão remota)</span><span class="sxs-lookup"><span data-stu-id="de72a-185">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** or **Session** parameter (remote session)</span></span>
- <span data-ttu-id="de72a-186">Trabalhos em segundo plano, iniciados com `Start-Job` (sessão fora do processo)</span><span class="sxs-lookup"><span data-stu-id="de72a-186">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="de72a-187">Trabalhos de thread, iniciados via `Start-ThreadJob` ou `ForEach-Object -Parallel` (sessão de thread separada)</span><span class="sxs-lookup"><span data-stu-id="de72a-187">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="de72a-188">Dependendo do contexto, os valores de variáveis inseridos são cópias independentes dos dados no escopo do chamador ou referências a ele.</span><span class="sxs-lookup"><span data-stu-id="de72a-188">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="de72a-189">Em sessões remotas e fora do processo, elas são sempre cópias independentes.</span><span class="sxs-lookup"><span data-stu-id="de72a-189">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="de72a-190">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="de72a-190">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="de72a-191">Em sessões de thread, elas são passadas por referência.</span><span class="sxs-lookup"><span data-stu-id="de72a-191">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="de72a-192">Isso significa que é possível modificar variáveis de escopo de chamada em um thread diferente.</span><span class="sxs-lookup"><span data-stu-id="de72a-192">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="de72a-193">Para modificar com segurança as variáveis exige a sincronização de threads.</span><span class="sxs-lookup"><span data-stu-id="de72a-193">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="de72a-194">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="de72a-194">For more information see:</span></span>

- [<span data-ttu-id="de72a-195">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="de72a-195">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="de72a-196">Serialização de valores de variáveis</span><span class="sxs-lookup"><span data-stu-id="de72a-196">Serialization of variable values</span></span>

<span data-ttu-id="de72a-197">Comandos executados remotamente e trabalhos em segundo plano são executados fora do processo.</span><span class="sxs-lookup"><span data-stu-id="de72a-197">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="de72a-198">Sessões fora do processo usam serialização e desserialização baseadas em XML para tornar os valores das variáveis disponíveis nos limites do processo.</span><span class="sxs-lookup"><span data-stu-id="de72a-198">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="de72a-199">O processo de serialização converte objetos em um **PSObject** que contém as propriedades dos objetos originais, mas não seus métodos.</span><span class="sxs-lookup"><span data-stu-id="de72a-199">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="de72a-200">Para um conjunto limitado de tipos, a desserialização rehydrates objetos de volta para o tipo original.</span><span class="sxs-lookup"><span data-stu-id="de72a-200">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="de72a-201">O objeto de resalimentação é uma cópia da instância do objeto original.</span><span class="sxs-lookup"><span data-stu-id="de72a-201">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="de72a-202">Ele tem as propriedades e os métodos do tipo.</span><span class="sxs-lookup"><span data-stu-id="de72a-202">It has the type properties and methods.</span></span> <span data-ttu-id="de72a-203">Para tipos simples, como **System. Version** , a cópia é exata.</span><span class="sxs-lookup"><span data-stu-id="de72a-203">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="de72a-204">Para tipos complexos, a cópia é imperfeita.</span><span class="sxs-lookup"><span data-stu-id="de72a-204">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="de72a-205">Por exemplo, os objetos de certificado resalimentados não incluem a chave privada.</span><span class="sxs-lookup"><span data-stu-id="de72a-205">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="de72a-206">Instâncias de todos os outros tipos são instâncias de **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="de72a-206">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="de72a-207">A propriedade **PSTypeNames** contém o nome do tipo original prefixado com **desserializado** , por exemplo, **Deserialized.System. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="de72a-207">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="de72a-208">A opção de escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-208">The AllScope Option</span></span>

<span data-ttu-id="de72a-209">Variáveis e aliases têm uma propriedade **Option** que pode assumir um valor de **escopo** .</span><span class="sxs-lookup"><span data-stu-id="de72a-209">Variables and aliases have an **Option** property that can take a value of **AllScope** .</span></span> <span data-ttu-id="de72a-210">Os itens que têm a propriedade de **escopo** se tornam parte de qualquer escopo filho que você criar, embora eles não sejam herdados retroativamente por escopos pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-210">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="de72a-211">Um item que tem a propriedade de **escopo** é visível no escopo filho e faz parte desse escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-211">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="de72a-212">As alterações no item em qualquer escopo afetam todos os escopos nos quais a variável é definida.</span><span class="sxs-lookup"><span data-stu-id="de72a-212">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="de72a-213">Gerenciando escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-213">Managing Scope</span></span>

<span data-ttu-id="de72a-214">Vários cmdlets têm um parâmetro de **escopo** que permite obter ou definir (criar e alterar) itens em um escopo específico.</span><span class="sxs-lookup"><span data-stu-id="de72a-214">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="de72a-215">Use o seguinte comando para localizar todos os cmdlets em sua sessão que têm um parâmetro de **escopo** :</span><span class="sxs-lookup"><span data-stu-id="de72a-215">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="de72a-216">Para localizar as variáveis que são visíveis em um escopo específico, use o `Scope` parâmetro de `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="de72a-216">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="de72a-217">As variáveis visíveis incluem variáveis globais, variáveis no escopo pai e variáveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-217">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="de72a-218">Por exemplo, o comando a seguir obtém as variáveis que são visíveis no escopo local:</span><span class="sxs-lookup"><span data-stu-id="de72a-218">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="de72a-219">Para criar uma variável em um escopo específico, use um modificador de escopo ou o parâmetro de **escopo** de `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="de72a-219">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="de72a-220">O comando a seguir cria uma variável no escopo global:</span><span class="sxs-lookup"><span data-stu-id="de72a-220">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="de72a-221">Você também pode usar o parâmetro de escopo dos `New-Alias` `Set-Alias` `Get-Alias` cmdlets, ou para especificar o escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-221">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="de72a-222">O comando a seguir cria um alias no escopo global:</span><span class="sxs-lookup"><span data-stu-id="de72a-222">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="de72a-223">Para obter as funções em um escopo específico, use o `Get-Item` cmdlet quando estiver no escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-223">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="de72a-224">O `Get-Item` cmdlet não tem um parâmetro de **escopo** .</span><span class="sxs-lookup"><span data-stu-id="de72a-224">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="de72a-225">Para os cmdlets que usam o parâmetro de **escopo** , você também pode se referir a escopos por número.</span><span class="sxs-lookup"><span data-stu-id="de72a-225">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="de72a-226">O número descreve a posição relativa de um escopo para outro.</span><span class="sxs-lookup"><span data-stu-id="de72a-226">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="de72a-227">O escopo 0 representa o escopo atual, ou local.</span><span class="sxs-lookup"><span data-stu-id="de72a-227">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="de72a-228">O escopo 1 indica o escopo pai imediato.</span><span class="sxs-lookup"><span data-stu-id="de72a-228">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="de72a-229">Escopo 2 indica o pai do escopo pai e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="de72a-229">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="de72a-230">Os escopos numerados serão úteis se você tiver criado muitos escopos recursivos.</span><span class="sxs-lookup"><span data-stu-id="de72a-230">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="de72a-231">Usando a notação de origem de ponto com escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-231">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="de72a-232">Scripts e funções seguem todas as regras de escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-232">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="de72a-233">Você os cria em um escopo específico e eles afetam somente esse escopo, a menos que você use um parâmetro de cmdlet ou um modificador de escopo para alterar esse escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-233">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="de72a-234">Mas, você pode adicionar um script ou função ao escopo atual usando a notação de origem de ponto.</span><span class="sxs-lookup"><span data-stu-id="de72a-234">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="de72a-235">Em seguida, quando um script é executado no escopo atual, todas as funções, aliases e variáveis que o script cria estão disponíveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-235">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="de72a-236">Para adicionar uma função ao escopo atual, digite um ponto (.) e um espaço antes do caminho e do nome da função na chamada de função.</span><span class="sxs-lookup"><span data-stu-id="de72a-236">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="de72a-237">Por exemplo, para executar o script Sample.ps1 do diretório C:\Scripts no escopo do script (o padrão para scripts), use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="de72a-237">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="de72a-238">Para executar o script de Sample.ps1 no escopo local, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="de72a-238">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="de72a-239">Quando você usa o operador de chamada (&) para executar uma função ou script, ele não é adicionado ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-239">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="de72a-240">O exemplo a seguir usa o operador Call:</span><span class="sxs-lookup"><span data-stu-id="de72a-240">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="de72a-241">Você pode ler mais sobre o operador de chamada em [about_Operators](about_operators.md).</span><span class="sxs-lookup"><span data-stu-id="de72a-241">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="de72a-242">Quaisquer aliases, funções ou variáveis que o script de Sample.ps1 cria não estão disponíveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-242">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="de72a-243">Restringindo sem escopo</span><span class="sxs-lookup"><span data-stu-id="de72a-243">Restricting Without Scope</span></span>

<span data-ttu-id="de72a-244">Alguns conceitos do PowerShell são semelhantes ao escopo ou a interação com o escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-244">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="de72a-245">Esses conceitos podem ser confundidos com o escopo ou o comportamento do escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-245">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="de72a-246">As sessões, os módulos e os prompts aninhados são ambientes independentes, mas não são escopos filho do escopo global na sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-246">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="de72a-247">Sessões</span><span class="sxs-lookup"><span data-stu-id="de72a-247">Sessions</span></span>

<span data-ttu-id="de72a-248">Uma sessão é um ambiente no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="de72a-248">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="de72a-249">Quando você cria uma sessão em um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="de72a-249">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="de72a-250">A conexão persistente permite que você use a sessão para vários comandos relacionados.</span><span class="sxs-lookup"><span data-stu-id="de72a-250">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="de72a-251">Como uma sessão é um ambiente contido, ela tem seu próprio escopo, mas uma sessão não é um escopo filho da sessão na qual foi criada.</span><span class="sxs-lookup"><span data-stu-id="de72a-251">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="de72a-252">A sessão começa com seu próprio escopo global.</span><span class="sxs-lookup"><span data-stu-id="de72a-252">The session starts with its own global scope.</span></span> <span data-ttu-id="de72a-253">Esse escopo é independente do escopo global da sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-253">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="de72a-254">Você pode criar escopos filho na sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-254">You can create child scopes in the session.</span></span> <span data-ttu-id="de72a-255">Por exemplo, você pode executar um script para criar um escopo filho em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-255">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="de72a-256">Módulos</span><span class="sxs-lookup"><span data-stu-id="de72a-256">Modules</span></span>

<span data-ttu-id="de72a-257">Você pode usar um módulo do PowerShell para compartilhar e entregar ferramentas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de72a-257">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="de72a-258">Um módulo é uma unidade que pode conter cmdlets, scripts, funções, variáveis, aliases e outros itens úteis.</span><span class="sxs-lookup"><span data-stu-id="de72a-258">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="de72a-259">A menos que definido explicitamente, os itens em um módulo não são acessíveis fora do módulo.</span><span class="sxs-lookup"><span data-stu-id="de72a-259">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="de72a-260">Portanto, você pode adicionar o módulo à sua sessão e usar os itens públicos sem se preocupar que os outros itens podem substituir os cmdlets, scripts, funções e outros itens em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-260">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="de72a-261">Por padrão, os módulos são carregados no nível superior do _estado de sessão_ atual, não no _escopo_ atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-261">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_ .</span></span> <span data-ttu-id="de72a-262">O estado da sessão atual pode ser um estado de sessão de módulo ou o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="de72a-262">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="de72a-263">A adição de um módulo a uma sessão não altera o escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-263">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="de72a-264">Se você estiver no escopo global, os módulos serão carregados no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="de72a-264">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="de72a-265">Todas as exportações são colocadas nas tabelas globais.</span><span class="sxs-lookup"><span data-stu-id="de72a-265">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="de72a-266">Se você carregar Module2 de _dentro_ de Module1, Module2 será carregado no estado de sessão de Module1 não o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="de72a-266">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="de72a-267">Todas as exportações de Module2 são colocadas na parte superior do estado de sessão do Module1.</span><span class="sxs-lookup"><span data-stu-id="de72a-267">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="de72a-268">Se você usar `Import-Module -Scope local` , as exportações serão colocadas no objeto de escopo atual, e não no nível superior.</span><span class="sxs-lookup"><span data-stu-id="de72a-268">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="de72a-269">Se você estiver _em um módulo_ e usar `Import-Module -Scope global` (ou `Import-Module -Global` ) para carregar outro módulo, esse módulo e as exportações serão carregados no estado de sessão global em vez do estado de sessão local do módulo.</span><span class="sxs-lookup"><span data-stu-id="de72a-269">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="de72a-270">Esse recurso foi criado para gravar o módulo que manipula módulos.</span><span class="sxs-lookup"><span data-stu-id="de72a-270">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="de72a-271">O módulo **WindowsCompatibility** faz isso para importar módulos de proxy para o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="de72a-271">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="de72a-272">Dentro do estado da sessão, os módulos têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-272">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="de72a-273">Considere o seguinte módulo `C:\temp\mod1.psm1` :</span><span class="sxs-lookup"><span data-stu-id="de72a-273">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="de72a-274">Agora, criamos uma variável global `$a` , atribuimos a ela um valor e chamamos a função **foo** .</span><span class="sxs-lookup"><span data-stu-id="de72a-274">Now we create a global variable `$a`, give it a value and call the function **foo** .</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="de72a-275">O módulo declara a variável `$a` no escopo do módulo e, em seguida, a função **foo** gera o valor da variável em ambos os escopos.</span><span class="sxs-lookup"><span data-stu-id="de72a-275">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="de72a-276">Prompts aninhados</span><span class="sxs-lookup"><span data-stu-id="de72a-276">Nested Prompts</span></span>

<span data-ttu-id="de72a-277">Os prompts aninhados não têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-277">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="de72a-278">Quando você insere um prompt aninhado, o prompt aninhado é um subconjunto do ambiente.</span><span class="sxs-lookup"><span data-stu-id="de72a-278">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="de72a-279">Mas, você permanece dentro do escopo local.</span><span class="sxs-lookup"><span data-stu-id="de72a-279">But, you remain within the local scope.</span></span>

<span data-ttu-id="de72a-280">Os scripts têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-280">Scripts do have their own scope.</span></span> <span data-ttu-id="de72a-281">Se você estiver depurando um script e chegar a um ponto de interrupção no script, insira o escopo do script.</span><span class="sxs-lookup"><span data-stu-id="de72a-281">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="de72a-282">Opção particular</span><span class="sxs-lookup"><span data-stu-id="de72a-282">Private Option</span></span>

<span data-ttu-id="de72a-283">Aliases e variáveis têm uma propriedade **Option** que pode ter um valor de **Private** .</span><span class="sxs-lookup"><span data-stu-id="de72a-283">Aliases and variables have an **Option** property that can take a value of **Private** .</span></span> <span data-ttu-id="de72a-284">Os itens que têm a opção **particular** podem ser exibidos e alterados no escopo no qual eles são criados, mas não podem ser exibidos ou alterados fora desse escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-284">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="de72a-285">Por exemplo, se você criar uma variável que tenha uma opção particular no escopo global e, em seguida, executar um script, `Get-Variable` os comandos no script não exibirão a variável particular.</span><span class="sxs-lookup"><span data-stu-id="de72a-285">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="de72a-286">Usar o modificador de escopo global nessa instância não exibe a variável particular.</span><span class="sxs-lookup"><span data-stu-id="de72a-286">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="de72a-287">Você pode usar o parâmetro Option dos `New-Variable` `Set-Variable` `New-Alias` cmdlets,, e `Set-Alias` para definir o valor da propriedade Option como Private.</span><span class="sxs-lookup"><span data-stu-id="de72a-287">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="de72a-288">Visibilidade</span><span class="sxs-lookup"><span data-stu-id="de72a-288">Visibility</span></span>

<span data-ttu-id="de72a-289">A propriedade **Visibility** de uma variável ou alias determina se você pode ver o item fora do contêiner, no qual ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="de72a-289">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="de72a-290">Um contêiner pode ser um módulo, um script ou um snap-in.</span><span class="sxs-lookup"><span data-stu-id="de72a-290">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="de72a-291">A visibilidade é projetada para contêineres da mesma maneira que o valor **particular** da propriedade **Option** é projetado para escopos.</span><span class="sxs-lookup"><span data-stu-id="de72a-291">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="de72a-292">A propriedade **Visibility** usa os valores **público** e **privado** .</span><span class="sxs-lookup"><span data-stu-id="de72a-292">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="de72a-293">Os itens que têm visibilidade privada podem ser exibidos e alterados somente no contêiner no qual eles foram criados.</span><span class="sxs-lookup"><span data-stu-id="de72a-293">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="de72a-294">Se o contêiner for adicionado ou importado, os itens que têm visibilidade privada não poderão ser exibidos ou alterados.</span><span class="sxs-lookup"><span data-stu-id="de72a-294">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="de72a-295">Como a visibilidade é projetada para contêineres, ela funciona de forma diferente em um escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-295">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="de72a-296">Se você criar um item que tenha visibilidade privada no escopo global, não poderá exibir nem alterar o item em nenhum escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-296">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="de72a-297">Se você tentar exibir ou alterar o valor de uma variável que tem visibilidade privada, o PowerShell retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="de72a-297">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="de72a-298">Você pode usar os `New-Variable` `Set-Variable` cmdlets e para criar uma variável que tenha visibilidade privada.</span><span class="sxs-lookup"><span data-stu-id="de72a-298">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="de72a-299">Exemplos</span><span class="sxs-lookup"><span data-stu-id="de72a-299">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="de72a-300">Exemplo 1: alterar um valor de variável somente em um script</span><span class="sxs-lookup"><span data-stu-id="de72a-300">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="de72a-301">O comando a seguir altera o valor da `$ConfirmPreference` variável em um script.</span><span class="sxs-lookup"><span data-stu-id="de72a-301">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="de72a-302">A alteração não afeta o escopo global.</span><span class="sxs-lookup"><span data-stu-id="de72a-302">The change does not affect the global scope.</span></span>

<span data-ttu-id="de72a-303">Primeiro, para exibir o valor da `$ConfirmPreference` variável no escopo local, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="de72a-303">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="de72a-304">Crie um script de Scope.ps1 que contenha os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="de72a-304">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="de72a-305">Execute o script.</span><span class="sxs-lookup"><span data-stu-id="de72a-305">Run the script.</span></span> <span data-ttu-id="de72a-306">O script altera o valor da `$ConfirmPreference` variável e, em seguida, relata seu valor no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="de72a-306">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="de72a-307">A saída deve se parecer com a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="de72a-307">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="de72a-308">Em seguida, teste o valor atual da `$ConfirmPreference` variável no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="de72a-308">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="de72a-309">Este exemplo mostra que as alterações no valor de uma variável no escopo do script não afetam o valor da variável no escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-309">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="de72a-310">Exemplo 2: exibir um valor de variável em escopos diferentes</span><span class="sxs-lookup"><span data-stu-id="de72a-310">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="de72a-311">Você pode usar modificadores de escopo para exibir o valor de uma variável no escopo local e em um escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-311">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="de72a-312">Primeiro, defina uma `$test` variável no escopo global.</span><span class="sxs-lookup"><span data-stu-id="de72a-312">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="de72a-313">Em seguida, crie um script de Sample.ps1 que define a `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="de72a-313">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="de72a-314">No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="de72a-314">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="de72a-315">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="de72a-315">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="de72a-316">Quando você executa Sample.ps1, a saída deve se parecer com a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="de72a-316">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="de72a-317">Quando o script for concluído, somente o valor global de `$test` será definido na sessão.</span><span class="sxs-lookup"><span data-stu-id="de72a-317">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="de72a-318">Exemplo 3: alterar o valor de uma variável em um escopo pai</span><span class="sxs-lookup"><span data-stu-id="de72a-318">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="de72a-319">A menos que você proteja um item usando a opção particular ou outro método, você pode exibir e alterar o valor de uma variável em um escopo pai.</span><span class="sxs-lookup"><span data-stu-id="de72a-319">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="de72a-320">Primeiro, defina uma `$test` variável no escopo global.</span><span class="sxs-lookup"><span data-stu-id="de72a-320">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="de72a-321">Em seguida, crie um script de Sample.ps1 que define a `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="de72a-321">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="de72a-322">No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="de72a-322">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="de72a-323">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="de72a-323">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="de72a-324">Quando o script for concluído, o valor global de `$test` será alterado.</span><span class="sxs-lookup"><span data-stu-id="de72a-324">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="de72a-325">Exemplo 4: criando uma variável privada</span><span class="sxs-lookup"><span data-stu-id="de72a-325">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="de72a-326">Uma variável particular é uma variável que tem uma propriedade **Option** que tem um valor de *Private* .</span><span class="sxs-lookup"><span data-stu-id="de72a-326">A private variable is a variable that has an **Option** property that has a value of *Private* .</span></span> <span data-ttu-id="de72a-327">As variáveis *privadas* são herdadas pelo escopo filho, mas só podem ser exibidas ou alteradas no escopo no qual foram criadas.</span><span class="sxs-lookup"><span data-stu-id="de72a-327">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="de72a-328">O comando a seguir cria uma variável privada chamada `$ptest` no escopo local.</span><span class="sxs-lookup"><span data-stu-id="de72a-328">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="de72a-329">Você pode exibir e alterar o valor de `$ptest` no escopo local.</span><span class="sxs-lookup"><span data-stu-id="de72a-329">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="de72a-330">Em seguida, crie um script de Sample.ps1 que contenha os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="de72a-330">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="de72a-331">O comando tenta exibir e alterar o valor de `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="de72a-331">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="de72a-332">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="de72a-332">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="de72a-333">A `$ptest` variável não está visível no escopo do script, a saída está vazia.</span><span class="sxs-lookup"><span data-stu-id="de72a-333">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="de72a-334">Exemplo 5: usando uma variável local em um comando remoto</span><span class="sxs-lookup"><span data-stu-id="de72a-334">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="de72a-335">Para variáveis em um comando remoto criado na sessão local, use o `Using` modificador de escopo.</span><span class="sxs-lookup"><span data-stu-id="de72a-335">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="de72a-336">O PowerShell pressupõe que as variáveis em comandos remotos foram criadas na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="de72a-336">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="de72a-337">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="de72a-337">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="de72a-338">Por exemplo, os comandos a seguir criam uma `$Cred` variável na sessão local e, em seguida, usam a `$Cred` variável em um comando remoto:</span><span class="sxs-lookup"><span data-stu-id="de72a-338">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="de72a-339">O escopo de uso foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de72a-339">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="de72a-340">No PowerShell 2,0, para indicar que uma variável foi criada na sessão local, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="de72a-340">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="de72a-341">Confira também</span><span class="sxs-lookup"><span data-stu-id="de72a-341">See also</span></span>

[<span data-ttu-id="de72a-342">about_Variables</span><span class="sxs-lookup"><span data-stu-id="de72a-342">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="de72a-343">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="de72a-343">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="de72a-344">about_Functions</span><span class="sxs-lookup"><span data-stu-id="de72a-344">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="de72a-345">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="de72a-345">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="de72a-346">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="de72a-346">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)
