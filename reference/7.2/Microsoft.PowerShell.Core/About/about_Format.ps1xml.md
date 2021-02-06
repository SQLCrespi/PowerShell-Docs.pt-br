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
# <a name="about-formatps1xml"></a>Sobre o Format.ps1XML

## <a name="short-description"></a>Descrição breve

A partir do PowerShell 6, as exibições padrão para objetos são definidas no código-fonte do PowerShell.

Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.

## <a name="long-description"></a>Descrição longa

A partir do PowerShell 6, as exibições padrão são definidas no código-fonte do PowerShell. Os `Format.ps1xml` arquivos do powershell 5,1 e versões anteriores não existem no PowerShell 6 e versões posteriores.

O código-fonte do PowerShell define a exibição padrão de objetos no console do PowerShell. Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.

Quando o PowerShell exibe um objeto, ele usa os dados em arquivos de formatação estruturados para determinar a exibição padrão do objeto. Os dados nos arquivos de formatação determinam se o objeto é renderizado em uma tabela ou em uma lista e determina quais propriedades são exibidas por padrão.

A formatação afeta apenas a exibição. Ele não afeta quais propriedades de objeto são passadas pelo pipeline ou como elas são passadas. `Format.ps1xml` os arquivos não podem ser usados para personalizar o formato de saída para tabelas de hash.

Um `.ps1xml` arquivo de formatação pode definir quatro exibições diferentes de cada objeto:

- Tabela
- List
- Ampla
- Personalizado

Por exemplo, quando a saída de um `Get-ChildItem` comando é canalizada para um `Format-List` comando, `Format-List` o usa o modo de exibição de lista definido no código-fonte para determinar como exibir os objetos de arquivo e pasta como uma lista.

Quando um arquivo de formatação inclui mais de uma exibição de um objeto, o PowerShell aplica a primeira exibição que ele encontra.

Em um `Format.ps1xml` arquivo personalizado, uma exibição é definida por um conjunto de marcas XML que descrevem o nome da exibição, o tipo de objeto ao qual ele pode ser aplicado, os cabeçalhos de coluna e as propriedades que são exibidas no corpo da exibição. O formato nos `Format.ps1xml` arquivos é aplicado logo antes de os dados serem apresentados ao usuário.

## <a name="creating-new-formatps1xml-files"></a>Criando novos arquivos XML Format.ps1

