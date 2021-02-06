---
description: A partir do PowerShell 6, as exibições padrão para objetos são definidas no código-fonte do PowerShell.  Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: 56bac204e33c39aa6192da9e6a899f00b0a4a743
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598831"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="b751e-104">Sobre o Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="b751e-104">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="b751e-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="b751e-105">Short description</span></span>

<span data-ttu-id="b751e-106">A partir do PowerShell 6, as exibições padrão para objetos são definidas no código-fonte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-106">Beginning in PowerShell 6, the default views for objects are defined in PowerShell source code.</span></span>

<span data-ttu-id="b751e-107">Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-107">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b751e-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="b751e-108">Long description</span></span>

<span data-ttu-id="b751e-109">A partir do PowerShell 6, as exibições padrão são definidas no código-fonte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-109">Beginning in PowerShell 6, the default views are defined in PowerShell source code.</span></span> <span data-ttu-id="b751e-110">Os `Format.ps1xml` arquivos do powershell 5,1 e versões anteriores não existem no PowerShell 6 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="b751e-110">The `Format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="b751e-111">O código-fonte do PowerShell define a exibição padrão de objetos no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-111">The PowerShell source code defines the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="b751e-112">Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-112">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="b751e-113">Quando o PowerShell exibe um objeto, ele usa os dados em arquivos de formatação estruturados para determinar a exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="b751e-113">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="b751e-114">Os dados nos arquivos de formatação determinam se o objeto é renderizado em uma tabela ou em uma lista e determina quais propriedades são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="b751e-114">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="b751e-115">A formatação afeta apenas a exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-115">The formatting affects the display only.</span></span> <span data-ttu-id="b751e-116">Ele não afeta quais propriedades de objeto são passadas pelo pipeline ou como elas são passadas.</span><span class="sxs-lookup"><span data-stu-id="b751e-116">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="b751e-117">`Format.ps1xml` os arquivos não podem ser usados para personalizar o formato de saída para tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="b751e-117">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="b751e-118">Um `.ps1xml` arquivo de formatação pode definir quatro exibições diferentes de cada objeto:</span><span class="sxs-lookup"><span data-stu-id="b751e-118">A `.ps1xml` formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="b751e-119">Tabela</span><span class="sxs-lookup"><span data-stu-id="b751e-119">Table</span></span>
- <span data-ttu-id="b751e-120">List</span><span class="sxs-lookup"><span data-stu-id="b751e-120">List</span></span>
- <span data-ttu-id="b751e-121">Ampla</span><span class="sxs-lookup"><span data-stu-id="b751e-121">Wide</span></span>
- <span data-ttu-id="b751e-122">Personalizado</span><span class="sxs-lookup"><span data-stu-id="b751e-122">Custom</span></span>

