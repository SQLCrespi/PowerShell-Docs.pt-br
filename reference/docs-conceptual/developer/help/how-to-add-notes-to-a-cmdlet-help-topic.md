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
ms.openlocfilehash: 1a365a167c245006bb882a542aedb5c43cfc4c96
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557100"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Como adicionar notas a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção observações a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção observações é usada para explicar os detalhes que não se ajustam facilmente às outras seções estruturadas, como uma explicação mais detalhada de um parâmetro. Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, mas importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.

Não há limites para o número de anotações que você pode adicionar a uma seção de anotações. Para cada observação, adicione um par de \< marcas maml: alerta> ao \< nó maml: alertset>. O conteúdo de cada nota é adicionado dentro de um conjunto de \< marcas maml: para>. Use \< marcas maml: para> em branco para espaçamento.

O XML a seguir mostra um \< nó maml: alertset> com duas observações. Observe que cada observação tem uma \< marca opcional maml: title> (os títulos podem ser usados para agrupar qualquer conjunto de \< maml: marcas de alerta>) e que cada nota tem uma linha em branco após o conteúdo para espaçamento.

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
