---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para GroupBy (formato)
description: Elemento CustomEntries para CustomControl para GroupBy (formato)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666783"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="f4cd5-103">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-103">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="f4cd5-104">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-104">Provides the definitions for the control.</span></span> <span data-ttu-id="f4cd5-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f4cd5-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4cd5-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f4cd5-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4cd5-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f4cd5-108">Attributes and Elements</span></span>

<span data-ttu-id="f4cd5-109">As seções a seguir descrevem atributos, elementos filho e elementos pai do `CustomEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="f4cd5-110">Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4cd5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f4cd5-111">Attributes</span></span>

<span data-ttu-id="f4cd5-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4cd5-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f4cd5-113">Child Elements</span></span>

|<span data-ttu-id="f4cd5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4cd5-114">Element</span></span>|<span data-ttu-id="f4cd5-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4cd5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4cd5-116">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-116">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="f4cd5-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-117">Required element.</span></span><br /><br /> <span data-ttu-id="f4cd5-118">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f4cd5-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f4cd5-119">Parent Elements</span></span>

|<span data-ttu-id="f4cd5-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4cd5-120">Element</span></span>|<span data-ttu-id="f4cd5-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4cd5-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4cd5-122">Elemento CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-122">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="f4cd5-123">Define o controle personalizado que exibe o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-123">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f4cd5-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4cd5-124">Remarks</span></span>

<span data-ttu-id="f4cd5-125">Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="f4cd5-126">No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes grupos.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-126">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="f4cd5-127">Nesses casos, você pode definir um `CustomEntry` elemento para um grupo.</span><span class="sxs-lookup"><span data-stu-id="f4cd5-127">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4cd5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4cd5-128">See Also</span></span>

[<span data-ttu-id="f4cd5-129">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="f4cd5-130">Elemento CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4cd5-130">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="f4cd5-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4cd5-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
