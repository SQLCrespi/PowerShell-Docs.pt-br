---
title: Tudo o que você queria saber sobre a substituição de variáveis em cadeias de caracteres
description: Há diversas maneiras de usar variáveis em cadeias de caracteres para criar textos formatados.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301311"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a><span data-ttu-id="7a9ff-103">Tudo o que você queria saber sobre a substituição de variáveis em cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="7a9ff-103">Everything you wanted to know about variable substitution in strings</span></span>

<span data-ttu-id="7a9ff-104">Há diversas maneiras de usar variáveis em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-104">There are many ways to use variables in strings.</span></span> <span data-ttu-id="7a9ff-105">Estou chamando isso de substituição de variáveis, mas me refiro a qualquer ocasião em que você queira formatar uma cadeia de caracteres para incluir valores de variáveis.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-105">I'm calling this variable substitution but I'm referring to any time you want to format a string to include values from variables.</span></span> <span data-ttu-id="7a9ff-106">Isso é algo que explico com frequência para novos criadores de scripts.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-106">This is something that I often find myself explaining to new scripters.</span></span>

> [!NOTE]
> <span data-ttu-id="7a9ff-107">A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="7a9ff-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="7a9ff-108">A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="7a9ff-109">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="7a9ff-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="concatenation"></a><span data-ttu-id="7a9ff-110">Concatenação</span><span class="sxs-lookup"><span data-stu-id="7a9ff-110">Concatenation</span></span>

<span data-ttu-id="7a9ff-111">A primeira classe de métodos pode ser chamada de concatenação.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-111">The first class of methods can be referred to as concatenation.</span></span> <span data-ttu-id="7a9ff-112">Basicamente, ela reúne várias cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-112">It's basically taking several strings and joining them together.</span></span> <span data-ttu-id="7a9ff-113">Há um longo histórico de uso da concatenação para criar cadeias de caracteres formatadas.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-113">There's a long history of using concatenation to build formatted strings.</span></span>

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

<span data-ttu-id="7a9ff-114">A concatenação funciona bem quando há apenas alguns valores a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-114">Concatenation works out OK when there are only a few values to add.</span></span> <span data-ttu-id="7a9ff-115">Porém, isso logo pode ficar complicado.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-115">But this can get complicated quickly.</span></span>

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

<span data-ttu-id="7a9ff-116">Este exemplo simples já está ficando mais difícil de ler.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-116">This simple example is already getting harder to read.</span></span>

## <a name="variable-substitution"></a><span data-ttu-id="7a9ff-117">Substituição de variáveis</span><span class="sxs-lookup"><span data-stu-id="7a9ff-117">Variable substitution</span></span>

<span data-ttu-id="7a9ff-118">O PowerShell tem uma opção mais fácil.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-118">PowerShell has another option that is easier.</span></span> <span data-ttu-id="7a9ff-119">Você pode especificar variáveis diretamente nas cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-119">You can specify your variables directly in the strings.</span></span>

```powershell
$message = "Hello, $first $last."
```

<span data-ttu-id="7a9ff-120">O tipo de aspas usado em volta da cadeia de caracteres faz diferença.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-120">The type of quotes you use around the string makes a difference.</span></span> <span data-ttu-id="7a9ff-121">Uma cadeia de caracteres entre aspas duplas permite a substituição, mas uma cadeia de caracteres entre aspas simples não.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-121">A double quoted string allows the substitution but a single quoted string doesn't.</span></span> <span data-ttu-id="7a9ff-122">Há ocasiões em que você deseja uma ou outra para ter uma opção.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-122">There are times you want one or the other so you have an option.</span></span>

## <a name="command-substitution"></a><span data-ttu-id="7a9ff-123">Substituição de comando</span><span class="sxs-lookup"><span data-stu-id="7a9ff-123">Command substitution</span></span>

