---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 7406b2cac771ae7a741af92cd362cce834c59a50
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194005"
---
# <span data-ttu-id="1bc68-103">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-103">Remove-Alias</span></span>

## <span data-ttu-id="1bc68-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1bc68-104">SYNOPSIS</span></span>
<span data-ttu-id="1bc68-105">Remover um alias da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1bc68-105">Remove an alias from the current session.</span></span>

## <span data-ttu-id="1bc68-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1bc68-106">SYNTAX</span></span>

### <span data-ttu-id="1bc68-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bc68-107">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="1bc68-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1bc68-108">DESCRIPTION</span></span>

<span data-ttu-id="1bc68-109">O `Remove-Alias` cmdlet Remove um alias da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bc68-109">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="1bc68-110">Para remover um alias com a propriedade **Option** definida como **ReadOnly** , use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-110">To remove an alias with the **Option** property set to **ReadOnly** , use the **Force** parameter.</span></span>

<span data-ttu-id="1bc68-111">O `Remove-Alias` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1bc68-111">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="1bc68-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1bc68-112">EXAMPLES</span></span>

### <span data-ttu-id="1bc68-113">Exemplo 1-remover um alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-113">Example 1 - Remove an alias</span></span>

<span data-ttu-id="1bc68-114">Este exemplo remove um alias chamado `del` que representa o `Remove-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bc68-114">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="1bc68-115">Exemplo 2-remover todos os aliases não constantes</span><span class="sxs-lookup"><span data-stu-id="1bc68-115">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="1bc68-116">Este exemplo remove todos os aliases da sessão atual do PowerShell, com exceção de aliases com a propriedade **Options** definida como **Constant** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-116">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant** .</span></span> <span data-ttu-id="1bc68-117">Depois que o comando é executado, os aliases estão disponíveis em outras sessões do PowerShell ou novas sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bc68-117">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="1bc68-118">`Get-Alias` Obtém todos os aliases na sessão do PowerShell e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="1bc68-118">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="1bc68-119">`Where-Object` usa um bloco de script, e a propriedade de `$_` **Opções** e a variável automática () e as propriedades representam o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="1bc68-119">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="1bc68-120">O parâmetro **ne** (diferente de), seleciona objetos que não têm um valor de **Opções** definido como **constante** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-120">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant** .</span></span> <span data-ttu-id="1bc68-121">`Remove-Alias` usa o parâmetro **Force** para remover aliases, incluindo aliases somente leitura, da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bc68-121">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="1bc68-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1bc68-122">PARAMETERS</span></span>

### <span data-ttu-id="1bc68-123">-Force</span><span class="sxs-lookup"><span data-stu-id="1bc68-123">-Force</span></span>

<span data-ttu-id="1bc68-124">Indica que o cmdlet Remove um alias, incluindo aliases com a propriedade **Option** definida como **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-124">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly** .</span></span> <span data-ttu-id="1bc68-125">O parâmetro **Force** não pode remover um alias com uma propriedade **Option** definida como **Constant** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-125">The **Force** parameter can't remove an alias with an **Option** property set to **Constant** .</span></span>

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

### <span data-ttu-id="1bc68-126">-Name</span><span class="sxs-lookup"><span data-stu-id="1bc68-126">-Name</span></span>

<span data-ttu-id="1bc68-127">Especifica o nome do alias a ser removido.</span><span class="sxs-lookup"><span data-stu-id="1bc68-127">Specifies the name of the alias to remove.</span></span>

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

### <span data-ttu-id="1bc68-128">-Escopo</span><span class="sxs-lookup"><span data-stu-id="1bc68-128">-Scope</span></span>

<span data-ttu-id="1bc68-129">Afeta somente os aliases no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="1bc68-129">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="1bc68-130">O escopo padrão é **local** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-130">The default scope is **Local** .</span></span> <span data-ttu-id="1bc68-131">Para obter mais informações, consulte [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="1bc68-131">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="1bc68-132">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1bc68-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1bc68-133">Global</span><span class="sxs-lookup"><span data-stu-id="1bc68-133">Global</span></span>
- <span data-ttu-id="1bc68-134">Local</span><span class="sxs-lookup"><span data-stu-id="1bc68-134">Local</span></span>
- <span data-ttu-id="1bc68-135">script</span><span class="sxs-lookup"><span data-stu-id="1bc68-135">Script</span></span>
- <span data-ttu-id="1bc68-136">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="1bc68-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

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

### <span data-ttu-id="1bc68-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1bc68-137">CommonParameters</span></span>

<span data-ttu-id="1bc68-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1bc68-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1bc68-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1bc68-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1bc68-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1bc68-140">INPUTS</span></span>

### <span data-ttu-id="1bc68-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1bc68-141">System.String[]</span></span>

<span data-ttu-id="1bc68-142">É possível canalizar um objeto de alias para **Remove-alias** .</span><span class="sxs-lookup"><span data-stu-id="1bc68-142">You can pipe an alias object to **Remove-Alias** .</span></span>

## <span data-ttu-id="1bc68-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1bc68-143">OUTPUTS</span></span>

### <span data-ttu-id="1bc68-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1bc68-144">None</span></span>

<span data-ttu-id="1bc68-145">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="1bc68-145">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="1bc68-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1bc68-146">NOTES</span></span>

<span data-ttu-id="1bc68-147">As alterações afetam apenas o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="1bc68-147">Changes only affect the current scope.</span></span> <span data-ttu-id="1bc68-148">Para remover um alias de todas as sessões, adicione um comando **Remove-alias** ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bc68-148">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="1bc68-149">Para obter mais informações, consulte [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span><span class="sxs-lookup"><span data-stu-id="1bc68-149">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="1bc68-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1bc68-150">RELATED LINKS</span></span>

[<span data-ttu-id="1bc68-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1bc68-151">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="1bc68-152">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-152">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="1bc68-153">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-153">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="1bc68-154">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-154">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="1bc68-155">New-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-155">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="1bc68-156">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="1bc68-156">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="1bc68-157">Where-Object</span><span class="sxs-lookup"><span data-stu-id="1bc68-157">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

