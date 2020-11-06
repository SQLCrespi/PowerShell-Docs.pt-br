---
description: Tanto o inteiro quanto os literais numéricos reais podem ter os sufixos tipo e multiplicador.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre literais numéricos
ms.openlocfilehash: 19ed71c2571a6cd343adf622a8cf71d6e5589aff
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354976"
---
# <a name="about-numeric-literals"></a>Sobre literais numéricos

Há dois tipos de literais numéricos: inteiro e real. Ambos podem ter um tipo e sufixos de multiplicador.

## <a name="integer-literals"></a>Literais inteiros

Os literais inteiros podem ser gravados em notação decimal, hexadecimal ou binária.
Os literais hexadecimais são prefixados com `0x` e os literais binários são prefixados com `0b` para diferenciá-los de números decimais.

Os literais inteiros podem ter um sufixo de tipo e um sufixo de multiplicador.

| Sufixo |            Significado             |          Observação           |
| ------ | ------------------------------ | ----------------------- |
| s      | tipo de dados byte assinado          | Adicionado no PowerShell 6,2 |
| uy     | tipo de dados byte não assinado        | Adicionado no PowerShell 6,2 |
| s      | tipo de dados curto                | Adicionado no PowerShell 6,2 |
| us     | tipo de dados curto não assinado       | Adicionado no PowerShell 6,2 |
| l      | tipo de dados Long                 |                         |
| u      | tipo de dados int ou Long não assinado | Adicionado no PowerShell 6,2 |
| UL     | tipo de dados Long não assinado        | Adicionado no PowerShell 6,2 |
| n      | Tipo de dados BigInteger           | Adicionado no PowerShell 7,0 |
| kb     | multiplicador de kilobytes            |                         |
| mb     | multiplicador de megabyte            |                         |
| Reino     | multiplicador de Gigabyte            |                         |
| TB     | multiplicador de terabyte            |                         |
| PB     | multiplicador petabyte            |                         |

O tipo de um inteiro literal é determinado por seu valor, o sufixo de tipo e o sufixo de multiplicador numérico.

Para um literal inteiro sem sufixo de tipo:

- Se o valor puder ser representado por tipo `[int]` , que é seu tipo.
- Caso contrário, se o valor puder ser representado pelo tipo `[long]` , esse será seu tipo.
- Caso contrário, se o valor puder ser representado pelo tipo `[decimal]` , esse será seu tipo.
- Caso contrário, ele é representado por tipo `[double]` .

Para um literal inteiro com um sufixo de tipo:

- Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[uint]` , seu tipo será `[uint]` .
- Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[ulong]` , seu tipo será `[ulong]` .
- Se seu valor puder ser representado pelo tipo especificado, esse é seu tipo.
- Caso contrário, esse literal será malformado.

## <a name="real-literals"></a>Literais reais

Os literais reais só podem ser gravados em notação decimal. Essa notação pode incluir valores fracionários após um ponto decimal e notação científica usando uma parte exponencial.

A parte exponencial inclui um ' e ' seguido por um sinal opcional (+/-) e um número que representa o expoente. Por exemplo, o valor literal `1e2` é igual ao valor numérico 100.

Os literais reais podem ter um sufixo de tipo e um sufixo de multiplicador.

| Sufixo |       Significado       |
| ------ | ------------------- |
| d      | tipo de dados decimal   |
| kb     | multiplicador de kilobytes |
| mb     | multiplicador de megabyte |
| Reino     | multiplicador de Gigabyte |
| TB     | multiplicador de terabyte |
| PB     | multiplicador petabyte |

Há dois tipos de literal real: Double e decimal. Eles são indicados pela ausência ou presença, respectivamente, do sufixo de tipo decimal. O PowerShell não dá suporte a uma representação literal de um `[float]` valor. Um literal real duplo tem tipo `[double]` . Um literal real decimal tem tipo `[decimal]` .
Zeros à direita na parte fracionária de um literal real decimal são significativos.

Se o valor dos dígitos da parte exponencial em um `[double]` literal real for menor que o mínimo suportado, o valor desse `[double]` literal real será 0. Se o valor dos dígitos da parte exponencial em um `[decimal]` literal real for menor que o mínimo suportado, esse literal será malformado. Se o valor dos dígitos da parte exponencial em um `[double]` ou `[decimal]` literal real for maior que o máximo suportado, esse literal será malformado.

> [!NOTE]
> A sintaxe permite que um literal real duplo tenha um sufixo de tipo longo.
> O PowerShell trata esse caso como um literal inteiro cujo valor é representado por tipo `[long]` . Esse recurso foi retido para compatibilidade com versões anteriores do PowerShell. No entanto, os programadores são desencorajados de usar literais inteiros desse formulário, pois podem facilmente obscurecer o valor real do literal. Por exemplo, `1.2L` tem o valor 1, `1.2345e1L` tem o valor 12 e `1.2345e-5L` tem o valor 0, nenhum dos quais é imediatamente óbvio.

## <a name="numeric-multipliers"></a>Multiplicadores numéricos

