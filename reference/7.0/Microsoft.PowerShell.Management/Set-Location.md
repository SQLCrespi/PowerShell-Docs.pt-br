---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: dddc3d8309095520167d80ac73bb45399ba436f5
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "93195221"
---
# <span data-ttu-id="7fa82-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="7fa82-103">Set-Location</span></span>

## <span data-ttu-id="7fa82-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7fa82-104">SYNOPSIS</span></span>
<span data-ttu-id="7fa82-105">Define o local de trabalho atual em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="7fa82-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="7fa82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7fa82-106">SYNTAX</span></span>

### <span data-ttu-id="7fa82-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="7fa82-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="7fa82-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7fa82-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="7fa82-109">Pilha</span><span class="sxs-lookup"><span data-stu-id="7fa82-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="7fa82-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7fa82-110">DESCRIPTION</span></span>

<span data-ttu-id="7fa82-111">O `Set-Location` cmdlet define o local de trabalho para um local especificado.</span><span class="sxs-lookup"><span data-stu-id="7fa82-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="7fa82-112">Esse local pode ser um diretório, um subdiretório, um local do registro ou qualquer caminho do provedor.</span><span class="sxs-lookup"><span data-stu-id="7fa82-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="7fa82-113">O PowerShell 6,2 adicionou suporte para `-` e `+` como valores para o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="7fa82-113">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="7fa82-114">O PowerShell mantém um histórico dos últimos 20 locais que podem ser acessados com o `-` e o `+` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-114">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="7fa82-115">Essa lista é independente da pilha de local que é acessada usando o parâmetro **StackName** .</span><span class="sxs-lookup"><span data-stu-id="7fa82-115">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="7fa82-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7fa82-116">EXAMPLES</span></span>

### <span data-ttu-id="7fa82-117">Exemplo 1: definir o local atual</span><span class="sxs-lookup"><span data-stu-id="7fa82-117">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="7fa82-118">Esse comando define o local atual como a raiz da `HKLM:` unidade.</span><span class="sxs-lookup"><span data-stu-id="7fa82-118">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="7fa82-119">Exemplo 2: definir o local atual e exibir esse local</span><span class="sxs-lookup"><span data-stu-id="7fa82-119">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="7fa82-120">Esse comando define o local atual como a raiz da `Env:` unidade.</span><span class="sxs-lookup"><span data-stu-id="7fa82-120">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="7fa82-121">Ele usa o parâmetro **PassThru** para direcionar o PowerShell para retornar um objeto **PathInfo** que representa o `Env:\` local.</span><span class="sxs-lookup"><span data-stu-id="7fa82-121">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="7fa82-122">Exemplo 3: definir local para o local atual na unidade C:</span><span class="sxs-lookup"><span data-stu-id="7fa82-122">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="7fa82-123">O primeiro comando define o local para a raiz da `HKLM:` unidade no provedor de registro.</span><span class="sxs-lookup"><span data-stu-id="7fa82-123">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="7fa82-124">O segundo comando define o local para o local atual da `C:` unidade no provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="7fa82-124">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="7fa82-125">Quando o nome da unidade é especificado no formulário `<DriveName>:` (sem barra invertida), o cmdlet define o local para o local atual no PSDrive.</span><span class="sxs-lookup"><span data-stu-id="7fa82-125">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="7fa82-126">Para obter o local atual no comando PSDrive use `Get-Location -PSDrive <DriveName>` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-126">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="7fa82-127">Exemplo 4: definir o local atual para uma pilha nomeada</span><span class="sxs-lookup"><span data-stu-id="7fa82-127">Example 4: Set the current location to a named stack</span></span>

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="7fa82-128">O primeiro comando adiciona o local atual à pilha de caminhos.</span><span class="sxs-lookup"><span data-stu-id="7fa82-128">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="7fa82-129">O segundo comando torna o local dos caminhos empilhar a pilha do local atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-129">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="7fa82-130">O terceiro comando exibe os locais na pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-130">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="7fa82-131">Os `*-Location` cmdlets usam a pilha de local atual, a menos que uma pilha de local diferente seja especificada no comando.</span><span class="sxs-lookup"><span data-stu-id="7fa82-131">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="7fa82-132">Para obter informações sobre as pilhas de locais, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="7fa82-132">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="7fa82-133">Exemplo 5: navegar no histórico de local usando `+` ou `-`</span><span class="sxs-lookup"><span data-stu-id="7fa82-133">Example 5: Navigate location history using `+` or `-`</span></span>

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

