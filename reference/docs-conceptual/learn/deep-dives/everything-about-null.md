---
title: Tudo o que você queria saber sobre o $null
description: Normalmente, o $null do PowerShell parece ser simples, mas tem inúmeras nuances. Vamos examinar o $null para entender o que acontece quando nos deparamos inesperadamente com um valor nulo.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e0553a5e17450d8044f548792649369e99903850
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149469"
---
# <a name="everything-you-wanted-to-know-about-null"></a>Tudo o que você queria saber sobre o $null

Normalmente, o `$null` do PowerShell parece ser simples, mas tem inúmeras nuances. Vamos examinar o `$null` para entender o que acontece quando nos deparamos inesperadamente com um valor `$null`.

> [!NOTE]
> A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="what-is-null"></a>O que é NULL?

Você pode pensar no NULL como um valor desconhecido ou vazio. Uma variável será NULL até que você atribua um valor ou um objeto a ela. Isso pode ser importante porque há alguns comandos que exigem um valor e geram erros se o valor for NULL.

### <a name="powershell-null"></a>$null do PowerShell

O `$null` é uma variável automática do PowerShell usada para representar NULL. Você poderá atribui-la a variáveis, usá-la em comparações ou empregá-la como um espaço reservado para NULL em uma coleção.

O PowerShell trata `$null` como um objeto de valor NULL. Isso é diferente do que você pode esperar se estiver acostumado com outras linguagens.

## <a name="examples-of-null"></a>Exemplos de $null

Sempre que você tentar usar uma variável que não foi inicializada, o valor será `$null`. Essa é uma das maneiras mais comuns pelas quais os valores `$null` se infiltram em seu código.

```powershell
PS> $null -eq $undefinedVariable
True
```

Se você digitar o nome de uma variável incorretamente por engano, o PowerShell a verá como uma variável diferente e o valor atribuído será `$null`.

A outra maneira de encontrar valores `$null` é quando eles são provenientes de outros comandos que não fornecem nenhum resultado.

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a>Impacto do $null

Os valores `$null` impactam seu código de maneira diferente, dependendo do local em que aparecem.

### <a name="in-strings"></a>Em cadeias de caracteres

Se você usar o `$null` em uma cadeia de caracteres, ela será um valor em branco (ou uma cadeia de caracteres vazia).

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

Essa é uma das razões pelas quais eu gosto de colocar colchetes ao redor das variáveis ao usá-las nas mensagens de log. É ainda mais importante identificar os limites dos valores das variáveis quando o valor está ao final da cadeia de caracteres.

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

Isso torna as cadeias de caracteres vazias e os valores `$null` fáceis de identificar.

### <a name="in-numeric-equation"></a>Em equações numéricas

Quando um valor `$null` é usado em uma equação numérica, os resultados são inválidos caso não gerem erro. Às vezes, o `$null` é avaliado como `0` e outras vezes torna todo o resultado `$null`.
Aqui está um exemplo com multiplicação que fornece 0 ou `$null`, dependendo da ordem dos valores.

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a>No lugar de uma coleção

Uma coleção permite que você use um índice para acessar os valores. Se você tentar indexar uma coleção que corresponde a `null`, receberá o seguinte erro: `Cannot index into a null array`.

```powershell
PS> $value = $null
PS> $value[10]
Cannot index into a null array.
At line:1 char:1
+ $value[10]
+ ~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : NullArray
```

Se você tiver uma coleção, mas tentar acessar um elemento que não pertence à coleção, receberá `$null` como resultado.

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a>No lugar de um objeto

Se você tentar acessar uma propriedade ou uma subpropriedade de um objeto que não tem aquela propriedade especificada, obterá um valor `$null`, assim como ocorreria para uma variável indefinida. Não importa se a variável é `$null` ou um objeto real nesse caso.

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a>Método em uma expressão com valor nulo

Chamar um método em um objeto `$null` gera um `RuntimeException`.

```powershell
PS> $value = $null
PS> $value.toString()
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $value.tostring()
+ ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
```

Sempre que vejo a frase `You cannot call a method on a null-valued expression`, a primeira coisa que procuro são locais onde algum método esteja sendo chamado em uma variável sem antes verificar se ele corresponde a `$null`.

## <a name="checking-for-null"></a>Verificando se corresponde a $null

Talvez você tenha notado que eu sempre coloco o `$null` à esquerda ao verificar se corresponde a `$null` em meus exemplos. Isso é intencional e aceito como uma melhor prática do PowerShell. Há alguns cenários em que colocá-lo à direita não gera o resultado esperado.

Observe o próximo exemplo e tente prever os resultados:

```powershell
if ( $value -eq $null )
{
    'The array is $null'
}
if ( $value -ne $null )
{
    'The array is not $null'
}
```

