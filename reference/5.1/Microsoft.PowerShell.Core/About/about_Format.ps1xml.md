---
description: Os `Format.ps1xml` arquivos no PowerShell definem a exibição padrão de objetos no console do PowerShell. Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196024"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="bf8fd-105">Sobre o Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="bf8fd-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="bf8fd-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="bf8fd-106">Short description</span></span>

<span data-ttu-id="bf8fd-107">Os `Format.ps1xml` arquivos no PowerShell definem a exibição padrão de objetos no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-107">The `Format.ps1xml` files in PowerShell define the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="bf8fd-108">Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="bf8fd-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="bf8fd-109">Long description</span></span>

<span data-ttu-id="bf8fd-110">Os `Format.ps1xml` arquivos no PowerShell definem a exibição padrão de objetos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-110">The `Format.ps1xml` files in PowerShell define the default display of objects in PowerShell.</span></span> <span data-ttu-id="bf8fd-111">Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-111">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="bf8fd-112">Quando o PowerShell exibe um objeto, ele usa os dados em arquivos de formatação estruturados para determinar a exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-112">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="bf8fd-113">Os dados nos arquivos de formatação determinam se o objeto é renderizado em uma tabela ou em uma lista e determina quais propriedades são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-113">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="bf8fd-114">A formatação afeta apenas a exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-114">The formatting affects the display only.</span></span> <span data-ttu-id="bf8fd-115">Ele não afeta quais propriedades de objeto são passadas pelo pipeline ou como elas são passadas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-115">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="bf8fd-116">`Format.ps1xml` os arquivos não podem ser usados para personalizar o formato de saída para tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-116">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="bf8fd-117">O PowerShell inclui sete arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-117">PowerShell includes seven formatting files.</span></span> <span data-ttu-id="bf8fd-118">Esses arquivos estão localizados no diretório de instalação ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-118">These files are located in the installation directory (`$PSHOME`).</span></span> <span data-ttu-id="bf8fd-119">Cada arquivo define a exibição de um grupo de objetos do Microsoft .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-119">Each file defines the display of a group of Microsoft .NET Framework objects:</span></span>

1. `Certificate.Format.ps1xml`

   <span data-ttu-id="bf8fd-120">Objetos no repositório de certificados, como certificados X. 509 e repositórios de certificados.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-120">Objects in the Certificate store, such as X.509 certificates and certificate stores.</span></span>

1. `DotNetTypes.Format.ps1xml`

   <span data-ttu-id="bf8fd-121">Outros tipos de .NET Framework, como objetos CultureInfo, FileVersionInfo e EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-121">Other .NET Framework types, such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

1. `FileSystem.Format.ps1xml`

   <span data-ttu-id="bf8fd-122">Objetos do sistema de arquivos, como arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-122">File system objects, such as files and directories.</span></span>

1. `Help.Format.ps1xml`

   <span data-ttu-id="bf8fd-123">Exibições da ajuda, como exibições detalhadas e completas, parâmetros e exemplos.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-123">Help views, such as detailed and full views, parameters, and examples.</span></span>

1. `PowerShellCore.Format.ps1xml`

   <span data-ttu-id="bf8fd-124">Objetos gerados por cmdlets do PowerShell Core, como `Get-Member` e `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-124">Objects generated by PowerShell core cmdlets, such as `Get-Member` and `Get-History`.</span></span>

1. `PowerShellTrace.Format.ps1xml`

   <span data-ttu-id="bf8fd-125">Objetos de rastreamento, como os gerados pelo `Trace-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-125">Trace objects, such as those generated by the `Trace-Command` cmdlet.</span></span>

1. `Registry.Format.ps1xml`

   <span data-ttu-id="bf8fd-126">Objetos do registro, como chaves e entradas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-126">Registry objects, such as keys and entries.</span></span>

<span data-ttu-id="bf8fd-127">Um arquivo de formatação pode definir quatro exibições diferentes de cada objeto:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-127">A formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="bf8fd-128">Tabela</span><span class="sxs-lookup"><span data-stu-id="bf8fd-128">Table</span></span>
- <span data-ttu-id="bf8fd-129">Lista</span><span class="sxs-lookup"><span data-stu-id="bf8fd-129">List</span></span>
- <span data-ttu-id="bf8fd-130">Ampla</span><span class="sxs-lookup"><span data-stu-id="bf8fd-130">Wide</span></span>
- <span data-ttu-id="bf8fd-131">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bf8fd-131">Custom</span></span>

