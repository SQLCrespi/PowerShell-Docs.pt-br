---
title: Descobrir o PowerShell
ms.date: 03/12/2021
ms.custom: chnoring
ms.reviewer: sewhee
description: Saiba o que é o PowerShell e alguns comandos essenciais usados para descobrir mais sobre o PowerShell.
ms.openlocfilehash: 34bbd465a918224c203e7243834e7fb3a3a6070c
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104729979"
---
# <a name="discover-powershell"></a><span data-ttu-id="a6b95-103">Descobrir o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6b95-103">Discover PowerShell</span></span>

<span data-ttu-id="a6b95-104">O PowerShell é um shell de linha de comando e uma linguagem de script integrados.</span><span class="sxs-lookup"><span data-stu-id="a6b95-104">PowerShell is a command-line shell and a scripting language in one.</span></span> <span data-ttu-id="a6b95-105">Ele começou no Windows.</span><span class="sxs-lookup"><span data-stu-id="a6b95-105">PowerShell started out on Windows.</span></span> <span data-ttu-id="a6b95-106">Destinava-se a ajudar com a automação de tarefas de administração, mas agora cresceu para se tornar multiplataforma e pode ser usado para uma variedade de tarefas.</span><span class="sxs-lookup"><span data-stu-id="a6b95-106">It was meant to help with task automation for administration tasks but has now grown to be cross platform and can be used for a variety of tasks.</span></span>

<span data-ttu-id="a6b95-107">A característica que faz o PowerShell ser exclusivo é que ele aceita e retorna objetos .NET, em vez de um texto.</span><span class="sxs-lookup"><span data-stu-id="a6b95-107">The thing that makes PowerShell unique is that accepts and returns .NET objects, rather than text.</span></span>
<span data-ttu-id="a6b95-108">Esse fato facilita a conexão de diferentes comandos na série, em um _pipeline_.</span><span class="sxs-lookup"><span data-stu-id="a6b95-108">This fact makes it easier to connect different commands in series, in a _pipeline_.</span></span>

> [!NOTE]
> <span data-ttu-id="a6b95-109">Os pipelines serão abordados mais detalhadamente nesta série de tutoriais.</span><span class="sxs-lookup"><span data-stu-id="a6b95-109">Pipelines will be covered more in detail in this tutorial series.</span></span>

<span data-ttu-id="a6b95-110">Mesmo assim, talvez seja necessário _processar_ os resultados um pouco.</span><span class="sxs-lookup"><span data-stu-id="a6b95-110">Even then, you might need to _massage_ the results a little.</span></span>

## <a name="what-can-powershell--be-used-for"></a><span data-ttu-id="a6b95-111">Para o que o PowerShell pode ser usado?</span><span class="sxs-lookup"><span data-stu-id="a6b95-111">What can PowerShell  be used for?</span></span>

<span data-ttu-id="a6b95-112">O uso do PowerShell aumentou desde a época em que ele era somente Windows.</span><span class="sxs-lookup"><span data-stu-id="a6b95-112">Usage of PowerShell has grown since the days when it was Windows-only.</span></span> <span data-ttu-id="a6b95-113">Ele ainda é usado para a automação de tarefas do Windows, mas hoje, você pode usá-lo para uma variedade de tarefas como:</span><span class="sxs-lookup"><span data-stu-id="a6b95-113">It's still used for Windows task automation, but today, you can use for a variety of tasks like:</span></span>

- <span data-ttu-id="a6b95-114">**Gerenciamento de nuvem**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-114">**Cloud management**.</span></span> <span data-ttu-id="a6b95-115">O PowerShell pode ser usado para gerenciar recursos da nuvem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-115">PowerShell can be used to manage cloud resources.</span></span> <span data-ttu-id="a6b95-116">Por exemplo, você pode recuperar informações sobre recursos da nuvem, bem como atualizar ou implantar novos recursos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-116">For example, you can retrieve information about cloud resources, as well as update or deploy new resources.</span></span>
- <span data-ttu-id="a6b95-117">**CI/CD**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-117">**CI/CD**.</span></span> <span data-ttu-id="a6b95-118">Ele também pode ser usado como parte de um pipeline de integração contínua/implantação contínua.</span><span class="sxs-lookup"><span data-stu-id="a6b95-118">It can also be used as part of a Continuous Integration/Continuous Deployment pipeline.</span></span>
- <span data-ttu-id="a6b95-119">**Automatizar tarefas para o Active Directory e o Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-119">**Automate tasks for Active Directory and Exchange**.</span></span> <span data-ttu-id="a6b95-120">Você pode usá-lo para automatizar quase todas as tarefas do Windows, como a criação de usuários no Active Directory e as caixas de correio no Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6b95-120">You can use it to automate almost any task on Windows like creating users in Active Directory and mailboxes in Exchange.</span></span>

<span data-ttu-id="a6b95-121">Há muitas outras áreas de uso, mas a lista acima já indica que o PowerShell tem feito bastante sucesso.</span><span class="sxs-lookup"><span data-stu-id="a6b95-121">There are many more areas of usage but the list above gives you a hint that PowerShell has come a long way.</span></span>

