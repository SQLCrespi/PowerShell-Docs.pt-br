---
title: The Help System (O Sistema de Ajuda)
description: Dominar o sistema de ajuda é o segredo para ser bem-sucedido com o PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 98876cf324b367fd5bb3c3462cb90ea6d7c7d5b9
ms.sourcegitcommit: 0942a6de384f4a1c624e89b1889434a30d22f4d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2020
ms.locfileid: "93143306"
---
# <a name="chapter-2---the-help-system"></a><span data-ttu-id="3a959-103">Capítulo 2 – O sistema de ajuda</span><span class="sxs-lookup"><span data-stu-id="3a959-103">Chapter 2 - The Help System</span></span>

<span data-ttu-id="3a959-104">Dois grupos de profissionais de TI receberam um teste escrito sem acesso a um computador para determinar o nível de habilidade com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-104">Two groups of IT pros were given a written test without access to a computer to determine their skill level with PowerShell.</span></span> <span data-ttu-id="3a959-105">Os iniciantes em PowerShell foram colocados em um grupo e os especialistas, em outro.</span><span class="sxs-lookup"><span data-stu-id="3a959-105">PowerShell beginners were placed in one group and experts in another.</span></span>
<span data-ttu-id="3a959-106">Com base nos resultados do teste, não parece haver muita diferença no nível de habilidade entre os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="3a959-106">Based on the results of the test, there didn't seem to be much difference in the skill level between the two groups.</span></span> <span data-ttu-id="3a959-107">Os dois grupos receberam um segundo teste semelhante ao primeiro.</span><span class="sxs-lookup"><span data-stu-id="3a959-107">Both groups were given a second test similar to the first one.</span></span> <span data-ttu-id="3a959-108">Desta vez, eles receberam acesso a um computador com o PowerShell que não tinha conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="3a959-108">This time they were given access to a computer with PowerShell that didn't have access to the internet.</span></span> <span data-ttu-id="3a959-109">Os resultados do segundo teste mostraram uma grande diferença no nível de habilidade entre os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="3a959-109">The results of the second test showed a huge difference in the skill level between the two groups.</span></span> <span data-ttu-id="3a959-110">Os especialistas nem sempre sabem as respostas, mas sabem como encontrá-las.</span><span class="sxs-lookup"><span data-stu-id="3a959-110">Experts don't always know the answers, but they know how to figure out the answers.</span></span>

<span data-ttu-id="3a959-111">Qual foi a diferença nos resultados do primeiro e do segundo teste entre esses dois grupos?</span><span class="sxs-lookup"><span data-stu-id="3a959-111">What was the difference in the results of the first and second test between these two groups?</span></span>

<span data-ttu-id="3a959-112">As diferenças observadas nesses dois testes foram o que os especialistas não memorizam como usar milhares de comandos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-112">The differences observed in these two tests were because experts don't memorize how to use thousands of commands in PowerShell.</span></span> <span data-ttu-id="3a959-113">Eles aprendem muito bem a usar o sistema de ajuda no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-113">They learn how to use the help system within PowerShell extremely well.</span></span>
<span data-ttu-id="3a959-114">Isso lhes permite encontrar os comandos necessários quando necessário e como usar esses comandos depois de encontrá-los.</span><span class="sxs-lookup"><span data-stu-id="3a959-114">This allows them to find the necessary commands when needed and how to use those commands once they've found them.</span></span>

<span data-ttu-id="3a959-115">Ouvi dizer Jeffrey Snover, o inventor do PowerShell, contou uma história semelhante várias vezes.</span><span class="sxs-lookup"><span data-stu-id="3a959-115">I've heard Jeffrey Snover, the inventor of PowerShell, tell a similar story a number of times.</span></span>

<span data-ttu-id="3a959-116">Dominar o sistema de ajuda é o segredo para ser bem-sucedido com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-116">Mastering the help system is the key to being successful with PowerShell.</span></span>

## <a name="discoverability"></a><span data-ttu-id="3a959-117">Detectabilidade</span><span class="sxs-lookup"><span data-stu-id="3a959-117">Discoverability</span></span>

<span data-ttu-id="3a959-118">Os comandos compilados no PowerShell são chamados de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3a959-118">Compiled commands in PowerShell are called cmdlets.</span></span> <span data-ttu-id="3a959-119">O cmdlet é pronunciado "command-let" (não CMD-Let).</span><span class="sxs-lookup"><span data-stu-id="3a959-119">Cmdlet is pronounced "command-let" (not CMD-let).</span></span> <span data-ttu-id="3a959-120">Os nomes de cmdlets têm a forma de comandos "verbo-substantivo" no singular para torná-los facilmente detectáveis.</span><span class="sxs-lookup"><span data-stu-id="3a959-120">Cmdlets names have the form of singular "Verb-Noun" commands to make them easily discoverable.</span></span> <span data-ttu-id="3a959-121">Por exemplo, o cmdlet para determinar quais processos estão sendo executados é `Get-Process` e o cmdlet para recuperar uma lista de serviços e seus status é `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="3a959-121">For example, the cmdlet for determining what processes are running is `Get-Process` and the cmdlet for retrieving a list of services and their statuses is `Get-Service`.</span></span> <span data-ttu-id="3a959-122">Há outros tipos de comandos no PowerShell, como aliases e funções, que serão abordados posteriormente neste livro.</span><span class="sxs-lookup"><span data-stu-id="3a959-122">There are other types of commands in PowerShell such as aliases and functions that will be covered later in this book.</span></span> <span data-ttu-id="3a959-123">O termo comando do PowerShell é um termo genérico que geralmente é usado para fazer referência a qualquer tipo de comando no PowerShell, independentemente de ser ou não um cmdlet, uma função ou um alias.</span><span class="sxs-lookup"><span data-stu-id="3a959-123">The term PowerShell command is a generic term that's often used to refer to any type of command in PowerShell, regardless of whether or not it's a cmdlet, function, or alias.</span></span>

## <a name="the-three-core-cmdlets-in-powershell"></a><span data-ttu-id="3a959-124">Os três cmdlets principais no PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a959-124">The Three Core Cmdlets in PowerShell</span></span>

- `Get-Command`
- `Get-Help`
- <span data-ttu-id="3a959-125">`Get-Member` (abordado no capítulo 3)</span><span class="sxs-lookup"><span data-stu-id="3a959-125">`Get-Member` (covered in chapter 3)</span></span>

<span data-ttu-id="3a959-126">Uma pergunta que costumam me fazer é como você descobrirá quais são os comandos no PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3a959-126">One question I'm often asked is how do you figure out what the commands are in PowerShell?</span></span> <span data-ttu-id="3a959-127">Tanto `Get-Command` quanto `Get-Help` podem ser usados para determinar os comandos.</span><span class="sxs-lookup"><span data-stu-id="3a959-127">Both `Get-Command` and `Get-Help` can be used to determine the commands.</span></span>

## <a name="get-help"></a><span data-ttu-id="3a959-128">Get-Help</span><span class="sxs-lookup"><span data-stu-id="3a959-128">Get-Help</span></span>

