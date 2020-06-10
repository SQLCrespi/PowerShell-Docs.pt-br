---
title: Tudo o que você queria saber sobre o ShouldProcess
description: O ShouldProcess é um recurso importante que geralmente é ignorado. Os parâmetros WhatIf e Confirm o tornam fáceis de adicionar às suas funções.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1d9110302a191b90bd11bdf742f77704a8c9d6f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149479"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a><span data-ttu-id="50302-104">Tudo o que você queria saber sobre o ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="50302-104">Everything you wanted to know about ShouldProcess</span></span>

<span data-ttu-id="50302-105">As funções do PowerShell têm vários recursos que melhoram muito a maneira como os usuários interagem com eles.</span><span class="sxs-lookup"><span data-stu-id="50302-105">PowerShell functions have several features that greatly improve the way users interact with them.</span></span>
<span data-ttu-id="50302-106">Um recurso importante que muitas vezes é ignorado é o suporte para `-WhatIf` e `-Confirm`, e é muito fácil de adicioná-lo às suas funções.</span><span class="sxs-lookup"><span data-stu-id="50302-106">One important feature that is often overlooked is `-WhatIf` and `-Confirm` support and it's easy to add to your functions.</span></span> <span data-ttu-id="50302-107">Neste artigo, vamos nos aprofundar em como implementar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="50302-107">In this article, we dive deep into how to implement this feature.</span></span>

> [!NOTE]
> <span data-ttu-id="50302-108">A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="50302-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="50302-109">A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="50302-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="50302-110">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="50302-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

<span data-ttu-id="50302-111">Esse é um recurso simples e que você pode habilitar em suas funções para fornecer uma rede de segurança aos usuários que precisarem.</span><span class="sxs-lookup"><span data-stu-id="50302-111">This is a simple feature you can enable in your functions to provide a safety net for the users that need it.</span></span> <span data-ttu-id="50302-112">Não há nada mais assustador do que executar pela primeira vez um comando que você sabe que pode ser perigoso.</span><span class="sxs-lookup"><span data-stu-id="50302-112">There's nothing scarier than running a command that you know can be dangerous for the first time.</span></span> <span data-ttu-id="50302-113">A opção de executá-lo com `-WhatIf` pode fazer uma grande diferença.</span><span class="sxs-lookup"><span data-stu-id="50302-113">The option to run it with `-WhatIf` can make a big difference.</span></span>

## <a name="commonparameters"></a><span data-ttu-id="50302-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50302-114">CommonParameters</span></span>

<span data-ttu-id="50302-115">Antes de vermos como implementar esses [parâmetros comuns][], vamos dar uma olhada em como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="50302-115">Before we look at implementing these [common parameters][], I want to take a quick look at how they're used.</span></span>

## <a name="using--whatif"></a><span data-ttu-id="50302-116">Usando o -WhatIf</span><span class="sxs-lookup"><span data-stu-id="50302-116">Using -WhatIf</span></span>

<span data-ttu-id="50302-117">Quando um comando dá suporte ao parâmetro `-WhatIf`, ele permite que você veja o que o comando teria feito em vez de fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="50302-117">When a command supports the `-WhatIf` parameter, it allows you to see what the command would have done instead of making changes.</span></span> <span data-ttu-id="50302-118">É uma boa maneira de testar o impacto de um comando, especialmente antes de fazer algo destrutivo.</span><span class="sxs-lookup"><span data-stu-id="50302-118">it's a good way to test out the impact of a command, especially before you do something destructive.</span></span>

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="50302-119">Se o comando implementar corretamente `ShouldProcess`, ele mostrará todas as alterações que teria feito.</span><span class="sxs-lookup"><span data-stu-id="50302-119">If the command correctly implements `ShouldProcess`, it should show you all the changes that it would have made.</span></span> <span data-ttu-id="50302-120">Aqui está um exemplo que usa um curinga para excluir vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="50302-120">Here is an example using a wildcard to delete multiple files.</span></span>

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a><span data-ttu-id="50302-121">Usando o -Confirm</span><span class="sxs-lookup"><span data-stu-id="50302-121">Using -Confirm</span></span>

