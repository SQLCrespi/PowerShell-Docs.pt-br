---
description: Descreve expressões regulares no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 6112c63b6d0c1018b56df85ec6ae919a0285ffc3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195661"
---
# <a name="about-regular-expressions"></a>Sobre expressões regulares

## <a name="short-description"></a>Descrição breve
Descreve expressões regulares no PowerShell.

## <a name="long-description"></a>Descrição longa

> [!NOTE]
> Este artigo mostrará a sintaxe e os métodos para usar expressões regulares no PowerShell, nem toda a sintaxe será discutida. Para obter uma referência mais completa, consulte a [linguagem de expressão regular – referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).

Uma expressão regular é um padrão usado para corresponder texto. Ele pode ser composto por caracteres literais, operadores e outras construções.

Este artigo demonstra a sintaxe de expressão regular no PowerShell. O PowerShell tem vários operadores e cmdlets que usam expressões regulares. Você pode ler mais sobre sua sintaxe e uso nos links abaixo.

- [Select-String](xref:Microsoft.PowerShell.Utility.Select-String)
- [operadores de correspondência e substituição](about_Comparison_Operators.md)
- [-Divisão](about_Split.md)
- [instrução switch com a opção-Regex](about_Switch.md)

As expressões regulares do PowerShell não diferenciam maiúsculas de minúsculas por padrão. Cada método mostrado acima tem uma maneira diferente de forçar a diferenciação de maiúsculas e minúsculas.

|       Método       |                      Diferenciação de maiúsculas e minúsculas                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | usar `-CaseSensitive` opção                                |
| Instrução `switch` | Use a `-casesensitive` opção                            |
| operadores          | prefixar com **' C'** ( `-cmatch` , `-csplit` ou `-creplace` ) |

### <a name="character-literals"></a>Literais de caracteres

Uma expressão regular pode ser um caractere literal ou uma cadeia de caracteres. A expressão faz com que o mecanismo corresponda exatamente ao texto especificado.

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a>Classes de caracteres

Enquanto os literais de caractere funcionam se você sabe o padrão exato, as classes de caractere permitem que você seja menos específico.

#### <a name="character-groups"></a>Grupos de caracteres

`[character group]` permite que você corresponda a qualquer número de caracteres uma vez, enquanto `[^character group]` só corresponde a caracteres que não estão no grupo.

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

Se a lista de caracteres a corresponder incluir o caractere de hífen ( `-` ), ela deverá estar no início ou no final da lista para distingui-la de uma expressão de intervalo de caracteres.

#### <a name="character-ranges"></a>Intervalos de caracteres

Um padrão também pode ser um intervalo de caracteres. Os caracteres podem ser alfabéticos `[A-Z]` , numéricos `[0-9]` ou até mesmo baseados em ASCII `[ -~]` (todos os caracteres imprimíveis).

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a>Números

A `\d` classe de caractere corresponderá a qualquer dígito decimal. Por outro lado, o `\D` coincidirá com qualquer dígito diferente de Decimal.

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a>Caracteres de palavra

A `\w` classe de caractere corresponderá a qualquer caractere de palavra `[a-zA-Z_0-9]` . Para corresponder a qualquer caractere que não seja palavra, use `\W` .

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a>Curingas

O period ( `.` ) é um caractere curinga em expressões regulares. Ele fará a correspondência de qualquer caractere, exceto uma nova linha ( `\n` ).

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a>Espaço em branco

O espaço em branco é correspondido usando a `\s` classe Character. Qualquer caractere diferente de espaço em branco é correspondido usando `\S` . Os caracteres de espaço literal `' '` também podem ser usados.

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a>Quantificadores

Quantificadores controlam quantas instâncias de cada elemento devem estar presentes na cadeia de caracteres de entrada.

A seguir estão alguns dos quantificadores disponíveis no PowerShell:

| Quantificador |                Descrição                |
| ---------- | ----------------------------------------- |
| `*`        | Zero ou mais vezes.                       |
| `+`        | Uma ou mais vezes.                        |
| `?`        | Zero ou uma vez.                         |
| `{n,m}`    | Pelo menos `n` , mas não mais do que `m` vezes. |

O asterisco ( `*` ) corresponde ao elemento anterior zero ou mais vezes. O resultado é que até mesmo uma cadeia de caracteres de entrada sem o elemento seria uma correspondência.

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

O sinal de adição ( `+` ) corresponde ao elemento anterior uma ou mais vezes.

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

O ponto de interrogação `?` corresponde ao elemento anterior zero ou uma vez. Como `*` um asterisco, ele corresponderá até mesmo às cadeias de caracteres em que o elemento está ausente.

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

O `{n, m}` quantificador pode ser usado de várias maneiras diferentes para permitir o controle granular do quantificador. O segundo elemento `m` e a vírgula `,` são opcionais.

| Quantificador |                Descrição                 |
| ---------- | ------------------------------------------ |
| `{n}`      | Corresponder exatamente ao `n` número de vezes.         |
| `{n,}`     | Corresponder pelo menos `n` número de vezes.        |
| `{n,m}`    | Correspondência entre `n` e `m` número de vezes. |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a>Âncoras

As âncoras permitem que você cause uma correspondência com êxito ou falha com base na posição de correspondências dentro da cadeia de caracteres de entrada.

