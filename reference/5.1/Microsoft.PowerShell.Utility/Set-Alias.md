---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 3c3e95058ff150666c9db9e84d9a6fce38fc74bb
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274231"
---
# <span data-ttu-id="9ddc2-103">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="9ddc2-103">Set-Alias</span></span>

## <span data-ttu-id="9ddc2-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="9ddc2-104">Synopsis</span></span>
<span data-ttu-id="9ddc2-105">Cria ou altera um alias para um cmdlet ou outro comando na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-105">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="9ddc2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ddc2-106">Syntax</span></span>

### <span data-ttu-id="9ddc2-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="9ddc2-107">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9ddc2-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ddc2-108">Description</span></span>

<span data-ttu-id="9ddc2-109">O `Set-Alias` cmdlet cria ou altera um alias para um cmdlet ou um comando, como uma função, script, arquivo ou outro executável.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-109">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="9ddc2-110">Um alias é um nome alternativo que se refere a um cmdlet ou comando.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-110">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="9ddc2-111">Por exemplo, `sal` é o alias para o `Set-Alias` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-111">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="9ddc2-112">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="9ddc2-112">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="9ddc2-113">Um cmdlet pode ter vários aliases, mas um alias só pode ser associado a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-113">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="9ddc2-114">Você pode usar `Set-Alias` para reatribuir um alias existente a outro cmdlet ou alterar as propriedades de um alias, como a descrição.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-114">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="9ddc2-115">Um alias que é criado ou alterado pelo `Set-Alias` não é permanente e só está disponível durante a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-115">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="9ddc2-116">Quando a sessão do PowerShell é fechada, o alias é removido.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-116">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="9ddc2-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9ddc2-117">Examples</span></span>

### <span data-ttu-id="9ddc2-118">Exemplo 1: criar um alias para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ddc2-118">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="9ddc2-119">Este comando cria um alias para um cmdlet na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-119">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="9ddc2-120">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-120">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="9ddc2-121">O parâmetro **Name** especifica o nome do alias, `list` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-121">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="9ddc2-122">O parâmetro **Value** especifica o cmdlet que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-122">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="9ddc2-123">Para executar o alias, digite `list` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-123">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="9ddc2-124">Exemplo 2: Reatribuir um alias existente a um cmdlet diferente</span><span class="sxs-lookup"><span data-stu-id="9ddc2-124">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="9ddc2-125">Esse comando reatribui um alias existente para executar um cmdlet diferente.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-125">This command reassigns an existing alias to run a different cmdlet.</span></span>

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

<span data-ttu-id="9ddc2-126">O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-126">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="9ddc2-127">O `list` alias está associado ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-127">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="9ddc2-128">Quando o `list` alias é executado, os itens no diretório atual são exibidos.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-128">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="9ddc2-129">O `Set-Alias` cmdlet usa o parâmetro **Name** para especificar o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-129">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="9ddc2-130">O parâmetro **Value** associa o alias ao `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-130">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="9ddc2-131">O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-131">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="9ddc2-132">O `list` alias está associado ao `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-132">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="9ddc2-133">Quando o `list` alias é executado, o local do diretório atual é exibido.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-133">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="9ddc2-134">Exemplo 3: criar e alterar um alias somente leitura</span><span class="sxs-lookup"><span data-stu-id="9ddc2-134">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="9ddc2-135">Este comando cria um alias somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-135">This command creates a read-only alias.</span></span> <span data-ttu-id="9ddc2-136">A opção somente leitura impede alterações involuntárias em um alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-136">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="9ddc2-137">Para alterar ou excluir um alias somente leitura, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-137">To change or delete a read-only alias, use the **Force** parameter.</span></span>

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

