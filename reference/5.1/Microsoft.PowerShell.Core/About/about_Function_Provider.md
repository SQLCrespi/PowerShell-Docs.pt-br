---
description: Função
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Function
ms.openlocfilehash: ac2f09c6352f936a0b0fece108e87e3fe15b5998
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196020"
---
# <a name="function-provider"></a><span data-ttu-id="ac38a-104">Provedor de funções</span><span class="sxs-lookup"><span data-stu-id="ac38a-104">Function provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="ac38a-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="ac38a-105">Provider name</span></span>

<span data-ttu-id="ac38a-106">Função</span><span class="sxs-lookup"><span data-stu-id="ac38a-106">Function</span></span>

## <a name="drives"></a><span data-ttu-id="ac38a-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="ac38a-107">Drives</span></span>

`Function:`

## <a name="capabilities"></a><span data-ttu-id="ac38a-108">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="ac38a-108">Capabilities</span></span>

<span data-ttu-id="ac38a-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="ac38a-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="ac38a-110">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="ac38a-110">Short description</span></span>

<span data-ttu-id="ac38a-111">Fornece acesso às funções definidas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-111">Provides access to the functions defined in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="ac38a-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="ac38a-112">Detailed description</span></span>

<span data-ttu-id="ac38a-113">O provedor de **funções** do PowerShell permite que você obtenha, adicione, altere, apague e exclua as funções e os filtros no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-113">The PowerShell **Function** provider lets you get, add, change, clear, and delete the functions and filters in PowerShell.</span></span>

<span data-ttu-id="ac38a-114">Uma função é um bloco nomeado de código que executa uma ação.</span><span class="sxs-lookup"><span data-stu-id="ac38a-114">A function is a named block of code that performs an action.</span></span> <span data-ttu-id="ac38a-115">Quando você digita o nome da função, o código na função é executado.</span><span class="sxs-lookup"><span data-stu-id="ac38a-115">When you type the function name, the code in the function runs.</span></span> <span data-ttu-id="ac38a-116">Um filtro é um bloco de código nomeado que estabelece as condições para uma ação.</span><span class="sxs-lookup"><span data-stu-id="ac38a-116">A filter is a named block of code that establishes conditions for an action.</span></span> <span data-ttu-id="ac38a-117">Você pode digitar o nome do filtro no lugar da condição, como em um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="ac38a-117">You can type the name of the filter in place of the condition, such as in a `Where-Object` command.</span></span>

<span data-ttu-id="ac38a-118">A unidade de **função** é um namespace simples que contém apenas os objetos de função e de filtro.</span><span class="sxs-lookup"><span data-stu-id="ac38a-118">The **Function** drive is a flat namespace that contains only the function and filter objects.</span></span> <span data-ttu-id="ac38a-119">Nem funções nem filtros possuem itens filhos.</span><span class="sxs-lookup"><span data-stu-id="ac38a-119">Neither functions nor filters have child items.</span></span>

<span data-ttu-id="ac38a-120">O provedor de **funções** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ac38a-120">The **Function** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="ac38a-121">Get-Location</span><span class="sxs-lookup"><span data-stu-id="ac38a-121">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="ac38a-122">Set-Location</span><span class="sxs-lookup"><span data-stu-id="ac38a-122">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="ac38a-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-123">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="ac38a-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="ac38a-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="ac38a-126">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-126">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="ac38a-127">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="ac38a-127">Types exposed by this provider</span></span>

<span data-ttu-id="ac38a-128">Cada função é uma instância da classe [System. Management. Automation. FunctionInfo](/dotnet/api/system.management.automation.functioninfo) .</span><span class="sxs-lookup"><span data-stu-id="ac38a-128">Each function is an instance of the [System.Management.Automation.FunctionInfo](/dotnet/api/system.management.automation.functioninfo) class.</span></span> <span data-ttu-id="ac38a-129">Cada filtro é uma instância da classe [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) .</span><span class="sxs-lookup"><span data-stu-id="ac38a-129">Each filter is an instance of the [System.Management.Automation.FilterInfo](/dotnet/api/system.management.automation.filterinfo) class.</span></span>

