---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)
description: Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664745"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a>Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)

Define uma condição que deve existir para que uma definição de controle seja usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionCondition GroupBy (Format) para EntrySelectedBy para GroupBy (Format)

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
|[Elemento PropertyName para SelectionCondition para GroupBy (formato)](./propertyname-element-for-selectioncondition-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica uma propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para GroupBy (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para GroupBy (formato)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que dispara a condição.|
|[Elemento TypeName para SelectionCondition para GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.|

## <a name="remarks"></a>Comentários

Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para SelectionCondition para CustomControl para View (formato)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Elemento SelectionSetName para SelectionCondition para controle personalizado para exibição (formato)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Elemento TypeName para SelectionCondition para GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
