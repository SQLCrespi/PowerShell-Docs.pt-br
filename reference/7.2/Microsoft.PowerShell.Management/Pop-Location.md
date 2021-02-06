---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 8a44849f27de80ece486b573f1adccafab51972a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597413"
---
# <span data-ttu-id="caaa1-102">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="caaa1-102">Pop-Location</span></span>

## <span data-ttu-id="caaa1-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="caaa1-103">SYNOPSIS</span></span>
<span data-ttu-id="caaa1-104">Altera o local atual para o local mais recentemente inserido na pilha.</span><span class="sxs-lookup"><span data-stu-id="caaa1-104">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="caaa1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="caaa1-105">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="caaa1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="caaa1-106">DESCRIPTION</span></span>

<span data-ttu-id="caaa1-107">O `Pop-Location` cmdlet altera o local atual para o local mais recentemente enviado para a pilha usando o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-107">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="caaa1-108">Você pode mostrar um local da pilha padrão ou de uma pilha que você cria usando um `Push-Location` comando.</span><span class="sxs-lookup"><span data-stu-id="caaa1-108">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="caaa1-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="caaa1-109">EXAMPLES</span></span>

### <span data-ttu-id="caaa1-110">Exemplo 1: alterar para o local mais recente</span><span class="sxs-lookup"><span data-stu-id="caaa1-110">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="caaa1-111">Este comando altera o local para o local mais recentemente adicionado à pilha atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-111">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="caaa1-112">Exemplo 2: alterar para o local mais recente em uma pilha nomeada</span><span class="sxs-lookup"><span data-stu-id="caaa1-112">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="caaa1-113">Este comando altera o local para o local mais recentemente adicionado à pilha de local Stack2.</span><span class="sxs-lookup"><span data-stu-id="caaa1-113">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="caaa1-114">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="caaa1-114">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="caaa1-115">Exemplo 3: mover entre locais para provedores diferentes</span><span class="sxs-lookup"><span data-stu-id="caaa1-115">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="caaa1-116">Esses comandos usam os `Push-Location` `Pop-Location` cmdlets e para se mover entre os locais com suporte de diferentes provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="caaa1-116">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="caaa1-117">Os comandos usam o `pushd` alias para `Push-Location` e o `popd` alias para `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="caaa1-117">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="caaa1-118">O primeiro comando envia o local do sistema de arquivos atual para a pilha e move para a unidade HKLM suportada pelo provedor de registro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="caaa1-118">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="caaa1-119">O segundo comando envia o local do registro para a pilha e move para um local com suporte do provedor de certificados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="caaa1-119">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="caaa1-120">Os dois últimos comandos removem esses locais da pilha.</span><span class="sxs-lookup"><span data-stu-id="caaa1-120">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="caaa1-121">O primeiro `popd` comando retorna à unidade do registro e o segundo comando retorna à unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="caaa1-121">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="caaa1-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="caaa1-122">PARAMETERS</span></span>

### <span data-ttu-id="caaa1-123">-PassThru</span><span class="sxs-lookup"><span data-stu-id="caaa1-123">-PassThru</span></span>

<span data-ttu-id="caaa1-124">Passa um objeto que representa o local para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="caaa1-124">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="caaa1-125">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="caaa1-125">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="caaa1-126">-StackName</span><span class="sxs-lookup"><span data-stu-id="caaa1-126">-StackName</span></span>

<span data-ttu-id="caaa1-127">Especifica a pilha do local de onde o local é exibido.</span><span class="sxs-lookup"><span data-stu-id="caaa1-127">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="caaa1-128">Digite um nome de pilha de local.</span><span class="sxs-lookup"><span data-stu-id="caaa1-128">Enter a location stack name.</span></span>

<span data-ttu-id="caaa1-129">Sem esse parâmetro, `Pop-Location` o exibe um local da pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-129">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="caaa1-130">Por padrão, a pilha de local atual é a pilha de locais padrão sem nome que o PowerShell cria.</span><span class="sxs-lookup"><span data-stu-id="caaa1-130">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="caaa1-131">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-131">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="caaa1-132">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="caaa1-132">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="caaa1-133">`Pop-Location` Não é possível retirar um local da pilha padrão sem nome, a menos que seja a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-133">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="caaa1-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="caaa1-134">CommonParameters</span></span>

<span data-ttu-id="caaa1-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="caaa1-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="caaa1-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="caaa1-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="caaa1-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="caaa1-137">INPUTS</span></span>

### <span data-ttu-id="caaa1-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="caaa1-138">None</span></span>

<span data-ttu-id="caaa1-139">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="caaa1-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="caaa1-140">OUTPUTS</span></span>

### <span data-ttu-id="caaa1-141">Nenhum, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="caaa1-141">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="caaa1-142">Esse cmdlet gera um objeto **System. Management. Automation. PathInfo** que representa o local, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="caaa1-142">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="caaa1-143">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="caaa1-143">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="caaa1-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="caaa1-144">NOTES</span></span>

<span data-ttu-id="caaa1-145">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="caaa1-145">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="caaa1-146">Cada runspace tem seu próprio _diretório atual_.</span><span class="sxs-lookup"><span data-stu-id="caaa1-146">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="caaa1-147">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="caaa1-147">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="caaa1-148">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="caaa1-148">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="caaa1-149">Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="caaa1-149">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="caaa1-150">Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-150">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="caaa1-151">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="caaa1-151">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="caaa1-152">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="caaa1-152">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="caaa1-153">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="caaa1-153">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="caaa1-154">O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="caaa1-154">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="caaa1-155">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-155">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="caaa1-156">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-156">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="caaa1-157">Para gerenciar as pilhas de locais, use os `*-Location` cmdlets do PowerShell, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="caaa1-157">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="caaa1-158">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-158">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="caaa1-159">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-159">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="caaa1-160">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-160">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="caaa1-161">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-161">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="caaa1-162">Para criar uma nova pilha de locais, use o parâmetro **StackName** do `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-162">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="caaa1-163">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="caaa1-163">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="caaa1-164">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="caaa1-164">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="caaa1-165">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="caaa1-165">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="caaa1-166">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="caaa1-166">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="caaa1-167">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$Null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="caaa1-167">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="caaa1-168">Você também pode consultar `Pop-Location` por seu alias interno, `popd` .</span><span class="sxs-lookup"><span data-stu-id="caaa1-168">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="caaa1-169">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="caaa1-169">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="caaa1-170">`Pop-Location` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="caaa1-170">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="caaa1-171">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="caaa1-171">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="caaa1-172">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="caaa1-172">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="caaa1-173">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="caaa1-173">RELATED LINKS</span></span>

[<span data-ttu-id="caaa1-174">Get-Location</span><span class="sxs-lookup"><span data-stu-id="caaa1-174">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="caaa1-175">Push-Location</span><span class="sxs-lookup"><span data-stu-id="caaa1-175">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="caaa1-176">Set-Location</span><span class="sxs-lookup"><span data-stu-id="caaa1-176">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="caaa1-177">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="caaa1-177">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="caaa1-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="caaa1-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
