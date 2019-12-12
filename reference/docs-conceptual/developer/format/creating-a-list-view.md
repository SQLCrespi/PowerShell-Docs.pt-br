---
title: Criando um modo de exibição de lista | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c7a40ca-1786-46f0-bab5-6ce229daa7ee
caps.latest.revision: 14
ms.openlocfilehash: 25d24063501196d44e0f806a55bb699c82f771ce
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368975"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="404d8-102">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-102">Creating a List View</span></span>

<span data-ttu-id="404d8-103">Um modo de exibição de lista exibe dados em uma única coluna (em ordem sequencial).</span><span class="sxs-lookup"><span data-stu-id="404d8-103">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="404d8-104">Os dados exibidos na lista podem ser o valor de uma propriedade do .NET ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="404d8-104">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="404d8-105">Exibição de uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-105">A List View Display</span></span>

<span data-ttu-id="404d8-106">A saída a seguir mostra como o Windows PowerShell exibe as propriedades de [System. ServiceProcess. ServiceController? Objetos createplayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) que são retornados pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="404d8-106">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="404d8-107">Neste exemplo, três objetos foram retornados, com cada objeto separado do objeto anterior por uma linha em branco.</span><span class="sxs-lookup"><span data-stu-id="404d8-107">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

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

## <a name="defining-the-list-view"></a><span data-ttu-id="404d8-108">Definindo o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-108">Defining the List View</span></span>

