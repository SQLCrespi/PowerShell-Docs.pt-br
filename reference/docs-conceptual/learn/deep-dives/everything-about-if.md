---
title: Tudo o que você queria saber sobre a instrução if
description: Como muitas outras linguagens, o PowerShell tem instruções para executar código condicionalmente em seus scripts.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: b6bafb99bfb8ecd0152bae841e5c58d4c27ccd3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "86469745"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a>Tudo o que você queria saber sobre a instrução `if`

Como muitas outras linguagens, o PowerShell tem instruções para executar código condicionalmente em seus scripts. Uma dessas instruções é a instrução [If][]. Hoje, vamos nos aprofundar em um dos comandos mais fundamentais no PowerShell.

> [!NOTE]
> A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="conditional-execution"></a>Execução condicional

Os scripts geralmente precisam tomar decisões e executar diferentes lógicas com base nessas decisões.
Isso é o que quero dizer pela execução condicional. Você tem uma instrução ou valor a ser avaliado e executa uma seção diferente do código com base nessa avaliação. Isso é exatamente o que a instrução `if` faz.

## <a name="the-if-statement"></a>A instrução `if`

Aqui está um exemplo básico da instrução `if`:

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

A primeira coisa que a instrução `if` faz é avaliar a expressão entre parênteses. Se for avaliada como `$true`, executará o `scriptblock` nas chaves. Se o valor fosse `$false`, esse scriptblock seria ignorado.

No exemplo anterior, a instrução `if` estava apenas avaliando a variável `$condition`. Foi `$true` e teria executado o comando `Write-Output` dentro do scriptblock.

Em algumas linguagens, você pode posicionar uma única linha de código após a instrução `if` e esta é executada. Não é o caso no PowerShell. Você deverá fornecer um `scriptblock` completo com chaves para funcionar corretamente.

## <a name="comparison-operators"></a>Operadores de comparação

O uso mais comum da instrução `if` é comparar dois itens entre si. O PowerShell tem operadores especiais para cenários de comparação diferentes. Quando você usa um operador de comparação, o valor no lado esquerdo é comparado ao valor no lado direito.

### <a name="-eq-for-equality"></a>-eq para igualdade

O `-eq` faz uma verificação de igualdade entre dois valores para garantir que eles sejam iguais.

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

Neste exemplo, estou assumindo um valor conhecido de `5` e comparando com meu `$value` para ver se correspondem.

Um possível caso de uso é verificar o status de um valor antes de executar uma ação. Você pode obter um serviço e verificar se o status estava definido como em execução antes de chamar `Restart-Service`.

É comum em outras linguagens, como C#, usar `==` para igualdade (por exemplo, `5 == $value`). Mas isso não funciona com o PowerShell. Outro erro comum é usar o sinal de igual (por exemplo, `5 = $value`) que é reservado para atribuir valores para variáveis. Colocar seu valor conhecido à esquerda torna o erro mais embaraçoso.

Este operador (e outros) tem algumas variações.

- `-eq` igualdade que não diferencia maiúsculas e minúsculas
- `-ieq` igualdade que não diferencia maiúsculas e minúsculas
- `-ceq` igualdade que diferencia maiúsculas e minúsculas

### <a name="-ne-not-equal"></a>-ne diferente de

Muitos operadores têm um operador relacionado que está verificando o resultado oposto. `-ne` verifica se os valores não são iguais.

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

Use para garantir que a ação seja executada somente se o valor não for `5`. Um bom caso de uso seria verificar se um serviço está em estado de execução antes de tentar iniciá-lo.

**Variações:**

- `-ne` não igual que não diferencia maiúsculas de minúsculas
- `-ine` não igual que não diferencia maiúsculas de minúsculas
- `-cne` não igual que diferencia maiúsculas de minúsculas

São variações inversas de `-eq`. Agruparei esses tipos quando listar as variações para outros operadores.

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a>-gt -ge -lt -le para maior que ou menor que

Esses operadores são usados durante a verificação para ver se um valor é maior ou menor que outro valor.
Os `-gt -ge -lt -le` são GreaterThan, GreaterThanOrEqual, LessThan e LessThanOrEqual.

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

**Variações:**

