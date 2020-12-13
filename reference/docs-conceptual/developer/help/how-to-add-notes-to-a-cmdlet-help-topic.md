---
ms.date: 10/20/2020
ms.topic: reference
title: Como adicionar notas a um tópico de ajuda do cmdlet
description: Como adicionar notas a um tópico de ajuda do cmdlet
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659565"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Como adicionar notas a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção **NOTAS** a um tópico de ajuda de cmdlet do PowerShell. A seção **NOTAS** é usada para explicar os detalhes que não se encaixam com facilidade em outras seções estruturadas, como uma explicação mais detalhada de um parâmetro. Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, porém importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.

A seção **NOTAS** é definida usando um único nó `<maml:alertset>`. Não há limites para o número de anotações que você pode adicionar a uma seção Notas. Para cada nota, adicione um par de marcas `<maml:alert>` ao nó `<maml:alertset>`. O conteúdo de cada nota é adicionado dentro de um conjunto de marcas `<maml:para>`. Use as marcas `<maml:para>` em branco para espaçamento.

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