## <a name="who-uses-powershell"></a><span data-ttu-id="a6b95-122">Quem usa o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a6b95-122">Who uses PowerShell?</span></span>

<span data-ttu-id="a6b95-123">O PowerShell é muito eficiente e muitas pessoas, trabalhando em diversas funções, podem se beneficiar do uso dele.</span><span class="sxs-lookup"><span data-stu-id="a6b95-123">PowerShell is very powerful and a lot of people, working in multitude of roles, can benefit from using it.</span></span> <span data-ttu-id="a6b95-124">Tradicionalmente, o PowerShell vem sendo usado pela função Administrador do sistema, mas já está sendo usado por pessoas que se intitulam Engenheiros de DevOps e de nuvem e, até mesmo, desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="a6b95-124">Traditionally, PowerShell has been used by the System Administrator role but is now being used by people calling themselves DevOps, Cloud Ops, and even Developers.</span></span>

## <a name="powershell-cmdlets"></a><span data-ttu-id="a6b95-125">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6b95-125">PowerShell cmdlets</span></span>

<span data-ttu-id="a6b95-126">O PowerShell é fornecido com centenas de comandos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="a6b95-126">PowerShell comes with hundreds of preinstalled commands.</span></span> <span data-ttu-id="a6b95-127">Os comandos do PowerShell são chamados de cmdlets (pronuncia-se "command-lets").</span><span class="sxs-lookup"><span data-stu-id="a6b95-127">PowerShell command are called cmdlets; pronounced as "command-lets".</span></span>

<span data-ttu-id="a6b95-128">O nome de cada cmdlet consiste em um par de "verbo-substantivo"; por exemplo, `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-128">The name of each cmdlet consists of a "Verb-Noun" pair; for example `Get-Process`.</span></span> <span data-ttu-id="a6b95-129">Essa convenção de nomenclatura facilita o entendimento da função do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6b95-129">This naming convention makes it easier to understand what the cmdlet does.</span></span> <span data-ttu-id="a6b95-130">Também facilita a localização do comando procurado.</span><span class="sxs-lookup"><span data-stu-id="a6b95-130">It also make it easier to find the command your looking for.</span></span> <span data-ttu-id="a6b95-131">Ao procurar um cmdlet para uso, você pode filtrar pelo verbo ou pelo substantivo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-131">When looking for a cmdlet to use, you can filter on the verb or noun.</span></span>

### <a name="using-cmdlets-to-explore-powershell"></a><span data-ttu-id="a6b95-132">Como usar cmdlets para explorar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6b95-132">Using cmdlets to explore PowerShell</span></span>

<span data-ttu-id="a6b95-133">Quando você usa o PowerShell pela primeira vez, ele pode parecer intimidador, pois parece muito difícil de aprender.</span><span class="sxs-lookup"><span data-stu-id="a6b95-133">When you first pick up PowerShell, it might feel intimidating as there seems to be so much to learn.</span></span>
<span data-ttu-id="a6b95-134">No entanto, o PowerShell foi projetado para ajudar você a aprender um pouco de cada vez, conforme a sua necessidade.</span><span class="sxs-lookup"><span data-stu-id="a6b95-134">However, PowerShell is designed to help you learn a little at a time, as you need it.</span></span>

<span data-ttu-id="a6b95-135">O PowerShell inclui cmdlets que ajudam você a descobri-lo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-135">PowerShell includes cmdlets that help you discover PowerShell.</span></span> <span data-ttu-id="a6b95-136">Usando estes três cmdlets, você pode descobrir quais comandos estão disponíveis, o que eles fazem e em quais tipos eles operam.</span><span class="sxs-lookup"><span data-stu-id="a6b95-136">Using these three cmdlets, you can discover what commands available, what they do, and what types they operate on.</span></span>

- <span data-ttu-id="a6b95-137">`Get-Verb`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-137">`Get-Verb`.</span></span> <span data-ttu-id="a6b95-138">A execução desse comando retorna uma lista de verbos seguidos pela maioria dos comandos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-138">Running this command returns a list of verbs that most commands adhere to.</span></span>
  <span data-ttu-id="a6b95-139">Além disso, a resposta descreve o que esses verbos fazem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-139">Additionally, the response describes what these verbs does.</span></span> <span data-ttu-id="a6b95-140">Como a maioria dos comandos segue essa nomenclatura, ela define as expectativas sobre o que um comando faz, o que ajuda você a escolher o comando apropriado, mas também como nomear um comando, caso você esteja criando um.</span><span class="sxs-lookup"><span data-stu-id="a6b95-140">As most commands follow this naming, it sets expectations on what a command does, which helps you select the appropriate command but also what to name a command, should you be creating one.</span></span>
- <span data-ttu-id="a6b95-141">`Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-141">`Get-Command`.</span></span> <span data-ttu-id="a6b95-142">Esse comando recupera uma lista de todos os comandos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="a6b95-142">This command retrieves a list of all commands installed on your machine.</span></span>
- <span data-ttu-id="a6b95-143">`Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-143">`Get-Member`.</span></span> <span data-ttu-id="a6b95-144">Ele opera na saída baseada em objeto e pode descobrir quais objetos, propriedades e métodos estão disponíveis para um comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-144">It operates on object based output and is able to discover what object, properties and methods are available for a command.</span></span>
- <span data-ttu-id="a6b95-145">`Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-145">`Get-Help`.</span></span> <span data-ttu-id="a6b95-146">A invocação desse comando com o nome de um comando como argumento exibe uma página de ajuda que descreve várias partes de um comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-146">Invoking this command with the name of a command as an argument displays a help page describing various parts of a command.</span></span>

