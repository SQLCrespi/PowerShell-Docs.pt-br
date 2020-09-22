---
title: Tudo o que você queria saber sobre as tabelas de hash
description: As tabelas de hash são muito importantes no PowerShell, portanto, é bom entendê-las bem.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: c67f00911b6c9d05fa9b5b5a700bbae795cf9244
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85353814"
---
# <a name="everything-you-wanted-to-know-about-hashtables"></a>Tudo o que você queria saber sobre as tabelas de hash

Quero voltar um pouco e falar sobre as [tabelas de hash][]. Eu as utilizo o tempo todo agora. Eu estava ensinando alguém sobre elas após nossa reunião de grupo de usuários na noite passada e percebi que já tive a mesma dúvida sobre esse assunto. As tabelas de hash são muito importantes no PowerShell, portanto, é bom entendê-las bem.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="hashtable-as-a-collection-of-things"></a>A tabela de hash como uma coleção de coisas

Primeiro, quero que você enxergue a **tabela de hash** como uma coleção, conforme a definição tradicional desse recurso. Essa definição proporciona uma compreensão fundamental de como elas funcionam, e isso será muito útil ao empregá-las para coisas mais avançadas no futuro. Pular essa compreensão fundamental, muitas vezes, pode gerar confusão.

## <a name="what-is-an-array"></a>O que é uma matriz?

Antes de falar sobre o que é uma **tabela de hash** eu preciso mencionar as [matrizes][]. No âmbito desta discussão, a matriz é uma lista ou coleção de valores ou objetos.

```powershell
$array = @(1,2,3,5,7,11)
```

Depois de armazenar seus itens em uma matriz, você poderá usar o `foreach` para percorrer cada elemento da matriz sequencialmente ou poderá usar um índice para acessar cada elemento da matriz individualmente.

```powershell
foreach($item in $array)
{
    Write-Output $item
}

Write-Output $array[3]
```

Você também pode atualizar valores usando um índice da mesma maneira.

```powershell
$array[2] = 13
```

Isso é apenas uma breve introdução sobre as matrizes, mas é suficiente para contextualizá-las e permitir que nos aprofundemos nas tabelas de hash.

## <a name="what-is-a-hashtable"></a>O que é uma tabela de hash?

Vamos começar com uma descrição técnica básica do que são as tabelas de hash no sentido geral e depois veremos as outras formas de uso exploradas pelo PowerShell.

Uma tabela de hash é uma estrutura de dados muito parecida com uma matriz, exceto pelo fato de que você armazena cada valor (objeto) usando uma chave. Trata-se de um esquema de armazenamento básico de chave/valor. Primeiro, criamos uma tabela de hash vazia.

```powershell
$ageList = @{}
```

Observe que usamos chaves, em vez de parênteses, para definir uma tabela de hash. Em seguida, adicionamos um item usando uma chave, da seguinte maneira:

```powershell
$key = 'Kevin'
$value = 36
$ageList.add( $key, $value )

$ageList.add( 'Alex', 9 )
```

O nome da pessoa é a chave e a idade da pessoa é o valor que queremos salvar.

## <a name="using-the-brackets-for-access"></a>Usando os colchetes para acesso

Depois de adicionar os valores desejados à tabela de hash, você poderá acessá-los novamente por meio das mesmas chaves (em vez de usar índices numéricos, como é feito nas matrizes).

```powershell
$ageList['Kevin']
$ageList['Alex']
```

Quando queremos recuperar a idade de Kevin, usamos o nome dele para poder acessá-la. Também podemos usar essa abordagem para adicionar ou atualizar valores na tabela de hash. Isso é exatamente como usar a função `add()` acima.

```powershell
$ageList = @{}

$key = 'Kevin'
$value = 36
$ageList[$key] = $value

$ageList['Alex'] = 9
```

Há também outra sintaxe que pode ser usada para acessar e atualizar os valores armazenados em uma tabela de hash, mas será abordada em uma seção futura. Se você estiver chegando ao PowerShell após trabalhar com outras linguagens, esses exemplos deverão corresponder à forma como você pode ter usado as tabelas de hash no passado.

### <a name="creating-hashtables-with-values"></a>Criando tabelas de hash com valores

Até o momento, criamos apenas uma tabela de hash vazia para esses exemplos. Você pode preencher previamente as chaves e os valores ao criar tabelas de hash.

```powershell
$ageList = @{
    Kevin = 36
    Alex  = 9
}
```

### <a name="as-a-lookup-table"></a>Como uma tabela de pesquisa

O grande benefício desse tipo de tabela de hash é que podemos usá-lo como uma tabela de pesquisa. Veja um exemplo simples.

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}

