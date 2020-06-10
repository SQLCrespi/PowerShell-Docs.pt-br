---
title: Tudo o que você sempre quis saber sobre a instrução switch
description: A instrução switch no PowerShell oferece recursos que não são encontrados em outras linguagens.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ebf6191d56374273465ae6bee49ef82a02cc1580
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149419"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a>Tudo o que você sempre quis saber sobre a instrução switch

Como muitas outras linguagens, o PowerShell tem comandos para controlar o fluxo de execução dentro dos seus scripts. Uma dessas instruções é a instrução [switch][] e, no PowerShell, ela oferece recursos que não são encontrados em outras linguagens. Hoje, vamos nos aprofundar sobre como trabalhar com o `switch` do PowerShell.

> [!NOTE]
> A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="if-statement"></a>Instrução If

Uma das primeiras instruções que você aprende é a instrução `if`. Ela permitirá que você execute um bloco de script se uma instrução for `$true`.

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

Você pode ter uma lógica muito mais complicada usando instruções `elseif` e `else`. A seguir está um exemplo no qual tenho um valor numérico para o dia da semana e quero obter o nome como uma cadeia de caracteres.

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

Esse é um padrão comum e há várias maneiras de lidar com isso. Uma delas é com um `switch`.

## <a name="switch-statement"></a>Instrução switch

A instrução `switch` permite que você forneça uma variável e uma lista de valores possíveis. Se o valor corresponder à variável, o bloco de script será executado.

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

Nesse exemplo, o valor de `$day` corresponde a um dos valores numéricos, em seguida, o nome correto é atribuído a `$result`. Estamos apenas fazendo uma atribuição de variável nesse exemplo, mas qualquer PowerShell pode ser executado nesses blocos de script.

### <a name="assign-to-a-variable"></a>Atribuir a uma variável

Podemos gravar esse último exemplo de outra maneira.

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

Estamos colocando o valor no pipeline do PowerShell e atribuindo-o ao `$result`. Você pode fazer a mesma coisa com as instruções `if` e `foreach`.

### <a name="default"></a>Padrão

Podemos usar a palavra-chave `default` para identificar o que deve acontecer se não houver nenhuma correspondência.

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

Aqui, retornamos o valor `Unknown` no caso padrão.

### <a name="strings"></a>Cadeias de caracteres

Estava correspondendo números nesses últimos exemplos, mas você também pode corresponder cadeias de caracteres.

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

Decidi não encapsular as correspondências `Component`,`Role` e `Location` entre aspas aqui para realçar que elas são opcionais. O `switch` trata elas como uma cadeia de caracteres na maioria dos casos.

## <a name="arrays"></a>Matrizes

Um dos recursos interessantes de `switch` do PowerShell é a maneira como ele lida com matrizes. Se você fornecer uma matriz a um `switch`, ele processará cada elemento nessa coleção.

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

Se você tiver itens repetidos na sua matriz, eles serão correspondidos várias vezes pela seção apropriada.

### <a name="psitem"></a>PSItem

Você pode usar `$PSItem` ou `$_` para fazer referência ao item atual que foi processado. Quando fazemos uma correspondência simples, `$PSItem` é o valor que estamos correspondendo. Executarei algumas correspondências avançadas na próxima seção nas quais essa variável é usada.

## <a name="parameters"></a>Parâmetros

Um recurso exclusivo de `switch` do PowerShell é que ele tem um número de [parâmetros de opção][] que alteram a forma como ele é executado.

### <a name="-casesensitive"></a>-CaseSensitive

Por padrão, as correspondências não diferenciam maiúsculas de minúsculas. Se você precisar diferenciar maiúsculas de minúsculas, poderá usar `-CaseSensitive`. Isso pode ser usado em combinação com os outros parâmetros de opção.

### <a name="-wildcard"></a>-Wildcard

Podemos habilitar o suporte a curinga com a switch `-wildcard`. Isso usa a mesma lógica de curinga que o operador `-like` para fazer cada correspondência.

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

Aqui, estamos processando uma mensagem e, em seguida, gerando-a em fluxos diferentes com base no conteúdo.

### <a name="-regex"></a>-Regex

