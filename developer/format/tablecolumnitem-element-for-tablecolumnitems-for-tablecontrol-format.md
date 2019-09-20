---
title: Elemento TableColumnItem para TableColumnItems para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 9e6cffc7476ef01124d95ecbf287d9788b0324c9
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143575"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="733b5-102">Elemento TableColumnItem para TableColumnItems para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="733b5-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="733b5-103">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="733b5-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="733b5-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) Elemento TableColumnItems para TableControlEntry para TableControl (Format) TableColumnItem elemento para TableColumnItems para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="733b5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="733b5-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="733b5-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="733b5-106">Attributes and Elements</span></span>

<span data-ttu-id="733b5-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai `TableColumnItem` do elemento.</span><span class="sxs-lookup"><span data-stu-id="733b5-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="733b5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="733b5-108">Attributes</span></span>

<span data-ttu-id="733b5-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="733b5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="733b5-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="733b5-110">Child Elements</span></span>

|<span data-ttu-id="733b5-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="733b5-111">Element</span></span>|<span data-ttu-id="733b5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="733b5-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="733b5-113">Elemento Alignment para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="733b5-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="733b5-114">Optional element.</span></span><br /><br /> <span data-ttu-id="733b5-115">Define como os dados em uma coluna da linha são exibidos.</span><span class="sxs-lookup"><span data-stu-id="733b5-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="733b5-116">Elemento FormatString para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="733b5-117">Especifica um padrão de formato que é usado para formatar os dados na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="733b5-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="733b5-118">Elemento PropertyName para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="733b5-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="733b5-119">Optional element.</span></span><br /><br /> <span data-ttu-id="733b5-120">Especifica o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="733b5-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="733b5-121">Elemento ScriptBlock para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="733b5-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="733b5-122">Optional element.</span></span><br /><br /> <span data-ttu-id="733b5-123">Especifica o script cujo valor é exibido na coluna de uma linha.</span><span class="sxs-lookup"><span data-stu-id="733b5-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="733b5-124">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="733b5-124">Parent Elements</span></span>

|<span data-ttu-id="733b5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="733b5-125">Element</span></span>|<span data-ttu-id="733b5-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="733b5-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="733b5-127">Elemento TableColumnItems para TableControlEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="733b5-128">Define as propriedades ou os scripts cujos valores são exibidos na linha.</span><span class="sxs-lookup"><span data-stu-id="733b5-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="733b5-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="733b5-129">Remarks</span></span>

<span data-ttu-id="733b5-130">Você pode especificar uma propriedade de um objeto ou um script em cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="733b5-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="733b5-131">Se nenhum elemento filho for especificado, o item será um espaço reservado e nenhum dado será exibido.</span><span class="sxs-lookup"><span data-stu-id="733b5-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="733b5-132">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="733b5-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="733b5-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="733b5-133">Example</span></span>

<span data-ttu-id="733b5-134">Este exemplo mostra um `TableColumnItem` elemento que exibe o valor `Status` da Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="733b5-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="733b5-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="733b5-135">See Also</span></span>

[<span data-ttu-id="733b5-136">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="733b5-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="733b5-137">Elemento Alignment para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="733b5-138">Elemento TableColumnItems (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="733b5-139">Elemento FormatString para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="733b5-140">Elemento PropertyName para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="733b5-141">Elemento ScriptBlock para TableColumnItem para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="733b5-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="733b5-142">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="733b5-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
