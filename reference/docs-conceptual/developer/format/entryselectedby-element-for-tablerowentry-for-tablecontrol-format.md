---
title: Elemento EntrySelectedBy para TableRowEntry para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363335"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)

Define os tipos .NET que usam essa definição da exibição de tabela ou a condição que deve existir para que essa definição seja usada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento TableControl (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para esta definição de exibição de tabela a ser usada.|
|[Elemento SelectionSetName para EntrySelectedBy para TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam esta definição de exibição de tabela.|
|[Elemento TypeName para EntrySelectedBy para TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa esta definição de exibição de tabela.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableRowEntry para TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Define os dados que são exibidos em uma linha da tabela.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de tabela. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true`. Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `TableRowEntry` que é usado para exibir as propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>Consulte Também

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Elemento SelectionCondition para EntrySelectedBy para TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[Elemento TableRowEntry para TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Elemento TypeName para EntrySelectedBy para TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
