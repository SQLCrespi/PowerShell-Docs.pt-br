---
description: Descreve matrizes, que são estruturas de dados projetadas para armazenar coleções de itens.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 96e3798d4ff0a737421bb6211b809b192afa96f0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196072"
---
# <a name="about-arrays"></a>Sobre matrizes

## <a name="short-description"></a>Descrição breve
Descreve matrizes, que são estruturas de dados projetadas para armazenar coleções de itens.

## <a name="long-description"></a>Descrição longa

Uma matriz é uma estrutura de dados que é projetada para armazenar uma coleção de itens.
Os itens podem ser do mesmo tipo ou tipos diferentes.

A partir do Windows PowerShell 3,0, uma coleção de zero ou um objeto tem algumas propriedades de matrizes.

## <a name="creating-and-initializing-an-array"></a>Criando e inicializando uma matriz

Para criar e inicializar uma matriz, atribua vários valores a uma variável. Os valores armazenados na matriz são delimitados por uma vírgula e separados do nome da variável pelo operador de atribuição ( `=` ).

Por exemplo, para criar uma matriz chamada `$A` que contenha os sete valores numéricos (int) de 22, 5, 10, 8, 12, 9 e 80, digite:

```powershell
$A = 22,5,10,8,12,9,80
```

A vírgula também pode ser usada para inicializar uma única matriz de item colocando a vírgula antes do único item.

Por exemplo, para criar uma única matriz de item denominada `$B` contendo o único valor de 7, digite:

```powershell
$B = ,7
```

Você também pode criar e inicializar uma matriz usando o operador de intervalo ( `..` ).
O exemplo a seguir cria uma matriz que contém os valores de 5 a 8.

```powershell
$C = 5..8
```

Como resultado, `$C` contém quatro valores: 5, 6, 7 e 8.

Quando nenhum tipo de dados é especificado, o PowerShell cria cada matriz como uma matriz de objetos ( **System. Object []** ). Para determinar o tipo de dados de uma matriz, use o método **GetType ()** . Por exemplo, para determinar o tipo de dados da `$A` matriz, digite:

```powershell
$A.GetType()
```

Para criar uma matriz fortemente tipada, ou seja, uma matriz que possa conter apenas valores de um tipo específico, converta a variável como um tipo de matriz, como **String []** , **Long []** ou **Int32 []** . Para converter uma matriz, preceda o nome da variável com um tipo de matriz entre colchetes. Por exemplo, para criar uma matriz de inteiros de 32 bits chamada `$ia` contendo quatro inteiros (1500, 2230, 3350 e 4000), digite:

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

Como resultado, a `$ia` matriz pode conter apenas números inteiros.

Você pode criar matrizes que são convertidas para qualquer tipo com suporte na estrutura de Microsoft .NET. Por exemplo, os objetos `Get-Process` recuperados para representar processos são do tipo **System. Diagnostics. Process** . Para criar uma matriz fortemente tipada de objetos de processo, digite o seguinte comando:

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a>O operador de subexpressão de matriz

O operador de subexpressão de matriz cria uma matriz das instruções dentro dela. Qualquer que seja a instrução dentro do operador, o operador a coloca em uma matriz. Mesmo que haja zero ou um objeto.

A sintaxe do operador de matriz é a seguinte:

```syntax
@( ... )
```

Você pode usar o operador de matriz para criar uma matriz de zero ou um objeto. Por exemplo:

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

O operador de matriz é útil em scripts quando você está obtendo objetos, mas não sabe quantos objetos você obtém. Por exemplo:

```powershell
$p = @(Get-Process Notepad)
```

Para obter mais informações sobre o operador de subexpressão de matriz, consulte [about_Operators](about_Operators.md).

## <a name="accessing-and-using-array-elements"></a>Acessando e usando elementos de matriz

### <a name="reading-an-array"></a>Lendo uma matriz

Você pode fazer referência a uma matriz usando seu nome de variável. Para exibir todos os elementos na matriz, digite o nome da matriz. Por exemplo, supondo que `$a` seja uma matriz contendo inteiros 0, 1, 2, até 9; digitando:

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

Você pode consultar os elementos em uma matriz usando um índice, começando na posição 0. Coloque o número de índice entre colchetes. Por exemplo, para exibir o primeiro elemento na `$a` matriz, digite:

```powershell
$a[0]
```

```Output
0
```