$server = $environments[$env]
```

Neste exemplo, você especifica um ambiente para a variável `$env` e ela escolherá o servidor correto. Você pode usar uma `switch($env){...}` para esse tipo de seleção, mas a tabela de hash é uma opção interessante.

E fica ainda melhor quando você cria dinamicamente a tabela de pesquisa para uso posterior. Então, pense em usar essa abordagem quando precisar fazer a referência cruzada de algo. Acho que veríamos ainda mais esse cenário se o PowerShell não fosse tão bom na filtragem no pipe com `Where-Object`. Se, em algum momento, você se encontrar em uma situação em que o desempenho é importante, essa abordagem deve ser considerada.

Não vou afirmar categoricamente que é mais rápida em todos os casos, mas se encaixa na seguinte regra geral: [Se o desempenho for importante, teste-o][].

#### <a name="multiselection"></a>Seleção múltipla

De modo geral, uma tabela de hash equivale a um conjunto de pares de chave/valor em que você fornece uma chave e obtém um valor. O PowerShell permite que você forneça uma matriz de chaves para obter vários valores.

```powershell
$environments[@('QA','DEV')]
$environments[('QA','DEV')]
$environments['QA','DEV']
```

Neste exemplo, usamos a mesma tabela de hash de pesquisa acima e fornecemos três estilos de matriz diferentes para obter os valores correspondentes. Essa é uma joia preciosa do PowerShell que a maioria das pessoas não conhece.

## <a name="iterating-hashtables"></a>Percorrendo os elementos das tabelas de hash

Como uma tabela de hash é uma coleção de pares de chave/valor, você percorre seus elementos de maneira diferente do que faria com uma matriz ou uma lista normal de itens.

A primeira coisa a ser observada é que, se você armazenar a tabela de hash em um pipe, ele a tratará como apenas um objeto.

```powershell
PS> $ageList | Measure-Object
count : 1
```

Embora a propriedade `.count` informe quantos valores ela contém.

```powershell
PS> $ageList.count
2
```

Você contorna esse problema usando a propriedade `.values`, se tudo o que você precisa são os valores.

```powershell
PS> $ageList.values | Measure-Object -Average
Count   : 2
Average : 22.5
```

Em geral, é mais útil enumerar as chaves e usá-las para acessar os valores.

```powershell
PS> $ageList.keys | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_, $ageList[$_]
    Write-Output $message
}
Kevin is 36 years old
Alex is 9 years old
```

Aqui está o mesmo exemplo com um loop do `foreach(){...}`.

```powershell
foreach($key in $ageList.keys)
{
    $message = '{0} is {1} years old' -f $key, $ageList[$key]
    Write-Output $message
}
```

Estamos percorrendo cada chave da tabela de hash e, em seguida, usando-a para acessar o valor correspondente. Esse é um padrão comum ao trabalhar com as tabelas de hash como coleção.

### <a name="getenumerator"></a>GetEnumerator()

Isso nos leva ao `GetEnumerator()` para percorrer os elementos da nossa tabela de hash.

```powershell
$ageList.GetEnumerator() | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_.key, $_.value
    Write-Output $message
}
```

O enumerador fornece cada par de chave/valor, um após o outro. Ele foi projetado especificamente para esse caso de uso. Agradeço a [Mark Kraus](https://get-PowerShellblog.blogspot.com) por me lembrar disso.

### <a name="badenumeration"></a>BadEnumeration

Um detalhe importante é que não podemos modificar uma tabela de hash enquanto ela está sendo enumerada. Se começarmos com nosso exemplo básico do `$environments`:

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}
```

E a tentativa de definir toda chave ao mesmo valor do servidor não funciona.

```powershell
$environments.Keys | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}

An error occurred while enumerating through a collection: Collection was modified; enumeration operation may not execute.
+ CategoryInfo          : InvalidOperation: tableEnumerator:HashtableEnumerator) [], RuntimeException
+ FullyQualifiedErrorId : BadEnumeration
```

Isso também não vai funcionar, embora pareça que não haja problema:

```powershell
foreach($key in $environments.keys) {
    $environments[$key] = 'SrvDev03'
}

Collection was modified; enumeration operation may not execute.
    + CategoryInfo          : OperationStopped: (:) [], InvalidOperationException
    + FullyQualifiedErrorId : System.InvalidOperationException
```

O truque para essa situação é clonar as chaves antes de fazer a enumeração.

```powershell
$environments.Keys.Clone() | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}
```

## <a name="hashtable-as-a-collection-of-properties"></a>A tabela de hash como uma coleção de propriedades