Para conveniência, inteiros e literais reais podem conter um multiplicador numérico, que indica um de um conjunto de potências usadas com frequência de 2. O multiplicador numérico pode ser escrito em qualquer combinação de letras maiúsculas ou minúsculas.

Os sufixos de multiplicador podem ser usados em combinação com quaisquer sufixos de tipo, mas devem estar presentes após o sufixo de tipo. Por exemplo, o literal `100gbL` está malformado, mas o literal `100Lgb` é válido.

Se um multiplicador criar um valor que exceda os valores possíveis para o tipo numérico que o sufixo especifica, o literal será malformado. Por exemplo, o literal `1usgb` está malformado, porque o valor é maior do que o `1gb` permitido para o `[ushort]` tipo especificado pelo `us` sufixo.

### <a name="multiplier-examples"></a>Exemplos de multiplicador

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a>Aceleradores de tipo numérico

O PowerShell dá suporte aos seguintes aceleradores de tipos:

| Acelerador |         Observação         |           Descrição            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | Byte (não assinado)                  |
| `[sbyte]`   |                      | Byte (assinado)                    |
| `[Int16]`   |                      | inteiro de 16 bits                   |
| `[short]`   | alias para `[int16]`  | inteiro de 16 bits                   |
| `[UInt16]`  |                      | inteiro de 16 bits (não assinado)        |
| `[ushort]`  | alias para `[uint16]` | inteiro de 16 bits (não assinado)        |
| `[Int32]`   |                      | Inteiro de 32 bits                   |
| `[int]`     | alias para `[int32]`  | Inteiro de 32 bits                   |
| `[UInt32]`  |                      | inteiro de 32 bits (não assinado)        |
| `[uint]`    | alias para `[uint32]` | inteiro de 32 bits (não assinado)        |
| `[Int64]`   |                      | Inteiro de 64 bits                   |
| `[long]`    | alias para `[int64]`  | Inteiro de 64 bits                   |
| `[UInt64]`  |                      | inteiro de 64 bits (não assinado)        |
| `[ulong]`   | alias para `[uint64]` | inteiro de 64 bits (não assinado)        |
| `[bigint]`  |                      | Consulte a [estrutura BigInteger][bigint]  |
| `[single]`  |                      | Ponto flutuante de precisão única  |
| `[float]`   | alias para `[single]` | Ponto flutuante de precisão única  |
| `[double]`  |                      | Ponto flutuante de precisão dupla  |
| `[decimal]` |                      | ponto flutuante de 128 bits           |

> [!NOTE]
> Os seguintes aceleradores de tipos foram adicionados no PowerShell 6,2: `[short]` ,, `[ushort]` `[uint]` , `[ulong]` .

## <a name="examples"></a>Exemplos

A tabela a seguir contém vários exemplos de literais numéricos e lista seu tipo e valor:

|   Número    |    Tipo    |    Valor     |
| ----------: | ---------- | -----------: |
|         100 | Int32      |          100 |
|        100u | UInt32     |          100 |
|        100D | Decimal    |          100 |
|        100l | Int64      |          100 |
|       100uL | UInt64     |          100 |
|       100us | UInt16     |          100 |
|       100uy | Byte       |          100 |
|        100y | SByte      |          100 |
|         1e2 | Duplo     |          100 |
|        1. E2 | Duplo     |          100 |
|       0x1e2 | Int32      |          482 |
|      0x1e2L | Int64      |          482 |
|      0x1e2D | Int32      |         7725 |
|        482D | Decimal    |          482 |
|       482gb | Int64      | 517543559168 |
|      482ngb | BigInteger | 517543559168 |
|    0x1e2lgb | Int64      | 517543559168 |
|   0b1011011 | Int32      |           91 |
|     0xFFFFs | Int16      |           -1 |
|  0xFFFFFFFF | Int32      |           -1 |
| -0xFFFFFFFF | Int32      |            1 |
| 0xFFFFFFFFu | UInt32     |   4294967295 |

### <a name="working-with-binary-or-hexadecimal-numbers"></a>Trabalhando com números binários ou hexadecimais

Os literais binários ou hexadecimais excessivamente grandes podem retornar como `[bigint]` em vez de falhar na análise, se e somente se o `n` sufixo for especificado. No entanto, os bits de sinal ainda são respeitados acima dos `[decimal]` intervalos pares:

- Se uma cadeia de caracteres binária for de um múltiplo de 8 bits de comprimento, o bit mais alto será tratado como o bit de sinal.
- Se uma cadeia de caracteres hexadecimal, que tem um comprimento múltiplo de 8, tiver o primeiro dígito com 8 ou superior, o numeral será tratado como negativo.

A especificação de um sufixo não assinado em literais binários e hexadecimais ignora o sinal de bits. Por exemplo, `0xFFFFFFFF` retorna `-1` , mas `0xFFFFFFFFu` retorna o `[uint]::MaxValue` de 4294967295.

No PowerShell 7,1, o uso de um sufixo de tipo em um literal hexadecimal agora retorna um valor assinado desse tipo. Por exemplo, no PowerShell 7,0, a expressão `0xFFFFs` retorna um erro porque o valor positivo é muito grande para um `[int16]` tipo.
O PowerShell 7,1 interpreta isso como `-1` é um `[int16]` tipo.