<span data-ttu-id="a6b95-147">Usando esses comandos, você pode descobrir quase tudo do que precisa saber sobre o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6b95-147">Using these commands, you can discover almost anything you need to know about PowerShell.</span></span>

### <a name="verb"></a><span data-ttu-id="a6b95-148">Verbo</span><span class="sxs-lookup"><span data-stu-id="a6b95-148">Verb</span></span>

<span data-ttu-id="a6b95-149">O verbo é um conceito importante no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6b95-149">Verb is an important concepts in PowerShell.</span></span> <span data-ttu-id="a6b95-150">É um padrão de nomenclatura seguido pela maioria dos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a6b95-150">It's a naming standard that most cmdlets follow.</span></span> <span data-ttu-id="a6b95-151">Também é um padrão de nomenclatura que você deve seguir depois de escrever comandos próprios.</span><span class="sxs-lookup"><span data-stu-id="a6b95-151">It's also a naming standard you're expected to follow, once you write your own commands.</span></span> <span data-ttu-id="a6b95-152">A ideia é que o _verbo_ indica o que você está tentando fazer: ler dados ou talvez alterá-los.</span><span class="sxs-lookup"><span data-stu-id="a6b95-152">The idea is that the _verb_ says what you're trying to do, read data or maybe change it.</span></span> <span data-ttu-id="a6b95-153">O PowerShell tem uma lista padronizada de verbos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-153">PowerShell has a standardized list of verbs.</span></span> <span data-ttu-id="a6b95-154">Para obter uma lista completa de todos os verbos possíveis, use o cmdlet `Get-Verb`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-154">To get a full list of all possible verbs, use the `Get-Verb` cmdlet:</span></span>

```powershell
Get-Verb
```

<span data-ttu-id="a6b95-155">A saída da execução dele é uma longa lista de verbos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-155">The output from running it, is a long list of verbs.</span></span> <span data-ttu-id="a6b95-156">O que é informativo sobre a resposta é que ela também mostra mais contexto, o que esse verbo deve fazer.</span><span class="sxs-lookup"><span data-stu-id="a6b95-156">What's informative about the response, is that it also shows more context, what such a verb is meant to do.</span></span> <span data-ttu-id="a6b95-157">Veja a primeira linha da saída:</span><span class="sxs-lookup"><span data-stu-id="a6b95-157">Here's the first row of the output:</span></span>

```output
Verb        AliasPrefix Group          Description
----        ----------- -----          -----------
Add         a           Common         Adds a resource to a container, or attaches an item to ano…
```

## <a name="find-commands-with-get-command"></a><span data-ttu-id="a6b95-158">Localizar comandos com Get-Command</span><span class="sxs-lookup"><span data-stu-id="a6b95-158">Find commands with Get-Command</span></span>

<span data-ttu-id="a6b95-159">O cmdlet `Get-Command` retorna uma lista de todos os comandos disponíveis instalados no sistema.</span><span class="sxs-lookup"><span data-stu-id="a6b95-159">The `Get-Command` cmdlet returns a list of all available commands that are installed on your system.</span></span>
<span data-ttu-id="a6b95-160">No entanto, a lista que você recebe é bem grande.</span><span class="sxs-lookup"><span data-stu-id="a6b95-160">That list you get back, is quite large though.</span></span> <span data-ttu-id="a6b95-161">Para facilitar a localização dos comandos, limite o volume de informações retornado.</span><span class="sxs-lookup"><span data-stu-id="a6b95-161">To make finding commands easier you can limit the amount of information that comes back.</span></span> <span data-ttu-id="a6b95-162">Você pode filtrar a resposta usando parâmetros ou cmdlets auxiliares.</span><span class="sxs-lookup"><span data-stu-id="a6b95-162">You can filter the response using either parameters or by using helper cmdlets.</span></span>

### <a name="filter-on-name"></a><span data-ttu-id="a6b95-163">Filtragem por nome</span><span class="sxs-lookup"><span data-stu-id="a6b95-163">Filter on name</span></span>

