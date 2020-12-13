---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)
description: Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645742"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="91c07-103">Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="91c07-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="91c07-104">Especifica um tipo .NET que usa essa definição do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="91c07-104">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="91c07-105">Não há nenhum limite para o número de tipos que podem ser especificados para uma definição.</span><span class="sxs-lookup"><span data-stu-id="91c07-105">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="91c07-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para o elemento View (Format) TypeName para EntrySelectedBy para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="91c07-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91c07-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91c07-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91c07-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="91c07-108">Attributes and Elements</span></span>

<span data-ttu-id="91c07-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="91c07-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91c07-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="91c07-110">Attributes</span></span>

<span data-ttu-id="91c07-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="91c07-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91c07-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="91c07-112">Child Elements</span></span>

<span data-ttu-id="91c07-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="91c07-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91c07-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="91c07-114">Parent Elements</span></span>

|<span data-ttu-id="91c07-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="91c07-115">Element</span></span>|<span data-ttu-id="91c07-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="91c07-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91c07-117">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="91c07-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="91c07-118">Define os tipos .NET que usam essa definição de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="91c07-118">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91c07-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="91c07-119">Text Value</span></span>

<span data-ttu-id="91c07-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="91c07-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91c07-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="91c07-121">Remarks</span></span>

<span data-ttu-id="91c07-122">Cada definição de exibição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="91c07-122">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="91c07-123">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="91c07-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91c07-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91c07-124">See Also</span></span>

[<span data-ttu-id="91c07-125">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="91c07-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="91c07-126">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="91c07-126">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="91c07-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="91c07-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