<span data-ttu-id="7a9ff-124">Tudo fica um pouco complicado quando você tenta colocar os valores de propriedades em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-124">Things get a little tricky when you start trying to get the values of properties into a string.</span></span> <span data-ttu-id="7a9ff-125">É aí que muitos novatos se confundem.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-125">This is where many new people get tripped up.</span></span> <span data-ttu-id="7a9ff-126">Primeiro, deixe-me mostrar o que eles acham que deve funcionar (e, à primeira vista, quase parece que deveria funcionar).</span><span class="sxs-lookup"><span data-stu-id="7a9ff-126">First let me show you what they think should work (and at face value almost looks like it should).</span></span>

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

<span data-ttu-id="7a9ff-127">Você esperaria obter `CreationTime` de `$directory`, mas obtém o valor `Time: c:\windows.CreationTime`.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-127">You would be expecting to get the `CreationTime` off of the `$directory`, but instead you get this `Time: c:\windows.CreationTime` as your value.</span></span> <span data-ttu-id="7a9ff-128">O motivo é que esse tipo de substituição vê apenas a variável base.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-128">The reason is that this type of substitution only sees the base variable.</span></span> <span data-ttu-id="7a9ff-129">Ele considera o ponto como parte da cadeia de caracteres. Por isso, para de resolver o valor mais profundamente.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-129">It considers the period as part of the string so it stops resolving the value any deeper.</span></span>

<span data-ttu-id="7a9ff-130">Assim, esse objeto fornece uma cadeia de caracteres como um valor padrão quando colocado em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-130">It just so happens that this object gives a string as a default value when placed into a string.</span></span>
<span data-ttu-id="7a9ff-131">Alguns objetos fornecem o nome do tipo, como `System.Collections.Hashtable`.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-131">Some objects give you the type name instead like `System.Collections.Hashtable`.</span></span> <span data-ttu-id="7a9ff-132">Apenas algo a ser observado.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-132">Just something to watch for.</span></span>

<span data-ttu-id="7a9ff-133">O PowerShell permite que você faça a execução do comando dentro da cadeia de caracteres com uma sintaxe especial.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-133">PowerShell allows you to do command execution inside the string with a special syntax.</span></span> <span data-ttu-id="7a9ff-134">Isso nos permite obter as propriedades desses objetos e executar qualquer outro comando para obter um valor.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-134">This allows us to get the properties of these objects and run any other command to get a value.</span></span>

```powershell
$message = "Time: $($directory.CreationTime)"
```

<span data-ttu-id="7a9ff-135">Isso funciona muito bem para algumas situações, mas poderá ficar tão estranho quanto a concatenação se você tiver apenas algumas variáveis.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-135">This works great for some situations but it can get just as crazy as concatenation if you have just a few variables.</span></span>

### <a name="command-execution"></a><span data-ttu-id="7a9ff-136">Execução do comando</span><span class="sxs-lookup"><span data-stu-id="7a9ff-136">Command execution</span></span>

<span data-ttu-id="7a9ff-137">Você pode executar comandos dentro de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-137">You can run commands inside a string.</span></span> <span data-ttu-id="7a9ff-138">Embora eu tenha essa opção, não gosto dela.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-138">Even though I have this option, I don't like it.</span></span> <span data-ttu-id="7a9ff-139">Logo tudo fica confuso e difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-139">It gets cluttered quickly and hard to debug.</span></span> <span data-ttu-id="7a9ff-140">Executo o comando e o salvo em uma variável ou uso uma cadeia de caracteres de formato.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-140">I either run the command and save to a variable or use a format string.</span></span>

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a><span data-ttu-id="7a9ff-141">Cadeia de formato</span><span class="sxs-lookup"><span data-stu-id="7a9ff-141">Format string</span></span>

