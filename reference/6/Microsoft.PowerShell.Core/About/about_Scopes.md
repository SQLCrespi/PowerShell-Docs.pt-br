---
description: Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 15c3d606ec13166e137bbcd633269dbf03ab7817
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354841"
---
# <a name="about-scopes"></a><span data-ttu-id="e1a1f-104">Sobre escopos</span><span class="sxs-lookup"><span data-stu-id="e1a1f-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="e1a1f-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="e1a1f-105">Short description</span></span>
<span data-ttu-id="e1a1f-106">Explica o conceito de escopo no PowerShell e mostra como definir e alterar o escopo dos elementos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="e1a1f-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="e1a1f-107">Long description</span></span>

<span data-ttu-id="e1a1f-108">O PowerShell protege o acesso a variáveis, aliases, funções e unidades do PowerShell (PSDrive) limitando o local em que eles podem ser lidos e alterados.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="e1a1f-109">O PowerShell usa regras de escopo para garantir que você não altere inadvertidamente um item que não deva ser alterado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="e1a1f-110">A seguir estão as regras básicas de escopo:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="e1a1f-111">Os escopos podem ser aninhados.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-111">Scopes may nest.</span></span> <span data-ttu-id="e1a1f-112">Um escopo externo é conhecido como escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="e1a1f-113">Todos os escopos aninhados são escopos filho desse pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="e1a1f-114">Um item é visível no escopo no qual ele foi criado e em qualquer escopo filho, a menos que você o torne explicitamente privado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="e1a1f-115">Você pode inserir variáveis, aliases, funções ou unidades do PowerShell em um ou mais escopos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="e1a1f-116">Um item que você criou em um escopo pode ser alterado somente no escopo no qual ele foi criado, a menos que você especifique explicitamente um escopo diferente.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="e1a1f-117">Se você criar um item em um escopo e o item compartilhar seu nome com um item em um escopo diferente, o item original poderá estar oculto no novo item, mas ele não será substituído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="e1a1f-118">Escopos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1a1f-118">PowerShell Scopes</span></span>

<span data-ttu-id="e1a1f-119">O PowerShell dá suporte aos seguintes escopos:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="e1a1f-120">Global: o escopo que está em vigor quando o PowerShell é iniciado ou quando você cria uma nova sessão ou runspace.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-120">Global: The scope that is in effect when PowerShell starts or when you create a new session or runspace.</span></span> <span data-ttu-id="e1a1f-121">Variáveis e funções que estão presentes quando o PowerShell é iniciado foram criadas no escopo global, como variáveis automáticas e variáveis de preferência.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="e1a1f-122">As variáveis, os aliases e as funções nos perfis do PowerShell também são criados no escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span> <span data-ttu-id="e1a1f-123">O escopo global é o escopo pai raiz em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-123">The global scope is the root parent scope in a session.</span></span>