<span data-ttu-id="b751e-123">Por exemplo, quando a saída de um `Get-ChildItem` comando é canalizada para um `Format-List` comando, `Format-List` o usa o modo de exibição de lista definido no código-fonte para determinar como exibir os objetos de arquivo e pasta como uma lista.</span><span class="sxs-lookup"><span data-stu-id="b751e-123">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the list view defined in the source code to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="b751e-124">Quando um arquivo de formatação inclui mais de uma exibição de um objeto, o PowerShell aplica a primeira exibição que ele encontra.</span><span class="sxs-lookup"><span data-stu-id="b751e-124">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="b751e-125">Em um `Format.ps1xml` arquivo personalizado, uma exibição é definida por um conjunto de marcas XML que descrevem o nome da exibição, o tipo de objeto ao qual ele pode ser aplicado, os cabeçalhos de coluna e as propriedades que são exibidas no corpo da exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-125">In a custom `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="b751e-126">O formato nos `Format.ps1xml` arquivos é aplicado logo antes de os dados serem apresentados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b751e-126">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="b751e-127">Criando novos arquivos XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="b751e-127">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="b751e-128">Para alterar o formato de exibição de uma exibição de objeto existente ou para adicionar exibições para novos objetos, crie seus próprios `Format.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-128">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="b751e-129">Para criar um `Format.ps1xml` arquivo para definir uma exibição personalizada, use os cmdlets [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) e [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) .</span><span class="sxs-lookup"><span data-stu-id="b751e-129">To create a `Format.ps1xml` file to define a custom view, use the [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) and [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlets.</span></span> <span data-ttu-id="b751e-130">Use um editor de texto para editar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b751e-130">Use a text editor to edit the file.</span></span> <span data-ttu-id="b751e-131">O arquivo pode ser salvo em qualquer diretório que o PowerShell possa acessar, como um subdiretório de `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="b751e-131">The file can be saved to any directory that PowerShell can access, such as a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="b751e-132">Para alterar a formatação de um modo de exibição atual, localize o modo de exibição no arquivo de formatação e, em seguida, use as marcas para alterar a exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-132">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="b751e-133">Para criar um modo de exibição para um novo tipo de objeto, crie um novo modo de exibição ou use um modo de exibição existente como modelo.</span><span class="sxs-lookup"><span data-stu-id="b751e-133">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="b751e-134">As marcas são descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="b751e-134">The tags are described in the next section.</span></span> <span data-ttu-id="b751e-135">Você pode excluir todas as outras exibições no arquivo para que as alterações sejam óbvias para qualquer pessoa que examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b751e-135">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="b751e-136">Depois de salvar as alterações, use o [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) para adicionar o novo arquivo à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-136">After you save the changes, use the [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) to add the new file to your PowerShell session.</span></span> <span data-ttu-id="b751e-137">Se você quiser que a exibição tenha precedência sobre uma exibição definida nos arquivos internos, use o parâmetro **PrependPath** .</span><span class="sxs-lookup"><span data-stu-id="b751e-137">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span> <span data-ttu-id="b751e-138">`Update-FormatData` afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b751e-138">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="b751e-139">Para fazer a alteração em todas as sessões futuras, adicione o `Update-FormatData` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-139">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-add-calendar-data-to-culture-objects"></a><span data-ttu-id="b751e-140">Exemplo: adicionar dados de calendário a objetos de cultura</span><span class="sxs-lookup"><span data-stu-id="b751e-140">Example: Add calendar data to culture objects</span></span>

<span data-ttu-id="b751e-141">Este exemplo mostra como alterar a formatação dos objetos de cultura **System. Globalization. CultureInfo** gerados pelo `Get-Culture` cmdlet na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-141">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="b751e-142">Os comandos no exemplo adicionam a propriedade **Calendar** à exibição de tabela padrão exibir objetos de cultura.</span><span class="sxs-lookup"><span data-stu-id="b751e-142">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="b751e-143">Para começar, obtenha os dados de formato do arquivo de código-fonte e crie um `Format.ps1xml` arquivo que contenha a exibição atual dos objetos de cultura.</span><span class="sxs-lookup"><span data-stu-id="b751e-143">To begin, get the format data from the source code file and create a `Format.ps1xml` file that contains the current view of the culture objects.</span></span>

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="b751e-144">Abra o `CultureInfo.Format.ps1xml` arquivo em qualquer XML ou editor de texto, como Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b751e-144">Open the `CultureInfo.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="b751e-145">O XML a seguir define as exibições do objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="b751e-145">The following XML defines the views of the **CultureInfo** object.</span></span>

