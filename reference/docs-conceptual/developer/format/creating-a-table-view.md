---
title: Criando uma exibição de tabela | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 862f942facafff6cea66c4f8f1040772c6a62ec3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363405"
---
# <a name="creating-a-table-view"></a>Criar uma exibição de tabela

Uma exibição de tabela exibe dados em uma ou mais colunas. Cada linha na tabela representa um objeto .NET e cada coluna da tabela representa uma propriedade do objeto ou um valor de script. Você pode definir um modo de exibição de tabela que exibe todas as propriedades de um objeto ou um subconjunto das propriedades de um objeto.

## <a name="a-table-view-display"></a>Exibição de uma exibição de tabela

O exemplo a seguir mostra como o Windows PowerShell exibe o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) que é retornado pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) . Para esse objeto, o Windows PowerShell definiu um modo de exibição de tabela que exibe a propriedade `Status`, a propriedade `Name` (essa propriedade é uma propriedade de alias para a propriedade `ServiceName`) e a propriedade `DisplayName`. Cada linha na tabela representa um objeto retornado pelo cmdlet.

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a>Definindo a exibição de tabela

O XML a seguir mostra o esquema de exibição de tabela para exibir o [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) . Você deve especificar cada propriedade que deseja exibir na exibição de tabela.

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

Os seguintes elementos XML são usados para definir um modo de exibição de lista:

- O elemento [View](./view-element-format.md) é o elemento pai da exibição de tabela. (Esse é o mesmo elemento pai para as exibições de controle de lista, largo e personalizado.)

- O elemento [Name](./name-element-for-view-format.md) especifica o nome da exibição. Esse elemento é necessário para todas as exibições.

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define os objetos que usam a exibição. Este elemento é obrigatório.

- O elemento [GroupBy](./groupby-element-for-view-format.md) (não mostrado neste exemplo) define quando um novo grupo de objetos é exibido. Um novo grupo é iniciado sempre que o valor de uma propriedade ou script específico é alterado. Esse elemento é opcional.

- O elemento [Controls](./controls-element-for-view-format.md) (não mostrado neste exemplo) define os controles personalizados que são definidos pelo modo de exibição de tabela. Os controles oferecem uma maneira de especificar como os dados são exibidos. Esse elemento é opcional. Uma exibição pode definir seus próprios controles personalizados ou pode usar controles comuns que podem ser usados por qualquer exibição no arquivo de formatação. Para obter mais informações sobre controles personalizados, consulte [criando controles personalizados](./creating-custom-controls.md).

- O elemento [HideTableHeaders](./hidetableheaders-element-format.md) (não mostrado neste exemplo) especifica que a tabela não mostrará nenhum rótulo na parte superior da tabela. Esse elemento é opcional.

- O elemento [TableControl](./tablecontrol-element-format.md) que define as informações de cabeçalho e linha da tabela. Semelhante a todas as outras exibições, um modo de exibição de tabela pode exibir os valores de propriedades de objeto ou valores gerados por scripts.

## <a name="defining-column-headers"></a>Definindo cabeçalhos de coluna

1. O elemento [TableHeaders](./tableheaders-element-format.md) e seus elementos filho definem o que é exibido na parte superior da tabela.

2. O elemento [TableColumnHeader](./tablecolumnheader-element-format.md) define o que é exibido na parte superior de uma coluna da tabela. Especifique esses elementos na ordem em que você deseja que os cabeçalhos sejam exibidos.

   Não há nenhum limite para o número desse elemento que você pode usar, mas o número de elementos [TableColumnHeader](./tablecolumnheader-element-format.md) no modo de exibição de tabela deve ser igual ao número de elementos [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) que você usa.