<span data-ttu-id="a6b95-164">Você pode filtrar a saída de `Get-Command` usando diferentes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a6b95-164">You can filter the output of `Get-Command`, using different parameters.</span></span> <span data-ttu-id="a6b95-165">Esse tipo de filtragem consiste em consultar uma propriedade específica no comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-165">Filtering this way, is about querying a specific property on the command.</span></span> <span data-ttu-id="a6b95-166">A ideia é que você especifica a propriedade para filtragem e fornece uma cadeia de caracteres para correspondência.</span><span class="sxs-lookup"><span data-stu-id="a6b95-166">The idea is that you specify what property you want to filter against, and then you provide a string that you want to match against.</span></span> <span data-ttu-id="a6b95-167">Portanto, você obterá uma comparação semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a6b95-167">You'll therefore get a comparison that looks like this:</span></span>

```powershell
Get-Command -Name '*Process'
```

<span data-ttu-id="a6b95-168">Neste ponto, a filtragem está tentando fazer uma correspondência exata com o argumento de cadeia de caracteres fornecido.</span><span class="sxs-lookup"><span data-stu-id="a6b95-168">At this point, the filtering is trying to do an exact matching against the provided string argument.</span></span>
<span data-ttu-id="a6b95-169">Caso deseje ter mais flexibilidade na comparação, use um curinga `*`, que faz a correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="a6b95-169">If you want to have more flexibility, in the comparison, you can use a wildcard `*`, that does pattern matching.</span></span> <span data-ttu-id="a6b95-170">O seguinte código procura todos os comandos cujo nome termina com Process:</span><span class="sxs-lookup"><span data-stu-id="a6b95-170">The following code would look for all commands, who's name ends with process:</span></span>

<span data-ttu-id="a6b95-171">Acima, o parâmetro `-Name` é usado para filtragem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-171">Above, the parameter the `-Name` is used to filter.</span></span> <span data-ttu-id="a6b95-172">Além de `-Name`, você também pode fazer a filtragem por `-ParameterName` e `-Type`, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-172">Apart from `-Name`, you can also filter on `-ParameterName` and `-Type`, for example.</span></span>

### <a name="filtering-on-noun-and-verb"></a><span data-ttu-id="a6b95-173">Filtragem por substantivo e verbo</span><span class="sxs-lookup"><span data-stu-id="a6b95-173">Filtering on Noun and Verb</span></span>

<span data-ttu-id="a6b95-174">Você viu como fazer a filtragem por `-Name` e descobriu que há outros parâmetros que também podem ser usados para a filtragem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-174">You've seen how you can filter on `-Name`, and that there are other parameters you can filter on as well.</span></span> <span data-ttu-id="a6b95-175">Os verbos e os substantivos são algo que também podem ser usados na filtragem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-175">Verb and noun is something you can filter on as well.</span></span> <span data-ttu-id="a6b95-176">Essa filtragem é direcionada a uma parte do nome de um comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-176">Such filtering targets part of a command's name.</span></span>

- <span data-ttu-id="a6b95-177">**Filtragem por verbo**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-177">**Filter on verb**.</span></span> <span data-ttu-id="a6b95-178">A parte do verbo do nome de um comando é a parte mais à esquerda.</span><span class="sxs-lookup"><span data-stu-id="a6b95-178">The verb part of a command's name is the leftmost part.</span></span> <span data-ttu-id="a6b95-179">No comando `Get-Process`, a parte do verbo é `Get`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-179">In the command `Get-Process`, the verb part is `Get`.</span></span> <span data-ttu-id="a6b95-180">Para fazer a filtragem na parte do verbo, especifique `-Verb` como um parâmetro desta maneira:</span><span class="sxs-lookup"><span data-stu-id="a6b95-180">To filter on th verb part, specify `-Verb` as a parameter like so:</span></span>

   ```powershell
   Get-Command -Verb 'Get'
   ```

   <span data-ttu-id="a6b95-181">O comando acima listará todos os comandos em que a parte do verbo é `Get`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-181">The above command would list all the commands where the verb part is `Get`.</span></span>

- <span data-ttu-id="a6b95-182">**Filtragem por substantivo**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-182">**Filter on noun**.</span></span> <span data-ttu-id="a6b95-183">A parte mais à direita de um comando é a parte do substantivo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-183">The rightmost part of a command is the noun part.</span></span> <span data-ttu-id="a6b95-184">Enquanto o verbo deve estar entre os verbos retornados da invocação `Get-Verb`, um substantivo pode ser qualquer coisa.</span><span class="sxs-lookup"><span data-stu-id="a6b95-184">Where verb should be among the verbs returned from invoking `Get-Verb`, a noun can be anything.</span></span> <span data-ttu-id="a6b95-185">No comando `Get-Process`, a parte do substantivo é `Process`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-185">In the command `Get-Process`, the noun part is `Process`.</span></span> <span data-ttu-id="a6b95-186">Para fazer a filtragem por substantivo, especifique `-Noun` como um parâmetro e um argumento de cadeia de caracteres desta maneira:</span><span class="sxs-lookup"><span data-stu-id="a6b95-186">To filter on noun, specify `-Noun` as a parameter and a string argument, like so:</span></span>

   ```powershell
   Get-Command -Noun U*
   ```

