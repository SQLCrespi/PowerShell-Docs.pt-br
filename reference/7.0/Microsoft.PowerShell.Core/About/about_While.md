---
description: Descreve uma instrução de linguagem que você pode usar para executar um bloco de comando com base nos resultados de um teste condicional.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 4008c1c8738b6911949d79882cc6909be2edbe97
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195877"
---
# <a name="about-while"></a>Sobre while

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve uma instrução de linguagem que você pode usar para executar um bloco de comando com base nos resultados de um teste condicional.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A instrução while (também conhecida como um loop while) é uma construção de linguagem para a criação de um loop que executa comandos em um bloco de comando, desde que um teste condicional seja avaliado como true. A instrução while é mais fácil de construir do que uma instrução for, pois sua sintaxe é menos complicada. Além disso, é mais flexível do que a instrução foreach porque você especifica um teste condicional na instrução while para controlar quantas vezes o loop é executado.

O seguinte mostra a sintaxe da instrução While:

```powershell
while (<condition>){<statement list>}
```

Quando você executa uma instrução while, o PowerShell avalia a `<condition>` seção da instrução antes de inserir a `<statement list>` seção. A parte da condição da instrução é resolvida como true ou false. Desde que a condição permaneça verdadeira, o PowerShell executa a `<statement list>` seção novamente.

A `<statement list>` seção da instrução contém um ou mais comandos que são executados cada vez que o loop é inserido ou repetido.

Por exemplo, a instrução While a seguir exibe os números de 1 a 3 se a variável $val não foi criada ou se a variável $val foi criada e inicializada como 0.

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

Neste exemplo, a condição ($val não é igual a 3) é true enquanto $val \= 0, 1, 2. Cada vez pelo loop, $val é incrementado em 1 usando o \+ \+ operador de incremento unário ($Val \+ \+ ). A última hora pelo loop, $val \= 3. Quando $val é igual a 3, a instrução Condition é avaliada como false e o loop é encerrado.

Para escrever convenientemente esse comando no prompt de comando do PowerShell, você pode inseri-lo da seguinte maneira:

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

Observe que o ponto e vírgula separa o primeiro comando que adiciona 1 a $val do segundo comando que grava o valor de $val no console.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Do](about_Do.md)

[about_Foreach](about_Foreach.md)

[about_For](about_For.md)

[about_Language_Keywords](about_Language_Keywords.md)