## <a name="navigating-the-function-drive"></a><span data-ttu-id="ac38a-130">Navegando pela unidade de função</span><span class="sxs-lookup"><span data-stu-id="ac38a-130">Navigating the Function drive</span></span>

<span data-ttu-id="ac38a-131">O provedor de **funções** expõe seu armazenamento de dados na `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-131">The **Function** provider exposes its data store in the `Function:` drive.</span></span> <span data-ttu-id="ac38a-132">Para trabalhar com funções, você pode alterar seu local para a `Function:` unidade ( `Set-Location Function:` ).</span><span class="sxs-lookup"><span data-stu-id="ac38a-132">To work with functions, you can change your location to the `Function:` drive (`Set-Location Function:`).</span></span> <span data-ttu-id="ac38a-133">Ou, você pode trabalhar de outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-133">Or, you can work from another PowerShell drive.</span></span> <span data-ttu-id="ac38a-134">Para fazer referência a uma função de outro local, use o nome da unidade ( `Function:` ) no caminho.</span><span class="sxs-lookup"><span data-stu-id="ac38a-134">To reference a function from another location, use the drive name (`Function:`) in the path.</span></span>

```powershell
Set-Location Function:
```

<span data-ttu-id="ac38a-135">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-135">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="ac38a-136">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="ac38a-136">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="ac38a-137">Você também pode trabalhar com o provedor de **funções** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-137">You can also work with the **Function** provider from any other PowerShell drive.</span></span> <span data-ttu-id="ac38a-138">Para fazer referência a uma função de outro local, use o nome da unidade `Function:` no caminho.</span><span class="sxs-lookup"><span data-stu-id="ac38a-138">To reference an function from another location, use the drive name `Function:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="ac38a-139">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="ac38a-139">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="ac38a-140">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="ac38a-140">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="ac38a-141">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="ac38a-141">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-functions"></a><span data-ttu-id="ac38a-142">Obtendo funções</span><span class="sxs-lookup"><span data-stu-id="ac38a-142">Getting functions</span></span>

<span data-ttu-id="ac38a-143">Esse comando obtém a lista de todas as funções na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ac38a-143">This command gets the list of all the functions in the current session.</span></span> <span data-ttu-id="ac38a-144">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-144">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="ac38a-145">O provedor de funções não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-145">The Function provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="ac38a-146">Você pode recuperar a definição de uma função acessando a propriedade **definição** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="ac38a-146">You can retrieve a function's definition by accessing the **Definition** property, as shown below.</span></span>

```powershell
(Get-Item -Path function:more).Definition
```

<span data-ttu-id="ac38a-147">Você também pode recuperar a definição de uma função usando seu caminho de provedor prefixado pelo cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="ac38a-147">You can also retrieve a function's definition using its provider path prefixed by the dollar sign (`$`).</span></span>

```powershell
$function:more
```

### <a name="getting-selected-functions"></a><span data-ttu-id="ac38a-148">Obtendo funções selecionadas</span><span class="sxs-lookup"><span data-stu-id="ac38a-148">Getting selected functions</span></span>

<span data-ttu-id="ac38a-149">Esse comando obtém a `man` função da `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-149">This command gets the `man` function from the `Function:` drive.</span></span> <span data-ttu-id="ac38a-150">Ele usa o `Get-Item` cmdlet para obter a função.</span><span class="sxs-lookup"><span data-stu-id="ac38a-150">It uses the `Get-Item` cmdlet to get the function.</span></span> <span data-ttu-id="ac38a-151">O operador de pipeline ( `|` ) envia o resultado para `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-151">The pipeline operator (`|`) sends the result to `Format-Table`.</span></span> <span data-ttu-id="ac38a-152">O `-Wrap` parâmetro direciona o texto que não cabe na linha para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="ac38a-152">The `-Wrap` parameter directs text that does not fit on the line onto the next line.</span></span> <span data-ttu-id="ac38a-153">O `-Autosize` parâmetro redimensiona as colunas da tabela para acomodar o texto.</span><span class="sxs-lookup"><span data-stu-id="ac38a-153">The `-Autosize` parameter resizes the table columns to accommodate the text.</span></span>

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a><span data-ttu-id="ac38a-154">Trabalhando com caminhos de provedor de funções</span><span class="sxs-lookup"><span data-stu-id="ac38a-154">Working with Function provider paths</span></span>