- `-gt` maior que
- `-igt` maior que, não diferencia maiúsculas de minúsculas
- `-cgt` maior que, diferencia maiúsculas de minúsculas
- `-ge` maior que ou igual a
- `-ige` maior que ou igual a, não diferencia maiúsculas de minúsculas
- `-cge` maior que ou igual a, diferencia maiúsculas de minúsculas
- `-lt` menor que
- `-ilt` menor que, não diferencia maiúsculas de minúsculas
- `-clt` menor que, diferencia maiúsculas de minúsculas
- `-le` menor que ou igual a
- `-ile` menor que ou igual a, não diferencia maiúsculas de minúsculas
- `-cle` menor que ou igual a, diferencia maiúsculas de minúsculas

Não sei por que você usaria opções que diferenciam e não diferenciam maiúsculas de minúsculas para esses operadores.

### <a name="-like-wildcard-matches"></a>-like correspondências de caractere curinga

O PowerShell tem sua própria sintaxe de correspondência de padrões baseada em caractere curinga e você pode usá-la com o operador `-like`. Esses padrões de caractere curinga são bastante básicos.

- `?` corresponde a qualquer caractere único
- `*` corresponde a qualquer número de caracteres

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

É importante ressaltar que o padrão corresponde à cadeia de caracteres inteira. Se você precisar corresponder algo no meio da cadeia de caracteres, você precisará posicionar `*` em ambas as extremidades da cadeia de caracteres.

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

**Variações:**

- `-like` caractere curinga que não diferencia maiúsculas de minúsculas
- `-ilike` caractere curinga que não diferencia maiúsculas de minúsculas
- `-clike` caractere curinga que diferencia maiúsculas de minúsculas
- `-notlike` caractere curinga que não diferencia maiúsculas e minúsculas não correspondente
- `-inotlike` caractere curinga que não diferencia maiúsculas e minúsculas não correspondente
- `-cnotlike` caractere curinga que diferencia maiúsculas e minúsculas não correspondente

### <a name="-match-regular-expression"></a>-match expressão regular

O operador `-match` permite que você procure uma correspondência baseada em expressão regular numa cadeia de caracteres. Use quando os padrões de caractere curinga não são flexíveis o suficiente.

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

Um padrão regex corresponde a qualquer local na cadeia de caracteres por padrão. Portanto, você pode especificar uma substring de caracteres que você deseja corresponder, por exemplo:

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

Regex é uma linguagem complexa e vale a pena analisar. Falarei mais sobre `-match` e [, as várias maneiras de usar regex][] em outro artigo.

**Variações:**

- `-match` regex que não diferencia maiúsculas e minúsculas
- `-imatch` regex que não diferencia maiúsculas e minúsculas
- `-cmatch` regex que diferencia maiúsculas e minúsculas
- `-notmatch` regex que não diferencia maiúsculas e minúsculas não correspondente
- `-inotmatch` regex que não diferencia maiúsculas e minúsculas não correspondente
- `-cnotmatch` regex que diferencia maiúsculas e minúsculas não correspondente

### <a name="-is-of-type"></a>-is é tipo

Você pode verificar o tipo de um valor com o operador `-is`.

```powershell
if ( $value -is [string] )
{
    # do something
}
```

Você pode usá-lo se estiver trabalhando com classes ou aceitando vários objetos por meio do pipeline. É possível ter um serviço ou um nome de serviço como sua entrada. Verifique se você tem um serviço e busque-o apenas com o nome.

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

**Variações:**

- `-is` do tipo
- `-isnot` não é do tipo

## <a name="collection-operators"></a>Operadores de coleção

Quando você usa os operadores anteriores com um único valor, o resultado é `$true` ou `$false`. Isso é tratado de forma levemente diferente ao trabalhar com uma coleção. Cada item na coleção é avaliado e o operador retorna todos os valores avaliados como `$true`.

```powershell
PS> 1,2,3,4 -eq 3
3
```

Isso ainda funciona corretamente em uma instrução `if`. Portanto, um valor é retornado pelo operador e a instrução inteira é `$true`.

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

Há uma pequena armadilha ocultada nos detalhes que preciso destacar. Quando você usa o operador `-ne` dessa forma, é fácil analisar incorretamente a lógica de forma invertida. Usar `-ne` com uma coleção retornará `$true` se qualquer item na coleção não corresponder ao seu valor.

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

Pode parecer um truque inteligente, mas temos operadores `-contains` e `-in` que lidam com isso com mais eficiência. E `-notcontains` faz o que você espera.

### <a name="-contains"></a>-contains

O operador `-contains` procura seu valor na coleção. Assim que encontra uma correspondência, retorna `$true`.

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

Essa é a melhor maneira de ver se uma coleção contém seu valor. O uso de `Where-Object` (ou `-eq`) percorre a lista inteira toda vez e é significativamente mais lento.

