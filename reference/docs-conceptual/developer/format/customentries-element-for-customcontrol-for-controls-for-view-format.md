---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para Controls para View (formato)
description: Elemento CustomEntries para CustomControl para Controls para View (formato)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652379"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="ed31c-103">Elemento CustomEntries para CustomControl para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ed31c-103">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="ed31c-104">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="ed31c-104">Provides the definitions for the control.</span></span> <span data-ttu-id="ed31c-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="ed31c-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ed31c-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ed31c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed31c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ed31c-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed31c-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ed31c-108">Attributes and Elements</span></span>

<span data-ttu-id="ed31c-109">As seções a seguir descrevem atributos, elementos filho e elementos pai do `CustomEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="ed31c-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="ed31c-110">Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="ed31c-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed31c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed31c-111">Attributes</span></span>

<span data-ttu-id="ed31c-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ed31c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed31c-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ed31c-113">Child Elements</span></span>

|<span data-ttu-id="ed31c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed31c-114">Element</span></span>|<span data-ttu-id="ed31c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed31c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed31c-116">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="ed31c-116">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="ed31c-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="ed31c-117">Required element.</span></span><br /><br /> <span data-ttu-id="ed31c-118">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="ed31c-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ed31c-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ed31c-119">Parent Elements</span></span>

|<span data-ttu-id="ed31c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed31c-120">Element</span></span>|<span data-ttu-id="ed31c-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed31c-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed31c-122">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ed31c-122">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ed31c-123">Define o controle usado pela exibição.</span><span class="sxs-lookup"><span data-stu-id="ed31c-123">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ed31c-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="ed31c-124">Remarks</span></span>

<span data-ttu-id="ed31c-125">Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="ed31c-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="ed31c-126">No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="ed31c-126">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="ed31c-127">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="ed31c-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed31c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed31c-128">See Also</span></span>

[<span data-ttu-id="ed31c-129">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="ed31c-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="ed31c-130">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ed31c-130">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ed31c-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed31c-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
