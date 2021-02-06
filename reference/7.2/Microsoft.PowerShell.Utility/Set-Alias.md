---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: e9e80b4bf558dcf1e225868a1138979270ea304f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598611"
---
# <span data-ttu-id="c5320-102">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-102">Set-Alias</span></span>

## <span data-ttu-id="c5320-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c5320-103">SYNOPSIS</span></span>
<span data-ttu-id="c5320-104">Cria ou altera um alias para um cmdlet ou outro comando na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-104">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="c5320-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5320-105">SYNTAX</span></span>

### <span data-ttu-id="c5320-106">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="c5320-106">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c5320-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5320-107">DESCRIPTION</span></span>

<span data-ttu-id="c5320-108">O `Set-Alias` cmdlet cria ou altera um alias para um cmdlet ou um comando, como uma função, script, arquivo ou outro executável.</span><span class="sxs-lookup"><span data-stu-id="c5320-108">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="c5320-109">Um alias é um nome alternativo que se refere a um cmdlet ou comando.</span><span class="sxs-lookup"><span data-stu-id="c5320-109">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="c5320-110">Por exemplo, `sal` é o alias para o `Set-Alias` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-110">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="c5320-111">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="c5320-111">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="c5320-112">Um cmdlet pode ter vários aliases, mas um alias só pode ser associado a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-112">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="c5320-113">Você pode usar `Set-Alias` para reatribuir um alias existente a outro cmdlet ou alterar as propriedades de um alias, como a descrição.</span><span class="sxs-lookup"><span data-stu-id="c5320-113">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="c5320-114">Um alias que é criado ou alterado pelo `Set-Alias` não é permanente e só está disponível durante a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-114">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="c5320-115">Quando a sessão do PowerShell é fechada, o alias é removido.</span><span class="sxs-lookup"><span data-stu-id="c5320-115">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="c5320-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c5320-116">EXAMPLES</span></span>

### <span data-ttu-id="c5320-117">Exemplo 1: criar um alias para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="c5320-117">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="c5320-118">Este comando cria um alias para um cmdlet na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-118">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="c5320-119">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-119">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="c5320-120">O parâmetro **Name** especifica o nome do alias, `list` .</span><span class="sxs-lookup"><span data-stu-id="c5320-120">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="c5320-121">O parâmetro **Value** especifica o cmdlet que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="c5320-121">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="c5320-122">Para executar o alias, digite `list` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-122">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="c5320-123">Exemplo 2: Reatribuir um alias existente a um cmdlet diferente</span><span class="sxs-lookup"><span data-stu-id="c5320-123">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="c5320-124">Esse comando reatribui um alias existente para executar um cmdlet diferente.</span><span class="sxs-lookup"><span data-stu-id="c5320-124">This command reassigns an existing alias to run a different cmdlet.</span></span>

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

<span data-ttu-id="c5320-125">O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-125">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="c5320-126">O `list` alias está associado ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-126">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="c5320-127">Quando o `list` alias é executado, os itens no diretório atual são exibidos.</span><span class="sxs-lookup"><span data-stu-id="c5320-127">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="c5320-128">O `Set-Alias` cmdlet usa o parâmetro **Name** para especificar o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-128">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="c5320-129">O parâmetro **Value** associa o alias ao `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-129">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="c5320-130">O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-130">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="c5320-131">O `list` alias está associado ao `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-131">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="c5320-132">Quando o `list` alias é executado, o local do diretório atual é exibido.</span><span class="sxs-lookup"><span data-stu-id="c5320-132">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="c5320-133">Exemplo 3: criar e alterar um alias somente leitura</span><span class="sxs-lookup"><span data-stu-id="c5320-133">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="c5320-134">Este comando cria um alias somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c5320-134">This command creates a read-only alias.</span></span> <span data-ttu-id="c5320-135">A opção somente leitura impede alterações involuntárias em um alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-135">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="c5320-136">Para alterar ou excluir um alias somente leitura, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="c5320-136">To change or delete a read-only alias, use the **Force** parameter.</span></span>

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

