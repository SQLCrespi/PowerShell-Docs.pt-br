---
description: Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 36c14dc0489345083e8938c066cefa77e3f5ef8d
ms.sourcegitcommit: 0c31814bed14ff715dc7d4aace07cbdc6df2438e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "99603554"
---
# <a name="about-continue"></a>Sobre o Continue

## <a name="short-description"></a>Descrição breve

Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.

## <a name="long-description"></a>Descrição longa

A `continue` instrução fornece uma maneira de sair do bloco de controle atual, mas continuar a execução, em vez de sair completamente. A instrução dá suporte a rótulos.
Um rótulo é um nome que você atribui a uma instrução em um script.

## <a name="using-continue-in-loops"></a>Usando continuar em loops

Uma instrução sem rótulo `continue` retorna imediatamente o fluxo do programa para a parte superior do loop mais interno que é controlado por `for` uma `foreach` instrução,, `do` ou `while` . A iteração atual do loop é encerrada e o loop continua com a próxima iteração.

No exemplo a seguir, o fluxo do programa retorna para a parte superior do `while` loop se a `$ctr` variável for igual a 5. Como resultado, todos os números entre 1 e 10 são exibidos, exceto 5:

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

Ao usar um `for` loop, a execução continua na `<Repeat>` instrução, seguida pelo `<Condition>` teste. No exemplo a seguir, um loop infinito não ocorrerá porque o decréscimo de `$i` ocorre após a `continue` palavra-chave.

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a>Usando uma continuação rotulada em um loop

Uma instrução rotulada `continue` encerra a execução da iteração e transfere o controle para o rótulo de iteração ou instrução de delimitação de destino `switch` .

No exemplo a seguir, o mais interno `for` é encerrado quando `$condition` é **verdadeiro** e a iteração continua com o segundo `for` loop em `labelB` .

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a>Usando continue em uma instrução switch

Uma instrução sem rótulo `continue` em um `switch` encerra a execução da `switch` iteração atual e transfere o controle para a parte superior do `switch` para obter o próximo item de entrada.

Quando há um único item de entrada, `continue` ele sai da `switch` instrução inteira.
Quando a `switch` entrada é uma coleção, o `switch` testa cada elemento da coleção. O `continue` sai da iteração atual e `switch` continua com o próximo elemento.

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a>Usando continuar em uma instrução de interceptação

Se a instrução final executada no corpo de uma `trap` instrução for `continue` , o erro interceptado será silenciosamente ignorado e a execução continuará com a instrução imediatamente após aquela que causou `trap` a ocorrência.

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a>Não usar continuar fora de um loop, comutador ou interceptação

Quando `continue` é usado fora de um Construct que dá suporte diretamente a ele (loops, `switch` , `trap` ), _o PowerShell pesquisa a pilha de chamadas_ para uma construção delimitadora. Se não for possível localizar uma construção delimitadora, o runspace atual será encerrado silenciosamente.

Isso significa que as funções e os scripts que usam inadvertidamente `continue` fora de uma construção delimitadora que dá suporte a ela podem encerrar inadvertidamente seus _chamadores_.

Usar `continue` dentro de um pipeline, como um `ForEach-Object` bloco de script, não apenas sai do pipeline, ele potencialmente encerra todo o runspace.

## <a name="see-also"></a>Consulte também

[about_Break](about_Break.md)

[about_For](about_For.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