<span data-ttu-id="7fa82-134">Usar o alias `cd -` ou `cd +` é uma maneira fácil de navegar pelo seu histórico de local enquanto estiver em seu terminal.</span><span class="sxs-lookup"><span data-stu-id="7fa82-134">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="7fa82-135">Para obter mais informações sobre como navegar com `-` / `+` o, consulte o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="7fa82-135">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="7fa82-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7fa82-136">PARAMETERS</span></span>

### <span data-ttu-id="7fa82-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7fa82-137">-LiteralPath</span></span>

<span data-ttu-id="7fa82-138">Especifica um caminho do local.</span><span class="sxs-lookup"><span data-stu-id="7fa82-138">Specifies a path of the location.</span></span> <span data-ttu-id="7fa82-139">O valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="7fa82-139">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="7fa82-140">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="7fa82-140">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="7fa82-141">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="7fa82-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7fa82-142">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="7fa82-142">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7fa82-143">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7fa82-143">-PassThru</span></span>

<span data-ttu-id="7fa82-144">Retorna um objeto **PathInfo** que representa o local.</span><span class="sxs-lookup"><span data-stu-id="7fa82-144">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="7fa82-145">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7fa82-145">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7fa82-146">-Path</span><span class="sxs-lookup"><span data-stu-id="7fa82-146">-Path</span></span>

<span data-ttu-id="7fa82-147">Especifique o caminho de um novo local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7fa82-147">Specify the path of a new working location.</span></span> <span data-ttu-id="7fa82-148">Se nenhum caminho for fornecido, `Set-Location` o padrão será o diretório base do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-148">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="7fa82-149">Quando caracteres curinga são usados, o cmdlet escolhe o primeiro caminho que corresponde ao padrão de curinga.</span><span class="sxs-lookup"><span data-stu-id="7fa82-149">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="7fa82-150">O PowerShell mantém um histórico dos últimos 20 locais que você definiu.</span><span class="sxs-lookup"><span data-stu-id="7fa82-150">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="7fa82-151">Se o valor do parâmetro **path** for o `-` caractere, o novo local de trabalho será o local de trabalho anterior no histórico (se existir).</span><span class="sxs-lookup"><span data-stu-id="7fa82-151">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="7fa82-152">Da mesma forma, se o valor for o `+` caractere, o novo local de trabalho será o próximo local de trabalho no histórico (se existir).</span><span class="sxs-lookup"><span data-stu-id="7fa82-152">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="7fa82-153">Isso é semelhante a usar `Pop-Location` e, `Push-Location` exceto que o histórico é uma lista, não uma pilha, e é rastreado implicitamente, não controlado manualmente.</span><span class="sxs-lookup"><span data-stu-id="7fa82-153">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="7fa82-154">Atualmente, não há como exibir a lista de histórico.</span><span class="sxs-lookup"><span data-stu-id="7fa82-154">Currently, there is no way to view the history list.</span></span>

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

### <span data-ttu-id="7fa82-155">-StackName</span><span class="sxs-lookup"><span data-stu-id="7fa82-155">-StackName</span></span>

