---
description: Descreve os operadores que executam aritmética no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: c7885e31e4b5b661473d5241b6629bbe05810824
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195790"
---
# <a name="about-arithmetic-operators"></a>Sobre operadores aritméticos

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os operadores que executam aritmética no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os operadores aritméticos calculam valores numéricos. Você pode usar um ou mais operadores aritméticos para adicionar, subtrair, multiplicar e dividir valores e para calcular o resto (módulo) de uma operação de divisão.

Além disso, o operador de adição ( `+` ) e o operador de multiplicação ( `*` ) também operam em cadeias de caracteres, matrizes e tabelas de hash. O operador de adição concatena a entrada. O operador de multiplicação retorna várias cópias da entrada. Você pode até mesmo misturar tipos de objeto em uma instrução aritmética. O método usado para avaliar a instrução é determinado pelo tipo do objeto mais à esquerda na expressão.

A partir do PowerShell 2,0, todos os operadores aritméticos funcionam em números de 64 bits.

A partir do PowerShell 3,0, o `-shr` (Shift-Right) e `-shl` (Shift-Left) são adicionados para dar suporte à aritmética de bits no PowerShell.

O PowerShell dá suporte aos seguintes operadores aritméticos:

|Operador|Descrição                       |Exemplo                      |
|--------|----------------------------------|-----------------------------|
| +      |Adiciona números inteiros; Concatena       |`6 + 2`                      |
|        |cadeias de caracteres, matrizes e tabelas de hash. |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |Subtrai um valor de outro  |`6 - 2`                      |
|        |value                             |                             |
| -      |Faz com que um número seja um número negativo  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |Multiplicar números ou copiar cadeias de caracteres  |`6 * 2`                      |
|        |e matrizes o número especificado   |`@("!") * 4`                 |
|        |de vezes.                         |`"!" * 3`                    |
| /      |Compara dois valores.               |`6 / 2`                      |
| %      |Módulo – retorna o restante de|`7 % 2`                      |
|        |uma operação de divisão.             |                             |
|-banda   |AND bit a bit                       |`5 -band 3`                  |
|-bnot   |NOT bit a bit                       |`-bnot 5`                    |
|-Bor    |OR bit a bit                        |`5 -bor 0x03`                |
|-bxor   |XOR bit a bit                       |`5 -bxor 3`                  |
|-shl    |Desloca bits para a esquerda           |`102 -shl 2`                 |
|-shr    |Desloca bits para a direita          |`102 -shr 2`                 |

Os operadores de bit a bit só funcionam em tipos inteiros.

## <a name="operator-precedence"></a>PRECEDÊNCIA DE OPERADOR

O PowerShell processa operadores aritméticos na seguinte ordem:

|Precedência|Operador          |Descrição                            |
|----------|------------------|---------------------------------------|
|1         | `()`             |Parênteses                            |
|2         | `-`              |Para um número negativo ou um operador unário|
|3         | `*`, `/`, `%`    |Para multiplicação e divisão        |
|4         | `+`, `-`         |Para adição e subtração           |
|5         | `-band`, `-bnot` |Para operações de bit a bit                 |
|5         | `-bor`, `-bxor`  |Para operações de bit a bit                 |
|5         | `-shr`, `-shl`   |Para operações de bit a bit                 |

O PowerShell processa as expressões da esquerda para a direita de acordo com as regras de precedência. Os exemplos a seguir mostram o efeito das regras de precedência:

|Expression |Resultado|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

A ordem na qual o PowerShell avalia expressões pode ser diferente de outras linguagens de programação e script que você usou. O exemplo a seguir mostra uma instrução de atribuição complicada.

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

Neste exemplo, a expressão `$a++` é avaliada antes de `$b[$a]` .
Avaliar `$a++` altera o valor de `$a` depois que ele é usado na instrução `$c[$a++]` ; Mas, antes de ser usado em `$b[$a]` . A variável `$a` em `$b[$a]` Equals `1` , não `0` ; portanto, a instrução atribui um valor a `$b[1]` , não `$b[0]` .

O código acima é equivalente a:

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a>DIVISÃO E ARREDONDAMENTO

Quando o quociente de uma operação de divisão é um inteiro, o PowerShell arredonda o valor para o número inteiro mais próximo. Quando o valor é `.5` , ele arredonda para o inteiro par mais próximo.

O exemplo a seguir mostra o efeito do arredondamento para o inteiro par mais próximo.

|Expression      |Resultado|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

Observe como **_5/2_ = 2,5** é arredondado para **2** . Mas, **_7/2_ = 3,5** é arredondado para **4** .

Você pode usar a `[Math]` classe para obter um comportamento de arredondamento diferente.

|                          Expression                          | Resultado |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

Para obter mais informações, consulte o método [Math. Round](/dotnet/api/system.math.round) .

## <a name="adding-and-multiplying-non-numeric-types"></a>ADICIONANDO E MULTIPLICANDO TIPOS NÃO NUMÉRICOS

