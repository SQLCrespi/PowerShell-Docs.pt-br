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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="16757-102">Como adicionar links relacionados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="16757-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="16757-103">Esta seção descreve como adicionar referências a outro conteúdo relacionado a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16757-103">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="16757-104">Como essas referências aparecem em uma janela de comando, elas não são vinculadas diretamente ao conteúdo referenciado.</span><span class="sxs-lookup"><span data-stu-id="16757-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="16757-105">Nos tópicos de ajuda do cmdlet incluídos no PowerShell, esses links fazem referência a outros cmdlets, conteúdo conceitual ( `about_` ) e outros documentos e arquivos de ajuda que não estão relacionados ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16757-105">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="16757-106">O XML a seguir mostra como adicionar um nó **RelatedLinks** que contém duas referências a tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="16757-106">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

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
