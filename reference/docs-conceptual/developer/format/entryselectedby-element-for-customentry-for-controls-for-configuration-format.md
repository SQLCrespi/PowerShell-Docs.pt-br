---
title: Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9467c8c2d80e46c0a47c31569efbddbabe25bb1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774262"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="f3fd2-102">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f3fd2-103">Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="f3fd2-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f3fd2-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f3fd2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f3fd2-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3fd2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f3fd2-107">Attributes and Elements</span></span>

<span data-ttu-id="f3fd2-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3fd2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3fd2-109">Attributes</span></span>

<span data-ttu-id="f3fd2-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f3fd2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f3fd2-111">Child Elements</span></span>

|<span data-ttu-id="f3fd2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3fd2-112">Element</span></span>|<span data-ttu-id="f3fd2-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3fd2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3fd2-114">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="f3fd2-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f3fd2-116">Define a condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="f3fd2-117">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="f3fd2-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f3fd2-119">Especifica um conjunto de tipos .NET que usam essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="f3fd2-120">Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="f3fd2-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f3fd2-122">Especifica um tipo .NET que usa essa definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f3fd2-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f3fd2-123">Parent Elements</span></span>

|<span data-ttu-id="f3fd2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3fd2-124">Element</span></span>|<span data-ttu-id="f3fd2-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3fd2-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3fd2-126">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="f3fd2-127">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3fd2-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="f3fd2-128">Remarks</span></span>

<span data-ttu-id="f3fd2-129">No mínimo, cada definição deve ter pelo menos um tipo .NET, um conjunto de seleção ou uma condição de seleção especificada.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="f3fd2-130">Não há nenhum limite máximo para o número de tipos, conjuntos de seleção ou condições de seleção que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="f3fd2-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3fd2-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3fd2-131">See Also</span></span>

[<span data-ttu-id="f3fd2-132">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="f3fd2-133">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f3fd2-134">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="f3fd2-135">Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f3fd2-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f3fd2-136">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3fd2-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
