---
title: Tudo o que você queria saber sobre matrizes
description: As matrizes são um recurso fundamental de linguagem da maioria das linguagens de programação.
ms.date: 07/07/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 307189bf27d383159d34181eca4dac1f77792e51
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91543365"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a>Tudo o que você queria saber sobre matrizes

As [matrizes][] são um recurso fundamental de linguagem da maioria das linguagens de programação. Elas são uma coleção de valores ou objetos difíceis de evitar. Vamos examinar as matrizes e tudo o que elas têm a oferecer.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="what-is-an-array"></a>O que é uma matriz?

Antes de mudar para as outras formas pelas quais o PowerShell faz uso das matrizes, começarei com uma descrição técnica básica do que são matrizes e como elas são usadas pela maioria das linguagens de programação.

Uma matriz é uma estrutura de dados que serve como uma coleção de vários itens. Você pode realizar uma iteração na matriz ou acessar itens individuais usando um índice. A matriz é criada como uma parte sequencial da memória, em que os valores são armazenados lado a lado.

Falarei sobre cada um desses detalhes no decorrer do artigo.

## <a name="basic-usage"></a>Uso básico

Como as matrizes são um recurso básico do PowerShell, há uma sintaxe simples para trabalhar com elas no PowerShell.

### <a name="create-an-array"></a>Criar uma matriz

Uma matriz vazia pode ser criada usando `@()`

```powershell
PS> $data = @()
PS> $data.count
0
```

Podemos criar uma matriz e propagá-la com valores apenas colocando-os nos parênteses `@()`.

```powershell
PS> $data = @('Zero','One','Two','Three')
PS> $data.count
4

PS> $data
Zero
One
Two
Three
```

Esta matriz tem quatro itens. Quando chamamos a variável `$data`, vemos a lista de nossos itens. Se for uma matriz de cadeias de caracteres, obteremos uma linha por cadeia de caracteres.

Podemos declarar uma matriz em várias linhas. A vírgula é opcional nesse caso e, geralmente, é deixada de fora.

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

Prefiro declarar minhas matrizes em várias linhas como visto acima. É mais fácil de ler quando você tem vários itens e também facilita a comparação com versões anteriores ao usar o controle do código-fonte.

#### <a name="other-syntax"></a>Outra sintaxe

`@()` é considerada a melhor sintaxe para criar uma matriz, mas as listas separadas por vírgulas funcionam na maior parte do tempo.

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a>Write-Output para criar matrizes

Um pequeno truque interessante que vale a pena mencionar é que você pode usar `Write-Output` para criar cadeias de caracteres no console com rapidez.

```powershell
$data = Write-Output Zero One Two Three
```

Isso é útil porque você não precisa colocar aspas nas extremidades das cadeias de caracteres quando o parâmetro aceita cadeias de caracteres. Eu nunca faria isso em um script, mas é compreensível que seja feito no console.

### <a name="accessing-items"></a>Acessar itens

Agora que você tem uma matriz com itens, talvez queira acessar e atualizar esses itens.

#### <a name="offset"></a>Deslocamento

Para acessar itens individuais, usamos os colchetes `[]` com um valor de deslocamento começando em 0. É assim que obtemos o primeiro item em nossa matriz:

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

O motivo pelo qual usamos zero aqui é porque o primeiro item está no início da lista; portanto, usamos um deslocamento de 0 item para chegar a ele. Para chegar ao segundo item, precisamos usar um deslocamento de 1 para ignorar o primeiro item.

```powershell
PS> $data[1]
One
```

Isso significa que o último item está no deslocamento 3.

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a>Índice

Agora você pode ver por que escolhi os valores usados para este exemplo. Apresentei a você como um deslocamento porque realmente é, mas esse deslocamento é mais comumente chamado de índice. Um índice que começa em `0`. No restante deste artigo, chamarei o deslocamento de índice.

#### <a name="special-index-tricks"></a>Truques especiais de índice

Na maioria das linguagens, você só pode especificar um único número como o índice e obter apenas um item de volta.
O PowerShell é muito mais flexível. Você pode usar vários índices ao mesmo tempo. Ao fornecer uma lista de índices, podemos selecionar diversos itens.

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