Para alterar o formato de exibição de uma exibição de objeto existente ou para adicionar exibições para novos objetos, crie seus próprios `Format.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.

Para criar um `Format.ps1xml` arquivo para definir uma exibição personalizada, use os cmdlets [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) e [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) . Use um editor de texto para editar o arquivo. O arquivo pode ser salvo em qualquer diretório que o PowerShell possa acessar, como um subdiretório de `$HOME` .

Para alterar a formatação de um modo de exibição atual, localize o modo de exibição no arquivo de formatação e, em seguida, use as marcas para alterar a exibição. Para criar um modo de exibição para um novo tipo de objeto, crie um novo modo de exibição ou use um modo de exibição existente como modelo. As marcas são descritas na próxima seção. Você pode excluir todas as outras exibições no arquivo para que as alterações sejam óbvias para qualquer pessoa que examina o arquivo.

Depois de salvar as alterações, use o [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) para adicionar o novo arquivo à sua sessão do PowerShell. Se você quiser que a exibição tenha precedência sobre uma exibição definida nos arquivos internos, use o parâmetro **PrependPath** . `Update-FormatData` afeta apenas a sessão atual. Para fazer a alteração em todas as sessões futuras, adicione o `Update-FormatData` comando ao seu perfil do PowerShell.

### <a name="example-add-calendar-data-to-culture-objects"></a>Exemplo: adicionar dados de calendário a objetos de cultura

Este exemplo mostra como alterar a formatação dos objetos de cultura **System. Globalization. CultureInfo** gerados pelo `Get-Culture` cmdlet na sessão atual do PowerShell. Os comandos no exemplo adicionam a propriedade **Calendar** à exibição de tabela padrão exibir objetos de cultura.

Para começar, obtenha os dados de formato do arquivo de código-fonte e crie um `Format.ps1xml` arquivo que contenha a exibição atual dos objetos de cultura.

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

Abra o `CultureInfo.Format.ps1xml` arquivo em qualquer XML ou editor de texto, como Visual Studio Code. O XML a seguir define as exibições do objeto **CultureInfo** .

O `CultureInfo.Format.ps1xml` arquivo deve ser semelhante ao exemplo a seguir:

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

Crie uma nova coluna para a propriedade **Calendar** adicionando um novo conjunto de `<TableColumnHeader>` marcas. O valor da propriedade **Calendar** pode ser longo, portanto, especifique um valor de 45 caracteres como o `<Width>` .

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

Adicione um novo item de coluna para **calendário** nas linhas da tabela usando `<TableColumnItem>` as `<PropertyName` marcas e:

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

Salve e feche o arquivo. Use `Update-FormatData` para adicionar o novo arquivo de formato à sessão atual do PowerShell.

Este exemplo usa o parâmetro **PrependPath** para posicionar o novo arquivo em uma ordem de precedência mais alta do que o arquivo original. Para obter mais informações, consulte [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

Para testar a alteração, digite `Get-Culture` e revise a saída que inclui a propriedade **Calendar** .

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a>O XML em arquivos Format.ps1XML

A definição de esquema completa pode ser encontrada em [Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) no repositório de código-fonte do PowerShell no github.

A seção **ViewDefinitions** de cada `Format.ps1xml` arquivo contém as `<View>` marcas que definem cada exibição. Uma `<View>` marca típica inclui as seguintes marcas:

- `<Name>` Identifica o nome da exibição.
- `<ViewSelectedBy>` Especifica o tipo de objeto ou tipos aos quais a exibição se aplica.
- `<GroupBy>` Especifica como os itens na exibição serão combinados em grupos.
- `<TableControl>`, `<ListControl>` , `<WideControl>` e `<CustomControl>` contêm as marcas que especificam como cada item será exibido.

### <a name="viewselectedby-tag"></a>Marca de ViewSelectedBy

A `<ViewSelectedBy>` marca pode conter uma `<TypeName>` marca para cada tipo de objeto ao qual a exibição se aplica. Ou, ele pode conter uma `<SelectionSetName>` marca que faz referência a um conjunto de seleção que é definido em outro lugar usando uma `<SelectionSet>` marca.

### <a name="groupby-tag"></a>Marca GroupBy

A `<GroupBy>` marca contém uma `<PropertyName>` marca que especifica a propriedade do objeto pela qual os itens devem ser agrupados. Ele também contém uma `<Label>` marca que especifica uma cadeia de caracteres a ser usada como um rótulo para cada grupo ou uma `<CustomControlName>` marca que faz referência a um controle personalizado definido em outro lugar usando uma `<Control>` marca. A `<Control>` marca contém uma `<Name>` marca e uma `<CustomControl>` marca.

### <a name="tablecontroltag"></a>TableControlTag

A `<TableControl>` marca normalmente contém `<TableHeaders>` `<TableRowEntries>` marcas e que definem a formatação para as cabeças e linhas da tabela. A `<TableHeaders>` marca normalmente contém `<TableColumnHeader>` marcas que contêm `<Label>` `<Width>` marcas, e `<Alignment>` . A `<TableRowEntries>` marca contém `<TableRowEntry>` marcas para cada linha na tabela. A `<TableRowEntry>` marca contém uma `<TableColumnItems>` marca que contém uma `<TableColumnItem>` marca para cada coluna na linha. Normalmente, a `<TableColumnItem>` marca contém uma `<PropertyName>` marca que identifica a propriedade do objeto a ser exibida no local definido ou uma `<ScriptBlock>` marca que contém o código de script que calcula um resultado a ser exibido no local.

> [!NOTE]
> Blocos de script também podem ser usados em outro lugar em locais onde os resultados calculados podem ser úteis.

A `<TableColumnItem>` marca também pode conter uma `<FormatString>` marca que especifica como a propriedade ou os resultados calculados serão exibidos.

### <a name="listcontrol-tag"></a>Marca ListControl

A `<ListControl>` marca normalmente contém uma `<ListEntries>` marca. A `<ListEntries>` marca contém uma `<ListEntry>` marca. A `<ListEntry>` marca contém uma `<ListItems>` marca. A `<ListItems>` marca contém `<ListItem>` marcas, que contêm `<PropertyName>` marcas. As `<PropertyName>` marcas especificam a propriedade do objeto a ser exibida no local especificado na lista. Se a seleção de exibição for definida usando um conjunto de seleção, as `<ListControl>` `<ListEntry>` marcas e também poderão conter uma `<EntrySelectedBy>` marca que contenha uma ou mais `<TypeName>` marcas. Essas `<TypeName>` marcas especificam o tipo de objeto que a `<ListControl>` marca pretende exibir.

### <a name="widecontrol-tag"></a>Marca de WideControl

A `<WideControl>` marca normalmente contém uma `<WideEntries>` marca. A `<WideEntries>` marca contém uma ou mais `<WideEntry>` marcas. Uma `<WideEntry>` marca normalmente contém uma `<PropertyName>` marca que especifica a propriedade a ser exibida no local especificado na exibição. A `<PropertyName>` marca pode conter uma `<FormatString>` marca que especifica como a propriedade deve ser exibida.

### <a name="customcontrol-tag"></a>Marca de CustomControl

A `<CustomControl>` marca permite que você use um bloco de script para definir um formato. Uma `<CustomControl>` marca normalmente contém uma `<CustomEntries>` marca que contém várias `<CustomEntry>` marcas. Cada `<CustomEntry>` marca contém uma `<CustomItem>` marca que pode conter uma variedade de marcas que especificam o conteúdo e a formatação do local especificado na exibição, incluindo as `<Text>` marcas,, e `<Indentation>` `<ExpressionBinding>` `<NewLine>` .

## <a name="tracing-formatps1xml-file-use"></a>Rastreando o uso de arquivo XML Format.ps1

Para detectar erros no carregamento ou aplicativo de `Format.ps1xml` arquivos, use o `Trace-Command` cmdlet com qualquer um dos seguintes componentes de formato como o valor do parâmetro **Name** :

- FormatFileLoading
- FormatViewBinding

Para obter mais informações, consulte [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) e [Get-tracename](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Assinando um arquivo XML Format.ps1

Para proteger os usuários do seu `Format.ps1xml` arquivo, assine o arquivo usando uma assinatura digital. Para obter mais informações, consulte [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>XML de exemplo para uma exibição personalizada Format-Table

O exemplo de XML a seguir cria uma `Format-Table` exibição personalizada para os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` . A exibição personalizada é denominada **mygciview** e adiciona a coluna **CreationTime** à tabela.