Até agora, os objetos que colocamos em nossa tabela de hash eram todos do mesmo tipo. Usamos a idade nos exemplos anteriores e a chave era o nome da pessoa. Essa é uma excelente abordagem quando cada objeto da coleção em questão tem um nome exclusivo. Outra forma comum de usar as tabelas de hash no PowerShell é manter uma coleção de propriedades em que a chave é o nome da propriedade. Vamos analisar essa ideia no próximo exemplo.

### <a name="property-based-access"></a>Acesso baseado na propriedade

O uso do acesso baseado na propriedade altera a dinâmica das tabelas de hash e a forma como você pode usá-las no PowerShell. Aqui está nosso exemplo anterior, mas agora usando as propriedades como chaves.

```powershell
$ageList = @{}
$ageList.Kevin = 35
$ageList.Alex = 9
```

Assim como aconteceu nos exemplos acima, aqui também as chaves são adicionadas caso ainda não existam na tabela de hash. Dependendo da forma como você define suas chaves e de quais são seus valores, essa abordagem pode parecer perfeita ou pode soar um pouco estranha. O exemplo da lista de idades funcionou muito até esse ponto. Porém, daqui em diante, vamos precisar de um novo exemplo para que as coisas soem mais naturais.

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
```

E podemos adicionar e acessar atributos no `$person` dessa forma.

```powershell
$person.city = 'Austin'
$person.state = 'TX'
```

De repente, essa tabela de hash começa a se parecer e se comportar como um objeto. Ainda é uma coleção de coisas, portanto, todos os exemplos acima ainda se aplicam. Nós apenas a abordamos sob um ponto de vista diferente.

### <a name="checking-for-keys-and-values"></a>Verificando chaves e valores

Na maioria dos casos, você pode apenas testar o valor com algo assim:

```powershell
if( $person.age ){...}
```

É algo simples, mas que já foi a fonte de muitos bugs para mim, pois minha lógica estava ignorando um detalhe importante. Comecei a usá-lo para testar se uma chave estava presente. Quando o valor era `$false` ou zero, inesperadamente essa instrução retornava `$false`.

```powershell
if( $person.age -ne $null ){...}
```

Isso contorna o problema para valores iguais a zero, mas não para chaves $null vs. não existentes. Na maioria das vezes você não precisa fazer essa distinção, mas há funções específicas para ajudar nas situações em que você precisa.

```powershell
if( $person.ContainsKey('age') ){...}
```

Também temos um `ContainsValue()` para situações em que você precisa testar um valor sem conhecer a chave ou percorrer a coleção inteira.

### <a name="removing-and-clearing-keys"></a>Removendo e limpando as chaves

Você pode remover as chaves com a função `.Remove()`.

```powershell
$person.remove('age')
```

Atribuir a eles um valor `$null` apenas deixa você com uma chave que tem o valor `$null`.

Uma forma comum de limpar uma tabela de hash é simplesmente inicializá-la como uma tabela de hash vazia.

```powershell
$person = @{}
```

Embora esse método funcione, vamos tentar usar a função `clear()` em vez dele.

```powershell
$person.clear()
```

Esse é um daqueles casos em que o uso da função cria um código autoexplicativo, que deixa suas intenções muito claras.

## <a name="all-the-fun-stuff"></a>Todas as coisas divertidas

### <a name="ordered-hashtables"></a>Tabelas de hash ordenadas

Por padrão, as tabelas de hash não são ordenadas (nem classificadas). No contexto tradicional, a ordem não importa quando sempre usamos uma chave para acessar os valores. Você pode descobrir que deseja manter as propriedades na ordem em que as definiu. Felizmente, há uma forma de fazer isso com a palavra-chave `ordered`.

```powershell
$person = [ordered]@{
    name = 'Kevin'
    age  = 36
}
```

Agora, quando você enumera as chaves e os valores, eles permanecem naquela ordem.

### <a name="inline-hashtables"></a>Tabelas de hash embutidas

Quando você estiver definindo uma tabela de hash em uma linha, poderá separar os pares de chave/valor com um ponto-e-vírgula.

```powershell
$person = @{ name = 'kevin'; age = 36; }
```

Isso poderá ser útil se você estiver criando os pares no pipe.

### <a name="custom-expressions-in-common-pipeline-commands"></a>Expressões personalizadas em comandos de pipeline comuns

Há alguns cmdlets que dão suporte ao uso de tabelas de hash para criar propriedades personalizadas ou calculadas. Normalmente vemos isso com `Select-Object` e `Format-Table`. As tabelas de hash têm uma sintaxe especial parecida com essa quando totalmente expandidas.

```powershell
$property = @{
    name = 'totalSpaceGB'
    expression = { ($_.used + $_.free) / 1GB }
}
```

`name` é o rótulo que o cmdlet daria para essa coluna. `expression` é um bloco de script executado, onde `$_` é o valor do objeto no pipe. Aqui está esse script em ação:

```powershell
$drives = Get-PSDrive | Where Used
$drives | Select-Object -Properties name, $property

