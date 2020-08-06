---
title: Elemento SelectionCondition para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4115ad1ee8729ea4fc16bc19698018d2f4ed9be1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772698"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a>Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)

Define a condição que deve existir para que essa definição seja usada. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de entrada ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento. Você deve especificar um único `PropertyName` `ScriptBlock` elemento ou. Os `SelectionSetName` `TypeName` elementos e são opcionais. Você pode especificar um de ambos os elementos.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o bloco de script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que dispara a condição.|
|[Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para WideEntry (formato)](./entryselectedby-element-for-wideentry-format.md)|Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.|

## <a name="remarks"></a>Comentários

Cada entrada larga deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento EntrySelectedBy para WideEntry (formato)](./entryselectedby-element-for-wideentry-format.md)

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
