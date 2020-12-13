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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="2f056-103">Como adicionar links relacionados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="2f056-103">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="2f056-104">Esta seção descreve como adicionar referências a outro conteúdo relacionado a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f056-104">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="2f056-105">Como essas referências aparecem em uma janela de comando, elas não são vinculadas diretamente ao conteúdo referenciado.</span><span class="sxs-lookup"><span data-stu-id="2f056-105">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="2f056-106">Nos tópicos de ajuda do cmdlet incluídos no PowerShell, esses links fazem referência a outros cmdlets, conteúdo conceitual ( `about_` ) e outros documentos e arquivos de ajuda que não estão relacionados ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f056-106">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="2f056-107">O XML a seguir mostra como adicionar um nó **RelatedLinks** que contém duas referências a tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="2f056-107">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

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
