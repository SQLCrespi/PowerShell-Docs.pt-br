---
title: Tudo o que você sempre quis saber sobre a instrução switch
description: A instrução switch no PowerShell oferece recursos que não são encontrados em outras linguagens.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 685a5691599408a0d54ca99bf383bcd7702322a6
ms.sourcegitcommit: 0afff6edbe560e88372dd5f1cdf51d77f9349972
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86469711"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a><span data-ttu-id="5963a-103">Tudo o que você sempre quis saber sobre a instrução switch</span><span class="sxs-lookup"><span data-stu-id="5963a-103">Everything you ever wanted to know about the switch statement</span></span>

<span data-ttu-id="5963a-104">Como muitas outras linguagens, o PowerShell tem comandos para controlar o fluxo de execução dentro dos seus scripts.</span><span class="sxs-lookup"><span data-stu-id="5963a-104">Like many other languages, PowerShell has commands for controlling the flow of execution within your scripts.</span></span> <span data-ttu-id="5963a-105">Uma dessas instruções é a instrução [switch][] e, no PowerShell, ela oferece recursos que não são encontrados em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="5963a-105">One of those statements is the [switch][] statement and in PowerShell, it offers features that aren't found in other languages.</span></span> <span data-ttu-id="5963a-106">Hoje, vamos nos aprofundar sobre como trabalhar com o `switch` do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5963a-106">Today, we take a deep dive into working with the PowerShell `switch`.</span></span>

> [!NOTE]
> <span data-ttu-id="5963a-107">A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="5963a-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="5963a-108">A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="5963a-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="5963a-109">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="5963a-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="5963a-110">A instrução `if`</span><span class="sxs-lookup"><span data-stu-id="5963a-110">The `if` statement</span></span>

<span data-ttu-id="5963a-111">Uma das primeiras instruções que você aprende é a instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="5963a-111">One of the first statements that you learn is the `if` statement.</span></span> <span data-ttu-id="5963a-112">Ela permitirá que você execute um bloco de script se uma instrução for `$true`.</span><span class="sxs-lookup"><span data-stu-id="5963a-112">It lets you execute a script block if a statement is `$true`.</span></span>

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

<span data-ttu-id="5963a-113">Você pode ter uma lógica muito mais complicada usando instruções `elseif` e `else`.</span><span class="sxs-lookup"><span data-stu-id="5963a-113">You can have much more complicated logic by using `elseif` and `else` statements.</span></span> <span data-ttu-id="5963a-114">A seguir está um exemplo no qual tenho um valor numérico para o dia da semana e quero obter o nome como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5963a-114">Here is an example where I have a numeric value for day of the week and I want to get the name as a string.</span></span>

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

<span data-ttu-id="5963a-115">Esse é um padrão comum e há várias maneiras de lidar com isso.</span><span class="sxs-lookup"><span data-stu-id="5963a-115">It turns out that this is a common pattern and there are many ways to deal with this.</span></span> <span data-ttu-id="5963a-116">Uma delas é com um `switch`.</span><span class="sxs-lookup"><span data-stu-id="5963a-116">One of them is with a `switch`.</span></span>

## <a name="switch-statement"></a><span data-ttu-id="5963a-117">Instrução switch</span><span class="sxs-lookup"><span data-stu-id="5963a-117">Switch statement</span></span>

<span data-ttu-id="5963a-118">A instrução `switch` permite que você forneça uma variável e uma lista de valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="5963a-118">The `switch` statement allows you to provide a variable and a list of possible values.</span></span> <span data-ttu-id="5963a-119">Se o valor corresponder à variável, o bloco de script será executado.</span><span class="sxs-lookup"><span data-stu-id="5963a-119">If the value matches the variable, then its scriptblock is executed.</span></span>

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

<span data-ttu-id="5963a-120">Nesse exemplo, o valor de `$day` corresponde a um dos valores numéricos, em seguida, o nome correto é atribuído a `$result`.</span><span class="sxs-lookup"><span data-stu-id="5963a-120">For this example, the value of `$day` matches one of the numeric values, then the correct name is assigned to `$result`.</span></span> <span data-ttu-id="5963a-121">Estamos apenas fazendo uma atribuição de variável nesse exemplo, mas qualquer PowerShell pode ser executado nesses blocos de script.</span><span class="sxs-lookup"><span data-stu-id="5963a-121">We are only doing a variable assignment in this example, but any PowerShell can be executed in those script blocks.</span></span>

