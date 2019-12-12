---
title: Elemento CustomEntries para CustomControl para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364085"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="37e1f-102">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="37e1f-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="37e1f-103">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="37e1f-103">Provides the definitions for the control.</span></span> <span data-ttu-id="37e1f-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="37e1f-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="37e1f-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37e1f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="37e1f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="37e1f-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="37e1f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="37e1f-107">Attributes and Elements</span></span>

<span data-ttu-id="37e1f-108">As seções a seguir descrevem atributos, elementos filho e elementos pai do elemento `CustomEntries`.</span><span class="sxs-lookup"><span data-stu-id="37e1f-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="37e1f-109">Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="37e1f-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="37e1f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="37e1f-110">Attributes</span></span>

<span data-ttu-id="37e1f-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="37e1f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="37e1f-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="37e1f-112">Child Elements</span></span>

|<span data-ttu-id="37e1f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="37e1f-113">Element</span></span>|<span data-ttu-id="37e1f-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="37e1f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="37e1f-115">Elemento CustomEntry para CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37e1f-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="37e1f-116">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="37e1f-116">Required element.</span></span><br /><br /> <span data-ttu-id="37e1f-117">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="37e1f-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="37e1f-118">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="37e1f-118">Parent Elements</span></span>

|<span data-ttu-id="37e1f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="37e1f-119">Element</span></span>|<span data-ttu-id="37e1f-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="37e1f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="37e1f-121">Elemento CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37e1f-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="37e1f-122">Define o controle personalizado que exibe o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="37e1f-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="37e1f-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="37e1f-123">Remarks</span></span>

<span data-ttu-id="37e1f-124">Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único elemento `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="37e1f-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="37e1f-125">No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes grupos.</span><span class="sxs-lookup"><span data-stu-id="37e1f-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="37e1f-126">Nesses casos, você pode definir um elemento `CustomEntry` para um grupo.</span><span class="sxs-lookup"><span data-stu-id="37e1f-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="37e1f-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="37e1f-127">See Also</span></span>

[<span data-ttu-id="37e1f-128">Elemento CustomEntry para CustomEntries para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="37e1f-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="37e1f-129">Elemento CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="37e1f-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="37e1f-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="37e1f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
