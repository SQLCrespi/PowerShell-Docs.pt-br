---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para View (formato)
description: Elemento CustomEntries para CustomControl para View (formato)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649975"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="b6915-103">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b6915-103">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="b6915-104">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6915-104">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="b6915-105">A exibição de controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="b6915-105">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="b6915-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="b6915-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6915-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b6915-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6915-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b6915-108">Attributes and Elements</span></span>

<span data-ttu-id="b6915-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="b6915-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="b6915-110">Você deve especificar um ou mais elementos filho.</span><span class="sxs-lookup"><span data-stu-id="b6915-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6915-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6915-111">Attributes</span></span>

<span data-ttu-id="b6915-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b6915-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6915-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b6915-113">Child Elements</span></span>

|<span data-ttu-id="b6915-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6915-114">Element</span></span>|<span data-ttu-id="b6915-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6915-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6915-116">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="b6915-116">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="b6915-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="b6915-117">Required element.</span></span><br /><br /> <span data-ttu-id="b6915-118">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6915-118">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b6915-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b6915-119">Parent Elements</span></span>

|<span data-ttu-id="b6915-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6915-120">Element</span></span>|<span data-ttu-id="b6915-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6915-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6915-122">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b6915-122">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="b6915-123">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="b6915-123">Required element.</span></span><br /><br /> <span data-ttu-id="b6915-124">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="b6915-124">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6915-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="b6915-125">Remarks</span></span>

<span data-ttu-id="b6915-126">Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="b6915-126">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="b6915-127">No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="b6915-127">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="b6915-128">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="b6915-128">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6915-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6915-129">See Also</span></span>

[<span data-ttu-id="b6915-130">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b6915-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="b6915-131">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="b6915-131">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b6915-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6915-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