A instrução switch dá suporte a correspondências de expressão regular, exatamente como acontece com curingas.

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

Há mais exemplos de uso de expressões regulares em outro artigo que escrevi: [As várias maneiras de usar regex][].

### <a name="-file"></a>-File

Um recurso pouco conhecido da instrução switch é que ela pode processar um arquivo com o parâmetro `-File`. Você usa `-file` com um caminho para um arquivo em vez de dar a ele uma expressão variável.

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

Ele funciona exatamente como processar uma matriz. Nesse exemplo, eu o combino com uma correspondência de curinga e uso o `$PSItem`. Isso processaria um arquivo de log e o converteria em mensagens erro e de aviso, dependendo das correspondências de expressão regular.

## <a name="advanced-details"></a>Detalhes avançados

Agora que você está ciente de todos esses recursos documentados, podemos usá-los no contexto de um processamento mais avançado.

### <a name="expressions"></a>Expressões

O `switch` pode estar em uma expressão em vez de em uma variável.

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

Independentemente de como a expressão é avaliada, ela é o valor usado para a correspondência.

### <a name="multiple-matches"></a>Múltiplas correspondências

Talvez você já tenha percebido, mas um `switch` pode corresponder a várias condições. Isso é especialmente verdadeiro ao usar as correspondências `-wildcard` ou `-regex`. Você pode adicionar a mesma condição várias vezes e todas elas serem disparadas.

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

Essas três instruções são disparadas. Isso mostra que todas as condições são verificadas (em ordem). Isso é verdadeiro para matrizes de processamento, nas quais cada item verifica cada condição.

### <a name="continue"></a>Continue

Normalmente, aqui que eu apresentaria a instrução `break`, mas é melhor que aprendemos a usar a `continue` primeiro. Assim como com um loop de `foreach`, o `continue` continua no próximo item da coleção ou sai do `switch`, se não houver mais itens. Podemos reescrever esse último exemplo com instruções continue para que apenas uma instrução seja executada.

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

Em vez de corresponder todos os três itens, o primeiro é correspondido e a switch continua para o próximo valor. Como não há valores restantes para processar, switch é fechada. Este próximo exemplo mostra como um curinga pode corresponder a vários itens.

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

Como uma linha no arquivo de entrada pode conter as palavras `Error` e `Warning`, queremos que apenas a primeira seja executada e, em seguida, continue processando o arquivo.

### <a name="break"></a>Interromper

Uma instrução `break` sai da switch. Esse é o mesmo comportamento que o `continue` apresenta para valores únicos. A diferença é mostrada durante o processamento de uma matriz. `break` interrompe todo o processamento na switch e `continue` passa para o próximo item.

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

Nesse caso, se atingirmos em alguma linha que começa com `Error`, obteremos um erro e a switch será interrompida.
Isso é o que essa instrução `break` está fazendo para nós. Se encontrarmos `Error` dentro da cadeia de caracteres e não apenas no início, vamos gravá-lo como um aviso. Faremos a mesma coisa para `Warning`. É possível que uma linha tenha ambas as palavras `Error` e `Warning`, mas precisamos apenas de uma para processar. Isso é o que a instrução `continue` está fazendo para nós.

### <a name="break-labels"></a>Rótulos de intervalo

A instrução `switch` dá suporte a rótulos `break/continue`, assim como `foreach`.

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

Pessoalmente, não gosto do uso de rótulos de intervalo, mas queria destacá-los porque eles são confusos se você nunca os viu antes. Quando você tiver várias instruções `switch` ou `foreach` aninhadas, talvez queira interromper mais do que o item mais interno. Você pode colocar um rótulo em um `switch` que pode ser o destino do seu `break`.

### <a name="enum"></a>Enum

O PowerShell 5.0 forneceu enumerações e podemos usá-las em uma switch.

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

Se você desejar manter tudo como enumerações fortemente tipadas, poderá colocá-las entre parênteses.

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

Os parênteses são necessários aqui para que a switch não trate o valor `[Context]::Location` como uma cadeia de caracteres literal.

### <a name="scriptblock"></a>Bloco de script

