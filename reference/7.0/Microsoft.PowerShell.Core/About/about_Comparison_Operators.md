---
description: Descreve os operadores que comparam valores no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: d6096de14d0bb8c7ba86c0585806b86cf3bb921a
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196469"
---
# <a name="about-comparison-operators"></a>Sobre operadores de comparação

## <a name="short-description"></a>Descrição breve
Descreve os operadores que comparam valores no PowerShell.

## <a name="long-description"></a>Descrição longa

Os operadores de comparação permitem especificar condições para comparar valores e localizar valores que correspondam aos padrões especificados. Para usar um operador de comparação, especifique os valores que você deseja comparar junto com um operador que separa esses valores.

O PowerShell inclui os seguintes operadores de comparação:

| Tipo        | Operadores    | Descrição                                 |
| ----------- | ------------ | --------------------------------------------|
| Igualitário    | -eq          | igual a                                      |
|             | -ne          | Não é igual a                                  |
|             | -gt          | maior que                                |
|             | -ge          | maior ou igual                       |
|             | -lt          | menor que                                   |
|             | -le          | menor ou igual                          |
|             |              |                                             |
| Matching    | -like        | Retorna true quando a cadeia de caracteres corresponde ao curinga   |
|             |              | pattern                                     |
|             | -notlike     | Retorna true quando a cadeia de caracteres não corresponde     |
|             |              | padrão de curinga                            |
|             | -match       | Retorna true quando a cadeia de caracteres corresponde ao Regex      |
|             |              | padrão $matches contém cadeias de caracteres correspondentes |
|             | -Não correspondente    | Retorna true quando a cadeia de caracteres não corresponde     |
|             |              | padrão Regex; $matches contém correspondência   |
|             |              | cadeias de caracteres                                     |
|             |              |                                             |
| Contenção | -contains    | Retorna true quando o valor de referência está contido |
|             |              | em uma coleção                             |
|             | -notcontains | Retorna true quando o valor de referência não é       |
|             |              | contido em uma coleção                   |
|             | -in          | Retorna true quando o valor de teste está contido em um |
|             |              | collection                                  |
|             | -notin       | Retorna true quando o valor de teste não está contido  |
|             |              | em uma coleção                             |
|             |              |                                             |
| Substituição | -substituir     | Substitui um padrão de cadeia de caracteres                   |
|             |              |                                             |
| Tipo        | -é          | Retornará true se ambos os objetos forem iguais    |
|             |              | tipo                                        |
|             | -IsNot       | Retornará true se os objetos não forem iguais|
|             |              | tipo                                        |

Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas. Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, preceda o nome do operador com um `c` . Por exemplo, a versão de diferenciação de maiúsculas e minúsculas do `-eq` é `-ceq` . Para tornar a diferenciação de maiúsculas e minúsculas explícita, preceda o operador com um `i` . Por exemplo, a versão explicitamente não diferencia maiúsculas de minúsculas de `-eq` é `-ieq` .

Quando a entrada para um operador é um valor escalar, os operadores de comparação retornam um valor booliano. Quando a entrada é uma coleção de valores, os operadores de comparação retornam quaisquer valores correspondentes. Se não houver nenhuma correspondência em uma coleção, os operadores de comparação retornarão uma matriz vazia.

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

As exceções são os operadores de confinamento, os operadores in e os operadores de tipo, que sempre retornam um valor **booliano** .

> [!NOTE]
> Se você precisar comparar um valor para `$null` você deve colocar `$null` no lado esquerdo da comparação. Quando você compara `$null` a um **objeto []** , o resultado é **false** porque o objeto de comparação é uma matriz. Quando você compara uma matriz com `$null` o, a comparação filtra quaisquer `$null` valores armazenados na matriz. Por exemplo:
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a>Operadores de igualdade

Os operadores de igualdade ( `-eq` , `-ne` ) retornam um valor de true ou as correspondências quando um ou mais valores de entrada são idênticos ao padrão especificado. O padrão inteiro deve corresponder a um valor inteiro.

Exemplo:

#### <a name="-eq"></a>-eq

Descrição: igual a. Inclui um valor idêntico.

Exemplo:

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

#### <a name="-ne"></a>-ne

Descrição: diferente de. Inclui um valor diferente.

Exemplo:

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

#### <a name="-gt"></a>-gt

Descrição: maior que.

Exemplo:

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> Isso não deve ser confundido com `>` o operador maior que em muitas outras linguagens de programação. No PowerShell, `>` é usado para redirecionamento. Para obter mais informações, consulte [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).

#### <a name="-ge"></a>-ge

Descrição: maior que ou igual a.

Exemplo:

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a>-lt

Descrição: menor que.

Exemplo:

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a>-le

Descrição: menor que ou igual a.

Exemplo:

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a>Operadores correspondentes