Os itens retornam com base na ordem dos índices fornecidos. Se você duplicar um índice, obterá esse item duas vezes.

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

Podemos especificar uma sequência de números com o operador `..` interno.

```powershell
PS> $data[1..3]
One
Two
Three
```

Isso também funciona em ordem inversa.

```powershell
PS> $data[3..1]
Three
Two
One
```

Você pode usar valores de índice negativos para começar o deslocamento do final. Portanto, se você precisar do último item da lista, poderá usar `-1`.

```powershell
PS> $data[-1]
Three
```

Tenha cuidado com o operador `..`. As sequências `0..-1` e `-1..0` avaliam os valores `0,-1` e `-1,0`. É fácil ver `$data[0..-1]` e pensar que ele enumerará todos os itens se você esquecer esse detalhe. `$data[0..-1]` fornece o mesmo valor que `$data[0,-1]` ao fornecer o primeiro e o último item na matriz (e nenhum dos outros valores).

#### <a name="out-of-bounds"></a>Fora dos limites

Na maioria das linguagens, se você tentar acessar um índice de um item que ultrapassa o fim da matriz, obterá algum tipo de erro ou exceção. O PowerShell não retorna nada.

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a>Não é possível indexar em uma matriz nula

Se a variável for `$null` e você tentar indexá-la como uma matriz, você receberá uma exceção `System.Management.Automation.RuntimeException` com a mensagem `Cannot index into a null array`.

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

Portanto, verifique se suas matrizes não são `$null` antes de tentar acessar elementos dentro delas.

#### <a name="count"></a>Contagem

Matrizes e outras coleções têm uma propriedade de contagem que informa quantos itens estão na matriz.

```powershell
PS> $data.count
4
```

O PowerShell 3.0 adicionou uma propriedade de contagem à maioria dos objetos. Você pode ter apenas um objeto e ele deve fornecer uma contagem de `1`.

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

Até mesmo `$null` tem uma propriedade de contagem, porém ela retorna `0`.

```powershell
PS> $null.count
0
```

Existem algumas armadilhas aqui que vou revisitar posteriormente quando abordar a verificação de `$null` ou de matrizes vazias neste artigo.

#### <a name="off-by-one-errors"></a>Erros por falta de uma repetição

Um erro de programação comum é criado porque as matrizes começam no índice 0. Os erros por falta de uma repetição podem ser introduzidos pensando em duas situações.

A primeira ocorre quando você pensa em obter o segundo item e usa um índice de `2`, o que faz com que você obtenha o terceiro item. Ou quando você usa a contagem para acessar o último item em uma matriz de quatro itens.

```powershell
$data[ $data.count ]
```

O PowerShell permite que você faça isso e dá a você exatamente o item existente no índice 4: `$null`. Você deve estar usando `$data.count - 1` ou o `-1` que aprendemos acima.

```powershell
PS> $data[ $data.count - 1 ]
Three
```

É aqui que você pode usar o índice `-1` para obter o último elemento.

```powershell
PS> $data[ -1 ]
Three
```

Lee Dailey também apontou que podemos usar `$data.GetUpperBound(0)` para obter o número máximo do índice.

```powershell
PS> $data.GetUpperBound(0)
3
PS> $data[ $data.GetUpperBound(0) ]
Three
```

A segunda situação mais comum ocorre ao iterar a lista e não parar no momento certo. Revisitarei isso quando falarmos sobre o uso do loop `for`.

### <a name="updating-items"></a>Atualizar itens

Podemos usar o mesmo índice para atualizar itens existentes na matriz. Isso nos dá acesso direto para atualizar itens individuais.

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

Se tentarmos atualizar um item que está além do último elemento, obteremos um erro `Index was outside the bounds of the array.`.

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

Revisitarei isso mais tarde quando falar sobre como aumentar uma matriz.

### <a name="iteration"></a>Iteração

Em algum momento, talvez seja necessário percorrer ou iterar toda a lista e executar alguma ação para cada item na matriz.

