---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 6f98a910e43b87793ac4f2af8ffb069d3e5d47ba
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192888"
---
# <span data-ttu-id="fce3e-103">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-103">Remove-Alias</span></span>

## <span data-ttu-id="fce3e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fce3e-104">SYNOPSIS</span></span>
<span data-ttu-id="fce3e-105">Remover um alias da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fce3e-105">Remove an alias from the current session.</span></span>

## <span data-ttu-id="fce3e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fce3e-106">SYNTAX</span></span>

### <span data-ttu-id="fce3e-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="fce3e-107">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="fce3e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fce3e-108">DESCRIPTION</span></span>

<span data-ttu-id="fce3e-109">O `Remove-Alias` cmdlet Remove um alias da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce3e-109">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="fce3e-110">Para remover um alias com a propriedade **Option** definida como **ReadOnly** , use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-110">To remove an alias with the **Option** property set to **ReadOnly** , use the **Force** parameter.</span></span>

<span data-ttu-id="fce3e-111">O `Remove-Alias` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="fce3e-111">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="fce3e-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fce3e-112">EXAMPLES</span></span>

### <span data-ttu-id="fce3e-113">Exemplo 1-remover um alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-113">Example 1 - Remove an alias</span></span>

<span data-ttu-id="fce3e-114">Este exemplo remove um alias chamado `del` que representa o `Remove-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fce3e-114">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="fce3e-115">Exemplo 2-remover todos os aliases não constantes</span><span class="sxs-lookup"><span data-stu-id="fce3e-115">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="fce3e-116">Este exemplo remove todos os aliases da sessão atual do PowerShell, com exceção de aliases com a propriedade **Options** definida como **Constant** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-116">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant** .</span></span> <span data-ttu-id="fce3e-117">Depois que o comando é executado, os aliases estão disponíveis em outras sessões do PowerShell ou novas sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce3e-117">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="fce3e-118">`Get-Alias` Obtém todos os aliases na sessão do PowerShell e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="fce3e-118">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="fce3e-119">`Where-Object` usa um bloco de script, e a propriedade de `$_` **Opções** e a variável automática () e as propriedades representam o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="fce3e-119">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="fce3e-120">O parâmetro **ne** (diferente de), seleciona objetos que não têm um valor de **Opções** definido como **constante** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-120">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant** .</span></span> <span data-ttu-id="fce3e-121">`Remove-Alias` usa o parâmetro **Force** para remover aliases, incluindo aliases somente leitura, da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce3e-121">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="fce3e-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fce3e-122">PARAMETERS</span></span>

### <span data-ttu-id="fce3e-123">-Force</span><span class="sxs-lookup"><span data-stu-id="fce3e-123">-Force</span></span>

<span data-ttu-id="fce3e-124">Indica que o cmdlet Remove um alias, incluindo aliases com a propriedade **Option** definida como **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-124">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly** .</span></span> <span data-ttu-id="fce3e-125">O parâmetro **Force** não pode remover um alias com uma propriedade **Option** definida como **Constant** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-125">The **Force** parameter can't remove an alias with an **Option** property set to **Constant** .</span></span>

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

### <span data-ttu-id="fce3e-126">-Name</span><span class="sxs-lookup"><span data-stu-id="fce3e-126">-Name</span></span>

<span data-ttu-id="fce3e-127">Especifica o nome do alias a ser removido.</span><span class="sxs-lookup"><span data-stu-id="fce3e-127">Specifies the name of the alias to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fce3e-128">-Escopo</span><span class="sxs-lookup"><span data-stu-id="fce3e-128">-Scope</span></span>

<span data-ttu-id="fce3e-129">Afeta somente os aliases no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="fce3e-129">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="fce3e-130">O escopo padrão é **local** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-130">The default scope is **Local** .</span></span> <span data-ttu-id="fce3e-131">Para obter mais informações, consulte [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="fce3e-131">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="fce3e-132">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="fce3e-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fce3e-133">Global</span><span class="sxs-lookup"><span data-stu-id="fce3e-133">Global</span></span>
- <span data-ttu-id="fce3e-134">Local</span><span class="sxs-lookup"><span data-stu-id="fce3e-134">Local</span></span>
- <span data-ttu-id="fce3e-135">script</span><span class="sxs-lookup"><span data-stu-id="fce3e-135">Script</span></span>
- <span data-ttu-id="fce3e-136">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="fce3e-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

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

### <span data-ttu-id="fce3e-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fce3e-137">CommonParameters</span></span>

<span data-ttu-id="fce3e-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fce3e-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fce3e-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fce3e-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fce3e-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fce3e-140">INPUTS</span></span>

### <span data-ttu-id="fce3e-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="fce3e-141">System.String[]</span></span>

<span data-ttu-id="fce3e-142">É possível canalizar um objeto de alias para **Remove-alias** .</span><span class="sxs-lookup"><span data-stu-id="fce3e-142">You can pipe an alias object to **Remove-Alias** .</span></span>

## <span data-ttu-id="fce3e-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fce3e-143">OUTPUTS</span></span>

### <span data-ttu-id="fce3e-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fce3e-144">None</span></span>

<span data-ttu-id="fce3e-145">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fce3e-145">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="fce3e-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fce3e-146">NOTES</span></span>

<span data-ttu-id="fce3e-147">As alterações afetam apenas o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fce3e-147">Changes only affect the current scope.</span></span> <span data-ttu-id="fce3e-148">Para remover um alias de todas as sessões, adicione um comando **Remove-alias** ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fce3e-148">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="fce3e-149">Para obter mais informações, consulte [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span><span class="sxs-lookup"><span data-stu-id="fce3e-149">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="fce3e-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fce3e-150">RELATED LINKS</span></span>

[<span data-ttu-id="fce3e-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="fce3e-151">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="fce3e-152">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-152">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="fce3e-153">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-153">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="fce3e-154">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-154">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="fce3e-155">New-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-155">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="fce3e-156">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="fce3e-156">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="fce3e-157">Where-Object</span><span class="sxs-lookup"><span data-stu-id="fce3e-157">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
