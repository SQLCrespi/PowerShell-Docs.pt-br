---
description: Variável
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Variable
ms.openlocfilehash: c58ec641db0902088bf931d8bf4a48f5f7fa2ab8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195598"
---
# <a name="variable-provider"></a><span data-ttu-id="2c456-104">Provedor de variáveis</span><span class="sxs-lookup"><span data-stu-id="2c456-104">Variable provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="2c456-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="2c456-105">Provider name</span></span>
<span data-ttu-id="2c456-106">Variável</span><span class="sxs-lookup"><span data-stu-id="2c456-106">Variable</span></span>

## <a name="drives"></a><span data-ttu-id="2c456-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="2c456-107">Drives</span></span>

`Variable:`

## <a name="capabilities"></a><span data-ttu-id="2c456-108">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="2c456-108">Capabilities</span></span>

<span data-ttu-id="2c456-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="2c456-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="2c456-110">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="2c456-110">Short description</span></span>

<span data-ttu-id="2c456-111">Fornece acesso às variáveis do PowerShell e aos seus valores.</span><span class="sxs-lookup"><span data-stu-id="2c456-111">Provides access to the PowerShell variables and to their values.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="2c456-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2c456-112">Detailed description</span></span>

<span data-ttu-id="2c456-113">O provedor de **variáveis** do PowerShell permite que você obtenha, adicione, altere, apague e exclua variáveis do PowerShell no console atual.</span><span class="sxs-lookup"><span data-stu-id="2c456-113">The PowerShell **Variable** provider lets you get, add, change, clear, and delete PowerShell variables in the current console.</span></span>

<span data-ttu-id="2c456-114">O provedor de **variáveis** do PowerShell dá suporte às variáveis que o PowerShell cria, incluindo as variáveis automáticas, as variáveis de preferência e as variáveis que você cria.</span><span class="sxs-lookup"><span data-stu-id="2c456-114">The PowerShell **Variable** provider supports the variables that PowerShell creates, including the automatic variables, the preference variables, and the variables that you create.</span></span>

<span data-ttu-id="2c456-115">A unidade **variável** é um namespace simples que contém apenas os objetos de variável.</span><span class="sxs-lookup"><span data-stu-id="2c456-115">The **Variable** drive is a flat namespace that contains only the variable objects.</span></span> <span data-ttu-id="2c456-116">As variáveis não possuem itens filho.</span><span class="sxs-lookup"><span data-stu-id="2c456-116">The variables have no child items.</span></span>

<span data-ttu-id="2c456-117">O provedor de **variáveis** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2c456-117">The **Variable** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="2c456-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="2c456-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="2c456-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="2c456-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="2c456-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="2c456-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="2c456-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="2c456-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="2c456-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2c456-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="2c456-123">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="2c456-123">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="2c456-124">O PowerShell também inclui um conjunto de cmdlets projetados especialmente para exibir e alterar variáveis.</span><span class="sxs-lookup"><span data-stu-id="2c456-124">PowerShell also includes a set of cmdlets designed especially to view and to change variables.</span></span> <span data-ttu-id="2c456-125">Quando você usa cmdlets **variáveis** , não é necessário especificar a `Variable:` unidade no nome.</span><span class="sxs-lookup"><span data-stu-id="2c456-125">When you use **Variable** cmdlets, you do not need to specify the `Variable:` drive in the name.</span></span> <span data-ttu-id="2c456-126">Este artigo não aborda o trabalho com cmdlets **variáveis** .</span><span class="sxs-lookup"><span data-stu-id="2c456-126">This article does not cover working with **Variable** cmdlets.</span></span>