<span data-ttu-id="50302-122">Comandos que oferecem suporte ao `-WhatIf` também oferecem suporte ao `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="50302-122">Commands that support `-WhatIf` also support `-Confirm`.</span></span> <span data-ttu-id="50302-123">Isso dá a você a chance de confirmar uma ação antes de executá-la.</span><span class="sxs-lookup"><span data-stu-id="50302-123">This gives you a chance confirm an action before performing it.</span></span>

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="50302-124">Nesse caso, você tem várias opções que permitem continuar, ignorar uma alteração ou parar o script.</span><span class="sxs-lookup"><span data-stu-id="50302-124">In this case, you have multiple options that allow you to continue, skip a change, or stop the script.</span></span> <span data-ttu-id="50302-125">O prompt de ajuda descreve cada uma dessas opções assim.</span><span class="sxs-lookup"><span data-stu-id="50302-125">The help prompt describes each of those options like this.</span></span>

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a><span data-ttu-id="50302-126">Localização</span><span class="sxs-lookup"><span data-stu-id="50302-126">Localization</span></span>

<span data-ttu-id="50302-127">Esse prompt é localizado no PowerShell para que o idioma seja alterado com base no idioma do seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="50302-127">This prompt is localized in PowerShell so the language changes based on the language of your operating system.</span></span> <span data-ttu-id="50302-128">Essa é mais uma das coisas que o PowerShell gerencia para você.</span><span class="sxs-lookup"><span data-stu-id="50302-128">This is one more thing that PowerShell manages for you.</span></span>

### <a name="switch-parameters"></a><span data-ttu-id="50302-129">Parâmetros de opção</span><span class="sxs-lookup"><span data-stu-id="50302-129">Switch parameters</span></span>

<span data-ttu-id="50302-130">Vejamos rapidamente algumas maneiras de como passar um valor para um parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="50302-130">Let's take quick moment to look at ways to pass a value to a switch parameter.</span></span> <span data-ttu-id="50302-131">O principal motivo pelo qual eu enfatizo isso é que, muitas vezes, você deseja passar valores de parâmetro para as funções que chama.</span><span class="sxs-lookup"><span data-stu-id="50302-131">The main reason I call this out is that you often want to pass parameter values to functions you call.</span></span>

<span data-ttu-id="50302-132">A primeira abordagem é uma sintaxe de parâmetro específica que pode ser usada para todos os parâmetros, mas que é usada principalmente para parâmetros de switch.</span><span class="sxs-lookup"><span data-stu-id="50302-132">The first approach is a specific parameter syntax that can be used for all parameters but you mostly see it used for switch parameters.</span></span> <span data-ttu-id="50302-133">Você especifica dois-pontos para anexar um valor ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="50302-133">You specify a colon to attach a value to the parameter.</span></span>

```powershell
Remove-Item -Path:* -WhatIf:$true
```

<span data-ttu-id="50302-134">Você pode fazer o mesmo com uma variável.</span><span class="sxs-lookup"><span data-stu-id="50302-134">You can do the same with a variable.</span></span>

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

<span data-ttu-id="50302-135">A segunda abordagem é usar uma tabela de hash para nivelar o valor.</span><span class="sxs-lookup"><span data-stu-id="50302-135">The second approach is to use a hashtable to splat the value.</span></span>

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

<span data-ttu-id="50302-136">Caso você seja um novato em tabelas de hash ou nivelamento, escrevi outro artigo sobre isso que aborda [tudo o que você queria saber sobre as tabelas de hash][].</span><span class="sxs-lookup"><span data-stu-id="50302-136">If you're new to hashtables or splatting, I have another article on that covers [everything you wanted to know about hashtables][].</span></span>

## <a name="supportsshouldprocess"></a><span data-ttu-id="50302-137">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="50302-137">SupportsShouldProcess</span></span>

<span data-ttu-id="50302-138">A primeira etapa para habilitar o suporte a `-WhatIf` e `-Confirm` é especificar `SupportsShouldProcess` no `CmdletBinding` de sua função.</span><span class="sxs-lookup"><span data-stu-id="50302-138">The first step to enable `-WhatIf` and `-Confirm` support is to specify `SupportsShouldProcess` in the `CmdletBinding` of your function.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

<span data-ttu-id="50302-139">Ao especificar `SupportsShouldProcess` dessa forma, podemos chamar nossa função com `-WhatIf` (ou `-Confirm`).</span><span class="sxs-lookup"><span data-stu-id="50302-139">By specifying `SupportsShouldProcess` in this way, we can now call our function with `-WhatIf` (or `-Confirm`).</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="50302-140">Observe que eu não criei um parâmetro chamado `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-140">Notice that I did not create a parameter called `-WhatIf`.</span></span> <span data-ttu-id="50302-141">Especificar `SupportsShouldProcess` automaticamente o cria para nós.</span><span class="sxs-lookup"><span data-stu-id="50302-141">Specifying `SupportsShouldProcess` automatically creates it for us.</span></span> <span data-ttu-id="50302-142">Quando especificamos o parâmetro `-WhatIf` no `Test-ShouldProcess`, algumas coisas que chamamos também executam o processamento `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-142">When we specify the `-WhatIf` parameter on `Test-ShouldProcess`, some things we call also perform `-WhatIf` processing.</span></span>

### <a name="trust-but-verify"></a><span data-ttu-id="50302-143">Confiar sem deixar de verificar</span><span class="sxs-lookup"><span data-stu-id="50302-143">Trust but verify</span></span>

<span data-ttu-id="50302-144">Há certo perigo em confiar que tudo o que você chama herdará valores `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-144">There's some danger here trusting that everything you call inherits `-WhatIf` values.</span></span> <span data-ttu-id="50302-145">Para o restante dos exemplos, vou supor que não funcionará assim e serei bastante explícito ao fazer chamadas para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="50302-145">For the rest of the examples, I'm going to assume that it doesn't work and be very explicit when making calls to other commands.</span></span> <span data-ttu-id="50302-146">Recomendo que você faça o mesmo.</span><span class="sxs-lookup"><span data-stu-id="50302-146">I recommend that you do the same.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIf
}
```

<span data-ttu-id="50302-147">Revisitarei as nuances mais tarde, quando você já você tiver uma compreensão melhor de todas as peças em jogo.</span><span class="sxs-lookup"><span data-stu-id="50302-147">I will revisit the nuances much later once you have a better understanding of all the pieces in play.</span></span>

## <a name="pscmdletshouldprocess"></a><span data-ttu-id="50302-148">$PSCmdlet.ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="50302-148">$PSCmdlet.ShouldProcess</span></span>

