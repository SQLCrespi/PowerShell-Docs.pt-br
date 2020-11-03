---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 647424d8148cad8830235abc7b238b79b552c4fb
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "93195226"
---
# <span data-ttu-id="b0737-103">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b0737-103">Get-Location</span></span>

## <span data-ttu-id="b0737-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b0737-104">SYNOPSIS</span></span>
<span data-ttu-id="b0737-105">Obtém informações sobre o local de trabalho atual ou uma pilha de locais.</span><span class="sxs-lookup"><span data-stu-id="b0737-105">Gets information about the current working location or a location stack.</span></span>

## <span data-ttu-id="b0737-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0737-106">SYNTAX</span></span>

### <span data-ttu-id="b0737-107">Local (padrão)</span><span class="sxs-lookup"><span data-stu-id="b0737-107">Location (Default)</span></span>

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b0737-108">Pilha</span><span class="sxs-lookup"><span data-stu-id="b0737-108">Stack</span></span>

```
Get-Location [-Stack] [-StackName <String[]>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b0737-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0737-109">DESCRIPTION</span></span>

<span data-ttu-id="b0737-110">O `Get-Location` cmdlet obtém um objeto que representa o diretório atual, assim como o comando de pasta de trabalho de impressão (pwd).</span><span class="sxs-lookup"><span data-stu-id="b0737-110">The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.</span></span>

<span data-ttu-id="b0737-111">Quando você se move entre as unidades do PowerShell, o PowerShell retém seu local em cada unidade.</span><span class="sxs-lookup"><span data-stu-id="b0737-111">When you move between PowerShell drives, PowerShell retains your location in each drive.</span></span> <span data-ttu-id="b0737-112">Você pode usar este cmdlet para localizar seu local em cada unidade.</span><span class="sxs-lookup"><span data-stu-id="b0737-112">You can use this cmdlet to find your location in each drive.</span></span>

<span data-ttu-id="b0737-113">Você pode usar este cmdlet para obter o diretório atual em tempo de execução e usá-lo em funções e scripts, como em uma função que exibe o diretório atual no prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0737-113">You can use this cmdlet to get the current directory at run time and use it in functions and scripts, such as in a function that displays the current directory in the PowerShell prompt.</span></span>

<span data-ttu-id="b0737-114">Você também pode usar este cmdlet para exibir os locais em uma pilha de local.</span><span class="sxs-lookup"><span data-stu-id="b0737-114">You can also use this cmdlet to display the locations in a location stack.</span></span> <span data-ttu-id="b0737-115">Para obter mais informações, consulte as observações e as descrições dos parâmetros **Stack** e **StackName** .</span><span class="sxs-lookup"><span data-stu-id="b0737-115">For more information, see the Notes and the descriptions of the **Stack** and **StackName** parameters.</span></span>

## <span data-ttu-id="b0737-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b0737-116">EXAMPLES</span></span>

### <span data-ttu-id="b0737-117">Exemplo 1: exibir o local da unidade atual</span><span class="sxs-lookup"><span data-stu-id="b0737-117">Example 1: Display your current drive location</span></span>

<span data-ttu-id="b0737-118">Esse comando exibe o local na unidade atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0737-118">This command displays your location in the current PowerShell drive.</span></span>

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="b0737-119">Por exemplo, se você estiver no `Windows` diretório da `C:` unidade, ele exibirá o caminho para esse diretório.</span><span class="sxs-lookup"><span data-stu-id="b0737-119">For instance, if you are in the `Windows` directory of the `C:` drive, it displays the path to that directory.</span></span>

### <span data-ttu-id="b0737-120">Exemplo 2: exibir seu local atual para unidades diferentes</span><span class="sxs-lookup"><span data-stu-id="b0737-120">Example 2: Display your current location for different drives</span></span>

<span data-ttu-id="b0737-121">Este exemplo demonstra o uso do `Get-Location` para exibir seu local atual em diferentes unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0737-121">This example demonstrates the use of `Get-Location` to display your current location in different PowerShell drives.</span></span> <span data-ttu-id="b0737-122">`Set-Location` é usado para alterar o local para vários caminhos diferentes em PSDrives diferentes.</span><span class="sxs-lookup"><span data-stu-id="b0737-122">`Set-Location` is used to change the location to several different paths on different PSDrives.</span></span>

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### <span data-ttu-id="b0737-123">Exemplo 3: obter locais usando pilhas</span><span class="sxs-lookup"><span data-stu-id="b0737-123">Example 3: Get locations using stacks</span></span>

<span data-ttu-id="b0737-124">Este exemplo mostra como usar os parâmetros **Stack** e **StackName** de `Get-Location` para listar os locais na pilha de local atual e as pilhas de local alternativas.</span><span class="sxs-lookup"><span data-stu-id="b0737-124">This example shows how to use the **Stack** and **StackName** parameters of `Get-Location` to list the locations in the current location stack and alternate location stacks.</span></span>

<span data-ttu-id="b0737-125">O `Push-Location` cmdlet é usado para alterar em três locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="b0737-125">The `Push-Location` cmdlet is used to change into three different locations.</span></span> <span data-ttu-id="b0737-126">O terceiro envio por push usa um nome de pilha diferente.</span><span class="sxs-lookup"><span data-stu-id="b0737-126">The third push uses a different stack name.</span></span> <span data-ttu-id="b0737-127">O parâmetro **Stack** de `Get-Location` exibe o conteúdo da pilha padrão.</span><span class="sxs-lookup"><span data-stu-id="b0737-127">The **Stack** parameter of `Get-Location` displays the contents of the default stack.</span></span> <span data-ttu-id="b0737-128">O parâmetro **StackName** de `Get-Location` exibe o conteúdo da pilha chamada `Stack2` .</span><span class="sxs-lookup"><span data-stu-id="b0737-128">The **StackName** parameter of `Get-Location` displays the contents of the stack named `Stack2`.</span></span>

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### <span data-ttu-id="b0737-129">Exemplo 4: personalizar o prompt do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0737-129">Example 4: Customize the PowerShell prompt</span></span>

<span data-ttu-id="b0737-130">Este exemplo mostra como personalizar o prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0737-130">This example shows how to customize the PowerShell prompt.</span></span>

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

<span data-ttu-id="b0737-131">A função que define o prompt inclui um `Get-Location` comando, que é executado sempre que o prompt é exibido no console do.</span><span class="sxs-lookup"><span data-stu-id="b0737-131">The function that defines the prompt includes a `Get-Location` command, which is run whenever the prompt appears in the console.</span></span>

<span data-ttu-id="b0737-132">O formato do prompt padrão do PowerShell é definido por uma função especial chamada `prompt` .</span><span class="sxs-lookup"><span data-stu-id="b0737-132">The format of the default PowerShell prompt is defined by a special function named `prompt`.</span></span> <span data-ttu-id="b0737-133">Você pode alterar o prompt no console criando uma nova função chamada `prompt` .</span><span class="sxs-lookup"><span data-stu-id="b0737-133">You can change the prompt in your console by creating a new function named `prompt`.</span></span>

<span data-ttu-id="b0737-134">Para ver a função de prompt atual, digite o seguinte comando: `Get-Content Function:\prompt`</span><span class="sxs-lookup"><span data-stu-id="b0737-134">To see the current prompt function, type the following command: `Get-Content Function:\prompt`</span></span>

## <span data-ttu-id="b0737-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0737-135">PARAMETERS</span></span>

### <span data-ttu-id="b0737-136">-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b0737-136">-PSDrive</span></span>

<span data-ttu-id="b0737-137">Obtém o local atual na unidade do PowerShell especificada.</span><span class="sxs-lookup"><span data-stu-id="b0737-137">Gets the current location in the specified PowerShell drive.</span></span>

<span data-ttu-id="b0737-138">Por exemplo, se você estiver na `Cert:` unidade, poderá usar esse parâmetro para localizar o local atual na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="b0737-138">For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b0737-139">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b0737-139">-PSProvider</span></span>

<span data-ttu-id="b0737-140">Obtém o local atual na unidade com suporte pelo provedor do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="b0737-140">Gets the current location in the drive supported by the specified PowerShell provider.</span></span>
<span data-ttu-id="b0737-141">Se o provedor especificado oferecer suporte a mais de uma unidade, esse cmdlet retornará o local na unidade acessada mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="b0737-141">If the specified provider supports more than one drive, this cmdlet returns the location on the most recently accessed drive.</span></span>

<span data-ttu-id="b0737-142">Por exemplo, se você estiver na `C:` unidade, poderá usar esse parâmetro para localizar o local atual nas unidades do provedor de **registro** do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0737-142">For example, if you are in the `C:` drive, you can use this parameter to find your current location in the drives of the PowerShell **Registry** provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b0737-143">-Pilha</span><span class="sxs-lookup"><span data-stu-id="b0737-143">-Stack</span></span>

<span data-ttu-id="b0737-144">Indica que esse cmdlet exibe os locais adicionados à pilha do local atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-144">Indicates that this cmdlet displays the locations added to the current location stack.</span></span> <span data-ttu-id="b0737-145">Você pode adicionar locais a pilhas usando o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-145">You can add locations to stacks by using the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="b0737-146">Para exibir os locais em uma pilha de local diferente, use o parâmetro **StackName** .</span><span class="sxs-lookup"><span data-stu-id="b0737-146">To display the locations in a different location stack, use the **StackName** parameter.</span></span> <span data-ttu-id="b0737-147">Para obter informações sobre as pilhas de locais, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="b0737-147">For information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0737-148">-StackName</span><span class="sxs-lookup"><span data-stu-id="b0737-148">-StackName</span></span>

<span data-ttu-id="b0737-149">Especifica, como uma matriz de cadeia de caracteres, as pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="b0737-149">Specifies, as a string array, the named location stacks.</span></span> <span data-ttu-id="b0737-150">Insira um ou mais nomes de pilha de locais.</span><span class="sxs-lookup"><span data-stu-id="b0737-150">Enter one or more location stack names.</span></span>

<span data-ttu-id="b0737-151">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** .</span><span class="sxs-lookup"><span data-stu-id="b0737-151">To display the locations in the current location stack, use the **Stack** parameter.</span></span> <span data-ttu-id="b0737-152">Para tornar uma pilha de localização a pilha de locais atual, use o `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-152">To make a location stack the current location stack, use the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="b0737-153">Esse cmdlet não pode exibir os locais na pilha padrão sem nome, a menos que seja a pilha atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-153">This cmdlet cannot display the locations in the unnamed default stack unless it is the current stack.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b0737-154">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b0737-154">-UseTransaction</span></span>
<span data-ttu-id="b0737-155">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="b0737-155">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b0737-156">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="b0737-156">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b0737-157">Para obter mais informações, consulte about_transactions.</span><span class="sxs-lookup"><span data-stu-id="b0737-157">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="b0737-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b0737-158">CommonParameters</span></span>

