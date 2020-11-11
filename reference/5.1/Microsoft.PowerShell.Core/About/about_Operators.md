---
description: Descreve os operadores com suporte do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: b783d2cb76fe8a0a66ec77b67ef915f3b78def04
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94482985"
---
# <a name="about-operators"></a>Sobre operadores

## <a name="short-description"></a>Descrição breve
Descreve os operadores com suporte do PowerShell.

## <a name="long-description"></a>Descrição longa

Um operador é um elemento de linguagem que você pode usar em um comando ou expressão.
O PowerShell dá suporte a vários tipos de operadores para ajudá-lo a manipular valores.

### <a name="arithmetic-operators"></a>Operadores aritméticos

Use operadores aritméticos (,,, `+` `-` `*` `/` , `%` ) para calcular valores em um comando ou expressão. Com esses operadores, você pode adicionar, subtrair, multiplicar ou dividir valores e calcular o resto (módulo) de uma operação de divisão.

O operador de adição concatena os elementos. O operador de multiplicação retorna o número especificado de cópias de cada elemento. Você pode usar operadores aritméticos em qualquer tipo .NET que os implemente, como: `Int` ,, `String` `DateTime` , `Hashtable` e matrizes.

Os operadores bit `-band` a bit (, `-bor` , `-bxor` ,, `-bnot` `-shl` , `-shr` ) manipulam os padrões de bits em valores.

Para obter mais informações, consulte [about_Arithmetic_Operators](about_Arithmetic_Operators.md).

### <a name="assignment-operators"></a>Operadores de atribuição

Use operadores de atribuição ( `=` ,, `+=` ,, `-=` `*=` `/=` , `%=` ) para atribuir, alterar ou acrescentar valores a variáveis. Você pode combinar operadores aritméticos com atribuição para atribuir o resultado da operação aritmética a uma variável.

Para obter mais informações, consulte [about_assignment_operators](about_Assignment_Operators.md).

### <a name="comparison-operators"></a>Operadores de comparação

Use operadores de comparação ( `-eq` ,, `-ne` ,, `-gt` `-lt` `-le` , `-ge` ) para comparar valores e condições de teste. Por exemplo, você pode comparar dois valores de cadeia de caracteres para determinar se eles são iguais.

Os operadores de comparação também incluem operadores que localizam ou substituem padrões no texto. Os `-match` operadores (, `-notmatch` , `-replace` ) usam expressões regulares e ( `-like` , `-notlike` ) usam Curingas `*` .

Os operadores de comparação de confinamento determinam se um valor de teste aparece em um conjunto de referência (,,, `-in` `-notin` `-contains` `-notcontains` ).

Operadores de comparação de tipo ( `-is` , `-isnot` ) determinam se um objeto é de um tipo específico.

Para obter mais informações, consulte [about_Comparison_Operators](about_Comparison_Operators.md).

### <a name="logical-operators"></a>Operadores lógicos

Use operadores lógicos (,,, `-and` `-or` `-xor` `-not` , `!` ) para conectar instruções condicionais em um único condicional complexo. Por exemplo, você pode usar um `-and` operador lógico para criar um filtro de objeto com duas condições diferentes.

Para obter mais informações, consulte [about_Logical_Operators](about_logical_operators.md).

### <a name="redirection-operators"></a>Operadores de redirecionamento

Use operadores de redirecionamento ( `>` ,, `>>` `2>` , `2>>` e `2>&1` ) para enviar a saída de um comando ou expressão para um arquivo de texto. Os operadores de redirecionamento funcionam como o `Out-File` cmdlet (sem parâmetros), mas também permitem redirecionar a saída de erro para os arquivos especificados. Você também pode usar o `Tee-Object` cmdlet para redirecionar a saída.

Para obter mais informações, consulte [about_Redirection](about_Redirection.md)

### <a name="split-and-join-operators"></a>Operadores de divisão e junção

