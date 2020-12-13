---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento View (formato)
description: Elemento View (formato)
ms.openlocfilehash: 6fed1304d94339cc90b6ae53e06483c08d937c12
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649737"
---
# <a name="view-element-format"></a><span data-ttu-id="dedb2-103">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-103">View Element (Format)</span></span>

<span data-ttu-id="dedb2-104">Define uma exibição que exibe um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="dedb2-104">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="dedb2-105">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="dedb2-105">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="dedb2-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format)</span><span class="sxs-lookup"><span data-stu-id="dedb2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dedb2-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dedb2-107">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dedb2-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="dedb2-108">Attributes and Elements</span></span>

<span data-ttu-id="dedb2-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `View` elemento.</span><span class="sxs-lookup"><span data-stu-id="dedb2-109">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="dedb2-110">Você deve especificar um e apenas um dos elementos filho do controle, e deve especificar o nome da exibição e os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-110">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="dedb2-111">Definir controles personalizados, como agrupar objetos e especificar se a exibição está fora de banda é opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-111">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="dedb2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="dedb2-112">Attributes</span></span>

<span data-ttu-id="dedb2-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="dedb2-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dedb2-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="dedb2-114">Child Elements</span></span>

|<span data-ttu-id="dedb2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="dedb2-115">Element</span></span>|<span data-ttu-id="dedb2-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="dedb2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dedb2-117">Elemento Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-117">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="dedb2-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-118">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-119">Define um conjunto de controles que podem ser referenciados por seu nome de dentro da exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-119">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="dedb2-120">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dedb2-120">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="dedb2-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-121">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-122">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-122">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="dedb2-123">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-123">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="dedb2-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-124">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-125">Define como os membros dos objetos .NET são agrupados.</span><span class="sxs-lookup"><span data-stu-id="dedb2-125">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="dedb2-126">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-126">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="dedb2-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-127">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-128">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-128">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="dedb2-129">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-129">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="dedb2-130">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="dedb2-130">Required element.</span></span><br /><br /> <span data-ttu-id="dedb2-131">Especifica o nome usado para fazer referência à exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-131">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="dedb2-132">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-132">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="dedb2-133">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-133">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-134">Define um formato de tabela para a exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-134">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="dedb2-135">Elemento ViewSelectedBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-135">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="dedb2-136">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="dedb2-136">Required element.</span></span><br /><br /> <span data-ttu-id="dedb2-137">Define os objetos .NET exibidos por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-137">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="dedb2-138">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-138">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="dedb2-139">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="dedb2-139">Optional element.</span></span><br /><br /> <span data-ttu-id="dedb2-140">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="dedb2-140">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dedb2-141">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="dedb2-141">Parent Elements</span></span>

|<span data-ttu-id="dedb2-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="dedb2-142">Element</span></span>|<span data-ttu-id="dedb2-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="dedb2-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dedb2-144">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-144">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="dedb2-145">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="dedb2-145">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dedb2-146">Comentários</span><span class="sxs-lookup"><span data-stu-id="dedb2-146">Remarks</span></span>

<span data-ttu-id="dedb2-147">Para obter mais informações sobre os componentes de diferentes exibições e controles personalizados, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dedb2-147">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="dedb2-148">Componentes de exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="dedb2-148">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="dedb2-149">Componentes de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="dedb2-149">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="dedb2-150">Componentes de exibição ampla</span><span class="sxs-lookup"><span data-stu-id="dedb2-150">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="dedb2-151">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="dedb2-151">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="dedb2-152">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dedb2-152">Example</span></span>

<span data-ttu-id="dedb2-153">Este exemplo mostra um `View` elemento que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="dedb2-153">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="dedb2-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dedb2-154">See Also</span></span>

[<span data-ttu-id="dedb2-155">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-155">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="dedb2-156">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-156">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="dedb2-157">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-157">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="dedb2-158">Elemento Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-158">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="dedb2-159">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-159">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="dedb2-160">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-160">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="dedb2-161">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-161">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="dedb2-162">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dedb2-162">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="dedb2-163">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dedb2-163">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="dedb2-164">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="dedb2-164">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