<span data-ttu-id="3a959-129">`Get-Help` é um comando multipropósito.</span><span class="sxs-lookup"><span data-stu-id="3a959-129">`Get-Help` is a multipurpose command.</span></span> <span data-ttu-id="3a959-130">`Get-Help` ajuda você a aprender a usar comandos quando encontrá-los.</span><span class="sxs-lookup"><span data-stu-id="3a959-130">`Get-Help` helps you learn how to use commands once you find them.</span></span> <span data-ttu-id="3a959-131">`Get-Help` também pode ser usado para ajudar a localizar comandos, mas de um modo diferente e mais indireto em comparação com `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="3a959-131">`Get-Help` can also be used to help locate commands, but in a different and more indirect way when compared to `Get-Command`.</span></span>

<span data-ttu-id="3a959-132">Quando `Get-Help` é usado para localizar comandos, ele primeiro pesquisa correspondências curinga de nomes de comando com base na entrada fornecida.</span><span class="sxs-lookup"><span data-stu-id="3a959-132">When `Get-Help` is used to locate commands, it first searches for wildcard matches of command names based on the provided input.</span></span> <span data-ttu-id="3a959-133">Se não encontrar uma correspondência, ele pesquisará os tópicos da ajuda em si e, se nenhuma correspondência for encontrada, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="3a959-133">If it doesn't find a match, it searches through the help topics themselves, and if no match is found an error is returned.</span></span> <span data-ttu-id="3a959-134">Ao contrário da crença popular, `Get-Help` pode ser usado para encontrar comandos que não têm tópicos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-134">Contrary to popular belief, `Get-Help` can be used to find commands that don't have help topics.</span></span>

<span data-ttu-id="3a959-135">A primeira coisa que você precisa saber sobre o sistema de ajuda no PowerShell é como usar o cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-135">The first thing you need to know about the help system in PowerShell is how to use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="3a959-136">O comando a seguir é usado para exibir o tópico da ajuda para `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-136">The following command is used to display the help topic for `Get-Help`.</span></span>

```powershell
Get-Help -Name Get-Help
```

```Output
Do you want to run Update-Help?
The Update-Help cmdlet downloads the most current Help files for Windows PowerShell
modules, and installs them on your computer. For more information about the Update-Help
cmdlet, see http://go.microsoft.com/fwlink/?LinkId=210614.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="3a959-137">Do PowerShell versão 3 em diante, a ajuda do PowerShell não é fornecida com o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3a959-137">Beginning with PowerShell version 3, PowerShell help doesn't ship with the operating system.</span></span> <span data-ttu-id="3a959-138">Na primeira vez em que `Get-Help` for executado para um comando, a mensagem anterior será exibida.</span><span class="sxs-lookup"><span data-stu-id="3a959-138">The first time `Get-Help` is run for a command, the previous message is displayed.</span></span> <span data-ttu-id="3a959-139">Se a função `help` ou o alias de `man` for usado em vez do cmdlet `Get-Help`, você não receberá esse prompt.</span><span class="sxs-lookup"><span data-stu-id="3a959-139">If the `help` function or `man` alias is used instead of the `Get-Help` cmdlet, you don't receive this prompt.</span></span>

<span data-ttu-id="3a959-140">Responder Sim pressionando <kbd>Y</kbd> executa o cmdlet `Update-Help`, que requer acesso à Internet por padrão.</span><span class="sxs-lookup"><span data-stu-id="3a959-140">Answering yes by pressing <kbd>Y</kbd> runs the `Update-Help` cmdlet, which requires internet access by default.</span></span> <span data-ttu-id="3a959-141">`Y` pode ser especificado em letras maiúsculas ou minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3a959-141">`Y` can be specified in either upper or lower case.</span></span>

<span data-ttu-id="3a959-142">Depois que a ajuda for baixada e a atualização for concluída, o tópico da ajuda será retornado para o comando especificado:</span><span class="sxs-lookup"><span data-stu-id="3a959-142">Once the help is downloaded and the update is complete, the help topic is returned for the specified command:</span></span>

```powershell
Get-Help -Name Get-Help
```

<span data-ttu-id="3a959-143">Reserve um tempo para executar esse exemplo em seu computador, examinar a saída e anotar como as informações são agrupadas:</span><span class="sxs-lookup"><span data-stu-id="3a959-143">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="3a959-144">NAME</span><span class="sxs-lookup"><span data-stu-id="3a959-144">NAME</span></span>
- <span data-ttu-id="3a959-145">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3a959-145">SYNOPSIS</span></span>
- <span data-ttu-id="3a959-146">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a959-146">SYNTAX</span></span>
- <span data-ttu-id="3a959-147">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a959-147">DESCRIPTION</span></span>
- <span data-ttu-id="3a959-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3a959-148">RELATED LINKS</span></span>
- <span data-ttu-id="3a959-149">COMENTÁRIOS</span><span class="sxs-lookup"><span data-stu-id="3a959-149">REMARKS</span></span>

<span data-ttu-id="3a959-150">Como você pode ver, os tópicos da ajuda podem conter uma enorme quantidade de informações e isso não é nem o tópico inteiro da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-150">As you can see, help topics can contain an enormous amount of information and this isn't even the entire help topic.</span></span>

<span data-ttu-id="3a959-151">Embora não seja específico do PowerShell, um parâmetro é um modo de fornecer entrada para um comando.</span><span class="sxs-lookup"><span data-stu-id="3a959-151">While not specific to PowerShell, a parameter is a way to provide input to a command.</span></span> <span data-ttu-id="3a959-152">`Get-Help` tem muitos parâmetros que podem ser especificados para retornar todo o tópico da ajuda ou um subconjunto dele.</span><span class="sxs-lookup"><span data-stu-id="3a959-152">`Get-Help` has many parameters that can be specified in order to return the entire help topic or a subset of it.</span></span>

<span data-ttu-id="3a959-153">A seção de sintaxe do tópico da ajuda mostrada no conjunto de resultados anterior lista todos os parâmetros para `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-153">The syntax section of the help topic shown in the previous set of results lists all of the parameters for `Get-Help`.</span></span> <span data-ttu-id="3a959-154">À primeira vista, parece que os mesmos parâmetros estão listados seis vezes diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a959-154">At first glance, it appears the same parameters are listed six different times.</span></span> <span data-ttu-id="3a959-155">Cada um desses blocos diferentes na seção de sintaxe é um conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3a959-155">Each of those different blocks in the syntax section is a parameter set.</span></span> <span data-ttu-id="3a959-156">Isso significa que o cmdlet `Get-Help` tem seis conjuntos de parâmetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a959-156">This means the `Get-Help` cmdlet has six different parameter sets.</span></span> <span data-ttu-id="3a959-157">Se você examinar mais de perto, verá que pelo menos um parâmetro é diferente em cada um dos conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3a959-157">If you take a closer look, you'll notice that at least one parameter is different in each of the parameter sets.</span></span>

<span data-ttu-id="3a959-158">Os conjuntos de parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="3a959-158">Parameter sets are mutually exclusive.</span></span> <span data-ttu-id="3a959-159">Quando um parâmetro exclusivo que só existe em um dos conjuntos de parâmetros é usado, somente os parâmetros contidos nesse conjunto de parâmetros podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="3a959-159">Once a unique parameter that only exists in one of the parameter sets is used, only parameters contained within that parameter set can be used.</span></span> <span data-ttu-id="3a959-160">Por exemplo, os parâmetros **Full** e **Detailed** não podiam ser especificados ao mesmo tempo porque estavam em conjuntos de parâmetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a959-160">For example, both the **Full** and **Detailed** parameters couldn't be specified at the same time because they are in different parameter sets.</span></span>

