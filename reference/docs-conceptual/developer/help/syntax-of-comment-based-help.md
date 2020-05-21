---
title: Sintaxe da ajuda baseada em comentários | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8adc997-1a71-48e9-9383-513ef13da7cf
caps.latest.revision: 4
ms.openlocfilehash: da74c674c704794d8648dcdf9ba0a1617decba9b
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560603"
---
# <a name="syntax-of-comment-based-help"></a>Sintaxe de ajuda baseada em comentários

Esta seção descreve a sintaxe da ajuda baseada em comentários.

## <a name="syntax-diagram"></a>Diagrama de sintaxe

 A sintaxe da ajuda baseada em comentários é a seguinte:

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a>Descrição da sintaxe

 A ajuda baseada em comentários é escrita como uma série de comentários. Você pode digitar um símbolo de comentário (#) antes de cada linha de comentários ou pode usar os \< símbolos "#" e "# >" para criar um bloco de comentário. Todas as linhas dentro do bloco de comentários são interpretadas como comentários.

 Cada seção da ajuda baseada em comentários é definida por uma palavra-chave e cada palavra-chave é precedida por um ponto (.). As palavras-chave podem aparecer em qualquer ordem. Os nomes de palavra-chave não diferenciam maiúsculas de minúsculas.

 Um bloco de comentário deve conter pelo menos uma palavra-chave de ajuda. Algumas das palavras-chave, como EXAMPLE, podem aparecer muitas vezes no mesmo bloco de comentário. O conteúdo da ajuda para cada palavra-chave começa na linha após a palavra-chave e pode abranger várias linhas.

 Todas as linhas em um tópico de ajuda com base em comentários devem ser contíguas. Se um tópico de ajuda baseado em comentário seguir um comentário que não faz parte do tópico da ajuda, deve haver pelo menos uma linha em branco entre a última linha de comentário de não ajuda e o início da ajuda baseada em comentários.

 Por exemplo, o tópico de ajuda baseado em comentário a seguir contém o. Palavra-chave Description e seu valor, que é uma descrição de uma função ou script.

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