<span data-ttu-id="a6b95-187">Na filtragem, o uso apenas do verbo ou do substantivo ainda pode gerar um resultado grande.</span><span class="sxs-lookup"><span data-stu-id="a6b95-187">Only using the verb, or the noun, to filter on, might lead to a big result still.</span></span> <span data-ttu-id="a6b95-188">Para restringir a pesquisa, é bom combinar os dois parâmetros, como o exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="a6b95-188">To narrow down your search, it's good to combine the two parameters like the below example:</span></span>

```powershell
Get-Command -Verb Get -Noun U*
```

<span data-ttu-id="a6b95-189">O resultado da pesquisa acima ficará parecido com este:</span><span class="sxs-lookup"><span data-stu-id="a6b95-189">The result of the above looks like so:</span></span>

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Get-UICulture                7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Unique                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Uptime                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-UsageAggregates          2.0.0      Az.Billing
```

<span data-ttu-id="a6b95-190">Assim, você limitou muito a saída sabendo o verbo e como ele é chamado.</span><span class="sxs-lookup"><span data-stu-id="a6b95-190">Thereby, you narrowed down the output quite bit by knowing the verb and what it's called.</span></span>

### <a name="use-helper-cmdlets-to-filter-results"></a><span data-ttu-id="a6b95-191">Usar cmdlets auxiliares para filtrar os resultados</span><span class="sxs-lookup"><span data-stu-id="a6b95-191">Use helper cmdlets to filter results</span></span>

<span data-ttu-id="a6b95-192">Além de usar parâmetros para filtragem, use também comandos para ajudar você com essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="a6b95-192">Apart from using parameters to filter, you can also use commands to help you with this task.</span></span> <span data-ttu-id="a6b95-193">Estes são alguns comandos que podem funcionar como filtros:</span><span class="sxs-lookup"><span data-stu-id="a6b95-193">Here's some commands that can act as filters:</span></span>

- <span data-ttu-id="a6b95-194">`Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-194">`Select-Object`.</span></span> <span data-ttu-id="a6b95-195">É um comando muito versátil que ajuda você a selecionar propriedades específicas de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-195">It's a very versatile command that helps you pick out specific properties from one or more objects.</span></span> <span data-ttu-id="a6b95-196">Além disso, com o uso de parâmetros, você pode limitar a resposta retornada.</span><span class="sxs-lookup"><span data-stu-id="a6b95-196">Additionally by using it's parameters you can limit the response you get back.</span></span> <span data-ttu-id="a6b95-197">Este é um exemplo do uso de `Select-Object` para solicitar um número limitado de registros:</span><span class="sxs-lookup"><span data-stu-id="a6b95-197">Here's an example of `Select-Object` being used to ask for a limited number of records:</span></span>

   ```powershell
   Get-Command | Select-Object -First 3
   ```

   <span data-ttu-id="a6b95-198">O resultado da pesquisa acima são os três primeiros comandos, contados do início.</span><span class="sxs-lookup"><span data-stu-id="a6b95-198">The result from the above is the three first commands, counted from the top.</span></span> <span data-ttu-id="a6b95-199">O resultado será parecido com este:</span><span class="sxs-lookup"><span data-stu-id="a6b95-199">The result looks like so:</span></span>

   ```output
   CommandType     Name                                               Version    Source
   -----------     ----                                               -------    ------
   Alias           Add-AdlAnalyticsDataSource                         1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlAnalyticsFirewallRule                       1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlStoreFirewallRule                           1.3.0      Az.DataLakeStore
   ```

   <span data-ttu-id="a6b95-200">Vale a pena examinar esse comando mais detalhadamente na [documentação de Select-Object](/powershell/module/microsoft.powershell.utility/select-object), pois ele pode fazer muitas outras coisas</span><span class="sxs-lookup"><span data-stu-id="a6b95-200">It's worth looking into to this command further as it can do a lot more  [docs Select-Object](/powershell/module/microsoft.powershell.utility/select-object)</span></span>