### <a name="assign-to-a-variable"></a><span data-ttu-id="5963a-122">Atribuir a uma variável</span><span class="sxs-lookup"><span data-stu-id="5963a-122">Assign to a variable</span></span>

<span data-ttu-id="5963a-123">Podemos gravar esse último exemplo de outra maneira.</span><span class="sxs-lookup"><span data-stu-id="5963a-123">We can write that last example in another way.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

<span data-ttu-id="5963a-124">Estamos colocando o valor no pipeline do PowerShell e atribuindo-o ao `$result`.</span><span class="sxs-lookup"><span data-stu-id="5963a-124">We are placing the value on the PowerShell pipeline and assigning it to the `$result`.</span></span> <span data-ttu-id="5963a-125">Você pode fazer a mesma coisa com as instruções `if` e `foreach`.</span><span class="sxs-lookup"><span data-stu-id="5963a-125">You can do this same thing with the `if` and `foreach` statements.</span></span>

### <a name="default"></a><span data-ttu-id="5963a-126">Padrão</span><span class="sxs-lookup"><span data-stu-id="5963a-126">Default</span></span>

<span data-ttu-id="5963a-127">Podemos usar a palavra-chave `default` para identificar o que deve acontecer se não houver nenhuma correspondência.</span><span class="sxs-lookup"><span data-stu-id="5963a-127">We can use the `default` keyword to identify the what should happen if there is no match.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

<span data-ttu-id="5963a-128">Aqui, retornamos o valor `Unknown` no caso padrão.</span><span class="sxs-lookup"><span data-stu-id="5963a-128">Here we return the value `Unknown` in the default case.</span></span>

### <a name="strings"></a><span data-ttu-id="5963a-129">Cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="5963a-129">Strings</span></span>

<span data-ttu-id="5963a-130">Estava correspondendo números nesses últimos exemplos, mas você também pode corresponder cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5963a-130">I was matching numbers in those last examples, but you can also match strings.</span></span>

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="5963a-131">Decidi não encapsular as correspondências `Component`,`Role` e `Location` entre aspas aqui para realçar que elas são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5963a-131">I decided not to wrap the `Component`,`Role` and `Location` matches in quotes here to highlight that they're optional.</span></span> <span data-ttu-id="5963a-132">O `switch` trata elas como uma cadeia de caracteres na maioria dos casos.</span><span class="sxs-lookup"><span data-stu-id="5963a-132">The `switch` treats those as a string in most cases.</span></span>

## <a name="arrays"></a><span data-ttu-id="5963a-133">Matrizes</span><span class="sxs-lookup"><span data-stu-id="5963a-133">Arrays</span></span>

<span data-ttu-id="5963a-134">Um dos recursos interessantes de `switch` do PowerShell é a maneira como ele lida com matrizes.</span><span class="sxs-lookup"><span data-stu-id="5963a-134">One of the cool features of the PowerShell `switch` is the way it handles arrays.</span></span> <span data-ttu-id="5963a-135">Se você fornecer uma matriz a um `switch`, ele processará cada elemento nessa coleção.</span><span class="sxs-lookup"><span data-stu-id="5963a-135">If you give a `switch` an array, it processes each element in that collection.</span></span>

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

<span data-ttu-id="5963a-136">Se você tiver itens repetidos na sua matriz, eles serão correspondidos várias vezes pela seção apropriada.</span><span class="sxs-lookup"><span data-stu-id="5963a-136">If you have repeated items in your array, then they're matched multiple times by the appropriate section.</span></span>

### <a name="psitem"></a><span data-ttu-id="5963a-137">PSItem</span><span class="sxs-lookup"><span data-stu-id="5963a-137">PSItem</span></span>

<span data-ttu-id="5963a-138">Você pode usar `$PSItem` ou `$_` para fazer referência ao item atual que foi processado.</span><span class="sxs-lookup"><span data-stu-id="5963a-138">You can use the `$PSItem` or `$_` to reference the current item that was processed.</span></span> <span data-ttu-id="5963a-139">Quando fazemos uma correspondência simples, `$PSItem` é o valor que estamos correspondendo.</span><span class="sxs-lookup"><span data-stu-id="5963a-139">When we do a simple match, `$PSItem` is the value that we are matching.</span></span> <span data-ttu-id="5963a-140">Executarei algumas correspondências avançadas na próxima seção nas quais essa variável é usada.</span><span class="sxs-lookup"><span data-stu-id="5963a-140">I'll be performing some advanced matches in the next section where this variable is used.</span></span>

