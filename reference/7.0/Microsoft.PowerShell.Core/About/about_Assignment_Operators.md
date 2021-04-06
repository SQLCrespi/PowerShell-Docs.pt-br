---
description: Descreve como usar operadores para atribuir valores a variáveis.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: 5ebb637d885488cfdccd63052b1bc5ffa161867f
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072389"
---
# <a name="about-assignment-operators"></a>Sobre operadores de atribuição

## <a name="short-description"></a>Descrição breve
Descreve como usar operadores para atribuir valores a variáveis.

## <a name="long-description"></a>Descrição longa

Os operadores de atribuição atribuem um ou mais valores a uma variável. Eles podem executar operações numéricas nos valores antes da atribuição.

O PowerShell dá suporte aos seguintes operadores de atribuição.

|Operador|Descrição                                                  |
|--------|-------------------------------------------------------------|
|=       |Define o valor de uma variável para o valor especificado.         |
|+=      |Aumenta o valor de uma variável pelo valor especificado ou |
|        |acrescenta o valor especificado ao valor existente.           |
|-=      |Diminui o valor de uma variável pelo valor especificado.    |
|*=      |Multiplica o valor de uma variável pelo valor especificado ou|
|        |acrescenta o valor especificado ao valor existente.           |
|/=      |Divide o valor de uma variável pelo valor especificado.      |
|%=      |Divide o valor de uma variável pelo valor especificado e   |
|        |em seguida, atribui o resto (módulo) à variável.        |
|++      |Aumenta o valor de uma variável, Propriedade atribuível ou   |
|        |elemento de matriz em 1.                                          |
|--      |Diminui o valor de uma variável, Propriedade atribuível ou   |
|        |elemento de matriz em 1.                                          |

## <a name="syntax"></a>Syntax

A sintaxe dos operadores de atribuição é a seguinte:

`<assignable-expression>` `<assignment-operator>` `<value>`

As expressões atribuíveis incluem variáveis e propriedades. O valor pode ser um único valor, uma matriz de valores ou um comando, expressão ou instrução.

Os operadores de incremento e decremento são operadores unários. Cada uma tem versões de prefixo e sufixo.

`<assignable-expression><operator>`
`<operator><assignable-expression>`

A expressão atribuível deve ser um número ou deve ser conversível em um número.

## <a name="assigning-values"></a>Atribuindo valores

Variáveis são nomes de espaços de memória que armazenam valores. Você armazena os valores em variáveis usando o operador de atribuição `=` . O novo valor pode substituir o valor existente da variável ou você pode acrescentar um novo valor ao valor existente.

O operador de atribuição básica é o sinal de igual `=` `(ASCII 61)` . Por exemplo, a instrução a seguir atribui o valor PowerShell à `$MyShell` variável:

```powershell
$MyShell = "PowerShell"
```

Quando você atribui um valor a uma variável no PowerShell, a variável é criada, caso ainda não exista. Por exemplo, a primeira das duas instruções de atribuição a seguir cria a `$a` variável e atribui um valor de 6 a `$a` . A segunda instrução de atribuição atribui um valor de 12 a `$a` . A primeira instrução cria uma nova variável. A segunda instrução altera apenas seu valor:

```powershell
$a = 6
$a = 12
```

As variáveis no PowerShell não têm um tipo de dados específico, a menos que você as converta.
Quando uma variável contém apenas um objeto, a variável usa o tipo de dados desse objeto. Quando uma variável contém uma coleção de objetos, a variável tem o tipo de dados System. Object. Portanto, você pode atribuir qualquer tipo de objeto à coleção. O exemplo a seguir mostra que você pode adicionar objetos de processo, objetos de serviço, cadeias de caracteres e inteiros a uma variável sem gerar um erro:

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

Como o operador de atribuição `=` tem uma precedência mais baixa do que o operador de pipeline `|` , não são necessários parênteses para atribuir o resultado de um pipeline de comando a uma variável. Por exemplo, o comando a seguir classifica os serviços no computador e atribui os serviços classificados à `$a` variável:

```powershell
$a = Get-Service | Sort-Object -Property name
```

Você também pode atribuir o valor criado por uma instrução a uma variável, como no exemplo a seguir:

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

Este exemplo atribui zero à `$a` variável se o valor de `$b` for menor que zero. Ele atribui o valor de `$b` para `$a` se o valor de `$b` não for menor que zero.

### <a name="the-assignment-operator"></a>O operador de atribuição

O operador de atribuição `=` atribui valores a variáveis. Se a variável já tiver um valor, o operador de atribuição `=` substituirá o valor sem aviso.

A instrução a seguir atribui o valor inteiro 6 à `$a` variável:

```powershell
$a = 6
```

