---
description: Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: ed57cec30577fbd02f7aa317460bf1a73b006685
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195469"
---
# <a name="about-split"></a>Sobre divisão

## <a name="short-description"></a>DESCRIÇÃO BREVE
Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O operador Split divide uma ou mais cadeias de caracteres em subcadeias. Você pode alterar os seguintes elementos da operação Split:

- Delimitador. O padrão é espaço em branco, mas você pode especificar caracteres, cadeias, padrões ou blocos de script que especificam o delimitador. O operador split no PowerShell usa uma expressão regular no delimitador, em vez de um caractere simples.
- Número máximo de subcadeias de caracteres. O padrão é retornar todas as subcadeias de caracteres. Se você especificar um número menor que o número de subcadeias de caracteres, as subcadeias restantes serão concatenadas na última subcadeia de caracteres.
- Opções que especificam as condições sob as quais o delimitador é correspondido, como SimpleMatch e Multiline.

## <a name="syntax"></a>SYNTAX

O diagrama a seguir mostra a sintaxe do operador-split.

Os nomes de parâmetro não aparecem no comando. Inclua apenas os valores de parâmetro. Os valores devem aparecer na ordem especificada no diagrama de sintaxe.

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

Você pode substituir `-iSplit` ou `-cSplit` `-split` em qualquer instrução Split binária (uma instrução Split que inclui um delimitador ou bloco de script). Os `-iSplit` operadores e não diferenciam `-split` maiúsculas de minúsculas. O `-cSplit` operador diferencia maiúsculas de minúsculas, o que significa que o caso é considerado quando as regras de delimitador são aplicadas.

## <a name="parameters"></a>PARAMETERS

### <a name="string-or-string"></a>\<String\> ou \<String[]\>

Especifica uma ou mais cadeias de caracteres a serem divididas. Se você enviar várias cadeias de caracteres, todas as cadeias de caracteres serão divididas usando as mesmas regras de delimitador.

Exemplo:

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