## <a name="parameters"></a><span data-ttu-id="5963a-141">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5963a-141">Parameters</span></span>

<span data-ttu-id="5963a-142">Um recurso exclusivo de `switch` do PowerShell é que ele tem um número de [parâmetros de opção][] que alteram a forma como ele é executado.</span><span class="sxs-lookup"><span data-stu-id="5963a-142">A unique feature of the PowerShell `switch` is that it has a number of [switch parameters][] that change how it performs.</span></span>

### <a name="-casesensitive"></a><span data-ttu-id="5963a-143">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="5963a-143">-CaseSensitive</span></span>

<span data-ttu-id="5963a-144">Por padrão, as correspondências não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5963a-144">The matches aren't case-sensitive by default.</span></span> <span data-ttu-id="5963a-145">Se você precisar diferenciar maiúsculas de minúsculas, poderá usar `-CaseSensitive`.</span><span class="sxs-lookup"><span data-stu-id="5963a-145">If you need to be case-sensitive, you can use `-CaseSensitive`.</span></span> <span data-ttu-id="5963a-146">Isso pode ser usado em combinação com os outros parâmetros de opção.</span><span class="sxs-lookup"><span data-stu-id="5963a-146">This can be used in combination with the other switch parameters.</span></span>

### <a name="-wildcard"></a><span data-ttu-id="5963a-147">-Wildcard</span><span class="sxs-lookup"><span data-stu-id="5963a-147">-Wildcard</span></span>

<span data-ttu-id="5963a-148">Podemos habilitar o suporte a curinga com a switch `-wildcard`.</span><span class="sxs-lookup"><span data-stu-id="5963a-148">We can enable wildcard support with the `-wildcard` switch.</span></span> <span data-ttu-id="5963a-149">Isso usa a mesma lógica de curinga que o operador `-like` para fazer cada correspondência.</span><span class="sxs-lookup"><span data-stu-id="5963a-149">This uses the same wildcard logic as the `-like` operator to do each match.</span></span>

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

<span data-ttu-id="5963a-150">Aqui, estamos processando uma mensagem e, em seguida, gerando-a em fluxos diferentes com base no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5963a-150">Here we are processing a message and then outputting it on different streams based on the contents.</span></span>

### <a name="-regex"></a><span data-ttu-id="5963a-151">-Regex</span><span class="sxs-lookup"><span data-stu-id="5963a-151">-Regex</span></span>

<span data-ttu-id="5963a-152">A instrução switch dá suporte a correspondências de expressão regular, exatamente como acontece com curingas.</span><span class="sxs-lookup"><span data-stu-id="5963a-152">The switch statement supports regex matches just like it does wildcards.</span></span>

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

<span data-ttu-id="5963a-153">Há mais exemplos de uso de expressões regulares em outro artigo que escrevi: [As várias maneiras de usar regex][].</span><span class="sxs-lookup"><span data-stu-id="5963a-153">I have more examples of using regex in another article I wrote: [The many ways to use regex][].</span></span>

### <a name="-file"></a><span data-ttu-id="5963a-154">-File</span><span class="sxs-lookup"><span data-stu-id="5963a-154">-File</span></span>

<span data-ttu-id="5963a-155">Um recurso pouco conhecido da instrução switch é que ela pode processar um arquivo com o parâmetro `-File`.</span><span class="sxs-lookup"><span data-stu-id="5963a-155">A little known feature of the switch statement is that it can process a file with the `-File` parameter.</span></span> <span data-ttu-id="5963a-156">Você usa `-file` com um caminho para um arquivo em vez de dar a ele uma expressão variável.</span><span class="sxs-lookup"><span data-stu-id="5963a-156">You use `-file` with a path to a file instead of giving it a variable expression.</span></span>

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="5963a-157">Ele funciona exatamente como processar uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5963a-157">It works just like processing an array.</span></span> <span data-ttu-id="5963a-158">Nesse exemplo, eu o combino com uma correspondência de curinga e uso o `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="5963a-158">In this example, I combine it with wildcard matching and make use of the `$PSItem`.</span></span> <span data-ttu-id="5963a-159">Isso processaria um arquivo de log e o converteria em mensagens erro e de aviso, dependendo das correspondências de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="5963a-159">This would process a log file and convert it to warning and error messages depending on the regex matches.</span></span>