Name     totalSpaceGB
----     ------------
C    238.472652435303
```

Coloquei em uma variável, mas poderia facilmente ter sido definido embutido e você poderia ter encurtado de `name` para `n` e de `expression` para `e` enquanto estivesse lá.

```powershell
$drives | Select-Object -properties name, @{n='totalSpaceGB';e={($_.used + $_.free) / 1GB}}
```

Particularmente, eu não gosto porque deixa os comandos muito longos e geralmente ocasionam comportamentos indevidos (que prefiro não detalhar aqui). É mais provável que eu crie uma nova tabela de hash ou um `pscustomobject` com todos os campos e as propriedades que eu quiser em vez de usar essa abordagem em meus scripts. Mas há muitos códigos por aí que usam isso, então, achei válido mostrar aqui. Falarei sobre a criação de um `pscustomobject` mais adiante.

### <a name="custom-sort-expression"></a>Expressão de classificação personalizada

Será fácil classificar uma coleção se os objetos tiverem os dados pelos quais você deseja classificar. Você pode adicionar os dados ao objeto antes de classificá-los ou criar uma expressão personalizada para `Sort-Object`.

```powershell
Get-ADUser | Sort-Object -Parameter @{ e={ Get-TotalSales $_.Name } }
```

Neste exemplo, eu pego uma lista de usuários e uso algum cmdlet personalizado para obter informações adicionais apenas para a classificação.

#### <a name="sort-a-list-of-hashtables"></a>Classificar uma lista de tabelas de hash

Se você tiver uma lista de tabelas de hash que deseja classificar, descobrirá que o `Sort-Object` não trata suas chaves como propriedades. Podemos contornar isso usando uma expressão de classificação personalizada.

```powershell
$data = @(
    @{name='a'}
    @{name='c'}
    @{name='e'}
    @{name='f'}
    @{name='d'}
    @{name='b'}
)

$data | Sort-Object -Property @{e={$_.name}}
```

## <a name="splatting-hashtables-at-cmdlets"></a>Fracionando as tabelas de hash em cmdlets

Essa é uma das coisas que mais gosto nas tabelas de hash e muitas pessoas demoram para descobrir.
A ideia é que, em vez de atribuir todas as propriedades a um cmdlet em uma linha, você possa compactá-las em uma tabela de hash primeiro. Então, você pode fornecer a tabela de hash à função de maneira especial.
Aqui está um exemplo de como criar um escopo DHCP da maneira normal.

```powershell
Add-DhcpServerv4Scope -Name 'TestNetwork' -StartRange'10.0.0.2' -EndRange '10.0.0.254' -SubnetMask '255.255.255.0' -Description 'Network for testlab A' -LeaseDuration (New-TimeSpan -Days 8) -Type "Both"
```

Sem usar o [fracionamento][], todas essas coisas precisam ser definidas em uma só linha. Ou as informações rolam para fora da tela ou são quebradas em algum ponto arbitrário. Agora, compare isso com um comando que usa o fracionamento.

```powershell
$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    SubnetMask  = '255.255.255.0'
    Description = 'Network for testlab A'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}
Add-DhcpServerv4Scope @DHCPScope
```

O uso do sinal `@` em vez do `$` é o que invoca a operação de fracionamento.

Reserve um tempo para contemplar como é fácil ler o exemplo. São exatamente o mesmo comando, com todos os valores iguais. O segundo é mais fácil de entender e manter no futuro.

Eu uso o fracionamento sempre que o comando ficar muito longo. Eu o considero muito longo quando ultrapassa o limite da janela, sendo necessário rolar a tela para a direita. Se eu usar três propriedades por função, é provável que eu a reescreva usando uma tabela de hash com fracionamento.

### <a name="splatting-for-optional-parameters"></a>Fracionamento para parâmetros opcionais

Uma das maneiras mais comuns de usar o fracionamento é ao lidar com parâmetros opcionais que vêm de algum outro lugar do script. Vamos supor que eu tenha uma função que quebre a linha de uma chamada de `Get-CIMInstance` com um argumento opcional `$Credential`.

```powershell
$CIMParams = @{
    ClassName = 'Win32_Bios'
    ComputerName = $ComputerName
}

if($Credential)
{
    $CIMParams.Credential = $Credential
}

