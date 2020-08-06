---
title: Elemento View (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785023"
---
# <a name="view-element-format"></a><span data-ttu-id="984e2-102">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-102">View Element (Format)</span></span>

<span data-ttu-id="984e2-103">Define uma exibição que exibe um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="984e2-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="984e2-104">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="984e2-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="984e2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format)</span><span class="sxs-lookup"><span data-stu-id="984e2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="984e2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="984e2-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="984e2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="984e2-107">Attributes and Elements</span></span>

<span data-ttu-id="984e2-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `View` elemento.</span><span class="sxs-lookup"><span data-stu-id="984e2-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="984e2-109">Você deve especificar um e apenas um dos elementos filho do controle, e deve especificar o nome da exibição e os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="984e2-110">Definir controles personalizados, como agrupar objetos e especificar se a exibição está fora de banda é opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="984e2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="984e2-111">Attributes</span></span>

<span data-ttu-id="984e2-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="984e2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="984e2-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="984e2-113">Child Elements</span></span>

|<span data-ttu-id="984e2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="984e2-114">Element</span></span>|<span data-ttu-id="984e2-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="984e2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="984e2-116">Elemento Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="984e2-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-118">Define um conjunto de controles que podem ser referenciados por seu nome de dentro da exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="984e2-119">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="984e2-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="984e2-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-121">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="984e2-122">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="984e2-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-123">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-124">Define como os membros dos objetos .NET são agrupados.</span><span class="sxs-lookup"><span data-stu-id="984e2-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="984e2-125">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="984e2-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-126">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-127">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="984e2-128">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="984e2-129">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="984e2-129">Required element.</span></span><br /><br /> <span data-ttu-id="984e2-130">Especifica o nome usado para fazer referência à exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="984e2-131">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="984e2-132">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-132">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-133">Define um formato de tabela para a exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="984e2-134">Elemento ViewSelectedBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="984e2-135">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="984e2-135">Required element.</span></span><br /><br /> <span data-ttu-id="984e2-136">Define os objetos .NET exibidos por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="984e2-137">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="984e2-138">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="984e2-138">Optional element.</span></span><br /><br /> <span data-ttu-id="984e2-139">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="984e2-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="984e2-140">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="984e2-140">Parent Elements</span></span>

|<span data-ttu-id="984e2-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="984e2-141">Element</span></span>|<span data-ttu-id="984e2-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="984e2-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="984e2-143">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="984e2-144">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="984e2-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="984e2-145">Comentários</span><span class="sxs-lookup"><span data-stu-id="984e2-145">Remarks</span></span>

<span data-ttu-id="984e2-146">Para obter mais informações sobre os componentes de diferentes exibições e controles personalizados, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="984e2-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="984e2-147">Componentes de exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="984e2-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="984e2-148">Componentes de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="984e2-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="984e2-149">Componentes de exibição ampla</span><span class="sxs-lookup"><span data-stu-id="984e2-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="984e2-150">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="984e2-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="984e2-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="984e2-151">Example</span></span>

<span data-ttu-id="984e2-152">Este exemplo mostra um `View` elemento que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="984e2-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="984e2-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="984e2-153">See Also</span></span>

[<span data-ttu-id="984e2-154">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="984e2-155">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="984e2-156">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="984e2-157">Elemento Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="984e2-158">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="984e2-159">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="984e2-160">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="984e2-161">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="984e2-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="984e2-162">Elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="984e2-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="984e2-163">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="984e2-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
