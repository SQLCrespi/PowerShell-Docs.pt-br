---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: ec442dd1e24774b21cf9e00f2e46226d0b714432
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274214"
---
# <span data-ttu-id="d4ab6-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="d4ab6-103">New-Alias</span></span>

## <span data-ttu-id="d4ab6-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d4ab6-104">Synopsis</span></span>
<span data-ttu-id="d4ab6-105">Cria um novo alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-105">Creates a new alias.</span></span>

## <span data-ttu-id="d4ab6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d4ab6-106">Syntax</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d4ab6-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4ab6-107">Description</span></span>

<span data-ttu-id="d4ab6-108">O `New-Alias` cmdlet cria um novo alias na sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-108">The `New-Alias` cmdlet creates a new alias in the current Windows PowerShell session.</span></span> <span data-ttu-id="d4ab6-109">Os aliases criados por meio `New-Alias` do não são salvos depois que você sai da sessão ou fecha o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-109">Aliases created by using `New-Alias` are not saved after you exit the session or close Windows PowerShell.</span></span>
<span data-ttu-id="d4ab6-110">Você pode usar o `Export-Alias` cmdlet para salvar suas informações de alias em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-110">You can use the `Export-Alias` cmdlet to save your alias information to a file.</span></span> <span data-ttu-id="d4ab6-111">Posteriormente, você pode usar `Import-Alias` para recuperar as informações de alias salvas.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-111">You can later use `Import-Alias` to retrieve that saved alias information.</span></span>

## <span data-ttu-id="d4ab6-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d4ab6-112">Examples</span></span>

### <span data-ttu-id="d4ab6-113">Exemplo 1: criar um alias para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="d4ab6-113">Example 1: Create an alias for a cmdlet</span></span>

```
New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="d4ab6-114">Este comando cria um alias chamado List para representar o cmdlet Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="d4ab6-115">Exemplo 2: criar um alias somente leitura para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="d4ab6-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
New-Alias -Name "C" -Value Get-ChildItem -Description "quick gci alias" -Option ReadOnly
Get-Alias -Name "C" | Format-List *
```

