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
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="18f69-102">Como adicionar notas a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="18f69-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="18f69-103">Esta seção descreve como adicionar uma seção **observações** a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18f69-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="18f69-104">A seção **observações** é usada para explicar os detalhes que não se ajustam facilmente às outras seções estruturadas, como uma explicação mais detalhada de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="18f69-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="18f69-105">Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, mas importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.</span><span class="sxs-lookup"><span data-stu-id="18f69-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="18f69-106">Não há limites para o número de anotações que você pode adicionar a uma seção de anotações.</span><span class="sxs-lookup"><span data-stu-id="18f69-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="18f69-107">Para cada nota, adicione um par de `<maml:alert>` marcas ao `<maml:alertset>` nó.</span><span class="sxs-lookup"><span data-stu-id="18f69-107">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="18f69-108">O conteúdo de cada nota é adicionado dentro de um conjunto de `<maml:para>` marcas.</span><span class="sxs-lookup"><span data-stu-id="18f69-108">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="18f69-109">Use marcas em branco `<maml:para>` para espaçamento.</span><span class="sxs-lookup"><span data-stu-id="18f69-109">Use blank `<maml:para>` tags for spacing.</span></span>

<span data-ttu-id="18f69-110">O XML a seguir mostra um `<maml:alertset>` nó com duas observações.</span><span class="sxs-lookup"><span data-stu-id="18f69-110">The following XML shows an `<maml:alertset>` node with two notes.</span></span> <span data-ttu-id="18f69-111">Observe que cada observação tem uma `<maml:title>` marca opcional (os títulos podem ser usados para agrupar qualquer conjunto de `<maml:alert>` marcas) e que cada nota tem uma linha em branco após o conteúdo do espaçamento.</span><span class="sxs-lookup"><span data-stu-id="18f69-111">Notice that each note has an optional `<maml:title>` tag (titles can be used to group any set of `<maml:alert>` tags), and that each note has a blank line following the content for spacing.</span></span>

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