Você pode adicionar números, cadeias de caracteres, matrizes e tabelas de hash. E, você pode multiplicar números, cadeias de caracteres e matrizes. No entanto, não é possível multiplicar tabelas de hash.

Quando você adiciona cadeias de caracteres, matrizes ou tabelas de hash, os elementos são concatenados. Quando você concatena coleções, como matrizes ou tabelas de hash, é criado um novo objeto que contém os objetos de ambas as coleções. Se você tentar concatenar tabelas de hash que têm a mesma chave, a operação falhará.

Por exemplo, os comandos a seguir criam duas matrizes e, em seguida, as adicionam:

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

Você também pode executar operações aritméticas em objetos de tipos diferentes.
A operação que o PowerShell executa é determinada pelo tipo de estrutura de Microsoft .NET do objeto mais à esquerda na operação. O PowerShell tenta converter todos os objetos na operação para o tipo de .NET Framework do primeiro objeto. Se tiver sucesso na conversão dos objetos, ele executará a operação apropriada para o tipo de .NET Framework do primeiro objeto. Se houver falha na conversão de qualquer um dos objetos, a operação falhará.

Os exemplos a seguir demonstram o uso dos operadores de adição e multiplicação; em operações que incluem tipos de objeto diferentes. Suponha que `$array = 1,2,3` :

|Expression       |Resultado                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |`1`,`2`,`3`,`16`       |
|`$array + "file"`|`1`,`2`,`3`,`file`     |
|`$array * 2`     |`1`,`2`,`3`,`1`,`2`,`3`|
|`"file" * 3`     |`filefilefile`         |

Como o método usado para avaliar instruções é determinado pelo objeto mais à esquerda, a adição e a multiplicação no PowerShell não são estritamente comutadores. Por exemplo, `(a + b)` nem sempre é igual `(b + a)` e `(ab)` nem sempre é igual a `(ba)` .

Os exemplos a seguir demonstram esse princípio:

|Expression   |Resultado                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |+ 16 + "arquivo" "                                       |

As tabelas de hash são um caso um pouco diferente. Você pode adicionar tabelas de hash a outra tabela de hash, desde que as tabelas de hash adicionadas não tenham chaves duplicadas.

O exemplo a seguir mostra como adicionar tabelas de hash entre si.

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

O exemplo a seguir gera um erro porque uma das chaves é duplicada em ambas as tabelas de hash.

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

Além disso, você pode adicionar uma tabela de hash a uma matriz; e, toda a tabela de hash se torna um item na matriz.

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

No entanto, você não pode adicionar nenhum outro tipo a uma tabela de hash.

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

Embora os operadores de adição sejam muito úteis, use os operadores de atribuição para adicionar elementos a tabelas de hash e matrizes. Para obter mais informações, consulte [about_assignment_operators](about_Assignment_Operators.md). Os exemplos a seguir usam o `+=` operador de atribuição para adicionar itens a uma matriz:

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a>CONVERSÃO DE TIPO PARA ACOMODAR O RESULTADO

O PowerShell seleciona automaticamente o tipo numérico .NET Framework que melhor expresse o resultado sem perder a precisão. Por exemplo:

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

Se o resultado de uma operação for muito grande para o tipo, o tipo do resultado será ampliado para acomodar o resultado, como no exemplo a seguir:

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

O tipo do resultado não será necessariamente o mesmo que um dos operandos. No exemplo a seguir, o valor negativo não pode ser convertido em um inteiro sem sinal e o inteiro não assinado é muito grande para ser convertido em `Int32` :

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

Neste exemplo, `Int64` pode acomodar ambos os tipos.

O `System.Decimal` tipo é uma exceção. Se um dos operandos tiver o tipo decimal, o resultado será do tipo decimal. Se o resultado for muito grande para o tipo decimal, ele não será convertido em Double. Em vez disso, ocorre um erro.

|Expression               |Resultado                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a>VARIÁVEIS E OPERADORES ARITMÉTICOS

Você também pode usar operadores aritméticos com variáveis. Os operadores atuam nos valores das variáveis. Os exemplos a seguir demonstram o uso de operadores aritméticos com variáveis:

| Expression                                    |Resultado      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a>OPERADORES ARITMÉTICOS E COMANDOS

Normalmente, você usa os operadores aritméticos em expressões com números, cadeias de caracteres e matrizes. No entanto, você também pode usar operadores aritméticos com os objetos que os comandos retornam e com as propriedades desses objetos.

Os exemplos a seguir mostram como usar os operadores aritméticos em expressões com comandos do PowerShell:

```powershell
(get-date) + (new-timespan -day 1)
```

O operador de parênteses força a avaliação do `get-date` cmdlet e a avaliação da `new-timespan -day 1` expressão do cmdlet, nessa ordem. Os dois resultados são então adicionados usando o `+` operador.

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

Na expressão acima, cada espaço de trabalho do processo ( `$_.ws` ) é multiplicado por `2` ; e o resultado é comparado com o `50mb` para ver se ele é maior que isso.

