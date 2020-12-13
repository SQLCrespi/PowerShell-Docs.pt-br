---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ListItem para ListControl (formato)
description: Elemento PropertyName para ListItem para ListControl (formato)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665967"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="66190-103">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="66190-103">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="66190-104">Especifica a propriedade .NET cujo valor é exibido na lista.</span><span class="sxs-lookup"><span data-stu-id="66190-104">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="66190-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) NomeDaPropriedade Element for ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="66190-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="66190-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="66190-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="66190-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="66190-107">Attributes and Elements</span></span>

<span data-ttu-id="66190-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="66190-108">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="66190-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="66190-109">Attributes</span></span>

<span data-ttu-id="66190-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="66190-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="66190-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="66190-111">Child Elements</span></span>

<span data-ttu-id="66190-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="66190-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="66190-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="66190-113">Parent Elements</span></span>

|<span data-ttu-id="66190-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="66190-114">Element</span></span>|<span data-ttu-id="66190-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="66190-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="66190-116">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="66190-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="66190-117">Define a propriedade ou o script cujo valor é exibido na linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="66190-117">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="66190-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="66190-118">Text Value</span></span>

<span data-ttu-id="66190-119">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="66190-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="66190-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="66190-120">Remarks</span></span>

<span data-ttu-id="66190-121">Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="66190-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="66190-122">Além de exibir o valor da propriedade, você também pode especificar um rótulo para o valor ou uma cadeia de caracteres de formato que possa ser usada para alterar a exibição do valor.</span><span class="sxs-lookup"><span data-stu-id="66190-122">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="66190-123">Para obter mais informações sobre como especificar dados em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="66190-123">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="66190-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="66190-124">Example</span></span>

<span data-ttu-id="66190-125">O exemplo a seguir mostra como especificar o rótulo e a propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="66190-125">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="66190-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66190-126">See Also</span></span>

[<span data-ttu-id="66190-127">Elemento ScriptBlock para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="66190-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="66190-128">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="66190-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="66190-129">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="66190-129">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="66190-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="66190-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
