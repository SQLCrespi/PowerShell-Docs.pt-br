---
title: Visão geral do arquivo de formatação | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363685"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="503dd-102">Visão geral do arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="503dd-102">Formatting File Overview</span></span>

<span data-ttu-id="503dd-103">O formato de exibição para os objetos que são retornados por comandos (cmdlets, funções e scripts) são definidos usando arquivos de formatação (arquivos Format. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="503dd-103">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="503dd-104">Vários desses arquivos são fornecidos pelo PowerShell para definir o formato de exibição para os objetos retornados pelos comandos fornecidos pelo PowerShell, como o objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) retornado pelo cmdlet `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="503dd-104">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="503dd-105">No entanto, você também pode criar seus próprios arquivos de formatação personalizados para substituir os formatos de exibição padrão ou pode escrever um arquivo de formatação personalizado para definir a exibição de objetos retornados por seus próprios comandos.</span><span class="sxs-lookup"><span data-stu-id="503dd-105">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="503dd-106">Os arquivos de formatação não determinam os elementos de um objeto que são retornados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="503dd-106">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="503dd-107">Quando um objeto é retornado para o pipeline, todos os membros desse objeto ficam disponíveis mesmo que alguns não sejam exibidos.</span><span class="sxs-lookup"><span data-stu-id="503dd-107">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="503dd-108">O PowerShell usa os dados nesses arquivos de formatação para determinar o que é exibido e como os dados exibidos são formatados.</span><span class="sxs-lookup"><span data-stu-id="503dd-108">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="503dd-109">Os dados exibidos podem incluir as propriedades de um objeto ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="503dd-109">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="503dd-110">Os scripts serão usados se você quiser exibir algum valor que não esteja disponível diretamente das propriedades de um objeto, como adicionar o valor de duas propriedades de um objeto e, em seguida, exibir a soma como um dado.</span><span class="sxs-lookup"><span data-stu-id="503dd-110">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="503dd-111">A formatação dos dados exibidos é feita com a definição de modos de exibição para os objetos que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="503dd-111">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="503dd-112">Você pode definir uma única exibição para cada objeto, pode definir uma única exibição para vários objetos ou pode definir várias exibições para o mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="503dd-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="503dd-113">Não há nenhum limite para o número de exibições que você pode definir.</span><span class="sxs-lookup"><span data-stu-id="503dd-113">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="503dd-114">Recursos comuns de formatação de arquivos</span><span class="sxs-lookup"><span data-stu-id="503dd-114">Common Features of Formatting Files</span></span>

<span data-ttu-id="503dd-115">Cada arquivo de formatação pode definir os seguintes componentes que podem ser compartilhados entre todas as exibições definidas pelo arquivo:</span><span class="sxs-lookup"><span data-stu-id="503dd-115">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="503dd-116">Definição de configuração padrão, como se os dados exibidos nas linhas das tabelas serão exibidos na próxima linha se os dados forem maiores do que a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="503dd-116">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="503dd-117">Para obter mais informações sobre essas configurações, consulte [definindo definições de configuração comuns](./defining-common-configuration-features.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-117">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="503dd-118">Conjuntos de objetos que podem ser exibidos por qualquer uma das exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="503dd-118">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="503dd-119">Para obter mais informações sobre esses conjuntos (chamados de *conjuntos de seleção*), consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-119">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="503dd-120">Controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="503dd-120">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="503dd-121">Os controles oferecem um melhor controle sobre como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="503dd-121">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="503dd-122">Para obter mais informações sobre controles, consulte [definindo controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-122">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="503dd-123">Exibições de formatação</span><span class="sxs-lookup"><span data-stu-id="503dd-123">Formatting Views</span></span>

<span data-ttu-id="503dd-124">As exibições de formatação podem exibir objetos em formato de tabela, formato de lista, formato largo e formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="503dd-124">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="503dd-125">Para a maior parte, cada definição de formatação é descrita por um conjunto de marcas XML que descrevem a exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-125">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="503dd-126">Cada exibição contém o nome da exibição, os objetos que usam a exibição e os elementos da exibição, como as informações de coluna e linha de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="503dd-126">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="503dd-127">Exibição de tabela lista as propriedades de um objeto ou um valor de bloco de script em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="503dd-127">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="503dd-128">Cada coluna representa uma única propriedade do objeto ou um valor de script.</span><span class="sxs-lookup"><span data-stu-id="503dd-128">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="503dd-129">Você pode definir um modo de exibição de tabela que exibe todas as propriedades de um objeto, um subconjunto das propriedades de um objeto ou uma combinação de propriedades e valores de script.</span><span class="sxs-lookup"><span data-stu-id="503dd-129">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="503dd-130">Cada linha da tabela representa um objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="503dd-130">Each row of the table represents a returned object.</span></span> <span data-ttu-id="503dd-131">Criar uma exibição de tabela é muito semelhante ao quando você canaliza um objeto para o cmdlet `Format-Table`.</span><span class="sxs-lookup"><span data-stu-id="503dd-131">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="503dd-132">Para obter mais informações sobre essa exibição, consulte [exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-132">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="503dd-133">Exibição de lista lista as propriedades de um objeto ou um valor de script em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="503dd-133">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="503dd-134">Cada linha da lista exibe um rótulo opcional ou o nome da propriedade seguido pelo valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="503dd-134">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="503dd-135">Criar um modo de exibição de lista é muito semelhante a canalizar um objeto para o cmdlet `Format-List`.</span><span class="sxs-lookup"><span data-stu-id="503dd-135">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="503dd-136">Para obter mais informações sobre essa exibição, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-136">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="503dd-137">Exibição ampla lista uma única propriedade de um objeto ou um valor de script em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="503dd-137">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="503dd-138">Não há rótulo ou cabeçalho para esta exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-138">There is no label or header for this view.</span></span> <span data-ttu-id="503dd-139">Criar uma exibição ampla é muito semelhante a canalizar um objeto para o cmdlet `Format-Wide`.</span><span class="sxs-lookup"><span data-stu-id="503dd-139">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="503dd-140">Para obter mais informações sobre essa exibição, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-140">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="503dd-141">Exibição personalizada exibe uma exibição personalizável de propriedades de objeto ou valores de script que não aderem à estrutura rígida de exibições de tabela, exibições de lista ou exibições amplas.</span><span class="sxs-lookup"><span data-stu-id="503dd-141">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="503dd-142">Você pode definir uma exibição personalizada autônoma ou pode definir uma exibição personalizada que é usada por outra exibição, como uma exibição de tabela ou exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="503dd-142">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="503dd-143">Criar uma exibição personalizada é muito semelhante a canalizar um objeto para o cmdlet `Format-Custom`.</span><span class="sxs-lookup"><span data-stu-id="503dd-143">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="503dd-144">Para obter mais informações sobre essa exibição, consulte [modo de exibição personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="503dd-144">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="503dd-145">Componentes de uma exibição</span><span class="sxs-lookup"><span data-stu-id="503dd-145">Components of a View</span></span>

<span data-ttu-id="503dd-146">Os exemplos de XML a seguir mostram os componentes XML básicos de uma exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-146">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="503dd-147">Os elementos XML individuais variam de acordo com a exibição que você deseja criar, mas os componentes básicos das exibições são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="503dd-147">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="503dd-148">Para começar, cada exibição tem um elemento `Name` que especifica um nome amigável de usuário que é usado para fazer referência à exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-148">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="503dd-149">um elemento `ViewSelectedBy` que define quais objetos .NET são exibidos pela exibição e um elemento de *controle* que define a exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-149">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

<span data-ttu-id="503dd-150">Dentro do elemento Control, você pode definir um ou mais elementos *entry* .</span><span class="sxs-lookup"><span data-stu-id="503dd-150">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="503dd-151">Se você usar várias definições, deverá especificar quais objetos .NET usam cada definição.</span><span class="sxs-lookup"><span data-stu-id="503dd-151">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="503dd-152">Normalmente, apenas uma entrada, com apenas uma definição, é necessária para cada controle.</span><span class="sxs-lookup"><span data-stu-id="503dd-152">Typically only one entry, with only one definition, is needed for each control.</span></span>

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

<span data-ttu-id="503dd-153">Dentro de cada elemento de entrada de uma exibição, você especifica os elementos do *Item* que definem as propriedades ou os scripts do .net exibidos por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-153">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="503dd-154">Conforme mostrado nos exemplos anteriores, o arquivo de formatação pode conter várias exibições, uma exibição pode conter várias definições e cada definição pode conter vários itens.</span><span class="sxs-lookup"><span data-stu-id="503dd-154">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="503dd-155">Exemplo de uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="503dd-155">Example of a Table View</span></span>

<span data-ttu-id="503dd-156">O exemplo a seguir mostra as marcas XML usadas para definir um modo de exibição de tabela que contém duas colunas.</span><span class="sxs-lookup"><span data-stu-id="503dd-156">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="503dd-157">O elemento [ViewDefinitions](./viewdefinitions-element-format.md) é o elemento contêiner para todas as exibições definidas no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="503dd-157">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="503dd-158">O elemento [View](./view-element-format.md) define a tabela, lista, largura ou exibição personalizada específica.</span><span class="sxs-lookup"><span data-stu-id="503dd-158">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="503dd-159">Dentro de cada elemento [View](./view-element-format.md) , o elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição, o elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição e os elementos de controle diferentes (como o elemento `TableControl` mostrado no exemplo a seguir) definem o tipo da exibição.</span><span class="sxs-lookup"><span data-stu-id="503dd-159">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="503dd-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="503dd-160">See Also</span></span>

[<span data-ttu-id="503dd-161">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="503dd-161">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="503dd-162">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="503dd-162">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="503dd-163">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="503dd-163">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="503dd-164">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="503dd-164">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="503dd-165">Gravando um arquivo de tipos e formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="503dd-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