## <a name="bitwise-operators"></a>Operadores bit a bit

O PowerShell dá suporte aos operadores bit a bit padrão, incluindo AND bit-a-e ( `-bAnd` ), os operadores or (and) de or bitais inclusivos e exclusivos ( `-bOr` and `-bXor` ) e bit-a-not ( `-bNot` ).

A partir do PowerShell 2,0, todos os operadores de bit a ponto funcionam com inteiros de 64 bits.

A partir do PowerShell 3,0, o `-shr` (Shift-Right) e `-shl` (Shift-Left) são introduzidos para dar suporte à aritmética de ponto a bit no PowerShell.

O PowerShell dá suporte aos operadores bit a seguir.

| Operador | Descrição            | Expression   | Resultado |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | AND bit a bit            | `10 -band 3` | 2      |
| `-bor`   | OR-bit (inclusivo) | `10 -bor 3`  | 11     |
| `-bxor`  | OR-bit (exclusivo) | `10 -bxor 3` | 9      |
| `-bnot`  | NOT bit a bit            | `-bNot 10`   | -11    |
| `-shl`   | SHIFT-esquerda             | `102 -shl 2` | 408    |
| `-shr`   | SHIFT-direita            | `102 -shr 1` | 51     |

Os operadores bit a bit atuam no formato binário de um valor. Por exemplo, a estrutura de bits para o número 10 é 00001010 (com base em 1 byte) e a estrutura de bits para o número 3 é 00000011. Quando você usa um operador bit a bit para comparar 10 a 3, os bits individuais em cada byte são comparados.

Em uma operação AND de bits, o bit resultante é definido como 1 somente quando ambos os bits de entrada são 1.

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

Em uma operação (inclusiva) de bit (inclusive), o bit resultante é definido como 1 quando um ou ambos os bits de entrada são 1. O bit resultante é definido como 0 somente quando ambos os bits de entrada são definidos como 0.

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

Em uma operação OR (exclusiva) de bit (), o bit resultante é definido como 1 somente quando um bit de entrada é 1.

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

O operador nonbit-a NOT é um operador unário que produz o complemento binário do valor. Um bit de 1 é definido como 0 e um bit de 0 é definido como 1.

Por exemplo, o complemento binário de 0 é-1, o inteiro não assinado máximo (0xFFFFFFFF) e o complemento binário de-1 é 0.

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

Em uma operação de deslocamento para a esquerda de bit-a-ponto, todos os bits são movidos para a esquerda, em que "n" é o valor do operando direito. Um zero é inserido no lugar.

Quando o operando esquerdo é um valor inteiro (32 bits), os 5 bits inferiores do operando direito determinam quantos bits do operando esquerdo são deslocados.

Quando o operando esquerdo é um valor longo (64 bits), os 6 bits inferiores do operando à direita determinam quantos bits do operando esquerdo são deslocados.

|Expression |Resultado|Resultado binário|
|-----------|------|-------------|
|`21 -shl 0`|21    |0001 0101    |
|`21 -shl 1`|42    |0010 1010    |
|`21 -shl 2`|84    |0101 0100    |

Em uma operação Shift-Right de bit-a-ponto, todos os bits são movidos para "n" locais à direita, onde "n" é especificado pelo operando à direita. O operador Shift-Right (-SHR) insere um zero no lugar à esquerda ao deslocar um valor positivo ou não assinado para a direita.

Quando o operando esquerdo é um valor inteiro (32 bits), os 5 bits inferiores do operando direito determinam quantos bits do operando esquerdo são deslocados.

Quando o operando esquerdo é um valor longo (64 bits), os 6 bits inferiores do operando à direita determinam quantos bits do operando esquerdo são deslocados.

|Expression              |Resultado      |Binário     |Hex         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | 21         | 0001 0101 | 0x15       |
|`21 -shr 1`             | 10         | 0000 1010 | 0x0A       |
|`21 -shr 2`             | 5          | 0000 0101 | 0x05       |
|`21 -shr 31`            | 0          | 0000 0000 | 0x00       |
|`21 -shr 32`            | 21         | 0001 0101 | 0x15       |
|`21 -shr 64`            | 21         | 0001 0101 | 0x15       |
|`21 -shr 65`            | 10         | 0000 1010 | 0x0A       |
|`21 -shr 66`            | 5          | 0000 0101 | 0x05       |
|`[int]::MaxValue -shr 1`| 1073741823 |           | 0x3FFFFFFF |
|`[int]::MinValue -shr 1`| -1073741824|           | 0xC0000000 |
|`-1 -shr 1`             | -1         |           | 0xFFFFFFFF |

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_arrays](about_Arrays.md)
- [about_assignment_operators](about_Assignment_Operators.md)
- [about_comparison_operators](about_Comparison_Operators.md)
- [about_hash_tables](about_Hash_Tables.md)
- [about_operators](about_Operators.md)
- [about_variables](about_Variables.md)
- [Obter Data](xref:Microsoft.PowerShell.Utility.Get-Date)
- [New-TimeSpan](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