Os operadores like ( `-like` e `-notlike` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões curinga.

A sintaxe do é:

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

Os operadores de correspondência ( `-match` e `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões regulares.

Os operadores de correspondência preenchem a `$Matches` variável automática quando a entrada (o argumento do lado esquerdo) para o operador é um único objeto escalar. Quando a entrada é escalar, os `-match` `-notmatch` operadores e retornam um valor booliano e definem o valor da `$Matches` variável automática para os componentes correspondentes do argumento.

A sintaxe do é:

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a>-like

Descrição: correspondência usando o caractere curinga ( \* ).

Exemplo:

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a>-notlike

Descrição: não corresponde usando o caractere curinga ( \* ).

Exemplo:

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a>-match

Descrição: corresponde a uma cadeia de caracteres usando expressões regulares. Quando a entrada é escalar, ela popula a `$Matches` variável automática.

Se a entrada for uma coleção, os `-match` `-notmatch` operadores e retornarão os membros correspondentes dessa coleção, mas o operador não preencherá a `$Matches` variável.

Por exemplo, o comando a seguir envia uma coleção de cadeias de caracteres para o `-match` operador. O `-match` operador retorna os itens na coleção que correspondem. Ele não preenche a `$Matches` variável automática.

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

Por outro lado, o comando a seguir envia uma única cadeia de caracteres para o `-match` operador. O `-match` operador retorna um valor booliano e popula a `$Matches` variável automática. A `$Matches` variável automática é uma **tabela de hash** . Se nenhum agrupamento ou captura for usado, apenas uma chave será populada.
A `0` chave representa todo o texto que foi correspondido. Para obter mais informações sobre agrupamento e captura usando expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

É importante observar que a tabela de `$Matches` hash conterá apenas a primeira ocorrência de qualquer padrão correspondente.

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> A `0` chave é um **número inteiro** . Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.
>
> ```powershell
> PS> "Good Dog" -match "Dog"
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

O `-notmatch` operador popula a `$Matches` variável automática quando a entrada é escalar e o resultado é false, quando detecta uma correspondência.

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

#### <a name="-notmatch"></a>-Não correspondente

Descrição: não corresponde a uma cadeia de caracteres. Usa expressões regulares. Quando a entrada é escalar, ela popula a `$Matches` variável automática.

Exemplo:

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

### <a name="containment-operators"></a>Operadores de confinamento

Os operadores de confinamento ( `-contains` e `-notcontains` ) são semelhantes aos operadores de igualdade. No entanto, os operadores de confinamento sempre retornam um valor booliano, mesmo quando a entrada é uma coleção.

Além disso, ao contrário dos operadores de igualdade, os operadores de confinamento retornam um valor assim que detectam a primeira correspondência. Os operadores de igualdade avaliam todas as entradas e retornam todas as correspondências na coleção.

#### <a name="-contains"></a>-contains

Descrição: operador de contenção. Informa se uma coleção de valores de referência inclui um único valor de teste. Sempre retorna um valor booliano. Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.

Quando o valor de teste é uma coleção, o operador Contains usa a igualdade de referência. Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.

Em uma coleção muito grande, o `-contains` operador retorna resultados mais rapidamente do que o operador igual a.

Sintaxe:

`<Reference-values> -contains <Test-value>`

Exemplos:

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

#### <a name="-notcontains"></a>-notcontains

Descrição: operador de contenção. Informa se uma coleção de valores de referência inclui um único valor de teste. Sempre retorna um valor booliano. Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.

Quando o valor de teste é uma coleção, o operador não Contains usa a igualdade de referência.

Sintaxe:

`<Reference-values> -notcontains <Test-value>`

Exemplos:

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

#### <a name="-in"></a>-in

Descrição: no operador. Informa se um valor de teste aparece em uma coleção de valores de referência. Sempre retornar como valor booliano. Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.

Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.
Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.

O `-in` operador foi introduzido no PowerShell 3,0.

Sintaxe:

`<Test-value> -in <Reference-values>`

Exemplos:

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

#### <a name="-notin"></a>-notin

Descrição: informa se um valor de teste aparece em uma coleção de valores de referência. Sempre retorna um valor booliano. Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.

Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.
Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.

O `-notin` operador foi introduzido no PowerShell 3,0.

Sintaxe:

`<Test-value> -notin <Reference-values>`

Exemplos:

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

### <a name="replacement-operator"></a>Operador de substituição

O `-replace` operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares. Você pode usar o `-replace` operador para muitas tarefas administrativas, como renomear arquivos. Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os arquivos. txt para. log:

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

A sintaxe do `-replace` operador é a seguinte, em que o `<original>` espaço reservado representa os caracteres a serem substituídos e o `<substitute>` espaço reservado representa os caracteres que os substituirão:

`<input> <operator> <original>, <substitute>`

Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas. Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` . Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .

Considere os seguintes exemplos:

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições. Para obter mais informações, consulte [about_Regular_Expressions](about_Regular_Expressions.md).

### <a name="scriptblock-substitutions"></a>Substituições de ScriptBlock

A partir do PowerShell 6, você pode usar um argumento **scriptblock** para o texto de *substituição* . O **scriptblock** será executado para cada correspondência encontrada na cadeia de caracteres de *entrada* .

Dentro do **scriptblock** , use a `$_` variável automática para fazer referência ao objeto **System. Text. RegularExpressions. Match** atual. O objeto **Match** fornece acesso ao texto de entrada atual que está sendo substituído, bem como outras informações úteis.

Este exemplo substitui cada sequência de três decimais pelo caractere equivalente. O **scriptblock** é executado para cada conjunto de três decimais que precisa ser substituído.

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

### <a name="type-comparison"></a>Comparação de tipos

Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.

#### <a name="-is"></a>-é

Sintaxe:

`<object> -is <type reference>`

Exemplo:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a>-IsNot

Sintaxe:

`<object> -isnot <type reference>`

Exemplo:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