**Variações:**

- `-contains` correspondência que não diferencia maiúsculas e minúsculas
- `-icontains` correspondência que não diferencia maiúsculas e minúsculas
- `-ccontains` correspondência que diferencia maiúsculas e minúsculas
- `-notcontains` não correspondência que não diferencia maiúsculas e minúsculas
- `-inotcontains` não correspondência que não diferencia maiúsculas e minúsculas
- `-cnotcontains` não correspondência que diferencia maiúsculas e minúsculas

### <a name="-in"></a>-in

O operador `-in` é exatamente como o operador `-contains`, exceto que a coleção está no lado direito.

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

**Variações:**

- `-in` correspondência que não diferencia maiúsculas e minúsculas
- `-iin` correspondência que não diferencia maiúsculas e minúsculas
- `-cin` correspondência que diferencia maiúsculas e minúsculas
- `-notin` não correspondência que não diferencia maiúsculas e minúsculas
- `-inotin` não correspondência que não diferencia maiúsculas e minúsculas
- `-cnotin` não correspondência que diferencia maiúsculas e minúsculas

## <a name="logical-operators"></a>Operadores lógicos

Os operadores lógicos são usados para inverter ou combinar outras expressões.

### <a name="-not"></a>-not

O operador `-not` inverte uma expressão de `$false` para `$true` ou de `$true` para `$false`. Aqui está um exemplo em que queremos executar uma ação quando `Test-Path` é `$false`.

```powershell
if ( -not ( Test-Path -Path $path ) )
```

A maioria dos operadores nos quais falamos tem uma variação em que você não precisa usar o operador `-not`. Mas ainda há momentos em que é útil.

### <a name="-operator"></a>! operador

Você pode usar `!` como um alias para `-not`.

```powershell
if ( -not $value ){}
if ( !$value ){}
```

Você pode ver `!` usados mais por pessoas acostumadas com outras linguagens, como C#. Prefiro digitar, pois acho difícil encontrar ao analisar rapidamente meus scripts.

### <a name="-and"></a>-and

Você pode combinar expressões com o operador `-and`. Quando você faz isso, ambos os lados precisam ser `$true` para que toda a expressão seja `$true`.

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

Nesse exemplo, `$age` deve ser 13 ou mais velho no lado esquerdo e menor que 55 no lado direito. Adicionei parênteses extras para deixar mais claro nesse exemplo, mas são opcionais, desde que a expressão seja simples. Aqui está o mesmo exemplo sem eles.

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

A avaliação ocorre da esquerda para a direita. Se o primeiro item for avaliado como `$false`, sairá antes e não executará a comparação correta. Isso é útil quando você precisa ter certeza de que um valor existe antes de usá-lo. Por exemplo, `Test-Path` gera um erro se você der a ele um caminho `$null`.

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a>-or

O `-or` permite que você especifique duas expressões e retorna `$true` se uma delas for `$true`.

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

Assim como com o operador `-and`, a avaliação ocorre da esquerda para a direita. Exceto que, se a primeira parte for `$true`, a instrução inteira será `$true` e não processará o restante da expressão.

Além disso, observe como a sintaxe funciona para esses operadores. Você precisa de duas expressões separadas. Já vi usuários tentarem fazer algo como isso `$value -eq 5 -or 6` sem perceber o erro.

### <a name="-xor-exclusive-or"></a>-xor ou exclusivo

Esse é um pouco incomum. `-xor` permite que apenas uma expressão seja avaliada como `$true`. Portanto, se ambos os itens forem `$false` ou `$true`, a expressão inteira será `$false`. Outra maneira de analisar é que a expressão só será `$true` quando os resultados da expressão forem diferentes.

O uso desse operador lógico é raro e não consigo pensar em um bom exemplo em que o usaria.

## <a name="bitwise-operators"></a>Operadores bit a bit

Os operadores bit a bit executam cálculos nos bits dentro dos valores e produzem um novo valor como resultado. Ensinar [operadores bit a bit][] está além do escopo deste artigo. Mas aqui está a lista deles.

- `-band` binário AND
- `-bor` binário OR
- `-bxor` binário OR exclusivo
- `-bnot` binário NOT
- `-shl` shift left
- `-shr` shift right

## <a name="powershell-expressions"></a>Expressões do PowerShell

Podemos usar o PowerShell normal dentro da instrução de condição.

```powershell
if ( Test-Path -Path $Path )
```

