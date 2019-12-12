---
title: Como adicionar links relacionados a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5aadb730-4eb7-4936-b8df-3b0c0ca04fd5
caps.latest.revision: 5
ms.openlocfilehash: aa46cbc5bfcfdfec9fcf9d2581ff641baa532860
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361215"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Como adicionar links relacionados a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar referências a outro conteúdo relacionado a um tópico de ajuda do cmdlet® do Windows PowerShell. Como essas referências aparecem em uma janela de comando, elas não são vinculadas diretamente ao conteúdo referenciado.

Nos tópicos de ajuda do cmdlet incluídos no Windows PowerShell®, esses links fazem referência a outros cmdlets, conteúdo conceitual ("about_") e outros documentos e arquivos de ajuda que não estão relacionados ao® do Windows PowerShell.

O XML a seguir mostra como adicionar um nó RelatedLinks que contém duas referências a tópicos relacionados.

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



