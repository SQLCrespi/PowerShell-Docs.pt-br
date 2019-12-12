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
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="f54f4-102">Como adicionar notas a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="f54f4-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="f54f4-103">Esta seção descreve como adicionar uma seção observações a um tópico de ajuda do cmdlet® do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f54f4-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="f54f4-104">A seção observações é usada para explicar os detalhes que não se ajustam facilmente às outras seções estruturadas, como uma explicação mais detalhada de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f54f4-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="f54f4-105">Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, mas importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.</span><span class="sxs-lookup"><span data-stu-id="f54f4-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="f54f4-106">Não há limites para o número de anotações que você pode adicionar a uma seção de anotações.</span><span class="sxs-lookup"><span data-stu-id="f54f4-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="f54f4-107">Para cada nota, adicione um par de \<maml: > marcas de alerta ao nó \<maml: alertSet >.</span><span class="sxs-lookup"><span data-stu-id="f54f4-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="f54f4-108">O conteúdo de cada nota é adicionado dentro de um conjunto de \<maml: para > marcas.</span><span class="sxs-lookup"><span data-stu-id="f54f4-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="f54f4-109">Use as marcas em branco \<maml: para > para espaçamento.</span><span class="sxs-lookup"><span data-stu-id="f54f4-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="f54f4-110">O XML a seguir mostra um \<maml: alertSet > nó com duas observações.</span><span class="sxs-lookup"><span data-stu-id="f54f4-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="f54f4-111">Observe que cada observação tem uma marcação opcional \<maml: title > (os títulos podem ser usados para agrupar qualquer conjunto de \<maml: marcas de > de alerta) e que cada nota tenha uma linha em branco após o conteúdo para espaçamento.</span><span class="sxs-lookup"><span data-stu-id="f54f4-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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



