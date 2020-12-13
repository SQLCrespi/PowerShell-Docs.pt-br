---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)
description: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 2fb09e27eef1ce5d6e864c72edb595817d91f729
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655050"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)

Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição de tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy para TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Define a condição que deve existir para ser usada para esta definição da exibição de tabela.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define. Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
