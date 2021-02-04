---
description: Descreve os operadores que comparam valores no PowerShell.
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: 9c868b376bdd2e4fda3950f68a09e6569d44853d
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98619917"
---
# <a name="about-comparison-operators"></a>Sobre operadores de comparação

## <a name="short-description"></a>Descrição breve

Os operadores de comparação no PowerShell podem comparar dois valores ou filtrar elementos de uma coleção em relação a um valor de entrada.

## <a name="long-description"></a>Descrição longa

Os operadores de comparação permitem comparar valores ou localizar valores que correspondem aos padrões especificados. O PowerShell inclui os seguintes operadores de comparação:

|    Tipo     |   Operador   |              Teste de comparação              |
| ----------- | ------------ | ----------------------------------------- |
| Igualitário    | -eq          | equals                                    |
|             | -ne          | Não é igual a                                |
|             | -gt          | maior que                              |
|             | -ge          | maior ou igual                     |
|             | -lt          | menor que                                 |
|             | -le          | menor ou igual                        |
| Matching    | -like        | Cadeia de caracteres corresponde ao padrão curinga           |
|             | -notlike     | a cadeia de caracteres não corresponde ao padrão curinga    |
|             | -match       | Cadeia de caracteres corresponde ao padrão Regex              |
|             | -Não correspondente    | a cadeia de caracteres não corresponde ao padrão Regex       |
| Substituição | -substituir     | Substitui cadeias de caracteres correspondentes a um padrão Regex |
| Contenção | -contains    | a coleção contém um valor               |
|             | -notcontains | a coleção não contém um valor       |
|             | -in          | o valor está em uma coleção                  |
|             | -notin       | o valor não está em uma coleção              |
| Tipo        | -é          | ambos os objetos são do mesmo tipo            |
|             | -IsNot       | os objetos não são do mesmo tipo         |

## <a name="common-features"></a>Recursos comuns

Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas. Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, adicione um `c` após o `-` . Por exemplo, `-ceq` é a versão que diferencia maiúsculas de minúsculas do `-eq` . Para tornar a diferenciação de maiúsculas e minúsculas explícita, adicione um `i` antes `-` . Por exemplo, `-ieq` é a versão explicitamente sem diferenciação de maiúsculas e minúsculas do `-eq` .

Quando a entrada de um operador é um valor escalar, o operador retorna um valor **booliano** . Quando a entrada é uma coleção, o operador retorna os elementos da coleção que correspondem ao valor do lado direito da expressão.
Se não houver nenhuma correspondência na coleção, os operadores de comparação retornarão uma matriz vazia. Por exemplo:

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

Há algumas exceções:

- Os operadores de contenção e de tipo sempre retornam um valor **booliano**
- O `-replace` operador retorna o resultado de substituição
- Os `-match` `-notmatch` operadores e também preenchem a `$Matches` variável automática

## <a name="equality-operators"></a>Operadores de igualdade

### <a name="-eq-and--ne"></a>-eq e -ne

Quando o lado esquerdo for escalar, `-eq` retornará **true** se o lado direito for uma correspondência exata, caso contrário, `-eq` retornará **false**. `-ne` faz o oposto; retorna **false** quando ambos os lados correspondem; caso contrário, `-ne` retornará true.

Exemplo:

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

Quando o lado esquerdo é uma coleção, `-eq` retorna os membros que correspondem ao lado direito, enquanto `-ne` os filtra.

Exemplo:

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

Esses operadores processam todos os elementos da coleção. Exemplo:

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

Os operadores de igualdade aceitam quaisquer dois objetos, não apenas um escalar ou uma coleção.
Mas não há garantia de que o resultado da comparação seja significativo para o usuário final.
O exemplo a seguir demonstra o problema.

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

Neste exemplo, criamos dois objetos com propriedades idênticas. No entanto, o resultado do teste de igualdade é **false** porque eles são objetos diferentes. Para criar classes comparáveis, você precisa implementar [System. IEquatable \<T> ][2] em sua classe. O exemplo a seguir demonstra a implementação parcial de uma classe **Myfileinfoset** que implementa [System. \<T> IEquatable][2] e tem duas propriedades, **File** e **size**. O `Equals()` método retornará true se as propriedades de arquivo e tamanho de dois objetos **myfileinfoset** forem iguais.

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

