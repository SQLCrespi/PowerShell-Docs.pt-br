---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomControl para View (formato)
description: Elemento CustomControl para View (formato)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655464"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="6e49b-103">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e49b-103">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="6e49b-104">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="6e49b-104">Defines a custom control format for the view.</span></span>

<span data-ttu-id="6e49b-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6e49b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e49b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e49b-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e49b-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6e49b-107">Attributes and Elements</span></span>

<span data-ttu-id="6e49b-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e49b-108">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="6e49b-109">Você deve especificar um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="6e49b-109">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e49b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e49b-110">Attributes</span></span>

<span data-ttu-id="6e49b-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="6e49b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e49b-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6e49b-112">Child Elements</span></span>

|<span data-ttu-id="6e49b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e49b-113">Element</span></span>|<span data-ttu-id="6e49b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e49b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e49b-115">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e49b-115">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="6e49b-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="6e49b-116">Required element.</span></span><br /><br /> <span data-ttu-id="6e49b-117">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="6e49b-117">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e49b-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6e49b-118">Parent Elements</span></span>

|<span data-ttu-id="6e49b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e49b-119">Element</span></span>|<span data-ttu-id="6e49b-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e49b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e49b-121">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e49b-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="6e49b-122">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="6e49b-122">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e49b-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e49b-123">Remarks</span></span>

<span data-ttu-id="6e49b-124">Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle, mas é possível fornecer várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="6e49b-124">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="6e49b-125">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="6e49b-125">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e49b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e49b-126">See Also</span></span>

[<span data-ttu-id="6e49b-127">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e49b-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e49b-128">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e49b-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="6e49b-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e49b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