Os caracteres que identificam o final de uma subcadeia de caracteres. O delimitador padrão é espaço em branco, incluindo espaços e caracteres não imprimíveis, como nova linha ( \` n) e tabulação ( \` t). Quando as cadeias de caracteres são divididas, o delimitador é omitido de todas as subcadeias de caracteres. Exemplo:

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

Por padrão, o delimitador é omitido dos resultados. Para preservar todo ou parte do delimitador, coloque entre parênteses a parte que você deseja preservar.
Se o \<Max-substrings\> parâmetro for adicionado, isso terá precedência quando o comando dividir a coleção. Se você optar por incluir um delimitador como parte da saída, o comando retornará o delimitador como parte da saída; no entanto, dividir a cadeia de caracteres para retornar o delimitador como parte da saída não conta como uma divisão.

Exemplos:

```
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

No exemplo a seguir, \<Max-substrings\> é definido como 3. Isso resulta em três divisões dos valores de cadeia de caracteres, mas um total de cinco cadeias na saída resultante; o delimitador é incluído após as divisões, até que o máximo de três subcadeias de caracteres seja atingido. Delimitadores adicionais na Subcadeia de caracteres final tornam-se parte da subcadeia de caracteres.

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

Especifica o número máximo de vezes que uma cadeia de caracteres é dividida. O padrão é todas as subcadeias de caracteres divididas pelo delimitador. Se houver mais subcadeias de caracteres, elas serão concatenadas à subcadeia de caracteres final. Se houver menos subcadeias de caracteres, todas as subcadeias de caracteres serão retornadas. Um valor de 0 retorna todas as subcadeias de caracteres. Valores negativos retornam a quantidade de subcadeias de caracteres solicitadas a partir do final da cadeia de caracteres de entrada.

> [!NOTE]
> O suporte para valores negativos foi adicionado no PowerShell 7.

**Max-subcadeias de caracteres** não especifica o número máximo de objetos retornados. Seu valor é igual ao número máximo de vezes que uma cadeia de caracteres é dividida.
Se você enviar mais de uma cadeia de caracteres (uma matriz de cadeias de caracteres) para o `-split` operador, o limite máx. de **subcadeias de caracteres** será aplicado a cada cadeia de caracteres separadamente.

Exemplo:

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

Uma expressão que especifica regras para aplicar o delimitador. A expressão deve ser avaliada como $true ou $false. Coloque o bloco de script entre chaves.

Exemplo:

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

Coloque o nome da opção entre aspas. As opções são válidas somente quando o \<Max-substrings\> parâmetro é usado na instrução.

A sintaxe para o parâmetro options é:

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

As opções de SimpleMatch são:

- **SimpleMatch** : Use a comparação de cadeia de caracteres simples ao avaliar o delimitador. Não pode ser usado com RegexMatch.
- **IgnoreCase** : força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.

As opções de RegexMatch são:

- **RegexMatch** : Use a correspondência de expressão regular para avaliar o delimitador. Esse é o comportamento padrão. Não pode ser usado com SimpleMatch.
- **IgnoreCase** : força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.
- **CultureInvariant** : ignora diferenças culturais em linguagem quando evaluting o delimitador. Válido somente com RegexMatch.
- **IgnorePatternWhitespace** : ignora o espaço em branco e os comentários sem escape marcados com o sinal numérico (#). Válido somente com RegexMatch.
- **Multiline** : o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.
- **Unificação** : o modo de única trata a cadeia de caracteres de entrada como uma *única* .
  Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .
- **ExplicitCapture** : ignora grupos de correspondências não nomeados para que apenas grupos de captura explícitos sejam retornados na lista de resultados. Válido somente com RegexMatch.

## <a name="unary-and-binary-split-operators"></a>OPERADORES unários e de divisão binária

O operador de divisão unário ( `-split <string>` ) tem precedência mais alta do que uma vírgula. Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador de divisão unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será dividida.

Use um dos seguintes padrões para dividir mais de uma cadeia de caracteres:

- Usar o operador de divisão binária ( \<string[]\> -Split \<delimiter\> )
- Coloque todas as cadeias de caracteres entre parênteses
- Armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para o operador de divisão

Considere o seguinte exemplo:

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a>EXEMPLOS

A instrução a seguir divide a cadeia de caracteres em espaço em branco.

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

A instrução a seguir divide a cadeia de caracteres em qualquer vírgula.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

A instrução a seguir divide a cadeia de caracteres no padrão "er".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

A instrução a seguir executa uma divisão com diferenciação de maiúsculas e minúsculas na letra "N".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

A instrução a seguir divide a cadeia de caracteres em "e" e "t".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

A instrução a seguir divide a cadeia de caracteres em "e" e "r", mas limita as subcadeias de caracteres resultantes a seis subcadeias de caracteres.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

A instrução a seguir divide uma cadeia de caracteres em três subcadeias.

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

A instrução a seguir divide uma cadeia de caracteres em três subcadeias de caracteres começando do final da cadeia de caracteres.

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

A instrução a seguir divide duas cadeias de caracteres em três subcadeias.
(O limite é aplicado a cada cadeia de caracteres de forma independente.)

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

A instrução a seguir divide cada linha na cadeia de caracteres here no primeiro dígito. Ele usa a opção MultiLine para reconhecer o início de cada linha e cadeia de caracteres.

O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings. Você pode usar opções, como MultiLine, somente quando o valor Max-substrings for especificado.

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

A instrução a seguir usa o caractere de barra invertida para escapar do delimitador de ponto (.).

Com o padrão, RegexMatch, o ponto entre aspas (".") é interpretado para corresponder a qualquer caractere, exceto para um caractere de nova linha. Como resultado, a instrução Split retorna uma linha em branco para cada caractere, exceto nova linha.

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

A instrução a seguir usa a opção SimpleMatch para direcionar o operador-split para interpretar o delimitador de ponto (.) literalmente.

O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings. Você pode usar opções, como SimpleMatch, somente quando o valor Max-substrings for especificado.

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

A instrução a seguir divide a cadeia de caracteres em um dos dois delimitadores, dependendo do valor de uma variável.

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Join](about_Join.md)
