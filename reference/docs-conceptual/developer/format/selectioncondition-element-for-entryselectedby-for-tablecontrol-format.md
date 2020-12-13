---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)
description: Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645758"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)

Define a condição que deve existir para ser usada para esta definição da exibição de tabela. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento SelectionCondition.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que disparam a condição.|
|[Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para TableRowEntry (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.|

## <a name="remarks"></a>Comentários

Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento EntrySelectedBy (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