<span data-ttu-id="ac38a-155">Esses comandos obtêm a função chamada `c:` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-155">These commands both get the function named `c:`.</span></span> <span data-ttu-id="ac38a-156">O primeiro comando pode ser usado em qualquer unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-156">The first command can be used in any drive.</span></span> <span data-ttu-id="ac38a-157">O segundo comando é usado na `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-157">The second command is used in the `Function:` drive.</span></span> <span data-ttu-id="ac38a-158">Como o nome termina com dois-pontos, que é a sintaxe para uma unidade, você deve qualificar o caminho com o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-158">Because the name ends in a colon, which is the syntax for a drive, you must qualify the path with the drive name.</span></span> <span data-ttu-id="ac38a-159">Dentro da `Function:` unidade, você pode usar qualquer um dos formatos.</span><span class="sxs-lookup"><span data-stu-id="ac38a-159">Within the `Function:` drive, you can use either format.</span></span> <span data-ttu-id="ac38a-160">No segundo comando, o ponto ( `.` ) representa o local atual.</span><span class="sxs-lookup"><span data-stu-id="ac38a-160">In the second command, the dot (`.`) represents the current location.</span></span>

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a><span data-ttu-id="ac38a-161">Criando uma função</span><span class="sxs-lookup"><span data-stu-id="ac38a-161">Creating a function</span></span>

<span data-ttu-id="ac38a-162">Esse comando usa o `New-Item` cmdlet para criar uma função chamada `Win32:` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-162">This command uses the `New-Item` cmdlet to create a function called `Win32:`.</span></span>
<span data-ttu-id="ac38a-163">A expressão entre chaves é o bloco de script que é representado pelo nome da função.</span><span class="sxs-lookup"><span data-stu-id="ac38a-163">The expression in braces is the script block that is represented by the function name.</span></span>

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

<span data-ttu-id="ac38a-164">Você também pode criar uma função digitando-a na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac38a-164">You can also create a function by typing it at the PowerShell command line.</span></span> <span data-ttu-id="ac38a-165">Por exemplo, TPE `Function:Win32: {Set-Location C:\Windows\System32}` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-165">For example, tpe `Function:Win32: {Set-Location C:\Windows\System32}`.</span></span> <span data-ttu-id="ac38a-166">Se você estiver na `Function:` unidade, poderá omitir o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="ac38a-166">If you are in the `Function:` drive, you can omit the drive name.</span></span>

## <a name="deleting-a-function"></a><span data-ttu-id="ac38a-167">Excluindo uma função</span><span class="sxs-lookup"><span data-stu-id="ac38a-167">Deleting a function</span></span>

<span data-ttu-id="ac38a-168">Este comando exclui a `more:` função da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ac38a-168">This command deletes the `more:` function from the current session.</span></span>

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a><span data-ttu-id="ac38a-169">Alterando uma função</span><span class="sxs-lookup"><span data-stu-id="ac38a-169">Changing a function</span></span>

<span data-ttu-id="ac38a-170">Esse comando usa o `Set-Item` cmdlet para alterar a `prompt` função para que ela exiba a hora antes do caminho.</span><span class="sxs-lookup"><span data-stu-id="ac38a-170">This command uses the `Set-Item` cmdlet to change the `prompt` function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a><span data-ttu-id="ac38a-171">Renomear uma função</span><span class="sxs-lookup"><span data-stu-id="ac38a-171">Rename a function</span></span>

<span data-ttu-id="ac38a-172">Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `help` função para `gh` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-172">This command uses the `Rename-Item` cmdlet to change the name of the `help` function to `gh`.</span></span>

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a><span data-ttu-id="ac38a-173">Copiando uma função</span><span class="sxs-lookup"><span data-stu-id="ac38a-173">Copying a function</span></span>

<span data-ttu-id="ac38a-174">Esse comando copia a `prompt` função para `oldPrompt` , criando efetivamente um novo nome para o bloco de script que está associado à função de prompt.</span><span class="sxs-lookup"><span data-stu-id="ac38a-174">This command copies the `prompt` function to `oldPrompt`, effectively creating a new name for the script block that is associated with the prompt function.</span></span>
<span data-ttu-id="ac38a-175">Você pode usar isso para salvar a função de prompt original se quiser alterá-la.</span><span class="sxs-lookup"><span data-stu-id="ac38a-175">You can use this to save the original prompt function if you plan to change it.</span></span>
<span data-ttu-id="ac38a-176">A propriedade **Options** da nova função tem um valor de `None` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-176">The **Options** property of the new function has a value of `None`.</span></span> <span data-ttu-id="ac38a-177">Para alterar o valor da propriedade **Options** , use `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-177">To change the value of the **Options** property, use `Set-Item`.</span></span>

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a><span data-ttu-id="ac38a-178">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="ac38a-178">Dynamic parameters</span></span>

