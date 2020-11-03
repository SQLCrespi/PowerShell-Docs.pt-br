---
description: Executa uma lista de instruções uma ou mais vezes, sujeito a uma condição while ou until.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195758"
---
# <a name="about-do"></a>Sobre o

## <a name="short-description"></a>DESCRIÇÃO BREVE
Executa uma lista de instruções uma ou mais vezes, sujeito a uma condição while ou until.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A palavra-chave do funciona com a palavra-chave while ou a palavra-chave until para executar as instruções em um bloco de script, sujeito a uma condição. Ao contrário do loop while relacionado, o bloco de script em um loop do sempre é executado pelo menos uma vez.

Um loop do **-while** é uma variedade do loop While. Em um loop **do-while** , a condição é avaliada após a execução do bloco de script. Como em um loop while, o bloco de script é repetido, desde que a condição seja avaliada como true.

Como um loop **do-while** , um loop **do-until** sempre é executado pelo menos uma vez antes que a condição seja avaliada. No entanto, o bloco de script é executado somente enquanto a condição é falsa.

As palavras-chave de controle de fluxo de *continuação* e *interrupção* podem ser usadas em um loop **do-while** ou em um loop **do-until** .

### <a name="syntax"></a>Syntax

O seguinte mostra a sintaxe da instrução do **-while** :

```powershell
do {<statement list>} while (<condition>)
```

O seguinte mostra a sintaxe da instrução do **-until** :

```powershell
do {<statement list>} until (<condition>)
```

A lista de instruções contém uma ou mais instruções que são executadas cada vez que o loop é inserido ou repetido.

A parte da condição da instrução é resolvida como true ou false.

### <a name="example"></a>Exemplo

O exemplo a seguir de uma instrução do conta os itens em uma matriz até alcançar um item com um valor de 0.

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

O exemplo a seguir usa a palavra-chave until. Observe que o operador não igual a ( `-ne` ) é substituído pelo operador Equals to ( `-eq` ).

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

O exemplo a seguir grava todos os valores de uma matriz, ignorando qualquer valor menor que zero.

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_While](about_While.md)

[about_Operators](about_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)