<span data-ttu-id="b751e-146">O `CultureInfo.Format.ps1xml` arquivo deve ser semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="b751e-146">The `CultureInfo.Format.ps1xml` file should look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
        <TypeName>System.Globalization.CultureInfo</TypeName>
      </ViewSelectedBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader />
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>LCID</PropertyName>
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
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="b751e-147">Crie uma nova coluna para a propriedade **Calendar** adicionando um novo conjunto de `<TableColumnHeader>` marcas.</span><span class="sxs-lookup"><span data-stu-id="b751e-147">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="b751e-148">O valor da propriedade **Calendar** pode ser longo, portanto, especifique um valor de 45 caracteres como o `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="b751e-148">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

<span data-ttu-id="b751e-149">Adicione um novo item de coluna para **calendário** nas linhas da tabela usando `<TableColumnItem>` as `<PropertyName` marcas e:</span><span class="sxs-lookup"><span data-stu-id="b751e-149">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

<span data-ttu-id="b751e-150">Salve e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b751e-150">Save and close the file.</span></span> <span data-ttu-id="b751e-151">Use `Update-FormatData` para adicionar o novo arquivo de formato à sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-151">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="b751e-152">Este exemplo usa o parâmetro **PrependPath** para posicionar o novo arquivo em uma ordem de precedência mais alta do que o arquivo original.</span><span class="sxs-lookup"><span data-stu-id="b751e-152">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="b751e-153">Para obter mais informações, consulte [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="b751e-153">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="b751e-154">Para testar a alteração, digite `Get-Culture` e revise a saída que inclui a propriedade **Calendar** .</span><span class="sxs-lookup"><span data-stu-id="b751e-154">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="b751e-155">O XML em arquivos Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="b751e-155">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="b751e-156">A definição de esquema completa pode ser encontrada em [Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) no repositório de código-fonte do PowerShell no github.</span><span class="sxs-lookup"><span data-stu-id="b751e-156">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="b751e-157">A seção **ViewDefinitions** de cada `Format.ps1xml` arquivo contém as `<View>` marcas que definem cada exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-157">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="b751e-158">Uma `<View>` marca típica inclui as seguintes marcas:</span><span class="sxs-lookup"><span data-stu-id="b751e-158">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="b751e-159">`<Name>` Identifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-159">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="b751e-160">`<ViewSelectedBy>` Especifica o tipo de objeto ou tipos aos quais a exibição se aplica.</span><span class="sxs-lookup"><span data-stu-id="b751e-160">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="b751e-161">`<GroupBy>` Especifica como os itens na exibição serão combinados em grupos.</span><span class="sxs-lookup"><span data-stu-id="b751e-161">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="b751e-162">`<TableControl>`, `<ListControl>` , `<WideControl>` e `<CustomControl>` contêm as marcas que especificam como cada item será exibido.</span><span class="sxs-lookup"><span data-stu-id="b751e-162">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="b751e-163">Marca de ViewSelectedBy</span><span class="sxs-lookup"><span data-stu-id="b751e-163">ViewSelectedBy tag</span></span>

<span data-ttu-id="b751e-164">A `<ViewSelectedBy>` marca pode conter uma `<TypeName>` marca para cada tipo de objeto ao qual a exibição se aplica.</span><span class="sxs-lookup"><span data-stu-id="b751e-164">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="b751e-165">Ou, ele pode conter uma `<SelectionSetName>` marca que faz referência a um conjunto de seleção que é definido em outro lugar usando uma `<SelectionSet>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-165">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="b751e-166">Marca GroupBy</span><span class="sxs-lookup"><span data-stu-id="b751e-166">GroupBy tag</span></span>

<span data-ttu-id="b751e-167">A `<GroupBy>` marca contém uma `<PropertyName>` marca que especifica a propriedade do objeto pela qual os itens devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="b751e-167">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="b751e-168">Ele também contém uma `<Label>` marca que especifica uma cadeia de caracteres a ser usada como um rótulo para cada grupo ou uma `<CustomControlName>` marca que faz referência a um controle personalizado definido em outro lugar usando uma `<Control>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-168">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="b751e-169">A `<Control>` marca contém uma `<Name>` marca e uma `<CustomControl>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-169">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="b751e-170">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="b751e-170">TableControlTag</span></span>

<span data-ttu-id="b751e-171">A `<TableControl>` marca normalmente contém `<TableHeaders>` `<TableRowEntries>` marcas e que definem a formatação para as cabeças e linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="b751e-171">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="b751e-172">A `<TableHeaders>` marca normalmente contém `<TableColumnHeader>` marcas que contêm `<Label>` `<Width>` marcas, e `<Alignment>` .</span><span class="sxs-lookup"><span data-stu-id="b751e-172">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="b751e-173">A `<TableRowEntries>` marca contém `<TableRowEntry>` marcas para cada linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="b751e-173">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="b751e-174">A `<TableRowEntry>` marca contém uma `<TableColumnItems>` marca que contém uma `<TableColumnItem>` marca para cada coluna na linha.</span><span class="sxs-lookup"><span data-stu-id="b751e-174">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="b751e-175">Normalmente, a `<TableColumnItem>` marca contém uma `<PropertyName>` marca que identifica a propriedade do objeto a ser exibida no local definido ou uma `<ScriptBlock>` marca que contém o código de script que calcula um resultado a ser exibido no local.</span><span class="sxs-lookup"><span data-stu-id="b751e-175">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="b751e-176">Blocos de script também podem ser usados em outro lugar em locais onde os resultados calculados podem ser úteis.</span><span class="sxs-lookup"><span data-stu-id="b751e-176">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="b751e-177">A `<TableColumnItem>` marca também pode conter uma `<FormatString>` marca que especifica como a propriedade ou os resultados calculados serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="b751e-177">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="b751e-178">Marca ListControl</span><span class="sxs-lookup"><span data-stu-id="b751e-178">ListControl tag</span></span>

