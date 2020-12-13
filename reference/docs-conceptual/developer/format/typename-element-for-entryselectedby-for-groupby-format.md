---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para GroupBy (formato)
description: Elemento TypeName para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645705"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="2f5d8-103">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2f5d8-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="2f5d8-104">Especifica um tipo .NET que usa essa definição do controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-104">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="2f5d8-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2f5d8-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element para CustomEntry para o elemento GroupBy (Format) TypeName para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f5d8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2f5d8-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2f5d8-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f5d8-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2f5d8-108">Attributes and Elements</span></span>

<span data-ttu-id="2f5d8-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f5d8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f5d8-110">Attributes</span></span>

<span data-ttu-id="2f5d8-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2f5d8-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2f5d8-112">Child Elements</span></span>

<span data-ttu-id="2f5d8-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f5d8-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2f5d8-114">Parent Elements</span></span>

|<span data-ttu-id="2f5d8-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f5d8-115">Element</span></span>|<span data-ttu-id="2f5d8-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="2f5d8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f5d8-117">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2f5d8-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="2f5d8-118">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2f5d8-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2f5d8-119">Text Value</span></span>

<span data-ttu-id="2f5d8-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="2f5d8-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f5d8-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="2f5d8-121">Remarks</span></span>

<span data-ttu-id="2f5d8-122">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2f5d8-123">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2f5d8-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f5d8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f5d8-124">See Also</span></span>

[<span data-ttu-id="2f5d8-125">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="2f5d8-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2f5d8-126">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2f5d8-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="2f5d8-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f5d8-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
