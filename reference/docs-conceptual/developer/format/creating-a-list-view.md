---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma exibição de lista
description: Criar uma exibição de lista
ms.openlocfilehash: c34c4fddc27d4fd016fba37fc465924d693756a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655634"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="a64c3-103">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-103">Creating a List View</span></span>

<span data-ttu-id="a64c3-104">Um modo de exibição de lista exibe dados em uma única coluna (em ordem sequencial).</span><span class="sxs-lookup"><span data-stu-id="a64c3-104">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="a64c3-105">Os dados exibidos na lista podem ser o valor de uma propriedade do .NET ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-105">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="a64c3-106">Exibição de uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-106">A List View Display</span></span>

<span data-ttu-id="a64c3-107">A saída a seguir mostra como o Windows PowerShell exibe as propriedades de [System. ServiceProcess. ServiceController? Objetos createplayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) que são retornados pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-107">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="a64c3-108">Neste exemplo, três objetos foram retornados, com cada objeto separado do objeto anterior por uma linha em branco.</span><span class="sxs-lookup"><span data-stu-id="a64c3-108">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a><span data-ttu-id="a64c3-109">Definindo o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-109">Defining the List View</span></span>

<span data-ttu-id="a64c3-110">O XML a seguir mostra o esquema de exibição de lista para exibir várias propriedades do [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-110">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="a64c3-111">Você deve especificar cada propriedade que deseja exibir na exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-111">You must specify each property that you want displayed in the list view.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

<span data-ttu-id="a64c3-112">Os seguintes elementos XML são usados para definir um modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="a64c3-112">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="a64c3-113">O elemento [View](./view-element-format.md) é o elemento pai da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-113">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="a64c3-114">(Esse é o mesmo elemento pai das exibições de controle de tabela, largo e personalizado.)</span><span class="sxs-lookup"><span data-stu-id="a64c3-114">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="a64c3-115">O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="a64c3-116">Esse elemento é necessário para todas as exibições.</span><span class="sxs-lookup"><span data-stu-id="a64c3-116">This element is required for all views.</span></span>

- <span data-ttu-id="a64c3-117">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="a64c3-118">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="a64c3-118">This element is required.</span></span>

- <span data-ttu-id="a64c3-119">O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="a64c3-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="a64c3-120">Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="a64c3-121">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-121">This element is optional.</span></span>

- <span data-ttu-id="a64c3-122">O elemento [Controls](./controls-element-for-view-format.md) define os controles personalizados que são definidos pelo modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-122">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="a64c3-123">Os controles oferecem uma maneira de especificar como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="a64c3-124">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-124">This element is optional.</span></span> <span data-ttu-id="a64c3-125">Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="a64c3-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="a64c3-126">Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="a64c3-127">O elemento [ListControl](./listcontrol-element-format.md) define o que é exibido na exibição e como ele é formatado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-127">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="a64c3-128">Semelhante a todas as outras exibições, um modo de exibição de lista pode exibir os valores de propriedades de objeto ou valores gerados pelo script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-128">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="a64c3-129">Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-129">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="a64c3-130">Fornecendo definições para o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-130">Providing Definitions for Your List View</span></span>

<span data-ttu-id="a64c3-131">As exibições de lista podem fornecer uma ou mais definições usando os elementos filho do elemento [ListControl](./listcontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-131">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="a64c3-132">Normalmente, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="a64c3-133">No exemplo a seguir, a exibição fornece uma única definição que exibe várias propriedades do [System. Diagnostics. Process? Displayproperty = objeto FullName](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-133">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="a64c3-134">Um modo de exibição de lista pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).</span><span class="sxs-lookup"><span data-stu-id="a64c3-134">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

<span data-ttu-id="a64c3-135">Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="a64c3-135">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="a64c3-136">O elemento [ListControl](./listcontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-136">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="a64c3-137">O elemento [ListEntries](./listentries-element-for-listcontrol-format.md) fornece as definições da exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-137">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="a64c3-138">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-138">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="a64c3-139">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="a64c3-139">This element is required.</span></span>

- <span data-ttu-id="a64c3-140">O elemento [ListEntry](./listentry-element-for-listcontrol-format.md) fornece uma definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-140">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="a64c3-141">Pelo menos um [ListEntry](./listentry-element-for-listcontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="a64c3-141">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="a64c3-142">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-142">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="a64c3-143">O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) especifica os objetos que são exibidos por uma definição específica.</span><span class="sxs-lookup"><span data-stu-id="a64c3-143">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="a64c3-144">Esse elemento é opcional e só é necessário quando você define vários elementos [ListEntry](./listentry-element-for-listcontrol-format.md) que exibem objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a64c3-144">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="a64c3-145">O elemento [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) especifica as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-145">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="a64c3-146">O elemento [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) especifica uma propriedade ou um script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-146">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="a64c3-147">Um modo de exibição de lista deve especificar pelo menos uma propriedade ou script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-147">A list view must specify at least one property or script.</span></span> <span data-ttu-id="a64c3-148">Não há nenhum limite máximo para o número de linhas que podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="a64c3-148">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="a64c3-149">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="a64c3-149">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="a64c3-150">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-150">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="a64c3-151">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="a64c3-151">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="a64c3-152">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-152">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="a64c3-153">O elemento [Label](./label-element-for-listitem-for-listcontrol-format.md) especifica o rótulo que é exibido à esquerda da propriedade ou do valor do script na linha.</span><span class="sxs-lookup"><span data-stu-id="a64c3-153">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="a64c3-154">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-154">This element is optional.</span></span> <span data-ttu-id="a64c3-155">Se um rótulo não for especificado, o nome da propriedade ou do script será exibido.</span><span class="sxs-lookup"><span data-stu-id="a64c3-155">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="a64c3-156">Para obter um exemplo completo, consulte [exibição de lista (rótulos)](./list-view-labels.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-156">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="a64c3-157">O elemento [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) especifica uma condição que deve existir para que a linha seja exibida.</span><span class="sxs-lookup"><span data-stu-id="a64c3-157">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="a64c3-158">Para obter mais informações sobre como adicionar condições ao modo de exibição de lista, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-158">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="a64c3-159">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-159">This element is optional.</span></span>

- <span data-ttu-id="a64c3-160">O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão que é usado para exibir o valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-160">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="a64c3-161">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-161">This element is optional.</span></span>

<span data-ttu-id="a64c3-162">Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-162">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="a64c3-163">Definindo os objetos que usam o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-163">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="a64c3-164">Há duas maneiras de definir quais objetos .NET usam o modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-164">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="a64c3-165">Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) para definir quais objetos são exibidos por uma definição específica da exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-165">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="a64c3-166">Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-166">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="a64c3-167">O exemplo a seguir mostra como definir os objetos que são exibidos pelo modo de exibição de lista usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-167">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="a64c3-168">Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.</span><span class="sxs-lookup"><span data-stu-id="a64c3-168">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="a64c3-169">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="a64c3-169">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="a64c3-170">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-170">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="a64c3-171">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-171">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="a64c3-172">O nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="a64c3-172">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="a64c3-173">Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-173">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="a64c3-174">Para obter um exemplo de um arquivo de formatação completo, consulte [exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-174">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="a64c3-175">O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-175">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="a64c3-176">Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição de lista e uma exibição de tabela para os mesmos objetos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-176">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="a64c3-177">Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-177">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="a64c3-178">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="a64c3-178">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="a64c3-179">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a64c3-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="a64c3-180">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-180">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="a64c3-181">Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-181">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="a64c3-182">O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição de lista usando o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a64c3-182">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="a64c3-183">Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="a64c3-183">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="a64c3-184">Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-184">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="a64c3-185">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="a64c3-185">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="a64c3-186">O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) define quais objetos são exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-186">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="a64c3-187">O elemento [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) especifica o objeto .NET que é exibido pela definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-187">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="a64c3-188">Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="a64c3-188">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="a64c3-189">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="a64c3-190">O elemento [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-190">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="a64c3-191">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-191">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="a64c3-192">O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="a64c3-192">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="a64c3-193">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-193">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="a64c3-194">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-194">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="a64c3-195">Exibindo grupos de objetos em um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="a64c3-195">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="a64c3-196">Você pode separar os objetos que são exibidos pelo modo de exibição de lista em grupos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-196">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="a64c3-197">Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-197">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="a64c3-198">No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-198">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="a64c3-199">Os seguintes elementos XML são usados para definir quando um grupo é iniciado:</span><span class="sxs-lookup"><span data-stu-id="a64c3-199">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="a64c3-200">O elemento [GroupBy](./groupby-element-for-view-format.md) define a propriedade ou o script que inicia o novo grupo e define como o grupo é exibido.</span><span class="sxs-lookup"><span data-stu-id="a64c3-200">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="a64c3-201">O elemento [PropertyName](./propertyname-element-for-groupby-format.md) especifica a propriedade que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-201">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="a64c3-202">Você deve especificar uma propriedade ou um script para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-202">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="a64c3-203">O elemento [scriptblock](./scriptblock-element-for-groupby-format.md) especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="a64c3-203">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="a64c3-204">Você deve especificar um script ou uma propriedade para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-204">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="a64c3-205">O elemento [Label](./label-element-for-groupby-format.md) define um rótulo que é exibido no início de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="a64c3-205">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="a64c3-206">Além do texto especificado por esse elemento, o Windows PowerShell exibe o valor que disparou o novo grupo e adiciona uma linha em branco antes e depois do rótulo.</span><span class="sxs-lookup"><span data-stu-id="a64c3-206">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="a64c3-207">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-207">This element is optional.</span></span>

- <span data-ttu-id="a64c3-208">O elemento [CustomControl](./customcontrol-element-for-groupby-format.md) define um controle que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-208">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="a64c3-209">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-209">This element is optional.</span></span>

- <span data-ttu-id="a64c3-210">O elemento [CustomControlName](./customcontrolname-element-for-groupby-format.md) especifica um controle comum ou de exibição que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="a64c3-210">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="a64c3-211">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a64c3-211">This element is optional.</span></span>

<span data-ttu-id="a64c3-212">Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [modo de exibição de lista (GroupBy)](./list-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="a64c3-212">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="a64c3-213">Usando cadeias de caracteres de formato</span><span class="sxs-lookup"><span data-stu-id="a64c3-213">Using Format Strings</span></span>

<span data-ttu-id="a64c3-214">As cadeias de caracteres de formatação podem ser adicionadas a uma exibição para definir ainda mais como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-214">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="a64c3-215">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a64c3-215">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="a64c3-216">Os seguintes elementos XML podem ser usados para especificar um padrão de formato:</span><span class="sxs-lookup"><span data-stu-id="a64c3-216">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="a64c3-217">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-217">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="a64c3-218">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-218">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="a64c3-219">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-219">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="a64c3-220">O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-220">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="a64c3-221">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-221">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="a64c3-222">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-222">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="a64c3-223">No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-223">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="a64c3-224">Os scripts podem chamar qualquer método de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a64c3-224">Scripts can call any method of an object.</span></span> <span data-ttu-id="a64c3-225">Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.</span><span class="sxs-lookup"><span data-stu-id="a64c3-225">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="a64c3-226">O elemento XML a seguir pode ser usado para chamar o `ToString` método:</span><span class="sxs-lookup"><span data-stu-id="a64c3-226">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="a64c3-227">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-227">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="a64c3-228">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="a64c3-228">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="a64c3-229">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a64c3-229">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a64c3-230">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a64c3-230">See Also</span></span>

[<span data-ttu-id="a64c3-231">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a64c3-231">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
