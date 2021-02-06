---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: 7b6f639d1c5685e341260c056a1dd0a17fe9f46d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595349"
---
# <span data-ttu-id="34116-102">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="34116-102">Get-Alias</span></span>

## <span data-ttu-id="34116-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="34116-103">SYNOPSIS</span></span>
<span data-ttu-id="34116-104">Obtém os aliases para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="34116-104">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="34116-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34116-105">SYNTAX</span></span>

### <span data-ttu-id="34116-106">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="34116-106">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="34116-107">Definição</span><span class="sxs-lookup"><span data-stu-id="34116-107">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="34116-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="34116-108">DESCRIPTION</span></span>

<span data-ttu-id="34116-109">O cmdlet **Get-Alias** Obtém os aliases na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="34116-109">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="34116-110">Isso inclui aliases internos, aliases que você definiu ou importou e aliases que você adicionou ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34116-110">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="34116-111">Por padrão, **Get-Alias** usa um alias e retorna o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="34116-111">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="34116-112">Quando você usa o parâmetro de *definição* , **Get-Alias** usa um nome de comando e retorna seus aliases.</span><span class="sxs-lookup"><span data-stu-id="34116-112">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="34116-113">A partir do Windows PowerShell 3,0, **Get-Alias** exibe nomes de alias não hifenizados em um `<alias> -> <definition>` formato para facilitar ainda mais a localização das informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="34116-113">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="34116-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="34116-114">EXAMPLES</span></span>

### <span data-ttu-id="34116-115">Exemplo 1: obter todos os aliases na sessão atual</span><span class="sxs-lookup"><span data-stu-id="34116-115">Example 1: Get all aliases in the current session</span></span>

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

<span data-ttu-id="34116-116">Este comando obtém todos os aliases na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="34116-116">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="34116-117">A saída mostra o `<alias> -> <definition>` formato que foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="34116-117">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="34116-118">Esse formato é usado apenas para aliases que não incluem hifens, pois aliases com hifens são geralmente nomes preferidos de cmdlets e funções, em vez de apelidos.</span><span class="sxs-lookup"><span data-stu-id="34116-118">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="34116-119">Exemplo 2: obter aliases por nome</span><span class="sxs-lookup"><span data-stu-id="34116-119">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="34116-120">Esse comando obtém todos os aliases que começam com GP ou SP, exceto para aliases que terminam com PS.</span><span class="sxs-lookup"><span data-stu-id="34116-120">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="34116-121">Exemplo 3: obter aliases para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="34116-121">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="34116-122">Este comando obtém os aliases para o cmdlet Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="34116-122">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="34116-123">Por padrão, o cmdlet **Get-Alias** Obtém o nome do item quando você conhece o alias.</span><span class="sxs-lookup"><span data-stu-id="34116-123">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="34116-124">O parâmetro de *definição* Obtém o alias quando você sabe o nome do item.</span><span class="sxs-lookup"><span data-stu-id="34116-124">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="34116-125">Exemplo 4: obter aliases por Propriedade</span><span class="sxs-lookup"><span data-stu-id="34116-125">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="34116-126">Esse comando obtém todos os aliases nos quais o valor da Propriedade Options é ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="34116-126">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="34116-127">Esse comando fornece uma maneira rápida de localizar os aliases que são criados no PowerShell, pois eles têm a opção ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="34116-127">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="34116-128">Options é apenas uma propriedade dos objetos AliasInfo que **Get-Alias** obtém.</span><span class="sxs-lookup"><span data-stu-id="34116-128">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="34116-129">Para localizar todas as propriedades e métodos de objetos AliasInfo, digite `Get-Alias | get-member` .</span><span class="sxs-lookup"><span data-stu-id="34116-129">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="34116-130">Exemplo 5: obter aliases por nome e filtro por letra inicial</span><span class="sxs-lookup"><span data-stu-id="34116-130">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="34116-131">Este exemplo obtém aliases para comandos com nomes que terminam em "-PSSession", exceto para aqueles que começam com "e".</span><span class="sxs-lookup"><span data-stu-id="34116-131">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="34116-132">O comando usa o parâmetro *Scope* para aplicar o comando no escopo global.</span><span class="sxs-lookup"><span data-stu-id="34116-132">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="34116-133">Isso é útil em scripts quando você deseja obter os aliases na sessão.</span><span class="sxs-lookup"><span data-stu-id="34116-133">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="34116-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34116-134">PARAMETERS</span></span>

### <span data-ttu-id="34116-135">-Definition</span><span class="sxs-lookup"><span data-stu-id="34116-135">-Definition</span></span>

