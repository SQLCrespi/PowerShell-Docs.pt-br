---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)
description: Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666664"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="bca85-103">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="bca85-104">Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="bca85-104">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="bca85-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="bca85-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="bca85-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="bca85-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bca85-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bca85-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bca85-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bca85-108">Attributes and Elements</span></span>

<span data-ttu-id="bca85-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="bca85-109">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bca85-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bca85-110">Attributes</span></span>

<span data-ttu-id="bca85-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bca85-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bca85-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bca85-112">Child Elements</span></span>

|<span data-ttu-id="bca85-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="bca85-113">Element</span></span>|<span data-ttu-id="bca85-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="bca85-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bca85-115">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="bca85-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bca85-116">Optional element.</span></span><br /><br /> <span data-ttu-id="bca85-117">Define a condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="bca85-117">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="bca85-118">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="bca85-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bca85-119">Optional element.</span></span><br /><br /> <span data-ttu-id="bca85-120">Especifica um conjunto de tipos .NET que usam essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="bca85-120">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="bca85-121">Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="bca85-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bca85-122">Optional element.</span></span><br /><br /> <span data-ttu-id="bca85-123">Especifica um tipo .NET que usa essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="bca85-123">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bca85-124">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bca85-124">Parent Elements</span></span>

|<span data-ttu-id="bca85-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bca85-125">Element</span></span>|<span data-ttu-id="bca85-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="bca85-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bca85-127">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="bca85-128">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="bca85-128">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bca85-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="bca85-129">Remarks</span></span>

<span data-ttu-id="bca85-130">No mínimo, cada definição deve ter pelo menos um tipo .NET, um conjunto de seleção ou uma condição de seleção especificada.</span><span class="sxs-lookup"><span data-stu-id="bca85-130">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="bca85-131">Não há nenhum limite máximo para o número de tipos, conjuntos de seleção ou condições de seleção que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="bca85-131">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="bca85-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bca85-132">See Also</span></span>

[<span data-ttu-id="bca85-133">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="bca85-134">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="bca85-135">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="bca85-136">Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="bca85-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="bca85-137">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bca85-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