<span data-ttu-id="c5320-137">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-137">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="c5320-138">O parâmetro **Name** especifica o nome do alias, `loc` .</span><span class="sxs-lookup"><span data-stu-id="c5320-138">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="c5320-139">O parâmetro **Value** especifica o `Get-Location` cmdlet que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="c5320-139">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="c5320-140">O parâmetro **Option** especifica o valor **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="c5320-140">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="c5320-141">O parâmetro **PassThru** representa o objeto alias e envia o objeto por meio do pipeline para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-141">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c5320-142">`Format-List` usa o parâmetro **Property** com um asterisco ( `*` ) para que todas as propriedades sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="c5320-142">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="c5320-143">A saída de exemplo mostra uma lista parcial dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="c5320-143">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="c5320-144">O `loc` alias é alterado com a adição de dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c5320-144">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="c5320-145">**Descrição** adiciona texto para explicar a finalidade do alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-145">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="c5320-146">O parâmetro **Force** é necessário porque o `loc` alias é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c5320-146">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="c5320-147">Se o parâmetro **Force** não for usado, a alteração falhará.</span><span class="sxs-lookup"><span data-stu-id="c5320-147">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="c5320-148">Exemplo 4: criar um alias para um arquivo executável</span><span class="sxs-lookup"><span data-stu-id="c5320-148">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="c5320-149">Este exemplo cria um alias para um arquivo executável no computador local.</span><span class="sxs-lookup"><span data-stu-id="c5320-149">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="c5320-150">O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-150">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="c5320-151">O parâmetro **Name** especifica o nome do alias, `np` .</span><span class="sxs-lookup"><span data-stu-id="c5320-151">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="c5320-152">O parâmetro **Value** especifica o caminho e o nome do aplicativo **C:\Windows\notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="c5320-152">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="c5320-153">O `Get-Alias` cmdlet usa o parâmetro **Name** para mostrar que o `np` alias está associado a **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="c5320-153">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="c5320-154">Para executar o alias, digite `np` na linha de comando do PowerShell para abrir **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="c5320-154">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="c5320-155">Exemplo 5: criar um alias para um comando com parâmetros</span><span class="sxs-lookup"><span data-stu-id="c5320-155">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="c5320-156">Este exemplo mostra como atribuir um alias a um comando com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c5320-156">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="c5320-157">Você pode criar um alias para um cmdlet, como `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="c5320-157">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="c5320-158">Você não pode criar um alias para um comando com parâmetros e valores, como `Set-Location -Path C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="c5320-158">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="c5320-159">Para criar um alias para um comando, crie uma função que inclua o comando e, em seguida, crie um alias para a função.</span><span class="sxs-lookup"><span data-stu-id="c5320-159">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="c5320-160">Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="c5320-160">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="c5320-161">Uma função chamada `CD32` é criada.</span><span class="sxs-lookup"><span data-stu-id="c5320-161">A function named `CD32` is created.</span></span> <span data-ttu-id="c5320-162">A função usa o `Set-Location` cmdlet com o parâmetro **Path** para especificar o diretório, **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="c5320-162">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32**.</span></span>

<span data-ttu-id="c5320-163">O `Set-Alias` cmdlet cria um alias para a função na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-163">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="c5320-164">O parâmetro **Name** especifica o nome do alias, `Go` .</span><span class="sxs-lookup"><span data-stu-id="c5320-164">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="c5320-165">O parâmetro **Value** especifica o nome da função, `CD32` .</span><span class="sxs-lookup"><span data-stu-id="c5320-165">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="c5320-166">Para executar o alias, digite `Go` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-166">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="c5320-167">A `CD32` função é executada e muda para o diretório **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="c5320-167">The `CD32` function runs and changes to the directory **C:\Windows\System32**.</span></span>

## <span data-ttu-id="c5320-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5320-168">PARAMETERS</span></span>