Para atribuir um valor de cadeia de caracteres a uma variável, coloque o valor da cadeia de caracteres entre aspas, da seguinte maneira:

```powershell
$a = "baseball"
```

Para atribuir uma matriz (vários valores) a uma variável, separe os valores com vírgulas, da seguinte maneira:

```powershell
$a = "apple", "orange", "lemon", "grape"
```

Para atribuir uma tabela de hash a uma variável, use a notação de tabela de hash padrão no PowerShell. Digite um sinal de entrada `@` seguido por pares de chave/valor separados por ponto e vírgula `;` e entre chaves `{ }` . Por exemplo, para atribuir uma tabela de hash à `$a` variável, digite:

```powershell
$a = @{one=1; two=2; three=3}
```

Para atribuir valores hexadecimais a uma variável, preceda o valor com `0x` .
O PowerShell converte o valor hexadecimal (0x10) em um valor decimal (neste caso, 16) e atribui esse valor à `$a` variável. Por exemplo, para atribuir um valor de 0x10 à `$a` variável, digite:

```powershell
$a = 0x10
```

Para atribuir um valor exponencial a uma variável, digite o número raiz, a letra `e` e um número que represente um múltiplo de 10. Por exemplo, para atribuir um valor de 3,1415 à potência de 1.000 para a `$a` variável, digite:

```powershell
$a = 3.1415e3
```

O PowerShell também pode converter quilobytes `KB` , megabytes `MB` e gigabytes `GB` em bytes. Por exemplo, para atribuir um valor de 10 kilobytes à `$a` variável, digite:

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a>O operador de atribuição por adição

O operador atribuição por adição `+=` incrementa o valor de uma variável ou acrescenta o valor especificado ao valor existente. A ação depende de se a variável tem um tipo numérico ou de cadeia de caracteres e se a variável contém um único valor (um escalar) ou vários valores (uma coleção).

O `+=` operador combina duas operações. Primeiro, ele adiciona e, em seguida, atribui.
Portanto, as instruções a seguir são equivalentes:

```powershell
$a += 2
$a = ($a + 2)
```

Quando a variável contém um único valor numérico, o `+=` operador incrementa o valor existente pelo valor no lado direito do operador. Em seguida, o operador atribui o valor resultante à variável. O exemplo a seguir mostra como usar o `+=` operador para aumentar o valor de uma variável:

```powershell
$a = 4
$a += 2
$a
```

```
6
```

Quando o valor da variável é uma cadeia de caracteres, o valor no lado direito do operador é acrescentado à cadeia de caracteres da seguinte maneira:

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

Quando o valor da variável é uma matriz, o `+=` operador acrescenta os valores no lado direito do operador à matriz. A menos que a matriz seja digitada explicitamente pela conversão, você pode acrescentar qualquer tipo de valor à matriz, da seguinte maneira:

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

e

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

Quando o valor de uma variável é uma tabela de hash, o `+=` operador acrescenta o valor no lado direito do operador à tabela de hash. No entanto, como o único tipo que você pode adicionar a uma tabela de hash é outra tabela de hash, todas as outras atribuições falham.

Por exemplo, o comando a seguir atribui uma tabela de hash à `$a` variável.
Em seguida, ele usa o `+=` operador para acrescentar outra tabela de hash à tabela de hash existente, adicionando efetivamente um novo par de chave/valor à tabela de hash existente.
Esse comando é bem sucedido, conforme mostrado na saída:

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

O comando a seguir tenta acrescentar um inteiro "1" à tabela de hash na `$a` variável. Este comando falha:

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a>O operador de atribuição por subtração

O operador atribuição por subtração `-=` Decrementa o valor de uma variável pelo valor especificado no lado direito do operador. Esse operador não pode ser usado com variáveis de cadeia de caracteres e não pode ser usado para remover um elemento de uma coleção.

O `-=` operador combina duas operações. Primeiro, ele subtrai e, em seguida, atribui. Portanto, as instruções a seguir são equivalentes:

```powershell
$a -= 2
$a = ($a - 2)
```

O exemplo a seguir mostra como usar o `-=` operador para diminuir o valor de uma variável:

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

Você também pode usar o `-=` operador de atribuição para diminuir o valor de um membro de uma matriz numérica. Para fazer isso, especifique o índice do elemento da matriz que você deseja alterar. No exemplo a seguir, o valor do terceiro elemento de uma matriz (elemento 2) é diminuído em 1:

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

Você não pode usar o `-=` operador para excluir os valores de uma variável. Para excluir todos os valores atribuídos a uma variável, use os cmdlets [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) ou [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) para atribuir um valor de `$null` ou `""` à variável.

```powershell
$a = $null
```