#### <a name="pipeline"></a>Pipeline

As matrizes e o pipeline do PowerShell são uma combinação perfeita. Essa é uma das maneiras mais simples de processar esses valores. Quando você passa uma matriz para um pipeline, cada item dentro da matriz é processado individualmente.

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

Se você ainda não viu `$PSItem` antes, apenas saiba que ele é o mesmo que `$_`. Você pode usar qualquer um deles porque ambos representam o objeto atual no pipeline.

#### <a name="foreach-loop"></a>Loop ForEach

O loop `ForEach` funciona bem com coleções. Usando a sintaxe: `foreach ( <variable> in <collection> )`

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a>Método ForEach

Eu costumo me esquecer deste método, mas ele funciona bem para operações simples. O PowerShell permite que você chame `.ForEach()` em uma coleção.

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

O `.foreach()` usa um parâmetro que é um bloco de script. Você pode descartar os parênteses e fornecer apenas o bloco de script.

```powershell
$data.foreach{"Item [$PSItem]"}
```

Essa é uma sintaxe menos conhecida, mas funciona exatamente da mesma forma. O método `foreach` foi adicionado no PowerShell 4.0.

#### <a name="for-loop"></a>Loop for

O loop `for` é muito usado na maioria das linguagens, mas não é muito comum no PowerShell. Geralmente ele é usado para percorrer uma matriz.

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

A primeira ação é inicializar um `$index` para `0`. Em seguida, adicionamos a condição de que `$index` deve ser menor que `$data.count`. Por fim, especificamos que, toda vez que executamos um loop, o índice precisa ser aumentado em `1`. Nesse caso, `$index++` é a abreviação de `$index = $index + 1`.

Sempre que você estiver usando um loop `for`, preste muita atenção à condição. Usei `$index -lt $data.count` aqui. É fácil obter uma condição um pouco errada para obter um erro por falta de uma repetição em sua lógica. É errado usar `$index -le $data.count` ou `$index -lt ($data.count - 1)`. Isso faria com que o resultado processasse muitos ou poucos itens. Este é o clássico erro por falta de uma repetição.

#### <a name="switch-loop"></a>Loop switch

Este é fácil de ser ignorado. Se você fornecer uma matriz a uma [instrução switch][], ela verificará cada item na matriz.

```powershell
$data = 'Zero','One','Two','Three'
switch( $data )
{
    'One'
    {
        'Tock'
    }
    'Three'
    {
        'Tock'
    }
    Default
    {
        'Tick'
    }
}
```

```Output
Tick
Tock
Tick
Tock
```

Há muitas coisas interessantes que podemos fazer com a instrução switch. Tenho outro artigo dedicado a isso.

- [Tudo o que você queria saber sobre a instrução switch][instrução switch]

#### <a name="updating-values"></a>Atualizar valores

Quando a matriz é uma coleção de cadeia de caracteres ou de inteiros (tipos de valor), às vezes, convém atualizar os valores na matriz conforme você faz um loop sobre eles. A maioria dos loops acima usa uma variável que contém uma cópia do valor. Se você atualizar essa variável, o valor original na matriz não será atualizado.

A exceção a essa instrução é o loop `for`. Se você deseja percorrer uma matriz e atualizar valores dentro dela, o loop `for` é o que você está procurando.

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

Este exemplo usa um valor por índice, faz algumas alterações e usa esse mesmo índice para atribuí-lo de volta.

## <a name="arrays-of-objects"></a>Matrizes de objetos

Até agora, o único item que colocamos em uma matriz é um tipo de valor, mas as matrizes também podem conter objetos.

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

Muitos cmdlets retornam coleções de objetos como matrizes quando você os atribui a uma variável.

```powershell
$processList = Get-Process
```

Todos os recursos básicos dos quais já falamos ainda se aplicam a matrizes de objetos com alguns detalhes que valem a pena destacar.

### <a name="accessing-properties"></a>Acessar propriedades

Podemos usar um índice para acessar um item individual em uma coleção, assim como ocorre com tipos de valor.

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

