---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)
description: Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: 413a77f7ba06fe952e574061e58d0b5d80c5b3c4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651823"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a>Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)

Especifica um conjunto de objetos .NET para a entrada de lista. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `SelectionSetName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Define os tipos .NET que usam essa entrada de lista ou a condição que deve existir para que essa entrada seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições. Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos. Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).

Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar um conjunto de seleção para uma entrada de uma exibição de lista.

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento EntrySelectedBy para ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
