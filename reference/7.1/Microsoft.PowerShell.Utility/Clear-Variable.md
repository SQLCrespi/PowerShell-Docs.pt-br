---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: e42371a58b49a25a9aaf0cc60551ff4bf27e2ec4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194744"
---
# <span data-ttu-id="6e01b-103">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="6e01b-103">Clear-Variable</span></span>

## <span data-ttu-id="6e01b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6e01b-104">SYNOPSIS</span></span>
<span data-ttu-id="6e01b-105">Excluir o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="6e01b-105">Deletes the value of a variable.</span></span>

## <span data-ttu-id="6e01b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e01b-106">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6e01b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e01b-107">DESCRIPTION</span></span>

<span data-ttu-id="6e01b-108">O cmdlet **Clear-Variable** exclui os dados armazenados em uma variável, mas não exclui a variável.</span><span class="sxs-lookup"><span data-stu-id="6e01b-108">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="6e01b-109">Como resultado, o valor da variável é NULL (vazio).</span><span class="sxs-lookup"><span data-stu-id="6e01b-109">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="6e01b-110">Se a variável tiver um tipo de dados ou objeto especificado, esse cmdlet preservará o tipo do objeto armazenado na variável.</span><span class="sxs-lookup"><span data-stu-id="6e01b-110">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="6e01b-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6e01b-111">EXAMPLES</span></span>

### <span data-ttu-id="6e01b-112">Exemplo 1: remover o valor de variáveis globais que começam com uma cadeia de caracteres de pesquisa</span><span class="sxs-lookup"><span data-stu-id="6e01b-112">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="6e01b-113">Esse comando Remove o valor de variáveis globais que têm nomes que começam com My.</span><span class="sxs-lookup"><span data-stu-id="6e01b-113">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="6e01b-114">Exemplo 2: limpar uma variável em um escopo filho, mas não no escopo pai</span><span class="sxs-lookup"><span data-stu-id="6e01b-114">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="6e01b-115">Esses comandos demonstram que apagar uma variável em um escopo filho não apaga o valor no escopo pai.</span><span class="sxs-lookup"><span data-stu-id="6e01b-115">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="6e01b-116">O primeiro comando define o valor da variável $A como 3.</span><span class="sxs-lookup"><span data-stu-id="6e01b-116">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="6e01b-117">O segundo comando usa o operador Invoke (&) para executar o comando **Clear-Variable** em um novo escopo.</span><span class="sxs-lookup"><span data-stu-id="6e01b-117">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="6e01b-118">A variável é apagada no escopo filho (embora ela não exista), mas não será apagada no escopo local.</span><span class="sxs-lookup"><span data-stu-id="6e01b-118">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="6e01b-119">O terceiro comando, que obtém o valor de $A, mostra que o valor 3 não é afetado.</span><span class="sxs-lookup"><span data-stu-id="6e01b-119">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="6e01b-120">Exemplo 3: excluir o valor da variável especificada</span><span class="sxs-lookup"><span data-stu-id="6e01b-120">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="6e01b-121">Esse comando exclui o valor da variável chamada Processes.</span><span class="sxs-lookup"><span data-stu-id="6e01b-121">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="6e01b-122">Depois que o cmdlet concluir a operação, a variável denominada processos ainda existirá, mas o valor será NULL.</span><span class="sxs-lookup"><span data-stu-id="6e01b-122">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="6e01b-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e01b-123">PARAMETERS</span></span>

### <span data-ttu-id="6e01b-124">-Excluir</span><span class="sxs-lookup"><span data-stu-id="6e01b-124">-Exclude</span></span>

<span data-ttu-id="6e01b-125">Especifica uma matriz de itens que esse cmdlet omite na operação.</span><span class="sxs-lookup"><span data-stu-id="6e01b-125">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="6e01b-126">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="6e01b-126">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="6e01b-127">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="6e01b-127">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="6e01b-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="6e01b-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6e01b-129">-Force</span><span class="sxs-lookup"><span data-stu-id="6e01b-129">-Force</span></span>

<span data-ttu-id="6e01b-130">Permite que o cmdlet apaga uma variável, mesmo se for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6e01b-130">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="6e01b-131">Mesmo usando o parâmetro Force, o cmdlet não pode remover uma constante.</span><span class="sxs-lookup"><span data-stu-id="6e01b-131">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="6e01b-132">-Incluir</span><span class="sxs-lookup"><span data-stu-id="6e01b-132">-Include</span></span>