<span data-ttu-id="50302-149">O método que permite implementar `SupportsShouldProcess` é `$PSCmdlet.ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="50302-149">The method that allows you to implement `SupportsShouldProcess` is `$PSCmdlet.ShouldProcess`.</span></span> <span data-ttu-id="50302-150">Você chama `$PSCmdlet.ShouldProcess(...)` para ver se deve processar alguma lógica e o PowerShell cuida do resto.</span><span class="sxs-lookup"><span data-stu-id="50302-150">You call `$PSCmdlet.ShouldProcess(...)` to see if you should process some logic and PowerShell takes care of the rest.</span></span> <span data-ttu-id="50302-151">Vamos começar com um exemplo:</span><span class="sxs-lookup"><span data-stu-id="50302-151">Let's start with an example:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

<span data-ttu-id="50302-152">A chamada para `$PSCmdlet.ShouldProcess($file.name)` verifica a `-WhatIf` (e o parâmetro `-Confirm`) e então a manipula adequadamente.</span><span class="sxs-lookup"><span data-stu-id="50302-152">The call to `$PSCmdlet.ShouldProcess($file.name)` checks for the `-WhatIf` (and `-Confirm` parameter) then handles it accordingly.</span></span> <span data-ttu-id="50302-153">O `-WhatIf` faz com que `ShouldProcess` gere uma descrição da alteração e retorne `$false`:</span><span class="sxs-lookup"><span data-stu-id="50302-153">The `-WhatIf` causes `ShouldProcess` to output a description of the change and return `$false`:</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

<span data-ttu-id="50302-154">Uma chamada usando `-Confirm` pausa o script e solicita ao usuário a opção de continuar.</span><span class="sxs-lookup"><span data-stu-id="50302-154">A call using `-Confirm` pauses the script and prompts the user with the option to continue.</span></span> <span data-ttu-id="50302-155">Ele retornará `$true` se o usuário tiver selecionado `Y`.</span><span class="sxs-lookup"><span data-stu-id="50302-155">It returns `$true` if the user selected `Y`.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="50302-156">Um recurso incrível do `$PSCmdlet.ShouldProcess` é que ele dobra como saída detalhada.</span><span class="sxs-lookup"><span data-stu-id="50302-156">An awesome feature of `$PSCmdlet.ShouldProcess` is that it doubles as verbose output.</span></span> <span data-ttu-id="50302-157">Eu dependo disso com frequência ao implementar `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="50302-157">I depend on this often when implementing `ShouldProcess`.</span></span>

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a><span data-ttu-id="50302-158">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="50302-158">Overloads</span></span>

<span data-ttu-id="50302-159">Há algumas sobrecargas diferentes para `$PSCmdlet.ShouldProcess` com parâmetros diferentes para personalizar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="50302-159">There are a few different overloads for `$PSCmdlet.ShouldProcess` with different parameters for customizing the messaging.</span></span> <span data-ttu-id="50302-160">Já vimos a primeira no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="50302-160">We already saw the first one in the example above.</span></span> <span data-ttu-id="50302-161">Vamos examinar cada uma com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="50302-161">Let's take a closer look at it.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

<span data-ttu-id="50302-162">Isso produz a saída que inclui o nome da função e o destino (valor do parâmetro).</span><span class="sxs-lookup"><span data-stu-id="50302-162">This produces output that includes both the function name and the target (value of the parameter).</span></span>

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

<span data-ttu-id="50302-163">Ao especificar um segundo parâmetro como a operação, o valor da operação é usado em vez do nome da função na mensagem.</span><span class="sxs-lookup"><span data-stu-id="50302-163">Specifying a second parameter as the operation uses the operation value instead of the function name in the message.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

<span data-ttu-id="50302-164">A próxima opção é especificar três parâmetros para personalizar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="50302-164">The next option is to specify three parameters to fully customize the message.</span></span> <span data-ttu-id="50302-165">Quando três parâmetros são usados, o primeiro é a mensagem inteira.</span><span class="sxs-lookup"><span data-stu-id="50302-165">When three parameters are used, the first one is the entire message.</span></span> <span data-ttu-id="50302-166">Os dois parâmetros seguintes ainda são usados na saída da mensagem de `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="50302-166">The second two parameters are still used in the `-Confirm` message output.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a><span data-ttu-id="50302-167">Referência de parâmetro rápida</span><span class="sxs-lookup"><span data-stu-id="50302-167">Quick parameter reference</span></span>

<span data-ttu-id="50302-168">Caso você esteja aqui apenas para descobrir quais parâmetros devem ser usados, aqui está uma referência rápida que mostra como os parâmetros alteram a mensagem nos diferentes cenários de `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-168">Just in case you came here only to figure out what parameters you should use, here is a quick reference showing how the parameters change the message in the different `-WhatIf` scenarios.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

<span data-ttu-id="50302-169">Eu tenho a tendência de usar o de dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="50302-169">I tend to use the one with two parameters.</span></span>

### <a name="shouldprocessreason"></a><span data-ttu-id="50302-170">ShouldProcessReason</span><span class="sxs-lookup"><span data-stu-id="50302-170">ShouldProcessReason</span></span>

<span data-ttu-id="50302-171">Há uma quarta sobrecarga que é mais avançada do que as outras.</span><span class="sxs-lookup"><span data-stu-id="50302-171">We have a fourth overload that's more advanced than the others.</span></span> <span data-ttu-id="50302-172">Ela permite que você obtenha o motivo `ShouldProcess` foi executado.</span><span class="sxs-lookup"><span data-stu-id="50302-172">It allows you to get the reason `ShouldProcess` was executed.</span></span> <span data-ttu-id="50302-173">Estou adicionando isso aqui apenas para fins de completude, pois podemos só verificar se `$WhatIf` está `$true`.</span><span class="sxs-lookup"><span data-stu-id="50302-173">I'm only adding this here for completeness because we can just check if `$WhatIf` is `$true` instead.</span></span>

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

