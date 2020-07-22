---
title: Como adicionar links relacionados a um tópico de ajuda do cmdlet
ms.date: 09/12/2016
ms.openlocfilehash: 7557b3856d8470434070dd286cd7e30c9ba015c5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893366"
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