Para exibir o terceiro elemento na `$a` matriz, digite:

```powershell
$a[2]
```

```Output
2
```

Você pode recuperar parte da matriz usando um operador de intervalo para o índice. Por exemplo, para recuperar o segundo para o quinto elementos da matriz, você digitaria:

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

Contagem de números negativos do final da matriz. Por exemplo, "-1" refere-se ao último elemento da matriz. Para exibir os três últimos elementos da matriz, em ordem crescente de índice, digite:

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

Se você digitar índices negativos em ordem decrescente, sua saída será alterada.

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

No entanto, tenha cuidado ao usar essa notação. A notação percorre o limite final até o início da matriz.

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

Além disso, um erro comum é assumir a `$a[0..-2]` referência a todos os elementos da matriz, exceto para o último. Refere-se ao primeiro, ao último e ao último elemento da matriz.

Você pode usar o operador de adição ( `+` ) para combinar intervalos com uma lista de elementos em uma matriz. Por exemplo, para exibir os elementos nas posições de índice 0, 2 e 4 a 6, digite:

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

Além disso, para listar vários intervalos e elementos individuais, você pode usar o operador de adição. Por exemplo, para listar os elementos de zero a dois, quatro a seis e o elemento em um oitavo tipo posicional:

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a>Iterações sobre elementos de matriz

Você também pode usar constructos de loop, como ForEach, for e loops while, para se referir aos elementos em uma matriz. Por exemplo, para usar um loop ForEach para exibir os elementos na `$a` matriz, digite:

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

O loop foreach itera na matriz e retorna cada valor na matriz até chegar ao final da matriz.

O loop for é útil quando você está incrementando contadores ao examinar os elementos em uma matriz. Por exemplo, para usar um loop for para retornar todos os outros valores em uma matriz, digite:

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

Você pode usar um loop while para exibir os elementos em uma matriz até que uma condição definida não seja mais verdadeira. Por exemplo, para exibir os elementos na `$a` matriz enquanto o índice de matriz é menor que 4, digite:

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a>Propriedades de matrizes

### <a name="count-or-length-or-longlength"></a>Contagem ou comprimento ou LongLength

Para determinar quantos itens estão em uma matriz, use a `Length` propriedade ou seu `Count` alias. `Longlength` será útil se a matriz contiver mais de 2.147.483.647 elementos.

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a>Rank

Retorna o número de dimensões na matriz. A maioria das matrizes no PowerShell tem apenas uma dimensão. Mesmo quando você acredita que está criando uma matriz multidimensional; semelhante ao exemplo a seguir:

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

O exemplo a seguir mostra como criar uma matriz verdadeiramente multidimensional usando o .NET Framework.

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a>Métodos de matrizes

### <a name="clear"></a>Limpar

Define todos os valores de elemento como o _valor padrão_ do tipo de elemento da matriz.
O método Clear () não redefine o tamanho da matriz.

No exemplo a seguir, `$a` há uma matriz de objetos.

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

Neste exemplo, `$intA` é digitado explicitamente para conter inteiros.

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a>ForEach

Permite iterar em todos os elementos na matriz e executar uma determinada operação para cada elemento da matriz.

O método ForEach tem várias sobrecargas que executam operações diferentes.

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a>ForEach (expressão scriptblock)

#### <a name="foreachscriptblock-expression-object-arguments"></a>ForEach (expressão scriptblock, argumentos Object [])

Esse método foi adicionado no PowerShell v4.

> [!NOTE]
> A sintaxe requer o uso de um bloco de script. Os parênteses serão opcionais se o scriptblock for o único parâmetro. Além disso, não deve haver um espaço entre o método e o parêntese de abertura ou a chave.

O exemplo a seguir mostra como usar o método ForEach. Nesse caso, a intenção é gerar o valor quadrado dos elementos na matriz.

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

Assim como o `-ArgumentList` parâmetro de `ForEach-Object` , o `arguments` parâmetro permite a passagem de uma matriz de argumentos para um bloco de script configurado para aceitá-los.

Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about_Splatting.md#splatting-with-arrays).

#### <a name="foreachtype-converttotype"></a>ForEach (tipo convertTotype)

O `ForEach` método pode ser usado para converter rapidamente os elementos em um tipo diferente; o exemplo a seguir mostra como converter uma lista de datas de cadeia de caracteres para `[DateTime]` tipo.

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a>ForEach (cadeia de caracteres propertyName)

