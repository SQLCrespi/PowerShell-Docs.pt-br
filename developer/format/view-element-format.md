---
title: Exibir o elemento (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083715"
---
# <a name="view-element-format"></a><span data-ttu-id="e814c-102">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-102">View Element (Format)</span></span>

<span data-ttu-id="e814c-103">Define uma exibição que exibe um ou mais objetos do .NET.</span><span class="sxs-lookup"><span data-stu-id="e814c-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="e814c-104">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="e814c-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="e814c-105">Elemento de exibição de ViewDefinitions elemento (formato) de (formato) do elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e814c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e814c-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e814c-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="e814c-107">Attributes and Elements</span></span>

<span data-ttu-id="e814c-108">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `View` elemento.</span><span class="sxs-lookup"><span data-stu-id="e814c-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="e814c-109">Você deve especificar apenas um dos elementos de filhos do controle, e você deve especificar o nome da exibição e os objetos que usam o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="e814c-110">Definindo controles personalizados, como agrupar objetos, e especifica se o modo de exibição é out-of-band são opcionais.</span><span class="sxs-lookup"><span data-stu-id="e814c-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="e814c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e814c-111">Attributes</span></span>

<span data-ttu-id="e814c-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e814c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e814c-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e814c-113">Child Elements</span></span>

|<span data-ttu-id="e814c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e814c-114">Element</span></span>|<span data-ttu-id="e814c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e814c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e814c-116">Elemento de controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="e814c-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-118">Define um conjunto de controles que podem ser referenciados por seu nome de dentro da exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="e814c-119">Elemento CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="e814c-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-121">Define um formato de controle personalizado para o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="e814c-122">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e814c-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-123">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-124">Define como os membros dos objetos .NET são agrupados.</span><span class="sxs-lookup"><span data-stu-id="e814c-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="e814c-125">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="e814c-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-126">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-127">Define um formato de lista para o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="e814c-128">Elemento de nome para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="e814c-129">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="e814c-129">Required element.</span></span><br /><br /> <span data-ttu-id="e814c-130">Especifica o nome usado para referenciar o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="e814c-131">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="e814c-132">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-132">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-133">Define um formato de tabela para o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="e814c-134">Elemento ViewSelectedBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="e814c-135">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="e814c-135">Required element.</span></span><br /><br /> <span data-ttu-id="e814c-136">Define os objetos do .NET que essa exibição exibe.</span><span class="sxs-lookup"><span data-stu-id="e814c-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="e814c-137">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="e814c-138">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e814c-138">Optional element.</span></span><br /><br /> <span data-ttu-id="e814c-139">Define uma ampla (único valor) formato de lista para o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e814c-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e814c-140">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e814c-140">Parent Elements</span></span>

|<span data-ttu-id="e814c-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="e814c-141">Element</span></span>|<span data-ttu-id="e814c-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="e814c-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e814c-143">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="e814c-144">Define os modos de exibição usados para exibir os objetos.</span><span class="sxs-lookup"><span data-stu-id="e814c-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e814c-145">Comentários</span><span class="sxs-lookup"><span data-stu-id="e814c-145">Remarks</span></span>

<span data-ttu-id="e814c-146">Para obter mais informações sobre os componentes de diferentes modos de exibição e controles personalizados, consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e814c-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="e814c-147">Componentes de exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="e814c-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="e814c-148">Componentes de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="e814c-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="e814c-149">Componentes de exibição ampla</span><span class="sxs-lookup"><span data-stu-id="e814c-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="e814c-150">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="e814c-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="e814c-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e814c-151">Example</span></span>

<span data-ttu-id="e814c-152">Este exemplo mostra uma `View` elemento que define uma exibição de tabela para o [ServiceProcess](/dotnet/api/System.ServiceProcess.ServiceController) objeto.</span><span class="sxs-lookup"><span data-stu-id="e814c-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e814c-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e814c-153">See Also</span></span>

[<span data-ttu-id="e814c-154">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="e814c-155">Elemento de nome para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="e814c-156">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="e814c-157">Elemento de controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="e814c-158">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e814c-159">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="e814c-160">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="e814c-161">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="e814c-162">Elemento CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e814c-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="e814c-163">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e814c-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
