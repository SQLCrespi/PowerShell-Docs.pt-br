---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: 98f68cff8501fec375e3a2b8ac446e41d5721fc7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192994"
---
# <span data-ttu-id="b0eb5-103">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-103">Get-Alias</span></span>

## <span data-ttu-id="b0eb5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b0eb5-104">SYNOPSIS</span></span>
<span data-ttu-id="b0eb5-105">Obtém os aliases para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-105">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="b0eb5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0eb5-106">SYNTAX</span></span>

### <span data-ttu-id="b0eb5-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="b0eb5-107">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="b0eb5-108">Definição</span><span class="sxs-lookup"><span data-stu-id="b0eb5-108">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="b0eb5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0eb5-109">DESCRIPTION</span></span>

<span data-ttu-id="b0eb5-110">O cmdlet **Get-Alias** Obtém os aliases na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-110">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="b0eb5-111">Isso inclui aliases internos, aliases que você definiu ou importou e aliases que você adicionou ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-111">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="b0eb5-112">Por padrão, **Get-Alias** usa um alias e retorna o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-112">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="b0eb5-113">Quando você usa o parâmetro de *definição* , **Get-Alias** usa um nome de comando e retorna seus aliases.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-113">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="b0eb5-114">A partir do Windows PowerShell 3,0, **Get-Alias** exibe nomes de alias não hifenizados em um `<alias> -> <definition>` formato para facilitar ainda mais a localização das informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-114">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="b0eb5-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b0eb5-115">EXAMPLES</span></span>

### <span data-ttu-id="b0eb5-116">Exemplo 1: obter todos os aliases na sessão atual</span><span class="sxs-lookup"><span data-stu-id="b0eb5-116">Example 1: Get all aliases in the current session</span></span>

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

<span data-ttu-id="b0eb5-117">Este comando obtém todos os aliases na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-117">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="b0eb5-118">A saída mostra o `<alias> -> <definition>` formato que foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-118">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="b0eb5-119">Esse formato é usado apenas para aliases que não incluem hifens, pois aliases com hifens são geralmente nomes preferidos de cmdlets e funções, em vez de apelidos.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-119">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="b0eb5-120">Exemplo 2: obter aliases por nome</span><span class="sxs-lookup"><span data-stu-id="b0eb5-120">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="b0eb5-121">Esse comando obtém todos os aliases que começam com GP ou SP, exceto para aliases que terminam com PS.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-121">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="b0eb5-122">Exemplo 3: obter aliases para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0eb5-122">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="b0eb5-123">Este comando obtém os aliases para o cmdlet Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-123">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="b0eb5-124">Por padrão, o cmdlet **Get-Alias** Obtém o nome do item quando você conhece o alias.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-124">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="b0eb5-125">O parâmetro de *definição* Obtém o alias quando você sabe o nome do item.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-125">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="b0eb5-126">Exemplo 4: obter aliases por Propriedade</span><span class="sxs-lookup"><span data-stu-id="b0eb5-126">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="b0eb5-127">Esse comando obtém todos os aliases nos quais o valor da Propriedade Options é ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-127">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="b0eb5-128">Esse comando fornece uma maneira rápida de localizar os aliases que são criados no PowerShell, pois eles têm a opção ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-128">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="b0eb5-129">Options é apenas uma propriedade dos objetos AliasInfo que **Get-Alias** obtém.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-129">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="b0eb5-130">Para localizar todas as propriedades e métodos de objetos AliasInfo, digite `Get-Alias | get-member` .</span><span class="sxs-lookup"><span data-stu-id="b0eb5-130">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="b0eb5-131">Exemplo 5: obter aliases por nome e filtro por letra inicial</span><span class="sxs-lookup"><span data-stu-id="b0eb5-131">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="b0eb5-132">Este exemplo obtém aliases para comandos com nomes que terminam em "-PSSession", exceto para aqueles que começam com "e".</span><span class="sxs-lookup"><span data-stu-id="b0eb5-132">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="b0eb5-133">O comando usa o parâmetro *Scope* para aplicar o comando no escopo global.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-133">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="b0eb5-134">Isso é útil em scripts quando você deseja obter os aliases na sessão.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-134">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="b0eb5-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0eb5-135">PARAMETERS</span></span>

### <span data-ttu-id="b0eb5-136">-Definition</span><span class="sxs-lookup"><span data-stu-id="b0eb5-136">-Definition</span></span>