Se eu não definir `$value`, o primeiro será avaliado como `$true` e a mensagem será `The array is $null`. A armadilha aqui é que é possível criar um `$value` que permita que ambos sejam `$false`

```powershell
$value = @( $null )
```

Nesse caso, o `$value` é uma matriz que contém um `$null`. O `-eq` verifica cada valor da matriz e retorna o `$null` com correspondência. Isso é avaliado como `$false`. O `-ne` retorna tudo que não corresponde a `$null` e, nesse caso, não há resultados (isso também é avaliado como `$false`). Nenhuma delas é `$true`, embora pareça que uma delas deveria ser.

Não só podemos criar um valor que faça com que ambos sejam avaliados como `$false`, também é possível criar um valor em que ambos sejam avaliados como `$true`. Mathias Jessen (@IISResetMe) tem uma [excelente postagem][] que explora esse cenário.

### <a name="psscriptanalyzer-and-vscode"></a>PSScriptAnalyzer e VSCode

O módulo do [PSScriptAnalyzer][] tem uma regra que verifica a ocorrência desse problema chamado `PSPossibleIncorrectComparisonWithNull`.

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

Como o VS Code também usa as regras do PSScriptAnalyser, ele realça ou identifica isso como um problema em seu script.

### <a name="simple-if-check"></a>Verificação simples

Uma forma comum pela qual as pessoas verificam um valor não $null é usando uma instrução `if()` simples sem a comparação.

```powershell
if ( $value )
{
    Do-Something
}
```

Se o valor for `$null`, isso será avaliado como `$false`. Isso é fácil de ler, mas tenha cuidado para que ele esteja procurando exatamente o que você espera que ele procure. Eu li essa linha de código como:

> Se `$value` tiver um valor.

Mas essa não é a realidade. Na verdade, a linha está dizendo:

> Se `$value` não for `$null` ou `0` ou `$false` ou um `empty string`

Aqui está um exemplo mais completo dessa instrução.

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

É perfeitamente possível usar uma verificação básica de `if`, contanto que você se lembre de que esses outros valores contam como `$false` e não apenas que uma variável tem um valor.

Eu tive esse problema ao refatorar alguns códigos há alguns dias. Ele tinha uma verificação de propriedade básica como esta.

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

Eu queria atribuir um valor à propriedade dos objetos somente se ele existisse. Na maioria dos casos, o objeto original tinha um valor que seria avaliado como `$true` na instrução `if`. Mas eu encontrei um problema em que o valor, ocasionalmente, não era definido. Eu depurei o código e descobri que o objeto tinha a propriedade, mas ela era um valor de cadeia de caracteres em branco. Isso impedia que ela fosse atualizada com a lógica anterior. Então, adicionei uma verificação de `$null` adequada e tudo funcionou.

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

São pequenos bugs como esses que são difíceis de identificar e fazem com que eu verifique de maneira agressiva se os valores correspondem a `$null`.

## <a name="nullcount"></a>$null.Count

Se você tentar acessar uma propriedade em um valor `$null`, a propriedade também será `$null`. A propriedade `count` é a exceção a essa regra.

```powershell
PS> $value = $null
PS> $value.count
0
```

Quando você tem um valor `$null`, então o `count` é `0`. Essa propriedade especial é adicionada pelo PowerShell.

### <a name="pscustomobject-count"></a>[PSCustomObject] Count

Quase todos os objetos do PowerShell têm essa propriedade Count. Uma exceção importante é o `[PSCustomObject]`, no Windows PowerShell 5.1 (isso é corrigido no PowerShell 6.0). Ele não tem a propriedade Count, então você receberá o valor `$null` se tentar usá-la. Eu chamo a atenção para isso aqui a fim de que você não tente usar `.Count` em vez de uma verificação `$null`.

A execução deste exemplo no Windows PowerShell 5.1 e no PowerShell 6.0 vai gerar resultados diferentes.

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a>Nulo vazio

Há um tipo especial de `$null` que funciona de maneira diferente dos demais. Vou chamá-lo de `$null` vazio, mas, na verdade, trata-se de um [System.Management.Automation.Internal.AutomationNull][]. Esse `$null` vazio é o que você recebe como resultado de uma função ou bloco de script que não retorna nada (um resultado nulo).

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

Se você o comparar com `$null`, receberá o valor `$null`. Quando usado em uma avaliação em que um valor seja obrigatório, o valor será sempre `$null`. Mas se você o colocr dentro de uma matriz, ele será tratado da mesma forma que uma matriz vazia.

```powershell
PS> $containempty = @( @() )
PS> $containnothing = @($nothing)
PS> $containnull = @($null)

PS> $containempty.count
0
PS> $containnothing.count
0
PS> $containnull.count
1
```

