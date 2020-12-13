---
title: Tudo o que você queria saber sobre a substituição de variáveis em cadeias de caracteres
description: Há diversas maneiras de usar variáveis em cadeias de caracteres para criar textos formatados.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "86301311"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a>Tudo o que você queria saber sobre a substituição de variáveis em cadeias de caracteres

Há diversas maneiras de usar variáveis em cadeias de caracteres. Estou chamando isso de substituição de variáveis, mas me refiro a qualquer ocasião em que você queira formatar uma cadeia de caracteres para incluir valores de variáveis. Isso é algo que explico com frequência para novos criadores de scripts.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="concatenation"></a>Concatenação

A primeira classe de métodos pode ser chamada de concatenação. Basicamente, ela reúne várias cadeias de caracteres. Há um longo histórico de uso da concatenação para criar cadeias de caracteres formatadas.

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

A concatenação funciona bem quando há apenas alguns valores a serem adicionados. Porém, isso logo pode ficar complicado.

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

Este exemplo simples já está ficando mais difícil de ler.

## <a name="variable-substitution"></a>Substituição de variáveis

O PowerShell tem uma opção mais fácil. Você pode especificar variáveis diretamente nas cadeias de caracteres.

```powershell
$message = "Hello, $first $last."
```

O tipo de aspas usado em volta da cadeia de caracteres faz diferença. Uma cadeia de caracteres entre aspas duplas permite a substituição, mas uma cadeia de caracteres entre aspas simples não. Há ocasiões em que você deseja uma ou outra para ter uma opção.

## <a name="command-substitution"></a>Substituição de comando

Tudo fica um pouco complicado quando você tenta colocar os valores de propriedades em uma cadeia de caracteres. É aí que muitos novatos se confundem. Primeiro, deixe-me mostrar o que eles acham que deve funcionar (e, à primeira vista, quase parece que deveria funcionar).

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

Você esperaria obter `CreationTime` de `$directory`, mas obtém o valor `Time: c:\windows.CreationTime`. O motivo é que esse tipo de substituição vê apenas a variável base. Ele considera o ponto como parte da cadeia de caracteres. Por isso, para de resolver o valor mais profundamente.

Assim, esse objeto fornece uma cadeia de caracteres como um valor padrão quando colocado em uma cadeia de caracteres.
Alguns objetos fornecem o nome do tipo, como `System.Collections.Hashtable`. Apenas algo a ser observado.

O PowerShell permite que você faça a execução do comando dentro da cadeia de caracteres com uma sintaxe especial. Isso nos permite obter as propriedades desses objetos e executar qualquer outro comando para obter um valor.

```powershell
$message = "Time: $($directory.CreationTime)"
```

Isso funciona muito bem para algumas situações, mas poderá ficar tão estranho quanto a concatenação se você tiver apenas algumas variáveis.

### <a name="command-execution"></a>Execução do comando

Você pode executar comandos dentro de uma cadeia de caracteres. Embora eu tenha essa opção, não gosto dela. Logo tudo fica confuso e difícil de depurar. Executo o comando e o salvo em uma variável ou uso uma cadeia de caracteres de formato.

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a>Cadeia de formato

O .NET tem um modo de formatar cadeias de caracteres com o qual acho muito fácil trabalhar. Mostrarei o método estático para isso, antes de mostrar o atalho do PowerShell para a mesma ação.

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

Aqui, a cadeia de caracteres é analisada para os tokens `{0}` e `{1}`. Em seguida, ela usa esse número para escolher entre os valores fornecidos. Se você quiser repetir um valor em algum lugar na cadeia de caracteres, poderá reutilizar esse número de valores.

Quanto mais complicada for a cadeia de caracteres, mais você aproveitará essa abordagem.

### <a name="format-values-as-arrays"></a>Formatar valores como matrizes

Se a linha de formato ficar muito longa, você poderá posicionar os valores em uma matriz primeiro.

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

Não é nivelamento, pois estou passando a matriz inteira, mas é semelhante.

## <a name="advanced-formatting"></a>Formatação avançada

Eu chamei estes intencionalmente como provenientes do .NET porque há muitas opções de formatação já [documentadas][]. Há maneiras internas de formatar vários tipos de dados.

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

Não falarei sobre elas, mas queria apenas informar de que se trata de um mecanismo de formatação muito eficiente, se necessário.

## <a name="joining-strings"></a>Junção de cadeias de caracteres

Às vezes, você quer concatenar uma lista de valores. Há um operador `-join` que pode fazer isso para você. Ele até mesmo permite que você especifique um caractere para unir as cadeias de caracteres.

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

Se você quiser usar `-join` para unir algumas cadeias de caracteres sem um separador, precisará especificar uma cadeia de caracteres vazia `''`.
Mas se isso for tudo de que você precisa, há uma opção mais rápida.

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