Get-CIMInstance @CIMParams
```

Eu começo criando a tabela de hash com parâmetros comuns. Então, eu adiciono o `$Credential` se ele existe.
Como estou usando o fracionamento aqui, só preciso ter a chamada para `Get-CIMInstance` no meu código uma vez. Esse padrão de design é muito limpo e pode manipular muitos parâmetros opcionais com facilidade.

Para ser justo, você pode gravar seus comandos para permitir `$null` valores como parâmetro. Nem sempre você tem controle sobre os outros comandos que está chamando.

### <a name="multiple-splats"></a>Várias frações

Você pode fracionar várias tabelas de hash para o mesmo cmdlet. Se revisitarmos nosso exemplo original de fracionamento:

```powershell
$Common = @{
    SubnetMask  = '255.255.255.0'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}

$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    Description = 'Network for testlab A'
}

Add-DhcpServerv4Scope @DHCPScope @Common
```

Usarei esse método quando tiver um conjunto comum de parâmetros sendo passados para vários comandos.

### <a name="splatting-for-clean-code"></a>Fracionamento para organização do código

Não há nada de errado com o fracionamento de um só parâmetro se isso tornar o código mais organizado.

```powershell
$log = @{Path = '.\logfile.log'}
Add-Content "logging this command" @log
```

### <a name="splatting-executables"></a>Fracionando executáveis

O fracionamento também funciona em alguns executáveis que usam a sintaxe `/param:value`. `Robocopy.exe`, por exemplo, tem alguns parâmetros como esse.

```powershell
$robo = @{R=1;W=1;MT=8}
robocopy source destination @robo
```

Não sei se isso é tão útil, mas achei muito interessante.

## <a name="adding-hashtables"></a>Adicionando tabelas de hash

As tabelas de hash dão suporte ao operador de adição a fim de combinar duas tabelas de hash.

```powershell
$person += @{Zip = '78701'}
```

Isso só funcionará se as duas tabelas de hash não compartilharem uma mesma chave.

## <a name="nested-hashtables"></a>Tabelas de hash aninhadas

Podemos usar tabelas de hash como valores dentro de uma tabela de hash.

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
$person.location = @{}
$person.location.city = 'Austin'
$person.location.state = 'TX'
```

Começamos com uma tabela de hash básica contendo duas chaves. Adicionamos uma chave chamada `location`, com uma tabela de hash vazia. Depois, adicionamos os dois últimos itens a essa tabela de hash `location`. Também podemos fazer tudo isso de maneira embutida.

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
    location = @{
        city  = 'Austin'
        state = 'TX'
    }
}
```

Isso cria a mesma tabela de hash que vimos acima e permite acessar as propriedades da mesma maneira.

```powershell
$person.location.city
Austin
```

Há várias maneiras de abordar a estrutura de seus objetos. Aqui está uma segunda maneira de examinar uma tabela de hash aninhada.

```powershell
$people = @{
    Kevin = @{
        age  = 36
        city = 'Austin'
    }
    Alex = @{
        age  = 9
        city = 'Austin'
    }
}
```

Deste modo, estaríamos combinando o conceito de tabelas de hash como coleção de objetos e como coleção de propriedades. Os valores ainda são fáceis de acessar, mesmo quando são aninhados por meio de qualquer abordagem que você preferir.

```powershell
PS> $people.kevin.age
36
PS> $people.kevin['city']
Austin
PS> $people['Alex'].age
9
PS> $people['Alex']['City']
Austin
```

Eu costumo usar a propriedade do ponto quando estou tratando como uma propriedade. Normalmente, essas são as coisas que defino estaticamente em meu código e que conheço de cor e salteado. Se for preciso percorrer a lista ou acessar programaticamente as chaves, usamos os colchetes para fornecer o nome da chave.

```powershell
foreach($name in $people.keys)
{
    $person = $people[$name]
    '{0}, age {1}, is in {2}' -f $name, $person.age, $person.city
}
```

Ter a capacidade de aninhar tabelas de hash oferece muita flexibilidade e opções.

### <a name="looking-at-nested-hashtables"></a>Examinando as tabelas de hash aninhadas

Assim que começar a aninhar tabelas de hash, você precisará de uma forma fácil de examiná-las por meio do console. Se eu executar essa última tabela de hash, receberei uma saída parecida com a seguinte (e essa é a profundidade que ela alcança):

```powershell
PS> $people
Name                           Value
----                           -----
Kevin                          {age, city}
Alex                           {age, city}
```

Meu comando preferido para examinar essas coisas é o `ConvertTo-JSON`, pois ele é muito organizado e, com frequência, uso o JSON para outras coisas.

```powershell
PS> $people | ConvertTo-Json
{
    "Kevin":  {
                "age":  36,
                "city":  "Austin"
            },
    "Alex":  {
                "age":  9,
                "city":  "Austin"
            }
}
```

Mesmo que você não conheça o JSON, você deve ser capaz de enxergar o que está procurando. Há um comando `Format-Custom` para dados estruturados como estes, mas eu ainda prefiro a exibição do JSON.

## <a name="creating-objects"></a>Criando objetos

Às vezes, você só precisa ter um objeto e usar uma tabela de hash para armazenar propriedades simplesmente não é o bastante. Normalmente, você deseja ver as chaves como nomes de coluna. Uma `pscustomobject` facilita esse processo.

```powershell
$person = [pscustomobject]@{
    name = 'Kevin'
    age  = 36
}