<span data-ttu-id="3a959-161">Cada um dos seguintes parâmetros está em conjuntos de parâmetros diferentes:</span><span class="sxs-lookup"><span data-stu-id="3a959-161">Each of the following parameters are in different parameter sets:</span></span>

- <span data-ttu-id="3a959-162">Completo</span><span class="sxs-lookup"><span data-stu-id="3a959-162">Full</span></span>
- <span data-ttu-id="3a959-163">Detalhado</span><span class="sxs-lookup"><span data-stu-id="3a959-163">Detailed</span></span>
- <span data-ttu-id="3a959-164">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3a959-164">Examples</span></span>
- <span data-ttu-id="3a959-165">Online</span><span class="sxs-lookup"><span data-stu-id="3a959-165">Online</span></span>
- <span data-ttu-id="3a959-166">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3a959-166">Parameter</span></span>
- <span data-ttu-id="3a959-167">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="3a959-167">ShowWindow</span></span>

<span data-ttu-id="3a959-168">Toda a sintaxe criptografada, como colchetes quadrados e angulares na seção de sintaxe, significa algo, mas isso será abordado no apêndice A deste livro.</span><span class="sxs-lookup"><span data-stu-id="3a959-168">All of the cryptic syntax such as square and angle brackets in the syntax section means something but will be covered in Appendix A of this book.</span></span> <span data-ttu-id="3a959-169">Embora seja importante, alguém que é novo no PowerShell e não o utiliza todos os dias costuma ter dificuldade para se lembrar de qual é a sintaxe criptografada.</span><span class="sxs-lookup"><span data-stu-id="3a959-169">While important, learning the cryptic syntax is often difficult to retain for someone who is new to PowerShell and may not use it everyday.</span></span>

<span data-ttu-id="3a959-170">Para obter mais informações para entender melhor a sintaxe criptografada, confira o [Apêndice A][].</span><span class="sxs-lookup"><span data-stu-id="3a959-170">For more information to better understand the cryptic syntax, see [Appendix A][].</span></span>

<span data-ttu-id="3a959-171">Para iniciantes, há um modo mais fácil de descobrir as mesmas informações, exceto em linguagem simples.</span><span class="sxs-lookup"><span data-stu-id="3a959-171">For beginners, there's an easier way to figure out the same information except in plain language.</span></span>

<span data-ttu-id="3a959-172">Quando o parâmetro **Completo** de `Get-Help` é especificado, todo o tópico da ajuda é retornado.</span><span class="sxs-lookup"><span data-stu-id="3a959-172">When the **Full** parameter of `Get-Help` is specified, the entire help topic is returned.</span></span>

```powershell
Get-Help -Name Get-Help -Full
```

<span data-ttu-id="3a959-173">Reserve um tempo para executar esse exemplo em seu computador, examinar a saída e anotar como as informações são agrupadas:</span><span class="sxs-lookup"><span data-stu-id="3a959-173">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="3a959-174">NAME</span><span class="sxs-lookup"><span data-stu-id="3a959-174">NAME</span></span>
- <span data-ttu-id="3a959-175">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3a959-175">SYNOPSIS</span></span>
- <span data-ttu-id="3a959-176">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a959-176">SYNTAX</span></span>
- <span data-ttu-id="3a959-177">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a959-177">DESCRIPTION</span></span>
- <span data-ttu-id="3a959-178">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a959-178">PARAMETERS</span></span>
- <span data-ttu-id="3a959-179">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3a959-179">INPUTS</span></span>
- <span data-ttu-id="3a959-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3a959-180">OUTPUTS</span></span>
- <span data-ttu-id="3a959-181">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3a959-181">NOTES</span></span>
- <span data-ttu-id="3a959-182">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3a959-182">EXAMPLES</span></span>
- <span data-ttu-id="3a959-183">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3a959-183">RELATED LINKS</span></span>

<span data-ttu-id="3a959-184">Observe que usar o parâmetro **Completo** retornou várias seções adicionais, uma das quais é a seção de parâmetros que fornece mais informações do que a seção de sintaxe criptografada.</span><span class="sxs-lookup"><span data-stu-id="3a959-184">Notice that using the **Full** parameter returned several additional sections, one of which is the PARAMETERS section that provides more information than the cryptic SYNTAX section.</span></span>

<span data-ttu-id="3a959-185">O parâmetro **Completo** é um parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="3a959-185">The **Full** parameter is a switch parameter.</span></span> <span data-ttu-id="3a959-186">Um parâmetro que não exige um valor é chamado de parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="3a959-186">A parameter that doesn't require a value is called a switch parameter.</span></span> <span data-ttu-id="3a959-187">Quando um parâmetro de opção é especificado, o valor é true; quando ele não é especificado, o valor é false.</span><span class="sxs-lookup"><span data-stu-id="3a959-187">When a switch parameter is specified, its value is true and when it's not, its value is false.</span></span>

<span data-ttu-id="3a959-188">Se você trabalhou com este capítulo no console do PowerShell, observou que o comando anterior exibe o tópico de ajuda completo para `Get-Help` mostrado por na tela sem lhe dar a oportunidade de lê-lo.</span><span class="sxs-lookup"><span data-stu-id="3a959-188">If you've been working through this chapter in the PowerShell console, you noticed that the previous command to display the full help topic for `Get-Help` flew by on the screen without giving you a chance to read it.</span></span> <span data-ttu-id="3a959-189">Há um modo melhor.</span><span class="sxs-lookup"><span data-stu-id="3a959-189">There's a better way.</span></span>

<span data-ttu-id="3a959-190">`Help` é uma função que canaliza `Get-Help` para uma função chamada `more`, que é um wrapper para o arquivo executável `more.com` no Windows.</span><span class="sxs-lookup"><span data-stu-id="3a959-190">`Help` is a function that pipes `Get-Help` to a function named `more`, which is a wrapper for the `more.com` executable file in Windows.</span></span> <span data-ttu-id="3a959-191">No console do PowerShell, `help` fornece uma página de ajuda de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3a959-191">In the PowerShell console, `help` provides one page of help at a time.</span></span> <span data-ttu-id="3a959-192">No ISE, funciona da mesma maneira que `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-192">In the ISE, it works the same way as `Get-Help`.</span></span> <span data-ttu-id="3a959-193">Minha recomendação é usar a função `help`, em vez do cmdlet `Get-Help`, uma vez que fornece uma experiência melhor e é menor para digitar.</span><span class="sxs-lookup"><span data-stu-id="3a959-193">My recommendation is to use the `help` function instead of the `Get-Help` cmdlet since it provides a better experience and it's less to type.</span></span>

<span data-ttu-id="3a959-194">No entanto, digitar menos nem sempre é algo bom.</span><span class="sxs-lookup"><span data-stu-id="3a959-194">Less typing isn't always a good thing, however.</span></span> <span data-ttu-id="3a959-195">Se você pretende salvar seus comandos como um script ou compartilhá-los com outra pessoa, use nomes de cmdlet e parâmetro completos.</span><span class="sxs-lookup"><span data-stu-id="3a959-195">If you're going to save your commands as a script or share them with someone else, be sure to use full cmdlet and parameter names.</span></span> <span data-ttu-id="3a959-196">Os nomes completos são autodocumentados, o que os torna mais fáceis de entender.</span><span class="sxs-lookup"><span data-stu-id="3a959-196">The full names are self-documenting, which makes them easier to understand.</span></span> <span data-ttu-id="3a959-197">Pense na próxima pessoa que precisará ler e entender seus comandos.</span><span class="sxs-lookup"><span data-stu-id="3a959-197">Think about the next person that has to read and understand your commands.</span></span> <span data-ttu-id="3a959-198">Ela pode ser você.</span><span class="sxs-lookup"><span data-stu-id="3a959-198">It could be you.</span></span> <span data-ttu-id="3a959-199">Seus colegas de trabalho e você mesmo no futuro agradecerão.</span><span class="sxs-lookup"><span data-stu-id="3a959-199">Your coworkers and future self will thank you.</span></span>

