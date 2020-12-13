---
ms.date: 10/20/2020
ms.topic: reference
title: Como adicionar notas a um tópico de ajuda do cmdlet
description: Como adicionar notas a um tópico de ajuda do cmdlet
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659565"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="09638-103">Como adicionar notas a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="09638-103">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="09638-104">Esta seção descreve como adicionar uma seção **NOTAS** a um tópico de ajuda de cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09638-104">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="09638-105">A seção **NOTAS** é usada para explicar os detalhes que não se encaixam com facilidade em outras seções estruturadas, como uma explicação mais detalhada de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="09638-105">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="09638-106">Esse conteúdo pode incluir comentários sobre como o cmdlet funciona com um provedor específico, alguns usos exclusivos, porém importantes, do cmdlet, ou maneiras de evitar possíveis condições de erro.</span><span class="sxs-lookup"><span data-stu-id="09638-106">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="09638-107">A seção **NOTAS** é definida usando um único nó `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="09638-107">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="09638-108">Não há limites para o número de anotações que você pode adicionar a uma seção Notas.</span><span class="sxs-lookup"><span data-stu-id="09638-108">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="09638-109">Para cada nota, adicione um par de marcas `<maml:alert>` ao nó `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="09638-109">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="09638-110">O conteúdo de cada nota é adicionado dentro de um conjunto de marcas `<maml:para>`.</span><span class="sxs-lookup"><span data-stu-id="09638-110">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="09638-111">Use as marcas `<maml:para>` em branco para espaçamento.</span><span class="sxs-lookup"><span data-stu-id="09638-111">Use blank `<maml:para>` tags for spacing.</span></span>

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
