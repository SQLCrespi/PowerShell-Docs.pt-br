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
# <a name="about-formatps1xml"></a>Sobre o Format.ps1XML

## <a name="short-description"></a>Descrição breve

Os `Format.ps1xml` arquivos no PowerShell definem a exibição padrão de objetos no console do PowerShell. Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.

## <a name="long-description"></a>Descrição longa

Os `Format.ps1xml` arquivos no PowerShell definem a exibição padrão de objetos no PowerShell. Você pode criar seus próprios `Format.ps1xml` arquivos para alterar a exibição de objetos ou para definir as exibições padrão para novos tipos de objetos que você criar no PowerShell.

Quando o PowerShell exibe um objeto, ele usa os dados em arquivos de formatação estruturados para determinar a exibição padrão do objeto. Os dados nos arquivos de formatação determinam se o objeto é renderizado em uma tabela ou em uma lista e determina quais propriedades são exibidas por padrão.

A formatação afeta apenas a exibição. Ele não afeta quais propriedades de objeto são passadas pelo pipeline ou como elas são passadas. `Format.ps1xml` os arquivos não podem ser usados para personalizar o formato de saída para tabelas de hash.

O PowerShell inclui sete arquivos de formatação. Esses arquivos estão localizados no diretório de instalação ( `$PSHOME` ). Cada arquivo define a exibição de um grupo de objetos do Microsoft .NET Framework:

1. `Certificate.Format.ps1xml`

   Objetos no repositório de certificados, como certificados X. 509 e repositórios de certificados.

1. `DotNetTypes.Format.ps1xml`

   Outros tipos de .NET Framework, como objetos CultureInfo, FileVersionInfo e EventLogEntry.

1. `FileSystem.Format.ps1xml`

   Objetos do sistema de arquivos, como arquivos e diretórios.

1. `Help.Format.ps1xml`

   Exibições da ajuda, como exibições detalhadas e completas, parâmetros e exemplos.

1. `PowerShellCore.Format.ps1xml`

   Objetos gerados por cmdlets do PowerShell Core, como `Get-Member` e `Get-History` .

1. `PowerShellTrace.Format.ps1xml`

   Objetos de rastreamento, como os gerados pelo `Trace-Command` cmdlet.

1. `Registry.Format.ps1xml`

   Objetos do registro, como chaves e entradas.

Um arquivo de formatação pode definir quatro exibições diferentes de cada objeto:

- Tabela
- Lista
- Ampla
- Personalizado

Por exemplo, quando a saída de um `Get-ChildItem` comando é canalizada para um `Format-List` comando, `Format-List` o usa a exibição no `FileSystem.Format.ps1xml` arquivo para determinar como exibir os objetos de arquivo e pasta como uma lista.

Quando um arquivo de formatação inclui mais de uma exibição de um objeto, o PowerShell aplica a primeira exibição que ele encontra.

Em um `Format.ps1xml` arquivo, uma exibição é definida por um conjunto de marcas XML que descrevem o nome da exibição, o tipo de objeto ao qual ele pode ser aplicado, os cabeçalhos de coluna e as propriedades que são exibidas no corpo da exibição. O formato nos `Format.ps1xml` arquivos é aplicado logo antes de os dados serem apresentados ao usuário.

## <a name="creating-new-formatps1xml-files"></a>Criando novos arquivos XML Format.ps1