Para excluir um valor específico de uma matriz, use a notação de matriz para atribuir um valor de `$null` para o item específico. Por exemplo, a instrução a seguir exclui o segundo valor (posição de índice 1) de uma matriz:

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

Para excluir uma variável, use o cmdlet [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) . Esse método é útil quando a variável é convertida explicitamente em um tipo de dados específico e você deseja uma variável não tipada. O comando a seguir exclui a `$a` variável:

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a>A atribuição por operador de multiplicação

A atribuição por operador de multiplicação `*=` multiplica um valor numérico ou acrescenta o número especificado de cópias do valor da cadeia de caracteres de uma variável.

Quando uma variável contém um único valor numérico, esse valor é multiplicado pelo valor no lado direito do operador. Por exemplo, o exemplo a seguir mostra como usar o `*=` operador para multiplicar o valor de uma variável:

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

Nesse caso, o `*=` operador combina duas operações. Primeiro, ele multiplica e, em seguida, atribui. Portanto, as instruções a seguir são equivalentes:

```powershell
$a *= 2
$a = ($a * 2)
```

Quando uma variável contém um valor de cadeia de caracteres, o PowerShell anexa o número de cadeias de caracteres especificado ao valor, da seguinte maneira:

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

Para multiplicar um elemento de uma matriz, use um índice para identificar o elemento que você deseja multiplicar. Por exemplo, o comando a seguir multiplica o primeiro elemento na matriz (posição do índice 0) por 2:

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a>A atribuição por operador de divisão

O operador atribuição por divisão `/=` divide um valor numérico pelo valor especificado no lado direito do operador. O operador não pode ser usado com variáveis de cadeia de caracteres.

O `/=` operador combina duas operações. Primeiro, ele divide e, em seguida, atribui. Portanto, as duas instruções a seguir são equivalentes:

```powershell
$a /= 2
$a = ($a / 2)
```

Por exemplo, o comando a seguir usa o `/=` operador para dividir o valor de uma variável:

```powershell
$a = 8
$a /=2
$a
```

```
4
```

Para dividir um elemento de uma matriz, use um índice para identificar o elemento que você deseja alterar. Por exemplo, o comando a seguir divide o segundo elemento na matriz (posição de índice 1) por 2:

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a>O operador de atribuição por módulo

A atribuição por operador de módulo `%=` divide o valor de uma variável pelo valor no lado direito do operador. Em seguida, o `%=` operador atribui o resto (conhecido como módulo) à variável. Você pode usar esse operador somente quando uma variável contiver um único valor numérico. Você não pode usar esse operador quando uma variável contém uma variável de cadeia de caracteres ou uma matriz.

O `%=` operador combina duas operações. Primeiro, ele divide e determina o restante e, em seguida, atribui o resto à variável. Portanto, as instruções a seguir são equivalentes:

```powershell
$a %= 2
$a = ($a % 2)
```

O exemplo a seguir mostra como usar o `%=` operador para salvar o módulo de um quociente:

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a>Os operadores de incremento e decremento

O operador de incremento `++` aumenta o valor de uma variável em 1. Quando você usa o operador de incremento em uma instrução simples, nenhum valor é retornado. Para exibir o resultado, exiba o valor da variável, da seguinte maneira:

```powershell
$a = 7
++$a
$a
```

```
8
```

Para forçar um valor a ser retornado, coloque a variável e o operador entre parênteses, da seguinte maneira:

```powershell
$a = 7
(++$a)
```

```
8
```

O operador de incremento pode ser colocado antes (prefixo) ou após (sufixo) uma variável. A versão de prefixo do operador incrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

A versão do sufixo do operador incrementa uma variável depois que seu valor é usado na instrução. No exemplo a seguir, as `$c` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$c` antes `$a` das alterações:

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

O operador decremento `--` diminui o valor de uma variável em 1. Assim como com o operador de incremento, nenhum valor é retornado quando você usa o operador em uma instrução simples. Use parênteses para retornar um valor, da seguinte maneira:

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

A versão de prefixo do operador decrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

A versão do sufixo do operador decrementa uma variável depois que seu valor é usado na instrução. No exemplo a seguir, as `$d` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$d` antes `$a` das alterações:

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a>Tipos de estrutura de Microsoft .NET

Por padrão, quando uma variável tem apenas um valor, o valor atribuído à variável determina o tipo de dados da variável. Por exemplo, o comando a seguir cria uma variável que tem o tipo "inteiro" (System. Int32):

```powershell
$a = 6
```

Para localizar o tipo de .NET Framework de uma variável, use o método **GetType** e sua propriedade **FullName** , da seguinte maneira. Certifique-se de incluir os parênteses após o nome do método **GetType** , mesmo que a chamada do método não tenha argumentos:

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