Podemos usar um bloco de script para executar a avaliação de uma correspondência, se necessário.

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

Isso aumenta a complexidade e pode tornar o seu `switch` difícil de ler. Na maioria dos casos em que você usaria algo semelhante a isso, seria melhor usar as instruções `if` e `elseif`. Eu consideraria o uso desse recurso se já tivesse uma instrução switch muito longa em vigor e precisasse que dois itens atingissem o mesmo bloco de avaliação.

Uma coisa que acho que me ajuda com a legibilidade é colocar o bloco de script entre parênteses.

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

Ele ainda é executado da mesma maneira e fornece uma quebra visual melhor ao olhar rapidamente.

### <a name="regex-matches"></a>$matches de expressão regular

Precisamos revisitar as expressões regulares para discutir algo que não é imediatamente óbvio. O uso de expressão regular popula a variável `$matches`. Eu me aprofundo mais sobre o uso do `$matches` ao falar sobre [As várias maneiras de usar regex][]. A seguir está um exemplo rápido para mostrá-lo em ação com correspondências nomeadas.

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

### <a name="null"></a>$null

Você pode corresponder um valor `$null` que não precisa ser o padrão.

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

O mesmo vale para uma cadeia de caracteres vazia.

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

### <a name="constant-expression"></a>Expressão de constante

Lee Dailey apontou que podemos usar uma expressão de constante `$true` para avaliar os itens `[bool]`.
Imagine se tivermos várias verificações boolianas que precisam ocorrer.

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

Essa é um modo limpo de avaliar e agir sobre o status de vários campos boolianos. O interessante disso é que uma correspondência pode inverter o status de um valor que ainda não foi avaliado.

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

A configuração de `$isEnabled` para `$true` nesse exemplo garante que `$isVisible` também seja definido como `$true`. Em seguida, quando `$isVisible` é avaliado, o bloco de script dele é invocado. Isso é um pouco contraintuitivo, mas é um uso inteligente da mecânica.

### <a name="switch-automatic-variable"></a>Variável automática $switch

Quando o `switch` estiver processando os valores, ele criará um enumerador e o chamará de `$switch`. Essa é uma variável automática criada pelo PowerShell e você pode manipulá-la diretamente.

Isso foi apontado para mim por [/u/frmadsen](https://www.reddit.com/user/frmadsen)

<div class="reddit-embed" data-embed-media="www.redditmedia.com" data-embed-parent="false" data-embed-live="false" data-embed-uuid="8f6edbf1-abc6-4513-971e-ccd1d202889d" data-embed-created="2018-12-25T22:05:33.986Z"><a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">Comentário</a> da discussão <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">O que eu (aluno de TI) devo aprender para dominar o PowerShell?</a>.</div><script async src="https://www.redditstatic.com/comment-embed.js"></script>

Isso fornece os resultados de:

```Output
2
4
```

Ao mover o enumerador para frente, o próximo item não é processado pelo `switch`, mas você pode acessar esse valor diretamente. Eu chamaria isso de loucura.

## <a name="other-patterns"></a>Outros padrões

### <a name="hashtables"></a>Tabelas de hash

Uma das minhas postagens mais populares é aquela que fiz sobre [tabelas de hash][]. Um dos casos de uso de um `hashtable` é ser uma tabela de pesquisa. Essa é uma abordagem alternativa para um padrão comum que uma instrução `switch` geralmente aborda.

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

Se estiver usando um `switch` apenas como uma pesquisa, geralmente usarei um `hashtable` em vez disso.

### <a name="enum"></a>Enum

O PowerShell 5.0 apresentou o `Enum` e ele também é uma opção nesse caso.

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

Poderíamos passar o dia analisando diferentes maneiras de resolver esse problema. Queria apenas me certificar de que você sabe que tem opções.

## <a name="final-words"></a>Conclusão

A instrução switch é aparentemente simples, mas oferece alguns recursos avançados que a maioria das pessoas não percebe que estão disponíveis. Juntar esses recursos torna esse um recurso poderoso. Espero que você tenha aprendido algo que não tinha percebido antes.

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[parâmetros de opção]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[As várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[tabelas de hash]: everything-about-hashtable.md