- <span data-ttu-id="a6b95-201">`Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-201">`Where-Object`.</span></span> <span data-ttu-id="a6b95-202">O objeto Where ajuda você a selecionar objetos de uma coleção com base nos valores das propriedades.</span><span class="sxs-lookup"><span data-stu-id="a6b95-202">The where object helps you select objects from a collection based on the values of properties.</span></span> <span data-ttu-id="a6b95-203">O comando usa uma expressão na qual você pode expressar quais colunas deseja usar para a correspondência com determinados valores.</span><span class="sxs-lookup"><span data-stu-id="a6b95-203">The command takes an expression in which you are able to express what column/s you want to match against what values.</span></span> <span data-ttu-id="a6b95-204">Para localizar todos os objetos de processo em que o `ProcessName` começa com `p`, use `Where-Object` desta forma:</span><span class="sxs-lookup"><span data-stu-id="a6b95-204">To find all process object where the `ProcessName` starts with `p`, you could use `Where-Object` like so:</span></span>

  ```powershell
  Get-Process | Where-Object {$_.ProcessName -Like "p*"}
  ```

  <span data-ttu-id="a6b95-205">Acima, o cmdlet `Get-Process` produz uma coleção de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-205">Above, the `Get-Process` cmdlet produces a collection of process objects.</span></span> <span data-ttu-id="a6b95-206">Para filtrar a resposta, _redirecione_ o comando `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-206">To filter down the response, you _pipe_ the command `Where-Object`.</span></span> <span data-ttu-id="a6b95-207">O uso de um pipe significa que dois ou mais comandos são conectados por meio de um caractere de barra vertical `|`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-207">Piping means that two or more commands are connected via a pipe `|` character.</span></span> <span data-ttu-id="a6b95-208">A ideia é que a saída de um comando sirva como a entrada do próximo, lido da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="a6b95-208">The idea is that the output from one command serves as the input for the next command, as read from left to right.</span></span> <span data-ttu-id="a6b95-209">O `Where-Object` usa uma expressão para filtragem.</span><span class="sxs-lookup"><span data-stu-id="a6b95-209">The `Where-Object` uses an expression to filter.</span></span> <span data-ttu-id="a6b95-210">A própria expressão usa o operador `-Like` e o argumento de cadeia de caracteres que é uma expressão curinga.</span><span class="sxs-lookup"><span data-stu-id="a6b95-210">The expression itself uses the `-Like` operator and string argument that is a wildcard expression.</span></span>

## <a name="explore-objects-with-get-member"></a><span data-ttu-id="a6b95-211">Explorar objetos com Get-Member</span><span class="sxs-lookup"><span data-stu-id="a6b95-211">Explore objects with Get-Member</span></span>

<span data-ttu-id="a6b95-212">Depois que você conseguir localizar o cmdlet desejado, o ideal será saber mais sobre o que ele produz, a saída.</span><span class="sxs-lookup"><span data-stu-id="a6b95-212">Once you've been able to locate the cmdlet you want, you want to know more about what it produces, the output.</span></span> <span data-ttu-id="a6b95-213">A saída é interessante por vários motivos, como:</span><span class="sxs-lookup"><span data-stu-id="a6b95-213">The output is interesting for several reasons like:</span></span>

- <span data-ttu-id="a6b95-214">**Autônomo**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-214">**Standalone**.</span></span> <span data-ttu-id="a6b95-215">Você pode executar apenas um cmdlet e desejar exibir a saída em um tipo de relatório.</span><span class="sxs-lookup"><span data-stu-id="a6b95-215">You might run just one cmdlet and you want to display the output in some sort of report.</span></span> <span data-ttu-id="a6b95-216">A pergunta a ser feita é se o comando produz uma saída que funciona para você ou se ela precisa ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a6b95-216">The question to ask yourself is whether the command produces an output that works for you, or if you need to change it.</span></span>
- <span data-ttu-id="a6b95-217">**Quando usado em um pipeline**.</span><span class="sxs-lookup"><span data-stu-id="a6b95-217">**When used in a pipeline**.</span></span> <span data-ttu-id="a6b95-218">No PowerShell, é comum conectar vários comandos em um pipeline para buscar dados, filtrá-los e, por fim, transformá-los.</span><span class="sxs-lookup"><span data-stu-id="a6b95-218">It's common in PowerShell to connect several commands in a pipeline, to fetch data, filter and finally to transform it.</span></span> <span data-ttu-id="a6b95-219">Para que um comando se ajuste a um pipeline, você precisa examinar a entrada e a saída produzidas por ele.</span><span class="sxs-lookup"><span data-stu-id="a6b95-219">For a command to fit into a pipeline, you have to look at what input and output it produces.</span></span> <span data-ttu-id="a6b95-220">A ideia é que a saída de um comando seja usada como a entrada de outro.</span><span class="sxs-lookup"><span data-stu-id="a6b95-220">The idea is that the output of a command is used as the input of another command.</span></span>

<span data-ttu-id="a6b95-221">O cmdlet `Get-Member` exibe as propriedades e os métodos do resultado.</span><span class="sxs-lookup"><span data-stu-id="a6b95-221">The `Get-Member` cmdlet displays the properties and methods of the result.</span></span> <span data-ttu-id="a6b95-222">Além disso, ele mostra o tipo do objeto.</span><span class="sxs-lookup"><span data-stu-id="a6b95-222">Additionally it also show the type of the object.</span></span> <span data-ttu-id="a6b95-223">Redirecione a saída que deseja inspecionar para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-223">Pipe the output you want to inspect to `Get-Member`.</span></span>

```powershell
Get-Process | Get-Member
```

<span data-ttu-id="a6b95-224">O resultado exibe o tipo de retorno como `TypeName`, e todas as propriedades e os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="a6b95-224">The result displays the returned type as `TypeName` and then all the properties and methods of the object.</span></span> <span data-ttu-id="a6b95-225">Veja um trecho desse resultado:</span><span class="sxs-lookup"><span data-stu-id="a6b95-225">Here's an excerpt of such a result:</span></span>