<span data-ttu-id="b0737-159">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0737-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0737-160">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b0737-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0737-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b0737-161">INPUTS</span></span>

### <span data-ttu-id="b0737-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b0737-162">None</span></span>

<span data-ttu-id="b0737-163">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b0737-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b0737-164">OUTPUTS</span></span>

### <span data-ttu-id="b0737-165">System. Management. Automation. PathInfo ou System. Management. Automation. PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="b0737-165">System.Management.Automation.PathInfo or System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="b0737-166">Se você usar os parâmetros **Stack** ou **StackName** , esse cmdlet retornará um objeto **PathInfoStack** .</span><span class="sxs-lookup"><span data-stu-id="b0737-166">If you use the **Stack** or **StackName** parameters, this cmdlet returns a **PathInfoStack** object.</span></span> <span data-ttu-id="b0737-167">Caso contrário, ele retorna um objeto **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="b0737-167">Otherwise, it returns a **PathInfo** object.</span></span>

## <span data-ttu-id="b0737-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b0737-168">NOTES</span></span>

<span data-ttu-id="b0737-169">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="b0737-169">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="b0737-170">Cada runspace tem seu próprio _diretório atual_ .</span><span class="sxs-lookup"><span data-stu-id="b0737-170">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="b0737-171">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="b0737-171">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="b0737-172">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="b0737-172">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>
<span data-ttu-id="b0737-173">O `Get-Location` cmdlet retorna o diretório atual do runspace do PowerShell atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-173">The `Get-Location` cmdlet returns the current directory of the current PowerShell runspace.</span></span>

