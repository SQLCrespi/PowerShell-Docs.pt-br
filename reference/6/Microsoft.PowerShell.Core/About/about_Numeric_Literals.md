---
description: Tanto o inteiro quanto os literais numéricos reais podem ter os sufixos tipo e multiplicador.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre literais numéricos
ms.openlocfilehash: 62f00ae9f3643724808146134fd03b6f01c29bce
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196506"
---
# <a name="about-numeric-literals"></a>Sobre literais numéricos

Há dois tipos de literais numéricos: inteiro e real. Ambos podem ter um tipo e sufixos de multiplicador.

## <a name="integer-literals"></a>Literais inteiros

Literais inteiros podem ser escritos em notação decimal ou hexadecimal. Os literais hexadecimais são prefixados com `0x` para distingui-los de números decimais.

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

Os sufixos de multiplicador podem ser usados em combinação com os `u` `ul` `l` sufixos, e de tipo.

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

### <a name="working-with-other-numeric-types"></a>Trabalhando com outros tipos numéricos

Para trabalhar com qualquer outro tipo numérico, você deve usar aceleradores de tipo, que não está sem alguns problemas. Por exemplo, valores inteiros altos são sempre analisados como Double antes de serem convertidos em qualquer outro tipo.

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

O valor é analisado como um duplo primeiro, perdendo a precisão nos intervalos mais altos.
Para evitar esse problema, insira valores como cadeias de caracteres e, em seguida, converta-os:

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a>Exemplos

A tabela a seguir contém vários exemplos de literais numéricos e lista seu tipo e valor:

|  Número  |  Tipo   |    Valor     |
| -------: | ------- | -----------: |
|      100 | Int32   |          100 |
|     100D | Decimal |          100 |
|     100l | Int64   |          100 |
|    100uL | UInt64  |          100 |
|    100us | UInt16  |          100 |
|    100uy | Byte    |          100 |
|     100y | SByte   |          100 |
|      1e2 | Duplo  |          100 |
|     1. E2 | Duplo  |          100 |
|    0x1e2 | Int32   |          482 |
|   0x1e2L | Int64   |          482 |
|   0x1e2D | Int32   |         7725 |
|     482D | Decimal |          482 |
|    482gb | Int64   | 517543559168 |
| 0x1e2lgb | Int64   | 517543559168 |

### <a name="commands-that-look-like-numeric-literals"></a>Comandos que se parecem com literais numéricos

Qualquer comando que se pareça com um literal numérico deve ser executado usando o operador Call ( `&` ), caso contrário, ele será interpretado como um número do tipo associado.

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

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger?view=netcore-2.2
