---
ms.date: 09/12/2016
ms.topic: reference
title: Como adicionar links relacionados a um tópico de ajuda do cmdlet
description: Como adicionar links relacionados a um tópico de ajuda do cmdlet
ms.openlocfilehash: 7f1baefea69310bdf835c52461f8d3f49c4d94e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661998"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Como adicionar links relacionados a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar referências a outro conteúdo relacionado a um tópico de ajuda do cmdlet do PowerShell. Como essas referências aparecem em uma janela de comando, elas não são vinculadas diretamente ao conteúdo referenciado.

Nos tópicos de ajuda do cmdlet incluídos no PowerShell, esses links fazem referência a outros cmdlets, conteúdo conceitual ( `about_` ) e outros documentos e arquivos de ajuda que não estão relacionados ao PowerShell.

O XML a seguir mostra como adicionar um nó **RelatedLinks** que contém duas referências a tópicos relacionados.

```xml
<maml:relatedLinks>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
</ maml:relatedLinks >
```
