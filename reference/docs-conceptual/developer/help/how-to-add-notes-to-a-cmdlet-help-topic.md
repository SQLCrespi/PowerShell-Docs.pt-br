---
title: Como adicionar notas a um tópico de ajuda do cmdlet
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298303"
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