<span data-ttu-id="d4ab6-116">Este comando cria um alias chamado `C` para representar o `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-116">This command creates an alias named `C` to represent the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="d4ab6-117">Ele cria uma descrição, alias WMI rápido, para o alias e o torna somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span> <span data-ttu-id="d4ab6-118">A última linha do comando usa `Get-Alias` para obter o novo alias e o canaliza para Format-List para exibir todas as informações sobre ele.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-118">The last line of the command uses `Get-Alias` to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="d4ab6-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d4ab6-119">Parameters</span></span>

### <span data-ttu-id="d4ab6-120">-Description</span><span class="sxs-lookup"><span data-stu-id="d4ab6-120">-Description</span></span>

<span data-ttu-id="d4ab6-121">Especifica uma descrição do alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-121">Specifies a description of the alias.</span></span> <span data-ttu-id="d4ab6-122">Você pode digitar qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-122">You can type any string.</span></span> <span data-ttu-id="d4ab6-123">Se a descrição incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="d4ab6-124">-Force</span><span class="sxs-lookup"><span data-stu-id="d4ab6-124">-Force</span></span>

<span data-ttu-id="d4ab6-125">Indica que o cmdlet funciona como `Set-Alias` se o alias chamado já existir.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-125">Indicates that the cmdlet acts like `Set-Alias` if the alias named already exists.</span></span>

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

### <span data-ttu-id="d4ab6-126">-Name</span><span class="sxs-lookup"><span data-stu-id="d4ab6-126">-Name</span></span>

<span data-ttu-id="d4ab6-127">Especifica o novo alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-127">Specifies the new alias.</span></span> <span data-ttu-id="d4ab6-128">Você pode usar qualquer caractere alfanumérico em um alias, mas o primeiro caractere não pode ser um número.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

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

### <span data-ttu-id="d4ab6-129">-Opção</span><span class="sxs-lookup"><span data-stu-id="d4ab6-129">-Option</span></span>

<span data-ttu-id="d4ab6-130">Especifica o valor da propriedade **Options** do alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="d4ab6-131">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="d4ab6-131">Valid values are:</span></span>

- <span data-ttu-id="d4ab6-132">`None`: O alias não tem restrições (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="d4ab6-132">`None`: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="d4ab6-133">`ReadOnly`: O alias pode ser excluído, mas não pode ser alterado com exceção do uso do parâmetro **Force**</span><span class="sxs-lookup"><span data-stu-id="d4ab6-133">`ReadOnly`: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="d4ab6-134">`Constant`: O alias não pode ser excluído ou alterado</span><span class="sxs-lookup"><span data-stu-id="d4ab6-134">`Constant`: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="d4ab6-135">`Private`: O alias está disponível somente no escopo atual</span><span class="sxs-lookup"><span data-stu-id="d4ab6-135">`Private`: The alias is available only in the current scope</span></span>
- <span data-ttu-id="d4ab6-136">`AllScope`: O alias é copiado para todos os novos escopos criados</span><span class="sxs-lookup"><span data-stu-id="d4ab6-136">`AllScope`: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="d4ab6-137">`Unspecified`: A opção não foi especificada</span><span class="sxs-lookup"><span data-stu-id="d4ab6-137">`Unspecified`: The option is not specified</span></span>

<span data-ttu-id="d4ab6-138">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-138">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="d4ab6-139">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-139">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="d4ab6-140">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-140">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="d4ab6-141">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-141">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="d4ab6-142">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-142">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

<span data-ttu-id="d4ab6-143">Para ver a propriedade **Options** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="d4ab6-143">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4ab6-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d4ab6-144">-PassThru</span></span>

<span data-ttu-id="d4ab6-145">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-145">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="d4ab6-146">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d4ab6-147">-Escopo</span><span class="sxs-lookup"><span data-stu-id="d4ab6-147">-Scope</span></span>

<span data-ttu-id="d4ab6-148">Especifica o escopo do novo alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-148">Specifies the scope of the new alias.</span></span> <span data-ttu-id="d4ab6-149">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d4ab6-149">The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- <span data-ttu-id="d4ab6-150">Um número relativo ao escopo atual (0 até o número de escopos, em que `0` é o escopo atual e `1` é seu pai).</span><span class="sxs-lookup"><span data-stu-id="d4ab6-150">A number relative to the current scope (0 through the number of scopes, where `0` is the current scope and `1` is its parent).</span></span>

<span data-ttu-id="d4ab6-151">`Local` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-151">`Local` is the default.</span></span> <span data-ttu-id="d4ab6-152">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="d4ab6-152">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="d4ab6-153">-Value</span><span class="sxs-lookup"><span data-stu-id="d4ab6-153">-Value</span></span>

<span data-ttu-id="d4ab6-154">Especifica o nome do elemento de comando ou de cmdlet que está recebendo o alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-154">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

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

### <span data-ttu-id="d4ab6-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d4ab6-155">-Confirm</span></span>

<span data-ttu-id="d4ab6-156">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d4ab6-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d4ab6-157">-WhatIf</span></span>

<span data-ttu-id="d4ab6-158">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-158">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d4ab6-159">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d4ab6-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d4ab6-160">CommonParameters</span></span>

<span data-ttu-id="d4ab6-161">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4ab6-162">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d4ab6-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d4ab6-163">Entradas</span><span class="sxs-lookup"><span data-stu-id="d4ab6-163">Inputs</span></span>

### <span data-ttu-id="d4ab6-164">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d4ab6-164">None</span></span>

<span data-ttu-id="d4ab6-165">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-165">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d4ab6-166">Saídas</span><span class="sxs-lookup"><span data-stu-id="d4ab6-166">Outputs</span></span>

### <span data-ttu-id="d4ab6-167">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="d4ab6-167">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="d4ab6-168">Quando você usa o parâmetro **PassThru** , o `New-Alias` gera um objeto **System. Management. Automation. AliasInfo** que representa o novo alias.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-168">When you use the **Passthru** parameter, `New-Alias` generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span> <span data-ttu-id="d4ab6-169">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d4ab6-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d4ab6-170">Observações</span><span class="sxs-lookup"><span data-stu-id="d4ab6-170">Notes</span></span>

- <span data-ttu-id="d4ab6-171">Para criar um novo alias, use `Set-Alias` ou `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="d4ab6-171">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="d4ab6-172">Para alterar um alias, use `Set-Alias` .</span><span class="sxs-lookup"><span data-stu-id="d4ab6-172">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="d4ab6-173">Para excluir um alias, use `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="d4ab6-173">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="d4ab6-174">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="d4ab6-174">Related Links</span></span>

[<span data-ttu-id="d4ab6-175">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="d4ab6-175">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="d4ab6-176">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="d4ab6-176">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="d4ab6-177">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="d4ab6-177">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="d4ab6-178">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="d4ab6-178">Set-Alias</span></span>](Set-Alias.md)
