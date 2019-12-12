---
title: Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368765"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="aa821-102">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aa821-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="aa821-103">Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="aa821-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="aa821-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="aa821-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="aa821-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento Configuration (Format) EntrySelectedBy para CustomEntry para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa821-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa821-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa821-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="aa821-107">Attributes and Elements</span></span>

<span data-ttu-id="aa821-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="aa821-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa821-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa821-109">Attributes</span></span>

<span data-ttu-id="aa821-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="aa821-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa821-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="aa821-111">Child Elements</span></span>

|<span data-ttu-id="aa821-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa821-112">Element</span></span>|<span data-ttu-id="aa821-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa821-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa821-114">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="aa821-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aa821-115">Optional element.</span></span><br /><br /> <span data-ttu-id="aa821-116">Define a condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="aa821-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="aa821-117">Elemento SelectionSetName para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="aa821-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aa821-118">Optional element.</span></span><br /><br /> <span data-ttu-id="aa821-119">Especifica um conjunto de tipos .NET que usam essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="aa821-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="aa821-120">Elemento TypeName para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="aa821-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aa821-121">Optional element.</span></span><br /><br /> <span data-ttu-id="aa821-122">Especifica um tipo .NET que usa essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="aa821-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa821-123">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="aa821-123">Parent Elements</span></span>

|<span data-ttu-id="aa821-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa821-124">Element</span></span>|<span data-ttu-id="aa821-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa821-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa821-126">Elemento CustomEntry para CustomControl para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="aa821-127">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="aa821-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa821-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa821-128">Remarks</span></span>

<span data-ttu-id="aa821-129">No mínimo, cada definição deve ter pelo menos um tipo .NET, um conjunto de seleção ou uma condição de seleção especificada.</span><span class="sxs-lookup"><span data-stu-id="aa821-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="aa821-130">Não há nenhum limite máximo para o número de tipos, conjuntos de seleção ou condições de seleção que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="aa821-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa821-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa821-131">See Also</span></span>

[<span data-ttu-id="aa821-132">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa821-133">Elemento SelectionSetName para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa821-134">Elemento CustomEntry para CustomControl para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa821-135">Elemento TypeName para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa821-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa821-136">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa821-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