- [<span data-ttu-id="2c456-127">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="2c456-127">Get-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [<span data-ttu-id="2c456-128">New-Variable</span><span class="sxs-lookup"><span data-stu-id="2c456-128">New-Variable</span></span>](xref:Microsoft.PowerShell.Utility.New-Variable)
- [<span data-ttu-id="2c456-129">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="2c456-129">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [<span data-ttu-id="2c456-130">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="2c456-130">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [<span data-ttu-id="2c456-131">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="2c456-131">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> <span data-ttu-id="2c456-132">Você também pode usar o analisador de expressão do PowerShell para criar, exibir e alterar os valores de variáveis sem usar os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2c456-132">You can also use the PowerShell expression parser to create, view, and change the values of variables without using the cmdlets.</span></span> <span data-ttu-id="2c456-133">Ao trabalhar com variáveis diretamente, use um sinal de cifrão ( `$` ) para identificar o nome como uma variável e o operador de atribuição ( `=` ) para estabelecer e alterar seu valor.</span><span class="sxs-lookup"><span data-stu-id="2c456-133">When working with variables directly, use a dollar sign (`$`) to identify the name as a variable and the assignment operator (`=`)to establish and change its value.</span></span> <span data-ttu-id="2c456-134">Por exemplo, `$p = Get-Process` cria a `p` variável e armazena os resultados de um `Get-Process` comando nela.</span><span class="sxs-lookup"><span data-stu-id="2c456-134">For example, `$p = Get-Process` creates the `p` variable and stores the results of a `Get-Process` command in it.</span></span>

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="2c456-135">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="2c456-135">Types exposed by this provider</span></span>

<span data-ttu-id="2c456-136">As variáveis podem ser um dos vários tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="2c456-136">Variables can be one of several different types.</span></span> <span data-ttu-id="2c456-137">A maioria das variáveis será instâncias da `PSVariable` classe.</span><span class="sxs-lookup"><span data-stu-id="2c456-137">Most variables will be instances of the `PSVariable` class.</span></span> <span data-ttu-id="2c456-138">Outras variáveis e seus tipos são listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="2c456-138">Other variables and their types are listed below.</span></span>

- <span data-ttu-id="2c456-139">A `?` variável é uma instância da `QuestionMarkVariable` classe.</span><span class="sxs-lookup"><span data-stu-id="2c456-139">The `?` variable is an instance of the `QuestionMarkVariable` class.</span></span>
- <span data-ttu-id="2c456-140">A `null` variável é uma instância da `NullVariable` classe.</span><span class="sxs-lookup"><span data-stu-id="2c456-140">The `null` variable is an instance of the `NullVariable` class.</span></span>
- <span data-ttu-id="2c456-141">As variáveis de contagem máxima são instâncias da `SessionStateCapacityVariable` classe.</span><span class="sxs-lookup"><span data-stu-id="2c456-141">The maximum count variables are instances of the `SessionStateCapacityVariable` class.</span></span>
- <span data-ttu-id="2c456-142">`LocalVariable` as instâncias contêm informações sobre a execução atual, como:</span><span class="sxs-lookup"><span data-stu-id="2c456-142">`LocalVariable` instances contain information about current execution, such as:</span></span>
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a><span data-ttu-id="2c456-143">Navegando pelas unidades variáveis</span><span class="sxs-lookup"><span data-stu-id="2c456-143">Navigating the Variable drives</span></span>

<span data-ttu-id="2c456-144">O provedor **variável** expõe seu armazenamento de dados na `Variable:` unidade.</span><span class="sxs-lookup"><span data-stu-id="2c456-144">The **Variable** provider exposes its data store in the `Variable:` drive.</span></span> <span data-ttu-id="2c456-145">Para trabalhar com variáveis, você pode alterar seu local para a `Variable:` unidade ( `Set-Location Variable:` ) ou pode trabalhar em qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c456-145">To work with variables, you can change your location to the `Variable:` drive (`Set-Location Variable:`), or you can work from any other PowerShell drive.</span></span> <span data-ttu-id="2c456-146">Para fazer referência a uma variável de outro local, use o nome da unidade ( `Variable:` ) no caminho.</span><span class="sxs-lookup"><span data-stu-id="2c456-146">To reference a variable from another location, use the drive name (`Variable:`) in the path.</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="2c456-147">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="2c456-147">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="2c456-148">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="2c456-148">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="2c456-149">Você também pode trabalhar com o provedor de **variáveis** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c456-149">You can also work with the **Variable** provider from any other PowerShell drive.</span></span> <span data-ttu-id="2c456-150">Para fazer referência a uma variável de outro local, use o nome da unidade `Variable:` no caminho.</span><span class="sxs-lookup"><span data-stu-id="2c456-150">To reference an variable from another location, use the drive name `Variable:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="2c456-151">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="2c456-151">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="2c456-152">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="2c456-152">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="2c456-153">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="2c456-153">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-value-of-variables"></a><span data-ttu-id="2c456-154">Exibindo o valor de variáveis</span><span class="sxs-lookup"><span data-stu-id="2c456-154">Displaying the value of variables</span></span>

### <a name="get-all-variables-in-the-current-session"></a><span data-ttu-id="2c456-155">Obter todas as variáveis na sessão atual</span><span class="sxs-lookup"><span data-stu-id="2c456-155">Get all variables in the current session</span></span>

<span data-ttu-id="2c456-156">Esse comando obtém a lista de todas as variáveis e seus valores na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2c456-156">This command gets the list of all the variables and their values in the current session.</span></span> <span data-ttu-id="2c456-157">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c456-157">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a><span data-ttu-id="2c456-158">Obter uma variável usando seu caminho de provedor</span><span class="sxs-lookup"><span data-stu-id="2c456-158">Get a variable using its provider path</span></span>

<span data-ttu-id="2c456-159">Esse comando recupera um valor de variáveis usando seu caminho de provedor prefixado pelo cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2c456-159">This command retrieves a variables value using its provider path prefixed by the dollar sign (`$`).</span></span> <span data-ttu-id="2c456-160">Isso tem o mesmo efeito que a prefixação do nome das variáveis com o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2c456-160">This has the same effect as prefixing the variables name with the dollar sign (`$`).</span></span>

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a><span data-ttu-id="2c456-161">Obter variáveis usando curingas</span><span class="sxs-lookup"><span data-stu-id="2c456-161">Get variables using wildcards</span></span>

<span data-ttu-id="2c456-162">Esse comando obtém as variáveis com nomes que começam com "max".</span><span class="sxs-lookup"><span data-stu-id="2c456-162">This command gets the variables with names that begin with "max".</span></span> <span data-ttu-id="2c456-163">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c456-163">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a><span data-ttu-id="2c456-164">Obter o valor do?</span><span class="sxs-lookup"><span data-stu-id="2c456-164">Get the value of the ?</span></span> <span data-ttu-id="2c456-165">variável</span><span class="sxs-lookup"><span data-stu-id="2c456-165">variable</span></span>

<span data-ttu-id="2c456-166">Esse comando usa o `-LiteralPath` parâmetro de [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) para obter o valor da `?` variável de dentro da `Variable:` unidade.</span><span class="sxs-lookup"><span data-stu-id="2c456-166">This command uses the `-LiteralPath` parameter of [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) to get the value of the `?` variable from within the `Variable:` drive.</span></span> <span data-ttu-id="2c456-167">O `?` é um caractere curinga em caminhos, mas `Get-ChildItem` não tenta resolver nenhum caractere curinga nos valores do `-LiteralPath` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2c456-167">The `?` is a wildcard in paths, but `Get-ChildItem` does not attempt to resolve any wildcards in the values of the `-LiteralPath` parameter.</span></span>

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a><span data-ttu-id="2c456-168">Obter variáveis ReadOnly e constantes</span><span class="sxs-lookup"><span data-stu-id="2c456-168">Get ReadOnly and Constant variables</span></span>

<span data-ttu-id="2c456-169">Esse comando obtém as variáveis que têm os valores de `ReadOnly` ou `Constant` para suas propriedades de **Opções** .</span><span class="sxs-lookup"><span data-stu-id="2c456-169">This command gets the variables that have the values of `ReadOnly` or `Constant` for their **Options** property.</span></span>

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a><span data-ttu-id="2c456-170">Criando variáveis</span><span class="sxs-lookup"><span data-stu-id="2c456-170">Creating variables</span></span>

### <a name="create-a-new-variable"></a><span data-ttu-id="2c456-171">Criar uma nova variável</span><span class="sxs-lookup"><span data-stu-id="2c456-171">Create a new variable</span></span>

<span data-ttu-id="2c456-172">Esse comando cria a `services` variável e armazena os resultados de um `Get-Service` comando nela.</span><span class="sxs-lookup"><span data-stu-id="2c456-172">This command creates the `services` variable and stores the results of a `Get-Service` command in it.</span></span> <span data-ttu-id="2c456-173">Como o local atual está na `Variable:` unidade, o valor do `-Path` parâmetro é um ponto ( `.` ), que representa o local atual.</span><span class="sxs-lookup"><span data-stu-id="2c456-173">Because the current location is in the `Variable:` drive, the value of the `-Path` parameter is a dot (`.`), which represents the current location.</span></span>

<span data-ttu-id="2c456-174">Os parênteses em volta do `Get-Service` comando garantem que o comando seja executado antes de a variável ser criada.</span><span class="sxs-lookup"><span data-stu-id="2c456-174">The parentheses around the `Get-Service` command ensure that the command is executed before the variable is created.</span></span> <span data-ttu-id="2c456-175">Sem os parênteses, o valor da nova variável é uma cadeia de caracteres "Get-Service".</span><span class="sxs-lookup"><span data-stu-id="2c456-175">Without the parentheses, the value of the new variable is a "Get-Service" string.</span></span>

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a><span data-ttu-id="2c456-176">Criar uma variável usando um caminho absoluto</span><span class="sxs-lookup"><span data-stu-id="2c456-176">Create a variable using an absolute path</span></span>

<span data-ttu-id="2c456-177">Esse comando cria uma `services` variável e armazena o resultado de um `Get-Service` comando nela.</span><span class="sxs-lookup"><span data-stu-id="2c456-177">This command creates a `services` variable and stores the result of a `Get-Service` command in it.</span></span>

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 <span data-ttu-id="2c456-178">Para criar uma variável sem um valor, omita o operador de atribuição.</span><span class="sxs-lookup"><span data-stu-id="2c456-178">To create a variable without a value, omit the assignment operator.</span></span>

## <a name="changing-variables"></a><span data-ttu-id="2c456-179">Alterando variáveis</span><span class="sxs-lookup"><span data-stu-id="2c456-179">Changing variables</span></span>

### <a name="rename-a-variable"></a><span data-ttu-id="2c456-180">Renomear uma variável</span><span class="sxs-lookup"><span data-stu-id="2c456-180">Rename a variable</span></span>

<span data-ttu-id="2c456-181">Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `a` variável para `processes` .</span><span class="sxs-lookup"><span data-stu-id="2c456-181">This command uses the `Rename-Item` cmdlet to change the name of the `a` variable to `processes`.</span></span>

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a><span data-ttu-id="2c456-182">Alterar o valor de uma variável</span><span class="sxs-lookup"><span data-stu-id="2c456-182">Change the value of a variable</span></span>

<span data-ttu-id="2c456-183">Esse comando usa o `Set-Item` cmdlet para alterar o valor da `ErrorActionPreference` variável para "Stop".</span><span class="sxs-lookup"><span data-stu-id="2c456-183">This command uses the `Set-Item` cmdlet to change the value of the `ErrorActionPreference` variable to "Stop".</span></span>

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a><span data-ttu-id="2c456-184">Copiar uma variável</span><span class="sxs-lookup"><span data-stu-id="2c456-184">Copy a variable</span></span>

<span data-ttu-id="2c456-185">Esse comando usa o `Copy-Item` cmdlet para copiar a `processes` variável para `old_processes` .</span><span class="sxs-lookup"><span data-stu-id="2c456-185">This command uses the `Copy-Item` cmdlet to copy the `processes` variable to `old_processes`.</span></span> <span data-ttu-id="2c456-186">Isso cria uma nova variável chamada `old_processes` que tem o mesmo valor que a `processes` variável.</span><span class="sxs-lookup"><span data-stu-id="2c456-186">This creates a new variable named `old_processes` that has the same value as the `processes` variable.</span></span>

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a><span data-ttu-id="2c456-187">Excluir uma variável</span><span class="sxs-lookup"><span data-stu-id="2c456-187">Delete a variable</span></span>

<span data-ttu-id="2c456-188">Esse comando exclui a `serv` variável da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2c456-188">This command deletes the `serv` variable from the current session.</span></span> <span data-ttu-id="2c456-189">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c456-189">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a><span data-ttu-id="2c456-190">Excluir variáveis usando o parâmetro-Force</span><span class="sxs-lookup"><span data-stu-id="2c456-190">Delete variables using the -Force parameter</span></span>

<span data-ttu-id="2c456-191">Esse comando exclui todas as variáveis da sessão atual, exceto pelas variáveis cuja propriedade **Options** tem um valor de `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2c456-191">This command deletes all variables from the current session except for the variables whose **Options** property has a value of `Constant`.</span></span> <span data-ttu-id="2c456-192">Sem o `-Force` parâmetro, o comando não exclui variáveis cuja propriedade **Options** tem um valor de `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="2c456-192">Without the `-Force` parameter, the command does not delete variables whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a><span data-ttu-id="2c456-193">Definindo o valor de uma variável como NULL</span><span class="sxs-lookup"><span data-stu-id="2c456-193">Setting the value of a variable to NULL</span></span>

<span data-ttu-id="2c456-194">Esse comando usa o `Clear-Item` cmdlet para alterar o valor da `processes` variável para NULL.</span><span class="sxs-lookup"><span data-stu-id="2c456-194">This command uses the `Clear-Item` cmdlet to change the value of the `processes` variable to NULL.</span></span>

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a><span data-ttu-id="2c456-195">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="2c456-195">Using the pipeline</span></span>

<span data-ttu-id="2c456-196">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c456-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="2c456-197">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="2c456-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="2c456-198">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2c456-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="2c456-199">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="2c456-199">Getting help</span></span>

<span data-ttu-id="2c456-200">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2c456-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="2c456-201">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2c456-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a><span data-ttu-id="2c456-202">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c456-202">See also</span></span>

[<span data-ttu-id="2c456-203">about_Variables</span><span class="sxs-lookup"><span data-stu-id="2c456-203">about_Variables</span></span>](../About/about_Variables.md)

[<span data-ttu-id="2c456-204">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="2c456-204">about_Automatic_Variables</span></span>](../About/about_Automatic_Variables.md)

[<span data-ttu-id="2c456-205">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2c456-205">about_Providers</span></span>](../About/about_Providers.md)