<span data-ttu-id="b0737-174">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="b0737-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b0737-175">Para listar os provedores em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b0737-175">To list the providers in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b0737-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b0737-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="b0737-177">As maneiras como os parâmetros **PSProvider** , **PSDrive** , **Stack** e **StackName** interagem dependem do provedor.</span><span class="sxs-lookup"><span data-stu-id="b0737-177">The ways that the **PSProvider** , **PSDrive** , **Stack** , and **StackName** parameters interact depends on the provider.</span></span> <span data-ttu-id="b0737-178">Algumas combinações resultarão em erros, como especificar uma unidade e um provedor que não expõe essa unidade.</span><span class="sxs-lookup"><span data-stu-id="b0737-178">Some combinations will result in errors, such as specifying both a drive and a provider that does not expose that drive.</span></span> <span data-ttu-id="b0737-179">Se nenhum parâmetro for especificado, esse cmdlet retornará o objeto **PathInfo** para o provedor que contém o local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-179">If no parameters are specified, this cmdlet returns the **PathInfo** object for the provider that contains the current working location.</span></span>

<span data-ttu-id="b0737-180">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente está acessível.</span><span class="sxs-lookup"><span data-stu-id="b0737-180">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span> <span data-ttu-id="b0737-181">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="b0737-181">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="b0737-182">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="b0737-182">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="b0737-183">O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="b0737-183">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="b0737-184">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-184">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="b0737-185">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-185">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="b0737-186">Para gerenciar as pilhas de locais, use os `*-Location` cmdlets do PowerShell, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b0737-186">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows.</span></span>

- <span data-ttu-id="b0737-187">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-187">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="b0737-188">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-188">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="b0737-189">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-189">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="b0737-190">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-190">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="b0737-191">Para criar uma nova pilha de locais, use o parâmetro **StackName** do `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-191">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span>
  <span data-ttu-id="b0737-192">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="b0737-192">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="b0737-193">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0737-193">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="b0737-194">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="b0737-194">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="b0737-195">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar este cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="b0737-195">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use this cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="b0737-196">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="b0737-196">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="b0737-197">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b0737-197">RELATED LINKS</span></span>

[<span data-ttu-id="b0737-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b0737-198">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="b0737-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b0737-199">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="b0737-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b0737-200">Set-Location</span></span>](Set-Location.md)