Podemos acessar e atualizar as propriedades diretamente.

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a>Propriedades da matriz

Normalmente, você teria que enumerar a lista inteira desta forma para acessar todas as propriedades:

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

Ou usar o cmdlet `Select-Object -ExpandProperty`.

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

Mas o PowerShell permite solicitar `LastName` diretamente. O PowerShell enumera todas elas para nós e retorna uma lista limpa.

```powershell
PS> $data.LastName

Marquette
Doe
```

A enumeração ainda acontece, mas não vemos a complexidade por trás dela.

### <a name="where-object-filtering"></a>Filtragem Where-Object

É aí que `Where-Object` entra em ação para que possamos filtrar e selecionar o que desejamos para fora da matriz com base nas propriedades do objeto.

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

Podemos gravar essa mesma consulta para obter o `FirstName` que estamos procurando.

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a>Where()

As matrizes têm um método `Where()` que permite especificar um `scriptblock` para o filtro.

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

Esse recurso foi adicionado no PowerShell 4.0.

### <a name="updating-objects-in-loops"></a>Atualizar objetos em loops

Com tipos de valor, a única maneira de atualizar a matriz é usando um loop for, pois precisamos saber o índice para substituir o valor. Temos mais opções com objetos porque são tipos de referência. Aqui está um exemplo rápido:

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

O loop está percorrendo cada objeto na matriz `$data`. Como os objetos são tipos de referência, a variável `$person` referencia exatamente o mesmo objeto que está na matriz. Portanto, as atualizações das suas propriedades atualizam o original.

Você ainda não pode substituir o objeto inteiro dessa maneira. Se você tentar atribuir um novo objeto à variável `$person`, atualizará a referência da variável para algo que não aponta mais para o objeto original na matriz. Isso não vai funcionar como esperado:

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a>Operadores

Os operadores no PowerShell também funcionam em matrizes. Alguns deles funcionam de modo ligeiramente diferente.

### <a name="-join"></a>-join

O operador `-join` é o mais óbvio. Portanto, vamos dar uma olhada nele primeiro. Gosto do operador `-join` e o uso com frequência. Ele une todos os elementos na matriz com o caractere ou a cadeia de caracteres que você especificar.

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

Um dos recursos que gosto sobre o operador `-join` é que ele lida com itens únicos.

```powershell
PS> 1 -join '-'
1
```

Uso isso dentro de mensagens detalhadas e de registro em log.

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a>-join $array

Este é um truque inteligente que Lee Dailey apresentou para mim. Se você quiser unir tudo sem um delimitador, em vez de fazer isso:

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

Você pode usar `-join` com a matriz como o parâmetro sem prefixo. Dê uma olhada neste exemplo para ver do que estou falando.

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a>-replace e -split

Os outros operadores, como `-replace` e `-split` são executados em cada item da matriz. Não posso dizer que já os usei dessa forma, mas aqui está um exemplo.

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a>-contains

O operador `-contains` permite que você verifique uma matriz de valores para ver se ela contém um valor especificado.

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a>-in

Quando você tem um único valor e deseja verificar se ele corresponde a um dos vários valores, pode usar o operador `-in`. O valor estaria no lado esquerdo e a matriz, no lado direito do operador.

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

Isso poderá sair caro se a lista for grande. Costumo usar um padrão regex para verificar mais do que alguns valores.

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a>-eq e -ne

Igualdade e matrizes podem ficar complicadas. Quando a matriz está no lado esquerdo, todos os itens são comparados. Em vez de retornar `True`, ela retorna o objeto correspondente.

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

Quando usamos o operador `-ne`, obtemos todos os valores que não são iguais ao nosso valor.

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

Quando você usa isso em uma instrução `if()`, um valor retornado é um valor `True`. Se nenhum valor for retornado, será um valor `False`. Ambas as próximas instruções são avaliadas como `True`.

```powershell
$data = @('red','green','blue')
if ( $data -eq 'green' )
{
    'Green was found'
}
if ( $data -ne 'green' )
{
    'And green was not found'
}
```