<span data-ttu-id="50302-174">Precisamos passar a variável `$reason` para o quarto parâmetro como uma variável de referência com `[ref]`.</span><span class="sxs-lookup"><span data-stu-id="50302-174">We have to pass the `$reason` variable into the fourth parameter as a reference variable with `[ref]`.</span></span> <span data-ttu-id="50302-175">`ShouldProcess` preenche `$reason` com o valor `None` ou `WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-175">`ShouldProcess` populates `$reason` with the value `None` or `WhatIf`.</span></span> <span data-ttu-id="50302-176">Eu nunca disse que isso era útil, nem que eu já tenha precisado usar.</span><span class="sxs-lookup"><span data-stu-id="50302-176">I didn't say this was useful and I have had no reason to ever use it.</span></span>

### <a name="where-to-place-it"></a><span data-ttu-id="50302-177">Onde colocar</span><span class="sxs-lookup"><span data-stu-id="50302-177">Where to place it</span></span>

<span data-ttu-id="50302-178">Você usa `ShouldProcess` para tornar seus scripts mais seguros.</span><span class="sxs-lookup"><span data-stu-id="50302-178">You use `ShouldProcess` to make your scripts safer.</span></span> <span data-ttu-id="50302-179">Portanto, você deve usá-lo quando seus scripts estão fazendo alterações.</span><span class="sxs-lookup"><span data-stu-id="50302-179">So you use it when your scripts are making changes.</span></span> <span data-ttu-id="50302-180">Gosto de posicionar a chamada de `$PSCmdlet.ShouldProcess` o mais próximo possível da alteração.</span><span class="sxs-lookup"><span data-stu-id="50302-180">I like to place the `$PSCmdlet.ShouldProcess` call as close to the change as possible.</span></span>

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

<span data-ttu-id="50302-181">Se eu estiver processando uma coleção de itens, eu o chamo para cada item.</span><span class="sxs-lookup"><span data-stu-id="50302-181">If I'm processing a collection of items, I call it for each item.</span></span> <span data-ttu-id="50302-182">Portanto, a chamada é colocada dentro do loop foreach.</span><span class="sxs-lookup"><span data-stu-id="50302-182">So the call gets placed inside the foreach loop.</span></span>

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

<span data-ttu-id="50302-183">O motivo pelo qual eu coloco `ShouldProcess` rigidamente ao redor da alteração, é porque eu quero que o máximo de códigos possível seja executado quando `-WhatIf` for especificado.</span><span class="sxs-lookup"><span data-stu-id="50302-183">The reason why I place `ShouldProcess` tightly around the change, is that I want as much code to execute as possible when `-WhatIf` is specified.</span></span> <span data-ttu-id="50302-184">Quero que a instalação e a validação sejam executadas, se possível, de maneira que o usuário veja esses erros.</span><span class="sxs-lookup"><span data-stu-id="50302-184">I want the setup and validation to run if possible so the user gets to see those errors.</span></span>

<span data-ttu-id="50302-185">Também gosto de usar isso em testes do Pester que validem meus projetos.</span><span class="sxs-lookup"><span data-stu-id="50302-185">I also like to use this in my Pester tests that validate my projects.</span></span> <span data-ttu-id="50302-186">Se eu tiver uma parte da lógica difícil de simular em Pester, eu geralmente a encapsulo `ShouldProcess` e a chamo com `-WhatIf` em meus testes.</span><span class="sxs-lookup"><span data-stu-id="50302-186">If I have a piece of logic that is hard to mock in pester, I can often wrap it in `ShouldProcess` and call it with `-WhatIf` in my tests.</span></span> <span data-ttu-id="50302-187">É melhor testar parte do código do que nenhum código.</span><span class="sxs-lookup"><span data-stu-id="50302-187">It's better to test some of your code than none of it.</span></span>

### <a name="whatifpreference"></a><span data-ttu-id="50302-188">$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="50302-188">$WhatIfPreference</span></span>

<span data-ttu-id="50302-189">A primeira variável de preferência que temos é `$WhatIfPreference`.</span><span class="sxs-lookup"><span data-stu-id="50302-189">The first preference variable we have is `$WhatIfPreference`.</span></span> <span data-ttu-id="50302-190">Por padrão, é `$false`.</span><span class="sxs-lookup"><span data-stu-id="50302-190">This is `$false` by default.</span></span> <span data-ttu-id="50302-191">Se você a definir como `$true`, a função será executada como se você tivesse especificado `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-191">If you set it to `$true` then your function executes as if you specified `-WhatIf`.</span></span> <span data-ttu-id="50302-192">Se você definir isso em sua sessão, todos os comandos executarão `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="50302-192">If you set this in your session, all commands perform `-WhatIf` execution.</span></span>

<span data-ttu-id="50302-193">Quando você chama uma função com `-WhatIf`, o valor de `$WhatIfPreference` é definido como `$true` dentro do escopo da sua função.</span><span class="sxs-lookup"><span data-stu-id="50302-193">When you call a function with `-WhatIf`, the value of `$WhatIfPreference` gets set to `$true` inside the scope of your function.</span></span>

## <a name="confirmimpact"></a><span data-ttu-id="50302-194">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="50302-194">ConfirmImpact</span></span>