<span data-ttu-id="ac38a-179">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="ac38a-179">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="ac38a-180">Opções < [System. Management. Automation. ScopedItemOptions] ></span><span class="sxs-lookup"><span data-stu-id="ac38a-180">Options <[System.Management.Automation.ScopedItemOptions]></span></span>

<span data-ttu-id="ac38a-181">Determina o valor da propriedade **Options** de uma função.</span><span class="sxs-lookup"><span data-stu-id="ac38a-181">Determines the value of the **Options** property of a function.</span></span>

- <span data-ttu-id="ac38a-182">`None`: Nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="ac38a-182">`None`: No options.</span></span> <span data-ttu-id="ac38a-183">`None` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="ac38a-183">`None` is the default.</span></span>
- <span data-ttu-id="ac38a-184">`Constant`: A função não pode ser excluída e suas propriedades não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="ac38a-184">`Constant`: The function cannot be deleted, and its properties cannot be changed.</span></span> <span data-ttu-id="ac38a-185">`Constant` está disponível somente quando você está criando uma função.</span><span class="sxs-lookup"><span data-stu-id="ac38a-185">`Constant` is available only when you are creating a function.</span></span>
  <span data-ttu-id="ac38a-186">Você não pode alterar a opção de uma função existente para `Constant` .</span><span class="sxs-lookup"><span data-stu-id="ac38a-186">You cannot change the option of an existing function to `Constant`.</span></span>
- <span data-ttu-id="ac38a-187">`Private`: A função é visível somente no escopo atual</span><span class="sxs-lookup"><span data-stu-id="ac38a-187">`Private`: The function is visible only in the current scope</span></span>
- <span data-ttu-id="ac38a-188">(não em escopos filho).</span><span class="sxs-lookup"><span data-stu-id="ac38a-188">(not in child scopes).</span></span>
- <span data-ttu-id="ac38a-189">`ReadOnly`: As propriedades da função não podem ser alteradas, exceto usando o `-Force` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ac38a-189">`ReadOnly`: The properties of the function cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="ac38a-190">Você pode usar `Remove-Item` para excluir a função.</span><span class="sxs-lookup"><span data-stu-id="ac38a-190">You can use `Remove-Item` to delete the function.</span></span>
- <span data-ttu-id="ac38a-191">`AllScope`: A função é copiada para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="ac38a-191">`AllScope`: The function is copied to any new scopes that are created.</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="ac38a-192">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="ac38a-192">Cmdlets supported</span></span>

- [<span data-ttu-id="ac38a-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-193">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

- [<span data-ttu-id="ac38a-194">Set-Item</span><span class="sxs-lookup"><span data-stu-id="ac38a-194">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="ac38a-195">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="ac38a-195">Using the pipeline</span></span>

<span data-ttu-id="ac38a-196">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="ac38a-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="ac38a-197">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="ac38a-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="ac38a-198">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ac38a-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="ac38a-199">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="ac38a-199">Getting help</span></span>

<span data-ttu-id="ac38a-200">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ac38a-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="ac38a-201">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ac38a-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a><span data-ttu-id="ac38a-202">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac38a-202">See also</span></span>

[<span data-ttu-id="ac38a-203">about_Functions</span><span class="sxs-lookup"><span data-stu-id="ac38a-203">about_Functions</span></span>](../About/about_Functions.md)

[<span data-ttu-id="ac38a-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ac38a-204">about_Providers</span></span>](../About/about_Providers.md)