## <a name="advanced-details"></a><span data-ttu-id="5963a-160">Detalhes avançados</span><span class="sxs-lookup"><span data-stu-id="5963a-160">Advanced details</span></span>

<span data-ttu-id="5963a-161">Agora que você está ciente de todos esses recursos documentados, podemos usá-los no contexto de um processamento mais avançado.</span><span class="sxs-lookup"><span data-stu-id="5963a-161">Now that you're aware of all these documented features, we can use them in the context of more advanced processing.</span></span>

### <a name="expressions"></a><span data-ttu-id="5963a-162">Expressões</span><span class="sxs-lookup"><span data-stu-id="5963a-162">Expressions</span></span>

<span data-ttu-id="5963a-163">O `switch` pode estar em uma expressão em vez de em uma variável.</span><span class="sxs-lookup"><span data-stu-id="5963a-163">The `switch` can be on an expression instead of a variable.</span></span>

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

<span data-ttu-id="5963a-164">Independentemente de como a expressão é avaliada, ela é o valor usado para a correspondência.</span><span class="sxs-lookup"><span data-stu-id="5963a-164">Whatever the expression evaluates to is the value used for the match.</span></span>

### <a name="multiple-matches"></a><span data-ttu-id="5963a-165">Múltiplas correspondências</span><span class="sxs-lookup"><span data-stu-id="5963a-165">Multiple matches</span></span>

<span data-ttu-id="5963a-166">Talvez você já tenha percebido, mas um `switch` pode corresponder a várias condições.</span><span class="sxs-lookup"><span data-stu-id="5963a-166">You may have already picked up on this, but a `switch` can match to multiple conditions.</span></span> <span data-ttu-id="5963a-167">Isso é especialmente verdadeiro ao usar as correspondências `-wildcard` ou `-regex`.</span><span class="sxs-lookup"><span data-stu-id="5963a-167">This is especially true when using `-wildcard` or `-regex` matches.</span></span> <span data-ttu-id="5963a-168">Você pode adicionar a mesma condição várias vezes e todas elas serem disparadas.</span><span class="sxs-lookup"><span data-stu-id="5963a-168">You can add the same condition multiple times and all of them are triggered.</span></span>

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

<span data-ttu-id="5963a-169">Essas três instruções são disparadas.</span><span class="sxs-lookup"><span data-stu-id="5963a-169">All three of these statements are fired.</span></span> <span data-ttu-id="5963a-170">Isso mostra que todas as condições são verificadas (em ordem).</span><span class="sxs-lookup"><span data-stu-id="5963a-170">This shows that every condition is checked (in order).</span></span> <span data-ttu-id="5963a-171">Isso é verdadeiro para matrizes de processamento, nas quais cada item verifica cada condição.</span><span class="sxs-lookup"><span data-stu-id="5963a-171">This holds true for processing arrays where each item checks each condition.</span></span>

### <a name="continue"></a><span data-ttu-id="5963a-172">Continue</span><span class="sxs-lookup"><span data-stu-id="5963a-172">Continue</span></span>

<span data-ttu-id="5963a-173">Normalmente, aqui que eu apresentaria a instrução `break`, mas é melhor que aprendemos a usar a `continue` primeiro.</span><span class="sxs-lookup"><span data-stu-id="5963a-173">Normally, this is where I would introduce the `break` statement, but it's better that we learn how to use `continue` first.</span></span> <span data-ttu-id="5963a-174">Assim como com um loop de `foreach`, o `continue` continua no próximo item da coleção ou sai do `switch`, se não houver mais itens.</span><span class="sxs-lookup"><span data-stu-id="5963a-174">Just like with a `foreach` loop, `continue` continues onto the next item in the collection or exits the `switch` if there are no more items.</span></span> <span data-ttu-id="5963a-175">Podemos reescrever esse último exemplo com instruções continue para que apenas uma instrução seja executada.</span><span class="sxs-lookup"><span data-stu-id="5963a-175">We can rewrite that last example with continue statements so that only one statement executes.</span></span>

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