As duas âncoras comumente usadas são `^` e `$` . O cursor `^` corresponde ao início de uma cadeia de caracteres e `$` , que corresponde ao final de uma cadeia de caracteres. As âncoras permitem que você corresponda ao texto em uma posição específica enquanto também descarta caracteres indesejados.

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> Ao definir um Regex contendo uma `$` âncora, certifique-se de colocar o Regex usando aspas simples ( `'` ) em vez de aspas duplas ( `"` ) ou o PowerShell expandirá a expressão como uma variável.

Ao usar âncoras no PowerShell, você deve entender a diferença entre as opções de expressão única de linhas **simples** e de **multilinha** .

- **Multiline** : o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.
- **Unificação** : o modo de única trata a cadeia de caracteres de entrada como uma **única** .
  Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .

Para ler mais sobre essas opções e como usá-las, visite a [linguagem de expressão regular-referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).

### <a name="escaping-characters"></a>Caracteres de escape

A barra invertida ( `\` ) é usada para escapar caracteres para que eles não sejam analisados pelo mecanismo de expressão regular.

Os seguintes caracteres são reservados: `[]().\^$|?*+{}` .

Você precisará escapar desses caracteres em seus padrões para que correspondam a eles nas cadeias de caracteres de entrada.

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

Há um método estático da classe Regex que pode escapar do texto para você.

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> Isso escapa todos os caracteres de expressão regular reservados, incluindo barras invertidas existentes usadas em classes de caracteres. Certifique-se de usá-lo apenas na parte do padrão que você precisa escapar.

#### <a name="other-character-escapes"></a>Outros escapes de caractere

Também há escapes de caractere reservado que você pode usar para corresponder a tipos de caracteres especiais.

A seguir estão alguns escapes de caractere usados com frequência:

|Escape de caractere  |Descrição  |
|---------|---------|
|`\t`|Corresponde a uma tabulação|
|`\n`|Corresponde a uma nova linha|
|`\r`|Corresponde a um retorno de carro|

### <a name="groups-captures-and-substitutions"></a>Grupos, capturas e substituições

O agrupamento de construções separa uma cadeia de caracteres de entrada em subcadeias de caracteres que podem ser capturadas ou ignoradas. Subcadeias de caracteres agrupadas são chamadas de subexpressões. Por padrão, as subexpressões são capturadas em grupos numerados, embora você também possa atribuir nomes a elas.

Uma construção de agrupamento é uma expressão regular entre parênteses. Qualquer texto correspondido pela expressão regular embutida é capturado. O exemplo a seguir quebrará o texto de entrada em dois grupos de captura.

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

Use a `$Matches` variável automática **Hashtable** para recuperar o texto capturado.
O texto que representa a correspondência inteira é armazenado na chave `0` .

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

As capturas são armazenadas em chaves de **inteiro** numéricos que aumentam da esquerda para a direita. A captura `1` contém todo o texto até que o nome de usuário, Capture `2` contenha apenas o nome de usuário.

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> A `0` chave é um **número inteiro** . Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.
>
> ```
> PS> 'Good Dog' -match 'Dog'
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

#### <a name="named-captures"></a>Capturas nomeadas

Por padrão, as capturas são armazenadas em ordem numérica crescente, da esquerda para a direita.
Você também pode atribuir um **nome** a um grupo de captura. Esse **nome** se torna uma chave na `$Matches` variável automática de **Hashtable** .

Dentro de um grupo de captura, use `?<keyname>` para armazenar dados capturados em uma chave nomeada.

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

O exemplo a seguir armazena a entrada de log mais recente no log de segurança do Windows.
A expressão regular fornecida extrai o nome de usuário e o domínio da mensagem e os armazena sob as chaves: **N** para nome e **D** para o domínio.

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

Para obter mais informações, consulte [agrupando construções em expressões regulares](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).

#### <a name="substitutions-in-regular-expressions"></a>Substituições em expressões regulares

Usar as expressões regulares com o `-replace` operador permite que você substitua dinamicamente o texto usando o texto capturado.

`<input> -replace <original>, <substitute>`

- `<input>`: A cadeia de caracteres a ser pesquisada
- `<original>`: Uma expressão regular usada para pesquisar a cadeia de caracteres de entrada
- `<substitute>`: Uma expressão de substituição de expressão regular para substituir as correspondências encontradas na cadeia de caracteres de entrada.

> [!NOTE]
> Os `<original>` `<substitute>` operandos e estão sujeitos às regras do mecanismo de expressão regular, como saída de caracteres.

Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres. A substituição é feita usando o `$` caractere antes do identificador de grupo.

Duas maneiras de fazer referência a grupos de captura são por **número** e por **nome** .

- Por grupos de captura de **número** , são numerados da esquerda para a direita.

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- Os grupos de captura de **nomes** também podem ser referenciados pelo nome.

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

A `$&` expressão representa todo o texto correspondido.

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> Como o `$` caractere é usado na expansão da cadeia de caracteres, você precisará usar cadeias literais com substituição ou escapar o `$` caractere ao usar aspas duplas.
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> Além disso, se você quiser ter o `$` como um caractere literal, use `$$` em vez dos caracteres de escape normais. Ao usar aspas duplas, ainda escapar de todas as instâncias do `$` para evitar a substituição incorreta.
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

Para obter mais informações, consulte [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="see-also"></a>Confira também

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Operators](about_Operators.md)
