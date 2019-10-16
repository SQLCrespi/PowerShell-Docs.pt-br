---
title: Elemento CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363355"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="bdcf1-102">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="bdcf1-103">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="bdcf1-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bdcf1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bdcf1-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bdcf1-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bdcf1-106">Attributes and Elements</span></span>

<span data-ttu-id="bdcf1-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControl`.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="bdcf1-108">Você deve especificar um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bdcf1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdcf1-109">Attributes</span></span>

<span data-ttu-id="bdcf1-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bdcf1-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="bdcf1-111">Child Elements</span></span>

|<span data-ttu-id="bdcf1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdcf1-112">Element</span></span>|<span data-ttu-id="bdcf1-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="bdcf1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdcf1-114">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="bdcf1-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-115">Required element.</span></span><br /><br /> <span data-ttu-id="bdcf1-116">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bdcf1-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="bdcf1-117">Parent Elements</span></span>

|<span data-ttu-id="bdcf1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdcf1-118">Element</span></span>|<span data-ttu-id="bdcf1-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="bdcf1-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdcf1-120">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="bdcf1-121">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bdcf1-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="bdcf1-122">Remarks</span></span>

<span data-ttu-id="bdcf1-123">Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle, mas é possível fornecer várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="bdcf1-124">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="bdcf1-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdcf1-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdcf1-125">See Also</span></span>

[<span data-ttu-id="bdcf1-126">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bdcf1-127">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="bdcf1-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="bdcf1-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdcf1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
