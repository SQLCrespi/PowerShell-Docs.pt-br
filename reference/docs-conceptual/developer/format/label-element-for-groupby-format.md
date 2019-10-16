---
title: Elemento Label para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365195"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="122fe-102">Elemento Label para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="122fe-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="122fe-103">Especifica um rótulo que é exibido quando um novo grupo é encontrado.</span><span class="sxs-lookup"><span data-stu-id="122fe-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="122fe-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de rótulo View (Format) para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="122fe-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="122fe-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="122fe-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="122fe-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="122fe-106">Attributes and Elements</span></span>

<span data-ttu-id="122fe-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Label`.</span><span class="sxs-lookup"><span data-stu-id="122fe-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="122fe-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="122fe-108">Attributes</span></span>

<span data-ttu-id="122fe-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="122fe-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="122fe-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="122fe-110">Child Elements</span></span>

<span data-ttu-id="122fe-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="122fe-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="122fe-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="122fe-112">Parent Elements</span></span>

|<span data-ttu-id="122fe-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="122fe-113">Element</span></span>|<span data-ttu-id="122fe-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="122fe-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="122fe-115">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="122fe-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="122fe-116">Define como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="122fe-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="122fe-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="122fe-117">Text Value</span></span>

<span data-ttu-id="122fe-118">Especifique o texto que será exibido sempre que o Windows PowerShell encontrar uma nova propriedade ou um novo valor de script.</span><span class="sxs-lookup"><span data-stu-id="122fe-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="122fe-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="122fe-119">Remarks</span></span>

<span data-ttu-id="122fe-120">Além do texto especificado por esse elemento, o Windows PowerShell exibe o novo valor que inicia o grupo e adiciona uma linha em branco antes e depois do grupo.</span><span class="sxs-lookup"><span data-stu-id="122fe-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="122fe-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="122fe-121">Example</span></span>

<span data-ttu-id="122fe-122">O exemplo a seguir mostra o rótulo de um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="122fe-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="122fe-123">O rótulo exibido seria semelhante a este: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="122fe-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="122fe-124">Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="122fe-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="122fe-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="122fe-125">See Also</span></span>

[<span data-ttu-id="122fe-126">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="122fe-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="122fe-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="122fe-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