Os `-split` `-join` operadores e dividem e combinam subcadeias de caracteres. O `-split` operador divide uma cadeia de caracteres em subcadeias de caracteres. O `-join` operador concatena várias cadeias de caracteres em uma única cadeia.

Para obter mais informações, consulte [about_Split](about_Split.md) e [about_join](about_Join.md).

### <a name="type-operators"></a>Operadores de tipo

Use os operadores de tipo ( `-is` , `-isnot` , `-as` ) para localizar ou alterar o tipo de .NET Framework de um objeto.

Para obter mais informações, consulte [about_Type_Operators](about_Type_Operators.md).

### <a name="unary-operators"></a>Operadores unários

Use operadores unários para incrementar ou decrementar variáveis ou propriedades de objeto e para definir inteiros como números positivos ou negativos. Por exemplo, para incrementar a variável `$a` de `9` para `10` , digite `$a++` .

### <a name="special-operators"></a>Operadores especiais

Operadores especiais têm casos de uso específicos que não se ajustam a nenhum outro grupo de operadores. Por exemplo, operadores especiais permitem que você execute comandos, altere o tipo de dados de um valor ou recupere elementos de uma matriz.

#### <a name="grouping-operator--"></a>Operador de agrupamento `( )`

Como em outras linguagens, `(...)` serve para substituir a precedência de operador em expressões. Por exemplo: `(1 + 2) / 3`

No entanto, no PowerShell, há comportamentos adicionais.

- `(...)` permite que você permita que a saída de um _comando_ participe de uma expressão. Por exemplo:

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- Quando usado como o primeiro segmento de um pipeline, o encapsulamento de um comando ou uma expressão em parênteses invariavelmente causa a _Enumeração_ do resultado da expressão. Se os parênteses encapsularem um _comando_ , ele será executado para conclusão com todas as saídas _coletadas na memória_ antes que os resultados sejam enviados por meio do pipeline.

> [!NOTE]
> O encapsulamento de um comando entre parênteses faz com que a variável automática `$?` seja definida como `$true` , mesmo quando o próprio comando incluído é definido `$?` como `$false` .
> Por exemplo, o `(Get-Item /Nosuch); $?` resultado é **verdadeiro** inesperadamente. Para obter mais informações sobre o `$?` , consulte [about_Automatic_Variables](about_Automatic_Variables.md).

#### <a name="subexpression-operator--"></a>Operador de subexpressão `$( )`

Retorna o resultado de uma ou mais instruções. Para um único resultado, retorna um escalar. Para vários resultados, retorna uma matriz. Use isso quando desejar usar uma expressão dentro de outra expressão. Por exemplo, para inserir os resultados do comando em uma expressão de cadeia de caracteres.

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a>Operador de subexpressão de matriz `@( )`

Retorna o resultado de uma ou mais instruções como uma matriz. Se houver apenas um item, a matriz terá apenas um membro.

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a>Sintaxe literal da tabela de hash `@{}`

Semelhante à subexpressão de matriz, essa sintaxe é usada para declarar uma tabela de hash.
Para obter mais informações, consulte [about_Hash_Tables](about_Hash_Tables.md).

#### <a name="call-operator-"></a>Operador de chamada `&`

Executa um comando, script ou bloco de script. O operador Call, também conhecido como "operador de invocação", permite executar comandos que são armazenados em variáveis e representados por cadeias de caracteres ou blocos de script. O operador de chamada é executado em um escopo filho. Para obter mais informações sobre escopos, consulte [about_Scopes](about_Scopes.md).

Este exemplo armazena um comando em uma cadeia de caracteres e executa-o usando o operador Call.

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