Você pode ter uma matriz que contém um valor `$null` e sua `count` será `1`. Mas se você inserir um resultado vazio dentro de uma matriz, ele não será contado como um item. A contagem será `0`.

Se você tratar o `$null` vazio como uma coleção, ela estará vazia.

### <a name="pipeline"></a>Pipeline

O principal local em que você vê a diferença é ao usar o pipeline. É possível armazenar em pipe um valor `$null`, mas não um valor `$null` vazio.

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

Dependendo do seu código, você deve considerar o `$null` em sua lógica.

Verifique se corresponde a `$null`, primeiro

- Filtrar nulo no pipeline (`... | Where {$null -ne $_} | ...`)
- Gerenciá-lo na função do pipeline

## <a name="foreach"></a>foreach

Um dos meus recursos favoritos do `foreach` é que ele não enumera em uma coleção `$null`.

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

Isso evita que eu precise verificar se a coleção corresponde a `$null` antes de enumerá-la. Se você tiver uma coleção de valores de `$null`, o `$node` ainda poderá ser `$null`.

O foreach começou a funcionar dessa forma no PowerShell 3.0. Se você estiver em uma versão mais antiga, então não será assim. Essa é uma das alterações importantes a serem observadas ao realizar a portabilidade do código para a compatibilidade com a versão 2.0.

## <a name="value-types"></a>Tipos de valor

Tecnicamente, apenas tipos de referência podem ser `$null`. Mas o PowerShell é muito generosa e permite que variáveis sejam de qualquer tipo. Se você decidir forçar a conversão de um tipo de valor, ele não poderá ser `$null`.
O PowerShell converte `$null` em um valor padrão para muitos tipos.

```powershell
PS> [int]$number = $null
PS> $number
0

PS> [bool]$boolean = $null
PS> $boolean
False

PS> [string]$string = $null
PS> $string -eq ''
True
```

Mas há alguns tipos que não têm uma conversão válida do `$null`. Esses tipos geram um erro de `Cannot convert null to type`.

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a>Parâmetros de função

Forçar a conversão de valores em parâmetros de função é algo muito comum. Em geral, aprendemos a definir os tipos de nossos parâmetros, mesmo se tivermos a tendência de não definir os tipos das outras variáveis do script. Talvez você já tenha algumas variáveis com a conversão de tipo forçada em suas funções e sequer tenha percebido.

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

Assim que você definir o tipo do parâmetro como `string`, o valor nunca mais poderá ser `$null`. É comum verificar se um valor é `$null` para ver se o usuário forneceu algum valor ou não.

```powershell
if ( $null -ne $Value ){...}
```

`$Value` é uma cadeia de caracteres `''` vazia quando nenhum valor é fornecido. Em vez disso, use a variável automática `$PSBoundParameters.Value`.

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

`$PSBoundParameters` contém apenas os parâmetros que foram especificados quando a função foi chamada.
Você também pode usar o método `ContainsKey` para verificar a propriedade.

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a>IsNotNullOrEmpty

Se o valor for uma cadeia de caracteres, você poderá usar uma função de cadeia de caracteres estática para verificar se o valor é `$null` ou uma cadeia de caracteres vazia ao mesmo tempo.

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

Eu me pego usando isso com frequência quando sei que o tipo de valor deve ser uma cadeia de caracteres.

## <a name="when-i-null-check"></a>Quando eu verifico se corresponde a $null

Eu sou um criador de scripts conservador. Sempre que eu chamo uma função e atribuo seu resultado a uma variável, eu a verifico se corresponde a `$null`.

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

Eu prefiro usar `if` ou `foreach` do que `try/catch`. Não me entenda mal, eu também uso `try/catch` com frequência. Mas se eu posso testar uma condição de erro ou um conjunto de resultados vazio, posso permitir que meu tratamento de exceção seja para exceções verdadeiras.

Também tenho a tendência de verificar se corresponde a `$null` antes de indexar um valor ou chamar métodos em um objeto. Essas duas ações falham em caso de objeto `$null`, portanto, acho importante validá-las primeiro. Já abordei esses cenários anteriormente nesta postagem.

### <a name="no-results-scenario"></a>Cenário sem resultados

É importante saber que funções e comandos diferentes gerenciam o cenário sem resultados de maneira diferente. Muitos comandos do PowerShell retornam o `$null` vazio e um erro no fluxo de erros. Mas outros geram exceções ou fornecem um objeto de status. É sua responsabilidade saber como os comandos que você usa gerenciam os cenários sem resultados e os cenários de erro.

## <a name="initializing-to-null"></a>Inicializando com $null