A prefixação do literal com um `0` irá ignorá-lo e ser tratado como não assinado.
Por exemplo: `0b011111111`. Isso pode ser necessário ao trabalhar com literais no `[bigint]` intervalo, pois os `u` `n` sufixos e não podem ser combinados.

Você também pode negar literais binários e hexadecimais usando o `-` prefixo. Isso pode resultar em um número positivo desde que os bits de sinal sejam permitidos.

Os bits de sinal são aceitos para numerais com sufixo BigInteger:

- O Hex com sufixo BigInteger trata o alto bit de qualquer literal com um comprimento múltiplo de 8 caracteres como o bit de sinal. O comprimento não inclui o `0x` prefixo ou quaisquer sufixos.
- O binário BigInteger-suffix aceita a entrada de bits em 96 e 128 caracteres e a cada 8 caracteres após.

### <a name="commands-that-look-like-numeric-literals"></a>Comandos que se parecem com literais numéricos

Qualquer comando que se pareça com um literal numérico válido deve ser executado usando o operador Call ( `&` ), caso contrário, ele será interpretado como um número. Literais malformados com sintaxe válida `1usgb` , como resultarão no seguinte erro:

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

No entanto, literais malformados com sintaxe inválida como `1gbus` serão interpretados como uma cadeia de caracteres Bare padrão e podem ser interpretados como um nome de comando válido em contextos onde os comandos podem ser chamados.

### <a name="access-properties-and-methods-of-numeric-objects"></a>Acessar propriedades e métodos de objetos numéricos

Para acessar um membro de um literal numérico, há casos em que você precisa colocar o literal entre parênteses.

- O literal não tem um ponto decimal
- O literal não tem nenhum dígito após o ponto decimal
- O literal não tem um sufixo

Por exemplo, o exemplo a seguir falha:

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

Os exemplos a seguir funcionam:

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

Os dois primeiros exemplos funcionam sem colocar o valor literal entre parênteses porque o analisador do PowerShell pode determinar onde o literal numérico termina e o método **GetType** é iniciado.

## <a name="how-powershell-parses-numeric-literals"></a>Como o PowerShell analisa literais numéricos

O PowerShell v 7.0 mudou a forma como os literais numéricos são analisados para habilitar os novos recursos.

### <a name="parsing-real-numeric-literals"></a>Analisando literais numéricos reais

Se o literal contiver um ponto decimal ou a notação e-Notation, a cadeia de caracteres literal será analisada em um número real.

- Se o sufixo decimal estiver presente diretamente no `[decimal]` .
- Caso contrário, analise como `[Double]` e aplique multiplicador ao valor. Em seguida, verifique os sufixos de tipo e tente convertê-los no tipo apropriado.
- Se a cadeia de caracteres não tiver nenhum sufixo de tipo, analise como `[Double]` .

### <a name="paring-integer-numeric-literals"></a>Literais numéricos de número inteiro emparelhamento

Os literais de tipo inteiro são analisados usando as seguintes etapas:

1. Determinar o formato de base
   - Para formatos binários, analise em `[BigInteger]` .
   - Para formatos hexadecimais, analise o `[BigInteger]` uso de Casies especiais para manter os comportamentos originais quando o valor estiver no `[int]` `[long]` intervalo ou.
   - Se nem binário nem Hex, analise normalmente como um `[BigInteger]` .
2. Aplique o valor de multiplicador antes de tentar qualquer conversão para garantir que os limites de tipo possam ser verificados adequadamente sem estouros.
3. Verifique os sufixos de tipo.
   - Verifique os limites de tipo e tente analisar nesse tipo.
   - Se nenhum sufixo for usado, o valor será associado, marcado na seguinte ordem, resultando no primeiro teste bem-sucedido que determina o tipo do número.
     - `[int]`
     - `[long]`
     - `[decimal]` (somente literais de base 10)
     - `[double]` (somente literais de base 10)
   - Se o valor estiver fora do `[long]` intervalo para números Hex e binários, a análise falhará.
   - Se o valor estiver fora do `[double]` intervalo para o número de base 10, a análise falhará.
   - Valores mais altos devem ser gravados explicitamente usando o `n` sufixo para analisar o literal como um `BigInteger` .

### <a name="parsing-large-value-literals"></a>Analisando literais de valor grande

Anteriormente, valores inteiros mais altos eram analisados como duplo antes de serem convertidos em qualquer outro tipo. Isso resulta em uma perda de precisão nos intervalos mais altos. Por exemplo:

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

Para evitar esse problema, você tinha que escrever valores como cadeias de caracteres e, em seguida, convertê-los:

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

No PowerShell 7,0, você deve usar o `N` sufixo.

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

Além disso, os valores entre `[ulong]::MaxValue` e `[decimal]::MaxValue` devem ser indicados usando o sufixo decimal `D` para manter a precisão. Sem o sufixo, esses valores são analisados como `[Double]` usando o modo de análise real.

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