$person

name  age
----  ---
Kevin  36
```

Mesmo que você não a crie como uma `pscustomobject` inicialmente, sempre será possível convertê-la depois, quando necessário.

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}

[pscustomobject]$person

name  age
----  ---
Kevin  36
```

Eu tenho um artigo detalhado sobre [pscustomobject][] que você deve ler após o presente documento. Ele se baseia em muitas coisas aprendidas aqui.

## <a name="reading-and-writing-hashtables-to-file"></a>Lendo e gravando tabelas de hash em arquivo

### <a name="saving-to-csv"></a>Salvando em CSV

A dificuldade de conseguir salvar uma tabela de hash em um arquivo CSV é uma das dificuldades a que me referia acima. Converta sua tabela de hash em uma `pscustomobject` e ela será salva corretamente em CSV. Ajuda se você começar com uma `pscustomobject` para que a ordem das colunas seja preservada. Mas você poderá convertê-la em um `pscustomobject` embutido, se necessário.

```powershell
$person | ForEach-Object{ [pscustomobject]$_ } | Export-CSV -Path $path
```

Novamente, confira meu artigo sobre como usar um [pscustomobject][].

### <a name="saving-a-nested-hashtable-to-file"></a>Salvando uma tabela de hash aninhada em arquivo

Se eu precisar salvar uma tabela de hash aninhada em um arquivo e lê-la novamente, usarei os cmdlets JSON para fazer isso.

```powershell
$people | ConvertTo-JSON | Set-Content -Path $path
$people = Get-Content -Path $path -Raw | ConvertFrom-JSON
```

Há dois pontos importantes sobre esse método. O primeiro é que o JSON é gravado em várias linhas, portanto, preciso usar a opção `-Raw` para lê-lo de volta em uma única cadeia de caracteres. O segundo é que o objeto importado não é mais uma `[hashtable]`. Agora é um `[pscustomobject]` e isso poderá causar problemas se você estiver esperando.

Observe as tabelas de hash profundamente aninhadas. Ao convertê-las em JSON, você pode não obter os resultados esperados.

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json

{
  "a": {
    "b": {
      "c": "System.Collections.Hashtable"
    }
  }
}
```

Use o parâmetro **Depth** para garantir que você expandiu todas as tabelas de hash aninhadas.

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json -Depth 3

{
  "a": {
    "b": {
      "c": {
        "d": "e"
      }
    }
  }
}
```

Se precisar que ele seja uma `[hashtable]` na importação, será necessário usar os comandos `Export-CliXml` e `Import-CliXml`.

### <a name="converting-json-to-hashtable"></a>Convertendo um JSON em uma tabela de hash

Se você precisa converter um JSON em uma `[hashtable]`, eu conheço apenas uma forma de fazer isso com o [JavaScriptSerializer][] no .NET.

```powershell
[Reflection.Assembly]::LoadWithPartialName("System.Web.Script.Serialization")
$JSSerializer = [System.Web.Script.Serialization.JavaScriptSerializer]::new()
$JSSerializer.Deserialize($json,'Hashtable')
```

A partir do PowerShell v6, o suporte a JSON usa o NewtonSoft JSON.NET e adiciona suporte à tabela de hash.

```powershell
'{ "a": "b" }' | ConvertFrom-Json -AsHashtable

Name      Value
----      -----
a         b
```

O PowerShell 6.2 adicionou o parâmetro**Depth** a `ConvertFrom-Json`. O padrão **Depth** é 1024.

### <a name="reading-directly-from-a-file"></a>Lendo diretamente de um arquivo

Se você tem um arquivo que contém uma tabela de hash usando a sintaxe do PowerShell, há uma forma de importá-lo diretamente.

```powershell
$content = Get-Content -Path $Path -Raw -ErrorAction Stop
$scriptBlock = [scriptblock]::Create( $content )
$scriptBlock.CheckRestrictedLanguage( $allowedCommands, $allowedVariables, $true )
$hashtable = ( & $scriptBlock )
```

