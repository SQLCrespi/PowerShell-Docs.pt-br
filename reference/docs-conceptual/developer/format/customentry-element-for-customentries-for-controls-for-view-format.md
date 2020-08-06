---
title: Elemento CustomEntry para CustomEntries para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785890"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="84b0b-102">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="84b0b-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="84b0b-103">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="84b0b-103">Provides a definition of the control.</span></span> <span data-ttu-id="84b0b-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="84b0b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="84b0b-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="84b0b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84b0b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="84b0b-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="84b0b-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="84b0b-107">Attributes and Elements</span></span>

<span data-ttu-id="84b0b-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="84b0b-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="84b0b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="84b0b-109">Attributes</span></span>

<span data-ttu-id="84b0b-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="84b0b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84b0b-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="84b0b-111">Child Elements</span></span>

|<span data-ttu-id="84b0b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="84b0b-112">Element</span></span>|<span data-ttu-id="84b0b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="84b0b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84b0b-114">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="84b0b-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="84b0b-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="84b0b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="84b0b-116">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="84b0b-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="84b0b-117">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="84b0b-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="84b0b-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="84b0b-118">Required element.</span></span><br /><br /> <span data-ttu-id="84b0b-119">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="84b0b-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="84b0b-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="84b0b-120">Parent Elements</span></span>

|<span data-ttu-id="84b0b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="84b0b-121">Element</span></span>|<span data-ttu-id="84b0b-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="84b0b-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84b0b-123">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="84b0b-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="84b0b-124">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="84b0b-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="84b0b-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="84b0b-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="84b0b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84b0b-126">See Also</span></span>

[<span data-ttu-id="84b0b-127">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="84b0b-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="84b0b-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="84b0b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