Os `.ps1xml` arquivos instalados com o PowerShell são assinados digitalmente para evitar a violação, pois a formatação pode incluir blocos de script. Para alterar o formato de exibição de uma exibição de objeto existente ou para adicionar exibições para novos objetos, crie seus próprios `Format.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.

Para criar um novo arquivo, copie um `Format.ps1xml` arquivo existente. O novo arquivo pode ter qualquer nome, mas deve ter uma `.ps1xml` extensão de nome de arquivo. Você pode posicionar o novo arquivo em qualquer diretório que esteja acessível ao PowerShell, mas é útil inserir os arquivos no diretório de instalação do PowerShell ( `$PSHOME` ) ou em um subdiretório do diretório de instalação.

Para alterar a formatação de um modo de exibição atual, localize o modo de exibição no arquivo de formatação e, em seguida, use as marcas para alterar a exibição. Para criar um modo de exibição para um novo tipo de objeto, crie um novo modo de exibição ou use um modo de exibição existente como modelo. As marcas são descritas na próxima seção. Você pode excluir todas as outras exibições no arquivo para que as alterações sejam óbvias para qualquer pessoa que examina o arquivo.

Depois de salvar as alterações, use o `Update-FormatData` cmdlet para adicionar o novo arquivo à sua sessão do PowerShell. Se você quiser que a exibição tenha precedência sobre uma exibição definida nos arquivos internos, use o parâmetro **PrependPath** .
`Update-FormatData` afeta apenas a sessão atual. Para fazer a alteração em todas as sessões futuras, adicione o `Update-FormatData` comando ao seu perfil do PowerShell.

### <a name="example-adding-calendar-data-to-culture-objects"></a>Exemplo: adicionando dados de calendário a objetos de cultura

Este exemplo mostra como alterar a formatação dos objetos de cultura **System. Globalization. CultureInfo** gerados pelo `Get-Culture` cmdlet na sessão atual do PowerShell. Os comandos no exemplo adicionam a propriedade **Calendar** à exibição de tabela padrão exibir objetos de cultura.

A primeira etapa é localizar o `Format.ps1xml` arquivo que contém a exibição atual dos objetos de cultura. O seguinte `Select-String` comando localiza o arquivo:

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

Esse comando revela que a definição está no `DotNetTypes.Format.ps1xml` arquivo.

O próximo comando copia o conteúdo do arquivo para um novo arquivo, `MyDotNetTypes.Format.ps1xml` .

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

Abra o `MyDotNetTypes.Format.ps1xml` arquivo em qualquer XML ou editor de texto, como Visual Studio Code. Localize a seção do objeto **System. Globalization. CultureInfo** . O XML a seguir define as exibições do objeto **CultureInfo** . O objeto tem apenas uma exibição **TableControl** .

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

Exclua o restante do arquivo, exceto as marcas de abertura `<?xml>` , `<Configuration>` , e marcações `<ViewDefinitions>` e o fechamento `<ViewDefinitions>` e as `<Configuration>` marcas. Se houver uma assinatura digital, exclua-a do `Format.ps1xml` arquivo personalizado.

O `MyDotNetTypes.Format.ps1xml` arquivo agora deve se parecer com o exemplo a seguir:

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
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

Para testar a alteração, digite `Get-Culture` e revise a saída que inclui a propriedade **Calendar** .

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
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

## <a name="default-displays-in-typesps1xml"></a>O padrão é exibido no XML Types.ps1

As exibições padrão de alguns tipos de objeto básicos são definidas no `Types.ps1xml` arquivo no `$PSHOME` diretório. Os nós são nomeados **PSStandardMembers** e os subnós usam uma das seguintes marcas:

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

Para obter mais informações, consulte [about_Types.ps1XML](about_Types.ps1xml.md).

## <a name="tracing-formatps1xml-file-use"></a>Rastreando o uso de arquivo XML Format.ps1

Para detectar erros no carregamento ou aplicativo de `Format.ps1xml` arquivos, use o `Trace-Command` cmdlet com qualquer um dos seguintes componentes de formato como o valor do parâmetro **Name** :

- FormatFileLoading
- FormatViewBinding

Para obter mais informações, consulte [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) e [Get-tracename](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Assinando um arquivo XML Format.ps1

Para proteger os usuários do seu `Format.ps1xml` arquivo, assine o arquivo usando uma assinatura digital. Para obter mais informações, consulte [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>XML de exemplo para uma exibição personalizada Format-Table

O exemplo a seguir cria uma `Format-Table` exibição personalizada para os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` . A exibição personalizada é denominada **mygciview** e adiciona a coluna **CreationTime** à tabela.

A exibição personalizada é criada a partir de uma versão editada do `FileSystem.Format.ps1xml` arquivo armazenado no `$PSHOME` PowerShell 5,1.

Depois que o `.ps1xml` arquivo personalizado for salvo, use `Update-FormatData` para incluir o modo de exibição em uma sessão do PowerShell. Para este exemplo, a exibição personalizada deve usar o formato de tabela, caso contrário, `Format-Table` falhará.

Use `Format-Table` com o parâmetro **View** para especificar o nome do modo de exibição personalizado e formatar a saída da tabela. Para obter um exemplo de como o comando é executado, consulte [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

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
> Para ajustar a amostra de XML dentro das limitações de largura de linha, era necessário compactar algum recuo e usar quebras de linha no código.

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

## <a name="see-also"></a>Confira também

[Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[Referência XML de esquema de formato](/powershell/scripting/developer/format/format-schema-xml-reference)

[Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command)

[Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[Escrever um arquivo de formatação do PowerShell](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