<span data-ttu-id="3a959-200">Tente executar os seguintes comandos no console do PowerShell em seu computador do ambiente de laboratório do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3a959-200">Try running the following commands in the PowerShell console on your Windows 10 lab environment computer.</span></span>

```powershell
Get-Help -Name Get-Help -Full
help -Name Get-Help -Full
help Get-Help -Full
```

<span data-ttu-id="3a959-201">Você observou alguma diferença na saída dos comandos listados anteriormente quando os executava em seu computador do ambiente de laboratório do Windows 10?</span><span class="sxs-lookup"><span data-stu-id="3a959-201">Did you notice any differences in the output from the previously listed commands when you ran them on your Windows 10 lab environment computer?</span></span>

<span data-ttu-id="3a959-202">Não há diferenças que não as duas últimas opções retornarem os resultados uma página por vez.</span><span class="sxs-lookup"><span data-stu-id="3a959-202">There aren't any differences other than the last two options return the results one page at a time.</span></span>
<span data-ttu-id="3a959-203">A <kbd>barra de espaços</kbd> é usada para exibir a próxima página de conteúdo ao usar a função `Help` e <kbd>Ctrl</kbd>+<kbd>C</kbd> cancela os comandos que estão em execução no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-203">The <kbd>spacebar</kbd> is used to display the next page of content when using the `Help` function and <kbd>Ctrl</kbd>+<kbd>C</kbd> cancels commands that are running in the PowerShell console.</span></span>

<span data-ttu-id="3a959-204">O primeiro exemplo usa o cmdlet `Get-Help`; o segundo usa a função `Help`; e o terceiro omite o parâmetro **Name** ao usar a função `Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-204">The first example uses the `Get-Help` cmdlet, the second uses the `Help` function, and the third omits the **Name** parameter when using the `Help` function.</span></span> <span data-ttu-id="3a959-205">**Name** é um parâmetro posicional e está sendo usado posicionalmente neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="3a959-205">**Name** is a positional parameter and it's being used positionally in that example.</span></span> <span data-ttu-id="3a959-206">Isso significa que o valor pode ser especificado sem especificar o nome do parâmetro, desde que o próprio valor seja especificado na posição correta.</span><span class="sxs-lookup"><span data-stu-id="3a959-206">This means the value can be specified without specifying the parameter name, as long as the value itself is specified in the correct position.</span></span> <span data-ttu-id="3a959-207">Como eu sabia em qual posição especificar o valor?</span><span class="sxs-lookup"><span data-stu-id="3a959-207">How did I know what position to specify the value in?</span></span> <span data-ttu-id="3a959-208">Lendo a ajuda conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a959-208">By reading the help as shown in the following example.</span></span>

```powershell
help Get-Help -Parameter Name
```

```Output
-Name <String>
    Gets help about the specified command or concept. Enter the name of a cmdlet, function,
    provider, script, or workflow, such as Get-Member, a conceptual article name, such as
    about_Objects, or an alias, such as ls. Wildcard characters are permitted in cmdlet and
    provider names, but you can't use wildcard characters to find the names of function help and
    script help articles.

    To get help for a script that isn't located in a path that's listed in the $env:Path
    environment variable, type the script's path and file name.

    If you enter the exact name of a help article, Get-Help displays the article contents.

    If you enter a word or word pattern that appears in several help article titles, Get-Help
    displays a list of the matching titles.

    If you enter a word that doesn't match any help article titles, Get-Help displays a list of
    articles that include that word in their contents.

    The names of conceptual articles, such as about_Objects, must be entered in English, even in
    non-English versions of PowerShell.

    Required?                    false
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  true
```

<span data-ttu-id="3a959-209">Observe que, no exemplo anterior, o parâmetro **Parameter** foi usado com a função Ajuda para retornar apenas informações do tópico da ajuda para o parâmetro **Name**.</span><span class="sxs-lookup"><span data-stu-id="3a959-209">Notice that in the previous example, the **Parameter** parameter was used with the Help function to only return information from the help topic for the **Name** parameter.</span></span> <span data-ttu-id="3a959-210">Isso é muito mais conciso do que tentar examinar manualmente o que às vezes parece um tópico de ajuda de centenas de páginas.</span><span class="sxs-lookup"><span data-stu-id="3a959-210">This is much more concise than trying to manually sift through what sometimes seems like a hundred page help topic.</span></span>

<span data-ttu-id="3a959-211">Com base nesses resultados, você pode ver que o parâmetro **Name** é posicional e deve ser especificado na posição zero (a primeira posição) quando usado de acordo com a posição.</span><span class="sxs-lookup"><span data-stu-id="3a959-211">Based on those results, you can see that the **Name** parameter is positional and must be specified in position zero (the first position) when used positionally.</span></span> <span data-ttu-id="3a959-212">A ordem em que os parâmetros são especificados não importa se o nome do parâmetro está especificado.</span><span class="sxs-lookup"><span data-stu-id="3a959-212">The order that parameters are specified in doesn't matter if the parameter name is specified.</span></span>

<span data-ttu-id="3a959-213">Outra informação importante é que o parâmetro **Name** espera que o tipo de dados de seu valor seja uma cadeia de caracteres única, que é denotada por `<String>`.</span><span class="sxs-lookup"><span data-stu-id="3a959-213">One other important piece of information is that the **Name** parameter expects the datatype for its value to be a single string, which is denoted by `<String>`.</span></span> <span data-ttu-id="3a959-214">Se ele aceitar várias cadeias de caracteres, o tipo de dados será listado como `<String[]>`.</span><span class="sxs-lookup"><span data-stu-id="3a959-214">If it accepted multiple strings, the datatype would be listed as `<String[]>`.</span></span>

<span data-ttu-id="3a959-215">Às vezes, você simplesmente não quer exibir o tópico inteiro da ajuda para um comando.</span><span class="sxs-lookup"><span data-stu-id="3a959-215">Sometimes you simply don't want to display the entire help topic for a command.</span></span> <span data-ttu-id="3a959-216">Há vários outros parâmetros, além de **Full** , que podem ser especificados com `Get-Help` ou `Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-216">There are a number of other parameters besides **Full** that can be specified with `Get-Help` or `Help`.</span></span> <span data-ttu-id="3a959-217">Tente executar os seguintes comandos no computador do ambiente de laboratório do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="3a959-217">Try running the following commands on your Windows 10 lab environment computer:</span></span>

```powershell
Get-Help -Name Get-Command -Full
Get-Help -Name Get-Command -Detailed
Get-Help -Name Get-Command -Examples
Get-Help -Name Get-Command -Online
Get-Help -Name Get-Command -Parameter Noun
Get-Help -Name Get-Command -ShowWindow
```

