---
title: Elemento CustomEntry para CustomEntries controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066463"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="6e2c1-102">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="6e2c1-103">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-103">Provides a definition of the control.</span></span> <span data-ttu-id="6e2c1-104">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="6e2c1-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para elemento de exibição (formato) CustomEntry CustomEntries controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e2c1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e2c1-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e2c1-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="6e2c1-107">Attributes and Elements</span></span>

<span data-ttu-id="6e2c1-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e2c1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e2c1-109">Attributes</span></span>

<span data-ttu-id="6e2c1-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e2c1-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6e2c1-111">Child Elements</span></span>

|<span data-ttu-id="6e2c1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e2c1-112">Element</span></span>|<span data-ttu-id="6e2c1-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e2c1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e2c1-114">Elemento EntrySelectedBy para CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="6e2c1-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6e2c1-116">Define os tipos de .NET que usam essa definição de controle ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="6e2c1-117">Elemento CustomItem para CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="6e2c1-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-118">Required element.</span></span><br /><br /> <span data-ttu-id="6e2c1-119">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e2c1-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6e2c1-120">Parent Elements</span></span>

|<span data-ttu-id="6e2c1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e2c1-121">Element</span></span>|<span data-ttu-id="6e2c1-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e2c1-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e2c1-123">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="6e2c1-124">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="6e2c1-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e2c1-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e2c1-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="6e2c1-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e2c1-126">See Also</span></span>

[<span data-ttu-id="6e2c1-127">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e2c1-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e2c1-128">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e2c1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
