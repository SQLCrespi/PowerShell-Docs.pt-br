---
description: Descreve uma instrução que você pode usar para fechar imediatamente as `foreach` instruções,, `for` ,, `while` `do` `switch` ou `trap` .
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: cd83a9487deaca0cdff1fe1af569cf4b22a36eaa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196373"
---
# <a name="about-break"></a>Sobre interrupção

## <a name="short-description"></a>Descrição breve

Descreve uma instrução que você pode usar para fechar imediatamente as `foreach` instruções,, `for` ,, `while` `do` `switch` ou `trap` .

## <a name="long-description"></a>Descrição longa

A `break` instrução fornece uma maneira de sair do bloco de controle atual.
A execução continua na próxima instrução após o bloco de controle. A instrução dá suporte a rótulos. Um rótulo é um nome que você atribui a uma instrução em um script.

## <a name="using-break-in-loops"></a>Usando quebras em loops

Quando uma `break` instrução é exibida em um loop, como um `foreach` loop,, `for` `do` ou `while` , o PowerShell sai imediatamente do loop.

Uma `break` instrução pode incluir um rótulo que permite que você saia de loops inseridos. Um rótulo pode especificar qualquer palavra-chave loop, como `foreach` , `for` ou, `while` em um script.

O exemplo a seguir mostra como usar uma `break` instrução para sair de uma `for` instrução:

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

Neste exemplo, a `break` instrução sai do `for` loop quando a `$i` variável é igual a 1. Embora a `for` instrução seja avaliada como **true** até que `$i` seja maior que 10, o PowerShell atinge a instrução break na primeira vez em que o `for` loop é executado.

É mais comum usar a `break` instrução em um loop em que uma condição interna deve ser atendida. Considere o seguinte `foreach` exemplo de instrução:

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

Neste exemplo, a `foreach` instrução itera a `$varB` matriz. A `if` instrução é avaliada como falsa as duas primeiras vezes em que o loop é executado e a variável `$i` é incrementada em 1. A terceira vez em que o loop é executado, `$i` é igual a 2 e a `$val` variável é igual a 30. Neste ponto, a `break` instrução é executada e o `foreach` loop é encerrado.

### <a name="using-a-labeled-break-in-a-loop"></a>Usando uma quebra rotulada em um loop

Uma `break` instrução pode incluir um rótulo. Se você usar a `break` palavra-chave com um rótulo, o PowerShell sairá do loop rotulado em vez de sair do loop atual.
O rótulo é um ponto-e-vírgula seguido de um nome que você atribui. O rótulo deve ser o primeiro token em uma instrução e deve ser seguido pela palavra-chave de loop, como `while` .

`break` move a execução para fora do loop rotulado. Em loops inseridos, isso tem um resultado diferente do que a `break` palavra-chave tem quando ela é usada por si mesma. Este exemplo tem uma `while` instrução com uma `for` instrução:

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

Se a condição 2 for avaliada como **true** , a execução do script será ignorada até a instrução após o loop rotulado. No exemplo, a execução começa novamente com a instrução `$a = $c` .

Você pode aninhar muitos loops rotulados, conforme mostrado no exemplo a seguir.

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

Se a `$b` variável for avaliada como true, a execução do script será retomada após o loop rotulado "Red". Se a `$c` variável for avaliada como true, a execução do controle de script será retomada após o loop rotulado "amarelo".

Se a `$a` variável for avaliada como true, a execução será retomada após o loop mais interno. Nenhum rótulo é necessário.

O PowerShell não limita a distância com que os rótulos podem retomar a execução. O rótulo pode até passar o controle entre os limites de chamada de script e de função.

## <a name="using-break-in-a-switch-statement"></a>Usando break em uma instrução switch

Em um `switch` constructo, `break` faz com que o PowerShell saia do `switch` bloco de código.

A `break` palavra-chave é usada para sair da `switch` construção. Por exemplo, a instrução a seguir `switch` usa `break` instruções para testar a condição mais específica:

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

Neste exemplo, a `$var` variável é criada e inicializada com um valor de cadeia de caracteres de `word2` . A `switch` instrução usa a classe **Regex** para corresponder o valor da variável primeiro com o termo `word2` . Como o valor da variável e o primeiro teste na `switch` instrução correspondem, o primeiro bloco de código na `switch` instrução é executado.

Quando o PowerShell atinge a primeira `break` instrução, a `switch` instrução é encerrada. Se as quatro `break` instruções forem removidas do exemplo, todas as quatro condições serão atendidas. Este exemplo usa a `break` instrução para exibir resultados quando a condição mais específica é atendida.

## <a name="using-break-in-a-trap-statement"></a>Usando break em uma instrução Trap

Se a instrução final executada no corpo de uma `trap` instrução for `break` , o objeto de erro será suprimido e a exceção será lançada novamente.

O exemplo a seguir cria uma exceção **DivideByZeroException** que é interceptada usando a `trap` instrução.

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Observe que a execução é interrompida na exceção. O `After loop` nunca é atingido.
A exceção é gerada novamente após a `trap` execução.

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a>Não usar quebra fora de um loop, comutador ou interceptação

Quando `break` é usado fora de um Construct que dá suporte diretamente a ele (loops, `switch` , `trap` ), _o PowerShell pesquisa a pilha de chamadas_ para uma construção delimitadora. Se não for possível localizar uma construção delimitadora, o runspace atual será encerrado silenciosamente.

Isso significa que as funções e os scripts que usam inadvertidamente `break` fora de uma construção delimitadora que dá suporte a ela podem encerrar inadvertidamente seus _chamadores_ .

Usar `break` dentro de um pipeline `break` , como um `ForEach-Object` bloco de script, não apenas sai do pipeline, ele potencialmente encerra todo o runspace.

## <a name="see-also"></a>Confira também

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Continue](about_Continue.md)

[about_For](about_For.md)

[about_Foreach](about_Foreach.md)

[about_Switch](about_Switch.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)

[about_While](about_While.md)