### <span data-ttu-id="c5320-169">-Description</span><span class="sxs-lookup"><span data-stu-id="c5320-169">-Description</span></span>

<span data-ttu-id="c5320-170">Especifica uma descrição do alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-170">Specifies a description of the alias.</span></span> <span data-ttu-id="c5320-171">Você pode digitar qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c5320-171">You can type any string.</span></span> <span data-ttu-id="c5320-172">Se a descrição incluir espaços, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="c5320-172">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="c5320-173">-Force</span><span class="sxs-lookup"><span data-stu-id="c5320-173">-Force</span></span>

<span data-ttu-id="c5320-174">Use o parâmetro **Force** para alterar ou excluir um alias que tenha o parâmetro **Option** definido como **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="c5320-174">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="c5320-175">O parâmetro **Force** não pode alterar nem excluir um alias com o parâmetro **Option** definido como **Constant**.</span><span class="sxs-lookup"><span data-stu-id="c5320-175">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

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

### <span data-ttu-id="c5320-176">-Name</span><span class="sxs-lookup"><span data-stu-id="c5320-176">-Name</span></span>

<span data-ttu-id="c5320-177">Especifica o nome de um novo alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-177">Specifies the name of a new alias.</span></span> <span data-ttu-id="c5320-178">Um nome de alias pode conter caracteres alfanuméricos e hifens.</span><span class="sxs-lookup"><span data-stu-id="c5320-178">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="c5320-179">Nomes de alias não podem ser numéricos, como 123.</span><span class="sxs-lookup"><span data-stu-id="c5320-179">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="c5320-180">-Opção</span><span class="sxs-lookup"><span data-stu-id="c5320-180">-Option</span></span>

<span data-ttu-id="c5320-181">Define o valor da propriedade de **opção** do alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-181">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="c5320-182">Valores como **ReadOnly** e **Constant** protegem um alias de alterações involuntárias.</span><span class="sxs-lookup"><span data-stu-id="c5320-182">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="c5320-183">Para ver a propriedade **Option** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="c5320-183">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="c5320-184">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c5320-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c5320-185">**Escopo** O alias é copiado para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="c5320-185">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="c5320-186">**Constante** Não pode ser alterado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="c5320-186">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="c5320-187">**Nenhum** Não define opções e é o padrão.</span><span class="sxs-lookup"><span data-stu-id="c5320-187">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="c5320-188">**Particular** O alias está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="c5320-188">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="c5320-189">**Somente leitura** Não pode ser alterado ou excluído, a menos que o parâmetro **Force** seja usado.</span><span class="sxs-lookup"><span data-stu-id="c5320-189">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="c5320-190">**Não especificado**</span><span class="sxs-lookup"><span data-stu-id="c5320-190">**Unspecified**</span></span>

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

### <span data-ttu-id="c5320-191">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c5320-191">-PassThru</span></span>

<span data-ttu-id="c5320-192">Retorna um objeto que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-192">Returns an object that represents the alias.</span></span> <span data-ttu-id="c5320-193">Use um cmdlet Format como `Format-List` para exibir o objeto.</span><span class="sxs-lookup"><span data-stu-id="c5320-193">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="c5320-194">Por padrão, `Set-Alias` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c5320-194">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="c5320-195">-Escopo</span><span class="sxs-lookup"><span data-stu-id="c5320-195">-Scope</span></span>

<span data-ttu-id="c5320-196">Especifica o escopo no qual esse alias é válido.</span><span class="sxs-lookup"><span data-stu-id="c5320-196">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="c5320-197">O valor padrão é **local**.</span><span class="sxs-lookup"><span data-stu-id="c5320-197">The default value is **Local**.</span></span> <span data-ttu-id="c5320-198">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="c5320-198">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="c5320-199">Os valores aceitáveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c5320-199">The acceptable values are as follows:</span></span>