<span data-ttu-id="5963a-176">Em vez de corresponder todos os três itens, o primeiro é correspondido e a switch continua para o próximo valor.</span><span class="sxs-lookup"><span data-stu-id="5963a-176">Instead of matching all three items, the first one is matched and the switch continues to the next value.</span></span> <span data-ttu-id="5963a-177">Como não há valores restantes para processar, switch é fechada.</span><span class="sxs-lookup"><span data-stu-id="5963a-177">Because there are no values left to process, the switch exits.</span></span> <span data-ttu-id="5963a-178">Este próximo exemplo mostra como um curinga pode corresponder a vários itens.</span><span class="sxs-lookup"><span data-stu-id="5963a-178">This next example is showing how a wildcard could match multiple items.</span></span>

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="5963a-179">Como uma linha no arquivo de entrada pode conter as palavras `Error` e `Warning`, queremos que apenas a primeira seja executada e, em seguida, continue processando o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5963a-179">Because a line in the input file could contain both the word `Error` and `Warning`, we only want the first one to execute and then continue processing the file.</span></span>

### <a name="break"></a><span data-ttu-id="5963a-180">Interromper</span><span class="sxs-lookup"><span data-stu-id="5963a-180">Break</span></span>

<span data-ttu-id="5963a-181">Uma instrução `break` sai da switch.</span><span class="sxs-lookup"><span data-stu-id="5963a-181">A `break` statement exits the switch.</span></span> <span data-ttu-id="5963a-182">Esse é o mesmo comportamento que o `continue` apresenta para valores únicos.</span><span class="sxs-lookup"><span data-stu-id="5963a-182">This is the same behavior that `continue` presents for single values.</span></span> <span data-ttu-id="5963a-183">A diferença é mostrada durante o processamento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5963a-183">The difference is shown when processing an array.</span></span> <span data-ttu-id="5963a-184">`break` interrompe todo o processamento na switch e `continue` passa para o próximo item.</span><span class="sxs-lookup"><span data-stu-id="5963a-184">`break` stops all processing in the switch and `continue` moves onto the next item.</span></span>

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

<span data-ttu-id="5963a-185">Nesse caso, se atingirmos em alguma linha que começa com `Error`, obteremos um erro e a switch será interrompida.</span><span class="sxs-lookup"><span data-stu-id="5963a-185">In this case, if we hit any lines that start with `Error` then we get an error and the switch stops.</span></span>
<span data-ttu-id="5963a-186">Isso é o que essa instrução `break` está fazendo para nós.</span><span class="sxs-lookup"><span data-stu-id="5963a-186">This is what that `break` statement is doing for us.</span></span> <span data-ttu-id="5963a-187">Se encontrarmos `Error` dentro da cadeia de caracteres e não apenas no início, vamos gravá-lo como um aviso.</span><span class="sxs-lookup"><span data-stu-id="5963a-187">If we find `Error` inside the string and not just at the beginning, we write it as a warning.</span></span> <span data-ttu-id="5963a-188">Faremos a mesma coisa para `Warning`.</span><span class="sxs-lookup"><span data-stu-id="5963a-188">We do the same thing for `Warning`.</span></span> <span data-ttu-id="5963a-189">É possível que uma linha tenha ambas as palavras `Error` e `Warning`, mas precisamos apenas de uma para processar.</span><span class="sxs-lookup"><span data-stu-id="5963a-189">It's possible that a line could have both the word `Error` and `Warning`, but we only need one to process.</span></span> <span data-ttu-id="5963a-190">Isso é o que a instrução `continue` está fazendo para nós.</span><span class="sxs-lookup"><span data-stu-id="5963a-190">This is what the `continue` statement is doing for us.</span></span>

### <a name="break-labels"></a><span data-ttu-id="5963a-191">Rótulos de intervalo</span><span class="sxs-lookup"><span data-stu-id="5963a-191">Break labels</span></span>

<span data-ttu-id="5963a-192">A instrução `switch` dá suporte a rótulos `break/continue`, assim como `foreach`.</span><span class="sxs-lookup"><span data-stu-id="5963a-192">The `switch` statement supports `break/continue` labels just like `foreach`.</span></span>

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

