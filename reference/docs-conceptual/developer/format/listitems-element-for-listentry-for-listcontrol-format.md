---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListItems para ListEntry para ListControl (formato)
description: Elemento ListItems para ListEntry para ListControl (formato)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666528"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="e003a-103">Elemento ListItems para ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e003a-103">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="e003a-104">Define as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e003a-104">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="e003a-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento de controle de lista (Format) ListEntry para o elemento ListControl (Format) ListItems para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e003a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e003a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e003a-106">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e003a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e003a-107">Attributes and Elements</span></span>

<span data-ttu-id="e003a-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListItems` elemento.</span><span class="sxs-lookup"><span data-stu-id="e003a-108">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="e003a-109">Não há nenhum limite para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="e003a-109">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="e003a-110">A ordem dos elementos filho define a ordem em que os valores são exibidos na exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e003a-110">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="e003a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e003a-111">Attributes</span></span>

<span data-ttu-id="e003a-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e003a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e003a-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e003a-113">Child Elements</span></span>

|<span data-ttu-id="e003a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e003a-114">Element</span></span>|<span data-ttu-id="e003a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e003a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e003a-116">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e003a-116">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="e003a-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="e003a-117">Required element.</span></span><br /><br /> <span data-ttu-id="e003a-118">Define a propriedade ou o script cujo valor é exibido pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e003a-118">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e003a-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e003a-119">Parent Elements</span></span>

|<span data-ttu-id="e003a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e003a-120">Element</span></span>|<span data-ttu-id="e003a-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e003a-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e003a-122">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e003a-122">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="e003a-123">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e003a-123">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e003a-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="e003a-124">Remarks</span></span>

<span data-ttu-id="e003a-125">Para obter mais informações sobre esse tipo de exibição, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e003a-125">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e003a-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e003a-126">Example</span></span>

<span data-ttu-id="e003a-127">Este exemplo mostra os elementos XML que definem três linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e003a-127">This example shows the XML elements that define three rows of the list view.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="e003a-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e003a-128">See Also</span></span>

[<span data-ttu-id="e003a-129">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e003a-129">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="e003a-130">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e003a-130">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="e003a-131">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="e003a-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e003a-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e003a-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