<span data-ttu-id="b751e-179">A `<ListControl>` marca normalmente contém uma `<ListEntries>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-179">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="b751e-180">A `<ListEntries>` marca contém uma `<ListEntry>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-180">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="b751e-181">A `<ListEntry>` marca contém uma `<ListItems>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-181">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="b751e-182">A `<ListItems>` marca contém `<ListItem>` marcas, que contêm `<PropertyName>` marcas.</span><span class="sxs-lookup"><span data-stu-id="b751e-182">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="b751e-183">As `<PropertyName>` marcas especificam a propriedade do objeto a ser exibida no local especificado na lista.</span><span class="sxs-lookup"><span data-stu-id="b751e-183">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="b751e-184">Se a seleção de exibição for definida usando um conjunto de seleção, as `<ListControl>` `<ListEntry>` marcas e também poderão conter uma `<EntrySelectedBy>` marca que contenha uma ou mais `<TypeName>` marcas.</span><span class="sxs-lookup"><span data-stu-id="b751e-184">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="b751e-185">Essas `<TypeName>` marcas especificam o tipo de objeto que a `<ListControl>` marca pretende exibir.</span><span class="sxs-lookup"><span data-stu-id="b751e-185">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="b751e-186">Marca de WideControl</span><span class="sxs-lookup"><span data-stu-id="b751e-186">WideControl tag</span></span>

<span data-ttu-id="b751e-187">A `<WideControl>` marca normalmente contém uma `<WideEntries>` marca.</span><span class="sxs-lookup"><span data-stu-id="b751e-187">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="b751e-188">A `<WideEntries>` marca contém uma ou mais `<WideEntry>` marcas.</span><span class="sxs-lookup"><span data-stu-id="b751e-188">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="b751e-189">Uma `<WideEntry>` marca normalmente contém uma `<PropertyName>` marca que especifica a propriedade a ser exibida no local especificado na exibição.</span><span class="sxs-lookup"><span data-stu-id="b751e-189">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="b751e-190">A `<PropertyName>` marca pode conter uma `<FormatString>` marca que especifica como a propriedade deve ser exibida.</span><span class="sxs-lookup"><span data-stu-id="b751e-190">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="b751e-191">Marca de CustomControl</span><span class="sxs-lookup"><span data-stu-id="b751e-191">CustomControl tag</span></span>