<span data-ttu-id="3a959-218">Normalmente, use `help <command name>` com o parâmetro **Full** ou **Online**.</span><span class="sxs-lookup"><span data-stu-id="3a959-218">I typically use `help <command name>` with the **Full** or **Online** parameter.</span></span> <span data-ttu-id="3a959-219">Se eu estiver interessado apenas nos exemplos, usarei o parâmetro **Examples** e, se estiver interessado apenas em um parâmetro específico, usarei o parâmetro **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="3a959-219">If I'm only interested in the examples, I'll use the **Examples** parameter and if I'm only interested in a specific parameter, I'll use the **Parameter** parameter.</span></span> <span data-ttu-id="3a959-220">O parâmetro **ShowWindow** abre o tópico da ajuda em uma janela pesquisável separada que poderá ser colocada em um monitor diferente se você tiver vários monitores.</span><span class="sxs-lookup"><span data-stu-id="3a959-220">The **ShowWindow** parameter opens the help topic in a separate searchable window that can be placed on a different monitor if you have multiple monitors.</span></span> <span data-ttu-id="3a959-221">Eu evitei o parâmetro **ShowWindow** porque há um bug conhecido em que ele não exibe todo o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-221">I've avoided the **ShowWindow** parameter because there's a known bug where it doesn't display the entire help topic.</span></span>

<span data-ttu-id="3a959-222">Se você quiser obter ajuda em uma janela separada, minha recomendação é usar o parâmetro **Online** ou usar o parâmetro **Full** e canalizar os resultados para `Out-GridView`, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a959-222">If you want help in a separate window, my recommendation is to either use the **Online** parameter or use the **Full** parameter and pipe the results to `Out-GridView`, as shown in the following example.</span></span>

```powershell
help Get-Command -Full | Out-GridView
```

<span data-ttu-id="3a959-223">Tanto o cmdlet `Out-GridView` quanto o parâmetro **ShowWindow** do cmdlet `Get-Help` exigem um sistema operacional com uma GUI (interface gráfica do usuário).</span><span class="sxs-lookup"><span data-stu-id="3a959-223">Both the `Out-GridView` cmdlet and the **ShowWindow** parameter of the `Get-Help` cmdlet require an operating system with a GUI (Graphical User Interface).</span></span> <span data-ttu-id="3a959-224">Eles vão gerar uma mensagem de erro se você tentar usar qualquer um deles no Windows Server instalado usando a opção de instalação de núcleo do servidor (sem GUI).</span><span class="sxs-lookup"><span data-stu-id="3a959-224">They will generate an error message if you attempt to use either of them on Windows Server that's been installed using the server core (no-GUI) installation option.</span></span>

<span data-ttu-id="3a959-225">Para usar `Get-Help` para localizar comandos, use o caractere curinga asterisco (`*`) com o parâmetro **Name**.</span><span class="sxs-lookup"><span data-stu-id="3a959-225">To use `Get-Help` to find commands, use the asterisk (`*`) wildcard character with the **Name** parameter.</span></span> <span data-ttu-id="3a959-226">Especifique um termo no qual você está procurando comandos como o valor para o parâmetro **Name** , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a959-226">Specify a term that you're searching for commands on as the value for the **Name** parameter as shown in the following example.</span></span>

```powershell
help *process*
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an intera...
Get-PSHostProcessInfo             Cmdlet    Microsoft.PowerShell.Core
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-AppvVirtualProcess            Function  AppvClient                ...
Start-AppvVirtualProcess          Function  AppvClient                ...
```

<span data-ttu-id="3a959-227">No exemplo anterior, os caracteres curinga `*` não são necessários e omiti-los produz o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="3a959-227">In the previous example, the `*` wildcard characters are not required and omitting them produces the same result.</span></span> <span data-ttu-id="3a959-228">`Get-Help` adiciona automaticamente os caracteres curinga em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3a959-228">`Get-Help` automatically adds the wildcard characters behind the scenes.</span></span>

```powershell
help process
```

<span data-ttu-id="3a959-229">O comando anterior produz os mesmos resultados que especificar o caractere curinga `*` em cada fim do processo.</span><span class="sxs-lookup"><span data-stu-id="3a959-229">The previous command produces the same results as specifying the `*` wildcard character on each end of process.</span></span>

<span data-ttu-id="3a959-230">Prefiro adicioná-los, pois essa é a opção que sempre funciona de modo consistente.</span><span class="sxs-lookup"><span data-stu-id="3a959-230">I prefer to add them since that's the option that always works consistently.</span></span> <span data-ttu-id="3a959-231">Caso contrário, eles serão necessários em determinados cenários e não em outros.</span><span class="sxs-lookup"><span data-stu-id="3a959-231">Otherwise, they are required in certain scenarios and not others.</span></span> <span data-ttu-id="3a959-232">Assim que você adicionar um caractere curinga no meio do valor, ele não será mais adicionado automaticamente em segundo plano ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="3a959-232">As soon as you add a wildcard character in the middle of the value, they're no longer automatically added behind the scenes to the value you specified.</span></span>

```powershell
help pr*cess
```

<span data-ttu-id="3a959-233">Nenhum resultado é retornado por esse comando, a menos que o caractere curinga `*` seja adicionado ao início, ao fim ou ao início e ao fim de `pr*cess`.</span><span class="sxs-lookup"><span data-stu-id="3a959-233">No results are returned by that command unless the `*` wildcard character is added to the beginning, end, or both the beginning and end of `pr*cess`.</span></span>

<span data-ttu-id="3a959-234">Se o valor especificado começar com um traço, um erro será gerado porque o PowerShell o interpretará como um nome de parâmetro e não existirá esse nome de parâmetro para o cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3a959-234">If the value you specified begins with a dash, then an error is generated because PowerShell interprets it as a parameter name and no such parameter name exists for the `Get-Help` cmdlet.</span></span>

```powershell
help -process
```

<span data-ttu-id="3a959-235">Se você está tentando procurar comandos que terminam com `-process`, basta adicionar o caractere curinga `*` ao início do valor.</span><span class="sxs-lookup"><span data-stu-id="3a959-235">If what you're attempting to look for are commands that end with `-process`, you only need to add the `*` wildcard character to the beginning of the value.</span></span>

```powershell
help *-process
```

<span data-ttu-id="3a959-236">Ao procurar comandos do PowerShell com `Get-Help`, você deve ser um pouco mais vago, em vez de específico demais com o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="3a959-236">When searching for PowerShell commands with `Get-Help`, you want to be a little more vague instead of being too specific with what you're searching for.</span></span>

<span data-ttu-id="3a959-237">Pesquisar `process` anteriormente encontrou apenas comandos que continham `process` no nome do comando e retornavam apenas esses resultados.</span><span class="sxs-lookup"><span data-stu-id="3a959-237">Searching for `process` earlier found only commands that contained `process` in the name of the command and returned only those results.</span></span> <span data-ttu-id="3a959-238">Quando `Get-Help` é usado para pesquisar `processes`, ele não localiza nenhuma correspondência para nomes de comando, portanto, executa uma pesquisa de cada tópico da ajuda no PowerShell no seu sistema e retorna as correspondências que encontra.</span><span class="sxs-lookup"><span data-stu-id="3a959-238">When `Get-Help` is used to search for `processes`, it doesn't find any matches for command names, so it performs a search of every help topic in PowerShell on your system and returns any matches it finds.</span></span> <span data-ttu-id="3a959-239">Isso faz com que ele retorne um número muito grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="3a959-239">This causes it to return an enormous number of results.</span></span>