Para criar o modo de exibição personalizado, use os `Get-FormatData` `Export-FormatData` cmdlets e para gerar um `.ps1xml` arquivo. Em seguida, edite o `.ps1xml` arquivo para criar o código para o modo de exibição personalizado. O `.ps1xml` arquivo pode ser armazenado em qualquer diretório que o PowerShell possa acessar. Por exemplo, um subdiretório de `$HOME` .

Depois que o `.ps1xml` arquivo for criado, use o `Update-FormatData` cmdlet para incluir o modo de exibição na sessão atual do PowerShell. Ou adicione o comando Update ao seu perfil do PowerShell se você precisar da exibição disponível em todas as sessões do PowerShell.

Para este exemplo, a exibição personalizada deve usar o formato de tabela, caso contrário, `Format-Table` falhará.

Use `Format-Table` com o parâmetro **View** para especificar o nome da exibição personalizada, **mygciview**, e formate a saída da tabela com a coluna **CreationTime** . Para obter um exemplo de como o comando é executado, consulte [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

> [!NOTE]
> Embora você possa obter o XML de formatação do código-fonte para criar uma exibição personalizada, mais desenvolvimento pode ser necessário para obter o resultado desejado.

No comando a seguir `Get-FormatData` , há uma alternativa para o parâmetro **PowerShellVersion** para garantir que todas as informações de formatação local sejam retornadas. Use `-PowerShellVersion $PSVersionTable.PSVersion` em vez de uma versão específica do PowerShell.

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

## <a name="see-also"></a>Consulte também

[Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[Referência XML de esquema de formato](/powershell/scripting/developer/format/format-schema-xml-reference)

[Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command)

[Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[Escrever um arquivo de formatação do PowerShell](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
