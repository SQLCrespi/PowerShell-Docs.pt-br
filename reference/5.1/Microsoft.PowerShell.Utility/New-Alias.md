---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: 00ef887dc79e35a6dff299a37bfafa57aebc77db
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193772"
---
# <span data-ttu-id="b7413-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="b7413-103">New-Alias</span></span>

## <span data-ttu-id="b7413-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b7413-104">SYNOPSIS</span></span>
<span data-ttu-id="b7413-105">Cria um novo alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-105">Creates a new alias.</span></span>

## <span data-ttu-id="b7413-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7413-106">SYNTAX</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b7413-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b7413-107">DESCRIPTION</span></span>
<span data-ttu-id="b7413-108">O cmdlet **New-Alias** cria um novo alias na sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7413-108">The **New-Alias** cmdlet creates a new alias in the current Windows PowerShell session.</span></span>
<span data-ttu-id="b7413-109">Os aliases criados usando **New-Alias** não são salvos depois que você sai da sessão ou fecha o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7413-109">Aliases created by using **New-Alias** are not saved after you exit the session or close Windows PowerShell.</span></span>
<span data-ttu-id="b7413-110">Você pode usar o cmdlet Export-Alias para salvar as informações de alias em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7413-110">You can use the Export-Alias cmdlet to save your alias information to a file.</span></span>
<span data-ttu-id="b7413-111">Posteriormente, você poderá usar **Import-Alias** para recuperar as informações de alias salvas.</span><span class="sxs-lookup"><span data-stu-id="b7413-111">You can later use **Import-Alias** to retrieve that saved alias information.</span></span>

## <span data-ttu-id="b7413-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b7413-112">EXAMPLES</span></span>

### <span data-ttu-id="b7413-113">Exemplo 1: criar um alias para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7413-113">Example 1: Create an alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="b7413-114">Este comando cria um alias chamado List para representar o cmdlet Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="b7413-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="b7413-115">Exemplo 2: criar um alias somente leitura para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7413-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

<span data-ttu-id="b7413-116">Esse comando cria um alias chamado W para representar o cmdlet Get-WmiObject.</span><span class="sxs-lookup"><span data-stu-id="b7413-116">This command creates an alias named W to represent the Get-WmiObject cmdlet.</span></span>
<span data-ttu-id="b7413-117">Ele cria uma descrição, alias WMI rápido, para o alias e o torna somente leitura.</span><span class="sxs-lookup"><span data-stu-id="b7413-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span>
<span data-ttu-id="b7413-118">A última linha do comando usa o Get-Alias para obter o novo alias e o redireciona para Format-List para exibir todas as informações sobre ele.</span><span class="sxs-lookup"><span data-stu-id="b7413-118">The last line of the command uses Get-Alias to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="b7413-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7413-119">PARAMETERS</span></span>

### <span data-ttu-id="b7413-120">-Description</span><span class="sxs-lookup"><span data-stu-id="b7413-120">-Description</span></span>
<span data-ttu-id="b7413-121">Especifica uma descrição do alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-121">Specifies a description of the alias.</span></span>
<span data-ttu-id="b7413-122">Você pode digitar qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b7413-122">You can type any string.</span></span>
<span data-ttu-id="b7413-123">Se a descrição incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="b7413-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="b7413-124">-Force</span><span class="sxs-lookup"><span data-stu-id="b7413-124">-Force</span></span>
<span data-ttu-id="b7413-125">Indica que o cmdlet funciona como Set-Alias se o alias chamado já existe.</span><span class="sxs-lookup"><span data-stu-id="b7413-125">Indicates that the cmdlet acts like Set-Alias if the alias named already exists.</span></span>

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

### <span data-ttu-id="b7413-126">-Name</span><span class="sxs-lookup"><span data-stu-id="b7413-126">-Name</span></span>
<span data-ttu-id="b7413-127">Especifica o novo alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-127">Specifies the new alias.</span></span>
<span data-ttu-id="b7413-128">Você pode usar qualquer caractere alfanumérico em um alias, mas o primeiro caractere não pode ser um número.</span><span class="sxs-lookup"><span data-stu-id="b7413-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

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

### <span data-ttu-id="b7413-129">-Opção</span><span class="sxs-lookup"><span data-stu-id="b7413-129">-Option</span></span>
<span data-ttu-id="b7413-130">Especifica o valor da propriedade **Options** do alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="b7413-131">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="b7413-131">Valid values are:</span></span>

