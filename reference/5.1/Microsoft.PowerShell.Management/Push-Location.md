---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: abc40f3ae388a915c9df42d0c2df24f848e45e73
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "93195130"
---
# <span data-ttu-id="7d1c4-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="7d1c4-103">Push-Location</span></span>

## <span data-ttu-id="7d1c4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7d1c4-104">SYNOPSIS</span></span>
<span data-ttu-id="7d1c4-105">Adiciona o local atual no topo de uma pilha de local.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="7d1c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d1c4-106">SYNTAX</span></span>

### <span data-ttu-id="7d1c4-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="7d1c4-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="7d1c4-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7d1c4-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="7d1c4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7d1c4-109">DESCRIPTION</span></span>

<span data-ttu-id="7d1c4-110">O `Push-Location` cmdlet adiciona ("envia") o local atual em uma pilha de local.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="7d1c4-111">Se você especificar um caminho, `Push-Location` o enviará o local atual para uma pilha de local e, em seguida, alterará o local atual para o local especificado pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="7d1c4-112">Você pode usar o `Pop-Location` cmdlet para obter locais da pilha de locais.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="7d1c4-113">Por padrão, o `Push-Location` cmdlet envia o local atual para a pilha de locais atual, mas você pode usar o parâmetro **StackName** para especificar uma pilha de local alternativa.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="7d1c4-114">Se a pilha não existir, a `Push-Location` criará.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="7d1c4-115">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="7d1c4-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7d1c4-116">EXAMPLES</span></span>

### <span data-ttu-id="7d1c4-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="7d1c4-117">Example 1</span></span>

<span data-ttu-id="7d1c4-118">Este exemplo envia por push o local atual para a pilha de locais padrão e, em seguida, altera o local para `C:\Windows` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="7d1c4-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="7d1c4-119">Example 2</span></span>

<span data-ttu-id="7d1c4-120">Este exemplo envia por push o local atual para a pilha RegFunction e altera o local atual para o `HKLM:\Software\Policies` local.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="7d1c4-121">Você pode usar os cmdlets de local em qualquer unidade do PowerShell (PSDrive).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="7d1c4-122">Exemplo 3:</span><span class="sxs-lookup"><span data-stu-id="7d1c4-122">Example 3</span></span>

<span data-ttu-id="7d1c4-123">Esse comando envia o local atual para a pilha padrão.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="7d1c4-124">O local não é alterado.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="7d1c4-125">Exemplo 4-criar e usar uma pilha nomeada</span><span class="sxs-lookup"><span data-stu-id="7d1c4-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="7d1c4-126">Esses comandos mostram como criar e usar uma pilha local nomeada.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="7d1c4-127">O primeiro comando envia o local atual para uma nova pilha chamada Stack2 e, em seguida, altera o local atual para o diretório base, representado no comando pelo símbolo de til ( `~` ), que quando usado em uma unidade do provedor FileSystem é equivalente a `$HOME` and `$env:USERPROFILE` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="7d1c4-128">Se Stack2 ainda não existir na sessão, o o `Push-Location` criará.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="7d1c4-129">O segundo comando usa o `Pop-Location` cmdlet para exibir o local original ( `C:\` ) da pilha Stack2.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="7d1c4-130">Sem o parâmetro **StackName** , `Pop-Location` seria exibido o local da pilha padrão sem nome.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="7d1c4-131">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="7d1c4-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d1c4-132">PARAMETERS</span></span>

### <span data-ttu-id="7d1c4-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7d1c4-133">-LiteralPath</span></span>

<span data-ttu-id="7d1c4-134">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-134">Specifies the path to the new location.</span></span> <span data-ttu-id="7d1c4-135">Ao contrário do parâmetro **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="7d1c4-136">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7d1c4-137">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7d1c4-138">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7d1c4-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7d1c4-139">-PassThru</span></span>

<span data-ttu-id="7d1c4-140">Passa um objeto representando o local para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="7d1c4-141">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7d1c4-142">-Path</span><span class="sxs-lookup"><span data-stu-id="7d1c4-142">-Path</span></span>

