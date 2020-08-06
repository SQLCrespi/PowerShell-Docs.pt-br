---
title: Elemento ListItems para ListEntry para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 03b89a3df2ab0498533d0c00f303f643e0039b25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781130"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="21ab2-102">Elemento ListItems para ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="21ab2-102">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="21ab2-103">Define as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="21ab2-103">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="21ab2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento de controle de lista (Format) ListEntry para o elemento ListControl (Format) ListItems para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="21ab2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21ab2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="21ab2-105">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21ab2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="21ab2-106">Attributes and Elements</span></span>

<span data-ttu-id="21ab2-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListItems` elemento.</span><span class="sxs-lookup"><span data-stu-id="21ab2-107">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="21ab2-108">Não há nenhum limite para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="21ab2-108">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="21ab2-109">A ordem dos elementos filho define a ordem em que os valores são exibidos na exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="21ab2-109">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="21ab2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="21ab2-110">Attributes</span></span>

<span data-ttu-id="21ab2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="21ab2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21ab2-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="21ab2-112">Child Elements</span></span>

|<span data-ttu-id="21ab2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="21ab2-113">Element</span></span>|<span data-ttu-id="21ab2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="21ab2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21ab2-115">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="21ab2-115">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="21ab2-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="21ab2-116">Required element.</span></span><br /><br /> <span data-ttu-id="21ab2-117">Define a propriedade ou o script cujo valor é exibido pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="21ab2-117">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="21ab2-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="21ab2-118">Parent Elements</span></span>

|<span data-ttu-id="21ab2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="21ab2-119">Element</span></span>|<span data-ttu-id="21ab2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="21ab2-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21ab2-121">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="21ab2-121">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="21ab2-122">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="21ab2-122">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="21ab2-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="21ab2-123">Remarks</span></span>

<span data-ttu-id="21ab2-124">Para obter mais informações sobre esse tipo de exibição, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="21ab2-124">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="21ab2-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="21ab2-125">Example</span></span>

<span data-ttu-id="21ab2-126">Este exemplo mostra os elementos XML que definem três linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="21ab2-126">This example shows the XML elements that define three rows of the list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="21ab2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21ab2-127">See Also</span></span>

[<span data-ttu-id="21ab2-128">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="21ab2-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="21ab2-129">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="21ab2-129">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="21ab2-130">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="21ab2-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="21ab2-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="21ab2-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
