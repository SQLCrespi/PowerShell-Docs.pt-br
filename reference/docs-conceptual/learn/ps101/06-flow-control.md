---
title: Controle de fluxo
description: O PowerShell fornece métodos para criar loops, tomar decisões e controlar logicamente o fluxo de código em scripts.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 4f0d7b7f5f3c12bb9475af5aed42b2d32cfbc14d
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437987"
---
# <a name="chapter-6---flow-control"></a><span data-ttu-id="b7386-103">Capítulo 6 – Controle de fluxo</span><span class="sxs-lookup"><span data-stu-id="b7386-103">Chapter 6 - Flow control</span></span>

## <a name="scripting"></a><span data-ttu-id="b7386-104">Scripting</span><span class="sxs-lookup"><span data-stu-id="b7386-104">Scripting</span></span>

<span data-ttu-id="b7386-105">Quando você passa da escrita de comandos de uma linha do PowerShell para a escrita de scripts, isso parece muito mais complicado do que realmente é.</span><span class="sxs-lookup"><span data-stu-id="b7386-105">When you move from writing PowerShell one-liners to writing scripts, it sounds a lot more complicated than it really is.</span></span> <span data-ttu-id="b7386-106">Um script não é nada mais do que os comandos idênticos ou semelhantes que você executará de maneira interativa no console do PowerShell, exceto que eles são salvos como um arquivo `.PS1`.</span><span class="sxs-lookup"><span data-stu-id="b7386-106">A script is nothing more than the same or similar commands that you would run interactively in the PowerShell console, except they're saved as a `.PS1` file.</span></span> <span data-ttu-id="b7386-107">Há alguns constructos de script que você poderá usar como um loop `foreach` em vez do cmdlet `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="b7386-107">There are some scripting constructs that you may use such as a `foreach` loop instead of the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="b7386-108">Para iniciantes, as diferenças podem ser confusas, especialmente quando você considera que `foreach` é um constructo de script e um alias para o cmdlet `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="b7386-108">To beginners, the differences can be confusing especially when you consider that `foreach` is both a scripting construct and an alias for the `ForEach-Object` cmdlet.</span></span>

## <a name="looping"></a><span data-ttu-id="b7386-109">Loop</span><span class="sxs-lookup"><span data-stu-id="b7386-109">Looping</span></span>

<span data-ttu-id="b7386-110">Uma das grandes vantagens do PowerShell é que, logo que você descobre como fazer algo para um item, é quase tão fácil realizar a mesma tarefa para centenas de itens.</span><span class="sxs-lookup"><span data-stu-id="b7386-110">One of the great things about PowerShell is, once you figure out how to do something for one item, it's almost as easy to do the same task for hundreds of items.</span></span> <span data-ttu-id="b7386-111">Basta executar um loop pelos itens usando um dos vários tipos diferentes de loops no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7386-111">Simply loop through the items using one of the many different types of loops in PowerShell.</span></span>

### <a name="foreach-object"></a><span data-ttu-id="b7386-112">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="b7386-112">ForEach-Object</span></span>

<span data-ttu-id="b7386-113">`ForEach-Object` é um cmdlet para iterar em itens de um pipeline, como é o caso dos comandos de uma linha do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7386-113">`ForEach-Object` is a cmdlet for iterating through items in a pipeline such as with PowerShell one-liners.</span></span> <span data-ttu-id="b7386-114">`ForEach-Object` transmite os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="b7386-114">`ForEach-Object` streams the objects through the pipeline.</span></span>

<span data-ttu-id="b7386-115">Embora o parâmetro **Module** de `Get-Command` aceite vários valores que são cadeias de caracteres, ele só os aceita por meio da entrada de pipeline pelo nome da propriedade ou por meio da entrada de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b7386-115">Although the **Module** parameter of `Get-Command` accepts multiple values that are strings, it only accepts them via pipeline input by property name or via parameter input.</span></span> <span data-ttu-id="b7386-116">No cenário a seguir, se eu quiser direcionar duas cadeias de caracteres por valor para `Get-Command` para uso com o parâmetro **Module**, precisarei usar o cmdlet `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="b7386-116">In the following scenario, if I want to pipe two strings by value to `Get-Command` for use with the **Module** parameter, I would need to use the `ForEach-Object` cmdlet.</span></span>