<span data-ttu-id="7fa82-156">Especifica o nome da pilha de local existente que esse cmdlet cria a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-156">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="7fa82-157">Digite um nome de pilha de local.</span><span class="sxs-lookup"><span data-stu-id="7fa82-157">Enter a location stack name.</span></span> <span data-ttu-id="7fa82-158">Para indicar a pilha de local padrão sem nome, digite `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="7fa82-158">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="7fa82-159">Os `*-Location` cmdlets atuam na pilha atual, a menos que você use o parâmetro **StackName** para especificar uma pilha diferente.</span><span class="sxs-lookup"><span data-stu-id="7fa82-159">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="7fa82-160">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="7fa82-160">For more information about location stacks, see the [Notes](#notes).</span></span>

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

### <span data-ttu-id="7fa82-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7fa82-161">CommonParameters</span></span>

<span data-ttu-id="7fa82-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7fa82-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7fa82-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7fa82-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7fa82-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7fa82-164">INPUTS</span></span>

### <span data-ttu-id="7fa82-165">System.String</span><span class="sxs-lookup"><span data-stu-id="7fa82-165">System.String</span></span>

<span data-ttu-id="7fa82-166">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fa82-166">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="7fa82-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7fa82-167">OUTPUTS</span></span>

### <span data-ttu-id="7fa82-168">Nenhum, System. Management. Automation. PathInfo, System. Management. Automation. PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="7fa82-168">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="7fa82-169">Esse cmdlet não gera nenhuma saída, a menos que você especifique o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="7fa82-169">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="7fa82-170">O uso de **PassThru** com **Path** ou **LiteralPath** gera um objeto **PathInfo** que representa o novo local.</span><span class="sxs-lookup"><span data-stu-id="7fa82-170">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="7fa82-171">O uso de **PassThru** com **StackName** gera um objeto **PathInfoStack** que representa o novo contexto da pilha.</span><span class="sxs-lookup"><span data-stu-id="7fa82-171">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="7fa82-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7fa82-172">NOTES</span></span>

<span data-ttu-id="7fa82-173">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="7fa82-173">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="7fa82-174">Cada runspace tem seu próprio _diretório atual_ .</span><span class="sxs-lookup"><span data-stu-id="7fa82-174">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="7fa82-175">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-175">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="7fa82-176">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="7fa82-176">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="7fa82-177">Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7fa82-177">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="7fa82-178">Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-178">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="7fa82-179">O `Set-Location` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="7fa82-179">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7fa82-180">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-180">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7fa82-181">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7fa82-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="7fa82-182">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="7fa82-182">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="7fa82-183">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="7fa82-183">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="7fa82-184">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="7fa82-184">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="7fa82-185">O PowerShell cria uma pilha de local padrão sem nome.</span><span class="sxs-lookup"><span data-stu-id="7fa82-185">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="7fa82-186">Você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="7fa82-186">You can create multiple named location stacks.</span></span> <span data-ttu-id="7fa82-187">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-187">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="7fa82-188">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-188">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="7fa82-189">Para gerenciar as pilhas de locais, use os `*-Location` cmdlets, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7fa82-189">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="7fa82-190">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fa82-190">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="7fa82-191">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fa82-191">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="7fa82-192">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fa82-192">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="7fa82-193">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** de `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-193">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="7fa82-194">Para criar uma nova pilha de locais, use o parâmetro **StackName** de `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-194">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="7fa82-195">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="7fa82-195">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="7fa82-196">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** de `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="7fa82-196">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="7fa82-197">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="7fa82-197">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="7fa82-198">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="7fa82-198">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="7fa82-199">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="7fa82-199">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="7fa82-200">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7fa82-200">RELATED LINKS</span></span>

[<span data-ttu-id="7fa82-201">Get-Location</span><span class="sxs-lookup"><span data-stu-id="7fa82-201">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="7fa82-202">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="7fa82-202">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="7fa82-203">Push-Location</span><span class="sxs-lookup"><span data-stu-id="7fa82-203">Push-Location</span></span>](Push-Location.md)