```powershell
Get-Help processes
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Disconnect-PSSession              Cmdlet    Microsoft.PowerShell.Core Disconnects from...
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an oper...
Get-PSSessionConfiguration        Cmdlet    Microsoft.PowerShell.Core Gets the registe...
New-PSTransportOption             Cmdlet    Microsoft.PowerShell.Core Creates an objec...
Out-Host                          Cmdlet    Microsoft.PowerShell.Core Sends output to ...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects ...
Clear-Variable                    Cmdlet    Microsoft.PowerShell.U... Deletes the valu...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two set...
Convert-String                    Cmdlet    Microsoft.PowerShell.U... Formats a string...
ConvertFrom-Csv                   Cmdlet    Microsoft.PowerShell.U... Converts object ...
ConvertTo-Html                    Cmdlet    Microsoft.PowerShell.U... Converts Microso...
ConvertTo-Xml                     Cmdlet    Microsoft.PowerShell.U... Creates an XML-b...
Debug-Runspace                    Cmdlet    Microsoft.PowerShell.U... Starts an intera...
Export-Csv                        Cmdlet    Microsoft.PowerShell.U... Converts objects...
Export-FormatData                 Cmdlet    Microsoft.PowerShell.U... Saves formatting...
Format-List                       Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Format-Table                      Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Get-Random                        Cmdlet    Microsoft.PowerShell.U... Gets a random nu...
Get-Unique                        Cmdlet    Microsoft.PowerShell.U... Returns unique i...
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects t...
Import-Clixml                     Cmdlet    Microsoft.PowerShell.U... Imports a CLIXML...
Import-Csv                        Cmdlet    Microsoft.PowerShell.U... Creates table-li...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the n...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Out-GridView                      Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects ...
Set-Variable                      Cmdlet    Microsoft.PowerShell.U... Sets the value o...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by...
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command ou...
Trace-Command                     Cmdlet    Microsoft.PowerShell.U... Configures and s...
Write-Output                      Cmdlet    Microsoft.PowerShell.U... Sends the specif...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances o...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-Counter                       Cmdlet    Microsoft.PowerShell.D... Gets performance...
Invoke-WSManAction                Cmdlet    Microsoft.WSMan.Manage... Invokes an actio...
Remove-WSManInstance              Cmdlet    Microsoft.WSMan.Manage... Deletes a manage...
Get-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Displays managem...
New-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Creates a new in...
Set-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Modifies the man...
about_Arithmetic_Operators        HelpFile                            Describes the op...
about_Arrays                      HelpFile                            Describes arrays...
about_Debuggers                   HelpFile                            Describes the Wi...
about_Execution_Policies          HelpFile                            Describes the Wi...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Foreach                     HelpFile                            Describes a lang...
about_Functions                   HelpFile                            Describes how to...
about_Language_Keywords           HelpFile                            Describes the ke...
about_Methods                     HelpFile                            Describes how to...
about_Objects                     HelpFile                            Provides essenti...
about_Parallel                    HelpFile                            Describes the Pa...
about_Pipelines                   HelpFile                            Combining comman...
about_Preference_Variables        HelpFile                            Variables that c...
about_Remote                      HelpFile                            Describes how to...
about_Remote_Output               HelpFile                            Describes how to...
about_Sequence                    HelpFile                            Describes the Se...
about_Session_Configuration_Files HelpFile                            Describes sessio...
about_Variables                   HelpFile                            Describes how va...
about_Windows_PowerShell_5.0      HelpFile                            Describes new fe...
about_WQL                         HelpFile                            Describes WMI Qu...
about_WS-Management_Cmdlets       HelpFile                            Provides an over...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Parallel                    HelpFile                            Describes the Pa...
about_Sequence                    HelpFile                            Describes the Se...
```

<span data-ttu-id="3a959-240">Usar `Help` para pesquisar `process` retornou 10 resultados e usá-lo para pesquisar `processes` retornou 68 resultados.</span><span class="sxs-lookup"><span data-stu-id="3a959-240">Using `Help` to search for `process` returned 10 results and using it to search for `processes` returned 68 results.</span></span> <span data-ttu-id="3a959-241">Se apenas um resultado for encontrado, o tópico da ajuda em si será exibido, em vez de uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a959-241">If only one result is found, the help topic itself will be displayed instead of a list of commands.</span></span>

```powershell
get-help *hotfix*
```

```Output
NAME
    Get-HotFix

SYNOPSIS
    Gets the hotfixes that have been applied to the local and remote computers.


SYNTAX
    Get-HotFix [-ComputerName <String[]>] [-Credential <PSCredential>] [-Description
    <String[]>] [<CommonParameters>]

    Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential
    <PSCredential>] [<CommonParameters>]


DESCRIPTION
    The Get-Hotfix cmdlet gets hotfixes (also called updates) that have been installed
    on either the local computer (or on specified remote computers) by Windows Update,
    Microsoft Update, or Windows Server Update Services; the cmdlet also gets hotfixes
    or updates that have been installed manually by users.


RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821586
    Win32_QuickFixEngineering http://go.microsoft.com/fwlink/?LinkID=145071
    Get-ComputerRestorePoint
    Add-Content

REMARKS
    To see the examples, type: "get-help Get-HotFix -examples".
    For more information, type: "get-help Get-HotFix -detailed".
    For technical information, type: "get-help Get-HotFix -full".
    For online help, type: "get-help Get-HotFix -online"
```

<span data-ttu-id="3a959-242">Agora, para desmistificar a ideia de que `Help` no PowerShell só pode encontrar comandos que tenham tópicos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-242">Now to debunk the myth that `Help` in PowerShell can only find commands that have help topics.</span></span>

```powershell
help *more*
```

```Output
NAME
    more

SYNTAX
    more [[-paths] <string[]>]


ALIASES
    None


REMARKS
    None
```

<span data-ttu-id="3a959-243">Observe, no exemplo anterior, que `more` não tem um tópico de ajuda, mas o sistema `Help` no PowerShell conseguiu encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="3a959-243">Notice in the previous example that `more` doesn't have a help topic, yet the `Help` system in PowerShell was able to find it.</span></span> <span data-ttu-id="3a959-244">Ele encontrou apenas uma correspondência e retornou as informações de sintaxe básicas que você verá quando um comando não tiver um tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-244">It only found one match and returned the basic syntax information that you'll see when a command doesn't have a help topic.</span></span>

<span data-ttu-id="3a959-245">O PowerShell contém vários tópicos de ajuda (Sobre) conceituais.</span><span class="sxs-lookup"><span data-stu-id="3a959-245">PowerShell contains numerous conceptual (About) help topics.</span></span> <span data-ttu-id="3a959-246">O comando a seguir pode ser usado para retornar uma lista de todos os tópicos de ajuda **Sobre** em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="3a959-246">The following command can be used to return a list of all **About** help topics on your system.</span></span>

```powershell
help About_*
```

<span data-ttu-id="3a959-247">Limitar os resultados a um único tópico sobre a ajuda exibe o tópico da ajuda real, em vez de retornar uma lista.</span><span class="sxs-lookup"><span data-stu-id="3a959-247">Limiting the results to one single About help topic displays the actual help topic instead of returning a list.</span></span>

```powershell
help about_Updatable_Help
```