<span data-ttu-id="7a9ff-142">O .NET tem um modo de formatar cadeias de caracteres com o qual acho muito fácil trabalhar.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-142">.NET has a way to format strings that I find fairly easy to work with.</span></span> <span data-ttu-id="7a9ff-143">Mostrarei o método estático para isso, antes de mostrar o atalho do PowerShell para a mesma ação.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-143">First let me show you the static method for it before I show you the PowerShell shortcut to do the same thing.</span></span>

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

<span data-ttu-id="7a9ff-144">Aqui, a cadeia de caracteres é analisada para os tokens `{0}` e `{1}`. Em seguida, ela usa esse número para escolher entre os valores fornecidos.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-144">What is happening here is that the string is parsed for the tokens `{0}` and `{1}`, then it uses that number to pick from the values provided.</span></span> <span data-ttu-id="7a9ff-145">Se você quiser repetir um valor em algum lugar na cadeia de caracteres, poderá reutilizar esse número de valores.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-145">If you want to repeat one value some place in the string, you can reuse that values number.</span></span>

<span data-ttu-id="7a9ff-146">Quanto mais complicada for a cadeia de caracteres, mais você aproveitará essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-146">The more complicated the string gets, the more value you get out of this approach.</span></span>

### <a name="format-values-as-arrays"></a><span data-ttu-id="7a9ff-147">Formatar valores como matrizes</span><span class="sxs-lookup"><span data-stu-id="7a9ff-147">Format values as arrays</span></span>

<span data-ttu-id="7a9ff-148">Se a linha de formato ficar muito longa, você poderá posicionar os valores em uma matriz primeiro.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-148">If your format line gets too long, you can place your values into an array first.</span></span>

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

<span data-ttu-id="7a9ff-149">Não é nivelamento, pois estou passando a matriz inteira, mas é semelhante.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-149">This is not splatting because I'm passing the whole array in, but the idea is similar.</span></span>

## <a name="advanced-formatting"></a><span data-ttu-id="7a9ff-150">Formatação avançada</span><span class="sxs-lookup"><span data-stu-id="7a9ff-150">Advanced formatting</span></span>

<span data-ttu-id="7a9ff-151">Eu chamei estes intencionalmente como provenientes do .NET porque há muitas opções de formatação já [documentadas][].</span><span class="sxs-lookup"><span data-stu-id="7a9ff-151">I intentionally called these out as coming from .NET because there are lots of formatting options already well [documented][] on it.</span></span> <span data-ttu-id="7a9ff-152">Há maneiras internas de formatar vários tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-152">There are built in ways to format various data types.</span></span>

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

<span data-ttu-id="7a9ff-153">Não falarei sobre elas, mas queria apenas informar de que se trata de um mecanismo de formatação muito eficiente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-153">I'm not going to go into them but I just wanted to let you know that this is a very powerful formatting engine if you need it.</span></span>

## <a name="joining-strings"></a><span data-ttu-id="7a9ff-154">Junção de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="7a9ff-154">Joining strings</span></span>

<span data-ttu-id="7a9ff-155">Às vezes, você quer concatenar uma lista de valores.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-155">Sometimes you actually do want to concatenate a list of values together.</span></span> <span data-ttu-id="7a9ff-156">Há um operador `-join` que pode fazer isso para você.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-156">There's a `-join` operator that can do that for you.</span></span> <span data-ttu-id="7a9ff-157">Ele até mesmo permite que você especifique um caractere para unir as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-157">It even lets you specify a character to join between the strings.</span></span>

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

<span data-ttu-id="7a9ff-158">Se você quiser usar `-join` para unir algumas cadeias de caracteres sem um separador, precisará especificar uma cadeia de caracteres vazia `''`.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-158">If you want to `-join` some strings without a separator, you need to specify an empty string `''`.</span></span>
<span data-ttu-id="7a9ff-159">Mas se isso for tudo de que você precisa, há uma opção mais rápida.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-159">But if that is all you need, there's a faster option.</span></span>

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

<span data-ttu-id="7a9ff-160">Também vale a pena destacar que é possível usar `-split` para dividir cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-160">It's also worth pointing out that you can also `-split` strings too.</span></span>