Um hábito que eu adquiri foi o de inicializar todas as minhas variáveis antes de usá-las. Isso é algo obrigatório em outras linguagens de programação. Na parte superior da função ou sempre no início do loop de um foreach, eu defino todos os valores que estou usando.

Aqui está um cenário que desejo examinar mais de perto contigo. É um exemplo de bug que já precisei enfrentar anteriormente.

```powershell
function Do-Something
{
    foreach ( $node in 1..6 )
    {
        try
        {
            $result = Get-Something -ID $node
        }
        catch
        {
            Write-Verbose "[$result] not valid"
        }

        if ( $null -ne $result )
        {
            Update-Something $result
        }
    }
}
```

A expectativa aqui é que `Get-Something` retorne um resultado ou um `$null` vazio. Se houver um erro, nós o registramos em um log. Em seguida, verificamos se recebemos um resultado válido antes de processá-lo.

O bug que se oculta nesse código é quando `Get-Something` gera uma exceção e não atribui um valor a `$result`. Ela falha antes da atribuição, portanto, nem chegamos a atribuir `$null` à variável `$result`. `$result` ainda contém a `$result` anterior válida, obtida em outras iterações.
`Update-Something` vai executar várias vezes no mesmo objeto neste exemplo.

Passei a definir `$result` como `$null` dentro do loop do foreach antes de usá-la para contornar esse problema.

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a>Problemas de escopo

Isso também ajuda a atenuar problemas de escopo. Nesse exemplo, atribuímos valores a `$result` repetidamente em um loop. Mas como o PowerShell permite que valores variáveis de fora da função sejam acessados no escopo da função atual, inicializá-los dentro da função atenua os bugs que podem ser introduzidos dessa maneira.

Uma variável não inicializada em sua função não será `$null` se ela estiver definida como um valor em um escopo superior.
O escopo superior pode ser outra função que chama sua função e usa os mesmos nomes de variáveis, por exemplo.

Se eu pegar o mesmo exemplo de `Do-something` e remover o loop, acabarei com algo parecido com este exemplo:

```powershell
function Invoke-Something
{
    $result = 'ParentScope'
    Do-Something
}

function Do-Something
{
    try
    {
        $result = Get-Something -ID $node
    }
    catch
    {
        Write-Verbose "[$result] not valid"
    }

    if ( $null -ne $result )
    {
        Update-Something $result
    }
}
```

Se a chamada à `Get-Something` gerar uma exceção, então minha verificação se corresponde a `$null` encontrará a `$result` de `Invoke-Something`. A inicialização do valor dentro da sua função atenua esse problema.

Dar nomes às variáveis é algo difícil, de modo que é comum um autor usar os mesmos nomes de variáveis em diferentes funções. Eu, por exemplo, uso `$node`, `$result` e `$data` o tempo todo. Portanto, é muito comum que valores de escopos diferentes acabem aparecendo em locais onde não deveriam.

## <a name="redirect-output-to-null"></a>Redirecionar a saída para $null

Tenho falado sobre valores `$null` ao longo de todo este artigo, mas o tópico não estaria completo se eu não mencionasse o redirecionamento da saída para `$null`. Há ocasiões em que determinados comandos geram informações ou objetos que você deseja suprimir. O redirecionamento da saída para `$null` faz exatamente isso.

### <a name="out-null"></a>Out-Null

O comando Out-Null é a maneira interna de redirecionar os dados do pipeline para `$null`.

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a>Atribuir $null

Você pode atribuir `$null` aos resultados de um comando para alcançar o mesmo efeito do uso de `Out-Null`.

```powershell
$null = New-Item -Type Directory -Path $path
```

Como `$null` é um valor constante, você jamais poderá substituí-lo. Não gosto da aparência dele em meus códigos, mas geralmente é executado mais rápido do que `Out-Null`.

### <a name="redirect-to-null"></a>Redirecionar para $null

Você também pode usar o operador de redirecionamento para enviar a saída para `$null`.

```powershell
New-Item -Type Directory -Path $path > $null
```

Se você estiver lidando com executáveis de linha de comando que geram saída em diferentes fluxos. Você poderá redirecionar todos os fluxos de saída para `$null` da seguinte maneira:

```powershell
git status *> $null
```

## <a name="summary"></a>Resumo

Eu abordei muitos aspectos sobre este assunto e estou ciente de que este artigo ficou mais fragmentado do que a maior parte dos meus estudos de aprofundamento. Isso ocorre porque valores `$null` podem aparecer em vários locais diferentes no PowerShell e todas as nuances são específicas ao local em que você os encontra. Espero que você saia com uma compreensão melhor do `$null` e com uma boa noção dos cenários mais obscuros que pode encontrar pela frente.

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[excelente postagem]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