Um exemplo proeminente de comparação de objetos arbitrários é descobrir se eles são nulos. Mas se você precisar determinar se uma variável é `$null` , deverá colocar `$null` no lado esquerdo do operador de igualdade. Colocá-lo no lado direito não faz o que você espera.

Por exemplo, deixe que `$a` seja uma matriz que contém elementos nulos:

```powershell
$a = 1, 2, $null, 4, $null, 6
```

Os testes a seguir `$a` não são nulos.

```powershell
$null -ne $a
```

```output
False
```

No entanto, a seguir, os Filers saem de todos os elementos nulos de `$a` :

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a>-gt,-GE,-lt e-Le

`-gt`, `-ge` , `-lt` e `-le` se comportar de forma muito semelhante. Quando ambos os lados são escalares, eles retornam **true** ou **false** , dependendo de como os dois lados se comparam:

| Operador | Retorna verdadeiro quando...                   |
| -------- | -------------------------------------- |
| -gt      | O lado esquerdo é maior          |
| -ge      | O lado esquerdo é maior ou igual a |
| -lt      | O lado esquerdo é menor          |
| -le      | O lado esquerdo é menor ou igual a |

Nos exemplos a seguir, todas as instruções retornam true.

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> Na maioria das linguagens de programação, o operador maior que é `>` . No PowerShell, esse caractere é usado para redirecionamento. Para obter detalhes, consulte [about_Redirection][3].

Quando o lado esquerdo é uma coleção, esses operadores comparam cada membro da coleção com o lado direito. Dependendo de sua lógica, eles mantêm ou descartam o membro.

Exemplo:

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

Esses operadores funcionam com qualquer classe que implemente [System. IComparable][1].

Exemplos:

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

O exemplo a seguir demonstra que não há nenhum símbolo em um teclado American QWERTY que é classificado após ' a '. Ele alimenta um conjunto contendo todos esses símbolos para o `-gt` operador para compará-los com ' a '. A saída é uma matriz vazia.

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

Se os dois lados dos operadores não forem razoavelmente comparáveis, esses operadores gerarão um erro de não finalização.

## <a name="matching-operators"></a>Operadores correspondentes