<span data-ttu-id="50302-195">A maioria dos meus exemplos são para `-WhatIf`, mas tudo o que vimos até agora também funciona com `-Confirm` para solicitar ao usuário.</span><span class="sxs-lookup"><span data-stu-id="50302-195">Most of my examples are for `-WhatIf` but everything so far also works with `-Confirm` to prompt the user.</span></span> <span data-ttu-id="50302-196">Você pode definir a `ConfirmImpact` da função como alta e ela solicitará ao usuário como se fosse chamada com `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="50302-196">You can set the `ConfirmImpact` of the function to high and it prompts the user as if it was called with `-Confirm`.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="50302-197">Essa chamada para `Test-ShouldProcess` está executando a ação `-Confirm` devido ao impacto `High`.</span><span class="sxs-lookup"><span data-stu-id="50302-197">This call to `Test-ShouldProcess` is performing the `-Confirm` action because of the `High` impact.</span></span>

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

<span data-ttu-id="50302-198">O problema óbvio é que agora é mais difícil usar em outros scripts sem avisar o usuário.</span><span class="sxs-lookup"><span data-stu-id="50302-198">The obvious issue is that now it's harder to use in other scripts without prompting the user.</span></span> <span data-ttu-id="50302-199">Nesse caso, podemos passar um `$false` para `-Confirm` para suprimir o prompt.</span><span class="sxs-lookup"><span data-stu-id="50302-199">In this case, we can pass a `$false` to `-Confirm` to suppress the prompt.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

<span data-ttu-id="50302-200">Abordarei como adicionar o suporte a `-Force` em uma seção posterior.</span><span class="sxs-lookup"><span data-stu-id="50302-200">I'll cover how to add `-Force` support in a later section.</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="50302-201">$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="50302-201">$ConfirmPreference</span></span>

<span data-ttu-id="50302-202">`$ConfirmPreference` é uma variável automática que controla quando `ConfirmImpact` solicita que você confirme a execução.</span><span class="sxs-lookup"><span data-stu-id="50302-202">`$ConfirmPreference` is an automatic variable that controls when `ConfirmImpact` asks you to confirm execution.</span></span> <span data-ttu-id="50302-203">Estes são os valores possíveis tanto para `$ConfirmPreference`, como para `ConfirmImpact`.</span><span class="sxs-lookup"><span data-stu-id="50302-203">Here are the possible values for both `$ConfirmPreference` and `ConfirmImpact`.</span></span>

- `High`
- `Medium`
- `Low`
- `None`

<span data-ttu-id="50302-204">Com esses valores, você pode especificar diferentes níveis de impacto para cada função.</span><span class="sxs-lookup"><span data-stu-id="50302-204">With these values, you can specify different levels of impact for each function.</span></span> <span data-ttu-id="50302-205">Se você tiver `$ConfirmPreference` definido com um valor maior que `ConfirmImpact`, não será solicitado que confirme a execução.</span><span class="sxs-lookup"><span data-stu-id="50302-205">If you have `$ConfirmPreference` set to a value higher than `ConfirmImpact`, then you aren't prompted to confirm execution.</span></span>

<span data-ttu-id="50302-206">Por padrão, `$ConfirmPreference` é definido como `High` e `ConfirmImpact`, como `Medium`.</span><span class="sxs-lookup"><span data-stu-id="50302-206">By default, `$ConfirmPreference` is set to `High` and `ConfirmImpact` is `Medium`.</span></span> <span data-ttu-id="50302-207">Se você quiser que sua função solicite automaticamente o usuário, defina seu `ConfirmImpact` como `High`.</span><span class="sxs-lookup"><span data-stu-id="50302-207">If you want your function to automatically prompt the user, set your `ConfirmImpact` to `High`.</span></span> <span data-ttu-id="50302-208">Caso contrário, defina-o como `Medium` se for destrutivo e use `Low` se o comando for sempre seguro ao executar o ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="50302-208">Otherwise set it to `Medium` if its destructive and use `Low` if the command is always safe run in production.</span></span> <span data-ttu-id="50302-209">Se você o definir como `none`, ele não será solicitado mesmo que `-Confirm` tenha sido especificado (mas ainda oferece suporte a `-WhatIf`).</span><span class="sxs-lookup"><span data-stu-id="50302-209">If you set it to `none`, it doesn't prompt even if `-Confirm` was specified (but it still gives you `-WhatIf` support).</span></span>

<span data-ttu-id="50302-210">Ao chamar uma função com `-Confirm`, o valor de `$ConfirmPreference` é definido como `Low` dentro do escopo da sua função.</span><span class="sxs-lookup"><span data-stu-id="50302-210">When calling a function with `-Confirm`, the value of `$ConfirmPreference` gets set to `Low` inside the scope of your function.</span></span>

### <a name="suppressing-nested-confirm-prompts"></a><span data-ttu-id="50302-211">Como suprimir prompts de confirmação aninhados</span><span class="sxs-lookup"><span data-stu-id="50302-211">Suppressing nested confirm prompts</span></span>

<span data-ttu-id="50302-212">O `$ConfirmPreference` pode ser obtido por funções que você chamou.</span><span class="sxs-lookup"><span data-stu-id="50302-212">The `$ConfirmPreference` can get picked up by functions that you call.</span></span> <span data-ttu-id="50302-213">Isso pode criar cenários em que você adiciona um prompt de confirmação e a função que você chama também solicita ao usuário.</span><span class="sxs-lookup"><span data-stu-id="50302-213">This can create scenarios where you add a confirm prompt and the function you call also prompts the user.</span></span>

<span data-ttu-id="50302-214">Nesse caso, eu geralmente especifico `-Confirm:$false` nos comandos que eu chamo quando já tratei do prompt.</span><span class="sxs-lookup"><span data-stu-id="50302-214">What I tend to do is specify `-Confirm:$false` on the commands that I call when I have already handled the prompting.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

<span data-ttu-id="50302-215">Isso nos leva de volta para o que já chamei a atenção antes: Há nuances sobre quando `-WhatIf` não é passado para uma função e quando `-Confirm` passa para uma função.</span><span class="sxs-lookup"><span data-stu-id="50302-215">This brings us back to an earlier warning: There are nuances as to when `-WhatIf` is not passed to a function and when `-Confirm` passes to a function.</span></span> <span data-ttu-id="50302-216">Prometo que tratarei disso depois.</span><span class="sxs-lookup"><span data-stu-id="50302-216">I promise I'll get back to this later.</span></span>

## <a name="pscmdletshouldcontinue"></a><span data-ttu-id="50302-217">$PSCmdlet.ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="50302-217">$PSCmdlet.ShouldContinue</span></span>

<span data-ttu-id="50302-218">Se precisar de mais controle do que `ShouldProcess` fornece, você poderá disparar o prompt diretamente com `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-218">If you need more control than `ShouldProcess` provides, you can trigger the prompt directly with `ShouldContinue`.</span></span> <span data-ttu-id="50302-219">`ShouldContinue` ignora `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference` e `-WhatIf` porque eles são solicitados toda vez que são executados.</span><span class="sxs-lookup"><span data-stu-id="50302-219">`ShouldContinue` ignores `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference`, and `-WhatIf` because it prompts every time it's executed.</span></span>

