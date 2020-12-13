---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ListItem para ListControl (formato)
description: Elemento ScriptBlock para ListItem para ListControl (formato)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664978"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="b1394-103">Elemento ScriptBlock para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1394-103">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="b1394-104">Especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="b1394-104">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="b1394-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ScriptBlock (Format) para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1394-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1394-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b1394-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1394-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b1394-107">Attributes and Elements</span></span>

<span data-ttu-id="b1394-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="b1394-108">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1394-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1394-109">Attributes</span></span>

<span data-ttu-id="b1394-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b1394-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1394-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b1394-111">Child Elements</span></span>

<span data-ttu-id="b1394-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b1394-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b1394-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b1394-113">Parent Elements</span></span>

|<span data-ttu-id="b1394-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1394-114">Element</span></span>|<span data-ttu-id="b1394-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1394-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1394-116">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="b1394-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="b1394-117">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="b1394-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b1394-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b1394-118">Text Value</span></span>

<span data-ttu-id="b1394-119">Especifique o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="b1394-119">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1394-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="b1394-120">Remarks</span></span>

<span data-ttu-id="b1394-121">Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="b1394-121">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="b1394-122">Para obter mais informações sobre como especificar scripts em uma exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="b1394-122">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1394-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b1394-123">Example</span></span>

<span data-ttu-id="b1394-124">O exemplo a seguir mostra como especificar a propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="b1394-124">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="b1394-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1394-125">See Also</span></span>

[<span data-ttu-id="b1394-126">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1394-126">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="b1394-127">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="b1394-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b1394-128">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1394-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="b1394-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1394-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