<span data-ttu-id="b751e-192">A `<CustomControl>` marca permite que você use um bloco de script para definir um formato.</span><span class="sxs-lookup"><span data-stu-id="b751e-192">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="b751e-193">Uma `<CustomControl>` marca normalmente contém uma `<CustomEntries>` marca que contém várias `<CustomEntry>` marcas.</span><span class="sxs-lookup"><span data-stu-id="b751e-193">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="b751e-194">Cada `<CustomEntry>` marca contém uma `<CustomItem>` marca que pode conter uma variedade de marcas que especificam o conteúdo e a formatação do local especificado na exibição, incluindo as `<Text>` marcas,, e `<Indentation>` `<ExpressionBinding>` `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="b751e-194">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="b751e-195">Rastreando o uso de arquivo XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="b751e-195">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="b751e-196">Para detectar erros no carregamento ou aplicativo de `Format.ps1xml` arquivos, use o `Trace-Command` cmdlet com qualquer um dos seguintes componentes de formato como o valor do parâmetro **Name** :</span><span class="sxs-lookup"><span data-stu-id="b751e-196">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="b751e-197">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="b751e-197">FormatFileLoading</span></span>
- <span data-ttu-id="b751e-198">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="b751e-198">FormatViewBinding</span></span>

<span data-ttu-id="b751e-199">Para obter mais informações, consulte [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) e [Get-tracename](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="b751e-199">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="b751e-200">Assinando um arquivo XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="b751e-200">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="b751e-201">Para proteger os usuários do seu `Format.ps1xml` arquivo, assine o arquivo usando uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="b751e-201">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="b751e-202">Para obter mais informações, consulte [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="b751e-202">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="b751e-203">XML de exemplo para uma exibição personalizada Format-Table</span><span class="sxs-lookup"><span data-stu-id="b751e-203">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="b751e-204">O exemplo de XML a seguir cria uma `Format-Table` exibição personalizada para os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b751e-204">The following XML sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="b751e-205">A exibição personalizada é denominada **mygciview** e adiciona a coluna **CreationTime** à tabela.</span><span class="sxs-lookup"><span data-stu-id="b751e-205">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="b751e-206">Para criar o modo de exibição personalizado, use os `Get-FormatData` `Export-FormatData` cmdlets e para gerar um `.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="b751e-206">To create the custom view, use the `Get-FormatData` and `Export-FormatData` cmdlets to generate a `.ps1xml` file.</span></span> <span data-ttu-id="b751e-207">Em seguida, edite o `.ps1xml` arquivo para criar o código para o modo de exibição personalizado.</span><span class="sxs-lookup"><span data-stu-id="b751e-207">Then, edit your `.ps1xml` file to create the code for your custom view.</span></span> <span data-ttu-id="b751e-208">O `.ps1xml` arquivo pode ser armazenado em qualquer diretório que o PowerShell possa acessar.</span><span class="sxs-lookup"><span data-stu-id="b751e-208">The `.ps1xml` file can be stored in any directory that PowerShell can access.</span></span> <span data-ttu-id="b751e-209">Por exemplo, um subdiretório de `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="b751e-209">For example, a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="b751e-210">Depois que o `.ps1xml` arquivo for criado, use o `Update-FormatData` cmdlet para incluir o modo de exibição na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-210">After the `.ps1xml` file is created, use the `Update-FormatData` cmdlet to include the view in the current PowerShell session.</span></span> <span data-ttu-id="b751e-211">Ou adicione o comando Update ao seu perfil do PowerShell se você precisar da exibição disponível em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-211">Or, add the update command to your PowerShell profile if you need the view available in all PowerShell sessions.</span></span>

<span data-ttu-id="b751e-212">Para este exemplo, a exibição personalizada deve usar o formato de tabela, caso contrário, `Format-Table` falhará.</span><span class="sxs-lookup"><span data-stu-id="b751e-212">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="b751e-213">Use `Format-Table` com o parâmetro **View** para especificar o nome da exibição personalizada, **mygciview**, e formate a saída da tabela com a coluna **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="b751e-213">Use `Format-Table` with the **View** parameter to specify the custom view's name, **mygciview**, and format the table's output with the **CreationTime** column.</span></span> <span data-ttu-id="b751e-214">Para obter um exemplo de como o comando é executado, consulte [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="b751e-214">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

> [!NOTE]
> <span data-ttu-id="b751e-215">Embora você possa obter o XML de formatação do código-fonte para criar uma exibição personalizada, mais desenvolvimento pode ser necessário para obter o resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="b751e-215">Although you can get the formatting XML from the source code to create a custom view, more development might be needed to get the desired result.</span></span>

<span data-ttu-id="b751e-216">No comando a seguir `Get-FormatData` , há uma alternativa para o parâmetro **PowerShellVersion** para garantir que todas as informações de formatação local sejam retornadas.</span><span class="sxs-lookup"><span data-stu-id="b751e-216">In the following `Get-FormatData` command, there's an alternative for the **PowerShellVersion** parameter to ensure that all local formatting information is returned.</span></span> <span data-ttu-id="b751e-217">Use `-PowerShellVersion $PSVersionTable.PSVersion` em vez de uma versão específica do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b751e-217">Use `-PowerShellVersion $PSVersionTable.PSVersion` rather than a specific PowerShell version.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Length</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="b751e-218">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b751e-218">See also</span></span>

[<span data-ttu-id="b751e-219">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="b751e-219">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="b751e-220">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="b751e-220">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="b751e-221">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="b751e-221">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="b751e-222">Referência XML de esquema de formato</span><span class="sxs-lookup"><span data-stu-id="b751e-222">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="b751e-223">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="b751e-223">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="b751e-224">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="b751e-224">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="b751e-225">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b751e-225">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