<span data-ttu-id="50302-220">De relance, é fácil confundir `ShouldProcess` e `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-220">At a quick glance, it's easy to confuse `ShouldProcess` and `ShouldContinue`.</span></span> <span data-ttu-id="50302-221">Eu geralmente me lembro de usar `ShouldProcess` porque o parâmetro é chamado `SupportsShouldProcess` no `CmdletBinding`.</span><span class="sxs-lookup"><span data-stu-id="50302-221">I tend to remember to use `ShouldProcess` because the parameter is called `SupportsShouldProcess` in the `CmdletBinding`.</span></span>
<span data-ttu-id="50302-222">Você deve usar `ShouldProcess` em quase todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="50302-222">You should use `ShouldProcess` in almost every scenario.</span></span> <span data-ttu-id="50302-223">É por isso que abordei esse método primeiro.</span><span class="sxs-lookup"><span data-stu-id="50302-223">That is why I covered that method first.</span></span>

<span data-ttu-id="50302-224">Vamos dar uma olhada no `ShouldContinue` em ação.</span><span class="sxs-lookup"><span data-stu-id="50302-224">Let's take a look at `ShouldContinue` in action.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="50302-225">Isso nos dá um prompt mais simples com menos opções.</span><span class="sxs-lookup"><span data-stu-id="50302-225">This provides us a simpler prompt with fewer options.</span></span>

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="50302-226">O maior problema com `ShouldContinue` é que ele requer que o usuário o execute interativamente porque ele sempre solicita ao usuário.</span><span class="sxs-lookup"><span data-stu-id="50302-226">The biggest issue with `ShouldContinue` is that it requires the user to run it interactively because it always prompts the user.</span></span> <span data-ttu-id="50302-227">Você deve estar sempre criando ferramentas que podem ser usadas por outros scripts.</span><span class="sxs-lookup"><span data-stu-id="50302-227">You should always be building tools that can be used by other scripts.</span></span> <span data-ttu-id="50302-228">A maneira de fazer isso é implementar `-Force`.</span><span class="sxs-lookup"><span data-stu-id="50302-228">The way you do this is by implementing `-Force`.</span></span> <span data-ttu-id="50302-229">Voltarei a essa ideia mais tarde.</span><span class="sxs-lookup"><span data-stu-id="50302-229">I'll revisit this idea later.</span></span>

### <a name="yes-to-all"></a><span data-ttu-id="50302-230">Sim para todos</span><span class="sxs-lookup"><span data-stu-id="50302-230">Yes to all</span></span>

<span data-ttu-id="50302-231">Isso é manipulado automaticamente com `ShouldProcess`, mas temos que nos esforçar um pouco mais para `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-231">This is automatically handled with `ShouldProcess` but we have to do a little more work for `ShouldContinue`.</span></span> <span data-ttu-id="50302-232">Há uma segunda sobrecarga de método em que precisamos passar alguns valores por referência para controlar a lógica.</span><span class="sxs-lookup"><span data-stu-id="50302-232">There's a second method overload where we have to pass in a few values by reference to control the logic.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

<span data-ttu-id="50302-233">Adicionei um loop de `foreach` e uma coleção para mostrá-lo em ação.</span><span class="sxs-lookup"><span data-stu-id="50302-233">I added a `foreach` loop and a collection to show it in action.</span></span> <span data-ttu-id="50302-234">Eu retirei a chamada `ShouldContinue` da instrução `if` para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="50302-234">I pulled the `ShouldContinue` call out of the `if` statement to make it easier to read.</span></span> <span data-ttu-id="50302-235">Chamar um método com quatro parâmetros não é muito bonito, mas tentei deixar tudo tão limpo quanto pude.</span><span class="sxs-lookup"><span data-stu-id="50302-235">Calling a method with four parameters starts to get a little ugly, but I tried to make it look as clean as I could.</span></span>

## <a name="implementing--force"></a><span data-ttu-id="50302-236">Implementando -Force</span><span class="sxs-lookup"><span data-stu-id="50302-236">Implementing -Force</span></span>

<span data-ttu-id="50302-237">`ShouldProcess` e `ShouldContinue` precisam implementar `-Force` de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="50302-237">`ShouldProcess` and `ShouldContinue` need to implement `-Force` in different ways.</span></span> <span data-ttu-id="50302-238">O truque para essas implementações é que `ShouldProcess` sempre deve ser executado, mas `ShouldContinue` não deve ser executado se `-Force` for especificado.</span><span class="sxs-lookup"><span data-stu-id="50302-238">The trick to these implementations is that `ShouldProcess` should always get executed, but `ShouldContinue` should not get executed if `-Force` is specified.</span></span>

### <a name="shouldprocess--force"></a><span data-ttu-id="50302-239">ShouldProcess -Force</span><span class="sxs-lookup"><span data-stu-id="50302-239">ShouldProcess -Force</span></span>

<span data-ttu-id="50302-240">Se você definir seu `ConfirmImpact` como `high`, a primeira coisa que os usuários tentarão é suprimi-lo com `-Force`.</span><span class="sxs-lookup"><span data-stu-id="50302-240">If you set your `ConfirmImpact` to `high`, the first thing your users are going to try is to suppress it with `-Force`.</span></span> <span data-ttu-id="50302-241">Essa é a primeira coisa que eu faço, pelo menos.</span><span class="sxs-lookup"><span data-stu-id="50302-241">That's the first thing I do anyway.</span></span>

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

<span data-ttu-id="50302-242">Se você se lembra da seção `ConfirmImpact`, elas na verdade precisam chamá-la da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="50302-242">If you recall from the `ConfirmImpact` section, they actually need to call it like this:</span></span>

```powershell
Test-ShouldProcess -Confirm:$false
```

