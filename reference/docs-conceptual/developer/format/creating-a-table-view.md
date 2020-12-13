---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma exibição de tabela
description: Criar uma exibição de tabela
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660294"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="2edde-103">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="2edde-103">Creating a Table View</span></span>

<span data-ttu-id="2edde-104">Uma exibição de tabela exibe dados em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="2edde-104">A table view displays data in one or more columns.</span></span> <span data-ttu-id="2edde-105">Cada linha na tabela representa um objeto .NET e cada coluna da tabela representa uma propriedade do objeto ou um valor de script.</span><span class="sxs-lookup"><span data-stu-id="2edde-105">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="2edde-106">Você pode definir um modo de exibição de tabela que exibe todas as propriedades de um objeto ou um subconjunto das propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="2edde-106">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="2edde-107">Exibição de uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="2edde-107">A Table View Display</span></span>

<span data-ttu-id="2edde-108">O exemplo a seguir mostra como o Windows PowerShell exibe o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) que é retornado pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="2edde-108">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="2edde-109">Para esse objeto, o Windows PowerShell definiu um modo de exibição de tabela que exibe a `Status` propriedade, a `Name` Propriedade (essa propriedade é uma propriedade de alias para a `ServiceName` Propriedade) e a `DisplayName` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2edde-109">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="2edde-110">Cada linha na tabela representa um objeto retornado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2edde-110">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="2edde-111">Definindo a exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="2edde-111">Defining the Table View</span></span>