`Test-Path` retorna `$true` ou `$false` quando é executado. Isso também se aplica a comandos que retornam outros valores.

```powershell
if ( Get-Process Notepad* )
```

Será avaliado como `$true` se houver um processo retornado e `$false` se não houver nada. É perfeitamente válido usar expressões de pipeline ou outras instruções do PowerShell, por exemplo:

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

As expressões podem ser combinadas entre si com os operadores `-and` e `-or`, mas talvez você precise usar parênteses para dividi-las em subexpressões.

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a>Verificação por $null

Obter "sem resultados" ou um valor de `$null` é avaliado como `$false` na instrução `if`. Quando você verifica especificamente por `$null`, é uma melhor prática adicionar `$null` no lado esquerdo.

```powershell
if ( $null -eq $value )
```

Há algumas nuances para lidar com valores de `$null` no PowerShell. Se você estiver interessado em se aprofundar, tenho um artigo sobre [tudo o que você precisa saber sobre $null][].

### <a name="variable-assignment"></a>Atribuição de variável

[Prasoon Karunan V][] me lembrou de adicionar, pois havia esquecido.

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

Normalmente, quando você atribui um valor a uma variável, o valor não é transmitido para o pipeline ou console. Quando você faz uma atribuição de variável em uma subexpressão, ela é transmitida para o pipeline.

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

Confira como a atribuição de `$first` não tem saída e a atribuição de `$second` tem. Quando uma atribuição é feita em uma instrução `if`, é executada exatamente como a atribuição de `$second` acima. Aqui está um exemplo claro de como você pode usá-la:

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

Se `$process` for atribuído com um valor, a instrução será `$true` e `$process` será interrompido.

Certifique-se de não confundir isso com `-eq` porque não é uma verificação de igualdade. Este é um recurso mais obscuro que a maioria das pessoas não percebe como funciona.

## <a name="alternate-execution-path"></a>Alterar o caminho da execução

A instrução `if` permite que você especifique uma ação para não apenas quando a instrução é `$true`, mas também para quando é `$false`. É aí que a instrução `else` entra em cena.

### <a name="else"></a>else

A instrução `else` é sempre a última parte da instrução `if`, quando usada.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

Neste exemplo, verificamos o `$path` para garantir que é um arquivo. Se encontrarmos o arquivo, nós o moveremos. Caso contrário, devemos escrever um aviso. Esse tipo de lógica de ramificação é muito comum.

### <a name="nested-if"></a>if aninhado

As instruções `if` e `else` usam um scriptblock. Portanto, podemos adicionar qualquer comando do PowerShell, incluindo outra instrução `if`. Isso permite que você use uma lógica muito mais complicada.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

Neste exemplo, testamos primeiro o caminho feliz e depois executamos uma ação nele. Se falhar, faremos outra verificação e forneceremos informações mais detalhadas para o usuário.

### <a name="elseif"></a>elseif

Não estamos limitados a apenas uma única verificação condicional. Podemos encadear instruções `if` e `else` juntas em vez de aninhar usando a instrução `elseif`.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

A execução ocorre de cima para baixo. A instrução `if` superior é avaliada primeiro. Se for `$false`, passará para a próxima `elseif` ou `else` na lista. A última `else` será a ação padrão a ser tomada se nenhuma das outras retornar `$true`.

### <a name="switch"></a>switch

Neste ponto, preciso mencionar a instrução `switch`. Fornece uma sintaxe alternativa para fazer várias comparações com um valor. Com `switch`, você especifica uma expressão, e esse resultado é comparado com vários valores diferentes. Se um dos valores corresponder, o bloco de código correspondente será executado. Veja este exemplo:

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

Há três valores possíveis que podem corresponder à `$itemType`. Nesse caso, corresponde com `Role`. Usei um exemplo simples apenas para mostrar a você um pouco do operador `switch`. Falarei mais sobre [tudo o que você queria saber sobre a instrução switch][] em outro artigo.

## <a name="pipeline"></a>Pipeline

O pipeline é um recurso exclusivo e importante do PowerShell. Qualquer valor que não seja suprimido ou atribuído a uma variável será colocado no pipeline. O `if` fornece uma maneira de aproveitar o pipeline de uma forma que nem sempre é óbvia.

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

Cada scriptblock está colocando os resultados dos comandos ou do valor no pipeline. Em seguida, atribuímos o resultado da instrução `if` à variável `$discount`. Esse exemplo poderia ser tão facilmente atribuído aos valores para a variável `$discount` diretamente em cada scriptblock. Não posso dizer que uso com a instrução `if` com frequência, mas tenho um exemplo onde usei recentemente.

