---
title: Elemento SelectionSetName para SelectionCondition para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 62f186be9e4b1dd5a297add0ce82011bc1ccdcd1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785227"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="6e297-102">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e297-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="6e297-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="6e297-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="6e297-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="6e297-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="6e297-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="6e297-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="6e297-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para o elemento de configuração (Format) SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="6e297-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e297-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e297-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e297-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6e297-108">Attributes and Elements</span></span>

<span data-ttu-id="6e297-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e297-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e297-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e297-110">Attributes</span></span>

<span data-ttu-id="6e297-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6e297-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e297-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6e297-112">Child Elements</span></span>

<span data-ttu-id="6e297-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6e297-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6e297-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6e297-114">Parent Elements</span></span>

|<span data-ttu-id="6e297-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e297-115">Element</span></span>|<span data-ttu-id="6e297-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e297-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e297-117">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e297-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="6e297-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="6e297-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6e297-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="6e297-119">Text Value</span></span>

<span data-ttu-id="6e297-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="6e297-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e297-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e297-121">Remarks</span></span>

<span data-ttu-id="6e297-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="6e297-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="6e297-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6e297-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="6e297-124">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6e297-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="6e297-125">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e297-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e297-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e297-126">See Also</span></span>

[<span data-ttu-id="6e297-127">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e297-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="6e297-128">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="6e297-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="6e297-129">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="6e297-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6e297-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e297-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
