---
title: Elemento View (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361455"
---
# <a name="view-element-format"></a><span data-ttu-id="5ac2a-102">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-102">View Element (Format)</span></span>

<span data-ttu-id="5ac2a-103">Define uma exibição que exibe um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="5ac2a-104">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="5ac2a-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ac2a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5ac2a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="5ac2a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5ac2a-107">Attributes and Elements</span></span>

<span data-ttu-id="5ac2a-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `View`.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="5ac2a-109">Você deve especificar um e apenas um dos elementos filho do controle, e deve especificar o nome da exibição e os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="5ac2a-110">Definir controles personalizados, como agrupar objetos e especificar se a exibição está fora de banda é opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ac2a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ac2a-111">Attributes</span></span>

<span data-ttu-id="5ac2a-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ac2a-113">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="5ac2a-113">Child Elements</span></span>

|<span data-ttu-id="5ac2a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ac2a-114">Element</span></span>|<span data-ttu-id="5ac2a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ac2a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ac2a-116">Elemento Controls para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="5ac2a-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-118">Define um conjunto de controles que podem ser referenciados por seu nome de dentro da exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="5ac2a-119">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="5ac2a-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-121">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="5ac2a-122">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="5ac2a-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-124">Define como os membros dos objetos .NET são agrupados.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="5ac2a-125">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="5ac2a-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-127">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="5ac2a-128">Elemento de nome para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="5ac2a-129">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-129">Required element.</span></span><br /><br /> <span data-ttu-id="5ac2a-130">Especifica o nome usado para fazer referência à exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="5ac2a-131">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="5ac2a-132">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-132">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-133">Define um formato de tabela para a exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="5ac2a-134">Elemento ViewSelectedBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="5ac2a-135">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-135">Required element.</span></span><br /><br /> <span data-ttu-id="5ac2a-136">Define os objetos .NET exibidos por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="5ac2a-137">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="5ac2a-138">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-138">Optional element.</span></span><br /><br /> <span data-ttu-id="5ac2a-139">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5ac2a-140">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="5ac2a-140">Parent Elements</span></span>

|<span data-ttu-id="5ac2a-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ac2a-141">Element</span></span>|<span data-ttu-id="5ac2a-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ac2a-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ac2a-143">Elemento ViewDefinitions (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="5ac2a-144">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="5ac2a-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5ac2a-145">Comentários</span><span class="sxs-lookup"><span data-stu-id="5ac2a-145">Remarks</span></span>

<span data-ttu-id="5ac2a-146">Para obter mais informações sobre os componentes de diferentes exibições e controles personalizados, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5ac2a-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="5ac2a-147">Componentes de exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="5ac2a-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="5ac2a-148">Componentes de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="5ac2a-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="5ac2a-149">Componentes de exibição ampla</span><span class="sxs-lookup"><span data-stu-id="5ac2a-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="5ac2a-150">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="5ac2a-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="5ac2a-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5ac2a-151">Example</span></span>

<span data-ttu-id="5ac2a-152">Este exemplo mostra um elemento `View` que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="5ac2a-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5ac2a-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ac2a-153">See Also</span></span>

[<span data-ttu-id="5ac2a-154">Elemento ViewDefinitions (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="5ac2a-155">Elemento de nome para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="5ac2a-156">Elemento ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="5ac2a-157">Elemento Controls para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="5ac2a-158">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="5ac2a-159">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="5ac2a-160">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="5ac2a-161">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="5ac2a-162">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ac2a-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="5ac2a-163">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ac2a-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
