---
title: Como adicionar notas a um tópico de ajuda do cmdlet
ms.date: 09/12/2016
ms.openlocfilehash: d3679126ea34d7e86bcda700d0d050d8312a7aa2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893400"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Como adicionar notas a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção **observações** a um tópico de ajuda do cmdlet do PowerShell. A seção **observações** é usada para explicar os detalhes que não se ajustam facilmente às outras seções estruturadas, como uma explicação mais detalhada de um parâmetro. Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, mas importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.

Não há limites para o número de anotações que você pode adicionar a uma seção de anotações. Para cada nota, adicione um par de `<maml:alert>` marcas ao `<maml:alertset>` nó. O conteúdo de cada nota é adicionado dentro de um conjunto de `<maml:para>` marcas. Use marcas em branco `<maml:para>` para espaçamento.

O XML a seguir mostra um `<maml:alertset>` nó com duas observações. Observe que cada observação tem uma `<maml:title>` marca opcional (os títulos podem ser usados para agrupar qualquer conjunto de `<maml:alert>` marcas) e que cada nota tem uma linha em branco após o conteúdo do espaçamento.

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```