<span data-ttu-id="5963a-193">Pessoalmente, não gosto do uso de rótulos de intervalo, mas queria destacá-los porque eles são confusos se você nunca os viu antes.</span><span class="sxs-lookup"><span data-stu-id="5963a-193">I personally don't like the use of break labels but I wanted to point them out because they're confusing if you've never seen them before.</span></span> <span data-ttu-id="5963a-194">Quando você tiver várias instruções `switch` ou `foreach` aninhadas, talvez queira interromper mais do que o item mais interno.</span><span class="sxs-lookup"><span data-stu-id="5963a-194">When you have multiple `switch` or `foreach` statements that are nested, you may want to break out of more than the inner most item.</span></span> <span data-ttu-id="5963a-195">Você pode colocar um rótulo em um `switch` que pode ser o destino do seu `break`.</span><span class="sxs-lookup"><span data-stu-id="5963a-195">You can place a label on a `switch` that can be the target of your `break`.</span></span>

### <a name="enum"></a><span data-ttu-id="5963a-196">Enum</span><span class="sxs-lookup"><span data-stu-id="5963a-196">Enum</span></span>

<span data-ttu-id="5963a-197">O PowerShell 5.0 forneceu enumerações e podemos usá-las em uma switch.</span><span class="sxs-lookup"><span data-stu-id="5963a-197">PowerShell 5.0 gave us enums and we can use them in a switch.</span></span>

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="5963a-198">Se você desejar manter tudo como enumerações fortemente tipadas, poderá colocá-las entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="5963a-198">If you want to keep everything as strongly typed enums, then you can place them in parentheses.</span></span>

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

<span data-ttu-id="5963a-199">Os parênteses são necessários aqui para que a switch não trate o valor `[Context]::Location` como uma cadeia de caracteres literal.</span><span class="sxs-lookup"><span data-stu-id="5963a-199">The parentheses are needed here so that the switch doesn't treat the value `[Context]::Location` as a literal string.</span></span>

### <a name="scriptblock"></a><span data-ttu-id="5963a-200">Bloco de script</span><span class="sxs-lookup"><span data-stu-id="5963a-200">ScriptBlock</span></span>

<span data-ttu-id="5963a-201">Podemos usar um bloco de script para executar a avaliação de uma correspondência, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5963a-201">We can use a scriptblock to perform the evaluation for a match if needed.</span></span>

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

<span data-ttu-id="5963a-202">Isso aumenta a complexidade e pode tornar o seu `switch` difícil de ler.</span><span class="sxs-lookup"><span data-stu-id="5963a-202">This adds complexity and can make your `switch` hard to read.</span></span> <span data-ttu-id="5963a-203">Na maioria dos casos em que você usaria algo semelhante a isso, seria melhor usar as instruções `if` e `elseif`.</span><span class="sxs-lookup"><span data-stu-id="5963a-203">In most cases where you would use something like this it would be better to use `if` and `elseif` statements.</span></span> <span data-ttu-id="5963a-204">Eu consideraria o uso desse recurso se já tivesse uma instrução switch muito longa em vigor e precisasse que dois itens atingissem o mesmo bloco de avaliação.</span><span class="sxs-lookup"><span data-stu-id="5963a-204">I would consider using this if I already had a large switch in place and I needed two items to hit the same evaluation block.</span></span>

<span data-ttu-id="5963a-205">Uma coisa que acho que me ajuda com a legibilidade é colocar o bloco de script entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="5963a-205">One thing that I think helps with legibility is to place the scriptblock in parentheses.</span></span>

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

<span data-ttu-id="5963a-206">Ele ainda é executado da mesma maneira e fornece uma quebra visual melhor ao olhar rapidamente.</span><span class="sxs-lookup"><span data-stu-id="5963a-206">It still executes the same way and gives a better visual break when quickly looking at it.</span></span>

### <a name="regex-matches"></a><span data-ttu-id="5963a-207">$matches de expressão regular</span><span class="sxs-lookup"><span data-stu-id="5963a-207">Regex $matches</span></span>

<span data-ttu-id="5963a-208">Precisamos revisitar as expressões regulares para discutir algo que não é imediatamente óbvio.</span><span class="sxs-lookup"><span data-stu-id="5963a-208">We need to revisit regex to touch on something that isn't immediately obvious.</span></span> <span data-ttu-id="5963a-209">O uso de expressões regulares popula a variável `$matches`.</span><span class="sxs-lookup"><span data-stu-id="5963a-209">The use of regex populates the `$matches` variable.</span></span> <span data-ttu-id="5963a-210">Eu me aprofundo mais sobre o uso do `$matches` ao falar sobre [As várias maneiras de usar regex][].</span><span class="sxs-lookup"><span data-stu-id="5963a-210">I do go into the use of `$matches` more when I talk about [The many ways to use regex][].</span></span> <span data-ttu-id="5963a-211">A seguir está um exemplo rápido para mostrá-lo em ação com correspondências nomeadas.</span><span class="sxs-lookup"><span data-stu-id="5963a-211">Here is a quick sample to show it in action with named matches.</span></span>

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a><span data-ttu-id="5963a-212">$null</span><span class="sxs-lookup"><span data-stu-id="5963a-212">$null</span></span>