## <a name="join-path"></a><span data-ttu-id="7a9ff-161">Join-Path</span><span class="sxs-lookup"><span data-stu-id="7a9ff-161">Join-Path</span></span>

<span data-ttu-id="7a9ff-162">Geralmente é ignorado, mas é um ótimo cmdlet para criar um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-162">This is often overlooked but a great cmdlet for building a file path.</span></span>

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

<span data-ttu-id="7a9ff-163">A grande vantagem é que ele usa as barras invertidas corretamente ao reunir os valores.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-163">The great thing about this is it works out the backslashes correctly when it puts the values together.</span></span> <span data-ttu-id="7a9ff-164">Isso é especialmente importante se você está usando valores de usuários ou de arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-164">This is especially important if you are taking values from users or config files.</span></span>

<span data-ttu-id="7a9ff-165">Além disso, funciona bem com `Split-Path` e `Test-Path`.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-165">This also goes well with `Split-Path` and `Test-Path`.</span></span> <span data-ttu-id="7a9ff-166">Também abordei isso em minha postagem sobre [ler e salvar em arquivos][].</span><span class="sxs-lookup"><span data-stu-id="7a9ff-166">I also cover these in my post about [reading and saving to files][].</span></span>

## <a name="strings-are-arrays"></a><span data-ttu-id="7a9ff-167">Cadeia de caracteres são matrizes</span><span class="sxs-lookup"><span data-stu-id="7a9ff-167">Strings are arrays</span></span>

<span data-ttu-id="7a9ff-168">Preciso falar sobre a adição de cadeias de caracteres antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-168">I do need to mention adding strings here before I go on.</span></span> <span data-ttu-id="7a9ff-169">Lembre-se de que uma cadeia de caracteres é apenas uma matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-169">Remember that a string is just an array of characters.</span></span> <span data-ttu-id="7a9ff-170">Quando você adiciona várias cadeias de caracteres juntas, uma nova matriz é criada a cada vez.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-170">When you add multiple strings together, a new array is created each time.</span></span>

<span data-ttu-id="7a9ff-171">Veja este exemplo:</span><span class="sxs-lookup"><span data-stu-id="7a9ff-171">Look at this example:</span></span>

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

<span data-ttu-id="7a9ff-172">Ele parece muito básico, mas o que você não vê é que sempre que uma cadeia de caracteres é adicionada a `$message`, uma cadeia de caracteres totalmente nova é criada.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-172">It looks very basic but what you don't see is that each time a string is added to `$message` that a whole new string is created.</span></span> <span data-ttu-id="7a9ff-173">A memória é alocada, os dados são copiados e a antiga é descartada.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-173">Memory gets allocated, data gets copied and the old one is discarded.</span></span>
<span data-ttu-id="7a9ff-174">Não é muito importante quando isso é feito apenas algumas vezes, mas um loop como esse evidencia o problema.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-174">Not a big deal when it's only done a few times, but a loop like this would really expose the issue.</span></span>

### <a name="stringbuilder"></a><span data-ttu-id="7a9ff-175">StringBuilder</span><span class="sxs-lookup"><span data-stu-id="7a9ff-175">StringBuilder</span></span>

<span data-ttu-id="7a9ff-176">O StringBuilder também é muito popular para a criação de cadeias de caracteres grandes com base em várias cadeias de caracteres menores.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-176">StringBuilder is also very popular for building large strings from lots of smaller strings.</span></span> <span data-ttu-id="7a9ff-177">O motivo disso é que ele apenas coleta todas as cadeias de caracteres adicionadas a ele e concatena todas elas no final quando você recupera o valor.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-177">The reason why is because it just collects all the strings you add to it and only concatenates all of them at the end when you retrieve the value.</span></span>

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