<span data-ttu-id="50302-243">Nem todos percebem que eles precisam fazer isso e que `-Confirm:$false` não suprime `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-243">Not everyone realizes they need to do that and `-Confirm:$false` doesn't suppress `ShouldContinue`.</span></span>
<span data-ttu-id="50302-244">Então, devemos implementar `-Force` pelo bem da saúde mental de nossos usuários.</span><span class="sxs-lookup"><span data-stu-id="50302-244">So we should implement `-Force` for the sanity of our users.</span></span> <span data-ttu-id="50302-245">Dê uma olhada neste exemplo completo:</span><span class="sxs-lookup"><span data-stu-id="50302-245">Take a look at this full example here:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force -and -not $Confirm){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="50302-246">Adicionamos nossa própria opção de `-Force` como um parâmetro e usamos o parâmetro automático `$Confirm` que está disponível ao adicionar `SupportsShouldProcess` no `CmdletBinding`.</span><span class="sxs-lookup"><span data-stu-id="50302-246">We add our own `-Force` switch as a parameter and use the `$Confirm` automatic parameter that is available when adding `SupportsShouldProcess` in the `CmdletBinding`.</span></span>

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

<span data-ttu-id="50302-247">Concentrando-se na lógica de `-Force` aqui:</span><span class="sxs-lookup"><span data-stu-id="50302-247">Focusing in on the `-Force` logic here:</span></span>

```powershell
if ($Force -and -not $Confirm){
    $ConfirmPreference = 'None'
}
```

<span data-ttu-id="50302-248">Se o usuário especificar `-Force`, precisaremos suprimir a solicitação de confirmação, a não ser que também especifique `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="50302-248">If the user specifies `-Force`, we want to suppress the confirm prompt unless they also specify `-Confirm`.</span></span> <span data-ttu-id="50302-249">Isso permite que um usuário Force uma alteração, mas ainda confirma a alteração.</span><span class="sxs-lookup"><span data-stu-id="50302-249">This allows a user to force a change but still confirm the change.</span></span> <span data-ttu-id="50302-250">Em seguida, definimos `$ConfirmPreference` no escopo local onde nossa chamada para `ShouldProcess` os descobre.</span><span class="sxs-lookup"><span data-stu-id="50302-250">Then we set `$ConfirmPreference` in the local scope where our call to `ShouldProcess` discoverers it.</span></span>

```powershell
if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

<span data-ttu-id="50302-251">Caso alguém especifique `-Force` e `-WhatIf`, então `-WhatIf` precisará ter prioridade.</span><span class="sxs-lookup"><span data-stu-id="50302-251">If someone specifies both `-Force` and `-WhatIf`, then `-WhatIf` needs to take priority.</span></span> <span data-ttu-id="50302-252">Essa abordagem preserva o processamento de `-WhatIf` porque `ShouldProcess` sempre é executado.</span><span class="sxs-lookup"><span data-stu-id="50302-252">This approach preserves `-WhatIf` processing because `ShouldProcess` always gets executed.</span></span>

<span data-ttu-id="50302-253">Não adicione uma verificação para o valor de `$Force` dentro da instrução if com o `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="50302-253">Do not add a check for the `$Force` value inside the if statement with the `ShouldProcess`.</span></span> <span data-ttu-id="50302-254">Esse é um antipadrão para esse cenário específico, embora seja a mesma coisa que eu mostrarei na próxima seção para `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-254">That is an anti-pattern for this specific scenario even though that's what I show you in the next section for `ShouldContinue`.</span></span>

### <a name="shouldcontinue--force"></a><span data-ttu-id="50302-255">ShouldContinue-Force</span><span class="sxs-lookup"><span data-stu-id="50302-255">ShouldContinue -Force</span></span>

<span data-ttu-id="50302-256">Essa é a maneira correta de implementar `-Force` com `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-256">This is the correct way to implement `-Force` with `ShouldContinue`.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="50302-257">Ao colocar o `$Force` à esquerda do operador de `-or`, ele é avaliado primeiro.</span><span class="sxs-lookup"><span data-stu-id="50302-257">By placing the `$Force` to the left of the `-or` operator, it gets evaluated first.</span></span> <span data-ttu-id="50302-258">Escrevê-lo dessa forma causa o curto-circuito da execução da instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="50302-258">Writing it this way short circuits the execution of the `if` statement.</span></span> <span data-ttu-id="50302-259">Se `$force` for `$true`, o `ShouldContinue` não será executado.</span><span class="sxs-lookup"><span data-stu-id="50302-259">If `$force` is `$true`, then the `ShouldContinue` is not executed.</span></span>

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

<span data-ttu-id="50302-260">Não precisamos nos preocupar com `-Confirm` ou `-WhatIf` nesse cenário porque eles não têm suporte do `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-260">We don't have to worry about `-Confirm` or `-WhatIf` in this scenario because they're not supported by `ShouldContinue`.</span></span> <span data-ttu-id="50302-261">É por isso que precisamos tratá-lo de maneira diferente do `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="50302-261">This is why it needs to be handled differently than `ShouldProcess`.</span></span>

## <a name="scope-issues"></a><span data-ttu-id="50302-262">Problemas de escopo</span><span class="sxs-lookup"><span data-stu-id="50302-262">Scope issues</span></span>

<span data-ttu-id="50302-263">`-WhatIf` e `-Confirm` devem ser aplicados a tudo dentro de suas funções e a tudo que eles chamam.</span><span class="sxs-lookup"><span data-stu-id="50302-263">Using `-WhatIf` and `-Confirm` are supposed to apply to everything inside your functions and everything they call.</span></span> <span data-ttu-id="50302-264">Eles o fazem definindo `$WhatIfPreference` como `$true` ou definindo `$ConfirmPreference` como `Low` no escopo local da função.</span><span class="sxs-lookup"><span data-stu-id="50302-264">They do this by setting `$WhatIfPreference` to `$true` or setting `$ConfirmPreference` to `Low` in the local scope of the function.</span></span> <span data-ttu-id="50302-265">Quando você chama outra função, as chamadas para `ShouldProcess` usam esses valores.</span><span class="sxs-lookup"><span data-stu-id="50302-265">When you call another function, calls to `ShouldProcess` use those values.</span></span>