Retornarei a este assunto daqui a pouco quando falarmos sobre testes para `$null`.

### <a name="-match"></a>-match

O operador `-match` tenta obter uma correspondência para cada item na coleção.

```powershell
PS> $servers = @(
    'LAX-SQL-01'
    'LAX-API-01'
    'ATX-SQL-01'
    'ATX-API-01'
)
PS> $servers -match 'SQL'
LAX-SQL-01
ATX-SQL-01
```

Quando você usa `-match` com um só valor, uma variável especial `$Matches` é populada com informações de correspondência. Isso não acontece quando uma matriz é processada dessa maneira.

Podemos usar a mesma abordagem com `Select-String`.

```powershell
$servers | Select-String SQL
```

Falo mais detalhadamente sobre `Select-String`, `-match` e a variável `$matches` em outra postagem chamada [As várias maneiras de usar regex][].

### <a name="null-or-empty"></a>$null ou vazia

O teste para matrizes `$null` ou vazias pode ser complicado. Aqui estão as armadilhas mais comuns com matrizes.

À primeira vista, essa instrução parece funcionar.

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

Mas acabei de mencionar como `-eq` verifica cada item na matriz. Portanto, podemos ter uma matriz de vários itens com um único valor $null e ele será avaliado como `$true`

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

Por esse motivo, a melhor prática é posicionar `$null` no lado esquerdo do operador. Isso faz com que esse cenário não seja um problema.

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

Uma matriz `$null` não é o mesmo que uma matriz vazia. Se você sabe que tem uma matriz, verifique a contagem de objetos nela. Se a matriz for `$null`, a contagem será `0`.

```powershell
if ( $array.count -gt 0 )
{
    'Array isn't empty'
}
```

Há mais uma armadilha a ser observada aqui. Você pode usar `count` mesmo que tenha um único objeto, a menos que esse objeto seja um `PSCustomObject`. Esse é um bug que foi corrigido no PowerShell 6.1.
Essa é uma boa notícia, mas muitas pessoas ainda usam a versão 5.1 e precisam prestar atenção nisso.

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

Se ainda estiver usando o PowerShell 5.1, você poderá encapsular o objeto em uma matriz antes de verificar a contagem para obter uma contagem precisa.

