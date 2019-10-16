---
title: Elemento TypeName para EntrySelectedBy para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361665"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="1674e-102">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1674e-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="1674e-103">Especifica um tipo .NET que usa essa definição do controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="1674e-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="1674e-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="1674e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1674e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) EntrySelectedBy elemento para CustomEntry para o elemento GroupBy (Format) TypeName para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1674e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1674e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1674e-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1674e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1674e-107">Attributes and Elements</span></span>

<span data-ttu-id="1674e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="1674e-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1674e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1674e-109">Attributes</span></span>

<span data-ttu-id="1674e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1674e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1674e-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="1674e-111">Child Elements</span></span>

<span data-ttu-id="1674e-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1674e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1674e-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="1674e-113">Parent Elements</span></span>

|<span data-ttu-id="1674e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="1674e-114">Element</span></span>|<span data-ttu-id="1674e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="1674e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1674e-116">Elemento EntrySelectedBy para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1674e-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="1674e-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="1674e-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1674e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1674e-118">Text Value</span></span>

<span data-ttu-id="1674e-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="1674e-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1674e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="1674e-120">Remarks</span></span>

<span data-ttu-id="1674e-121">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="1674e-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1674e-122">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1674e-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1674e-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1674e-123">See Also</span></span>

[<span data-ttu-id="1674e-124">Criando controles personalizados</span><span class="sxs-lookup"><span data-stu-id="1674e-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1674e-125">Elemento EntrySelectedBy para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1674e-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="1674e-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1674e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