<span data-ttu-id="9ddc2-138">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-138">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="9ddc2-139">O parâmetro **Name** especifica o nome do alias, `loc` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-139">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="9ddc2-140">O parâmetro **Value** especifica o `Get-Location` cmdlet que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-140">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="9ddc2-141">O parâmetro **Option** especifica o valor **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-141">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="9ddc2-142">O parâmetro **PassThru** representa o objeto alias e envia o objeto por meio do pipeline para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-142">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="9ddc2-143">`Format-List` usa o parâmetro **Property** com um asterisco ( `*` ) para que todas as propriedades sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-143">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="9ddc2-144">A saída de exemplo mostra uma lista parcial dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-144">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="9ddc2-145">O `loc` alias é alterado com a adição de dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-145">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="9ddc2-146">**Descrição** adiciona texto para explicar a finalidade do alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-146">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="9ddc2-147">O parâmetro **Force** é necessário porque o `loc` alias é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-147">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="9ddc2-148">Se o parâmetro **Force** não for usado, a alteração falhará.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-148">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="9ddc2-149">Exemplo 4: criar um alias para um arquivo executável</span><span class="sxs-lookup"><span data-stu-id="9ddc2-149">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="9ddc2-150">Este exemplo cria um alias para um arquivo executável no computador local.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-150">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="9ddc2-151">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-151">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="9ddc2-152">O parâmetro **Name** especifica o nome do alias, `np` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-152">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="9ddc2-153">O parâmetro **Value** especifica o caminho e o nome do aplicativo **C:\Windows\notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-153">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="9ddc2-154">O `Get-Alias` cmdlet usa o parâmetro **Name** para mostrar que o `np` alias está associado a **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-154">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="9ddc2-155">Para executar o alias, digite `np` na linha de comando do PowerShell para abrir **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-155">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="9ddc2-156">Exemplo 5: criar um alias para um comando com parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ddc2-156">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="9ddc2-157">Este exemplo mostra como atribuir um alias a um comando com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-157">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="9ddc2-158">Você pode criar um alias para um cmdlet, como `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-158">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="9ddc2-159">Você não pode criar um alias para um comando com parâmetros e valores, como `Set-Location -Path C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-159">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="9ddc2-160">Para criar um alias para um comando, crie uma função que inclua o comando e, em seguida, crie um alias para a função.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-160">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="9ddc2-161">Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="9ddc2-161">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
Function CD32 {Set-Location -Path C:\Windows\System32}

Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="9ddc2-162">Uma função chamada `CD32` é criada.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-162">A function named `CD32` is created.</span></span> <span data-ttu-id="9ddc2-163">A função usa o `Set-Location` cmdlet com o parâmetro **Path** para especificar o diretório, `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-163">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, `C:\Windows\System32`.</span></span>

