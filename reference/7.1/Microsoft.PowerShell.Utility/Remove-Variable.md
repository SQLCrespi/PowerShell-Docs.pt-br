---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: e6bbb1415a29b8dc3ef916ecc6c3e8bc6754583d
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195056"
---
# <span data-ttu-id="831b6-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="831b6-103">Remove-Variable</span></span>

## <span data-ttu-id="831b6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="831b6-104">SYNOPSIS</span></span>
<span data-ttu-id="831b6-105">Exclui uma variável e seu valor.</span><span class="sxs-lookup"><span data-stu-id="831b6-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="831b6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="831b6-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="831b6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="831b6-107">DESCRIPTION</span></span>

<span data-ttu-id="831b6-108">O `Remove-Variable` cmdlet exclui uma variável e seu valor do escopo no qual ela é definida, como a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="831b6-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="831b6-109">Não é possível utilizar este cmdlet para excluir as variáveis que são definidas como constantes ou aqueles que são de propriedade do sistema.</span><span class="sxs-lookup"><span data-stu-id="831b6-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="831b6-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="831b6-110">EXAMPLES</span></span>

### <span data-ttu-id="831b6-111">Exemplo 1: remover uma variável</span><span class="sxs-lookup"><span data-stu-id="831b6-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="831b6-112">Esse comando exclui a `$Smp` variável.</span><span class="sxs-lookup"><span data-stu-id="831b6-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="831b6-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="831b6-113">PARAMETERS</span></span>

### <span data-ttu-id="831b6-114">-Excluir</span><span class="sxs-lookup"><span data-stu-id="831b6-114">-Exclude</span></span>

<span data-ttu-id="831b6-115">Especifica uma matriz de itens que esse cmdlet omite da operação.</span><span class="sxs-lookup"><span data-stu-id="831b6-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="831b6-116">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="831b6-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="831b6-117">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="831b6-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="831b6-118">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="831b6-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="831b6-119">-Force</span><span class="sxs-lookup"><span data-stu-id="831b6-119">-Force</span></span>

<span data-ttu-id="831b6-120">Indica que o cmdlet Remove uma variável, mesmo se for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="831b6-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="831b6-121">Mesmo usando o parâmetro **Force** , o cmdlet não pode remover uma constante.</span><span class="sxs-lookup"><span data-stu-id="831b6-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="831b6-122">-Incluir</span><span class="sxs-lookup"><span data-stu-id="831b6-122">-Include</span></span>

<span data-ttu-id="831b6-123">Especifica uma matriz de itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="831b6-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="831b6-124">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="831b6-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="831b6-125">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="831b6-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="831b6-126">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="831b6-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="831b6-127">-Name</span><span class="sxs-lookup"><span data-stu-id="831b6-127">-Name</span></span>

<span data-ttu-id="831b6-128">Especifica o nome da variável a ser removida.</span><span class="sxs-lookup"><span data-stu-id="831b6-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="831b6-129">O nome do parâmetro ( **Name** ) é opcional.</span><span class="sxs-lookup"><span data-stu-id="831b6-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="831b6-130">Caracteres curinga são permitidos</span><span class="sxs-lookup"><span data-stu-id="831b6-130">Wildcards are permitted</span></span>

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

### <span data-ttu-id="831b6-131">-Escopo</span><span class="sxs-lookup"><span data-stu-id="831b6-131">-Scope</span></span>

<span data-ttu-id="831b6-132">Ele obtém somente as variáveis no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="831b6-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="831b6-133">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="831b6-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="831b6-134">Global</span><span class="sxs-lookup"><span data-stu-id="831b6-134">Global</span></span>
- <span data-ttu-id="831b6-135">Local</span><span class="sxs-lookup"><span data-stu-id="831b6-135">Local</span></span>
- <span data-ttu-id="831b6-136">script</span><span class="sxs-lookup"><span data-stu-id="831b6-136">Script</span></span>
- <span data-ttu-id="831b6-137">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="831b6-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="831b6-138">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="831b6-138">Local is the default.</span></span> <span data-ttu-id="831b6-139">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="831b6-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="831b6-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="831b6-140">-Confirm</span></span>

<span data-ttu-id="831b6-141">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="831b6-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="831b6-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="831b6-142">-WhatIf</span></span>

<span data-ttu-id="831b6-143">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="831b6-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="831b6-144">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="831b6-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="831b6-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="831b6-145">CommonParameters</span></span>

<span data-ttu-id="831b6-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="831b6-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="831b6-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="831b6-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="831b6-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="831b6-148">INPUTS</span></span>

### <span data-ttu-id="831b6-149">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="831b6-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="831b6-150">É possível canalizar um objeto de variável para `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="831b6-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="831b6-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="831b6-151">OUTPUTS</span></span>

### <span data-ttu-id="831b6-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="831b6-152">None</span></span>

<span data-ttu-id="831b6-153">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="831b6-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="831b6-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="831b6-154">NOTES</span></span>

- <span data-ttu-id="831b6-155">As alterações afetam apenas o escopo atual como uma sessão.</span><span class="sxs-lookup"><span data-stu-id="831b6-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="831b6-156">Para excluir uma variável de todas as sessões, adicione um `Remove-Variable` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="831b6-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="831b6-157">Você também pode consultar `Remove-Variable` por seu alias interno, `rv` .</span><span class="sxs-lookup"><span data-stu-id="831b6-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="831b6-158">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="831b6-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="831b6-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="831b6-159">RELATED LINKS</span></span>

[<span data-ttu-id="831b6-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="831b6-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="831b6-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="831b6-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="831b6-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="831b6-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="831b6-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="831b6-163">Set-Variable</span></span>](Set-Variable.md)