<span data-ttu-id="404d8-109">O XML a seguir mostra o esquema de exibição de lista para exibir várias propriedades do [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="404d8-109">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="404d8-110">Você deve especificar cada propriedade que deseja exibir na exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-110">You must specify each property that you want displayed in the list view.</span></span>

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

<span data-ttu-id="404d8-111">Os seguintes elementos XML são usados para definir um modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="404d8-111">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="404d8-112">O elemento [View](./view-element-format.md) é o elemento pai da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-112">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="404d8-113">(Esse é o mesmo elemento pai das exibições de controle de tabela, largo e personalizado.)</span><span class="sxs-lookup"><span data-stu-id="404d8-113">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="404d8-114">O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-114">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="404d8-115">Esse elemento é necessário para todas as exibições.</span><span class="sxs-lookup"><span data-stu-id="404d8-115">This element is required for all views.</span></span>

- <span data-ttu-id="404d8-116">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="404d8-117">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="404d8-117">This element is required.</span></span>

- <span data-ttu-id="404d8-118">O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="404d8-118">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="404d8-119">Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado.</span><span class="sxs-lookup"><span data-stu-id="404d8-119">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="404d8-120">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-120">This element is optional.</span></span>

- <span data-ttu-id="404d8-121">O elemento [Controls](./controls-element-for-view-format.md) define os controles personalizados que são definidos pelo modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-121">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="404d8-122">Os controles oferecem uma maneira de especificar como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="404d8-122">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="404d8-123">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-123">This element is optional.</span></span> <span data-ttu-id="404d8-124">Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="404d8-124">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="404d8-125">Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-125">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="404d8-126">O elemento [ListControl](./listcontrol-element-format.md) define o que é exibido na exibição e como ele é formatado.</span><span class="sxs-lookup"><span data-stu-id="404d8-126">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="404d8-127">Semelhante a todas as outras exibições, um modo de exibição de lista pode exibir os valores de propriedades de objeto ou valores gerados pelo script.</span><span class="sxs-lookup"><span data-stu-id="404d8-127">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="404d8-128">Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-128">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="404d8-129">Fornecendo definições para o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-129">Providing Definitions for Your List View</span></span>

<span data-ttu-id="404d8-130">As exibições de lista podem fornecer uma ou mais definições usando os elementos filho do elemento [ListControl](./listcontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="404d8-130">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="404d8-131">Normalmente, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-131">Typically, a view will have only one definition.</span></span> <span data-ttu-id="404d8-132">No exemplo a seguir, a exibição fornece uma única definição que exibe várias propriedades do [System. Diagnostics. Process? Displayproperty = objeto FullName](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="404d8-132">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="404d8-133">Um modo de exibição de lista pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).</span><span class="sxs-lookup"><span data-stu-id="404d8-133">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="404d8-134">Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="404d8-134">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="404d8-135">O elemento [ListControl](./listcontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-135">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="404d8-136">O elemento [ListEntries](./listentries-element-for-listcontrol-format.md) fornece as definições da exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-136">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="404d8-137">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-137">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="404d8-138">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="404d8-138">This element is required.</span></span>

- <span data-ttu-id="404d8-139">O elemento [ListEntry](./listentry-element-for-listcontrol-format.md) fornece uma definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-139">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="404d8-140">Pelo menos um [ListEntry](./listentry-element-for-listcontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="404d8-140">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="404d8-141">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-141">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="404d8-142">O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) especifica os objetos que são exibidos por uma definição específica.</span><span class="sxs-lookup"><span data-stu-id="404d8-142">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="404d8-143">Esse elemento é opcional e só é necessário quando você define vários elementos [ListEntry](./listentry-element-for-listcontrol-format.md) que exibem objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="404d8-143">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="404d8-144">O elemento [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) especifica as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-144">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="404d8-145">O elemento [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) especifica uma propriedade ou um script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-145">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="404d8-146">Um modo de exibição de lista deve especificar pelo menos uma propriedade ou script.</span><span class="sxs-lookup"><span data-stu-id="404d8-146">A list view must specify at least one property or script.</span></span> <span data-ttu-id="404d8-147">Não há nenhum limite máximo para o número de linhas que podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="404d8-147">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="404d8-148">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="404d8-148">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="404d8-149">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-149">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="404d8-150">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="404d8-150">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="404d8-151">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-151">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="404d8-152">O elemento [Label](./label-element-for-listitem-for-listcontrol-format.md) especifica o rótulo que é exibido à esquerda da propriedade ou do valor do script na linha.</span><span class="sxs-lookup"><span data-stu-id="404d8-152">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="404d8-153">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-153">This element is optional.</span></span> <span data-ttu-id="404d8-154">Se um rótulo não for especificado, o nome da propriedade ou do script será exibido.</span><span class="sxs-lookup"><span data-stu-id="404d8-154">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="404d8-155">Para obter um exemplo completo, consulte [exibição de lista (rótulos)](./list-view-labels.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-155">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="404d8-156">O elemento [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) especifica uma condição que deve existir para que a linha seja exibida.</span><span class="sxs-lookup"><span data-stu-id="404d8-156">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="404d8-157">Para obter mais informações sobre como adicionar condições ao modo de exibição de lista, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-157">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="404d8-158">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-158">This element is optional.</span></span>

- <span data-ttu-id="404d8-159">O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão que é usado para exibir o valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="404d8-159">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="404d8-160">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-160">This element is optional.</span></span>

<span data-ttu-id="404d8-161">Para obter um exemplo de um arquivo de formatação completo que define uma exibição de lista simples, consulte [modo de exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-161">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="404d8-162">Definindo os objetos que usam o modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-162">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="404d8-163">Há duas maneiras de definir quais objetos .NET usam o modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-163">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="404d8-164">Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) para definir quais objetos são exibidos por uma definição específica da exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-164">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="404d8-165">Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="404d8-165">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="404d8-166">O exemplo a seguir mostra como definir os objetos que são exibidos pelo modo de exibição de lista usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="404d8-166">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="404d8-167">Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.</span><span class="sxs-lookup"><span data-stu-id="404d8-167">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="404d8-168">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="404d8-168">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="404d8-169">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-169">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="404d8-170">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-170">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="404d8-171">O nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="404d8-171">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="404d8-172">Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="404d8-172">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="404d8-173">Para obter um exemplo de um arquivo de formatação completo, consulte [exibição de lista (básico)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-173">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="404d8-174">O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="404d8-174">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="404d8-175">Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição de lista e uma exibição de tabela para os mesmos objetos.</span><span class="sxs-lookup"><span data-stu-id="404d8-175">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="404d8-176">Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-176">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="404d8-177">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="404d8-177">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="404d8-178">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="404d8-178">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="404d8-179">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-179">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="404d8-180">Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="404d8-180">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="404d8-181">O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição de lista usando o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="404d8-181">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="404d8-182">Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="404d8-182">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="404d8-183">Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-183">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="404d8-184">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="404d8-184">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="404d8-185">O elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) define quais objetos são exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-185">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="404d8-186">O elemento [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) especifica o objeto .NET que é exibido pela definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-186">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="404d8-187">Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="404d8-187">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="404d8-188">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="404d8-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="404d8-189">O elemento [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="404d8-189">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="404d8-190">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="404d8-190">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="404d8-191">O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="404d8-191">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="404d8-192">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="404d8-192">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="404d8-193">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-193">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="404d8-194">Exibindo grupos de objetos em um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="404d8-194">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="404d8-195">Você pode separar os objetos que são exibidos pelo modo de exibição de lista em grupos.</span><span class="sxs-lookup"><span data-stu-id="404d8-195">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="404d8-196">Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado.</span><span class="sxs-lookup"><span data-stu-id="404d8-196">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="404d8-197">No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.</span><span class="sxs-lookup"><span data-stu-id="404d8-197">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="404d8-198">Os seguintes elementos XML são usados para definir quando um grupo é iniciado:</span><span class="sxs-lookup"><span data-stu-id="404d8-198">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="404d8-199">O elemento [GroupBy](./groupby-element-for-view-format.md) define a propriedade ou o script que inicia o novo grupo e define como o grupo é exibido.</span><span class="sxs-lookup"><span data-stu-id="404d8-199">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="404d8-200">O elemento [PropertyName](./propertyname-element-for-groupby-format.md) especifica a propriedade que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="404d8-200">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="404d8-201">Você deve especificar uma propriedade ou um script para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-201">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="404d8-202">O elemento [scriptblock](./scriptblock-element-for-groupby-format.md) especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="404d8-202">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="404d8-203">Você deve especificar um script ou uma propriedade para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-203">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="404d8-204">O elemento [Label](./label-element-for-groupby-format.md) define um rótulo que é exibido no início de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="404d8-204">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="404d8-205">Além do texto especificado por esse elemento, o Windows PowerShell exibe o valor que disparou o novo grupo e adiciona uma linha em branco antes e depois do rótulo.</span><span class="sxs-lookup"><span data-stu-id="404d8-205">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="404d8-206">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-206">This element is optional.</span></span>

- <span data-ttu-id="404d8-207">O elemento [CustomControl](./customcontrol-element-for-groupby-format.md) define um controle que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="404d8-207">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="404d8-208">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-208">This element is optional.</span></span>

- <span data-ttu-id="404d8-209">O elemento [CustomControlName](./customcontrolname-element-for-groupby-format.md) especifica um controle comum ou de exibição que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="404d8-209">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="404d8-210">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="404d8-210">This element is optional.</span></span>

<span data-ttu-id="404d8-211">Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [modo de exibição de lista (GroupBy)](./list-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="404d8-211">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="404d8-212">Usando cadeias de caracteres de formato</span><span class="sxs-lookup"><span data-stu-id="404d8-212">Using Format Strings</span></span>

<span data-ttu-id="404d8-213">As cadeias de caracteres de formatação podem ser adicionadas a uma exibição para definir ainda mais como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="404d8-213">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="404d8-214">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da propriedade `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="404d8-214">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="404d8-215">Os seguintes elementos XML podem ser usados para especificar um padrão de formato:</span><span class="sxs-lookup"><span data-stu-id="404d8-215">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="404d8-216">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-216">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="404d8-217">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-217">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="404d8-218">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-218">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="404d8-219">O elemento [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-219">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="404d8-220">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-220">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="404d8-221">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-221">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="404d8-222">No exemplo a seguir, o método `ToString` é chamado para formatar o valor do script.</span><span class="sxs-lookup"><span data-stu-id="404d8-222">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="404d8-223">Os scripts podem chamar qualquer método de um objeto.</span><span class="sxs-lookup"><span data-stu-id="404d8-223">Scripts can call any method of an object.</span></span> <span data-ttu-id="404d8-224">Portanto, se um objeto tiver um método, como `ToString`, que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.</span><span class="sxs-lookup"><span data-stu-id="404d8-224">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="404d8-225">O elemento XML a seguir pode ser usado para chamar o método de `ToString`:</span><span class="sxs-lookup"><span data-stu-id="404d8-225">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="404d8-226">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-226">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="404d8-227">O elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="404d8-227">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="404d8-228">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="404d8-228">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="404d8-229">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="404d8-229">See Also</span></span>

<span data-ttu-id="404d8-230">[Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="404d8-230">[Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md)</span></span>