- <span data-ttu-id="b7413-132">Nenhum: o alias não tem restrições (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="b7413-132">None: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="b7413-133">ReadOnly: o alias pode ser excluído, mas não pode ser alterado com exceção do uso do parâmetro **Force**</span><span class="sxs-lookup"><span data-stu-id="b7413-133">ReadOnly: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="b7413-134">Constante: o alias não pode ser excluído ou alterado</span><span class="sxs-lookup"><span data-stu-id="b7413-134">Constant: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="b7413-135">Particular: o alias está disponível somente no escopo atual</span><span class="sxs-lookup"><span data-stu-id="b7413-135">Private: The alias is available only in the current scope</span></span>
- <span data-ttu-id="b7413-136">Escopo: o alias é copiado para todos os novos escopos criados</span><span class="sxs-lookup"><span data-stu-id="b7413-136">AllScope: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="b7413-137">Não especificado: a opção não é especificada</span><span class="sxs-lookup"><span data-stu-id="b7413-137">Unspecified: The option is not specified</span></span>

<span data-ttu-id="b7413-138">Para ver a propriedade **Options** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="b7413-138">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

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

### <span data-ttu-id="b7413-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b7413-139">-PassThru</span></span>
<span data-ttu-id="b7413-140">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="b7413-140">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b7413-141">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b7413-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b7413-142">-Escopo</span><span class="sxs-lookup"><span data-stu-id="b7413-142">-Scope</span></span>
<span data-ttu-id="b7413-143">Especifica o escopo do novo alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-143">Specifies the scope of the new alias.</span></span>
<span data-ttu-id="b7413-144">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b7413-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b7413-145">Global</span><span class="sxs-lookup"><span data-stu-id="b7413-145">Global</span></span>
- <span data-ttu-id="b7413-146">Local</span><span class="sxs-lookup"><span data-stu-id="b7413-146">Local</span></span>
- <span data-ttu-id="b7413-147">script</span><span class="sxs-lookup"><span data-stu-id="b7413-147">Script</span></span>
- <span data-ttu-id="b7413-148">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="b7413-148">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="b7413-149">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b7413-149">Local is the default.</span></span>
<span data-ttu-id="b7413-150">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="b7413-150">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="b7413-151">-Value</span><span class="sxs-lookup"><span data-stu-id="b7413-151">-Value</span></span>
<span data-ttu-id="b7413-152">Especifica o nome do elemento de comando ou de cmdlet que está recebendo o alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-152">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

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

### <span data-ttu-id="b7413-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b7413-153">-Confirm</span></span>
<span data-ttu-id="b7413-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b7413-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b7413-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b7413-155">-WhatIf</span></span>
<span data-ttu-id="b7413-156">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b7413-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b7413-157">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b7413-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b7413-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b7413-158">CommonParameters</span></span>
<span data-ttu-id="b7413-159">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b7413-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7413-160">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b7413-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b7413-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b7413-161">INPUTS</span></span>

### <span data-ttu-id="b7413-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b7413-162">None</span></span>
<span data-ttu-id="b7413-163">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b7413-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b7413-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b7413-164">OUTPUTS</span></span>

### <span data-ttu-id="b7413-165">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="b7413-165">None or System.Management.Automation.AliasInfo</span></span>
<span data-ttu-id="b7413-166">Quando você usa o parâmetro *PassThru* , **New-Alias** gera um objeto **System. Management. Automation. AliasInfo** que representa o novo alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-166">When you use the *Passthru* parameter, **New-Alias** generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span>
<span data-ttu-id="b7413-167">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="b7413-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b7413-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b7413-168">NOTES</span></span>

* <span data-ttu-id="b7413-169">Para criar um novo alias, use Set-Alias ou New-Alias.</span><span class="sxs-lookup"><span data-stu-id="b7413-169">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="b7413-170">Para alterar um alias, use **set-alias** .</span><span class="sxs-lookup"><span data-stu-id="b7413-170">To change an alias, use **Set-Alias** .</span></span> <span data-ttu-id="b7413-171">Para excluir um alias, use Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="b7413-171">To delete an alias, use Remove-Item.</span></span>

*

## <span data-ttu-id="b7413-172">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b7413-172">RELATED LINKS</span></span>

[<span data-ttu-id="b7413-173">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="b7413-173">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="b7413-174">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b7413-174">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="b7413-175">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="b7413-175">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="b7413-176">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="b7413-176">Set-Alias</span></span>](Set-Alias.md)