<span data-ttu-id="2edde-112">O XML a seguir mostra o esquema de exibição de tabela para exibir o [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="2edde-112">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="2edde-113">Você deve especificar cada propriedade que deseja exibir na exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-113">You must specify each property that you want displayed in the table view.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="2edde-114">Os seguintes elementos XML são usados para definir um modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="2edde-114">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="2edde-115">O elemento [View](./view-element-format.md) é o elemento pai da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-115">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="2edde-116">(Esse é o mesmo elemento pai para as exibições de controle de lista, largo e personalizado.)</span><span class="sxs-lookup"><span data-stu-id="2edde-116">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="2edde-117">O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="2edde-117">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="2edde-118">Esse elemento é necessário para todas as exibições.</span><span class="sxs-lookup"><span data-stu-id="2edde-118">This element is required for all views.</span></span>

- <span data-ttu-id="2edde-119">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="2edde-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="2edde-120">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2edde-120">This element is required.</span></span>

- <span data-ttu-id="2edde-121">O elemento [GroupBy](./groupby-element-for-view-format.md) (não mostrado neste exemplo) define quando um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-121">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="2edde-122">Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado.</span><span class="sxs-lookup"><span data-stu-id="2edde-122">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="2edde-123">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-123">This element is optional.</span></span>

- <span data-ttu-id="2edde-124">O elemento [Controls](./controls-element-for-view-format.md) (não mostrado neste exemplo) define os controles personalizados que são definidos pelo modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-124">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="2edde-125">Os controles oferecem uma maneira de especificar como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="2edde-125">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="2edde-126">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-126">This element is optional.</span></span> <span data-ttu-id="2edde-127">Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="2edde-127">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="2edde-128">Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2edde-128">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="2edde-129">O elemento [HideTableHeaders](./hidetableheaders-element-format.md) (não mostrado neste exemplo) especifica que a tabela não mostrará nenhum rótulo na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-129">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="2edde-130">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-130">This element is optional.</span></span>

- <span data-ttu-id="2edde-131">O elemento [TableControl](./tablecontrol-element-format.md) que define as informações de cabeçalho e linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-131">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="2edde-132">Semelhante a todas as outras exibições, um modo de exibição de tabela pode exibir os valores de propriedades de objeto ou valores gerados por scripts.</span><span class="sxs-lookup"><span data-stu-id="2edde-132">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="2edde-133">Definindo cabeçalhos de coluna</span><span class="sxs-lookup"><span data-stu-id="2edde-133">Defining Column Headers</span></span>

1. <span data-ttu-id="2edde-134">O elemento [TableHeaders](./tableheaders-element-format.md) e seus elementos filho definem o que é exibido na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-134">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="2edde-135">O elemento [TableColumnHeader](./tablecolumnheader-element-format.md) define o que é exibido na parte superior de uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-135">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="2edde-136">Especifique esses elementos na ordem em que você deseja que os cabeçalhos sejam exibidos.</span><span class="sxs-lookup"><span data-stu-id="2edde-136">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="2edde-137">Não há nenhum limite para o número desse elemento que você pode usar, mas o número de elementos [TableColumnHeader](./tablecolumnheader-element-format.md) no modo de exibição de tabela deve ser igual ao número de elementos [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) que você usa.</span><span class="sxs-lookup"><span data-stu-id="2edde-137">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="2edde-138">O elemento [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica o texto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-138">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="2edde-139">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-139">This element is optional.</span></span>

4. <span data-ttu-id="2edde-140">O elemento [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica a largura (em caracteres) da coluna.</span><span class="sxs-lookup"><span data-stu-id="2edde-140">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="2edde-141">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-141">This element is optional.</span></span>

5. <span data-ttu-id="2edde-142">O elemento [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica como o rótulo é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-142">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="2edde-143">O rótulo pode ser alinhado à esquerda, à direita ou centralizado.</span><span class="sxs-lookup"><span data-stu-id="2edde-143">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="2edde-144">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-144">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="2edde-145">Definindo as linhas da tabela</span><span class="sxs-lookup"><span data-stu-id="2edde-145">Defining the Table Rows</span></span>

<span data-ttu-id="2edde-146">Exibições de tabela podem fornecer uma ou mais definições que especificam quais dados são exibidos nas linhas da tabela usando os elementos filho do elemento [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="2edde-146">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="2edde-147">Observe que você pode especificar várias definições para as linhas da tabela, mas os cabeçalhos das linhas permanecem os mesmos, independentemente de qual definição de linha é usada.</span><span class="sxs-lookup"><span data-stu-id="2edde-147">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="2edde-148">Normalmente, uma tabela terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="2edde-148">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="2edde-149">No exemplo a seguir, a exibição fornece uma única definição que exibe os valores de várias propriedades do [System. Diagnostics. Process? Displayproperty = objeto FullName](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="2edde-149">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="2edde-150">Um modo de exibição de tabela pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo) em suas linhas.</span><span class="sxs-lookup"><span data-stu-id="2edde-150">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

<span data-ttu-id="2edde-151">Os seguintes elementos XML podem ser usados para fornecer definições para uma linha:</span><span class="sxs-lookup"><span data-stu-id="2edde-151">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="2edde-152">O elemento [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) e seus elementos filho definem o que é exibido nas linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-152">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="2edde-153">O elemento [TableRowEntry](./listentry-element-for-listcontrol-format.md) fornece uma definição da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-153">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="2edde-154">Pelo menos um [TableRowEntry](./listentry-element-for-listcontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="2edde-154">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="2edde-155">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="2edde-155">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="2edde-156">O elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) especifica os objetos que são exibidos por uma definição específica.</span><span class="sxs-lookup"><span data-stu-id="2edde-156">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="2edde-157">Esse elemento é opcional e só é necessário quando você define vários elementos [TableRowEntry](./listentry-element-for-listcontrol-format.md) que exibem objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="2edde-157">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="2edde-158">O elemento [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) especifica que o texto que excede a largura da coluna é exibido na próxima linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-158">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="2edde-159">Por padrão, o texto que excede a largura da coluna é truncado.</span><span class="sxs-lookup"><span data-stu-id="2edde-159">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="2edde-160">O elemento [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) define as propriedades ou os scripts cujos valores são exibidos na linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-160">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="2edde-161">O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-161">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="2edde-162">Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-162">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="2edde-163">A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2edde-163">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="2edde-164">O elemento [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica a propriedade cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-164">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="2edde-165">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2edde-165">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="2edde-166">O elemento [scriptblock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-166">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="2edde-167">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2edde-167">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="2edde-168">O elemento [FormatString](./label-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-168">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="2edde-169">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-169">This element is optional.</span></span>

- <span data-ttu-id="2edde-170">O elemento [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica como o valor da propriedade ou do script é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-170">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="2edde-171">O valor pode ser alinhado à esquerda, à direita ou centralizado.</span><span class="sxs-lookup"><span data-stu-id="2edde-171">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="2edde-172">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="2edde-172">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="2edde-173">Definindo os objetos que usam o modo de exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="2edde-173">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="2edde-174">Há duas maneiras de definir quais objetos .NET usam o modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2edde-174">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="2edde-175">Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) para definir quais objetos são exibidos por uma definição específica da exibição.</span><span class="sxs-lookup"><span data-stu-id="2edde-175">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="2edde-176">Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="2edde-176">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="2edde-177">O exemplo a seguir mostra como definir os objetos que são exibidos pelo modo de exibição de tabela usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="2edde-177">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="2edde-178">Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.</span><span class="sxs-lookup"><span data-stu-id="2edde-178">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="2edde-179">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de tabela:</span><span class="sxs-lookup"><span data-stu-id="2edde-179">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="2edde-180">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2edde-180">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="2edde-181">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="2edde-181">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="2edde-182">O nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="2edde-182">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="2edde-183">Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="2edde-183">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="2edde-184">O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="2edde-184">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="2edde-185">Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição de lista e uma exibição de tabela para os mesmos objetos.</span><span class="sxs-lookup"><span data-stu-id="2edde-185">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="2edde-186">Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2edde-186">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="2edde-187">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="2edde-187">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="2edde-188">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2edde-188">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="2edde-189">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="2edde-189">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="2edde-190">Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="2edde-190">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="2edde-191">O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição de tabela usando o elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="2edde-191">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="2edde-192">Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="2edde-192">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="2edde-193">Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2edde-193">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2edde-194">Ao criar várias definições da exibição de tabela, não é possível especificar cabeçalhos de coluna diferentes.</span><span class="sxs-lookup"><span data-stu-id="2edde-194">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="2edde-195">Você pode especificar apenas o que é exibido nas linhas da tabela, como quais objetos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="2edde-195">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="2edde-196">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="2edde-196">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="2edde-197">O elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) define quais objetos são exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="2edde-197">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="2edde-198">O elemento [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) especifica o objeto .NET que é exibido pela definição.</span><span class="sxs-lookup"><span data-stu-id="2edde-198">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="2edde-199">Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="2edde-199">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="2edde-200">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="2edde-200">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="2edde-201">O elemento [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="2edde-201">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="2edde-202">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="2edde-202">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="2edde-203">O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="2edde-203">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="2edde-204">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="2edde-204">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="2edde-205">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2edde-205">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="2edde-206">Usando cadeias de caracteres de formato</span><span class="sxs-lookup"><span data-stu-id="2edde-206">Using Format Strings</span></span>

<span data-ttu-id="2edde-207">As cadeias de caracteres de formatação podem ser adicionadas a uma exibição para definir ainda mais como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="2edde-207">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="2edde-208">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2edde-208">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="2edde-209">Os seguintes elementos XML podem ser usados para especificar um padrão de formato:</span><span class="sxs-lookup"><span data-stu-id="2edde-209">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="2edde-210">O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-210">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="2edde-211">Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-211">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="2edde-212">A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2edde-212">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="2edde-213">O elemento [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica a propriedade cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-213">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="2edde-214">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2edde-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="2edde-215">O elemento [FormatString](./label-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido.</span><span class="sxs-lookup"><span data-stu-id="2edde-215">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="2edde-216">No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script.</span><span class="sxs-lookup"><span data-stu-id="2edde-216">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="2edde-217">Os scripts podem chamar qualquer método de um objeto.</span><span class="sxs-lookup"><span data-stu-id="2edde-217">Scripts can call any method of an object.</span></span> <span data-ttu-id="2edde-218">Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.</span><span class="sxs-lookup"><span data-stu-id="2edde-218">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="2edde-219">O elemento XML a seguir pode ser usado para chamar o `ToString` método:</span><span class="sxs-lookup"><span data-stu-id="2edde-219">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="2edde-220">O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-220">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="2edde-221">Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-221">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="2edde-222">A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2edde-222">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="2edde-223">O elemento [scriptblock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="2edde-223">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="2edde-224">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2edde-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="2edde-225">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2edde-225">See Also</span></span>

[<span data-ttu-id="2edde-226">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2edde-226">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
