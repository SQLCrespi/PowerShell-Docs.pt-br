---
title: Criando uma exibição ampla | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0cf6a35201c47e4b12dd160191570eccec3427ef
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786128"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="d79c1-102">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d79c1-102">Creating a Wide View</span></span>

<span data-ttu-id="d79c1-103">Uma exibição ampla exibe um único valor para cada objeto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d79c1-103">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="d79c1-104">O valor exibido pode ser o valor de uma propriedade de objeto .NET ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="d79c1-104">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="d79c1-105">Por padrão, não há nenhum rótulo ou cabeçalho para essa exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-105">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="d79c1-106">Uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d79c1-106">A Wide View Display</span></span>

<span data-ttu-id="d79c1-107">O exemplo a seguir mostra como o Windows PowerShell exibe o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) que é retornado pelo cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) quando sua saída é canalizada para o cmdlet [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-107">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="d79c1-108">(Por padrão, o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) retorna um modo de exibição de tabela.) Neste exemplo, as duas colunas são usadas para exibir o nome do processo para cada objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-108">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="d79c1-109">O nome da Propriedade do objeto não é exibido, somente o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="d79c1-109">The name of the object's property is not displayed, only the value of the property.</span></span>

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a><span data-ttu-id="d79c1-110">Definindo a exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d79c1-110">Defining the Wide View</span></span>

<span data-ttu-id="d79c1-111">O XML a seguir mostra o esquema de exibição ampla para o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-111">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

<span data-ttu-id="d79c1-112">Os seguintes elementos XML são usados para definir uma exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="d79c1-112">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="d79c1-113">O elemento [View](./view-element-format.md) é o elemento pai da exibição larga.</span><span class="sxs-lookup"><span data-stu-id="d79c1-113">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="d79c1-114">(Este é o mesmo elemento pai para a tabela, lista e exibições de controle personalizado.)</span><span class="sxs-lookup"><span data-stu-id="d79c1-114">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="d79c1-115">O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="d79c1-116">Esse elemento é necessário para todas as exibições.</span><span class="sxs-lookup"><span data-stu-id="d79c1-116">This element is required for all views.</span></span>

- <span data-ttu-id="d79c1-117">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="d79c1-118">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d79c1-118">This element is required.</span></span>

- <span data-ttu-id="d79c1-119">O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="d79c1-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="d79c1-120">Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="d79c1-121">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-121">This element is optional.</span></span>

- <span data-ttu-id="d79c1-122">Os elementos [Controls](./controls-element-for-view-format.md) definem os controles personalizados que são definidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="d79c1-122">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="d79c1-123">Os controles oferecem uma maneira de especificar como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="d79c1-124">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-124">This element is optional.</span></span> <span data-ttu-id="d79c1-125">Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d79c1-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="d79c1-126">Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="d79c1-127">O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-127">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="d79c1-128">No exemplo anterior, a exibição foi projetada para exibir a propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-128">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="d79c1-129">Para obter um exemplo de um arquivo de formatação completo que define uma exibição larga simples, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-129">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="d79c1-130">Fornecendo definições para sua ampla exibição</span><span class="sxs-lookup"><span data-stu-id="d79c1-130">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="d79c1-131">Exibições amplas podem fornecer uma ou mais definições usando os elementos filho do elemento [WideControl](./widecontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-131">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="d79c1-132">Normalmente, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="d79c1-133">No exemplo a seguir, a exibição fornece uma única definição que exibe o valor da propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-133">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="d79c1-134">Uma exibição ampla pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).</span><span class="sxs-lookup"><span data-stu-id="d79c1-134">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="d79c1-135">Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="d79c1-135">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="d79c1-136">O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-136">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="d79c1-137">O elemento [AutoSize](./autosize-element-for-widecontrol-format.md) especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-137">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="d79c1-138">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-138">This element is optional.</span></span>

- <span data-ttu-id="d79c1-139">O elemento [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) especifica o número de colunas exibidas na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="d79c1-139">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="d79c1-140">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-140">This element is optional.</span></span>

- <span data-ttu-id="d79c1-141">O elemento [WideEntries](./wideentries-element-for-widecontrol-format.md) fornece as definições da exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-141">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="d79c1-142">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-142">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="d79c1-143">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d79c1-143">This element is required.</span></span>

- <span data-ttu-id="d79c1-144">O elemento [WideEntry](./wideentry-element-for-widecontrol-format.md) fornece uma definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-144">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="d79c1-145">Pelo menos um [WideEntry](./wideentry-element-for-widecontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="d79c1-145">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="d79c1-146">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-146">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="d79c1-147">O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) especifica os objetos que são exibidos por uma definição específica.</span><span class="sxs-lookup"><span data-stu-id="d79c1-147">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="d79c1-148">Esse elemento é opcional e só é necessário quando você define vários elementos [WideEntry](./wideentry-element-for-widecontrol-format.md) que exibem objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d79c1-148">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="d79c1-149">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-149">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="d79c1-150">Ao contrário de outros tipos de exibições, um controle amplo pode exibir apenas um item.</span><span class="sxs-lookup"><span data-stu-id="d79c1-150">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="d79c1-151">O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-151">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="d79c1-152">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-152">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="d79c1-153">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-153">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="d79c1-154">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-154">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="d79c1-155">O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-155">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="d79c1-156">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-156">This element is optional.</span></span>