<span data-ttu-id="9ddc2-164">O `Set-Alias` cmdlet cria um alias para a função na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-164">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="9ddc2-165">O parâmetro **Name** especifica o nome do alias, `Go` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-165">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="9ddc2-166">O parâmetro **Value** especifica o nome da função, `CD32` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-166">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="9ddc2-167">Para executar o alias, digite `Go` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-167">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="9ddc2-168">A `CD32` função é executada e muda para o diretório `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-168">The `CD32` function runs and changes to the directory `C:\Windows\System32`.</span></span>

### <span data-ttu-id="9ddc2-169">Exemplo 6: atualizar opções para um alias existente</span><span class="sxs-lookup"><span data-stu-id="9ddc2-169">Example 6: Update options for an existing alias</span></span>

<span data-ttu-id="9ddc2-170">Este exemplo mostra como atribuir várias opções usando o parâmetro **Option** .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-170">This example shows how to assign multiple options using the **Option** parameter.</span></span>

<span data-ttu-id="9ddc2-171">Usando o exemplo acima, definiremos o alias `Go` como `ReadOnly` e `Private` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-171">Using the example above we will set the alias `Go` as `ReadOnly` and `Private`.</span></span>

```powershell
Set-Alias -Name Go -Option ReadOnly, Private
```

<span data-ttu-id="9ddc2-172">O alias `Go` já deve existir.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-172">The alias `Go` should already exist.</span></span> <span data-ttu-id="9ddc2-173">Depois de executar o comando acima, o alias não poderá ser alterado sem usar o parâmetro **Force** e só estará disponível no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-173">After running the command above, the alias is not be able to be changed without using the **Force** parameter and is only available in the current scope.</span></span>

## <span data-ttu-id="9ddc2-174">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ddc2-174">Parameters</span></span>

### <span data-ttu-id="9ddc2-175">-Description</span><span class="sxs-lookup"><span data-stu-id="9ddc2-175">-Description</span></span>

<span data-ttu-id="9ddc2-176">Especifica uma descrição do alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-176">Specifies a description of the alias.</span></span> <span data-ttu-id="9ddc2-177">Você pode digitar qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-177">You can type any string.</span></span> <span data-ttu-id="9ddc2-178">Se a descrição incluir espaços, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-178">If the description includes spaces, enclose it single quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-179">-Force</span><span class="sxs-lookup"><span data-stu-id="9ddc2-179">-Force</span></span>

<span data-ttu-id="9ddc2-180">Use o parâmetro **Force** para alterar ou excluir um alias que tenha o parâmetro **Option** definido como **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-180">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="9ddc2-181">O parâmetro **Force** não pode alterar nem excluir um alias com o parâmetro **Option** definido como **Constant**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-181">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-182">-Name</span><span class="sxs-lookup"><span data-stu-id="9ddc2-182">-Name</span></span>

<span data-ttu-id="9ddc2-183">Especifica o nome de um novo alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-183">Specifies the name of a new alias.</span></span> <span data-ttu-id="9ddc2-184">Um nome de alias pode conter caracteres alfanuméricos e hifens.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-184">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="9ddc2-185">Nomes de alias não podem ser numéricos, como 123.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-185">Alias names cannot be numeric, such as 123.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-186">-Opção</span><span class="sxs-lookup"><span data-stu-id="9ddc2-186">-Option</span></span>

<span data-ttu-id="9ddc2-187">Define o valor da propriedade de **opção** do alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-187">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="9ddc2-188">Valores como `ReadOnly` e `Constant` protegem um alias de alterações involuntárias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-188">Values such as `ReadOnly` and `Constant` protect an alias from unintended changes.</span></span> <span data-ttu-id="9ddc2-189">Para ver a propriedade **Option** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-189">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="9ddc2-190">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9ddc2-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9ddc2-191">`AllScope` -O alias é copiado para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-191">`AllScope` - The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="9ddc2-192">`Constant` -Não pode ser alterado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-192">`Constant` - Cannot be changed or deleted.</span></span>
- <span data-ttu-id="9ddc2-193">`None` -Não define opções e é o padrão.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-193">`None` - Sets no options and is the default.</span></span>
- <span data-ttu-id="9ddc2-194">`Private` -O alias está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-194">`Private` - The alias is available only in the current scope.</span></span>
- <span data-ttu-id="9ddc2-195">`ReadOnly` -Não pode ser alterado ou excluído, a menos que o parâmetro **Force** seja usado.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-195">`ReadOnly` - Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- `Unspecified`

<span data-ttu-id="9ddc2-196">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-196">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="9ddc2-197">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-197">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="9ddc2-198">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-198">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="9ddc2-199">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-199">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="9ddc2-200">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-200">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9ddc2-201">-PassThru</span></span>

<span data-ttu-id="9ddc2-202">Retorna um objeto que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-202">Returns an object that represents the alias.</span></span> <span data-ttu-id="9ddc2-203">Use um cmdlet Format como `Format-List` para exibir o objeto.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-203">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="9ddc2-204">Por padrão, `Set-Alias` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-204">By default, `Set-Alias` does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-205">-Escopo</span><span class="sxs-lookup"><span data-stu-id="9ddc2-205">-Scope</span></span>

<span data-ttu-id="9ddc2-206">Especifica o escopo no qual esse alias é válido.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-206">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="9ddc2-207">O valor padrão é **local**.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-207">The default value is **Local**.</span></span> <span data-ttu-id="9ddc2-208">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="9ddc2-208">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="9ddc2-209">Os valores aceitáveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9ddc2-209">The acceptable values are as follows:</span></span>

- <span data-ttu-id="9ddc2-210">Global</span><span class="sxs-lookup"><span data-stu-id="9ddc2-210">Global</span></span>
- <span data-ttu-id="9ddc2-211">Local</span><span class="sxs-lookup"><span data-stu-id="9ddc2-211">Local</span></span>
- <span data-ttu-id="9ddc2-212">Privados</span><span class="sxs-lookup"><span data-stu-id="9ddc2-212">Private</span></span>
- <span data-ttu-id="9ddc2-213">Escopos numerados</span><span class="sxs-lookup"><span data-stu-id="9ddc2-213">Numbered scopes</span></span>
- <span data-ttu-id="9ddc2-214">Script</span><span class="sxs-lookup"><span data-stu-id="9ddc2-214">Script</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-215">-Value</span><span class="sxs-lookup"><span data-stu-id="9ddc2-215">-Value</span></span>

<span data-ttu-id="9ddc2-216">Especifica o nome do cmdlet ou comando que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-216">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="9ddc2-217">O parâmetro de **valor** é a propriedade de **definição** do alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-217">The **Value** parameter is the alias's **Definition** property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-218">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9ddc2-218">-Confirm</span></span>

<span data-ttu-id="9ddc2-219">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-219">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-220">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9ddc2-220">-WhatIf</span></span>

<span data-ttu-id="9ddc2-221">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-221">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9ddc2-222">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-222">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ddc2-223">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9ddc2-223">CommonParameters</span></span>

<span data-ttu-id="9ddc2-224">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-224">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ddc2-225">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ddc2-225">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ddc2-226">Entradas</span><span class="sxs-lookup"><span data-stu-id="9ddc2-226">Inputs</span></span>

### <span data-ttu-id="9ddc2-227">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9ddc2-227">None</span></span>

<span data-ttu-id="9ddc2-228">`Set-Alias` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-228">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="9ddc2-229">Saídas</span><span class="sxs-lookup"><span data-stu-id="9ddc2-229">Outputs</span></span>

### <span data-ttu-id="9ddc2-230">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="9ddc2-230">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="9ddc2-231">Quando você usa o parâmetro **PassThru** , o `Set-Alias` gera um objeto **System. Management. Automation. AliasInfo** que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-231">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="9ddc2-232">Caso contrário, `Set-Alias` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-232">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="9ddc2-233">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9ddc2-233">NOTES</span></span>

<span data-ttu-id="9ddc2-234">O PowerShell inclui aliases internos que estão disponíveis em cada sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-234">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="9ddc2-235">O `Get-Alias` cmdlet exibe os aliases disponíveis em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-235">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="9ddc2-236">Para criar um novo alias, use `Set-Alias` ou `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-236">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="9ddc2-237">Para remover um alias, use o `Remove-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-237">To remove an alias use the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="9ddc2-238">Por exemplo, `Remove-Item -Path Alias:aliasname`.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-238">For example, `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="9ddc2-239">Para criar um alias que esteja disponível em cada sessão do PowerShell, adicione-o ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-239">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="9ddc2-240">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9ddc2-240">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="9ddc2-241">Um alias pode ser salvo e reutilizado em outra sessão do PowerShell fazendo uma exportação e uma importação.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-241">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="9ddc2-242">Para salvar um alias em um arquivo, use `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-242">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="9ddc2-243">Para adicionar um alias salvo a uma nova sessão do PowerShell, use `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="9ddc2-243">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="9ddc2-244">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9ddc2-244">RELATED LINKS</span></span>

[<span data-ttu-id="9ddc2-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="9ddc2-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="9ddc2-246">about_Functions</span><span class="sxs-lookup"><span data-stu-id="9ddc2-246">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="9ddc2-247">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="9ddc2-247">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="9ddc2-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="9ddc2-248">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="9ddc2-249">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="9ddc2-249">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="9ddc2-250">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="9ddc2-250">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="9ddc2-251">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="9ddc2-251">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="9ddc2-252">New-Alias</span><span class="sxs-lookup"><span data-stu-id="9ddc2-252">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="9ddc2-253">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9ddc2-253">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)