```powershell
'ActiveDirectory', 'SQLServer' |
   ForEach-Object {Get-Command -Module $_} |
     Group-Object -Property ModuleName -NoElement |
         Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  147 ActiveDirectory
   82 SqlServer
```

<span data-ttu-id="b7386-117">No exemplo anterior, `$_` é o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="b7386-117">In the previous example, `$_` is the current object.</span></span> <span data-ttu-id="b7386-118">No PowerShell versão 3.0 em diante, `$PSItem` pode ser usado em vez de `$_`.</span><span class="sxs-lookup"><span data-stu-id="b7386-118">Beginning with PowerShell version 3.0, `$PSItem` can be used instead of `$_`.</span></span> <span data-ttu-id="b7386-119">Porém, acho que os usuários mais experientes do PowerShell ainda preferem usar `$_`, já que ele é compatível com versões anteriores e leva menos tempo para digitar.</span><span class="sxs-lookup"><span data-stu-id="b7386-119">But I find that most experienced PowerShell users still prefer using `$_` since it's backward compatible and less to type.</span></span>

<span data-ttu-id="b7386-120">Ao usar a palavra-chave `foreach`, você precisará armazenar todos os itens na memória antes de iterar neles, o que pode ser difícil se você não sabe com quantos itens está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="b7386-120">When using the `foreach` keyword, you must store all of the items in memory before iterating through them, which could be difficult if you don't know how many items you're working with.</span></span>

```powershell
$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="b7386-121">É necessário muitas vezes um loop, como `foreach` ou `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="b7386-121">Many times a loop such as `foreach` or `ForEach-Object` is necessary.</span></span> <span data-ttu-id="b7386-122">Caso contrário, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b7386-122">Otherwise you'll receive an error message.</span></span>

```powershell
Get-ADComputer -Identity 'DC01', 'WEB01'
```

```Output
Get-ADComputer : Cannot convert 'System.Object[]' to the type
'Microsoft.ActiveDirectory.Management.ADComputer' required by parameter 'Identity'.
Specified method is not supported.
At line:1 char:26
+ Get-ADComputer -Identity 'DC01', 'WEB01'
+                          ```````````````
    + CategoryInfo          : InvalidArgument: (:) [Get-ADComputer], ParameterBindingExc
   eption
    + FullyQualifiedErrorId : CannotConvertArgument,Microsoft.ActiveDirectory.Management
   .Commands.GetADComputer
```

<span data-ttu-id="b7386-123">Em outras ocasiões, você pode obter os mesmos resultados eliminando o loop por completo.</span><span class="sxs-lookup"><span data-stu-id="b7386-123">Other times, you can get the same results while eliminating the loop altogether.</span></span> <span data-ttu-id="b7386-124">Consulte a ajuda do cmdlet para entender as opções.</span><span class="sxs-lookup"><span data-stu-id="b7386-124">Consult the cmdlet help to understand your options.</span></span>

```powershell
'DC01', 'WEB01' | Get-ADComputer
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="b7386-125">Como você pode ver nos exemplos anteriores, o parâmetro **Identity** para `Get-ADComputer` aceita apenas um só valor quando fornecido por meio da entrada de parâmetro, mas permite vários itens quando a entrada é fornecida por meio da entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="b7386-125">As you can see in the previous examples, the **Identity** parameter for `Get-ADComputer` only accepts a single value when provided via parameter input, but it allows for multiple items when the input is provided via pipeline input.</span></span>

### <a name="for"></a><span data-ttu-id="b7386-126">For (para)</span><span class="sxs-lookup"><span data-stu-id="b7386-126">For</span></span>

<span data-ttu-id="b7386-127">Um loop `for` itera enquanto uma condição especificada é verdadeira.</span><span class="sxs-lookup"><span data-stu-id="b7386-127">A `for` loop iterates while a specified condition is true.</span></span> <span data-ttu-id="b7386-128">O loop `for` não é algo que utilizo com frequência, mas ele tem usos próprios.</span><span class="sxs-lookup"><span data-stu-id="b7386-128">The `for` loop is not something that I use often, but it does have its uses.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