<span data-ttu-id="50302-266">Isso funciona corretamente na maioria das vezes.</span><span class="sxs-lookup"><span data-stu-id="50302-266">This actually works correctly most of the time.</span></span> <span data-ttu-id="50302-267">Sempre que você chamar o cmdlet interno ou uma função em seu mesmo escopo, isso funcionará.</span><span class="sxs-lookup"><span data-stu-id="50302-267">Anytime you call built-in cmdlet or a function in your same scope, it works.</span></span> <span data-ttu-id="50302-268">Também funcionará quando você chamar um script ou uma função em um módulo de script do console.</span><span class="sxs-lookup"><span data-stu-id="50302-268">It also works when you call a script or a function in a script module from the console.</span></span>

<span data-ttu-id="50302-269">O local específico em que ele não funciona é quando um script ou um módulo de script chama uma função em outro módulo de script.</span><span class="sxs-lookup"><span data-stu-id="50302-269">The one specific place where it doesn't work is when a script or a script module calls a function in another script module.</span></span> <span data-ttu-id="50302-270">Isso pode não parecer um grande problema, mas a maioria dos módulos criados ou extraídos do PSGallery são módulos de script.</span><span class="sxs-lookup"><span data-stu-id="50302-270">This may not sound like a big problem, but most of the modules you create or pull from the PSGallery are script modules.</span></span>

<span data-ttu-id="50302-271">O principal problema é que os módulos de script não herdam os valores de `$WhatIfPreference` ou `$ConfirmPreference` (e várias outros) quando chamados de funções em outros módulos de script.</span><span class="sxs-lookup"><span data-stu-id="50302-271">The core issue is that script modules do not inherit the values for `$WhatIfPreference` or `$ConfirmPreference` (and several others) when called from functions in other script modules.</span></span>

<span data-ttu-id="50302-272">A melhor maneira de resumir isso em uma regra geral é que funciona corretamente para módulos binários, mas não é confiável para módulos de script.</span><span class="sxs-lookup"><span data-stu-id="50302-272">The best way to summarize this as a general rule is that this works correctly for binary modules and never trust it to work for script modules.</span></span> <span data-ttu-id="50302-273">Caso você não tenha certeza, teste-o ou apenas presuma que ele não funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="50302-273">If you aren't sure, either test it or just assume it doesn't work correctly.</span></span>

<span data-ttu-id="50302-274">Pessoalmente, eu acredito que isso é muito perigoso porque cria cenários em que você adiciona suporte para `-WhatIf` a vários módulos que funcionam corretamente em isolamento, mas não quando chamam um ao outro.</span><span class="sxs-lookup"><span data-stu-id="50302-274">I personally feel this is very dangerous because it creates scenarios where you add `-WhatIf` support to multiple modules that work correctly in isolation, but fail to work correctly when they call each other.</span></span>

<span data-ttu-id="50302-275">Há uma RFC do GitHub trabalhando para corrigir esse problema.</span><span class="sxs-lookup"><span data-stu-id="50302-275">We do have a GitHub RFC working to get this issue fixed.</span></span> <span data-ttu-id="50302-276">Consulte [Propagar as preferências de execução além do escopo do módulo de script][RFC] para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="50302-276">See [Propagate execution preferences beyond script module scope][RFC] for more details.</span></span>

## <a name="in-closing"></a><span data-ttu-id="50302-277">Concluindo</span><span class="sxs-lookup"><span data-stu-id="50302-277">In closing</span></span>

<span data-ttu-id="50302-278">Preciso pesquisar como usar `ShouldProcess` sempre que eu preciso usar.</span><span class="sxs-lookup"><span data-stu-id="50302-278">I have to look up how to use `ShouldProcess` every time I need to use it.</span></span> <span data-ttu-id="50302-279">Demorei muito tempo para conseguir distinguir `ShouldProcess` de `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="50302-279">It took me a long time to distinguish `ShouldProcess` from `ShouldContinue`.</span></span> <span data-ttu-id="50302-280">Eu quase sempre preciso pesquisar os parâmetros para usá-los.</span><span class="sxs-lookup"><span data-stu-id="50302-280">I almost always need to look up what parameters to use.</span></span> <span data-ttu-id="50302-281">Então, não se preocupe se você ainda se sentir confuso de vez em quando.</span><span class="sxs-lookup"><span data-stu-id="50302-281">So don't worry if you still get confused from time to time.</span></span> <span data-ttu-id="50302-282">Este artigo estará aqui sempre que você precisar.</span><span class="sxs-lookup"><span data-stu-id="50302-282">This article will be here when you need it.</span></span> <span data-ttu-id="50302-283">Tenho certeza de que eu mesmo vou consultá-lo com frequência.</span><span class="sxs-lookup"><span data-stu-id="50302-283">I'm sure I will reference it often myself.</span></span>

<span data-ttu-id="50302-284">Se você gostou deste post, compartilhe seus pensamentos comigo no Twitter usando o link abaixo.</span><span class="sxs-lookup"><span data-stu-id="50302-284">If you liked this post, please share your thoughts with me on Twitter using the link below.</span></span> <span data-ttu-id="50302-285">Gosto de saber das pessoas que apreciam meus conteúdos.</span><span class="sxs-lookup"><span data-stu-id="50302-285">I always like hearing from people that get value from my content.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[original version]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[parâmetros comuns]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[common parameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[Tudo o que você queria saber sobre as tabelas de hash]: everything-about-hashtable.md
[everything you wanted to know about hashtables]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
