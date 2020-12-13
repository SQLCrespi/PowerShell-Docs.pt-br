---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListItem para ListItems para ListControl (formato)
description: Elemento ListItem para ListItems para ListControl (formato)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666545"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="e3bf2-103">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-103">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="e3bf2-104">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-104">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="e3bf2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems de ListControl (Format) ListItem para o elemento ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3bf2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e3bf2-106">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3bf2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e3bf2-107">Attributes and Elements</span></span>

<span data-ttu-id="e3bf2-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-108">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="e3bf2-109">Somente uma propriedade ou script pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-109">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3bf2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3bf2-110">Attributes</span></span>

<span data-ttu-id="e3bf2-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e3bf2-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3bf2-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e3bf2-112">Child Elements</span></span>

|<span data-ttu-id="e3bf2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3bf2-113">Element</span></span>|<span data-ttu-id="e3bf2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3bf2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3bf2-115">Elemento FormatString para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-115">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e3bf2-117">Especifica uma cadeia de caracteres de formato que define como o valor de propriedade ou script é exibido.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-117">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="e3bf2-118">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e3bf2-120">Define a condição que deve existir para este item de lista ser usado.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-120">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="e3bf2-121">Elemento Label para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-121">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-122">Elemento opcional</span><span class="sxs-lookup"><span data-stu-id="e3bf2-122">Optional element</span></span><br /><br /> <span data-ttu-id="e3bf2-123">Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-123">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="e3bf2-124">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-124">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-125">Optional element.</span></span><br /><br /> <span data-ttu-id="e3bf2-126">Especifica a propriedade .NET cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-126">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="e3bf2-127">Elemento ScriptBlock para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-128">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-128">Optional element.</span></span><br /><br /> <span data-ttu-id="e3bf2-129">Especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-129">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3bf2-130">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e3bf2-130">Parent Elements</span></span>

|<span data-ttu-id="e3bf2-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3bf2-131">Element</span></span>|<span data-ttu-id="e3bf2-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3bf2-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3bf2-133">Elemento ListItems para controle de lista (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-133">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="e3bf2-134">Define as propriedades e os scripts cujos valores são exibidos no modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-134">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3bf2-135">Comentários</span><span class="sxs-lookup"><span data-stu-id="e3bf2-135">Remarks</span></span>

<span data-ttu-id="e3bf2-136">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e3bf2-136">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e3bf2-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e3bf2-137">Example</span></span>

<span data-ttu-id="e3bf2-138">Este exemplo mostra os elementos XML que definem três linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-138">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="e3bf2-139">As duas primeiras linhas exibem o valor de uma propriedade do .NET e a última linha exibe um valor gerado por um script.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-139">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="e3bf2-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3bf2-140">See Also</span></span>

[<span data-ttu-id="e3bf2-141">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-141">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="e3bf2-142">Elemento FormatString para ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-142">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="e3bf2-143">Elemento Label para ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-143">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="e3bf2-144">Elemento PropertyName para ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-144">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="e3bf2-145">Elemento ScriptBlock para ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-145">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="e3bf2-146">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="e3bf2-146">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e3bf2-147">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3bf2-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