<span data-ttu-id="6e01b-133">Especifica uma matriz de itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="6e01b-133">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="6e01b-134">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="6e01b-134">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="6e01b-135">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="6e01b-135">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="6e01b-136">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="6e01b-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6e01b-137">-Name</span><span class="sxs-lookup"><span data-stu-id="6e01b-137">-Name</span></span>

<span data-ttu-id="6e01b-138">Especifica o nome da variável a ser apagada.</span><span class="sxs-lookup"><span data-stu-id="6e01b-138">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="6e01b-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="6e01b-139">Wildcards are permitted.</span></span>
<span data-ttu-id="6e01b-140">Este parâmetro é obrigatório, mas o nome do parâmetro ("Name") é opcional.</span><span class="sxs-lookup"><span data-stu-id="6e01b-140">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="6e01b-141">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6e01b-141">-PassThru</span></span>

<span data-ttu-id="6e01b-142">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="6e01b-142">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="6e01b-143">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="6e01b-143">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="6e01b-144">-Escopo</span><span class="sxs-lookup"><span data-stu-id="6e01b-144">-Scope</span></span>

<span data-ttu-id="6e01b-145">Especifica o escopo no qual esse alias é válido.</span><span class="sxs-lookup"><span data-stu-id="6e01b-145">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="6e01b-146">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="6e01b-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6e01b-147">Global</span><span class="sxs-lookup"><span data-stu-id="6e01b-147">Global</span></span>
- <span data-ttu-id="6e01b-148">Local</span><span class="sxs-lookup"><span data-stu-id="6e01b-148">Local</span></span>
- <span data-ttu-id="6e01b-149">script</span><span class="sxs-lookup"><span data-stu-id="6e01b-149">Script</span></span>

<span data-ttu-id="6e01b-150">Você também pode usar um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="6e01b-150">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="6e01b-151">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="6e01b-151">Local is the default.</span></span>
<span data-ttu-id="6e01b-152">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="6e01b-152">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="6e01b-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6e01b-153">-Confirm</span></span>

<span data-ttu-id="6e01b-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e01b-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6e01b-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6e01b-155">-WhatIf</span></span>

<span data-ttu-id="6e01b-156">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="6e01b-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6e01b-157">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="6e01b-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6e01b-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e01b-158">CommonParameters</span></span>

<span data-ttu-id="6e01b-159">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e01b-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e01b-160">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e01b-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e01b-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6e01b-161">INPUTS</span></span>

### <span data-ttu-id="6e01b-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6e01b-162">None</span></span>

<span data-ttu-id="6e01b-163">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e01b-163">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="6e01b-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6e01b-164">OUTPUTS</span></span>

### <span data-ttu-id="6e01b-165">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="6e01b-165">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="6e01b-166">Quando você usa o parâmetro *PassThru* , esse cmdlet gera um objeto **System. Management. Automation. PSVariable** que representa a variável limpa.</span><span class="sxs-lookup"><span data-stu-id="6e01b-166">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="6e01b-167">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="6e01b-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6e01b-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6e01b-168">NOTES</span></span>

* <span data-ttu-id="6e01b-169">Para excluir uma variável, juntamente com seus valores, use Remove-Variable ou Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="6e01b-169">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="6e01b-170">Esse cmdlet não exclui os valores de variáveis que são definidas como constantes ou pertencentes ao sistema, mesmo que você use o parâmetro *Force* .</span><span class="sxs-lookup"><span data-stu-id="6e01b-170">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="6e01b-171">Se a variável que você está limpando não existir, o cmdlet não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="6e01b-171">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="6e01b-172">Ele não cria uma variável com um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="6e01b-172">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="6e01b-173">Você também pode se referir a **Clear-Variable** por seu alias interno, CLV.</span><span class="sxs-lookup"><span data-stu-id="6e01b-173">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="6e01b-174">Para obter mais informações, consulte about_Aliases.</span><span class="sxs-lookup"><span data-stu-id="6e01b-174">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="6e01b-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6e01b-175">RELATED LINKS</span></span>

[<span data-ttu-id="6e01b-176">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="6e01b-176">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="6e01b-177">New-Variable</span><span class="sxs-lookup"><span data-stu-id="6e01b-177">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="6e01b-178">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="6e01b-178">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="6e01b-179">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="6e01b-179">Set-Variable</span></span>](Set-Variable.md)