### <a name="array-inline"></a>Matriz embutida

Tenho uma função chamada [Invoke-SnowSql][] que inicia um executável com vários argumentos de linha de comando. Aqui está um clipe da função em que crio a matriz de argumentos.

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

As variáveis `$Debug` e `$Path` são parâmetros na função fornecida pelo usuário final.
Posso avaliar embutidos dentro da inicialização da minha matriz. Se `$Debug` for true, os valores estarão no `$snowSqlParam` no local correto. O mesmo se aplica à variável `$Path`.

## <a name="simplify-complex-operations"></a>Simplificar operações complexas

É inevitável enfrentar situações em que haja muitas comparações a serem verificadas e a instrução `If` fique na extremidade direita da tela.

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

Podem ser difíceis de ler e que o tornam mais propenso a cometer erros. Há algumas coisas que podemos fazer sobre isso.

### <a name="line-continuation"></a>Continuação de linha

Há alguns operadores no PowerShell que permitem encapsular o comando na próxima linha. Os operadores lógicos `-and` e `-or` serão bons operadores para serem usados se você quiser dividir a expressão em várias linhas.

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

Ainda há muita coisa acontecendo, mas colocar cada peça em sua própria linha faz uma grande diferença.
Geralmente uso quando obtenho mais de duas comparações ou se preciso rolar para a direita para ler qualquer uma das lógicas.

### <a name="pre-calculating-results"></a>Pré-calcular resultados

Podemos retirar essa instrução da instrução `if` e verificar apenas o resultado.

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

Isso parecerá muito mais limpo que o exemplo anterior. Você também terá a oportunidade de usar um nome de variável que explica o que você está realmente verificando. Também é um exemplo de código de autodocumentação que evita comentários desnecessários.

### <a name="multiple-if-statements"></a>Várias instruções if

Podemos dividir em várias instruções e verificar uma de cada vez. Neste caso, usamos um sinalizador ou uma variável de rastreamento para combinar os resultados.

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

Precisei inverter a lógica para fazer com que a lógica do sinalizador funcionasse corretamente. Cada avaliação é uma instrução `if` individual. A vantagem disso é que, quando você estiver depurando, poderá dizer exatamente o que a lógica está fazendo. Ao mesmo tempo, consegui adicionar um detalhamento muito melhor.

A desvantagem óbvia é que há muito mais código a ser escrito. O código é mais complexo de examinar, pois usa uma única linha de lógica e a detalha em 25 ou mais linhas.

### <a name="using-functions"></a>Usar funções

Também podemos mover toda a lógica de validação para uma função. Veja rapidamente como parece limpo.

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

Você ainda precisará criar a função para fazer a validação, mas torna o código muito mais fácil para trabalhar. Torna o teste do código mais fácil. Em seus testes, você pode simular a chamada para `Test-ADDriveConfiguration` e só precisa de dois testes para essa função. Um onde retorna `$true` e outro onde retorna `$false`. Testar a outra função é mais simples porque é muito pequena.

O corpo dessa função ainda pode ser aquele de uma linha que começamos ou a lógica explodida que usamos na última seção. Isso funciona bem para ambos os cenários e permite que você altere facilmente a implementação posteriormente.

## <a name="error-handling"></a>Tratamento de erros

Um uso importante da instrução `if` é verificar as condições de erro antes de encontrar erros. Um bom exemplo é verificar se já existe uma pasta antes de tentar criá-la.

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

Se você espera que uma exceção aconteça, não é realmente uma exceção. Portanto, verifique os valores e valide as condições quando possível.

Se você quiser se aprofundar mais no tratamento de exceções, tenho um artigo sobre [tudo o que você quis saber sobre exceções][].

## <a name="final-words"></a>Conclusão

A instrução `if` é uma instrução simples, mas é uma parte fundamental do PowerShell. Você se encontrará usando-a várias vezes em quase todos os scripts que escrever. Espero que você tenha um entendimento melhor do que antes.

<!-- link references -->
[versão original]: https://powershellexplained.com/2019-08-11-Powershell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if
[operadores bit a bit]: /powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[, as várias maneiras de usar regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[tudo o que você quis saber sobre exceções]: everything-about-exceptions.md
[tudo o que você precisa saber sobre $null]: everything-about-null.md
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[tudo o que você queria saber sobre a instrução switch]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