Os operadores de correspondência ( `-like` , `-notlike` , e `-match` `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado. O padrão para `-like` e `-notlike` é uma expressão curinga (contendo `*` , `?` e `[ ]` ), enquanto `-match` e `-notmatch` aceita uma expressão regular (Regex).

A sintaxe do é:

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

Quando a entrada desses operadores é um valor escalar, eles retornam um valor **booliano** . Quando a entrada é uma coleção de valores, os operadores retornam quaisquer membros correspondentes. Se não houver nenhuma correspondência em uma coleção, os operadores retornarão uma matriz vazia.

### <a name="-like-and--notlike"></a>-like e-não gosto

`-like` e `-notlike` se comportar de forma semelhante `-eq` e `-ne` , mas o lado direito pode ser uma cadeia de caracteres que contém [curingas](about_Wildcards.md).

Exemplo:

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a>-Match e-cormatch

`-match` e `-notmatch` use expressões regulares para pesquisar por padrão nos valores do lado esquerdo. As expressões regulares podem corresponder a padrões complexos, como endereços de email, caminhos UNC ou números de telefone formatados. A cadeia de caracteres do lado direito deve aderir às regras de [expressões regulares](about_Regular_Expressions.md) .

Exemplos escalares:

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

Se a entrada for uma coleção, os operadores retornarão os membros correspondentes dessa coleção.

Exemplos de coleção:

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

`-match` e `-notmatch` dão suporte a grupos de captura Regex. Cada vez que eles são executados, eles substituem a `$Matches` variável automática. Quando `<input>` é uma coleção, a `$Matches` variável é `$null` . `$Matches` é uma **tabela de hash** que sempre tem uma chave chamada ' 0 ', que armazena toda a correspondência. Se a expressão regular contiver grupos de captura, o `$Matches` conterá chaves adicionais para cada grupo.

Exemplo:

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

Para obter detalhes, consulte [about_Regular_Expressions](about_Regular_Expressions.md).

## <a name="replacement-operator"></a>Operador de substituição

### <a name="replacement-with-regular-expressions"></a>Substituição com expressões regulares

Como `-match` , o `-replace` operador usa expressões regulares para localizar o padrão especificado. Mas, ao contrário `-match` , ele substitui as correspondências por outro valor especificado.

Sintaxe:

```
<input> -replace <regular-expression>, <substitute>
```

O operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares. Você pode usar o operador para muitas tarefas administrativas, como renomear arquivos. Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os `.txt` arquivos para `.log` :

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas. Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` . Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .

Exemplos:

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a>Substituições de expressões regulares

Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições. Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres usando o caractere de cifrão ( `$` ) antes do identificador de grupo.

No exemplo a seguir, o `-replace` operador aceita um nome de usuário na forma `DomainName\Username` e converte para o `Username@DomainName` formato:

```powershell
$SearchExp = '^(?<Username>[\w-.]+)\\(?<DomainName>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> O `$` caractere tem funções syntatic no PowerShell e em expressões regulares:
>
> - No PowerShell, entre aspas duplas, ele designa variáveis e atua como um operador de subexpressão.
> - Em cadeias de caracteres de pesquisa Regex, ele denota o fim da linha
> - Em cadeias de caracteres de substituição de Regex, ela denota grupos capturados como tal, certifique-se de colocar suas expressões regulares entre aspas simples ou inserir um caractere de acento grave ( `` ` `` ) antes delas.

Por exemplo:

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

`$$` em Regex, denota um literal `$` . Isso `$$` na cadeia de caracteres de substituição para incluir um literal `$` na substituição resultante. Por exemplo:

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

Para saber mais, confira [about_Regular_Expressions](about_Regular_Expressions.md) e [substituições em expressões regulares][4].

### <a name="substituting-in-a-collection"></a>Substituindo em uma coleção

Quando o `<input>` para o `-replace` operador é uma coleção, o PowerShell aplica a substituição a todos os valores na coleção. Por exemplo:

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="containment-operators"></a>Operadores de confinamento

Os operadores de confinamento ( `-contains` , `-notcontains` , e `-in` `-notin` ) são semelhantes aos operadores de igualdade, exceto que sempre retornam um valor **booliano** , mesmo quando a entrada é uma coleção. Esses operadores param de comparar assim que detectam a primeira correspondência, enquanto os operadores de igualdade avaliam todos os membros de entrada. Em uma coleção muito grande, esses operadores retornam mais rápido do que os operadores de igualdade.

Sintaxe:

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a>-Contains e-iscontains

Esses operadores informam se um conjunto inclui um determinado elemento. `-contains` Retorna true quando o lado direito (objeto de teste) corresponde a um dos elementos no conjunto. `-notcontains` Retorna false em vez disso. Quando o objeto de teste é uma coleção, esses operadores usam igualdade de referência, ou seja, eles verificam se um dos elementos do conjunto é a mesma instância do objeto de teste.

Exemplos:

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

Exemplos mais complexos:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a>-in e-notin

Os `-in` operadores e `notin` foram introduzidos no PowerShell 3 como a inversa sintática dos `contains` `-notcontain` operadores e. `-in` retorna **true** quando o lado esquerdo corresponde a `<test-object>` um dos elementos no conjunto. `-notin` retorna **false** em vez disso. Quando o objeto de teste é um conjunto, esses operadores usam a igualdade de referência para verificar se um dos elementos do conjunto é a mesma instância do objeto de teste.

Os exemplos a seguir fazem a mesma coisa que os exemplos para `-contain` e `-notcontain` fazem, mas são escritos com `-in` e `-notin` em vez disso.

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

Exemplos mais complexos:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a>Comparação de tipos

Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.

Sintaxe:

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

Exemplo:

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