3. O elemento [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica o texto que é exibido. Esse elemento é opcional.

4. O elemento [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica a largura (em caracteres) da coluna. Esse elemento é opcional.

5. O elemento [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) especifica como o rótulo é exibido. O rótulo pode ser alinhado à esquerda, à direita ou centralizado. Esse elemento é opcional.

## <a name="defining-the-table-rows"></a>Definindo as linhas da tabela

Exibições de tabela podem fornecer uma ou mais definições que especificam quais dados são exibidos nas linhas da tabela usando os elementos filho do elemento [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) . Observe que você pode especificar várias definições para as linhas da tabela, mas os cabeçalhos das linhas permanecem os mesmos, independentemente de qual definição de linha é usada. Normalmente, uma tabela terá apenas uma definição.

No exemplo a seguir, a exibição fornece uma única definição que exibe os valores de várias propriedades do [System. Diagnostics. Process? Displayproperty = objeto FullName](/dotnet/api/System.Diagnostics.Process) . Um modo de exibição de tabela pode exibir o valor de uma propriedade ou o valor de um script (não mostrado no exemplo) em suas linhas.

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

Os seguintes elementos XML podem ser usados para fornecer definições para uma linha:

- O elemento [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) e seus elementos filho definem o que é exibido nas linhas da tabela.

- O elemento [TableRowEntry](./listentry-element-for-listcontrol-format.md) fornece uma definição da linha. Pelo menos um [TableRowEntry](./listentry-element-for-listcontrol-format.md) é necessário; no entanto, não há nenhum limite máximo para o número de elementos que você pode adicionar. Na maioria dos casos, uma exibição terá apenas uma definição.

- O elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) especifica os objetos que são exibidos por uma definição específica. Esse elemento é opcional e só é necessário quando você define vários elementos [TableRowEntry](./listentry-element-for-listcontrol-format.md) que exibem objetos diferentes.

- O elemento [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) especifica que o texto que excede a largura da coluna é exibido na próxima linha. Por padrão, o texto que excede a largura da coluna é truncado.

- O elemento [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) define as propriedades ou os scripts cujos valores são exibidos na linha.

- O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha. Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha. A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.

- O elemento [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica a propriedade cujo valor é exibido na linha. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [scriptblock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica o script cujo valor é exibido na linha. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

- O elemento [FormatString](./label-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido. Esse elemento é opcional.

- O elemento [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica como o valor da propriedade ou do script é exibido. O valor pode ser alinhado à esquerda, à direita ou centralizado. Esse elemento é opcional.

## <a name="defining-the-objects-that-use-the-table-view"></a>Definindo os objetos que usam o modo de exibição de tabela

Há duas maneiras de definir quais objetos .NET usam o modo de exibição de tabela. Você pode usar o elemento [ViewSelectedBy](./viewselectedby-element-format.md) para definir os objetos que podem ser exibidos por todas as definições da exibição ou pode usar o elemento [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) para definir quais objetos são exibidos por uma definição específica da exibição. Na maioria dos casos, uma exibição tem apenas uma definição, portanto, os objetos são normalmente definidos pelo elemento [ViewSelectedBy](./viewselectedby-element-format.md) .

O exemplo a seguir mostra como definir os objetos que são exibidos pelo modo de exibição de tabela usando os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [TypeName](./typename-element-for-viewselectedby-format.md) . Não há nenhum limite para o número de elementos [TypeName](./typename-element-for-viewselectedby-format.md) que você pode especificar, e sua ordem não é significativa.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de tabela:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.

- O elemento [TypeName](./typename-element-for-viewselectedby-format.md) especifica o objeto .NET que é exibido pela exibição. O nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo ou seleção definida para a exibição, mas não há um número máximo de elementos que possam ser especificados.

O exemplo a seguir usa os elementos [ViewSelectedBy](./viewselectedby-element-format.md) e [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) . Use conjuntos de seleção em que você tenha um conjunto de objetos relacionado que são exibidos usando várias exibições, como quando você define uma exibição de lista e uma exibição de tabela para os mesmos objetos. Para obter mais informações sobre como criar um conjunto de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados pelo modo de exibição de lista:

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) define quais objetos são exibidos pela exibição de lista.

- O elemento [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) especifica um conjunto de objetos que podem ser exibidos pela exibição. Você deve especificar pelo menos um conjunto de seleção ou tipo para a exibição, mas não há um número máximo de elementos que possam ser especificados.

O exemplo a seguir mostra como definir os objetos exibidos por uma definição específica da exibição de tabela usando o elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) . Usando esse elemento, você pode especificar o nome do tipo .NET do objeto, um conjunto de objetos de seleção ou uma condição de seleção que especifica quando a definição é usada. Para obter mais informações sobre como criar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

> [!NOTE]
> Ao criar várias definições da exibição de tabela, não é possível especificar cabeçalhos de coluna diferentes. Você pode especificar apenas o que é exibido nas linhas da tabela, como quais objetos são exibidos.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

Os seguintes elementos XML podem ser usados para especificar os objetos que são usados por uma definição específica da exibição de lista:

- O elemento [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) define quais objetos são exibidos pela definição.

- O elemento [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) especifica o objeto .NET que é exibido pela definição. Ao usar esse elemento, o nome do tipo .NET totalmente qualificado é necessário. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica um conjunto de objetos que podem ser exibidos por essa definição. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados.

- O elemento [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (não mostrado) especifica uma condição que deve existir para que essa definição seja usada. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para a definição, mas não há um número máximo de elementos que possam ser especificados. Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="using-format-strings"></a>Usando cadeias de caracteres de formato

As cadeias de caracteres de formatação podem ser adicionadas a uma exibição para definir ainda mais como os dados são exibidos. O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da propriedade `StartTime`.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

Os seguintes elementos XML podem ser usados para especificar um padrão de formato:

- O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha. Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha. A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.

- O elemento [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica a propriedade cujo valor é exibido na linha. Você deve especificar uma propriedade ou um script, mas não pode especificar ambos.

- O elemento [FormatString](./label-element-for-listitem-for-listcontrol-format.md) especifica um padrão de formato que define como o valor de propriedade ou script é exibido.

No exemplo a seguir, o método `ToString` é chamado para formatar o valor do script. Os scripts podem chamar qualquer método de um objeto. Portanto, se um objeto tiver um método, como `ToString`, que tem parâmetros de formatação, o script poderá chamar esse método para formatar o valor de saída do script.

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

O elemento XML a seguir pode ser usado para chamar o método de `ToString`:

- O elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) define a propriedade ou o script cujo valor é exibido na coluna da linha. Um elemento [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) é necessário para cada coluna da linha. A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.

- O elemento [scriptblock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) especifica o script cujo valor é exibido na linha. Você deve especificar um script ou uma propriedade, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