- <span data-ttu-id="e1a1f-124">Local: o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-124">Local: The current scope.</span></span> <span data-ttu-id="e1a1f-125">O escopo local pode ser o escopo global ou qualquer outro escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-125">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="e1a1f-126">Script: o escopo que é criado enquanto um arquivo de script é executado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-126">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="e1a1f-127">Somente os comandos no script são executados no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-127">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="e1a1f-128">Para os comandos em um script, o escopo do script é o escopo local.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-128">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a1f-129">**Privado** não é um escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-129">**Private** is not a scope.</span></span> <span data-ttu-id="e1a1f-130">É uma [opção](#private-option) que altera a visibilidade de um item fora do escopo onde o item é definido.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-130">It is an [option](#private-option) that changes the visibility of an item outside of the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="e1a1f-131">Escopos pai e filho</span><span class="sxs-lookup"><span data-stu-id="e1a1f-131">Parent and Child Scopes</span></span>

<span data-ttu-id="e1a1f-132">Você pode criar um novo escopo filho chamando um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-132">You can create a new child scope by calling a script or function.</span></span> <span data-ttu-id="e1a1f-133">O escopo de chamada é o escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-133">The calling scope is the parent scope.</span></span> <span data-ttu-id="e1a1f-134">O script ou a função chamada é o escopo filho.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-134">The called script or function is the child scope.</span></span>
<span data-ttu-id="e1a1f-135">As funções ou os scripts chamados podem chamar outras funções, criando uma hierarquia de escopos filho cujo escopo raiz é o escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-135">The functions or scripts you call may call other functions, creating a hierarchy of child scopes whose root scope is the global scope.</span></span>

<span data-ttu-id="e1a1f-136">A menos que você explicitamente torne os itens particulares, os itens no escopo pai estão disponíveis para o escopo filho.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-136">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="e1a1f-137">No entanto, os itens que você cria e alteram no escopo filho não afetam o escopo pai, a menos que você especifique explicitamente o escopo ao criar os itens.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-137">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a1f-138">As funções de um módulo não são executadas em um escopo filho do escopo de chamada.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-138">Functions from a module do not run in a child scope of the calling scope.</span></span>
> <span data-ttu-id="e1a1f-139">Os módulos têm seu próprio estado de sessão que está vinculado ao escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-139">Modules have their own session state that is linked to the global scope.</span></span>
> <span data-ttu-id="e1a1f-140">Todos os códigos de módulo são executados em uma hierarquia específica de módulo de escopos que tem seu próprio escopo raiz.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-140">All module code runs in a module-specific hierarchy of scopes that has its own root scope.</span></span>

## <a name="inheritance"></a><span data-ttu-id="e1a1f-141">Herança</span><span class="sxs-lookup"><span data-stu-id="e1a1f-141">Inheritance</span></span>

<span data-ttu-id="e1a1f-142">Um escopo filho não herda as variáveis, aliases e funções do escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-142">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="e1a1f-143">A menos que um item seja privado, o escopo filho pode exibir os itens no escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-143">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="e1a1f-144">E ele pode alterar os itens especificando explicitamente o escopo pai, mas os itens não fazem parte do escopo filho.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-144">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="e1a1f-145">No entanto, um escopo filho é criado com um conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-145">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="e1a1f-146">Normalmente, inclui todos os aliases que têm a opção de **escopo** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-146">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="e1a1f-147">Essa opção será discutida posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-147">This option is discussed later in this article.</span></span> <span data-ttu-id="e1a1f-148">Ele inclui todas as variáveis que têm a opção de **escopo** , além de algumas variáveis automáticas.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-148">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="e1a1f-149">Para localizar os itens em um escopo específico, use o parâmetro scope de `Get-Variable` ou `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-149">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="e1a1f-150">Por exemplo, para obter todas as variáveis no escopo local, digite:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-150">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="e1a1f-151">Para obter todas as variáveis no escopo global, digite:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-151">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="e1a1f-152">Modificadores de escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-152">Scope Modifiers</span></span>

<span data-ttu-id="e1a1f-153">Uma variável, alias ou nome de função pode incluir qualquer um dos seguintes modificadores de escopo opcionais:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-153">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="e1a1f-154">`global:` -Especifica que o nome existe no escopo **global** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-154">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="e1a1f-155">`local:` -Especifica que o nome existe no escopo **local** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-155">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="e1a1f-156">O escopo atual é sempre o escopo **local** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-156">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="e1a1f-157">`private:` -Especifica que o nome é **privado** e visível somente para o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-157">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="e1a1f-158">`script:` -Especifica que o nome existe no escopo do **script** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-158">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="e1a1f-159">Escopo de **script** é o escopo do arquivo de script ancestral mais próximo ou **global** se não houver nenhum arquivo de script ancestral mais próximo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-159">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="e1a1f-160">`using:` -Usado para acessar variáveis definidas em outro escopo durante a execução de scripts por meio de cmdlets como `Start-Job` e `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-160">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="e1a1f-161">`workflow:` -Especifica que o nome existe em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-161">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="e1a1f-162">Observação: não há suporte para fluxos de trabalho no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-162">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="e1a1f-163">`<variable-namespace>` -Um modificador criado por um provedor PSDrive do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-163">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="e1a1f-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-164">For example:</span></span>

  |  <span data-ttu-id="e1a1f-165">Namespace</span><span class="sxs-lookup"><span data-stu-id="e1a1f-165">Namespace</span></span>  |                    <span data-ttu-id="e1a1f-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1a1f-166">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="e1a1f-167">Aliases definidos no escopo atual</span><span class="sxs-lookup"><span data-stu-id="e1a1f-167">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="e1a1f-168">Variáveis de ambiente definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="e1a1f-168">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="e1a1f-169">Funções definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="e1a1f-169">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="e1a1f-170">Variáveis definidas no escopo atual</span><span class="sxs-lookup"><span data-stu-id="e1a1f-170">Variables defined in the current scope</span></span>             |

<span data-ttu-id="e1a1f-171">O escopo padrão para scripts é o escopo do script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-171">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="e1a1f-172">O escopo padrão para funções e aliases é o escopo local, mesmo se eles forem definidos em um script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-172">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="e1a1f-173">Usando modificadores de escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-173">Using scope modifiers</span></span>

<span data-ttu-id="e1a1f-174">Para especificar o escopo de uma nova variável, alias ou função, use um modificador de escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-174">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="e1a1f-175">A sintaxe para um modificador de escopo em uma variável é:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-175">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="e1a1f-176">A sintaxe para um modificador de escopo em uma função é:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-176">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="e1a1f-177">O comando a seguir, que não usa um modificador de escopo, cria uma variável no escopo atual ou **local** :</span><span class="sxs-lookup"><span data-stu-id="e1a1f-177">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="e1a1f-178">Para criar a mesma variável no escopo **global** , use o `global:` modificador de escopo:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-178">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="e1a1f-179">Para criar a mesma variável no escopo do **script** , use o `script:` modificador de escopo:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-179">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="e1a1f-180">Você também pode usar um modificador de escopo com funções.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-180">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="e1a1f-181">A definição de função a seguir cria uma função no escopo **global** :</span><span class="sxs-lookup"><span data-stu-id="e1a1f-181">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="e1a1f-182">Você também pode usar modificadores de escopo para se referir a uma variável em um escopo diferente.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-182">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="e1a1f-183">O comando a seguir refere-se à `$test` variável, primeiro no escopo local e, em seguida, no escopo global:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-183">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="e1a1f-184">O `Using:` modificador de escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-184">The `Using:` scope modifier</span></span>

<span data-ttu-id="e1a1f-185">Using é um modificador de escopo especial que identifica uma variável local em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-185">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="e1a1f-186">Sem um modificador, o PowerShell espera que as variáveis em comandos remotos sejam definidas na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-186">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="e1a1f-187">O `Using` modificador de escopo é introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-187">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="e1a1f-188">Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-188">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="e1a1f-189">O `Using` modificador de escopo tem suporte nos seguintes contextos:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-189">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="e1a1f-190">Comandos executados remotamente, iniciados com `Invoke-Command` o uso dos parâmetros **ComputerName** , **hostname** , **SSHConnection** ou **Session** (sessão remota)</span><span class="sxs-lookup"><span data-stu-id="e1a1f-190">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="e1a1f-191">Trabalhos em segundo plano, iniciados com `Start-Job` (sessão fora do processo)</span><span class="sxs-lookup"><span data-stu-id="e1a1f-191">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="e1a1f-192">Trabalhos de thread iniciados via `Start-ThreadJob` (sessão de thread separada)</span><span class="sxs-lookup"><span data-stu-id="e1a1f-192">Thread jobs started via `Start-ThreadJob` (separate thread session)</span></span>

<span data-ttu-id="e1a1f-193">Dependendo do contexto, os valores de variáveis inseridos são cópias independentes dos dados no escopo do chamador ou referências a ele.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-193">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="e1a1f-194">Em sessões remotas e fora do processo, elas são sempre cópias independentes.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-194">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="e1a1f-195">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e1a1f-195">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="e1a1f-196">Em sessões de thread, elas são passadas por referência.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-196">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="e1a1f-197">Isso significa que é possível modificar variáveis de escopo de chamada em um thread diferente.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-197">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="e1a1f-198">Para modificar com segurança as variáveis exige a sincronização de threads.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-198">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="e1a1f-199">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-199">For more information see:</span></span>

- [<span data-ttu-id="e1a1f-200">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="e1a1f-200">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="e1a1f-201">Serialização de valores de variáveis</span><span class="sxs-lookup"><span data-stu-id="e1a1f-201">Serialization of variable values</span></span>

<span data-ttu-id="e1a1f-202">Comandos executados remotamente e trabalhos em segundo plano são executados fora do processo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-202">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="e1a1f-203">Sessões fora do processo usam serialização e desserialização baseadas em XML para tornar os valores das variáveis disponíveis nos limites do processo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-203">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="e1a1f-204">O processo de serialização converte objetos em um **PSObject** que contém as propriedades dos objetos originais, mas não seus métodos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-204">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="e1a1f-205">Para um conjunto limitado de tipos, a desserialização rehydrates objetos de volta para o tipo original.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-205">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="e1a1f-206">O objeto de resalimentação é uma cópia da instância do objeto original.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-206">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="e1a1f-207">Ele tem as propriedades e os métodos do tipo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-207">It has the type properties and methods.</span></span> <span data-ttu-id="e1a1f-208">Para tipos simples, como **System. Version** , a cópia é exata.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-208">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="e1a1f-209">Para tipos complexos, a cópia é imperfeita.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-209">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="e1a1f-210">Por exemplo, os objetos de certificado resalimentados não incluem a chave privada.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-210">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="e1a1f-211">Instâncias de todos os outros tipos são instâncias de **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-211">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="e1a1f-212">A propriedade **PSTypeNames** contém o nome do tipo original prefixado com **desserializado** , por exemplo, **Deserialized.System. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="e1a1f-212">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="e1a1f-213">A opção de escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-213">The AllScope Option</span></span>

<span data-ttu-id="e1a1f-214">Variáveis e aliases têm uma propriedade **Option** que pode assumir um valor de **escopo**.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-214">Variables and aliases have an **Option** property that can take a value of **AllScope**.</span></span> <span data-ttu-id="e1a1f-215">Os itens que têm a propriedade de **escopo** se tornam parte de qualquer escopo filho que você criar, embora eles não sejam herdados retroativamente por escopos pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-215">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="e1a1f-216">Um item que tem a propriedade de **escopo** é visível no escopo filho e faz parte desse escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-216">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="e1a1f-217">As alterações no item em qualquer escopo afetam todos os escopos nos quais a variável é definida.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-217">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="e1a1f-218">Gerenciando escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-218">Managing Scope</span></span>

<span data-ttu-id="e1a1f-219">Vários cmdlets têm um parâmetro de **escopo** que permite obter ou definir (criar e alterar) itens em um escopo específico.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-219">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="e1a1f-220">Use o seguinte comando para localizar todos os cmdlets em sua sessão que têm um parâmetro de **escopo** :</span><span class="sxs-lookup"><span data-stu-id="e1a1f-220">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="e1a1f-221">Para localizar as variáveis que são visíveis em um escopo específico, use o `Scope` parâmetro de `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-221">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="e1a1f-222">As variáveis visíveis incluem variáveis globais, variáveis no escopo pai e variáveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-222">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="e1a1f-223">Por exemplo, o comando a seguir obtém as variáveis que são visíveis no escopo local:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-223">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="e1a1f-224">Para criar uma variável em um escopo específico, use um modificador de escopo ou o parâmetro de **escopo** de `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-224">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="e1a1f-225">O comando a seguir cria uma variável no escopo global:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-225">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="e1a1f-226">Você também pode usar o parâmetro de escopo dos `New-Alias` `Set-Alias` `Get-Alias` cmdlets, ou para especificar o escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-226">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="e1a1f-227">O comando a seguir cria um alias no escopo global:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-227">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="e1a1f-228">Para obter as funções em um escopo específico, use o `Get-Item` cmdlet quando estiver no escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-228">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="e1a1f-229">O `Get-Item` cmdlet não tem um parâmetro de **escopo** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-229">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a1f-230">Para os cmdlets que usam o parâmetro de **escopo** , você também pode se referir a escopos por número.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-230">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="e1a1f-231">O número descreve a posição relativa de um escopo para outro.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-231">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="e1a1f-232">O escopo 0 representa o escopo atual, ou local.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-232">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="e1a1f-233">O escopo 1 indica o escopo pai imediato.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-233">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="e1a1f-234">Escopo 2 indica o pai do escopo pai e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-234">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="e1a1f-235">Os escopos numerados serão úteis se você tiver criado muitos escopos recursivos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-235">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="e1a1f-236">Usando a notação de origem de ponto com escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-236">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="e1a1f-237">Scripts e funções seguem todas as regras de escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-237">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="e1a1f-238">Você os cria em um escopo específico e eles afetam somente esse escopo, a menos que você use um parâmetro de cmdlet ou um modificador de escopo para alterar esse escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-238">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="e1a1f-239">Mas, você pode adicionar um script ou função ao escopo atual usando a notação de origem de ponto.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-239">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="e1a1f-240">Em seguida, quando um script é executado no escopo atual, todas as funções, aliases e variáveis que o script cria estão disponíveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-240">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="e1a1f-241">Para adicionar uma função ao escopo atual, digite um ponto (.) e um espaço antes do caminho e do nome da função na chamada de função.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-241">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="e1a1f-242">Por exemplo, para executar o script Sample.ps1 do diretório C:\Scripts no escopo do script (o padrão para scripts), use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-242">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="e1a1f-243">Para executar o script de Sample.ps1 no escopo local, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-243">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="e1a1f-244">Quando você usa o operador de chamada (&) para executar uma função ou script, ele não é adicionado ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-244">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="e1a1f-245">O exemplo a seguir usa o operador Call:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-245">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="e1a1f-246">Você pode ler mais sobre o operador de chamada em [about_Operators](about_operators.md).</span><span class="sxs-lookup"><span data-stu-id="e1a1f-246">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="e1a1f-247">Quaisquer aliases, funções ou variáveis que o script de Sample.ps1 cria não estão disponíveis no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-247">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="e1a1f-248">Restringindo sem escopo</span><span class="sxs-lookup"><span data-stu-id="e1a1f-248">Restricting Without Scope</span></span>

<span data-ttu-id="e1a1f-249">Alguns conceitos do PowerShell são semelhantes ao escopo ou a interação com o escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-249">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="e1a1f-250">Esses conceitos podem ser confundidos com o escopo ou o comportamento do escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-250">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="e1a1f-251">As sessões, os módulos e os prompts aninhados são ambientes independentes, mas não são escopos filho do escopo global na sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-251">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="e1a1f-252">Sessões</span><span class="sxs-lookup"><span data-stu-id="e1a1f-252">Sessions</span></span>

<span data-ttu-id="e1a1f-253">Uma sessão é um ambiente no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-253">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="e1a1f-254">Quando você cria uma sessão em um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-254">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="e1a1f-255">A conexão persistente permite que você use a sessão para vários comandos relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-255">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="e1a1f-256">Como uma sessão é um ambiente contido, ela tem seu próprio escopo, mas uma sessão não é um escopo filho da sessão na qual foi criada.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-256">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="e1a1f-257">A sessão começa com seu próprio escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-257">The session starts with its own global scope.</span></span> <span data-ttu-id="e1a1f-258">Esse escopo é independente do escopo global da sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-258">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="e1a1f-259">Você pode criar escopos filho na sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-259">You can create child scopes in the session.</span></span> <span data-ttu-id="e1a1f-260">Por exemplo, você pode executar um script para criar um escopo filho em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-260">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="e1a1f-261">Módulos</span><span class="sxs-lookup"><span data-stu-id="e1a1f-261">Modules</span></span>

<span data-ttu-id="e1a1f-262">Você pode usar um módulo do PowerShell para compartilhar e entregar ferramentas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-262">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="e1a1f-263">Um módulo é uma unidade que pode conter cmdlets, scripts, funções, variáveis, aliases e outros itens úteis.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-263">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="e1a1f-264">A menos que definido explicitamente, os itens em um módulo não são acessíveis fora do módulo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-264">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="e1a1f-265">Portanto, você pode adicionar o módulo à sua sessão e usar os itens públicos sem se preocupar que os outros itens podem substituir os cmdlets, scripts, funções e outros itens em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-265">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="e1a1f-266">Por padrão, os módulos são carregados no nível superior do _estado de sessão_ atual, não no _escopo_ atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-266">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_.</span></span> <span data-ttu-id="e1a1f-267">O estado da sessão atual pode ser um estado de sessão de módulo ou o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-267">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="e1a1f-268">A adição de um módulo a uma sessão não altera o escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-268">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="e1a1f-269">Se você estiver no escopo global, os módulos serão carregados no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-269">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="e1a1f-270">Todas as exportações são colocadas nas tabelas globais.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-270">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="e1a1f-271">Se você carregar Module2 de _dentro_ de Module1, Module2 será carregado no estado de sessão de Module1 não o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-271">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="e1a1f-272">Todas as exportações de Module2 são colocadas na parte superior do estado de sessão do Module1.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-272">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="e1a1f-273">Se você usar `Import-Module -Scope local` , as exportações serão colocadas no objeto de escopo atual, e não no nível superior.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-273">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="e1a1f-274">Se você estiver _em um módulo_ e usar `Import-Module -Scope global` (ou `Import-Module -Global` ) para carregar outro módulo, esse módulo e as exportações serão carregados no estado de sessão global em vez do estado de sessão local do módulo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-274">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="e1a1f-275">Esse recurso foi criado para gravar o módulo que manipula módulos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-275">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="e1a1f-276">O módulo **WindowsCompatibility** faz isso para importar módulos de proxy para o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-276">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="e1a1f-277">Dentro do estado da sessão, os módulos têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-277">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="e1a1f-278">Considere o seguinte módulo `C:\temp\mod1.psm1` :</span><span class="sxs-lookup"><span data-stu-id="e1a1f-278">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="e1a1f-279">Agora, criamos uma variável global `$a` , atribuimos a ela um valor e chamamos a função **foo**.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-279">Now we create a global variable `$a`, give it a value and call the function **foo**.</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="e1a1f-280">O módulo declara a variável `$a` no escopo do módulo e, em seguida, a função **foo** gera o valor da variável em ambos os escopos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-280">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="e1a1f-281">Prompts aninhados</span><span class="sxs-lookup"><span data-stu-id="e1a1f-281">Nested Prompts</span></span>

<span data-ttu-id="e1a1f-282">Os prompts aninhados não têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-282">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="e1a1f-283">Quando você insere um prompt aninhado, o prompt aninhado é um subconjunto do ambiente.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-283">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="e1a1f-284">Mas, você permanece dentro do escopo local.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-284">But, you remain within the local scope.</span></span>

<span data-ttu-id="e1a1f-285">Os scripts têm seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-285">Scripts do have their own scope.</span></span> <span data-ttu-id="e1a1f-286">Se você estiver depurando um script e chegar a um ponto de interrupção no script, insira o escopo do script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-286">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="e1a1f-287">Opção particular</span><span class="sxs-lookup"><span data-stu-id="e1a1f-287">Private Option</span></span>

<span data-ttu-id="e1a1f-288">Aliases e variáveis têm uma propriedade **Option** que pode ter um valor de **Private**.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-288">Aliases and variables have an **Option** property that can take a value of **Private**.</span></span> <span data-ttu-id="e1a1f-289">Os itens que têm a opção **particular** podem ser exibidos e alterados no escopo no qual eles são criados, mas não podem ser exibidos ou alterados fora desse escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-289">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="e1a1f-290">Por exemplo, se você criar uma variável que tenha uma opção particular no escopo global e, em seguida, executar um script, `Get-Variable` os comandos no script não exibirão a variável particular.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-290">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="e1a1f-291">Usar o modificador de escopo global nessa instância não exibe a variável particular.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-291">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="e1a1f-292">Você pode usar o parâmetro Option dos `New-Variable` `Set-Variable` `New-Alias` cmdlets,, e `Set-Alias` para definir o valor da propriedade Option como Private.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-292">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="e1a1f-293">Visibilidade</span><span class="sxs-lookup"><span data-stu-id="e1a1f-293">Visibility</span></span>

<span data-ttu-id="e1a1f-294">A propriedade **Visibility** de uma variável ou alias determina se você pode ver o item fora do contêiner, no qual ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-294">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="e1a1f-295">Um contêiner pode ser um módulo, um script ou um snap-in.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-295">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="e1a1f-296">A visibilidade é projetada para contêineres da mesma maneira que o valor **particular** da propriedade **Option** é projetado para escopos.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-296">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="e1a1f-297">A propriedade **Visibility** usa os valores **público** e **privado** .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-297">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="e1a1f-298">Os itens que têm visibilidade privada podem ser exibidos e alterados somente no contêiner no qual eles foram criados.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-298">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="e1a1f-299">Se o contêiner for adicionado ou importado, os itens que têm visibilidade privada não poderão ser exibidos ou alterados.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-299">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="e1a1f-300">Como a visibilidade é projetada para contêineres, ela funciona de forma diferente em um escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-300">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="e1a1f-301">Se você criar um item que tenha visibilidade privada no escopo global, não poderá exibir nem alterar o item em nenhum escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-301">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="e1a1f-302">Se você tentar exibir ou alterar o valor de uma variável que tem visibilidade privada, o PowerShell retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-302">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="e1a1f-303">Você pode usar os `New-Variable` `Set-Variable` cmdlets e para criar uma variável que tenha visibilidade privada.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-303">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="e1a1f-304">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e1a1f-304">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="e1a1f-305">Exemplo 1: alterar um valor de variável somente em um script</span><span class="sxs-lookup"><span data-stu-id="e1a1f-305">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="e1a1f-306">O comando a seguir altera o valor da `$ConfirmPreference` variável em um script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-306">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="e1a1f-307">A alteração não afeta o escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-307">The change does not affect the global scope.</span></span>

<span data-ttu-id="e1a1f-308">Primeiro, para exibir o valor da `$ConfirmPreference` variável no escopo local, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-308">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="e1a1f-309">Crie um script de Scope.ps1 que contenha os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-309">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="e1a1f-310">Execute o script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-310">Run the script.</span></span> <span data-ttu-id="e1a1f-311">O script altera o valor da `$ConfirmPreference` variável e, em seguida, relata seu valor no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-311">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="e1a1f-312">A saída deve se parecer com a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-312">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="e1a1f-313">Em seguida, teste o valor atual da `$ConfirmPreference` variável no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-313">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="e1a1f-314">Este exemplo mostra que as alterações no valor de uma variável no escopo do script não afetam o valor da variável no escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-314">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="e1a1f-315">Exemplo 2: exibir um valor de variável em escopos diferentes</span><span class="sxs-lookup"><span data-stu-id="e1a1f-315">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="e1a1f-316">Você pode usar modificadores de escopo para exibir o valor de uma variável no escopo local e em um escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-316">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="e1a1f-317">Primeiro, defina uma `$test` variável no escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-317">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="e1a1f-318">Em seguida, crie um script de Sample.ps1 que define a `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-318">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="e1a1f-319">No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-319">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="e1a1f-320">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-320">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="e1a1f-321">Quando você executa Sample.ps1, a saída deve se parecer com a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-321">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="e1a1f-322">Quando o script for concluído, somente o valor global de `$test` será definido na sessão.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-322">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="e1a1f-323">Exemplo 3: alterar o valor de uma variável em um escopo pai</span><span class="sxs-lookup"><span data-stu-id="e1a1f-323">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="e1a1f-324">A menos que você proteja um item usando a opção particular ou outro método, você pode exibir e alterar o valor de uma variável em um escopo pai.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-324">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="e1a1f-325">Primeiro, defina uma `$test` variável no escopo global.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-325">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="e1a1f-326">Em seguida, crie um script de Sample.ps1 que define a `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-326">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="e1a1f-327">No script, use um modificador de escopo para se referir às versões global ou local da `$test` variável.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-327">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="e1a1f-328">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-328">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="e1a1f-329">Quando o script for concluído, o valor global de `$test` será alterado.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-329">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="e1a1f-330">Exemplo 4: criando uma variável privada</span><span class="sxs-lookup"><span data-stu-id="e1a1f-330">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="e1a1f-331">Uma variável particular é uma variável que tem uma propriedade **Option** que tem um valor de *Private*.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-331">A private variable is a variable that has an **Option** property that has a value of *Private*.</span></span> <span data-ttu-id="e1a1f-332">As variáveis *privadas* são herdadas pelo escopo filho, mas só podem ser exibidas ou alteradas no escopo no qual foram criadas.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-332">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="e1a1f-333">O comando a seguir cria uma variável privada chamada `$ptest` no escopo local.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-333">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="e1a1f-334">Você pode exibir e alterar o valor de `$ptest` no escopo local.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-334">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="e1a1f-335">Em seguida, crie um script de Sample.ps1 que contenha os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-335">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="e1a1f-336">O comando tenta exibir e alterar o valor de `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="e1a1f-336">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="e1a1f-337">Em Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-337">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="e1a1f-338">A `$ptest` variável não está visível no escopo do script, a saída está vazia.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-338">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="e1a1f-339">Exemplo 5: usando uma variável local em um comando remoto</span><span class="sxs-lookup"><span data-stu-id="e1a1f-339">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="e1a1f-340">Para variáveis em um comando remoto criado na sessão local, use o `Using` modificador de escopo.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-340">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="e1a1f-341">O PowerShell pressupõe que as variáveis em comandos remotos foram criadas na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-341">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="e1a1f-342">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-342">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="e1a1f-343">Por exemplo, os comandos a seguir criam uma `$Cred` variável na sessão local e, em seguida, usam a `$Cred` variável em um comando remoto:</span><span class="sxs-lookup"><span data-stu-id="e1a1f-343">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="e1a1f-344">O escopo de uso foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-344">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="e1a1f-345">No PowerShell 2,0, para indicar que uma variável foi criada na sessão local, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="e1a1f-345">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="e1a1f-346">Confira também</span><span class="sxs-lookup"><span data-stu-id="e1a1f-346">See also</span></span>

[<span data-ttu-id="e1a1f-347">about_Variables</span><span class="sxs-lookup"><span data-stu-id="e1a1f-347">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="e1a1f-348">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="e1a1f-348">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="e1a1f-349">about_Functions</span><span class="sxs-lookup"><span data-stu-id="e1a1f-349">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="e1a1f-350">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="e1a1f-350">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="e1a1f-351">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="e1a1f-351">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)