<span data-ttu-id="bf8fd-132">Por exemplo, quando a saída de um `Get-ChildItem` comando é canalizada para um `Format-List` comando, `Format-List` o usa a exibição no `FileSystem.Format.ps1xml` arquivo para determinar como exibir os objetos de arquivo e pasta como uma lista.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-132">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the view in the `FileSystem.Format.ps1xml` file to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="bf8fd-133">Quando um arquivo de formatação inclui mais de uma exibição de um objeto, o PowerShell aplica a primeira exibição que ele encontra.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-133">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="bf8fd-134">Em um `Format.ps1xml` arquivo, uma exibição é definida por um conjunto de marcas XML que descrevem o nome da exibição, o tipo de objeto ao qual ele pode ser aplicado, os cabeçalhos de coluna e as propriedades que são exibidas no corpo da exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-134">In a `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="bf8fd-135">O formato nos `Format.ps1xml` arquivos é aplicado logo antes de os dados serem apresentados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-135">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="bf8fd-136">Criando novos arquivos XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="bf8fd-136">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="bf8fd-137">Os `.ps1xml` arquivos instalados com o PowerShell são assinados digitalmente para evitar a violação, pois a formatação pode incluir blocos de script.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-137">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="bf8fd-138">Para alterar o formato de exibição de uma exibição de objeto existente ou para adicionar exibições para novos objetos, crie seus próprios `Format.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-138">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="bf8fd-139">Para criar um novo arquivo, copie um `Format.ps1xml` arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-139">To create a new file, copy an existing `Format.ps1xml` file.</span></span> <span data-ttu-id="bf8fd-140">O novo arquivo pode ter qualquer nome, mas deve ter uma `.ps1xml` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-140">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="bf8fd-141">Você pode posicionar o novo arquivo em qualquer diretório que esteja acessível ao PowerShell, mas é útil inserir os arquivos no diretório de instalação do PowerShell ( `$PSHOME` ) ou em um subdiretório do diretório de instalação.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-141">You can place the new file in any directory that is accessible to PowerShell, but it's useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="bf8fd-142">Para alterar a formatação de um modo de exibição atual, localize o modo de exibição no arquivo de formatação e, em seguida, use as marcas para alterar a exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-142">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="bf8fd-143">Para criar um modo de exibição para um novo tipo de objeto, crie um novo modo de exibição ou use um modo de exibição existente como modelo.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-143">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="bf8fd-144">As marcas são descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-144">The tags are described in the next section.</span></span> <span data-ttu-id="bf8fd-145">Você pode excluir todas as outras exibições no arquivo para que as alterações sejam óbvias para qualquer pessoa que examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-145">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="bf8fd-146">Depois de salvar as alterações, use o `Update-FormatData` cmdlet para adicionar o novo arquivo à sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-146">After you save the changes, use the `Update-FormatData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="bf8fd-147">Se você quiser que a exibição tenha precedência sobre uma exibição definida nos arquivos internos, use o parâmetro **PrependPath** .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-147">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span>
<span data-ttu-id="bf8fd-148">`Update-FormatData` afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-148">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="bf8fd-149">Para fazer a alteração em todas as sessões futuras, adicione o `Update-FormatData` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-149">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-adding-calendar-data-to-culture-objects"></a><span data-ttu-id="bf8fd-150">Exemplo: adicionando dados de calendário a objetos de cultura</span><span class="sxs-lookup"><span data-stu-id="bf8fd-150">Example: Adding calendar data to culture objects</span></span>

<span data-ttu-id="bf8fd-151">Este exemplo mostra como alterar a formatação dos objetos de cultura **System. Globalization. CultureInfo** gerados pelo `Get-Culture` cmdlet na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-151">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="bf8fd-152">Os comandos no exemplo adicionam a propriedade **Calendar** à exibição de tabela padrão exibir objetos de cultura.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-152">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="bf8fd-153">A primeira etapa é localizar o `Format.ps1xml` arquivo que contém a exibição atual dos objetos de cultura.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-153">The first step is to find the `Format.ps1xml` file that contains the current view of the culture objects.</span></span> <span data-ttu-id="bf8fd-154">O seguinte `Select-String` comando localiza o arquivo:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-154">The following `Select-String` command finds the file:</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

<span data-ttu-id="bf8fd-155">Esse comando revela que a definição está no `DotNetTypes.Format.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-155">This command reveals that the definition is in the `DotNetTypes.Format.ps1xml` file.</span></span>