Para criar uma variável que contém uma cadeia de caracteres, atribua um valor de cadeia de caracteres à variável. Para indicar que o valor é uma cadeia de caracteres, coloque-o entre aspas, da seguinte maneira:

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

Se o primeiro valor que é atribuído à variável for uma cadeia de caracteres, o PowerShell tratará todas as operações como operações de cadeia de caracteres e converterá novos valores em cadeias.
Isso ocorre no exemplo a seguir:

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

Se o primeiro valor for um inteiro, o PowerShell tratará todas as operações como operações de inteiros e converterá novos valores em inteiros. Isso ocorre no exemplo a seguir:

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

Você pode converter uma nova variável escalar como qualquer .NET Framework tipo colocando o nome do tipo entre colchetes que precedem o nome da variável ou o primeiro valor de atribuição. Ao converter uma variável, você pode determinar os tipos de dados que podem ser armazenados na variável. E você pode determinar como a variável se comporta quando você a manipula.

Por exemplo, o comando a seguir converte a variável como um tipo de cadeia de caracteres:

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

O exemplo a seguir converte o primeiro valor, em vez de converter a variável:

```powershell
$a = [string]27
```

Quando você converte uma variável para um tipo específico, a Convenção comum é converter a variável, não o valor. No entanto, você não pode reconverter o tipo de dados de uma variável existente se seu valor não puder ser convertido para o novo tipo de dados. Para alterar o tipo de dados, você deve substituir seu valor, da seguinte maneira:

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

Além disso, quando você precede um nome de variável com um tipo de dados, o tipo dessa variável é bloqueado, a menos que você substitua explicitamente o tipo especificando outro tipo de dados. Se você tentar atribuir um valor incompatível com o tipo existente e não substituir explicitamente o tipo, o PowerShell exibirá um erro, conforme mostrado no exemplo a seguir:

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

No PowerShell, os tipos de dados de variáveis que contêm vários itens em uma matriz são tratados de forma diferente dos tipos de dados de variáveis que contêm um único item. A menos que um tipo de dados seja especificamente atribuído a uma variável de matriz, o tipo de dados é sempre `System.Object []` . Esse tipo de dados é específico para matrizes.

Às vezes, você pode substituir o tipo padrão especificando outro tipo. Por exemplo, o comando a seguir converte a variável como um `string []` tipo de matriz:

```powershell
[string []] $a = "one", "two", "three"
```

As variáveis do PowerShell podem ser qualquer tipo de dados .NET Framework. Além disso, você pode atribuir qualquer tipo de dados .NET Framework totalmente qualificado que esteja disponível no processo atual. Por exemplo, o comando a seguir especifica um `System.DateTime` tipo de dados:

```powershell
[System.DateTime]$a = "5/31/2005"
```

A variável será atribuída a um valor que esteja de acordo com o `System.DateTime` tipo de dados. O valor da `$a` variável seria o seguinte:

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a>Atribuindo várias variáveis

No PowerShell, você pode atribuir valores a várias variáveis usando um único comando. O primeiro elemento do valor de atribuição é atribuído à primeira variável, o segundo elemento é atribuído à segunda variável, o terceiro elemento à terceira variável e assim por diante. Isso é conhecido como _várias atribuições_.

Por exemplo, o comando a seguir atribui o valor 1 à `$a` variável, o valor 2 à `$b` variável e o valor 3 à `$c` variável:

```powershell
$a, $b, $c = 1, 2, 3
```

Se o valor de atribuição contiver mais elementos que variáveis, todos os valores restantes serão atribuídos à última variável. Por exemplo, o comando a seguir contém três variáveis e cinco valores:

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável. Ele atribui os valores 3, 4 e 5 à `$c` variável.
Para atribuir os valores na `$c` variável a três outras variáveis, use o seguinte formato:

```powershell
$d, $e, $f = $c
```

Esse comando atribui o valor 3 à `$d` variável, o valor 4 à `$e` variável e o valor 5 à `$f` variável.

Se o valor de atribuição contiver menos elementos que variáveis, as variáveis restantes receberão o valor `$null` . Por exemplo, o comando a seguir contém três variáveis e dois valores:

```powershell
$a, $b, $c = 1, 2
```

Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável. A `$c` variável é `$null` .

Você também pode atribuir um único valor a várias variáveis encadeando as variáveis. Por exemplo, o comando a seguir atribui um valor de "três" a todas as quatro variáveis:

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a>Cmdlets relacionados a variáveis

Além de usar uma operação de atribuição para definir um valor de variável, você também pode usar o cmdlet [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) . Por exemplo, o comando a seguir usa `Set-Variable` para atribuir uma matriz de 1, 2, 3 à `$a` variável.

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a>Confira também

[about_Arrays](about_Arrays.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Variables](about_Variables.md)

[Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable)