```powershell
if ( @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

Para não correr nenhum risco, verifique se há `$null` e, em seguida, verifique a contagem.

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

### <a name="all--eq"></a>Tudo -eq

Vi recentemente alguém perguntar [como verificar se cada valor em uma matriz corresponde a um determinado valor][].
O usuário do Reddit **/u/bis** criou essa [solução][] inteligente que verifica se há valores incorretos e inverte o resultado.

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a>Adicionar a matrizes

Agora você deve estar começando a imaginar como adicionar itens a uma matriz. A resposta rápida é que não é possível. Uma matriz é um tamanho fixo na memória. Se você precisar aumentá-la ou adicionar um item a ela, precisará criar uma matriz e copiar todos os valores da matriz antiga. Parece trabalhoso, no entanto, o PowerShell oculta a complexidade da criação da matriz. O PowerShell implementa o operador de adição (`+`) para matrizes.

> [!NOTE]
> O PowerShell não implementa uma operação de subtração. Se desejar uma alternativa flexível para uma matriz, você precisará usar um objeto [`List` genérico](#generic-list).

### <a name="array-addition"></a>Adição de matriz

Podemos usar o operador de adição com matrizes para criar uma matriz. Portanto, dadas estas duas matrizes:

```powershell
$first = @(
    'Zero'
    'One'
)
$second = @(
    'Two'
    'Three'
)
```

Podemos juntá-las para obter uma nova matriz.

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a>Mais igual +=

Podemos criar uma matriz no local e adicionar um item a ela da seguinte maneira:

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

Lembre-se de que sempre que usar `+=` você duplicará e criará uma matriz. Isso não é um problema para pequenos conjuntos de dados, mas não funciona bem em maior escala.

### <a name="pipeline-assignment"></a>Atribuição de pipeline

Você pode atribuir os resultados de qualquer pipeline em uma variável. Será uma matriz se contiver vários itens.

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

Normalmente, quando pensamos em usar o pipeline, consideramos os comandos de uma linha típicos do PowerShell. Podemos aproveitar o pipeline com instruções `foreach()` e outros loops. Então, em vez de adicionar itens a uma matriz em um loop, podemos soltar itens no pipeline.

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

## <a name="array-types"></a>Tipos de matriz

Por padrão, uma matriz no PowerShell é criada como um tipo `[PSObject[]]`. Isso permite que ela contenha qualquer tipo de objeto ou valor. Isso funciona porque tudo é herdado do tipo `PSObject`.

### <a name="strongly-typed-arrays"></a>Matrizes fortemente tipadas

Você pode criar uma matriz de qualquer tipo usando uma sintaxe semelhante. Quando você cria uma matriz fortemente tipada, ela só pode conter valores ou objetos do tipo especificado.

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a>ArrayList

Adicionar itens a uma matriz é uma das suas maiores limitações, mas há algumas outras coleções às quais podemos recorrer para resolver esse problema.

A `ArrayList` é normalmente uma das primeiras coisas em que pensamos quando precisamos de uma matriz mais rápida para trabalhar. Ela atua como uma matriz de objetos em todos os lugares necessários, mas lida com a adição de itens rapidamente.

Veja como criamos uma `ArrayList` e adicionamos itens a ela.

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

Estamos chamando o .NET para obter este tipo. Nesse caso, estamos usando o construtor padrão para criá-la. Em seguida, chamamos o método `Add` para adicionar um item a ela.

Usei `[void]` no início da linha para suprimir o código de retorno. Algumas chamadas .NET fazem isso e podem criar uma saída inesperada.

Se os únicos dados que você tem em sua matriz forem cadeias de caracteres, veja também como usar [StringBuilder][]. É quase a mesma coisa, mas alguns métodos são usados apenas para lidar com cadeias de caracteres. A `StringBuilder` é especialmente projetada para o desempenho.

É comum ver as pessoas migrarem para `ArrayList` de matrizes. Mas ela foi criada quando o C# não tinha suporte genérico. A `ArrayList` foi preterida para dar suporte à `List[]` genérica

### <a name="generic-list"></a>Lista genérica

Um tipo genérico é um tipo especial no C# que define uma classe generalizada e o usuário especifica os tipos de dados que ele usa quando criado. Portanto, se você quiser uma lista de números ou cadeias de caracteres, definirá que deseja uma lista de tipos `int` ou `string`.

Veja como criar uma lista de cadeias de caracteres.

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

Ou uma lista de números.

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

Podemos converter uma matriz existente em uma lista como esta, sem criar o objeto primeiro:

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

Podemos reduzir a sintaxe com a instrução `using namespace` no PowerShell 5 e em versões mais recentes. A instrução `using` precisa ser a primeira linha do seu script. Ao declarar um namespace, o PowerShell permite deixá-lo fora dos tipos de dados ao referenciá-los.

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

Isso torna a `List` muito mais utilizável.

Você tem um método `Add` semelhante disponível para você. Diferentemente de ArrayList, não há nenhum valor retornado no método `Add`. Portanto, não precisamos usar `void` para anulá-lo.

```powershell
$myList.Add(10)
```

E ainda podemos acessar os elementos como em outras matrizes.

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a>List[PSObject]

Você pode ter uma lista de qualquer tipo, mas quando não conhece o tipo dos objetos, pode usar `[List[PSObject]]` para contê-los.

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a>Remove()

A `ArrayList` e a `List[]` genérica dão suporte à remoção de itens da coleção.

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

Ao trabalhar com tipos de valor, ela remove o primeiro da lista. Você pode chamá-la repetidamente para continuar a remover esse valor. Se você tiver tipos de referência, será necessário fornecer o objeto que deseja remover.

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

O método de remoção retorna `true` caso tenha sido possível localizar e remover o item da coleção.

### <a name="more-collections"></a>Mais coleções

Há muitas outras coleções que podem ser usadas, mas essas são as melhores substituições genéricas para matriz.
Se você tiver interesse em saber mais sobre essas opções, dê uma olhada neste [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) que [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) reuniu.

## <a name="other-nuances"></a>Outras nuances

Agora que já abordei todas as principais funcionalidades, aqui estão alguns aspectos que eu queria mencionar antes de encerrar.

### <a name="pre-sized-arrays"></a>Matrizes pré-dimensionadas

Mencionei que não é possível alterar o tamanho de uma matriz depois que ela é criada. Podemos criar uma matriz de um tamanho predeterminado chamando-a com o construtor `new($size)`.

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a>Multiplicar matrizes

Um pequeno truque interessante é que você pode multiplicar uma matriz por um inteiro.

```powershell
PS> $data = @('red','green','blue')
PS> $data * 3
red
green
blue
red
green
blue
red
green
blue
```

### <a name="initialize-with-0"></a>Inicializar com 0

Um cenário comum é o desejo de criar uma matriz com todos os zeros. Se você for ter apenas inteiros, uma matriz fortemente tipada de inteiros assumirá como padrão todos os zeros.

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

Podemos usar o truque de multiplicação para fazer isso também.

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

O interessante sobre o truque de multiplicação é que você pode usar qualquer valor. Portanto, se você preferir ter `255` como valor padrão, essa seria uma boa maneira de fazer isso.

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a>Matrizes aninhadas

Uma matriz dentro de uma matriz é chamada de matriz aninhada. Não uso muito no PowerShell, mas as usei mais vezes em outras linguagens. Considere o uso de uma matriz de matrizes quando seus dados couberem em um padrão tipo grade.

Aqui estão duas maneiras de criar uma matriz bidimensional.

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

A vírgula é muito importante nesses exemplos. Forneci um exemplo anterior de uma matriz normal em várias linhas em que a vírgula era opcional. Esse não é o caso com uma matriz multidimensional.

A maneira como usamos a notação de índice muda um pouco agora que temos uma matriz aninhada. Acessaremos o valor 3 usando o `$data` acima.

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

Adicione um conjunto de colchetes para cada nível de aninhamento de matriz. O primeiro conjunto de colchetes é para a matriz mais externa e, em seguida, você continua o processo de lá.

### <a name="write-output--noenumerate"></a>Write-Output -NoEnumerate

O PowerShell gosta de desencapsular ou enumerar matrizes. Esse é um aspecto fundamental do modo como o PowerShell usa o pipeline, mas há ocasiões em que você não quer que isso aconteça.

Eu normalmente redireciono objetos para `Get-Member` a fim de saber mais sobre eles. Quando redireciono uma matriz para ele, ela é desencapsulada e Get-Member vê os membros da matriz e não a matriz real.

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

Para evitar o desencapsulamento da matriz, você pode usar `Write-Object -NoEnumerate`.

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

Tenho uma segunda forma que parece mais um ataque (e tento evitar ataques como esse). Você pode inserir uma vírgula na frente da matriz antes de redirecioná-la.

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a>Retornar uma matriz

Esse desencapsulamento de matrizes também acontece quando você gera ou retorna valores de uma função. Você ainda poderá obter uma matriz se atribuir a saída a uma variável. Portanto, isso não costuma ser um problema.

A questão é que você tem uma nova matriz. Se isso for um problema, você poderá usar `Write-Output -NoEnumerate $array` ou `return ,$array` para contorná-lo.

## <a name="anything-else"></a>Algo mais?

Sei que é muita informação a ser assimilada. Espero que você aprenda algo com este artigo toda vez que lê-lo e que ele se torne uma boa referência por muito tempo. Se você achou este conteúdo útil, compartilhe-o com outras pessoas que possam aproveitá-lo.

Daqui em diante, recomendo que você confira uma postagem semelhante que escrevi sobre [tabelas de hash][].

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[matrizes]: /powershell/module/microsoft.powershell.core/about/about_arrays
[instrução switch]: everything-about-switch.md
[tabelas de hash]: everything-about-hashtable.md
[As várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[como verificar se cada valor em uma matriz corresponde a um determinado valor]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[solução]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