Também vale a pena destacar que é possível usar `-split` para dividir cadeias de caracteres.

## <a name="join-path"></a>Join-Path

Geralmente é ignorado, mas é um ótimo cmdlet para criar um caminho de arquivo.

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

A grande vantagem é que ele usa as barras invertidas corretamente ao reunir os valores. Isso é especialmente importante se você está usando valores de usuários ou de arquivos de configuração.

Além disso, funciona bem com `Split-Path` e `Test-Path`. Também abordei isso em minha postagem sobre [ler e salvar em arquivos][].

## <a name="strings-are-arrays"></a>Cadeia de caracteres são matrizes

Preciso falar sobre a adição de cadeias de caracteres antes de continuar. Lembre-se de que uma cadeia de caracteres é apenas uma matriz de caracteres. Quando você adiciona várias cadeias de caracteres juntas, uma nova matriz é criada a cada vez.

Veja este exemplo:

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

Ele parece muito básico, mas o que você não vê é que sempre que uma cadeia de caracteres é adicionada a `$message`, uma cadeia de caracteres totalmente nova é criada. A memória é alocada, os dados são copiados e a antiga é descartada.
Não é muito importante quando isso é feito apenas algumas vezes, mas um loop como esse evidencia o problema.

### <a name="stringbuilder"></a>StringBuilder

O StringBuilder também é muito popular para a criação de cadeias de caracteres grandes com base em várias cadeias de caracteres menores. O motivo disso é que ele apenas coleta todas as cadeias de caracteres adicionadas a ele e concatena todas elas no final quando você recupera o valor.

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

Novamente, isso é algo que estou buscando no .NET. Não uso mais com frequência, mas é bom saber que está lá.

## <a name="delineation-with-braces"></a>Delineação com chaves

A delineação com chaves é usada para concatenação de sufixo dentro da cadeia de caracteres. Às vezes, sua variável não tem um limite de palavra claro.

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

Agradeço a [/u/real_parbold][] por isso.

Aqui está uma alternativa para essa abordagem:

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

Pessoalmente, uso a cadeia de caracteres de formato para isso, mas é bom saber, caso você encontre isso na prática.

## <a name="find-and-replace-tokens"></a>Localização e substituição de tokens

Embora a maioria desses recursos limite a necessidade de distribuir sua própria solução, há ocasiões em que você pode ter arquivos de modelo grandes em que deseja substituir cadeias de caracteres.

Vamos supor que você tenha recebido um modelo de um arquivo com muito texto.

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

Pode ser necessário substituir muitos tokens. O truque é usar um token muito distinto que seja fácil de localizar e substituir. Costumo usar um caractere especial em ambas as extremidades para que seja mais fácil diferenciá-lo.

Recentemente, descobri uma nova abordagem. Decidi deixar esta seção aqui porque esse é um padrão comumente usado.

### <a name="replace-multiple-tokens"></a>Substituir vários tokens

Quando tenho uma lista de tokens que preciso substituir, uso uma abordagem mais genérica. Coloco-os em uma tabela de hash e realizo uma iteração para fazer a substituição.

```powershell
$tokenList = @{
    Full_Name = 'Kevin Marquette'
    Location = 'Orange County'
    State = 'CA'
}

$letter = Get-Content -Path TemplateLetter.txt -RAW
foreach( $token in $tokenList.GetEnumerator() )
{
    $pattern = '#{0}#' -f $token.key
    $letter = $letter -replace $pattern, $token.Value
}
```

Esses tokens podem ser carregados de arquivos JSON ou CSV se necessário.

### <a name="executioncontext-expandstring"></a>ExecutionContext ExpandString

Há uma forma inteligente de definir uma cadeia de caracteres de substituição com aspas simples e expandir as variáveis posteriormente. Veja este exemplo:

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

A chamada para `.InvokeCommand.ExpandString` no contexto de execução atual usa as variáveis no escopo atual para substituição. O importante aqui é que `$message` pode ser definido muito cedo, antes que as variáveis existam.

Se entrarmos em mais detalhes, poderemos executar essa substituição várias vezes com valores diferentes.

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

Para continuar com essa mesma ideia, você pode importar um modelo de email grande de um arquivo de texto para fazer isso. Preciso agradecer a [Mark Kraus][] por essa [sugestão][].

## <a name="whatever-works-the-best-for-you"></a>O que for mais adequado para você

Sou um fã da abordagem de cadeia de caracteres de formato. Eu definitivamente faço isso com as cadeias de caracteres mais complicadas ou quando há muitas variáveis. Em algo muito curto, posso usar qualquer uma das abordagens.

## <a name="anything-else"></a>Algo mais?

Abordei muitos aspectos básicos neste artigo. Espero que você tenha aprendido algo novo.

<!-- link references -->
[versão original]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[sugestão]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[ler e salvar em arquivos]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[documentadas]: /dotnet/api/system.string.format#overloads