<span data-ttu-id="34116-136">Obtém os aliases para o item especificado.</span><span class="sxs-lookup"><span data-stu-id="34116-136">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="34116-137">Digite o nome de um cmdlet, uma função, um script, um arquivo ou arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="34116-137">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="34116-138">Esse parâmetro é chamado de *definição*, pois pesquisa o nome do item na propriedade definição do objeto alias.</span><span class="sxs-lookup"><span data-stu-id="34116-138">This parameter is called *Definition*, because it searches for the item name in the Definition property of the alias object.</span></span>

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

### <span data-ttu-id="34116-139">-Excluir</span><span class="sxs-lookup"><span data-stu-id="34116-139">-Exclude</span></span>

<span data-ttu-id="34116-140">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="34116-140">Omits the specified items.</span></span>
<span data-ttu-id="34116-141">O valor desse parâmetro qualifica os parâmetros Name e Definition.</span><span class="sxs-lookup"><span data-stu-id="34116-141">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="34116-142">Digite um nome, uma definição ou um padrão, como "s \*".</span><span class="sxs-lookup"><span data-stu-id="34116-142">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="34116-143">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="34116-143">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="34116-144">-Name</span><span class="sxs-lookup"><span data-stu-id="34116-144">-Name</span></span>

<span data-ttu-id="34116-145">Especifica os aliases que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="34116-145">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="34116-146">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="34116-146">Wildcards are permitted.</span></span>
<span data-ttu-id="34116-147">Por padrão, o `Get-Alias` recupera todos os aliases definidos para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="34116-147">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="34116-148">O **nome** do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="34116-148">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="34116-149">Você também pode canalizar nomes de alias para `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="34116-149">You can also pipe alias names to `Get-Alias`.</span></span>

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

### <span data-ttu-id="34116-150">-Escopo</span><span class="sxs-lookup"><span data-stu-id="34116-150">-Scope</span></span>

<span data-ttu-id="34116-151">Especifica o escopo para o qual este cmdlet obtém aliases.</span><span class="sxs-lookup"><span data-stu-id="34116-151">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="34116-152">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="34116-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="34116-153">Global</span><span class="sxs-lookup"><span data-stu-id="34116-153">Global</span></span>
- <span data-ttu-id="34116-154">Local</span><span class="sxs-lookup"><span data-stu-id="34116-154">Local</span></span>
- <span data-ttu-id="34116-155">Script</span><span class="sxs-lookup"><span data-stu-id="34116-155">Script</span></span>
- <span data-ttu-id="34116-156">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="34116-156">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="34116-157">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="34116-157">Local is the default.</span></span>
<span data-ttu-id="34116-158">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="34116-158">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="34116-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="34116-159">CommonParameters</span></span>

<span data-ttu-id="34116-160">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="34116-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34116-161">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="34116-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34116-162">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="34116-162">INPUTS</span></span>

### <span data-ttu-id="34116-163">System.String</span><span class="sxs-lookup"><span data-stu-id="34116-163">System.String</span></span>

<span data-ttu-id="34116-164">Você pode canalizar nomes de alias para **Get-Alias**.</span><span class="sxs-lookup"><span data-stu-id="34116-164">You can pipe alias names to **Get-Alias**.</span></span>

## <span data-ttu-id="34116-165">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="34116-165">OUTPUTS</span></span>

### <span data-ttu-id="34116-166">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="34116-166">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="34116-167">**Get-Alias** retorna um objeto que representa cada alias.</span><span class="sxs-lookup"><span data-stu-id="34116-167">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="34116-168">**Get-Alias** retorna o mesmo objeto para cada alias, mas o PowerShell usa um formato baseado em seta para exibir os nomes de aliases não-hifenizados.</span><span class="sxs-lookup"><span data-stu-id="34116-168">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="34116-169">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="34116-169">NOTES</span></span>

- <span data-ttu-id="34116-170">Para criar um novo alias, use Set-Alias ou New-Alias.</span><span class="sxs-lookup"><span data-stu-id="34116-170">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="34116-171">Para excluir um alias, use Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="34116-171">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="34116-172">O formato de nome de alias com base em seta não é usado para aliases que incluem um hífen.</span><span class="sxs-lookup"><span data-stu-id="34116-172">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="34116-173">Eles devem ser nomes substitutos preferenciais para cmdlets e funções, em vez de abreviações típicas ou apelidos.</span><span class="sxs-lookup"><span data-stu-id="34116-173">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="34116-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="34116-174">RELATED LINKS</span></span>

[<span data-ttu-id="34116-175">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="34116-175">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="34116-176">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="34116-176">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="34116-177">New-Alias</span><span class="sxs-lookup"><span data-stu-id="34116-177">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="34116-178">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="34116-178">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="34116-179">Provedor Alias</span><span class="sxs-lookup"><span data-stu-id="34116-179">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="34116-180">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="34116-180">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