```Output
Sleeping for 1 seconds
Sleeping for 2 seconds
Sleeping for 3 seconds
Sleeping for 4 seconds
```

<span data-ttu-id="b7386-129">No exemplo anterior, o loop vai iterar quatro vezes começando com o número um e continuar, desde que a variável do contador `$i` seja menor que 5.</span><span class="sxs-lookup"><span data-stu-id="b7386-129">In the previous example, the loop will iterate four times by starting off with the number one and continue as long as the counter variable `$i` is less than 5.</span></span> <span data-ttu-id="b7386-130">Ele será suspenso por um total de dez segundos.</span><span class="sxs-lookup"><span data-stu-id="b7386-130">It will sleep for a total of 10 seconds.</span></span>

### <a name="do"></a><span data-ttu-id="b7386-131">O que fazer</span><span class="sxs-lookup"><span data-stu-id="b7386-131">Do</span></span>

<span data-ttu-id="b7386-132">Há dois loops `do` diferentes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7386-132">There are two different `do` loops in PowerShell.</span></span> <span data-ttu-id="b7386-133">`Do Until` é executado enquanto a condição especificada é falsa.</span><span class="sxs-lookup"><span data-stu-id="b7386-133">`Do Until` runs while the specified condition is false.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  }
  elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
until ($guess -eq $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
```

<span data-ttu-id="b7386-134">O exemplo anterior é um jogo de números que continua até que o valor adivinhado seja igual ao mesmo número gerado pelo cmdlet `Get-Random`.</span><span class="sxs-lookup"><span data-stu-id="b7386-134">The previous example is a numbers game that continues until the value you guess equals the same number that the `Get-Random` cmdlet generated.</span></span>

<span data-ttu-id="b7386-135">`Do While` é justamente o oposto.</span><span class="sxs-lookup"><span data-stu-id="b7386-135">`Do While` is just the opposite.</span></span> <span data-ttu-id="b7386-136">Ele é executado desde que a condição especificada seja avaliada como verdadeira.</span><span class="sxs-lookup"><span data-stu-id="b7386-136">It runs as long as the specified condition evaluates to true.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  } elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
while ($guess -ne $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
Too low!
What's your guess?: 4
```

<span data-ttu-id="b7386-137">Os mesmos resultados são obtidos com um loop `Do While`, revertendo a condição de teste para não é igual a.</span><span class="sxs-lookup"><span data-stu-id="b7386-137">The same results are achieved with a `Do While` loop by reversing the test condition to not equals.</span></span>

<span data-ttu-id="b7386-138">Os loops `Do` sempre são executados pelo menos uma vez porque a condição é avaliada no final do loop.</span><span class="sxs-lookup"><span data-stu-id="b7386-138">`Do` loops always run at least once because the condition is evaluated at the end of the loop.</span></span>

### <a name="while"></a><span data-ttu-id="b7386-139">While</span><span class="sxs-lookup"><span data-stu-id="b7386-139">While</span></span>

<span data-ttu-id="b7386-140">De modo semelhante ao loop `Do While`, um loop `While` é executado, desde que a condição especificada seja verdadeira.</span><span class="sxs-lookup"><span data-stu-id="b7386-140">Similar to the `Do While` loop, a `While` loop runs as long as the specified condition is true.</span></span> <span data-ttu-id="b7386-141">No entanto, a diferença é que um loop `While` avalia a condição na parte superior do loop antes da execução de qualquer código.</span><span class="sxs-lookup"><span data-stu-id="b7386-141">The difference however, is that a `While` loop evaluates the condition at the top of the loop before any code is run.</span></span> <span data-ttu-id="b7386-142">Portanto, ele não é executado se a condição é avaliada como falsa.</span><span class="sxs-lookup"><span data-stu-id="b7386-142">So it doesn't run if the condition evaluates to false.</span></span>

```powershell
$date = Get-Date -Date 'November 22'
while ($date.DayOfWeek -ne 'Thursday') {
  $date = $date.AddDays(1)
}
Write-Output $date
```

```Output
Thursday, November 23, 2017 12:00:00 AM
```

<span data-ttu-id="b7386-143">O exemplo anterior calcula quando será o Dia de Ação de Graças nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="b7386-143">The previous example calculates what day Thanksgiving Day is on in the United States.</span></span> <span data-ttu-id="b7386-144">Ele sempre cai na quarta quinta-feira de novembro.</span><span class="sxs-lookup"><span data-stu-id="b7386-144">It's always on the fourth Thursday of November.</span></span> <span data-ttu-id="b7386-145">Portanto, o loop começa com o dia 22 de novembro e adiciona um dia enquanto o dia da semana não é igual a quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="b7386-145">So the loop starts with the 22nd day of November and adds a day while the day of the week isn't equal to Thursday.</span></span> <span data-ttu-id="b7386-146">Se o dia 22 for uma quinta-feira, o loop não será executado.</span><span class="sxs-lookup"><span data-stu-id="b7386-146">If the 22nd is a Thursday, the loop doesn't run at all.</span></span>

## <a name="break-continue-and-return"></a><span data-ttu-id="b7386-147">Interromper, continuar e retornar</span><span class="sxs-lookup"><span data-stu-id="b7386-147">Break, Continue, and Return</span></span>

<span data-ttu-id="b7386-148">`Break` foi projetado para interromper um loop.</span><span class="sxs-lookup"><span data-stu-id="b7386-148">`Break` is designed to break out of a loop.</span></span> <span data-ttu-id="b7386-149">Ele também é comumente usado com a instrução `switch`.</span><span class="sxs-lookup"><span data-stu-id="b7386-149">It's also commonly used with the `switch` statement.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
  break
}
```

```Output
Sleeping for 1 seconds
```

<span data-ttu-id="b7386-150">A instrução `break` mostrada no exemplo anterior faz com que o loop saia na primeira iteração.</span><span class="sxs-lookup"><span data-stu-id="b7386-150">The `break` statement shown in the previous example causes the loop to exit on the first iteration.</span></span>

<span data-ttu-id="b7386-151">Continue foi projetado para ir para a próxima iteração de um loop.</span><span class="sxs-lookup"><span data-stu-id="b7386-151">Continue is designed to skip to the next iteration of a loop.</span></span>

```powershell
while ($i -lt 5) {
  $i += 1
  if ($i -eq 3) {
    continue
  }
  Write-Output $i
}
```

```Output
1
2
4
5
```

<span data-ttu-id="b7386-152">O exemplo anterior produzirá os números 1, 2, 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="b7386-152">The previous example will output the numbers 1, 2, 4, and 5.</span></span> <span data-ttu-id="b7386-153">Ele ignora o número 3 e continua com a próxima iteração do loop.</span><span class="sxs-lookup"><span data-stu-id="b7386-153">It skips number 3 and continues with the next iteration of the loop.</span></span> <span data-ttu-id="b7386-154">De modo semelhante ao `break`, `continue` é interrompido do loop, exceto apenas para a iteração atual.</span><span class="sxs-lookup"><span data-stu-id="b7386-154">Similar to `break`, `continue` breaks out of the loop except only for the current iteration.</span></span> <span data-ttu-id="b7386-155">A execução continua com a próxima iteração em vez de interromper o loop e parar.</span><span class="sxs-lookup"><span data-stu-id="b7386-155">Execution continues with the next iteration instead of breaking out of the loop and stopping.</span></span>

<span data-ttu-id="b7386-156">Return foi projetado para sair do escopo existente.</span><span class="sxs-lookup"><span data-stu-id="b7386-156">Return is designed to exit out of the existing scope.</span></span>

```powershell
$number = 1..10
foreach ($n in $number) {
  if ($n -ge 4) {
    Return $n
  }
}
```

```Output
4
```

<span data-ttu-id="b7386-157">Observe que, no exemplo anterior, o retorno produz o primeiro resultado e, em seguida, sai do loop.</span><span class="sxs-lookup"><span data-stu-id="b7386-157">Notice that in the previous example, return outputs the first result and then exists out of the loop.</span></span> <span data-ttu-id="b7386-158">Encontre uma explicação mais completa da instrução result em um dos meus artigos de blog: ["A palavra-chave return do PowerShell"][].</span><span class="sxs-lookup"><span data-stu-id="b7386-158">A more thorough explanation of the result statement can be found in one of my blog articles: ["The PowerShell return keyword"][].</span></span>

## <a name="summary"></a><span data-ttu-id="b7386-159">Resumo</span><span class="sxs-lookup"><span data-stu-id="b7386-159">Summary</span></span>

<span data-ttu-id="b7386-160">Neste capítulo, você aprendeu mais sobre os diferentes tipos de loops existentes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7386-160">In this chapter, you've learned about the different types of loops that exist in PowerShell.</span></span>

## <a name="review"></a><span data-ttu-id="b7386-161">Revisão</span><span class="sxs-lookup"><span data-stu-id="b7386-161">Review</span></span>

1. <span data-ttu-id="b7386-162">Qual é a diferença entre o cmdlet `ForEach-Object` e o constructo de script foreach?</span><span class="sxs-lookup"><span data-stu-id="b7386-162">What is the difference in the `ForEach-Object` cmdlet and the foreach scripting construct?</span></span>
1. <span data-ttu-id="b7386-163">Qual é a principal vantagem de usar um loop While em vez de um loop Do While ou Do Until?</span><span class="sxs-lookup"><span data-stu-id="b7386-163">What is the primary advantage of using a While loop instead of a Do While or Do Until loop.</span></span>
1. <span data-ttu-id="b7386-164">Qual é diferença entre as instruções break e continue?</span><span class="sxs-lookup"><span data-stu-id="b7386-164">How do the break and continue statements differ?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="b7386-165">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="b7386-165">Recommended Reading</span></span>

- <span data-ttu-id="b7386-166">[ForEach-Object][]</span><span class="sxs-lookup"><span data-stu-id="b7386-166">[ForEach-Object][]</span></span>
- <span data-ttu-id="b7386-167">[about_ForEach][]</span><span class="sxs-lookup"><span data-stu-id="b7386-167">[about_ForEach][]</span></span>
- <span data-ttu-id="b7386-168">[about_For][]</span><span class="sxs-lookup"><span data-stu-id="b7386-168">[about_For][]</span></span>
- <span data-ttu-id="b7386-169">[about_Do][]</span><span class="sxs-lookup"><span data-stu-id="b7386-169">[about_Do][]</span></span>
- <span data-ttu-id="b7386-170">[about_While][]</span><span class="sxs-lookup"><span data-stu-id="b7386-170">[about_While][]</span></span>
- <span data-ttu-id="b7386-171">[about_Break][]</span><span class="sxs-lookup"><span data-stu-id="b7386-171">[about_Break][]</span></span>
- <span data-ttu-id="b7386-172">[about_Continue][]</span><span class="sxs-lookup"><span data-stu-id="b7386-172">[about_Continue][]</span></span>
- <span data-ttu-id="b7386-173">[about_Return][]</span><span class="sxs-lookup"><span data-stu-id="b7386-173">[about_Return][]</span></span>

<!-- link references -->
[ForEach-Object]: /powershell/module/microsoft.powershell.core/foreach-object
[about_ForEach]: /powershell/module/microsoft.powershell.core/about/about_foreach
[about_For]: /powershell/module/microsoft.powershell.core/about/about_for
[about_Do]: /powershell/module/microsoft.powershell.core/about/about_do
[about_While]: /powershell/module/microsoft.powershell.core/about/about_while
[about_Break]: /powershell/module/microsoft.powershell.core/about/about_break
[about_Continue]: /powershell/module/microsoft.powershell.core/about/about_continue
[about_Return]: /powershell/module/microsoft.powershell.core/about/about_return
["A palavra-chave return do PowerShell"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
["The PowerShell return keyword"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
