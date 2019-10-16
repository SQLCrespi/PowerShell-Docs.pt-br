---
title: Elemento CustomEntry para CustomEntries para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364045"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="8cd48-102">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="8cd48-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="8cd48-103">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="8cd48-103">Provides a definition of the control.</span></span> <span data-ttu-id="8cd48-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="8cd48-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8cd48-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8cd48-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8cd48-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8cd48-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cd48-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8cd48-107">Attributes and Elements</span></span>

<span data-ttu-id="8cd48-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do elemento `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="8cd48-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8cd48-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8cd48-109">Attributes</span></span>

<span data-ttu-id="8cd48-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8cd48-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8cd48-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="8cd48-111">Child Elements</span></span>

|<span data-ttu-id="8cd48-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8cd48-112">Element</span></span>|<span data-ttu-id="8cd48-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="8cd48-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8cd48-114">Elemento EntrySelectedBy para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8cd48-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="8cd48-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8cd48-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8cd48-116">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="8cd48-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="8cd48-117">Elemento CustomItem para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8cd48-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="8cd48-118">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8cd48-118">Required element.</span></span><br /><br /> <span data-ttu-id="8cd48-119">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="8cd48-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8cd48-120">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="8cd48-120">Parent Elements</span></span>

|<span data-ttu-id="8cd48-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8cd48-121">Element</span></span>|<span data-ttu-id="8cd48-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="8cd48-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8cd48-123">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8cd48-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="8cd48-124">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="8cd48-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8cd48-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="8cd48-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="8cd48-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8cd48-126">See Also</span></span>

[<span data-ttu-id="8cd48-127">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8cd48-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8cd48-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd48-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