- <span data-ttu-id="c5320-200">Global</span><span class="sxs-lookup"><span data-stu-id="c5320-200">Global</span></span>
- <span data-ttu-id="c5320-201">Local</span><span class="sxs-lookup"><span data-stu-id="c5320-201">Local</span></span>
- <span data-ttu-id="c5320-202">Privados</span><span class="sxs-lookup"><span data-stu-id="c5320-202">Private</span></span>
- <span data-ttu-id="c5320-203">Escopos numerados</span><span class="sxs-lookup"><span data-stu-id="c5320-203">Numbered scopes</span></span>
- <span data-ttu-id="c5320-204">Script</span><span class="sxs-lookup"><span data-stu-id="c5320-204">Script</span></span>

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

### <span data-ttu-id="c5320-205">-Value</span><span class="sxs-lookup"><span data-stu-id="c5320-205">-Value</span></span>

<span data-ttu-id="c5320-206">Especifica o nome do cmdlet ou comando que o alias executa.</span><span class="sxs-lookup"><span data-stu-id="c5320-206">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="c5320-207">O parâmetro de **valor** é a propriedade de **definição** do alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-207">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="c5320-208">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c5320-208">-Confirm</span></span>

<span data-ttu-id="c5320-209">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-209">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c5320-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c5320-210">-WhatIf</span></span>

<span data-ttu-id="c5320-211">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="c5320-211">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c5320-212">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c5320-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c5320-213">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5320-213">CommonParameters</span></span>

<span data-ttu-id="c5320-214">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5320-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5320-215">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5320-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5320-216">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c5320-216">INPUTS</span></span>

### <span data-ttu-id="c5320-217">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c5320-217">None</span></span>

<span data-ttu-id="c5320-218">`Set-Alias` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="c5320-218">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="c5320-219">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c5320-219">OUTPUTS</span></span>

### <span data-ttu-id="c5320-220">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="c5320-220">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="c5320-221">Quando você usa o parâmetro **PassThru** , o `Set-Alias` gera um objeto **System. Management. Automation. AliasInfo** que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="c5320-221">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="c5320-222">Caso contrário, `Set-Alias` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c5320-222">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="c5320-223">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c5320-223">NOTES</span></span>

<span data-ttu-id="c5320-224">O PowerShell inclui aliases internos que estão disponíveis em cada sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-224">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="c5320-225">O `Get-Alias` cmdlet exibe os aliases disponíveis em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-225">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="c5320-226">Para criar um alias, use os cmdlets `Set-Alias` ou `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="c5320-226">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="c5320-227">No PowerShell 6, para excluir um alias, use o `Remove-Alias` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5320-227">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="c5320-228">`Remove-Item` é aceita para compatibilidade com versões anteriores do PowerShell, por exemplo, para scripts criados</span><span class="sxs-lookup"><span data-stu-id="c5320-228">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="c5320-229">Use um comando como `Remove-Item -Path Alias:aliasname` .</span><span class="sxs-lookup"><span data-stu-id="c5320-229">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="c5320-230">Para criar um alias que esteja disponível em cada sessão do PowerShell, adicione-o ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5320-230">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="c5320-231">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c5320-231">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="c5320-232">Um alias pode ser salvo e reutilizado em outra sessão do PowerShell fazendo uma exportação e uma importação.</span><span class="sxs-lookup"><span data-stu-id="c5320-232">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="c5320-233">Para salvar um alias em um arquivo, use `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="c5320-233">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="c5320-234">Para adicionar um alias salvo a uma nova sessão do PowerShell, use `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="c5320-234">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="c5320-235">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c5320-235">RELATED LINKS</span></span>

[<span data-ttu-id="c5320-236">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="c5320-236">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="c5320-237">about_Functions</span><span class="sxs-lookup"><span data-stu-id="c5320-237">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="c5320-238">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="c5320-238">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="c5320-239">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="c5320-239">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="c5320-240">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-240">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="c5320-241">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-241">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="c5320-242">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-242">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="c5320-243">New-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-243">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="c5320-244">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="c5320-244">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="c5320-245">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c5320-245">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)

