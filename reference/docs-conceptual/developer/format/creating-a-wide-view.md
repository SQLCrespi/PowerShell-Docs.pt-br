---
ms.date: 09/13/2016
ms.topic: reference
title: Criar uma exibição ampla
description: Criar uma exibição ampla
ms.openlocfilehash: 4230ef91a3612e962b2773b12e8016df6f760eae
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655601"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="fd2c4-103">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd2c4-103">Creating a Wide View</span></span>

<span data-ttu-id="fd2c4-104">Uma exibição ampla exibe um único valor para cada objeto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-104">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="fd2c4-105">O valor exibido pode ser o valor de uma propriedade de objeto .NET ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-105">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="fd2c4-106">Por padrão, não há nenhum rótulo ou cabeçalho para essa exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-106">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="fd2c4-107">Uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd2c4-107">A Wide View Display</span></span>

<span data-ttu-id="fd2c4-108">O exemplo a seguir mostra como o Windows PowerShell exibe o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) que é retornado pelo cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) quando sua saída é canalizada para o cmdlet [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-108">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="fd2c4-109">(Por padrão, o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) retorna um modo de exibição de tabela.) Neste exemplo, as duas colunas são usadas para exibir o nome do processo para cada objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-109">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="fd2c4-110">O nome da Propriedade do objeto não é exibido, somente o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-110">The name of the object's property is not displayed, only the value of the property.</span></span>

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

## <a name="defining-the-wide-view"></a><span data-ttu-id="fd2c4-111">Definindo a exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd2c4-111">Defining the Wide View</span></span>

<span data-ttu-id="fd2c4-112">O XML a seguir mostra o esquema de exibição ampla para o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-112">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="fd2c4-113">Os seguintes elementos XML são usados para definir uma exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-113">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="fd2c4-114">O elemento [View](./view-element-format.md) é o elemento pai da exibição larga.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-114">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="fd2c4-115">(Este é o mesmo elemento pai para a tabela, lista e exibições de controle personalizado.)</span><span class="sxs-lookup"><span data-stu-id="fd2c4-115">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="fd2c4-116">O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="fd2c4-117">Esse elemento é necessário para todas as exibições.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-117">This element is required for all views.</span></span>

- <span data-ttu-id="fd2c4-118">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="fd2c4-119">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-119">This element is required.</span></span>

- <span data-ttu-id="fd2c4-120">O elemento [GroupBy](./groupby-element-for-view-format.md) define quando um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-120">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="fd2c4-121">Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="fd2c4-122">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-122">This element is optional.</span></span>

- <span data-ttu-id="fd2c4-123">Os elementos [Controls](./controls-element-for-view-format.md) definem os controles personalizados que são definidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-123">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="fd2c4-124">Os controles oferecem uma maneira de especificar como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="fd2c4-125">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-125">This element is optional.</span></span> <span data-ttu-id="fd2c4-126">Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="fd2c4-127">Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="fd2c4-128">O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-128">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="fd2c4-129">No exemplo anterior, a exibição foi projetada para exibir a propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-129">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="fd2c4-130">Para obter um exemplo de um arquivo de formatação completo que define uma exibição larga simples, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-130">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="fd2c4-131">Fornecendo definições para sua ampla exibição</span><span class="sxs-lookup"><span data-stu-id="fd2c4-131">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="fd2c4-132">Exibições amplas podem fornecer uma ou mais definições usando os elementos filho do elemento [WideControl](./widecontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-132">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="fd2c4-133">Normalmente, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-133">Typically, a view will have only one definition.</span></span> <span data-ttu-id="fd2c4-134">No exemplo a seguir, a exibição fornece uma única definição que exibe o valor da propriedade [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-134">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="fd2c4-135">Uma exibição ampla pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-135">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="fd2c4-136">Os seguintes elementos XML podem ser usados para fornecer definições para uma exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-136">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="fd2c4-137">O elemento [WideControl](./widecontrol-element-format.md) e seus elementos filho definem o que é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-137">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="fd2c4-138">O elemento [AutoSize](./autosize-element-for-widecontrol-format.md) especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-138">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="fd2c4-139">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-139">This element is optional.</span></span>

- <span data-ttu-id="fd2c4-140">O elemento [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) especifica o número de colunas exibidas na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-140">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="fd2c4-141">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-141">This element is optional.</span></span>

- <span data-ttu-id="fd2c4-142">O elemento [WideEntries](./wideentries-element-for-widecontrol-format.md) fornece as definições da exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-142">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="fd2c4-143">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-143">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="fd2c4-144">Este elemento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-144">This element is required.</span></span>

- <span data-ttu-id="fd2c4-145">O elemento [WideEntry](./wideentry-element-for-widecontrol-format.md) fornece uma definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-145">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="fd2c4-146">Pelo menos um [WideEntry](./wideentry-element-for-widecontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-146">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="fd2c4-147">Na maioria dos casos, uma exibição terá apenas uma definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-147">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="fd2c4-148">O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) especifica os objetos que são exibidos por uma definição específica.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-148">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="fd2c4-149">Esse elemento é opcional e só é necessário quando você define vários elementos [WideEntry](./wideentry-element-for-widecontrol-format.md) que exibem objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-149">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="fd2c4-150">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-150">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="fd2c4-151">Ao contrário de outros tipos de exibições, um controle amplo pode exibir apenas um item.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-151">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="fd2c4-152">O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-152">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="fd2c4-153">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-153">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="fd2c4-154">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-154">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="fd2c4-155">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-155">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="fd2c4-156">O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-156">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="fd2c4-157">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-157">This element is optional.</span></span>

<span data-ttu-id="fd2c4-158">Para obter um exemplo de um arquivo de formatação completo que define uma ampla definição de exibição, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-158">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="fd2c4-159">Definindo os objetos que usam a exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd2c4-159">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="fd2c4-160">Há duas maneiras de definir quais objetos .NET usam a exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-160">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="fd2c4-161">Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) para definir quais objetos são exibidos por uma definição específica da exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-161">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="fd2c4-162">Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-162">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="fd2c4-163">O exemplo a seguir mostra como definir os objetos que são exibidos pela exibição ampla usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-163">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="fd2c4-164">Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-164">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="fd2c4-165">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-165">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="fd2c4-166">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-166">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="fd2c4-167">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-167">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="fd2c4-168">O nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-168">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="fd2c4-169">Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-169">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="fd2c4-170">Para obter um exemplo de um arquivo de formatação completo, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-170">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="fd2c4-171">O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-171">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="fd2c4-172">Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição ampla e uma exibição de tabela para os mesmos objetos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-172">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="fd2c4-173">Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-173">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="fd2c4-174">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pela exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-174">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="fd2c4-175">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição larga.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-175">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="fd2c4-176">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-176">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="fd2c4-177">Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-177">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="fd2c4-178">O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição ampla usando o elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2c4-178">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="fd2c4-179">Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-179">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="fd2c4-180">Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-180">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="fd2c4-181">Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição ampla:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-181">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="fd2c4-182">O elemento [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) define quais objetos são exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-182">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="fd2c4-183">O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o .NET que é exibido pela definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-183">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="fd2c4-184">Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-184">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="fd2c4-185">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-185">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="fd2c4-186">O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-186">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="fd2c4-187">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-187">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="fd2c4-188">O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-188">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="fd2c4-189">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="fd2c4-190">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-190">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="fd2c4-191">Exibindo grupos de objetos em uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd2c4-191">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="fd2c4-192">Você pode separar os objetos que são exibidos pela exibição ampla em grupos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-192">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="fd2c4-193">Isso não significa que você defina um grupo, somente se o Windows PowerShell iniciar um novo grupo sempre que o valor de uma propriedade ou script específico for alterado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-193">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="fd2c4-194">No exemplo a seguir, um novo grupo é iniciado sempre que o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-194">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="fd2c4-195">Os seguintes elementos XML são usados para definir quando um grupo é iniciado:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-195">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="fd2c4-196">O elemento [GroupBy](./groupby-element-for-view-format.md) define a propriedade ou o script que inicia o novo grupo e define como o grupo é exibido.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-196">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="fd2c4-197">O elemento [PropertyName](./propertyname-element-for-groupby-format.md) especifica a propriedade que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-197">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="fd2c4-198">Você deve especificar uma propriedade ou um script para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-198">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="fd2c4-199">O elemento [scriptblock](./scriptblock-element-for-groupby-format.md) especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-199">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="fd2c4-200">Você deve especificar um script ou uma propriedade para iniciar o grupo, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-200">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="fd2c4-201">O elemento [Label](./label-element-for-groupby-format.md) define um rótulo que é exibido no início de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-201">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="fd2c4-202">Além do texto especificado por esse elemento, o Windows PowerShell exibe o valor que disparou o novo grupo e adiciona uma linha em branco antes e depois do rótulo.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-202">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="fd2c4-203">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-203">This element is optional.</span></span>

- <span data-ttu-id="fd2c4-204">O elemento [CustomControl](./customcontrol-element-for-groupby-format.md) define um controle que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-204">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="fd2c4-205">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-205">This element is optional.</span></span>

- <span data-ttu-id="fd2c4-206">O elemento [CustomControlName](./customcontrolname-element-for-groupby-format.md) especifica um controle comum ou de exibição que é usado para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-206">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="fd2c4-207">Esse elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-207">This element is optional.</span></span>

<span data-ttu-id="fd2c4-208">Para obter um exemplo de um arquivo de formatação completo que define grupos, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c4-208">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="fd2c4-209">Usando cadeias de caracteres de formato</span><span class="sxs-lookup"><span data-stu-id="fd2c4-209">Using Format Strings</span></span>

<span data-ttu-id="fd2c4-210">As cadeias de caracteres de formatação podem ser adicionadas a uma exibição ampla para definir ainda mais como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-210">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="fd2c4-211">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-211">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="fd2c4-212">Os seguintes elementos XML podem ser usados para especificar um padrão de formato:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-212">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="fd2c4-213">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-213">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="fd2c4-214">O elemento [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) especifica a propriedade cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-214">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="fd2c4-215">Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-215">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="fd2c4-216">O elemento [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição</span><span class="sxs-lookup"><span data-stu-id="fd2c4-216">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="fd2c4-217">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-217">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="fd2c4-218">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-218">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="fd2c4-219">No exemplo a seguir, o `ToString` método é chamado para formatar o valor do script.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-219">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="fd2c4-220">Os scripts podem chamar qualquer método de um objeto.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-220">Scripts can call any method of an object.</span></span> <span data-ttu-id="fd2c4-221">Portanto, se um objeto tiver um método, como `ToString` , que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-221">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="fd2c4-222">O elemento XML a seguir pode ser usado para chamar o `ToString` método:</span><span class="sxs-lookup"><span data-stu-id="fd2c4-222">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="fd2c4-223">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) especifica os dados que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-223">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="fd2c4-224">O elemento [scriptblock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (não mostrado) especifica o script cujo valor é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-224">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="fd2c4-225">Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd2c4-225">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd2c4-226">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd2c4-226">See Also</span></span>

[<span data-ttu-id="fd2c4-227">Exibição ampla (Básica)</span><span class="sxs-lookup"><span data-stu-id="fd2c4-227">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="fd2c4-228">Exibição ampla (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="fd2c4-228">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="fd2c4-229">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd2c4-229">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