#### <a name="foreachstring-propertyname-object-newvalue"></a>ForEach (String propertyName, Object [] newValue)

O `ForEach` método também pode ser usado para recuperar rapidamente ou definir valores de propriedade para cada item na coleção.

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a>ForEach (cadeia de caracteres methodName)

#### <a name="foreachstring-methodname-object-arguments"></a>ForEach (cadeia de caracteres methodName, argumentos Object [])

Por fim, os `ForEach` métodos podem ser usados para executar um método em cada item da coleção.

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

Assim como o `-ArgumentList` parâmetro de `ForEach-Object` , o `arguments` parâmetro permite a passagem de uma matriz de argumentos para um bloco de script configurado para aceitá-los.

> [!NOTE]
> A partir do Windows PowerShell 3,0 a recuperação de propriedades e execução de métodos para cada item em uma coleção também pode ser realizada usando "métodos de coleções e objetos escalares". você pode ler mais sobre isso aqui [about_methods](about_methods.md).

### <a name="where"></a>Where

Permite filtrar ou selecionar os elementos da matriz. O script deve ser avaliado como algo diferente de: zero (0), Cadeia de caracteres vazia `$false` ou `$null` para o elemento a ser mostrado após o `Where`

Há uma definição para o `Where` método.

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> A sintaxe requer o uso de um bloco de script. Os parênteses serão opcionais se o scriptblock for o único parâmetro. Além disso, não deve haver um espaço entre o método e o parêntese de abertura ou a chave.

O `Expression` scriptblock is é necessário para a filtragem, o `mode` argumento opcional permite recursos de seleção adicionais e o `numberToReturn` argumento opcional permite limitar quantos itens são retornados do filtro.

Os valores aceitáveis para `mode` são:

- Padrão (0)-retornar todos os itens
- Primeiro (1)-retornar o primeiro item
- Último (2) – retornar o último item
- SkipUntil (3) – ignorar itens até a condição ser verdadeira, retornar os itens restantes
- Até (4) – retornar todos os itens até que a condição seja verdadeira
- Split (5) – retornar uma matriz de dois elementos
  - O primeiro elemento contém itens correspondentes
  - O segundo elemento contém os itens restantes

O exemplo a seguir mostra como selecionar todos os números ímpares da matriz.

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

Este exemplo mostra como selecionar as cadeias de caracteres que não estão vazias.

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a>Padrão

O `Default` modo filtra itens usando o `Expression` scriptblock.

Se um `numberToReturn` for fornecido, ele especificará o número máximo de itens a serem retornados.

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> O `Default` modo e o `First` modo retornam os primeiros ( `numberToReturn` ) itens e podem ser usados de forma intercambiável.

#### <a name="last"></a>Último

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a>SkipUntil

O `SkipUntil` modo ignora todos os objetos em uma coleção até que um objeto passe o filtro de expressão de bloco de script. Em seguida, ele retorna **todos os** itens de coleta restantes sem testá-los. _Apenas um item de passagem é testado_ .

Isso significa que a coleção retornada contém itens de _passagem_ e _não APROVADOs_ que não foram testados.

O número de itens retornados pode ser limitado passando um valor para o `numberToReturn` argumento.

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a>Haja

O `Until` modo inverte o `SkipUntil` modo.  Ele retorna **todos os** itens em uma coleção até que um item passe a expressão de bloco de script. Depois que um item _passa_ a expressão scriptblock, o `Where` método interrompe o processamento de itens.

Isso significa que você recebe o primeiro conjunto de itens _não aprovados_ do `Where` método. _Depois_ que um item passa, o restante não é testado ou retornado.

O número de itens retornados pode ser limitado passando um valor para o `numberToReturn` argumento.

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> `Until`E `SkipUntil` operar com a premissa de não testar um lote de itens.
>
> `Until` Retorna os itens **antes** da primeira _passagem_ .
>
> `SkipUntil` Retorna todos os itens **após** a primeira _passagem_ , incluindo o primeiro item de passagem.

#### <a name="split"></a>Divisão

O `Split` modo divide ou agrupa itens de coleção em duas coleções separadas. Aqueles que passam a expressão scriptblock e os que não fazem.

Se um `numberToReturn` for especificado, a primeira coleção conterá os itens _aprovados_ , não para exceder o valor especificado.

