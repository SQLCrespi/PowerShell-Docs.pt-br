---
title: Como adicionar notas a um tópico de ajuda do cmdlet
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298303"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="8b94c-102">Como adicionar notas a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="8b94c-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="8b94c-103">Esta seção descreve como adicionar uma seção **NOTAS** a um tópico de ajuda de cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b94c-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="8b94c-104">A seção **NOTAS** é usada para explicar os detalhes que não se encaixam com facilidade em outras seções estruturadas, como uma explicação mais detalhada de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8b94c-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="8b94c-105">Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, porém importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.</span><span class="sxs-lookup"><span data-stu-id="8b94c-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="8b94c-106">A seção **NOTAS** é definida usando um único nó `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="8b94c-106">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="8b94c-107">Não há limites para o número de anotações que você pode adicionar a uma seção Notas.</span><span class="sxs-lookup"><span data-stu-id="8b94c-107">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="8b94c-108">Para cada nota, adicione um par de marcas `<maml:alert>` ao nó `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="8b94c-108">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="8b94c-109">O conteúdo de cada nota é adicionado dentro de um conjunto de marcas `<maml:para>`.</span><span class="sxs-lookup"><span data-stu-id="8b94c-109">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="8b94c-110">Use as marcas `<maml:para>` em branco para espaçamento.</span><span class="sxs-lookup"><span data-stu-id="8b94c-110">Use blank `<maml:para>` tags for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
