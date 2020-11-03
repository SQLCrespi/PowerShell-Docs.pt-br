---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: 128bdd997e006723a69997e1419efd2f012e97f6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193179"
---
# <span data-ttu-id="614bb-103">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="614bb-103">Get-Variable</span></span>

## <span data-ttu-id="614bb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="614bb-104">SYNOPSIS</span></span>
<span data-ttu-id="614bb-105">Obtém as variáveis no console atual.</span><span class="sxs-lookup"><span data-stu-id="614bb-105">Gets the variables in the current console.</span></span>

## <span data-ttu-id="614bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="614bb-106">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="614bb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="614bb-107">DESCRIPTION</span></span>

<span data-ttu-id="614bb-108">O `Get-Variable` cmdlet obtém as variáveis do PowerShell no console atual.</span><span class="sxs-lookup"><span data-stu-id="614bb-108">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="614bb-109">Você pode recuperar apenas os valores das variáveis especificando o parâmetro **ValueOnly** , além de filtrar por nome as variáveis retornadas.</span><span class="sxs-lookup"><span data-stu-id="614bb-109">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="614bb-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="614bb-110">EXAMPLES</span></span>

### <span data-ttu-id="614bb-111">Exemplo 1: obter variáveis por letra</span><span class="sxs-lookup"><span data-stu-id="614bb-111">Example 1: Get variables by letter</span></span>

<span data-ttu-id="614bb-112">Esse comando obtém variáveis com nomes que começam com a letra m.</span><span class="sxs-lookup"><span data-stu-id="614bb-112">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="614bb-113">O comando também obtém o valor das variáveis.</span><span class="sxs-lookup"><span data-stu-id="614bb-113">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="614bb-114">Exemplo 2: obter valores de variáveis por letra</span><span class="sxs-lookup"><span data-stu-id="614bb-114">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="614bb-115">Esse comando obtém somente os valores das variáveis que têm nomes que começam com m.</span><span class="sxs-lookup"><span data-stu-id="614bb-115">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="614bb-116">Exemplo 3: obter variáveis por duas letras</span><span class="sxs-lookup"><span data-stu-id="614bb-116">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="614bb-117">Esse comando obtém informações sobre as variáveis que começam com a letra M ou a letra P.</span><span class="sxs-lookup"><span data-stu-id="614bb-117">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="614bb-118">Exemplo 4: obter variáveis por escopo</span><span class="sxs-lookup"><span data-stu-id="614bb-118">Example 4: Get variables by scope</span></span>

<span data-ttu-id="614bb-119">O primeiro comando obtém apenas as variáveis que estão definidas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="614bb-119">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="614bb-120">É equivalente a `Get-Variable -Scope Local` e pode ser abreviado como `gv -s 0` .</span><span class="sxs-lookup"><span data-stu-id="614bb-120">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="614bb-121">O segundo comando usa o `Compare-Object` cmdlet para localizar as variáveis que são definidas no escopo pai (escopo 1), mas são visíveis apenas no escopo local (escopo 0).</span><span class="sxs-lookup"><span data-stu-id="614bb-121">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="614bb-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="614bb-122">PARAMETERS</span></span>

### <span data-ttu-id="614bb-123">-Excluir</span><span class="sxs-lookup"><span data-stu-id="614bb-123">-Exclude</span></span>

<span data-ttu-id="614bb-124">Especifica uma matriz de itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="614bb-124">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="614bb-125">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="614bb-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="614bb-126">-Incluir</span><span class="sxs-lookup"><span data-stu-id="614bb-126">-Include</span></span>

<span data-ttu-id="614bb-127">Especifica uma matriz de itens sobre a qual o cmdlet atuará, excluindo todos os outros.</span><span class="sxs-lookup"><span data-stu-id="614bb-127">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="614bb-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="614bb-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="614bb-129">-Name</span><span class="sxs-lookup"><span data-stu-id="614bb-129">-Name</span></span>

<span data-ttu-id="614bb-130">Especifica o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="614bb-130">Specifies the name of the variable.</span></span>
<span data-ttu-id="614bb-131">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="614bb-131">Wildcards are permitted.</span></span>
<span data-ttu-id="614bb-132">Também é possível canalizar um nome de variável para `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="614bb-132">You can also pipe a variable name to `Get-Variable`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="614bb-133">-Escopo</span><span class="sxs-lookup"><span data-stu-id="614bb-133">-Scope</span></span>

<span data-ttu-id="614bb-134">Especifica as variáveis no escopo. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="614bb-134">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="614bb-135">**Global**</span><span class="sxs-lookup"><span data-stu-id="614bb-135">**Global**</span></span>
- <span data-ttu-id="614bb-136">**Local**</span><span class="sxs-lookup"><span data-stu-id="614bb-136">**Local**</span></span>
- <span data-ttu-id="614bb-137">**script**</span><span class="sxs-lookup"><span data-stu-id="614bb-137">**Script**</span></span>
- <span data-ttu-id="614bb-138">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="614bb-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="614bb-139">**Local** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="614bb-139">**Local** is the default.</span></span>
<span data-ttu-id="614bb-140">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="614bb-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="614bb-141">-ValueOnly</span><span class="sxs-lookup"><span data-stu-id="614bb-141">-ValueOnly</span></span>

<span data-ttu-id="614bb-142">Indica que esse cmdlet obtém apenas o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="614bb-142">Indicates that this cmdlet gets only the value of the variable.</span></span>

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

### <span data-ttu-id="614bb-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="614bb-143">CommonParameters</span></span>

<span data-ttu-id="614bb-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="614bb-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="614bb-145">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="614bb-145">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="614bb-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="614bb-146">INPUTS</span></span>

### <span data-ttu-id="614bb-147">System.String</span><span class="sxs-lookup"><span data-stu-id="614bb-147">System.String</span></span>

<span data-ttu-id="614bb-148">É possível canalizar uma cadeia de caracteres que contém o nome da variável para `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="614bb-148">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="614bb-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="614bb-149">OUTPUTS</span></span>

### <span data-ttu-id="614bb-150">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="614bb-150">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="614bb-151">Esse cmdlet retorna um objeto **System. Management. AutomationPSVariable** para cada variável obtida.</span><span class="sxs-lookup"><span data-stu-id="614bb-151">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="614bb-152">O tipo de objeto depende da variável.</span><span class="sxs-lookup"><span data-stu-id="614bb-152">The object type depends on the variable.</span></span>

### <span data-ttu-id="614bb-153">System. Object []</span><span class="sxs-lookup"><span data-stu-id="614bb-153">System.Object[]</span></span>

<span data-ttu-id="614bb-154">Quando você especifica o parâmetro **valueonly** , se o valor da variável especificada for uma coleção, `Get-Variable` retornará um `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="614bb-154">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="614bb-155">Esse comportamento impede que a operação normal de pipeline processe os valores da variável um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="614bb-155">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="614bb-156">Uma solução alternativa para forçar a enumeração da coleção é colocar o `Get-Variable` comando entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="614bb-156">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="614bb-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="614bb-157">NOTES</span></span>

- <span data-ttu-id="614bb-158">Este cmdlet não gerencia as variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="614bb-158">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="614bb-159">Para gerenciar variáveis de ambiente, você pode usar o provedor de variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="614bb-159">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="614bb-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="614bb-160">RELATED LINKS</span></span>

[<span data-ttu-id="614bb-161">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="614bb-161">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="614bb-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="614bb-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="614bb-163">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="614bb-163">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="614bb-164">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="614bb-164">Set-Variable</span></span>](Set-Variable.md)