O operador de chamada não analisa cadeias de caracteres. Isso significa que você não pode usar parâmetros de comando em uma cadeia de caracteres ao usar o operador de chamada.

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
At line:1 char:2
+ & $c
+  ~~
    + CategoryInfo          : ObjectNotFound: (Get-Service -Name Spooler:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

O cmdlet [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) pode executar código que causa erros de análise ao usar o operador Call.

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

Você pode usar o operador de chamada para executar scripts usando seus nomes de File. O exemplo a seguir mostra um nome de arquivo de script que contém espaços. Quando você tenta executar o script, o PowerShell exibe o conteúdo da cadeia de caracteres entre aspas que contém o nome do arquivo. O operador Call permite que você execute o conteúdo da cadeia de caracteres que contém o nome do arquivo.

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

Para obter mais informações sobre blocos de script, consulte [about_Script_Blocks](about_Script_Blocks.md).

#### <a name="cast-operator--"></a>Operador cast `[ ]`

Converte ou limita objetos no tipo especificado. Se os objetos não puderem ser convertidos, o PowerShell gerará um erro.

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

Uma conversão também pode ser executada quando uma variável é atribuída ao uso de [notação de conversão](about_Variables.md).

#### <a name="comma-operator-"></a>Operador de vírgula `,`

Como um operador binário, a vírgula cria uma matriz ou acrescenta à matriz que está sendo criada. No modo de expressão, como um operador unário, a vírgula cria uma matriz com apenas um membro. Coloque a vírgula antes do membro.

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

Como `Write-Object` o espera um argumento, você deve colocar a expressão entre parênteses.

#### <a name="dot-sourcing-operator-"></a>Operador de fornecimento de ponto `.`

Executa um script no escopo atual para que quaisquer funções, aliases e variáveis que o script cria sejam adicionados ao escopo atual, substituindo os existentes. Os parâmetros declarados pelo script se tornam variáveis. Parâmetros para os quais nenhum valor foi fornecido se tornam variáveis sem valor. No entanto, a variável automática `$args` é preservada.

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> O operador ponto de fornecimento é seguido por um espaço. Use o espaço para distinguir o ponto do símbolo de ponto ( `.` ) que representa o diretório atual.
>
> No exemplo a seguir, o script Sample.ps1 no diretório atual é executado no escopo atual.
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a>Operador de formato `-f`

Formata cadeias de caracteres usando o método Format de objetos String. Insira a cadeia de caracteres de formato no lado esquerdo do operador e os objetos a serem formatados no lado direito do operador.

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

Se você precisar manter as chaves ( `{}` ) na cadeia de caracteres formatada, poderá escapar delas dobrando as chaves.

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

Para obter mais informações, consulte o método [String. Format](/dotnet/api/system.string.format) e a [formatação composta](/dotnet/standard/base-types/composite-formatting).

#### <a name="index-operator--"></a>Operador de índice `[ ]`

Seleciona objetos de coleções indexadas, como matrizes e tabelas de hash. Os índices de matriz são baseados em zero, portanto, o primeiro objeto é indexado como `[0]` . Para matrizes (somente), você também pode usar índices negativos para obter os últimos valores. As tabelas de hash são indexadas por valor de chave.

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a>Operador de pipeline `|`

Envia ("pipes") a saída do comando que o precede para o comando que o segue. Quando a saída inclui mais de um objeto (uma "coleção"), o operador de pipeline envia os objetos um de cada vez.

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a>Operador de intervalo `..`

Representa os inteiros sequenciais em uma matriz de inteiros, de acordo com um limite superior e inferior.

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

Você também pode criar intervalos na ordem inversa.

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

#### <a name="member-access-operator-"></a>Operador de acesso de membro `.`

Acessa as propriedades e os métodos de um objeto. O nome do membro pode ser uma expressão.

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a>Operador de membro estático `::`

Chama as propriedades e os métodos estáticos de uma classe .NET Framework. Para localizar as propriedades e os métodos estáticos de um objeto, use o parâmetro static do `Get-Member` cmdlet.  O nome do membro pode ser uma expressão.

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a>Confira também

[about_Arithmetic_Operators](about_Arithmetic_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Logical_Operators](about_logical_operators.md)

[about_Operator_Precedence](about_operator_precedence.md)

[about_Type_Operators](about_Type_Operators.md)

[about_Split](about_Split.md)

[about_Join](about_Join.md)

[about_Redirection](about_Redirection.md)