<span data-ttu-id="7d1c4-143">Altera seu local no local especificado por esse caminho depois de adicionado (enviado) o local atual para o topo da pilha.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="7d1c4-144">Insira um caminho para qualquer local cujo provedor oferece suporte a esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="7d1c4-145">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-145">Wildcards are permitted.</span></span> <span data-ttu-id="7d1c4-146">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-146">The parameter name is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="7d1c4-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="7d1c4-147">-StackName</span></span>

<span data-ttu-id="7d1c4-148">Especifica a pilha local à qual o local atual será adicionado.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="7d1c4-149">Digite um nome de pilha de local.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-149">Enter a location stack name.</span></span>
<span data-ttu-id="7d1c4-150">Se a pilha não existir, a `Push-Location` criará.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="7d1c4-151">Sem esse parâmetro, `Push-Location` o adiciona o local à pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="7d1c4-152">Por padrão, a pilha de local atual é a pilha de locais padrão sem nome que o PowerShell cria.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="7d1c4-153">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="7d1c4-154">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="7d1c4-155">`Push-Location` Não é possível adicionar um local à pilha padrão sem nome, a menos que ela seja a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7d1c4-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="7d1c4-156">-UseTransaction</span></span>

<span data-ttu-id="7d1c4-157">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-157">Includes the command in the active transaction.</span></span> <span data-ttu-id="7d1c4-158">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-158">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="7d1c4-159">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-159">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d1c4-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7d1c4-160">CommonParameters</span></span>

<span data-ttu-id="7d1c4-161">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d1c4-162">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d1c4-163">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7d1c4-163">INPUTS</span></span>

### <span data-ttu-id="7d1c4-164">System.String</span><span class="sxs-lookup"><span data-stu-id="7d1c4-164">System.String</span></span>

<span data-ttu-id="7d1c4-165">É possível canalizar uma cadeia de caracteres que contém um caminho (mas não um caminho literal) para `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-165">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="7d1c4-166">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7d1c4-166">OUTPUTS</span></span>

### <span data-ttu-id="7d1c4-167">Nenhum ou System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="7d1c4-167">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="7d1c4-168">Quando você usa o parâmetro **PassThru** , o `Push-Location` gera um objeto **System. Management. Automation. PathInfo** que representa o local.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-168">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="7d1c4-169">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7d1c4-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7d1c4-170">NOTES</span></span>

<span data-ttu-id="7d1c4-171">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-171">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="7d1c4-172">Cada runspace tem seu próprio _diretório atual_ .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-172">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="7d1c4-173">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-173">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="7d1c4-174">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-174">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="7d1c4-175">Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-175">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="7d1c4-176">Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-176">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="7d1c4-177">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente está acessível.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-177">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="7d1c4-178">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="7d1c4-179">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-179">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="7d1c4-180">O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-180">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="7d1c4-181">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-181">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="7d1c4-182">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-182">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="7d1c4-183">Para gerenciar as pilhas de locais, use os cmdlets de local do PowerShell, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-183">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="7d1c4-184">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-184">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="7d1c4-185">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-185">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="7d1c4-186">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-186">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="7d1c4-187">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-187">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="7d1c4-188">Para criar uma nova pilha de locais, use o parâmetro StackName do `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-188">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="7d1c4-189">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-189">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="7d1c4-190">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro StackName do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-190">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="7d1c4-191">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-191">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="7d1c4-192">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-192">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="7d1c4-193">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-193">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="7d1c4-194">Você também pode consultar `Push-Location` por seu alias interno, `pushd` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-194">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="7d1c4-195">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-195">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="7d1c4-196">O `Push-Location` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="7d1c4-196">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7d1c4-197">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="7d1c4-197">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7d1c4-198">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7d1c4-198">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7d1c4-199">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7d1c4-199">RELATED LINKS</span></span>

[<span data-ttu-id="7d1c4-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="7d1c4-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="7d1c4-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="7d1c4-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="7d1c4-202">Set-Location</span><span class="sxs-lookup"><span data-stu-id="7d1c4-202">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="7d1c4-203">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="7d1c4-203">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="7d1c4-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7d1c4-204">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
