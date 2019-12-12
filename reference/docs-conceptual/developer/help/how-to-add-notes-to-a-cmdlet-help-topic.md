---
title: Como adicionar anotações a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361265"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Como adicionar notas a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção observações a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção observações é usada para explicar os detalhes que não se ajustam facilmente às outras seções estruturadas, como uma explicação mais detalhada de um parâmetro. Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, mas importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.

Não há limites para o número de anotações que você pode adicionar a uma seção de anotações. Para cada nota, adicione um par de \<maml: > marcas de alerta ao nó \<maml: alertSet >. O conteúdo de cada nota é adicionado dentro de um conjunto de \<maml: para > marcas. Use as marcas em branco \<maml: para > para espaçamento.

O XML a seguir mostra um \<maml: alertSet > nó com duas observações. Observe que cada observação tem uma marcação opcional \<maml: title > (os títulos podem ser usados para agrupar qualquer conjunto de \<maml: marcas de > de alerta) e que cada nota tenha uma linha em branco após o conteúdo para espaçamento.

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