<span data-ttu-id="b0eb5-137">Obtém os aliases para o item especificado.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-137">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="b0eb5-138">Digite o nome de um cmdlet, uma função, um script, um arquivo ou arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-138">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="b0eb5-139">Esse parâmetro é chamado de *definição* , pois pesquisa o nome do item na propriedade definição do objeto alias.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-139">This parameter is called *Definition* , because it searches for the item name in the Definition property of the alias object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b0eb5-140">-Excluir</span><span class="sxs-lookup"><span data-stu-id="b0eb5-140">-Exclude</span></span>

<span data-ttu-id="b0eb5-141">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-141">Omits the specified items.</span></span>
<span data-ttu-id="b0eb5-142">O valor desse parâmetro qualifica os parâmetros Name e Definition.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-142">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="b0eb5-143">Digite um nome, uma definição ou um padrão, como "s \*".</span><span class="sxs-lookup"><span data-stu-id="b0eb5-143">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="b0eb5-144">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-144">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b0eb5-145">-Name</span><span class="sxs-lookup"><span data-stu-id="b0eb5-145">-Name</span></span>

<span data-ttu-id="b0eb5-146">Especifica os aliases que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-146">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="b0eb5-147">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-147">Wildcards are permitted.</span></span>
<span data-ttu-id="b0eb5-148">Por padrão, o `Get-Alias` recupera todos os aliases definidos para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-148">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="b0eb5-149">O **nome** do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-149">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="b0eb5-150">Você também pode canalizar nomes de alias para `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="b0eb5-150">You can also pipe alias names to `Get-Alias`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b0eb5-151">-Escopo</span><span class="sxs-lookup"><span data-stu-id="b0eb5-151">-Scope</span></span>

<span data-ttu-id="b0eb5-152">Especifica o escopo para o qual este cmdlet obtém aliases.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-152">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="b0eb5-153">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b0eb5-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b0eb5-154">Global</span><span class="sxs-lookup"><span data-stu-id="b0eb5-154">Global</span></span>
- <span data-ttu-id="b0eb5-155">Local</span><span class="sxs-lookup"><span data-stu-id="b0eb5-155">Local</span></span>
- <span data-ttu-id="b0eb5-156">script</span><span class="sxs-lookup"><span data-stu-id="b0eb5-156">Script</span></span>
- <span data-ttu-id="b0eb5-157">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="b0eb5-157">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="b0eb5-158">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-158">Local is the default.</span></span>
<span data-ttu-id="b0eb5-159">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-159">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0eb5-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b0eb5-160">CommonParameters</span></span>

<span data-ttu-id="b0eb5-161">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0eb5-162">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b0eb5-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0eb5-163">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b0eb5-163">INPUTS</span></span>

### <span data-ttu-id="b0eb5-164">System.String</span><span class="sxs-lookup"><span data-stu-id="b0eb5-164">System.String</span></span>

<span data-ttu-id="b0eb5-165">Você pode canalizar nomes de alias para **Get-Alias** .</span><span class="sxs-lookup"><span data-stu-id="b0eb5-165">You can pipe alias names to **Get-Alias** .</span></span>

## <span data-ttu-id="b0eb5-166">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b0eb5-166">OUTPUTS</span></span>

### <span data-ttu-id="b0eb5-167">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="b0eb5-167">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="b0eb5-168">**Get-Alias** retorna um objeto que representa cada alias.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-168">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="b0eb5-169">**Get-Alias** retorna o mesmo objeto para cada alias, mas o PowerShell usa um formato baseado em seta para exibir os nomes de aliases não-hifenizados.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-169">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="b0eb5-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b0eb5-170">NOTES</span></span>

- <span data-ttu-id="b0eb5-171">Para criar um novo alias, use Set-Alias ou New-Alias.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-171">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="b0eb5-172">Para excluir um alias, use Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-172">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="b0eb5-173">O formato de nome de alias com base em seta não é usado para aliases que incluem um hífen.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-173">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="b0eb5-174">Eles devem ser nomes substitutos preferenciais para cmdlets e funções, em vez de abreviações típicas ou apelidos.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-174">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="b0eb5-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b0eb5-175">RELATED LINKS</span></span>

[<span data-ttu-id="b0eb5-176">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-176">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="b0eb5-177">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-177">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="b0eb5-178">New-Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-178">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="b0eb5-179">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-179">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="b0eb5-180">Provedor Alias</span><span class="sxs-lookup"><span data-stu-id="b0eb5-180">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="b0eb5-181">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="b0eb5-181">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)
