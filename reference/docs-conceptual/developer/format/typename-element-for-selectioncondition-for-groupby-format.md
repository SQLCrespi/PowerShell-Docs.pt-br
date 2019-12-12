---
title: Elemento TypeName para SelectionCondition para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361475"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="622f3-102">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="622f3-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="622f3-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="622f3-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="622f3-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="622f3-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="622f3-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) EntrySelectedBy Element para CustomEntry para GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="622f3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="622f3-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="622f3-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="622f3-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="622f3-107">Attributes and Elements</span></span>

<span data-ttu-id="622f3-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="622f3-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="622f3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="622f3-109">Attributes</span></span>

<span data-ttu-id="622f3-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="622f3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="622f3-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="622f3-111">Child Elements</span></span>

<span data-ttu-id="622f3-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="622f3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="622f3-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="622f3-113">Parent Elements</span></span>

|<span data-ttu-id="622f3-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="622f3-114">Element</span></span>|<span data-ttu-id="622f3-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="622f3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="622f3-116">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="622f3-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="622f3-117">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="622f3-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="622f3-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="622f3-118">Text Value</span></span>

<span data-ttu-id="622f3-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="622f3-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="622f3-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="622f3-120">Remarks</span></span>

<span data-ttu-id="622f3-121">Quando esse elemento é especificado, você não pode especificar o elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="622f3-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="622f3-122">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="622f3-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="622f3-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="622f3-123">See Also</span></span>

[<span data-ttu-id="622f3-124">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="622f3-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="622f3-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="622f3-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