<span data-ttu-id="bf8fd-156">O próximo comando copia o conteúdo do arquivo para um novo arquivo, `MyDotNetTypes.Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-156">The next command copies the file contents to a new file, `MyDotNetTypes.Format.ps1xml`.</span></span>

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="bf8fd-157">Abra o `MyDotNetTypes.Format.ps1xml` arquivo em qualquer XML ou editor de texto, como Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-157">Open the `MyDotNetTypes.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="bf8fd-158">Localize a seção do objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-158">Find the **System.Globalization.CultureInfo** object section.</span></span> <span data-ttu-id="bf8fd-159">O XML a seguir define as exibições do objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-159">The following XML defines the views of the **CultureInfo** object.</span></span> <span data-ttu-id="bf8fd-160">O objeto tem apenas uma exibição **TableControl** .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-160">The object has only a **TableControl** view.</span></span>

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
```

<span data-ttu-id="bf8fd-161">Exclua o restante do arquivo, exceto as marcas de abertura `<?xml>` , `<Configuration>` , e marcações `<ViewDefinitions>` e o fechamento `<ViewDefinitions>` e as `<Configuration>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-161">Delete the remainder of the file, except for the opening `<?xml>`, `<Configuration>`, and `<ViewDefinitions>` tags and the closing `<ViewDefinitions>` and `<Configuration>` tags.</span></span> <span data-ttu-id="bf8fd-162">Se houver uma assinatura digital, exclua-a do `Format.ps1xml` arquivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-162">If there is a digital signature, delete it from your custom `Format.ps1xml`file.</span></span>

<span data-ttu-id="bf8fd-163">O `MyDotNetTypes.Format.ps1xml` arquivo agora deve se parecer com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-163">The `MyDotNetTypes.Format.ps1xml` file should now look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
      <TableColumnHeader/>
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

<span data-ttu-id="bf8fd-164">Crie uma nova coluna para a propriedade **Calendar** adicionando um novo conjunto de `<TableColumnHeader>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-164">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="bf8fd-165">O valor da propriedade **Calendar** pode ser longo, portanto, especifique um valor de 45 caracteres como o `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-165">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

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

<span data-ttu-id="bf8fd-166">Adicione um novo item de coluna para **calendário** nas linhas da tabela usando `<TableColumnItem>` as `<PropertyName` marcas e:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-166">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

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

<span data-ttu-id="bf8fd-167">Salve e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-167">Save and close the file.</span></span> <span data-ttu-id="bf8fd-168">Use `Update-FormatData` para adicionar o novo arquivo de formato à sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-168">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="bf8fd-169">Este exemplo usa o parâmetro **PrependPath** para posicionar o novo arquivo em uma ordem de precedência mais alta do que o arquivo original.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-169">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="bf8fd-170">Para obter mais informações, consulte [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-170">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="bf8fd-171">Para testar a alteração, digite `Get-Culture` e revise a saída que inclui a propriedade **Calendar** .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-171">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="bf8fd-172">O XML em arquivos Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="bf8fd-172">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="bf8fd-173">A definição de esquema completa pode ser encontrada em [Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) no repositório de código-fonte do PowerShell no github.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-173">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="bf8fd-174">A seção **ViewDefinitions** de cada `Format.ps1xml` arquivo contém as `<View>` marcas que definem cada exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-174">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="bf8fd-175">Uma `<View>` marca típica inclui as seguintes marcas:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-175">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="bf8fd-176">`<Name>` Identifica o nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-176">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="bf8fd-177">`<ViewSelectedBy>` Especifica o tipo de objeto ou tipos aos quais a exibição se aplica.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-177">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="bf8fd-178">`<GroupBy>` Especifica como os itens na exibição serão combinados em grupos.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-178">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="bf8fd-179">`<TableControl>`, `<ListControl>` , `<WideControl>` e `<CustomControl>` contêm as marcas que especificam como cada item será exibido.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-179">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="bf8fd-180">Marca de ViewSelectedBy</span><span class="sxs-lookup"><span data-stu-id="bf8fd-180">ViewSelectedBy tag</span></span>

<span data-ttu-id="bf8fd-181">A `<ViewSelectedBy>` marca pode conter uma `<TypeName>` marca para cada tipo de objeto ao qual a exibição se aplica.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-181">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="bf8fd-182">Ou, ele pode conter uma `<SelectionSetName>` marca que faz referência a um conjunto de seleção que é definido em outro lugar usando uma `<SelectionSet>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-182">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="bf8fd-183">Marca GroupBy</span><span class="sxs-lookup"><span data-stu-id="bf8fd-183">GroupBy tag</span></span>