<span data-ttu-id="7a9ff-178">Novamente, isso é algo que estou buscando no .NET.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-178">Again, this is something that I'm reaching out to .NET for.</span></span> <span data-ttu-id="7a9ff-179">Não uso mais com frequência, mas é bom saber que está lá.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-179">I don't use it often anymore but it's good to know it's there.</span></span>

## <a name="delineation-with-braces"></a><span data-ttu-id="7a9ff-180">Delineação com chaves</span><span class="sxs-lookup"><span data-stu-id="7a9ff-180">Delineation with braces</span></span>

<span data-ttu-id="7a9ff-181">A delineação com chaves é usada para concatenação de sufixo dentro da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-181">This is used for suffix concatenation within the string.</span></span> <span data-ttu-id="7a9ff-182">Às vezes, sua variável não tem um limite de palavra claro.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-182">Sometimes your variable doesn't have a clean word boundary.</span></span>

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

<span data-ttu-id="7a9ff-183">Agradeço a [/u/real_parbold][] por isso.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-183">Thank you [/u/real_parbold][] for that one.</span></span>

<span data-ttu-id="7a9ff-184">Aqui está uma alternativa para essa abordagem:</span><span class="sxs-lookup"><span data-stu-id="7a9ff-184">Here is an alternate to this approach:</span></span>

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

<span data-ttu-id="7a9ff-185">Pessoalmente, uso a cadeia de caracteres de formato para isso, mas é bom saber, caso você encontre isso na prática.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-185">I personally use format string for this, but this is good to know incase you see it in the wild.</span></span>

## <a name="find-and-replace-tokens"></a><span data-ttu-id="7a9ff-186">Localização e substituição de tokens</span><span class="sxs-lookup"><span data-stu-id="7a9ff-186">Find and replace tokens</span></span>

<span data-ttu-id="7a9ff-187">Embora a maioria desses recursos limite a necessidade de distribuir sua própria solução, há ocasiões em que você pode ter arquivos de modelo grandes em que deseja substituir cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-187">While most of these features limit your need to roll your own solution, there are times where you may have large template files where you want to replace strings inside.</span></span>

<span data-ttu-id="7a9ff-188">Vamos supor que você tenha recebido um modelo de um arquivo com muito texto.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-188">Let us assume you pulled in a template from a file that has a lot of text.</span></span>

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

<span data-ttu-id="7a9ff-189">Pode ser necessário substituir muitos tokens.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-189">You may have lots of tokens to replace.</span></span> <span data-ttu-id="7a9ff-190">O truque é usar um token muito distinto que seja fácil de localizar e substituir.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-190">The trick is to use a very distinct token that is easy to find and replace.</span></span> <span data-ttu-id="7a9ff-191">Costumo usar um caractere especial em ambas as extremidades para que seja mais fácil diferenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-191">I tend to use a special character at both ends to help distinguish it.</span></span>

<span data-ttu-id="7a9ff-192">Recentemente, descobri uma nova abordagem.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-192">I recently found a new way to approach this.</span></span> <span data-ttu-id="7a9ff-193">Decidi deixar esta seção aqui porque esse é um padrão comumente usado.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-193">I decided to leave this section in here because this is a pattern that is commonly used.</span></span>

### <a name="replace-multiple-tokens"></a><span data-ttu-id="7a9ff-194">Substituir vários tokens</span><span class="sxs-lookup"><span data-stu-id="7a9ff-194">Replace multiple tokens</span></span>

<span data-ttu-id="7a9ff-195">Quando tenho uma lista de tokens que preciso substituir, uso uma abordagem mais genérica.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-195">When I have a list of tokens that I need to replace, I take a more generic approach.</span></span> <span data-ttu-id="7a9ff-196">Coloco-os em uma tabela de hash e realizo uma iteração para fazer a substituição.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-196">I would place them in a hashtable and iterate over them to do the replace.</span></span>

