---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomEntries para Controls para configuração (formato)
description: Elemento CustomEntry para CustomEntries para Controls para configuração (formato)
ms.openlocfilehash: a525b198c8f595e04dc0804d36b5533b94f43c6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646078"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="2355d-103">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="2355d-103">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="2355d-104">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="2355d-104">Provides a definition of the control.</span></span> <span data-ttu-id="2355d-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="2355d-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="2355d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="2355d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2355d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2355d-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2355d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2355d-108">Attributes and Elements</span></span>

<span data-ttu-id="2355d-109">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="2355d-109">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2355d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2355d-110">Attributes</span></span>

<span data-ttu-id="2355d-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2355d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2355d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2355d-112">Child Elements</span></span>

|<span data-ttu-id="2355d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2355d-113">Element</span></span>|<span data-ttu-id="2355d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2355d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2355d-115">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2355d-115">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="2355d-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2355d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="2355d-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="2355d-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="2355d-118">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2355d-118">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="2355d-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="2355d-119">Required element.</span></span><br /><br /> <span data-ttu-id="2355d-120">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="2355d-120">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2355d-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2355d-121">Parent Elements</span></span>

|<span data-ttu-id="2355d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2355d-122">Element</span></span>|<span data-ttu-id="2355d-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="2355d-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2355d-124">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2355d-124">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="2355d-125">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="2355d-125">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2355d-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="2355d-126">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="2355d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2355d-127">See Also</span></span>

[<span data-ttu-id="2355d-128">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2355d-128">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2355d-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2355d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
