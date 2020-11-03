---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 4f5dffdc942112672c3a193fd1fef49b3b5c15d6
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "93195127"
---
# <span data-ttu-id="e8b61-103">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="e8b61-103">Pop-Location</span></span>

## <span data-ttu-id="e8b61-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e8b61-104">SYNOPSIS</span></span>
<span data-ttu-id="e8b61-105">Altera o local atual para o local mais recentemente inserido na pilha.</span><span class="sxs-lookup"><span data-stu-id="e8b61-105">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="e8b61-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8b61-106">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="e8b61-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8b61-107">DESCRIPTION</span></span>

<span data-ttu-id="e8b61-108">O `Pop-Location` cmdlet altera o local atual para o local mais recentemente enviado para a pilha usando o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-108">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="e8b61-109">Você pode mostrar um local da pilha padrão ou de uma pilha que você cria usando um `Push-Location` comando.</span><span class="sxs-lookup"><span data-stu-id="e8b61-109">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="e8b61-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e8b61-110">EXAMPLES</span></span>

### <span data-ttu-id="e8b61-111">Exemplo 1: alterar para o local mais recente</span><span class="sxs-lookup"><span data-stu-id="e8b61-111">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="e8b61-112">Este comando altera o local para o local mais recentemente adicionado à pilha atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-112">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="e8b61-113">Exemplo 2: alterar para o local mais recente em uma pilha nomeada</span><span class="sxs-lookup"><span data-stu-id="e8b61-113">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="e8b61-114">Este comando altera o local para o local mais recentemente adicionado à pilha de local Stack2.</span><span class="sxs-lookup"><span data-stu-id="e8b61-114">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="e8b61-115">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="e8b61-115">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="e8b61-116">Exemplo 3: mover entre locais para provedores diferentes</span><span class="sxs-lookup"><span data-stu-id="e8b61-116">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="e8b61-117">Esses comandos usam os `Push-Location` `Pop-Location` cmdlets e para se mover entre os locais com suporte de diferentes provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b61-117">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="e8b61-118">Os comandos usam o `pushd` alias para `Push-Location` e o `popd` alias para `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="e8b61-118">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="e8b61-119">O primeiro comando envia o local do sistema de arquivos atual para a pilha e move para a unidade HKLM suportada pelo provedor de registro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b61-119">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="e8b61-120">O segundo comando envia o local do registro para a pilha e move para um local com suporte do provedor de certificados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b61-120">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="e8b61-121">Os dois últimos comandos removem esses locais da pilha.</span><span class="sxs-lookup"><span data-stu-id="e8b61-121">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="e8b61-122">O primeiro `popd` comando retorna à unidade do registro e o segundo comando retorna à unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e8b61-122">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="e8b61-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8b61-123">PARAMETERS</span></span>

### <span data-ttu-id="e8b61-124">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e8b61-124">-PassThru</span></span>

<span data-ttu-id="e8b61-125">Passa um objeto que representa o local para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="e8b61-125">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="e8b61-126">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e8b61-126">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e8b61-127">-StackName</span><span class="sxs-lookup"><span data-stu-id="e8b61-127">-StackName</span></span>

<span data-ttu-id="e8b61-128">Especifica a pilha do local de onde o local é exibido.</span><span class="sxs-lookup"><span data-stu-id="e8b61-128">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="e8b61-129">Digite um nome de pilha de local.</span><span class="sxs-lookup"><span data-stu-id="e8b61-129">Enter a location stack name.</span></span>

<span data-ttu-id="e8b61-130">Sem esse parâmetro, `Pop-Location` o exibe um local da pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-130">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="e8b61-131">Por padrão, a pilha de local atual é a pilha de locais padrão sem nome que o PowerShell cria.</span><span class="sxs-lookup"><span data-stu-id="e8b61-131">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="e8b61-132">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-132">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="e8b61-133">Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).</span><span class="sxs-lookup"><span data-stu-id="e8b61-133">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="e8b61-134">`Pop-Location` Não é possível retirar um local da pilha padrão sem nome, a menos que seja a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-134">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

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

### <span data-ttu-id="e8b61-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e8b61-135">CommonParameters</span></span>

<span data-ttu-id="e8b61-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e8b61-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8b61-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e8b61-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e8b61-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e8b61-138">INPUTS</span></span>

### <span data-ttu-id="e8b61-139">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e8b61-139">None</span></span>

<span data-ttu-id="e8b61-140">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-140">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e8b61-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e8b61-141">OUTPUTS</span></span>

### <span data-ttu-id="e8b61-142">Nenhum, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="e8b61-142">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="e8b61-143">Esse cmdlet gera um objeto **System. Management. Automation. PathInfo** que representa o local, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="e8b61-143">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="e8b61-144">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e8b61-144">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e8b61-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e8b61-145">NOTES</span></span>

<span data-ttu-id="e8b61-146">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="e8b61-146">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="e8b61-147">Cada runspace tem seu próprio _diretório atual_ .</span><span class="sxs-lookup"><span data-stu-id="e8b61-147">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="e8b61-148">Isso não é o mesmo que `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="e8b61-148">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="e8b61-149">Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.</span><span class="sxs-lookup"><span data-stu-id="e8b61-149">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="e8b61-150">Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="e8b61-150">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="e8b61-151">Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-151">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="e8b61-152">Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="e8b61-152">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="e8b61-153">Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="e8b61-153">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="e8b61-154">O PowerShell permite que você armazene locais de provedores em pilhas de locais.</span><span class="sxs-lookup"><span data-stu-id="e8b61-154">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="e8b61-155">O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas.</span><span class="sxs-lookup"><span data-stu-id="e8b61-155">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="e8b61-156">Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-156">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="e8b61-157">Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-157">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="e8b61-158">Para gerenciar as pilhas de locais, use os `*-Location` cmdlets do PowerShell, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e8b61-158">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="e8b61-159">Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-159">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="e8b61-160">Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-160">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="e8b61-161">Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-161">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="e8b61-162">Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-162">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="e8b61-163">Para criar uma nova pilha de locais, use o parâmetro **StackName** do `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-163">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="e8b61-164">Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.</span><span class="sxs-lookup"><span data-stu-id="e8b61-164">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="e8b61-165">Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b61-165">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="e8b61-166">A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.</span><span class="sxs-lookup"><span data-stu-id="e8b61-166">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="e8b61-167">Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome.</span><span class="sxs-lookup"><span data-stu-id="e8b61-167">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="e8b61-168">Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$Null` ou uma cadeia de caracteres vazia ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="e8b61-168">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="e8b61-169">Você também pode consultar `Pop-Location` por seu alias interno, `popd` .</span><span class="sxs-lookup"><span data-stu-id="e8b61-169">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="e8b61-170">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="e8b61-170">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="e8b61-171">`Pop-Location` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="e8b61-171">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="e8b61-172">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="e8b61-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="e8b61-173">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e8b61-173">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e8b61-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e8b61-174">RELATED LINKS</span></span>

[<span data-ttu-id="e8b61-175">Get-Location</span><span class="sxs-lookup"><span data-stu-id="e8b61-175">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="e8b61-176">Push-Location</span><span class="sxs-lookup"><span data-stu-id="e8b61-176">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="e8b61-177">Set-Location</span><span class="sxs-lookup"><span data-stu-id="e8b61-177">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="e8b61-178">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="e8b61-178">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="e8b61-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e8b61-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
