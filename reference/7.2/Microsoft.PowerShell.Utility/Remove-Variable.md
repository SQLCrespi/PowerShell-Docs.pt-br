---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 6b9d351b5092d96d7698a28d3de63a493d566c6d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597639"
---
# <span data-ttu-id="f3add-102">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="f3add-102">Remove-Variable</span></span>

## <span data-ttu-id="f3add-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f3add-103">SYNOPSIS</span></span>
<span data-ttu-id="f3add-104">Exclui uma variável e seu valor.</span><span class="sxs-lookup"><span data-stu-id="f3add-104">Deletes a variable and its value.</span></span>

## <span data-ttu-id="f3add-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f3add-105">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f3add-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f3add-106">DESCRIPTION</span></span>

<span data-ttu-id="f3add-107">O `Remove-Variable` cmdlet exclui uma variável e seu valor do escopo no qual ela é definida, como a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f3add-107">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="f3add-108">Não é possível utilizar este cmdlet para excluir as variáveis que são definidas como constantes ou aqueles que são de propriedade do sistema.</span><span class="sxs-lookup"><span data-stu-id="f3add-108">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="f3add-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f3add-109">EXAMPLES</span></span>

### <span data-ttu-id="f3add-110">Exemplo 1: remover uma variável</span><span class="sxs-lookup"><span data-stu-id="f3add-110">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="f3add-111">Esse comando exclui a `$Smp` variável.</span><span class="sxs-lookup"><span data-stu-id="f3add-111">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="f3add-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f3add-112">PARAMETERS</span></span>

### <span data-ttu-id="f3add-113">-Excluir</span><span class="sxs-lookup"><span data-stu-id="f3add-113">-Exclude</span></span>

<span data-ttu-id="f3add-114">Especifica uma matriz de itens que esse cmdlet omite da operação.</span><span class="sxs-lookup"><span data-stu-id="f3add-114">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="f3add-115">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="f3add-115">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f3add-116">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="f3add-116">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="f3add-117">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f3add-117">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f3add-118">-Force</span><span class="sxs-lookup"><span data-stu-id="f3add-118">-Force</span></span>

<span data-ttu-id="f3add-119">Indica que o cmdlet Remove uma variável, mesmo se for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f3add-119">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="f3add-120">Mesmo usando o parâmetro **Force** , o cmdlet não pode remover uma constante.</span><span class="sxs-lookup"><span data-stu-id="f3add-120">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="f3add-121">-Incluir</span><span class="sxs-lookup"><span data-stu-id="f3add-121">-Include</span></span>

<span data-ttu-id="f3add-122">Especifica uma matriz de itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="f3add-122">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="f3add-123">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="f3add-123">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f3add-124">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="f3add-124">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="f3add-125">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f3add-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f3add-126">-Name</span><span class="sxs-lookup"><span data-stu-id="f3add-126">-Name</span></span>

<span data-ttu-id="f3add-127">Especifica o nome da variável a ser removida.</span><span class="sxs-lookup"><span data-stu-id="f3add-127">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="f3add-128">O nome do parâmetro (**Name**) é opcional.</span><span class="sxs-lookup"><span data-stu-id="f3add-128">The parameter name (**Name**) is optional.</span></span>
<span data-ttu-id="f3add-129">Caracteres curinga são permitidos</span><span class="sxs-lookup"><span data-stu-id="f3add-129">Wildcards are permitted</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f3add-130">-Escopo</span><span class="sxs-lookup"><span data-stu-id="f3add-130">-Scope</span></span>

<span data-ttu-id="f3add-131">Ele obtém somente as variáveis no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="f3add-131">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="f3add-132">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f3add-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f3add-133">Global</span><span class="sxs-lookup"><span data-stu-id="f3add-133">Global</span></span>
- <span data-ttu-id="f3add-134">Local</span><span class="sxs-lookup"><span data-stu-id="f3add-134">Local</span></span>
- <span data-ttu-id="f3add-135">Script</span><span class="sxs-lookup"><span data-stu-id="f3add-135">Script</span></span>
- <span data-ttu-id="f3add-136">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="f3add-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="f3add-137">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="f3add-137">Local is the default.</span></span> <span data-ttu-id="f3add-138">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="f3add-138">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="f3add-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f3add-139">-Confirm</span></span>

<span data-ttu-id="f3add-140">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3add-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f3add-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f3add-141">-WhatIf</span></span>

<span data-ttu-id="f3add-142">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f3add-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f3add-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f3add-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f3add-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f3add-144">CommonParameters</span></span>

<span data-ttu-id="f3add-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f3add-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f3add-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f3add-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f3add-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f3add-147">INPUTS</span></span>

### <span data-ttu-id="f3add-148">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="f3add-148">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="f3add-149">É possível canalizar um objeto de variável para `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="f3add-149">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="f3add-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f3add-150">OUTPUTS</span></span>

### <span data-ttu-id="f3add-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f3add-151">None</span></span>

<span data-ttu-id="f3add-152">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f3add-152">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="f3add-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f3add-153">NOTES</span></span>

- <span data-ttu-id="f3add-154">As alterações afetam apenas o escopo atual como uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f3add-154">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="f3add-155">Para excluir uma variável de todas as sessões, adicione um `Remove-Variable` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3add-155">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="f3add-156">Você também pode consultar `Remove-Variable` por seu alias interno, `rv` .</span><span class="sxs-lookup"><span data-stu-id="f3add-156">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="f3add-157">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="f3add-157">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="f3add-158">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f3add-158">RELATED LINKS</span></span>

[<span data-ttu-id="f3add-159">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="f3add-159">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="f3add-160">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="f3add-160">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="f3add-161">New-Variable</span><span class="sxs-lookup"><span data-stu-id="f3add-161">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="f3add-162">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="f3add-162">Set-Variable</span></span>](Set-Variable.md)
