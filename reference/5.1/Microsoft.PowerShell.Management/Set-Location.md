---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 06b1596366c9c9e20857b55aa9a17342bab07028
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "93195222"
---
# <span data-ttu-id="b5096-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b5096-103">Set-Location</span></span>

## <span data-ttu-id="b5096-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b5096-104">SYNOPSIS</span></span>
<span data-ttu-id="b5096-105">Define o local de trabalho atual em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="b5096-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="b5096-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5096-106">SYNTAX</span></span>

### <span data-ttu-id="b5096-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="b5096-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b5096-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b5096-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b5096-109">Pilha</span><span class="sxs-lookup"><span data-stu-id="b5096-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b5096-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5096-110">DESCRIPTION</span></span>

<span data-ttu-id="b5096-111">O `Set-Location` cmdlet define o local de trabalho para um local especificado.</span><span class="sxs-lookup"><span data-stu-id="b5096-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="b5096-112">Esse local pode ser um diretório, um subdiretório, um local do registro ou qualquer caminho do provedor.</span><span class="sxs-lookup"><span data-stu-id="b5096-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="b5096-113">Você também pode usar o parâmetro **StackName** para tornar uma pilha de local nomeada a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-113">You can also use the **StackName** parameter to make a named location stack the current location stack.</span></span> <span data-ttu-id="b5096-114">Para obter mais informações sobre as pilhas de locais, consulte as Observações.</span><span class="sxs-lookup"><span data-stu-id="b5096-114">For more information about location stacks, see the Notes.</span></span>

## <span data-ttu-id="b5096-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b5096-115">EXAMPLES</span></span>

### <span data-ttu-id="b5096-116">Exemplo 1: definir o local atual</span><span class="sxs-lookup"><span data-stu-id="b5096-116">Example 1: Set the current location</span></span>

```powershell
PS C:\> Set-Location -Path "HKLM:\"
```

```output
PS HKLM:\>
```

<span data-ttu-id="b5096-117">Esse comando define o local atual como a raiz da `HKLM:` unidade.</span><span class="sxs-lookup"><span data-stu-id="b5096-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="b5096-118">Exemplo 2: definir o local atual e exibir esse local</span><span class="sxs-lookup"><span data-stu-id="b5096-118">Example 2: Set the current location and display that location</span></span>

```powershell
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="b5096-119">Esse comando define o local atual como a raiz da `Env:` unidade.</span><span class="sxs-lookup"><span data-stu-id="b5096-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="b5096-120">Ele usa o parâmetro **PassThru** para direcionar o PowerShell para retornar um objeto **PathInfo** que representa o `Env:\` local.</span><span class="sxs-lookup"><span data-stu-id="b5096-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="b5096-121">Exemplo 3: definir local para o local atual na unidade C:</span><span class="sxs-lookup"><span data-stu-id="b5096-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="b5096-122">O primeiro comando define o local para a raiz da `HKLM:` unidade no provedor de registro.</span><span class="sxs-lookup"><span data-stu-id="b5096-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="b5096-123">O segundo comando define o local para o local atual da `C:` unidade no provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="b5096-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="b5096-124">Quando o nome da unidade é especificado no formulário `<DriveName>:` (sem barra invertida), o cmdlet define o local para o local atual no PSDrive.</span><span class="sxs-lookup"><span data-stu-id="b5096-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="b5096-125">Para obter o local atual no comando PSDrive use `Get-Location -PSDrive <DriveName>` .</span><span class="sxs-lookup"><span data-stu-id="b5096-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="b5096-126">Exemplo 4: definir o local atual para uma pilha nomeada</span><span class="sxs-lookup"><span data-stu-id="b5096-126">Example 4: Set the current location to a named stack</span></span>

```powershell
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="b5096-127">O primeiro comando adiciona o local atual à pilha de caminhos.</span><span class="sxs-lookup"><span data-stu-id="b5096-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="b5096-128">O segundo comando torna o local dos caminhos empilhar a pilha do local atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="b5096-129">O terceiro comando exibe os locais na pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="b5096-130">Os `*-Location` cmdlets usam a pilha de local atual, a menos que uma pilha de local diferente seja especificada no comando.</span><span class="sxs-lookup"><span data-stu-id="b5096-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="b5096-131">Para obter informações sobre as pilhas de locais, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="b5096-131">For information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="b5096-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5096-132">PARAMETERS</span></span>

### <span data-ttu-id="b5096-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b5096-133">-LiteralPath</span></span>

<span data-ttu-id="b5096-134">Especifica um caminho do local.</span><span class="sxs-lookup"><span data-stu-id="b5096-134">Specifies a path of the location.</span></span> <span data-ttu-id="b5096-135">O valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="b5096-135">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="b5096-136">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="b5096-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="b5096-137">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b5096-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b5096-138">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b5096-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b5096-139">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b5096-139">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5096-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b5096-140">-PassThru</span></span>

