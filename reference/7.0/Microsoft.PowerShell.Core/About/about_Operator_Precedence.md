---
description: Lista os operadores do PowerShell em ordem de precedência.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 8f0f69f2328343b9655ebd0d7515a469565ff5f5
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483088"
---
# <a name="about-operator-precedence"></a>Sobre a precedência de operador

## <a name="short-description"></a>DESCRIÇÃO BREVE
Lista os operadores do PowerShell em ordem de precedência.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os operadores do PowerShell permitem construir expressões simples, mas poderosas. Este tópico lista os operadores em ordem de precedência. Ordem de precedência é a ordem na qual o PowerShell avalia os operadores quando vários operadores aparecem na mesma expressão.

Quando os operadores têm precedência igual, o PowerShell os avalia da esquerda para a direita, conforme aparecem dentro da expressão. As exceções são os operadores de atribuição, os operadores de conversão e os operadores de negação ( `!` , `-not` , `-bnot` ), que são avaliados da direita para a esquerda.

Você pode usar os compartimentos, como parênteses, para substituir a ordem de precedência padrão e forçar o PowerShell a avaliar a parte inclusa de uma expressão antes de uma parte não colocada.

Na lista a seguir, os operadores são listados na ordem em que são avaliados. Os operadores na mesma linha ou no mesmo grupo têm precedência igual.

A coluna operador lista os operadores. A coluna referência lista o tópico de ajuda do PowerShell no qual o operador é descrito. Para exibir o tópico, digite `get-help <topic-name>` .

|         OPERATOR         |           REFERÊNCIA            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | [about_Operators][]            |
| `. ?.` (acesso de membro)   | [about_Operators][]            |
| `::` auto-estática            | [about_Operators][]            |
| `[0] ?[0]` (operador de índice) | [about_Operators][]         |
| `[int]` (operadores de conversão) | [about_Operators][]            |
| `-split` unário         | [about_Split][]                |
| `-join` unário          | [about_Join][]                 |
| `,` (operador de vírgula)     | [about_Operators][]            |
| `++ --`                  | [about_Assignment_Operators][] |
| `! -not`                 | [about_Logical_Operators][]    |
| `..` (operador de intervalo)    | [about_Operators][]            |
| `-f` (operador Format)   | [about_Operators][]            |
| `-` (unário/negativo)     | [about_Arithmetic_Operators][] |
| `* / %`                  | [about_Arithmetic_Operators][] |
| `+ -`                    | [about_Arithmetic_Operators][] |

O grupo de operadores a seguir tem precedência igual. Suas variantes que diferenciam maiúsculas de minúsculas e explicitamente não diferenciam maiúsculas de minúsculas têm a mesma precedência.

|         OPERATOR          |           REFERÊNCIA            |
| ------------------------- | ------------------------------ |
| `-split` binário         | [about_Split][]                |
| `-join` binário          | [about_Join][]                 |
| `-is -isnot -as`          | [about_Type_Operators][]       |
| `-eq -ne -gt -gt -lt -le` | [about_Comparison_Operators][] |
| `-like -notlike`          | [about_Comparison_Operators][] |
| `-match -notmatch`        | [about_Comparison_Operators][] |
| `-in -notIn`              | [about_Comparison_Operators][] |
| `-contains -notContains`  | [about_Comparison_Operators][] |
| `-replace`                | [about_Comparison_Operators][] |

A lista é retomada aqui com os seguintes operadores na ordem de precedência:

|                OPERATOR                 |           REFERÊNCIA            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | [about_Arithmetic_Operators][] |
| `-and -or -xor`                         | [about_Logical_Operators][]    |

Os itens a seguir não são operadores verdadeiros. Eles fazem parte da sintaxe de comando do PowerShell, não da sintaxe de expressão. A atribuição é sempre a última ação que acontece.

|                SYNTAX                   |           REFERÊNCIA            |
| --------------------------------------- | ------------------------------ |
| `.` (ponto-fonte)                        | [about_Operators][]            |
| `&` ligação                              | [about_Operators][]            |
| `? <if-true> : <if-false>` (Operador ternário) | [about_Operators][]      |
| `??` (operador NULL-)            | [about_Operators][]            |
| <code>&#124;</code> (operador de pipeline) | [about_Operators][]            |
| `> >> 2> 2>> 2>&1`                      | [about_Redirection][]          |
| <code>&& &#124;&#124;</code> (operadores de cadeia de pipeline) | [about_Operators][] |
| `= += -= *= /= %= ??=`                  | [about_Assignment_Operators][] |

## <a name="examples"></a>EXEMPLOS

Os dois comandos a seguir mostram os operadores aritméticos e o efeito de usar parênteses para forçar o PowerShell a avaliar a parte incluída da expressão primeiro.

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

O exemplo a seguir obtém os arquivos de texto somente leitura do diretório local e os salva na `$read_only` variável.

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

É equivalente ao exemplo a seguir.

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

Como o operador de pipeline ( `|` ) tem uma precedência mais alta do que o operador de atribuição ( `=` ), os arquivos que o `Get-ChildItem` cmdlet obtém são enviados para o `Where-Object` cmdlet para filtragem antes de serem atribuídos à `$read_only` variável.

O exemplo a seguir demonstra que o operador de índice tem precedência sobre o operador cast.

Essa expressão cria uma matriz de três cadeias de caracteres. Em seguida, ele usa o operador de índice com um valor de 0 para selecionar o primeiro objeto na matriz, que é a primeira cadeia de caracteres. Por fim, ele converte o objeto selecionado como uma cadeia de caracteres. Nesse caso, a conversão não tem nenhum efeito.

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

Essa expressão usa parênteses para forçar a operação de conversão a ocorrer antes da seleção de índice. Como resultado, toda a matriz é convertida como uma cadeia de caracteres (única). Em seguida, o operador de índice seleciona o primeiro item na matriz de cadeia de caracteres, que é o primeiro caractere.

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

No exemplo a seguir, como o `-gt` operador (maior que) tem uma precedência mais alta do que o `-and` operador (and lógico), o resultado da expressão é false.

```powershell
PS> 2 -gt 4 -and 1
False
```

É equivalente à expressão a seguir.

```powershell
PS> (2 -gt 4) -and 1
False
```

Se o operador and tiver precedência mais alta, a resposta seria TRUE.

```powershell
PS> 2 -gt (4 -and 1)
True
```

No entanto, este exemplo demonstra um princípio importante do gerenciamento de precedência de operador. Quando uma expressão é difícil para as pessoas interpretarem, use parênteses para forçar a ordem de avaliação, mesmo quando ela força a precedência de operador padrão. Os parênteses tornam suas intenções claras para as pessoas que estão lendo e mantendo seus scripts.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Operators][]

[about_Assignment_Operators][]

[about_Comparison_Operators][]

[about_Arithmetic_Operators][]

[about_Join][]

[about_Redirection][]

[about_Scopes][]

[about_Split][]

[about_Type_Operators][]

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md