Isso importará o conteúdo do arquivo para um `scriptblock` e, em seguida, verificará se não contém outros comandos do PowerShell antes de executá-lo.

Nessa observação, você sabia que um manifesto de módulo (o arquivo psd1) é apenas uma tabela de hash?

## <a name="keys-can-be-any-object"></a>As chaves podem ser qualquer objeto

Na maioria das vezes, as chaves são apenas cadeias de caracteres. Podemos colocar qualquer coisa entre aspas e transformar essa coisa em uma chave.

```powershell
$person = @{
    'full name' = 'Kevin Marquette'
    '#' = 3978
}
$person['full name']
```

Você pode fazer algumas coisas estranhas que talvez não soubesse que podia.

```powershell
$person.'full name'

$key = 'full name'
$person.$key
```

Só porque você é capaz de fazer algo, isso não significa que você deva fazê-lo. Essa última parece um bug pronto para acontecer e seria facilmente mal interpretada por qualquer pessoa que estivesse lendo seu código.

Tecnicamente, as chaves não precisam ser cadeias de caracteres, mas é mais fácil pensar nelas se você usar apenas cadeias de caracteres. No entanto, a indexação não funciona bem com as chaves complexas.

```powershell
$ht = @{ @(1,2,3) = "a" }
$ht

Name                           Value
----                           -----
{1, 2, 3}                      a
```

O acesso a um valor na tabela de hash por sua chave nem sempre funciona. Por exemplo:

```powershell
$key = $ht.keys[0]
$ht.$($key)
a
$ht[$key]
a
```

Quando a chave é uma matriz, você precisa encapsular a variável `$key` em uma subexpressão para que ela possa ser usada com a notação de acesso de membro (`.`). Ou, você pode usar a notação de índice de matriz (`[]`).

## <a name="use-in-automatic-variables"></a>Usar em variáveis automáticas

### <a name="psboundparameters"></a>$PSBoundParameters

[$PSBoundParameters][] é uma variável automática que existe apenas dentro do contexto de uma função.
Ela contém todos os parâmetros com os quais a função foi chamada. Ela não é exatamente uma tabela de hash, mas é parecida o suficiente para que você possa tratá-la como tal.

Isso inclui a remoção de chaves e o fracionamento em outras funções. Se você estiver escrevendo funções de proxy, dê uma olhada mais de perto neste artigo.

Confira [about_Automatic_Variables][] para obter mais detalhes.

### <a name="psboundparameters-gotcha"></a>Armadilha da PSBoundParameters

Uma coisa importante a ser lembrada é que essa variável inclui apenas os valores que são passados como parâmetros. Se também houver parâmetros com valores padrão que não forem passados pelo chamador, a `$PSBoundParameters` não incluirá esses valores. Normalmente, isso é ignorado.

### <a name="psdefaultparametervalues"></a>$PSDefaultParameterValues

Essa variável automática permite que você atribua valores padrão a qualquer cmdlet sem alterá-lo.
Confira este exemplo.

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "UTF8"
```

Ele adiciona uma entrada à tabela de hash `$PSDefaultParameterValues`, que define `UTF8` como o valor padrão para o parâmetro `Out-File -Encoding`. É algo específico da sessão, portanto, você deve colocar no `$profile`.

Eu uso isso sempre para atribuir previamente valores que costumo digitar com frequência.

```powershell
$PSDefaultParameterValues[ "Connect-VIServer:Server" ] = 'VCENTER01.contoso.local'
```

Ela também aceita curingas para que você possa definir valores em massa. Aqui estão algumas maneiras pelas quais você pode usar isso:

```powershell
$PSDefaultParameterValues[ "Get-*:Verbose" ] = $true
$PSDefaultParameterValues[ "*:Credential" ] = Get-Credential
```

Para obter um detalhamento mais aprofundado, confira este excelente artigo sobre [Padrões Automáticos][], escrito por [Michael Sorens][].

## <a name="regex-matches"></a>$Matches de expressão regular

Quando você usa o operador `-match`, uma variável automática chamada `$matches` é criada com os resultados da correspondência. Se você tiver qualquer subexpressão em sua expressão regular, essas subcorrespondências também serão listadas.

```powershell
$message = 'My SSN is 123-45-6789.'

$message -match 'My SSN is (.+)\.'
$Matches[0]
$Matches[1]
```

### <a name="named-matches"></a>Correspondências nomeadas

Esse é um dos meus recursos favoritos, que a maioria das pessoas não conhece. Se você usar uma correspondência de expressão regular nomeada, poderá acessar essa correspondência pelo nome entre as correspondências.

```powershell
$message = 'My Name is Kevin and my SSN is 123-45-6789.'