<span data-ttu-id="5963a-213">Você pode corresponder um valor `$null` que não precisa ser o padrão.</span><span class="sxs-lookup"><span data-stu-id="5963a-213">You can match a `$null` value that doesn't have to be the default.</span></span>

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

<span data-ttu-id="5963a-214">O mesmo vale para uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="5963a-214">Same goes for an empty string.</span></span>

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a><span data-ttu-id="5963a-215">Expressão de constante</span><span class="sxs-lookup"><span data-stu-id="5963a-215">Constant expression</span></span>

<span data-ttu-id="5963a-216">Lee Dailey apontou que podemos usar uma expressão de constante `$true` para avaliar os itens `[bool]`.</span><span class="sxs-lookup"><span data-stu-id="5963a-216">Lee Dailey pointed out that we can use a constant `$true` expression to evaluate `[bool]` items.</span></span>
<span data-ttu-id="5963a-217">Imagine se tivermos várias verificações boolianas que precisam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="5963a-217">Imagine if we have several boolean checks that need to happen.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

<span data-ttu-id="5963a-218">Essa é um modo limpo de avaliar e agir sobre o status de vários campos boolianos.</span><span class="sxs-lookup"><span data-stu-id="5963a-218">This is a clean way to evaluate and take action on the status of several boolean fields.</span></span> <span data-ttu-id="5963a-219">O interessante nisso é que uma correspondência pode inverter o status de um valor que ainda não foi avaliado.</span><span class="sxs-lookup"><span data-stu-id="5963a-219">The cool thing about this is that you can have one match flip the status of a value that hasn't been evaluated yet.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

<span data-ttu-id="5963a-220">A configuração de `$isEnabled` para `$true` nesse exemplo garante que `$isVisible` também seja definido como `$true`.</span><span class="sxs-lookup"><span data-stu-id="5963a-220">Setting `$isEnabled` to `$true` in this example makes sure that `$isVisible` is also set to `$true`.</span></span> <span data-ttu-id="5963a-221">Em seguida, quando `$isVisible` é avaliado, o bloco de script dele é invocado.</span><span class="sxs-lookup"><span data-stu-id="5963a-221">Then when `$isVisible` gets evaluated, its scriptblock is invoked.</span></span> <span data-ttu-id="5963a-222">Isso é um pouco contraintuitivo, mas é um uso inteligente da mecânica.</span><span class="sxs-lookup"><span data-stu-id="5963a-222">This is a bit counter-intuitive but is a clever use of the mechanics.</span></span>

### <a name="switch-automatic-variable"></a><span data-ttu-id="5963a-223">Variável automática $switch</span><span class="sxs-lookup"><span data-stu-id="5963a-223">$switch automatic variable</span></span>

<span data-ttu-id="5963a-224">Quando o `switch` estiver processando os valores, ele criará um enumerador e o chamará de `$switch`.</span><span class="sxs-lookup"><span data-stu-id="5963a-224">When the `switch` is processing its values, it creates an enumerator and calls it `$switch`.</span></span> <span data-ttu-id="5963a-225">Essa é uma variável automática criada pelo PowerShell, e você pode manipulá-la diretamente.</span><span class="sxs-lookup"><span data-stu-id="5963a-225">This is an automatic variable created by PowerShell and you can manipulate it directly.</span></span>