```powershell
$tokenList = @{
    Full_Name = 'Kevin Marquette'
    Location = 'Orange County'
    State = 'CA'
}

$letter = Get-Content -Path TemplateLetter.txt -RAW
foreach( $token in $tokenList.GetEnumerator() )
{
    $pattern = '#{0}#' -f $token.key
    $letter = $letter -replace $pattern, $token.Value
}
```

<span data-ttu-id="7a9ff-197">Esses tokens podem ser carregados de arquivos JSON ou CSV se necessário.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-197">Those tokens could be loaded from JSON or CSV if needed.</span></span>

### <a name="executioncontext-expandstring"></a><span data-ttu-id="7a9ff-198">ExecutionContext ExpandString</span><span class="sxs-lookup"><span data-stu-id="7a9ff-198">ExecutionContext ExpandString</span></span>

<span data-ttu-id="7a9ff-199">Há uma forma inteligente de definir uma cadeia de caracteres de substituição com aspas simples e expandir as variáveis posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-199">There's a clever way to define a substitution string with single quotes and expand the variables later.</span></span> <span data-ttu-id="7a9ff-200">Veja este exemplo:</span><span class="sxs-lookup"><span data-stu-id="7a9ff-200">Look at this example:</span></span>

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

<span data-ttu-id="7a9ff-201">A chamada para `.InvokeCommand.ExpandString` no contexto de execução atual usa as variáveis no escopo atual para substituição.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-201">The call to `.InvokeCommand.ExpandString` on the current execution context uses the variables in the current scope for substitution.</span></span> <span data-ttu-id="7a9ff-202">O importante aqui é que `$message` pode ser definido muito cedo, antes que as variáveis existam.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-202">The key thing here is that the `$message` can be defined very early before the variables even exist.</span></span>

<span data-ttu-id="7a9ff-203">Se entrarmos em mais detalhes, poderemos executar essa substituição várias vezes com valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-203">If we expand on that just a little bit, we can perform this substitution over and over wih different values.</span></span>

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

<span data-ttu-id="7a9ff-204">Para continuar com essa mesma ideia, você pode importar um modelo de email grande de um arquivo de texto para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-204">To keep going on this idea; you could be importing a large email template from a text file to do this.</span></span> <span data-ttu-id="7a9ff-205">Preciso agradecer a [Mark Kraus][] por essa [sugestão][].</span><span class="sxs-lookup"><span data-stu-id="7a9ff-205">I have to thank [Mark Kraus][] for this [suggestion][].</span></span>

## <a name="whatever-works-the-best-for-you"></a><span data-ttu-id="7a9ff-206">O que for mais adequado para você</span><span class="sxs-lookup"><span data-stu-id="7a9ff-206">Whatever works the best for you</span></span>

<span data-ttu-id="7a9ff-207">Sou um fã da abordagem de cadeia de caracteres de formato.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-207">I'm a fan of the format string approach.</span></span> <span data-ttu-id="7a9ff-208">Eu definitivamente faço isso com as cadeias de caracteres mais complicadas ou quando há muitas variáveis.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-208">I definitely do this with the more complicated strings or if there are multiple variables.</span></span> <span data-ttu-id="7a9ff-209">Em algo muito curto, posso usar qualquer uma das abordagens.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-209">On anything that is very short, I may use any one of these.</span></span>

## <a name="anything-else"></a><span data-ttu-id="7a9ff-210">Algo mais?</span><span class="sxs-lookup"><span data-stu-id="7a9ff-210">Anything else?</span></span>

<span data-ttu-id="7a9ff-211">Abordei muitos aspectos básicos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-211">I covered a lot of ground on this one.</span></span> <span data-ttu-id="7a9ff-212">Espero que você tenha aprendido algo novo.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-212">My hope is that you walk away learning something new.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[original version]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[sugestão]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[suggestion]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[ler e salvar em arquivos]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[reading and saving to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[documentadas]: /dotnet/api/system.string.format#overloads
[documented]: /dotnet/api/system.string.format#overloads