<span data-ttu-id="bf8fd-184">A `<GroupBy>` marca contém uma `<PropertyName>` marca que especifica a propriedade do objeto pela qual os itens devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-184">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="bf8fd-185">Ele também contém uma `<Label>` marca que especifica uma cadeia de caracteres a ser usada como um rótulo para cada grupo ou uma `<CustomControlName>` marca que faz referência a um controle personalizado definido em outro lugar usando uma `<Control>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-185">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="bf8fd-186">A `<Control>` marca contém uma `<Name>` marca e uma `<CustomControl>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-186">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="bf8fd-187">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="bf8fd-187">TableControlTag</span></span>

<span data-ttu-id="bf8fd-188">A `<TableControl>` marca normalmente contém `<TableHeaders>` `<TableRowEntries>` marcas e que definem a formatação para as cabeças e linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-188">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="bf8fd-189">A `<TableHeaders>` marca normalmente contém `<TableColumnHeader>` marcas que contêm `<Label>` `<Width>` marcas, e `<Alignment>` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-189">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="bf8fd-190">A `<TableRowEntries>` marca contém `<TableRowEntry>` marcas para cada linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-190">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="bf8fd-191">A `<TableRowEntry>` marca contém uma `<TableColumnItems>` marca que contém uma `<TableColumnItem>` marca para cada coluna na linha.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-191">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="bf8fd-192">Normalmente, a `<TableColumnItem>` marca contém uma `<PropertyName>` marca que identifica a propriedade do objeto a ser exibida no local definido ou uma `<ScriptBlock>` marca que contém o código de script que calcula um resultado a ser exibido no local.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-192">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="bf8fd-193">Blocos de script também podem ser usados em outro lugar em locais onde os resultados calculados podem ser úteis.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-193">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="bf8fd-194">A `<TableColumnItem>` marca também pode conter uma `<FormatString>` marca que especifica como a propriedade ou os resultados calculados serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-194">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="bf8fd-195">Marca ListControl</span><span class="sxs-lookup"><span data-stu-id="bf8fd-195">ListControl tag</span></span>

<span data-ttu-id="bf8fd-196">A `<ListControl>` marca normalmente contém uma `<ListEntries>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-196">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="bf8fd-197">A `<ListEntries>` marca contém uma `<ListEntry>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-197">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="bf8fd-198">A `<ListEntry>` marca contém uma `<ListItems>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-198">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="bf8fd-199">A `<ListItems>` marca contém `<ListItem>` marcas, que contêm `<PropertyName>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-199">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="bf8fd-200">As `<PropertyName>` marcas especificam a propriedade do objeto a ser exibida no local especificado na lista.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-200">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="bf8fd-201">Se a seleção de exibição for definida usando um conjunto de seleção, as `<ListControl>` `<ListEntry>` marcas e também poderão conter uma `<EntrySelectedBy>` marca que contenha uma ou mais `<TypeName>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-201">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="bf8fd-202">Essas `<TypeName>` marcas especificam o tipo de objeto que a `<ListControl>` marca pretende exibir.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-202">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="bf8fd-203">Marca de WideControl</span><span class="sxs-lookup"><span data-stu-id="bf8fd-203">WideControl tag</span></span>

<span data-ttu-id="bf8fd-204">A `<WideControl>` marca normalmente contém uma `<WideEntries>` marca.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-204">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="bf8fd-205">A `<WideEntries>` marca contém uma ou mais `<WideEntry>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-205">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="bf8fd-206">Uma `<WideEntry>` marca normalmente contém uma `<PropertyName>` marca que especifica a propriedade a ser exibida no local especificado na exibição.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-206">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="bf8fd-207">A `<PropertyName>` marca pode conter uma `<FormatString>` marca que especifica como a propriedade deve ser exibida.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-207">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="bf8fd-208">Marca de CustomControl</span><span class="sxs-lookup"><span data-stu-id="bf8fd-208">CustomControl tag</span></span>

