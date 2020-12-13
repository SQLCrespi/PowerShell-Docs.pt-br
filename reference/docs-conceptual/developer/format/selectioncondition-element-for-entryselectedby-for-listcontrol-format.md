---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655094"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a>Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)

Define a condição que deve existir para usar essa definição da exibição de lista. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que disparam a condição.|
|[Elemento TypeName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para TableRowEntry (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.|

## <a name="remarks"></a>Comentários

lWhen você está definindo uma condição de seleção, os seguintes requisitos se aplicam:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de lista](./creating-a-list-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento ListEntry (Format)](./listentry-element-for-listcontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para ListEntry (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Elemento TypeName para EntrySelectedBy para ListEntry (Format)](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