<span data-ttu-id="3a959-248">O sistema de ajuda no PowerShell precisa ser atualizado para que os tópicos de ajuda **Sobre** estejam presentes.</span><span class="sxs-lookup"><span data-stu-id="3a959-248">The help system in PowerShell has to be updated in order for the **About** help topics to be present.</span></span> <span data-ttu-id="3a959-249">Se, por algum motivo, a atualização inicial do sistema de ajuda falhar em seu computador, os arquivos não estarão disponíveis até que o cmdlet `Update-Help` tenha sido executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3a959-249">If for some reason the initial update of the help system failed on your computer, the files will not be available until the `Update-Help` cmdlet has been run successfully.</span></span>

## <a name="get-command"></a><span data-ttu-id="3a959-250">Get-Command</span><span class="sxs-lookup"><span data-stu-id="3a959-250">Get-Command</span></span>

<span data-ttu-id="3a959-251">`Get-Command` é projetado para ajudar você a localizar comandos.</span><span class="sxs-lookup"><span data-stu-id="3a959-251">`Get-Command` is designed to help you locate commands.</span></span> <span data-ttu-id="3a959-252">A execução do `Get-Command` sem parâmetros retorna uma lista de todos os comandos em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="3a959-252">Running `Get-Command` without any parameters returns a list of all the commands on your system.</span></span> <span data-ttu-id="3a959-253">O exemplo a seguir demonstra o uso do cmdlet `Get-Command` para determinar quais comandos existem para trabalhar com processos:</span><span class="sxs-lookup"><span data-stu-id="3a959-253">The following example demonstrates using the `Get-Command` cmdlet to determine what commands exist for working with processes:</span></span>

```powershell
Get-Command -Noun Process
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsof...
Cmdlet          Get-Process                                        3.1.0.0    Microsof...
Cmdlet          Start-Process                                      3.1.0.0    Microsof...
Cmdlet          Stop-Process                                       3.1.0.0    Microsof...
Cmdlet          Wait-Process                                       3.1.0.0    Microsof...
```

<span data-ttu-id="3a959-254">Observe no exemplo anterior em que `Get-Command` foi executado, o parâmetro **Noun** é usado e `Process` é especificado como o valor para o parâmetro **Noun**.</span><span class="sxs-lookup"><span data-stu-id="3a959-254">Notice in the previous example where `Get-Command` was run, the **Noun** parameter is used and `Process` is specified as the value for the **Noun** parameter.</span></span> <span data-ttu-id="3a959-255">E se você não sabia como usar o cmdlet `Get-Command`?</span><span class="sxs-lookup"><span data-stu-id="3a959-255">What if you didn't know how to use the `Get-Command` cmdlet?</span></span> <span data-ttu-id="3a959-256">Você pode usar `Get-Help` para exibir o tópico da ajuda para `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="3a959-256">You could use `Get-Help` to display the help topic for `Get-Command`.</span></span>

<span data-ttu-id="3a959-257">Os parâmetros **Name** , **Noun** e **Verb** aceitam curingas.</span><span class="sxs-lookup"><span data-stu-id="3a959-257">The **Name** , **Noun** , and **Verb** parameters accept wildcards.</span></span> <span data-ttu-id="3a959-258">O exemplo a seguir mostra os curingas que estão sendo usados com o parâmetro **Nome** :</span><span class="sxs-lookup"><span data-stu-id="3a959-258">The following example shows wildcards being used with the **Name** parameter:</span></span>

```Output
Get-Command -Name *service*
```

```powershell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Function        Set-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          New-Service                                        3.1.0.0    Microsof...
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
Application     AgentService.exe                                   10.0.14... C:\Windo...
Application     SensorDataService.exe                              10.0.14... C:\Windo...
Application     services.exe                                       10.0.14... C:\Windo...
Application     services.msc                                       0.0.0.0    C:\Windo...
Application     TieringEngineService.exe                           10.0.14... C:\Windo...
```

<span data-ttu-id="3a959-259">Não sou um fã do uso de curingas com o parâmetro **Name** de `Get-Command`, já que ele também retorna arquivos executáveis que não são comandos nativos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a959-259">I'm not a fan of using wildcards with the **Name** parameter of `Get-Command` since it also returns executable files that are not native PowerShell commands.</span></span>

<span data-ttu-id="3a959-260">Se você pretende usar caracteres curinga com o parâmetro **Name** , recomendo limitar os resultados com o parâmetro **CommandType**.</span><span class="sxs-lookup"><span data-stu-id="3a959-260">If you are going to use wildcard characters with the **Name** parameter, I recommend limiting the results with the **CommandType** parameter.</span></span>

```powershell
Get-Command -Name *service* -CommandType Cmdlet, Function, Alias
```

<span data-ttu-id="3a959-261">Uma opção melhor é usar o parâmetro **Verb** ou **Noun** ou ambos, já que apenas comandos do PowerShell têm verbos e substantivos.</span><span class="sxs-lookup"><span data-stu-id="3a959-261">A better option is to use either the **Verb** or **Noun** parameter or both of them since only PowerShell commands have both verbs and nouns.</span></span>

<span data-ttu-id="3a959-262">Encontrou algo errado com um tópico da ajuda?</span><span class="sxs-lookup"><span data-stu-id="3a959-262">Found something wrong with a help topic?</span></span> <span data-ttu-id="3a959-263">A boa notícia é que os tópicos de ajuda para o PowerShell foram acessados e estão disponíveis no repositório do [PowerShell-Docs][] no GitHub.</span><span class="sxs-lookup"><span data-stu-id="3a959-263">The good news is the help topics for PowerShell have been open-sourced and available in the [PowerShell-Docs][] repository on GitHub.</span></span> <span data-ttu-id="3a959-264">Passe esse benefício adiante não apenas corrigindo as informações incorretas para você mesmo, mas para todas as outras pessoas também.</span><span class="sxs-lookup"><span data-stu-id="3a959-264">Pay it forward by not only fixing the incorrect information for yourself, but everyone else as well.</span></span> <span data-ttu-id="3a959-265">Basta bifurcar o repositório de documentação do PowerShell no GitHub, atualizar o tópico da ajuda e enviar uma solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="3a959-265">Simply fork the PowerShell documentation repository on GitHub, update the help topic, and submit a pull request.</span></span>
<span data-ttu-id="3a959-266">Depois que a solicitação de pull for aceita, a documentação corrigida estará disponível para todos.</span><span class="sxs-lookup"><span data-stu-id="3a959-266">Once the pull request is accepted, the corrected documentation is available for everyone.</span></span>

## <a name="updating-help"></a><span data-ttu-id="3a959-267">Como atualizar a ajuda</span><span class="sxs-lookup"><span data-stu-id="3a959-267">Updating Help</span></span>

<span data-ttu-id="3a959-268">A cópia local dos tópicos da ajuda do PowerShell foi atualizada anteriormente na primeira vez em que a ajuda para um comando foi solicitada.</span><span class="sxs-lookup"><span data-stu-id="3a959-268">The local copy of the PowerShell help topics was previously updated the first-time help on a command was requested.</span></span> <span data-ttu-id="3a959-269">É recomendável atualizar periodicamente o sistema de ajuda, pois pode haver atualizações ao seu conteúdo de tempos em tempos.</span><span class="sxs-lookup"><span data-stu-id="3a959-269">It's recommended to periodically update the help system because there can be updates to the help content from time to time.</span></span> <span data-ttu-id="3a959-270">O cmdlet `Update-Help` é usado para atualizar os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-270">The `Update-Help` cmdlet is used to update the help topics.</span></span>
<span data-ttu-id="3a959-271">Por padrão, ele requer acesso à Internet e que você esteja executando o PowerShell com privilégios elevados como administrador.</span><span class="sxs-lookup"><span data-stu-id="3a959-271">It requires internet access by default and for you to be running PowerShell elevated as an administrator.</span></span>