<span data-ttu-id="b5096-141">Retorna um objeto **PathInfo** que representa o local.</span><span class="sxs-lookup"><span data-stu-id="b5096-141">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="b5096-142">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b5096-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b5096-143">-Path</span><span class="sxs-lookup"><span data-stu-id="b5096-143">-Path</span></span>

<span data-ttu-id="b5096-144">Especifique o caminho de um novo local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b5096-144">Specify the path of a new working location.</span></span> <span data-ttu-id="b5096-145">Se nenhum caminho for fornecido, `Set-Location` o padrão será o diretório base do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-145">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="b5096-146">Quando caracteres curinga são usados, o cmdlet escolhe o primeiro caminho que corresponde ao padrão de curinga.</span><span class="sxs-lookup"><span data-stu-id="b5096-146">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b5096-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="b5096-147">-StackName</span></span>

<span data-ttu-id="b5096-148">Especifica o nome da pilha de local existente que esse cmdlet cria a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-148">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="b5096-149">Digite um nome de pilha de local.</span><span class="sxs-lookup"><span data-stu-id="b5096-149">Enter a location stack name.</span></span> <span data-ttu-id="b5096-150">Para indicar a pilha de local padrão sem nome, digite `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="b5096-150">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="b5096-151">Os `*-Location` cmdlets atuam na pilha atual, a menos que você use o parâmetro **StackName** para especificar uma pilha diferente.</span><span class="sxs-lookup"><span data-stu-id="b5096-151">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span>

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5096-152">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b5096-152">-UseTransaction</span></span>

<span data-ttu-id="b5096-153">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="b5096-153">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b5096-154">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="b5096-154">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b5096-155">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="b5096-155">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="b5096-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5096-156">CommonParameters</span></span>

<span data-ttu-id="b5096-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5096-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5096-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5096-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5096-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b5096-159">INPUTS</span></span>

### <span data-ttu-id="b5096-160">System.String</span><span class="sxs-lookup"><span data-stu-id="b5096-160">System.String</span></span>

<span data-ttu-id="b5096-161">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5096-161">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="b5096-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b5096-162">OUTPUTS</span></span>

### <span data-ttu-id="b5096-163">Nenhum, System. Management. Automation. PathInfo, System. Management. Automation. PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="b5096-163">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="b5096-164">Esse cmdlet não gera nenhuma saída, a menos que você especifique o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="b5096-164">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b5096-165">O uso de **PassThru** com **Path** ou **LiteralPath** gera um objeto **PathInfo** que representa o novo local.</span><span class="sxs-lookup"><span data-stu-id="b5096-165">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="b5096-166">O uso de **PassThru** com **StackName** gera um objeto **PathInfoStack** que representa o novo contexto da pilha.</span><span class="sxs-lookup"><span data-stu-id="b5096-166">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="b5096-167">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b5096-167">NOTES</span></span>

<span data-ttu-id="b5096-168">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="b5096-168">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="b5096-169">Cada runspace tem seu próprio _diretório atual_ .</span><span class="sxs-lookup"><span data-stu-id="b5096-169">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="b5096-170">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="b5096-170">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="b5096-171">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="b5096-171">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="b5096-172">Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="b5096-172">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="b5096-173">Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-173">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="b5096-174">O `Set-Location` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="b5096-174">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b5096-175">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b5096-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b5096-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b5096-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="b5096-177">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="b5096-177">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="b5096-178">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="b5096-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="b5096-179">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="b5096-179">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="b5096-180">O PowerShell cria uma pilha de local padrão sem nome.</span><span class="sxs-lookup"><span data-stu-id="b5096-180">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="b5096-181">Você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="b5096-181">You can create multiple named location stacks.</span></span> <span data-ttu-id="b5096-182">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-182">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="b5096-183">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-183">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="b5096-184">Para gerenciar as pilhas de locais, use os `*-Location` cmdlets, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b5096-184">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="b5096-185">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5096-185">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="b5096-186">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5096-186">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="b5096-187">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5096-187">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="b5096-188">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** de `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="b5096-188">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="b5096-189">Para criar uma nova pilha de locais, use o parâmetro **StackName** de `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="b5096-189">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="b5096-190">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="b5096-190">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="b5096-191">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** de `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="b5096-191">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="b5096-192">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b5096-192">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="b5096-193">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="b5096-193">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="b5096-194">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="b5096-194">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="b5096-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b5096-195">RELATED LINKS</span></span>

[<span data-ttu-id="b5096-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b5096-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="b5096-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b5096-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="b5096-198">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b5096-198">Push-Location</span></span>](Push-Location.md)