```output
TypeName: System.Diagnostics.Process

Name        MemberType     Definition
----        ----------     ----------
Handles     AliasProperty  Handles = Handlecount
Name        AliasProperty  Name = ProcessName
```

<span data-ttu-id="a6b95-226">Um objeto geralmente tem muitas propriedades e métodos. Para encontrar com mais facilidade o que você está procurando, filtre os resultados.</span><span class="sxs-lookup"><span data-stu-id="a6b95-226">An object usually has plenty of properties and methods, to more easily find what you're looking for, you can filter the results.</span></span> <span data-ttu-id="a6b95-227">Usando o parâmetro `-MemberType`, você pode especificar, por exemplo, a visualização de todos os métodos, como no exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="a6b95-227">By using the parameter `-MemberType`, you can specify to, for example see all the methods, like in the below example:</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

<span data-ttu-id="a6b95-228">Quando você recebe uma resposta, o PowerShell geralmente exibe apenas algumas propriedades.</span><span class="sxs-lookup"><span data-stu-id="a6b95-228">When you get a response back, PowerShell usually only displays a few properties.</span></span> <span data-ttu-id="a6b95-229">Na resposta acima, as propriedades `Name`, `MemberType` e `Definition` foram exibidas.</span><span class="sxs-lookup"><span data-stu-id="a6b95-229">In the above response, `Name`, `MemberType` and `Definition` was displayed.</span></span> <span data-ttu-id="a6b95-230">Para alterar essa exibição, use o cmdlet `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-230">To change that display, you can use the cmdlet `Select-Object`.</span></span> <span data-ttu-id="a6b95-231">`Select-Object` permite que você especifique as colunas que deseja ver.</span><span class="sxs-lookup"><span data-stu-id="a6b95-231">`Select-Object` allows you to specify what columns you want to see.</span></span> <span data-ttu-id="a6b95-232">Você pode fornecê-lo com o nome da coluna, uma lista separada por vírgula ou um curinga `*`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-232">You can either provide it with the name of the column, a comma separated list or a wildcard `*`.</span></span> <span data-ttu-id="a6b95-233">Veja um exemplo em que `Select-Object` é usado para recuperar `Name` e `Definition`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-233">Here's an example where `Select-Object` is used to retrieve `Name` and `Definition`:</span></span>

```powershell
Get-Process | Get-Member | Select-Object Name, Definition
```

### <a name="search-by-type"></a><span data-ttu-id="a6b95-234">Pesquisa por tipo</span><span class="sxs-lookup"><span data-stu-id="a6b95-234">Search by type</span></span>

<span data-ttu-id="a6b95-235">Outra maneira de abordar a pesquisa do comando desejado é procurar todos os comandos que operam no mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-235">Another way to approach searching for the command you want, is by searching for commands all operating on the same type.</span></span> <span data-ttu-id="a6b95-236">Quando usou `Get-Member`, você obteve o tipo de retorno como a primeira linha da resposta, desta forma:</span><span class="sxs-lookup"><span data-stu-id="a6b95-236">When you used `Get-Member`, you got the returned type as the first line of the response like so:</span></span>

```output
TypeName: System.Diagnostics.Process
```

<span data-ttu-id="a6b95-237">Agora você pode usar esse tipo e pesquisar comandos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a6b95-237">You can now use this type and search for commands like so:</span></span>

```powershell
Get-Command -ParameterType Process
```

<span data-ttu-id="a6b95-238">O resultado da invocação do comando acima é uma lista com os comandos que só operam no tipo `Process`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-238">The result from invoking the above is a list with commands that solely operates on the `Process` type:</span></span>

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Debug-Process                7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Enter-PSHostProcess          7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Process                  7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Get-PSHostProcessInfo        7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Wait-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
```

<span data-ttu-id="a6b95-239">Como você pode ver, saber o tipo de um comando pode restringir muito a sua pesquisa com os comandos que podem ser interessantes para você.</span><span class="sxs-lookup"><span data-stu-id="a6b95-239">As you can see, knowing the type of a command, can greatly narrow down your search after commands that might be interesting for you.</span></span>

## <a name="exercise---calling-your-first-command"></a><span data-ttu-id="a6b95-240">Exercício – Como chamar seu primeiro comando</span><span class="sxs-lookup"><span data-stu-id="a6b95-240">Exercise - calling your first command</span></span>

<span data-ttu-id="a6b95-241">Neste exercício, você aprenderá a executar seu primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-241">In this exercise, you'll learn how to run your first command.</span></span>

1. <span data-ttu-id="a6b95-242">Inicie um console do PowerShell digitando `pwsh`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-242">Start a PowerShell console by typing `pwsh`:</span></span>

   ```powershell
   pwsh
   ```