<span data-ttu-id="d79c1-157">Para obter um exemplo de um arquivo de formatação completo que define uma ampla definição de exibição, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-157">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="d79c1-158">Definindo os objetos que usam a exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d79c1-158">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="d79c1-159">Há duas maneiras de definir quais objetos .NET usam a exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="d79c1-159">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="d79c1-160">Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) para definir quais objetos são exibidos por uma definição específica da exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-160">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="d79c1-161">Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-161">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="d79c1-162">O exemplo a seguir mostra como definir os objetos que são exibidos pela exibição ampla usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-162">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="d79c1-163">Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.</span><span class="sxs-lookup"><span data-stu-id="d79c1-163">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="d79c1-164">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="d79c1-164">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="d79c1-165">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="d79c1-165">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="d79c1-166">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-166">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="d79c1-167">O nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="d79c1-167">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="d79c1-168">Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-168">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="d79c1-169">Para obter um exemplo de um arquivo de formatação completo, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-169">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="d79c1-170">O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-170">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="d79c1-171">Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição ampla e uma exibição de tabela para os mesmos objetos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-171">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="d79c1-172">Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-172">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="d79c1-173">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="d79c1-173">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="d79c1-174">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="d79c1-174">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="d79c1-175">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-175">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="d79c1-176">Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-176">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="d79c1-177">O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição ampla usando o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d79c1-177">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="d79c1-178">Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="d79c1-178">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="d79c1-179">Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-179">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="d79c1-180">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="d79c1-180">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="d79c1-181">O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) define quais objetos são exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-181">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="d79c1-182">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-182">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="d79c1-183">Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="d79c1-183">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="d79c1-184">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-184">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="d79c1-185">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-185">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="d79c1-186">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-186">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="d79c1-187">O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="d79c1-187">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="d79c1-188">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="d79c1-189">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-189">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="d79c1-190">Exibindo grupos de objetos em uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d79c1-190">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="d79c1-191">Você pode separar os objetos que são exibidos pela exibição ampla em grupos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-191">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="d79c1-192">Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-192">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="d79c1-193">No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-193">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="d79c1-194">Os seguintes elementos XML são usados para definir quando um grupo é iniciado:</span><span class="sxs-lookup"><span data-stu-id="d79c1-194">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="d79c1-195">O elemento [GroupBy](./groupby-element-for-view-format.md) define a propriedade ou o script que inicia o novo grupo e define como o grupo é exibido.</span><span class="sxs-lookup"><span data-stu-id="d79c1-195">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="d79c1-196">O elemento [PropertyName](./propertyname-element-for-groupby-format.md) especifica a propriedade que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-196">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="d79c1-197">Você deve especificar uma propriedade ou um script para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-197">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="d79c1-198">O elemento [scriptblock](./scriptblock-element-for-groupby-format.md) especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="d79c1-198">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="d79c1-199">Você deve especificar um script ou uma propriedade para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-199">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="d79c1-200">O elemento [Label](./label-element-for-groupby-format.md) define um rótulo que é exibido no início de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="d79c1-200">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="d79c1-201">Além do texto especificado por esse elemento, o Windows PowerShell exibe o valor que disparou o novo grupo e adiciona uma linha em branco antes e depois do rótulo.</span><span class="sxs-lookup"><span data-stu-id="d79c1-201">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="d79c1-202">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-202">This element is optional.</span></span>

- <span data-ttu-id="d79c1-203">O elemento [CustomControl](./customcontrol-element-for-groupby-format.md) define um controle que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-203">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="d79c1-204">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-204">This element is optional.</span></span>

- <span data-ttu-id="d79c1-205">O elemento [CustomControlName](./customcontrolname-element-for-groupby-format.md) especifica um controle comum ou de exibição que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="d79c1-205">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="d79c1-206">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="d79c1-206">This element is optional.</span></span>

<span data-ttu-id="d79c1-207">Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="d79c1-207">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="d79c1-208">Usando cadeias de caracteres de formato</span><span class="sxs-lookup"><span data-stu-id="d79c1-208">Using Format Strings</span></span>

<span data-ttu-id="d79c1-209">As cadeias de caracteres de formatação podem ser adicionadas a uma exibição ampla para definir ainda mais como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-209">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="d79c1-210">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="d79c1-210">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="d79c1-211">Os seguintes elementos XML podem ser usados para especificar um padrão de formato:</span><span class="sxs-lookup"><span data-stu-id="d79c1-211">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="d79c1-212">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-212">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="d79c1-213">O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-213">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="d79c1-214">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="d79c1-215">O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição</span><span class="sxs-lookup"><span data-stu-id="d79c1-215">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="d79c1-216">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-216">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="d79c1-217">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-217">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="d79c1-218">No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script.</span><span class="sxs-lookup"><span data-stu-id="d79c1-218">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="d79c1-219">Os scripts podem chamar qualquer método de um objeto.</span><span class="sxs-lookup"><span data-stu-id="d79c1-219">Scripts can call any method of an object.</span></span> <span data-ttu-id="d79c1-220">Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.</span><span class="sxs-lookup"><span data-stu-id="d79c1-220">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="d79c1-221">O elemento XML a seguir pode ser usado para chamar o `ToString` método:</span><span class="sxs-lookup"><span data-stu-id="d79c1-221">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="d79c1-222">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-222">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="d79c1-223">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="d79c1-223">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="d79c1-224">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d79c1-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d79c1-225">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d79c1-225">See Also</span></span>

[<span data-ttu-id="d79c1-226">Exibição ampla (Básica)</span><span class="sxs-lookup"><span data-stu-id="d79c1-226">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="d79c1-227">Exibição ampla (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="d79c1-227">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="d79c1-228">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d79c1-228">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
