---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 0ce13bef77e9ef9647809336aed650833dab51f3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597593"
---
# <span data-ttu-id="32578-102">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-102">Remove-Alias</span></span>

## <span data-ttu-id="32578-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="32578-103">SYNOPSIS</span></span>
<span data-ttu-id="32578-104">Remover um alias da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="32578-104">Remove an alias from the current session.</span></span>

## <span data-ttu-id="32578-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32578-105">SYNTAX</span></span>

### <span data-ttu-id="32578-106">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="32578-106">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="32578-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32578-107">DESCRIPTION</span></span>

<span data-ttu-id="32578-108">O `Remove-Alias` cmdlet Remove um alias da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32578-108">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="32578-109">Para remover um alias com a propriedade **Option** definida como **ReadOnly**, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="32578-109">To remove an alias with the **Option** property set to **ReadOnly**, use the **Force** parameter.</span></span>

<span data-ttu-id="32578-110">O `Remove-Alias` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="32578-110">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="32578-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="32578-111">EXAMPLES</span></span>

### <span data-ttu-id="32578-112">Exemplo 1-remover um alias</span><span class="sxs-lookup"><span data-stu-id="32578-112">Example 1 - Remove an alias</span></span>

<span data-ttu-id="32578-113">Este exemplo remove um alias chamado `del` que representa o `Remove-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="32578-113">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="32578-114">Exemplo 2-remover todos os aliases não constantes</span><span class="sxs-lookup"><span data-stu-id="32578-114">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="32578-115">Este exemplo remove todos os aliases da sessão atual do PowerShell, com exceção de aliases com a propriedade **Options** definida como **Constant**.</span><span class="sxs-lookup"><span data-stu-id="32578-115">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant**.</span></span> <span data-ttu-id="32578-116">Depois que o comando é executado, os aliases estão disponíveis em outras sessões do PowerShell ou novas sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32578-116">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="32578-117">`Get-Alias` Obtém todos os aliases na sessão do PowerShell e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="32578-117">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="32578-118">`Where-Object` usa um bloco de script, e a propriedade de `$_` **Opções** e a variável automática () e as propriedades representam o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="32578-118">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="32578-119">O parâmetro **ne** (diferente de), seleciona objetos que não têm um valor de **Opções** definido como **constante**.</span><span class="sxs-lookup"><span data-stu-id="32578-119">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant**.</span></span> <span data-ttu-id="32578-120">`Remove-Alias` usa o parâmetro **Force** para remover aliases, incluindo aliases somente leitura, da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32578-120">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="32578-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32578-121">PARAMETERS</span></span>

### <span data-ttu-id="32578-122">-Force</span><span class="sxs-lookup"><span data-stu-id="32578-122">-Force</span></span>

<span data-ttu-id="32578-123">Indica que o cmdlet Remove um alias, incluindo aliases com a propriedade **Option** definida como **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="32578-123">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly**.</span></span> <span data-ttu-id="32578-124">O parâmetro **Force** não pode remover um alias com uma propriedade **Option** definida como **Constant**.</span><span class="sxs-lookup"><span data-stu-id="32578-124">The **Force** parameter can't remove an alias with an **Option** property set to **Constant**.</span></span>

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

### <span data-ttu-id="32578-125">-Name</span><span class="sxs-lookup"><span data-stu-id="32578-125">-Name</span></span>

<span data-ttu-id="32578-126">Especifica o nome do alias a ser removido.</span><span class="sxs-lookup"><span data-stu-id="32578-126">Specifies the name of the alias to remove.</span></span>

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

### <span data-ttu-id="32578-127">-Escopo</span><span class="sxs-lookup"><span data-stu-id="32578-127">-Scope</span></span>

<span data-ttu-id="32578-128">Afeta somente os aliases no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="32578-128">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="32578-129">O escopo padrão é **local**.</span><span class="sxs-lookup"><span data-stu-id="32578-129">The default scope is **Local**.</span></span> <span data-ttu-id="32578-130">Para obter mais informações, consulte [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="32578-130">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="32578-131">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="32578-131">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="32578-132">Global</span><span class="sxs-lookup"><span data-stu-id="32578-132">Global</span></span>
- <span data-ttu-id="32578-133">Local</span><span class="sxs-lookup"><span data-stu-id="32578-133">Local</span></span>
- <span data-ttu-id="32578-134">Script</span><span class="sxs-lookup"><span data-stu-id="32578-134">Script</span></span>
- <span data-ttu-id="32578-135">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="32578-135">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

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

### <span data-ttu-id="32578-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32578-136">CommonParameters</span></span>

<span data-ttu-id="32578-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32578-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32578-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="32578-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32578-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="32578-139">INPUTS</span></span>

### <span data-ttu-id="32578-140">System.String[]</span><span class="sxs-lookup"><span data-stu-id="32578-140">System.String[]</span></span>

<span data-ttu-id="32578-141">É possível canalizar um objeto de alias para **Remove-alias**.</span><span class="sxs-lookup"><span data-stu-id="32578-141">You can pipe an alias object to **Remove-Alias**.</span></span>

## <span data-ttu-id="32578-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="32578-142">OUTPUTS</span></span>

### <span data-ttu-id="32578-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="32578-143">None</span></span>

<span data-ttu-id="32578-144">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="32578-144">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="32578-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="32578-145">NOTES</span></span>

<span data-ttu-id="32578-146">As alterações afetam apenas o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="32578-146">Changes only affect the current scope.</span></span> <span data-ttu-id="32578-147">Para remover um alias de todas as sessões, adicione um comando **Remove-alias** ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32578-147">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="32578-148">Para obter mais informações, consulte [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span><span class="sxs-lookup"><span data-stu-id="32578-148">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="32578-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="32578-149">RELATED LINKS</span></span>

[<span data-ttu-id="32578-150">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="32578-150">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="32578-151">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-151">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="32578-152">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-152">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="32578-153">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-153">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="32578-154">New-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-154">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="32578-155">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="32578-155">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="32578-156">Where-Object</span><span class="sxs-lookup"><span data-stu-id="32578-156">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