```powershell
Update-Help
```

```Output
Update-Help : Failed to update Help for the module(s) 'BitsTransfer' with UI culture(s)
{en-US} : The value of the HelpInfoUri key in the module manifest must resolve to a
container or root URL on a website where the help files are stored. The HelpInfoUri
'https://technet.microsoft.com/en-us/library/dd819413.aspx' does not resolve to a
container.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : InvalidOperation: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : InvalidHelpInfoUri,Microsoft.PowerShell.Commands.UpdateHel
   pCommand

Update-Help : Failed to update Help for the module(s) 'NetworkControllerDiagnostics,
StorageReplica' with UI culture(s) {en-US} : Unable to retrieve the HelpInfo XML file
for UI culture en-US. Make sure the HelpInfoUri property in the module manifest is valid
or check your network connection and then try the command again.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : ResourceUnavailable: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : UnableToRetrieveHelpInfoXml,Microsoft.PowerShell.Commands.
   UpdateHelpCommand
```

<span data-ttu-id="3a959-272">Alguns módulos retornaram erros, o que não é incomum.</span><span class="sxs-lookup"><span data-stu-id="3a959-272">A couple of the modules returned errors, which is not uncommon.</span></span> <span data-ttu-id="3a959-273">Se o computador não tiver acesso à Internet, você poderá usar o cmdlet `Save-Help` em outro computador que tenha acesso à Internet para primeiro salvar as informações de ajuda atualizadas em um compartilhamento de arquivo em sua rede e, em seguida, usar o parâmetro **SourcePath** de `Update-Help` para especificar esse local de rede para os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3a959-273">If the machine didn't have internet access, you could use the `Save-Help` cmdlet on another machine that does have internet access to first save the updated help information to a file share on your network and then use the **SourcePath** parameter of `Update-Help` to specify this network location for the help topics.</span></span>

<span data-ttu-id="3a959-274">Considere configurar uma tarefa agendada ou adicionar alguma lógica ao script de perfil no PowerShell para atualizar periodicamente o conteúdo da ajuda em seu computador.</span><span class="sxs-lookup"><span data-stu-id="3a959-274">Consider setting up a scheduled task or adding some logic to your profile script in PowerShell to periodically update the help content on your computer.</span></span> <span data-ttu-id="3a959-275">Os scripts de perfil serão discutidos em um capítulo futuro.</span><span class="sxs-lookup"><span data-stu-id="3a959-275">Profile scripts will be discussed in an upcoming chapter.</span></span>

## <a name="summary"></a><span data-ttu-id="3a959-276">Resumo</span><span class="sxs-lookup"><span data-stu-id="3a959-276">Summary</span></span>

<span data-ttu-id="3a959-277">Neste capítulo, você aprendeu a encontrar comandos com `Get-Help` e `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="3a959-277">In this chapter you've learned how to find commands with both `Get-Help` and `Get-Command`.</span></span> <span data-ttu-id="3a959-278">Você aprendeu a usar o sistema de ajuda para descobrir como usar comandos depois de encontrá-los.</span><span class="sxs-lookup"><span data-stu-id="3a959-278">You've learned how to use the help system to figure out how to use commands once you find them.</span></span> <span data-ttu-id="3a959-279">Você também aprendeu a atualizar o conteúdo dos tópicos da ajuda quando as atualizações estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3a959-279">You've also learned how to update the content of the help topics when updates are available.</span></span>

<span data-ttu-id="3a959-280">Meu desafio para você é aprender um comando do PowerShell por dia.</span><span class="sxs-lookup"><span data-stu-id="3a959-280">My challenge to you is to learn a PowerShell command a day.</span></span>

```powershell
Get-Command | Get-Random | Get-Help -Full
```

## <a name="review"></a><span data-ttu-id="3a959-281">Revisão</span><span class="sxs-lookup"><span data-stu-id="3a959-281">Review</span></span>

1. <span data-ttu-id="3a959-282">O parâmetro **DisplayName** de posicional `Get-Service`?</span><span class="sxs-lookup"><span data-stu-id="3a959-282">Is the **DisplayName** parameter of `Get-Service` positional?</span></span>
1. <span data-ttu-id="3a959-283">Quantos conjuntos de parâmetros o cmdlet `Get-Process` tem?</span><span class="sxs-lookup"><span data-stu-id="3a959-283">How many parameter sets does the `Get-Process` cmdlet have?</span></span>
1. <span data-ttu-id="3a959-284">Quais comandos do PowerShell existem para trabalhar com logs de eventos?</span><span class="sxs-lookup"><span data-stu-id="3a959-284">What PowerShell commands exist for working with event logs?</span></span>
1. <span data-ttu-id="3a959-285">Qual é o comando do PowerShell para retornar uma lista de processos do PowerShell em execução no seu computador?</span><span class="sxs-lookup"><span data-stu-id="3a959-285">What is the PowerShell command for returning a list of PowerShell processes running on your computer?</span></span>
1. <span data-ttu-id="3a959-286">Como você atualiza o conteúdo da ajuda do PowerShell armazenado no computador?</span><span class="sxs-lookup"><span data-stu-id="3a959-286">How do you update the PowerShell help content that's stored on your computer?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="3a959-287">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="3a959-287">Recommended Reading</span></span>

<span data-ttu-id="3a959-288">Se você quer obter mais informações sobre os tópicos abordados neste capítulo, recomendo a leitura dos tópicos da Ajuda do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a959-288">If you want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="3a959-289">[Get-Help][]</span><span class="sxs-lookup"><span data-stu-id="3a959-289">[Get-Help][]</span></span>
- <span data-ttu-id="3a959-290">[Get-Command][]</span><span class="sxs-lookup"><span data-stu-id="3a959-290">[Get-Command][]</span></span>
- <span data-ttu-id="3a959-291">[Update-Help][]</span><span class="sxs-lookup"><span data-stu-id="3a959-291">[Update-Help][]</span></span>
- <span data-ttu-id="3a959-292">[Save-Help][]</span><span class="sxs-lookup"><span data-stu-id="3a959-292">[Save-Help][]</span></span>
- <span data-ttu-id="3a959-293">[about_Updatable_Help][]</span><span class="sxs-lookup"><span data-stu-id="3a959-293">[about_Updatable_Help][]</span></span>
- <span data-ttu-id="3a959-294">[about_Command_Syntax][]</span><span class="sxs-lookup"><span data-stu-id="3a959-294">[about_Command_Syntax][]</span></span>

<span data-ttu-id="3a959-295">No próximo capítulo, você aprenderá sobre o cmdlet `Get-Member`, bem como objetos, propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="3a959-295">In the next chapter, you'll learn about the `Get-Member` cmdlet as well as objects, properties, and methods.</span></span>

<!-- link references -->
[Get-Help]: /powershell/module/microsoft.powershell.core/get-help
[Get-Command]: /powershell/module/microsoft.powershell.core/get-command
[Update-Help]: /powershell/module/microsoft.powershell.core/update-help
[Save-Help]: /powershell/module/microsoft.powershell.core/save-help
[about_Updatable_Help]: /powershell/module/microsoft.powershell.core/about/about_updatable_help
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[PowerShell-Docs]: https://github.com/powershell/powershell
[Apêndice A]: appendix-a.md
[Appendix A]: appendix-a.md