<span data-ttu-id="5963a-226">Isso foi apontado para mim por [/u/frmadsen](https://www.reddit.com/user/frmadsen)</span><span class="sxs-lookup"><span data-stu-id="5963a-226">This was pointed out to me by [/u/frmadsen](https://www.reddit.com/user/frmadsen)</span></span>

<div class="reddit-embed" data-embed-media="www.redditmedia.com" data-embed-parent="false" data-embed-live="false" data-embed-uuid="8f6edbf1-abc6-4513-971e-ccd1d202889d" data-embed-created="2018-12-25T22:05:33.986Z"><span data-ttu-id="5963a-227"><a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">Comentário</a> da discussão <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">O que eu (aluno de TI) devo aprender para dominar o PowerShell?</a>.</span><span class="sxs-lookup"><span data-stu-id="5963a-227"><a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">Comment</a> from discussion <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">What should I (IT student) learn to master PowerShell?</a>.</span></span></div><script async src="https://www.redditstatic.com/comment-embed.js"></script>

<span data-ttu-id="5963a-228">Isso fornece os resultados de:</span><span class="sxs-lookup"><span data-stu-id="5963a-228">This gives you the results of:</span></span>

```Output
2
4
```

<span data-ttu-id="5963a-229">Ao mover o enumerador para frente, o próximo item não é processado pelo `switch`, mas você pode acessar esse valor diretamente.</span><span class="sxs-lookup"><span data-stu-id="5963a-229">By moving the enumerator forward, the next item doesn't get processed by the `switch` but you can access that value directly.</span></span> <span data-ttu-id="5963a-230">Eu chamaria isso de loucura.</span><span class="sxs-lookup"><span data-stu-id="5963a-230">I would call it madness.</span></span>

## <a name="other-patterns"></a><span data-ttu-id="5963a-231">Outros padrões</span><span class="sxs-lookup"><span data-stu-id="5963a-231">Other patterns</span></span>

### <a name="hashtables"></a><span data-ttu-id="5963a-232">Tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="5963a-232">Hashtables</span></span>

<span data-ttu-id="5963a-233">Uma das minhas postagens mais populares é aquela que fiz sobre [tabelas de hash][].</span><span class="sxs-lookup"><span data-stu-id="5963a-233">One of my most popular posts is the one I did on [hashtables][].</span></span> <span data-ttu-id="5963a-234">Um dos casos de uso de um `hashtable` é ser uma tabela de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5963a-234">One of the use cases for a `hashtable` is to be a lookup table.</span></span> <span data-ttu-id="5963a-235">Essa é uma abordagem alternativa para um padrão comum que uma instrução `switch` geralmente aborda.</span><span class="sxs-lookup"><span data-stu-id="5963a-235">That is an alternate approach to a common pattern that a `switch` statement is often addressing.</span></span>

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

<span data-ttu-id="5963a-236">Se estiver usando um `switch` apenas como uma pesquisa, geralmente usarei um `hashtable` em vez disso.</span><span class="sxs-lookup"><span data-stu-id="5963a-236">If I'm only using a `switch` as a lookup, I often use a `hashtable` instead.</span></span>

### <a name="enum"></a><span data-ttu-id="5963a-237">Enum</span><span class="sxs-lookup"><span data-stu-id="5963a-237">Enum</span></span>

<span data-ttu-id="5963a-238">O PowerShell 5.0 apresentou o `Enum` e ele também é uma opção nesse caso.</span><span class="sxs-lookup"><span data-stu-id="5963a-238">PowerShell 5.0 introduced the `Enum` and it's also an option in this case.</span></span>

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

<span data-ttu-id="5963a-239">Poderíamos passar o dia analisando diferentes maneiras de resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="5963a-239">We could go all day looking at different ways to solve this problem.</span></span> <span data-ttu-id="5963a-240">Queria apenas me certificar de que você sabe que tem opções.</span><span class="sxs-lookup"><span data-stu-id="5963a-240">I just wanted to make sure you knew you had options.</span></span>

## <a name="final-words"></a><span data-ttu-id="5963a-241">Conclusão</span><span class="sxs-lookup"><span data-stu-id="5963a-241">Final words</span></span>

<span data-ttu-id="5963a-242">A instrução switch é aparentemente simples, mas oferece alguns recursos avançados que a maioria das pessoas não percebe que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5963a-242">The switch statement is simple on the surface but it offers some advanced features that most people don't realize are available.</span></span> <span data-ttu-id="5963a-243">Juntar esses recursos torna esse um recurso poderoso.</span><span class="sxs-lookup"><span data-stu-id="5963a-243">Stringing those features together makes this a powerful feature.</span></span> <span data-ttu-id="5963a-244">Espero que você tenha aprendido algo que não tinha percebido antes.</span><span class="sxs-lookup"><span data-stu-id="5963a-244">I hope you learned something that you had not realized before.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[original version]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[parâmetros de opção]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[switch parameters]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[As várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[tabelas de hash]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
