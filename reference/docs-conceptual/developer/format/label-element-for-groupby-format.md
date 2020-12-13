---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para GroupBy (formato)
description: Elemento Label para GroupBy (formato)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649795"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="a4db8-103">Elemento Label para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="a4db8-103">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="a4db8-104">Especifica um rótulo que é exibido quando um novo grupo é encontrado.</span><span class="sxs-lookup"><span data-stu-id="a4db8-104">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="a4db8-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de rótulo View (Format) para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a4db8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4db8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4db8-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4db8-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a4db8-107">Attributes and Elements</span></span>

<span data-ttu-id="a4db8-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.</span><span class="sxs-lookup"><span data-stu-id="a4db8-108">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4db8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4db8-109">Attributes</span></span>

<span data-ttu-id="a4db8-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a4db8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4db8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a4db8-111">Child Elements</span></span>

<span data-ttu-id="a4db8-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a4db8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4db8-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a4db8-113">Parent Elements</span></span>

|<span data-ttu-id="a4db8-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4db8-114">Element</span></span>|<span data-ttu-id="a4db8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4db8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4db8-116">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="a4db8-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="a4db8-117">Define como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="a4db8-117">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a4db8-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="a4db8-118">Text Value</span></span>

<span data-ttu-id="a4db8-119">Especifique o texto que será exibido sempre que o Windows PowerShell encontrar uma nova propriedade ou um novo valor de script.</span><span class="sxs-lookup"><span data-stu-id="a4db8-119">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4db8-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="a4db8-120">Remarks</span></span>

<span data-ttu-id="a4db8-121">Além do texto especificado por esse elemento, o Windows PowerShell exibe o novo valor que inicia o grupo e adiciona uma linha em branco antes e depois do grupo.</span><span class="sxs-lookup"><span data-stu-id="a4db8-121">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="a4db8-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a4db8-122">Example</span></span>

<span data-ttu-id="a4db8-123">O exemplo a seguir mostra o rótulo de um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="a4db8-123">The following example shows the label for a new group.</span></span> <span data-ttu-id="a4db8-124">O rótulo exibido seria semelhante a este: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="a4db8-124">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="a4db8-125">Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="a4db8-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4db8-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4db8-126">See Also</span></span>

[<span data-ttu-id="a4db8-127">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="a4db8-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="a4db8-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4db8-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