if($message -match 'My Name is (?<Name>.+) and my SSN is (?<SSN>.+)\.')
{
    $Matches.Name
    $Matches.SSN
}
```

No exemplo acima, `(?<Name>.*)` é uma subexpressão nomeada. Então, esse valor é colocado na propriedade `$Matches.Name`.

## <a name="group-object--ashashtable"></a>Group-Object -AsHashtable

Um pequeno recurso conhecido do `Group-Object` é que ele pode transformar alguns conjuntos de dados em uma tabela de hash para você.

```powershell
Import-CSV $Path | Group-Object -AsHashtable -Property email
```

Isso adicionará cada linha a uma tabela de hash e usará a propriedade especificada como a chave para acessá-la.

## <a name="copying-hashtables"></a>Copiando tabelas de hash

Uma coisa importante a saber é que as tabelas de hash são objetos. E cada variável é apenas uma referência a um objeto. Isso significa que é necessário mais trabalho para fazer uma cópia válida de uma tabela de hash.

### <a name="assigning-reference-types"></a>Atribuindo tipos de referência

Quando você tem uma tabela de hash e a atribui a uma segunda variável, ambas as variáveis apontam para a mesma tabela de hash.

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [copy]
```

Algo que realça que elas são a mesma coisa é o fato de que alterar os valores em uma também alterará os valores na outra. Isso também se aplica ao passar tabelas de hash para outras funções. Se as funções fizerem alterações na tabela de hash passada, a original também será alterada.

### <a name="shallow-copies-single-level"></a>Cópias superficiais, nível único

Se tivermos uma tabela de hash simples, como no exemplo acima, poderemos usar `.Clone()` para fazer uma cópia superficial.

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig.Clone()
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [orig]
```

Isso nos permitirá fazer algumas alterações básicas em uma sem afetar a outra.

### <a name="shallow-copies-nested"></a>Cópias superficiais, aninhadas

O motivo pelo qual são chamadas de cópias superficiais é o fato de só copiarem as propriedades do nível	de base. Se alguma dessas propriedades for um tipo de referência (como outra tabela de hash), então os objetos aninhados ainda apontarão um para o outro.

```powershell
PS> $orig = @{
        person=@{
            name='orig'
        }
    }
PS> $copy = $orig.Clone()
PS> $copy.person.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.person.name
PS> 'Orig: [{0}]' -f $orig.person.name

Copy: [copy]
Orig: [copy]
```

Portanto, você pode notar que, embora eu tenha clonado a tabela de hash, a referência a `person` não foi clonada. Precisamos fazer uma cópia profunda para realmente ter uma segunda tabela de hash que não esteja vinculada à primeira.

### <a name="deep-copies"></a>Cópias profundas

Até o momento em que escrevi este artigo, eu não tinha ciência de nenhuma forma inteligente de fazer uma cópia profunda de uma tabela de hash (e mantê-la como uma tabela de hash). Essa é apenas uma daquelas coisas que a pessoa precisa gravar.
Aqui está um método rápido para fazer isso.

```powershell
function Get-DeepClone
{
    [CmdletBinding()]
    param(
        $InputObject
    )
    process
    {
        if($InputObject -is [hashtable]) {
            $clone = @{}
            foreach($key in $InputObject.keys)
            {
                $clone[$key] = Get-DeepClone $InputObject[$key]
            }
            return $clone
        } else {
            return $InputObject
        }
    }
}
```

Ele não gerencia nenhum outro tipo de referência ou matrizes, mas é um bom ponto de partida.

## <a name="anything-else"></a>Algo mais?

Abordei muitos aspectos de base rapidamente. Minha esperança é que, toda vez que ler o artigo, você saia com uma novidade aprendida ou tendo entendido melhor algo. Como abordei o espectro completo desse recurso, pode haver aspectos que não se aplicam a você neste momento. Isso é perfeitamente normal e até esperado, de certo modo, dependendo do seu nível de familiaridade com o PowerShell.

<!-- link references -->
[versão original]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[tabelas de hash]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[matrizes]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Se o desempenho for importante, teste-o]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[fracionamento]: /powershell/module/microsoft.powershell.core/about/about_splatting
[pscustomobject]: everything-about-pscustomobject.md
[JavaScriptSerializer]: /dotnet/api/system.web.script.serialization.javascriptserializer?view=netframework-4.8
[PSBoundParameters]: https://tommymaynard.com/the-psboundparameters-automatic-variable-2016/
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[Padrões automáticos]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Michael Sorens]: http://cleancode.sourceforge.net/wwwdoc/about.html