<span data-ttu-id="bf8fd-209">A `<CustomControl>` marca permite que você use um bloco de script para definir um formato.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-209">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="bf8fd-210">Uma `<CustomControl>` marca normalmente contém uma `<CustomEntries>` marca que contém várias `<CustomEntry>` marcas.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-210">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="bf8fd-211">Cada `<CustomEntry>` marca contém uma `<CustomItem>` marca que pode conter uma variedade de marcas que especificam o conteúdo e a formatação do local especificado na exibição, incluindo as `<Text>` marcas,, e `<Indentation>` `<ExpressionBinding>` `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-211">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="default-displays-in-typesps1xml"></a><span data-ttu-id="bf8fd-212">O padrão é exibido no XML Types.ps1</span><span class="sxs-lookup"><span data-stu-id="bf8fd-212">Default displays in Types.ps1xml</span></span>

<span data-ttu-id="bf8fd-213">As exibições padrão de alguns tipos de objeto básicos são definidas no `Types.ps1xml` arquivo no `$PSHOME` diretório.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-213">The default displays of some basic object types are defined in the `Types.ps1xml` file in the `$PSHOME` directory.</span></span> <span data-ttu-id="bf8fd-214">Os nós são nomeados **PSStandardMembers** e os subnós usam uma das seguintes marcas:</span><span class="sxs-lookup"><span data-stu-id="bf8fd-214">The nodes are named **PsStandardMembers** , and the subnodes use one of the following tags:</span></span>

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

<span data-ttu-id="bf8fd-215">Para obter mais informações, consulte [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-215">For more information, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="bf8fd-216">Rastreando o uso de arquivo XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="bf8fd-216">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="bf8fd-217">Para detectar erros no carregamento ou aplicativo de `Format.ps1xml` arquivos, use o `Trace-Command` cmdlet com qualquer um dos seguintes componentes de formato como o valor do parâmetro **Name** :</span><span class="sxs-lookup"><span data-stu-id="bf8fd-217">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="bf8fd-218">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="bf8fd-218">FormatFileLoading</span></span>
- <span data-ttu-id="bf8fd-219">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="bf8fd-219">FormatViewBinding</span></span>

<span data-ttu-id="bf8fd-220">Para obter mais informações, consulte [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) e [Get-tracename](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-220">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="bf8fd-221">Assinando um arquivo XML Format.ps1</span><span class="sxs-lookup"><span data-stu-id="bf8fd-221">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="bf8fd-222">Para proteger os usuários do seu `Format.ps1xml` arquivo, assine o arquivo usando uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-222">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="bf8fd-223">Para obter mais informações, consulte [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-223">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="bf8fd-224">XML de exemplo para uma exibição personalizada Format-Table</span><span class="sxs-lookup"><span data-stu-id="bf8fd-224">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="bf8fd-225">O exemplo a seguir cria uma `Format-Table` exibição personalizada para os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="bf8fd-225">The following sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="bf8fd-226">A exibição personalizada é denominada **mygciview** e adiciona a coluna **CreationTime** à tabela.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-226">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="bf8fd-227">A exibição personalizada é criada a partir de uma versão editada do `FileSystem.Format.ps1xml` arquivo armazenado no `$PSHOME` PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-227">The custom view is created from an edited version of the `FileSystem.Format.ps1xml` file that's stored in `$PSHOME` on PowerShell 5.1.</span></span>

<span data-ttu-id="bf8fd-228">Depois que o `.ps1xml` arquivo personalizado for salvo, use `Update-FormatData` para incluir o modo de exibição em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-228">After your custom `.ps1xml` file is saved, use `Update-FormatData` to include the view in a PowerShell session.</span></span> <span data-ttu-id="bf8fd-229">Para este exemplo, a exibição personalizada deve usar o formato de tabela, caso contrário, `Format-Table` falhará.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-229">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="bf8fd-230">Use `Format-Table` com o parâmetro **View** para especificar o nome do modo de exibição personalizado e formatar a saída da tabela.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-230">Use `Format-Table` with the **View** parameter to specify the custom view's name and format the table's output.</span></span> <span data-ttu-id="bf8fd-231">Para obter um exemplo de como o comando é executado, consulte [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="bf8fd-231">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> <span data-ttu-id="bf8fd-232">Para ajustar a amostra de XML dentro das limitações de largura de linha, era necessário compactar algum recuo e usar quebras de linha no código.</span><span class="sxs-lookup"><span data-stu-id="bf8fd-232">To fit the XML sample within line width limitations, it was necessary to compress some indentation and use line breaks within the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
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

## <a name="see-also"></a><span data-ttu-id="bf8fd-233">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf8fd-233">See also</span></span>

[<span data-ttu-id="bf8fd-234">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="bf8fd-234">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="bf8fd-235">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="bf8fd-235">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="bf8fd-236">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="bf8fd-236">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="bf8fd-237">Referência XML de esquema de formato</span><span class="sxs-lookup"><span data-stu-id="bf8fd-237">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="bf8fd-238">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="bf8fd-238">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="bf8fd-239">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="bf8fd-239">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="bf8fd-240">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8fd-240">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