1. <span data-ttu-id="a6b95-243">Execute o seguinte `$PSVersionTable.PSVersion`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-243">Run the following `$PSVersionTable.PSVersion`:</span></span>

   ```powershell
   $PSVersionTable.PSVersion
   ```

   <span data-ttu-id="a6b95-244">A saída será parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="a6b95-244">Your output looks similar to this:</span></span>

   ```output
   Major  Minor  Patch  PreReleaseLabel BuildLabel
   -----  -----  -----  --------------- ----------
   7      1      0
   ```

   <span data-ttu-id="a6b95-245">Parabéns! Você executou com êxito seu primeiro comando e conseguiu obter informações sobre a versão do PowerShell instalada no sistema.</span><span class="sxs-lookup"><span data-stu-id="a6b95-245">Congrats, you've successfully run your first command and was able to get information of what version of PowerShell is installed on your system.</span></span>

## <a name="exercise---find-related-commands"></a><span data-ttu-id="a6b95-246">Exercício – Localizar comandos relacionados</span><span class="sxs-lookup"><span data-stu-id="a6b95-246">Exercise - find related commands</span></span>

<span data-ttu-id="a6b95-247">Neste exercício, sua meta é aprender mais sobre um comando.</span><span class="sxs-lookup"><span data-stu-id="a6b95-247">In this exercise your goal is to learn more about a command.</span></span> <span data-ttu-id="a6b95-248">Ao fazer isso, você também encontrará informações como em que tipo ele opera e quais outros comandos semelhantes operam no mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="a6b95-248">In doing so you'll also find things like what type it operates on and what other similar commands operate on that same type.</span></span>

1. <span data-ttu-id="a6b95-249">Verifique se você tem um shell do PowerShell iniciado</span><span class="sxs-lookup"><span data-stu-id="a6b95-249">Ensure you have a started PowerShell shell</span></span>
1. <span data-ttu-id="a6b95-250">Execute o comando `Get-Process`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-250">Run the the command `Get-Process`:</span></span>

   ```powershell
   Get-Process | Get-Member | Select-Object TypeName -Unique
   ```

   <span data-ttu-id="a6b95-251">A saída será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a6b95-251">Your output resembles this:</span></span>

   ```output
   TypeName
   --------
   System.Diagnostics.Process
   --------
   ```

   <span data-ttu-id="a6b95-252">O que você recebe são os tipos retornados pelo comando `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-252">What you're getting back, is a the types returned by the command `Get-Command`.</span></span> <span data-ttu-id="a6b95-253">Neste ponto, agora você pode descobrir qual outro comando também opera nesses tipos.</span><span class="sxs-lookup"><span data-stu-id="a6b95-253">At this point you can now find out what other command also operates on these types.</span></span>

1. <span data-ttu-id="a6b95-254">Execute o comando `Get-Command`:</span><span class="sxs-lookup"><span data-stu-id="a6b95-254">Run the command `Get-Command`:</span></span>

   ```powershell
   Get-Command -ParameterType Process
   ```

   <span data-ttu-id="a6b95-255">A saída será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a6b95-255">Your output resembles this:</span></span>

   ```output
   CommandType     Name                         Version    Source
    -----------     ----                        -------    ------
    Cmdlet          Debug-Process               7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Enter-PSHostProcess         7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Get-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Get-PSHostProcessInfo       7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Stop-Process                7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Wait-Process                7.0.0.0    Microsoft.PowerShell.Managem…
   ```

   <span data-ttu-id="a6b95-256">Parabéns! Você conseguiu encontrar outros comandos que operam no mesmo tipo `Process`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-256">Congratulations, you've managed to find other commands that operates on the same type `Process`.</span></span>
   <span data-ttu-id="a6b95-257">O uso de `Get-Member` é um bom ponto de partida para entender quais outros comandos você deve conferir em seguida.</span><span class="sxs-lookup"><span data-stu-id="a6b95-257">Using `Get-Member` is a good starting point to understand what other commands you should check out next.</span></span>

## <a name="summary"></a><span data-ttu-id="a6b95-258">Resumo</span><span class="sxs-lookup"><span data-stu-id="a6b95-258">Summary</span></span>

<span data-ttu-id="a6b95-259">Nesta primeira parte, você aprendeu o que é o PowerShell e em quais áreas ele pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="a6b95-259">In this first part, you learned what PowerShell is and what areas in can be used.</span></span> <span data-ttu-id="a6b95-260">Depois, você aprendeu sobre os cmdlets, em particular, sobre `Get-Command`, `Get-Verb` e `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="a6b95-260">You where then taught about cmdlets and in particular `Get-Command`, `Get-Verb` and `Get-Member`.</span></span> <span data-ttu-id="a6b95-261">Saber esses cmdlets é importante, pois eles ensinam você a como aprender.</span><span class="sxs-lookup"><span data-stu-id="a6b95-261">Knowing theses cmdlets is important as it teaches you how to learn.</span></span> <span data-ttu-id="a6b95-262">Na próxima parte, você aprenderá a usar o eficiente sistema de ajuda.</span><span class="sxs-lookup"><span data-stu-id="a6b95-262">In the next part, you'll learn how to use the powerful help system.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a6b95-263">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a6b95-263">Additional resources</span></span>

- [<span data-ttu-id="a6b95-264">Get-Command</span><span class="sxs-lookup"><span data-stu-id="a6b95-264">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="a6b95-265">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a6b95-265">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