Os objetos restantes, até aqueles que **passam** o filtro de expressão, são retornados na segunda coleção.

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a>Obter os membros de uma matriz

Para obter as propriedades e os métodos de uma matriz, como a propriedade Length e o método **SetValue** , use o parâmetro **InputObject** do `Get-Member` cmdlet.

Quando você canaliza uma matriz para `Get-Member` o, o PowerShell envia os itens um de cada vez e `Get-Member` retorna o tipo de cada item na matriz (ignorando duplicatas).

Quando você usa o parâmetro **InputObject** , `Get-Member` o retorna os membros da matriz.

Por exemplo, o comando a seguir obtém os membros da `$a` variável de matriz.

```powershell
Get-Member -InputObject $a
```

Você também pode obter os membros de uma matriz digitando uma vírgula (,) antes do valor que é canalizado para o `Get-Member` cmdlet. A vírgula torna a matriz o segundo item em uma matriz de matrizes. O PowerShell canaliza as matrizes uma de cada vez e `Get-Member` retorna os membros da matriz. Como os dois exemplos a seguir.

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a>Manipulando uma matriz

Você pode alterar os elementos em uma matriz, adicionar um elemento a uma matriz e combinar os valores de duas matrizes em uma terceira matriz.

Para alterar o valor de um elemento específico em uma matriz, especifique o nome da matriz e o índice do elemento que você deseja alterar e, em seguida, use o operador de atribuição ( `=` ) para especificar um novo valor para o elemento. Por exemplo, para alterar o valor do segundo item na `$a` matriz (posição de índice 1) para 10, digite:

```powershell
$a[1] = 10
```

Você também pode usar o método **SetValue** de uma matriz para alterar um valor. O exemplo a seguir altera o segundo valor (posição de índice 1) da `$a` matriz para 500:

```powershell
$a.SetValue(500,1)
```

Você pode usar o `+=` operador para adicionar um elemento a uma matriz. O exemplo a seguir mostra como adicionar um elemento à `$a` matriz.

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> Quando você usa o `+=` operador, o PowerShell realmente cria uma nova matriz com os valores da matriz original e o valor adicionado. Isso pode causar problemas de desempenho se a operação for repetida várias vezes ou o tamanho da matriz for muito grande.

Não é fácil excluir elementos de uma matriz, mas você pode criar uma nova matriz que contém apenas os elementos selecionados de uma matriz existente. Por exemplo, para criar a `$t` matriz com todos os elementos na `$a` matriz, exceto para o valor na posição do índice 2, digite:

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

Para combinar duas matrizes em uma única matriz, use o operador de adição ( `+` ). O exemplo a seguir cria duas matrizes, combina-as e, em seguida, exibe a matriz combinada resultante.

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

Como resultado, a `$z` matriz contém 1, 3, 5 e 9.

Para excluir uma matriz, atribua um valor de `$null` à matriz. O comando a seguir exclui a matriz na `$a` variável.

`$a = $null`

Você também pode usar o `Remove-Item` cmdlet, mas atribuir um valor `$null` é mais rápido, especialmente para matrizes grandes.

## <a name="arrays-of-zero-or-one"></a>Matrizes de zero ou uma

A partir do Windows PowerShell 3,0, uma coleção de zero ou um objeto tem a propriedade Count e length. Além disso, você pode indexar em uma matriz de um objeto. Esse recurso ajuda a evitar erros de script que ocorrem quando um comando que espera uma coleção tem menos de dois itens.

Os exemplos a seguir demonstram esse recurso.

### <a name="zero-objects"></a>Zero objetos

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a>Um objeto

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a>Suporte de indexação para objetos System. tupla

O PowerShell 6,1 adicionou o suporte para acesso indexado de objetos de **tupla** , semelhante a matrizes.
Por exemplo:

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

Ao contrário de matrizes e outros objetos de coleção, os objetos de **tupla** são tratados como um único objeto quando passam pelo pipeline ou por parâmetros que dão suporte a matrizes de objetos.

Para obter mais informações, consulte [System. tupla](/dotnet/api/system.tuple).

## <a name="see-also"></a>Confira também

- [about_Assignment_Operators](about_Assignment_Operators.md)
- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Operators](about_Operators.md)
- [about_For](about_For.md)
- [about_Foreach](about_Foreach.md)
- [about_While](about_While.md)

