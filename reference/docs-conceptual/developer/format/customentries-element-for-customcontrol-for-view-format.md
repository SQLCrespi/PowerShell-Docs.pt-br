---
title: Elemento CustomEntries para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364075"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="5c918-102">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5c918-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="5c918-103">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="5c918-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="5c918-104">A exibição de controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="5c918-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="5c918-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c918-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c918-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5c918-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c918-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5c918-107">Attributes and Elements</span></span>

<span data-ttu-id="5c918-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControlEntries`.</span><span class="sxs-lookup"><span data-stu-id="5c918-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="5c918-109">Você deve especificar um ou mais elementos filho.</span><span class="sxs-lookup"><span data-stu-id="5c918-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c918-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c918-110">Attributes</span></span>

<span data-ttu-id="5c918-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5c918-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c918-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="5c918-112">Child Elements</span></span>

|<span data-ttu-id="5c918-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c918-113">Element</span></span>|<span data-ttu-id="5c918-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c918-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c918-115">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5c918-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="5c918-116">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5c918-116">Required element.</span></span><br /><br /> <span data-ttu-id="5c918-117">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="5c918-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5c918-118">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="5c918-118">Parent Elements</span></span>

|<span data-ttu-id="5c918-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c918-119">Element</span></span>|<span data-ttu-id="5c918-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c918-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c918-121">Elemento CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5c918-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="5c918-122">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5c918-122">Required element.</span></span><br /><br /> <span data-ttu-id="5c918-123">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="5c918-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5c918-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="5c918-124">Remarks</span></span>

<span data-ttu-id="5c918-125">Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único elemento `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="5c918-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="5c918-126">No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="5c918-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="5c918-127">Nesses casos, você pode definir um elemento `CustomEntry` para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="5c918-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c918-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c918-128">See Also</span></span>

[<span data-ttu-id="5c918-129">Elemento CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5c918-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="5c918-130">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5c918-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5c918-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c918-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
