---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableRowEntry para TableRowEntries para TableControl (formato)
description: Elemento TableRowEntry para TableRowEntries para TableControl (formato)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659770"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>Elemento TableRowEntry para TableRowEntries para TableControl (formato)

Define os dados que são exibidos em uma linha da tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `TableRowEntry` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para TableRowEntry para TableControl (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Elemento necessário.<br /><br /> Define os objetos cujos valores de propriedade são exibidos na linha.|
|[Elemento TableColumnItems para TableRowEntry para TableControl (formato)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Elemento necessário.<br /><br /> Define as propriedades ou os scripts cujos valores são exibidos.|
|[Elemento Wrap para TableRowEntry para TableControl (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica que o texto que excede a largura da coluna é exibido na próxima linha.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableRowEntries para TableControl (formato)](./tablerowentries-element-for-tablecontrol-format.md)|Define as linhas da tabela.|

## <a name="remarks"></a>Comentários

Um `TableColumnItems` elemento e um `EntrySelectedBy` elemento devem ser especificados.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `TableRowEntry` elemento que define uma linha que exibe os valores de duas propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento EntrySelectedBy para TableRowEntry para TableControl (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Elemento TableColumnItems para TableRowEntry para TableControl (formato)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Elemento TableRowEntries para TableControl (formato)](./tablerowentries-element-for-tablecontrol-format.md)

[Elemento Wrap para TableRowEntry para TableControl (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
