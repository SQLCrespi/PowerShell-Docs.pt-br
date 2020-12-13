---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)
description: Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645774"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)

Define uma condição que deve existir para que uma definição de controle comum seja usada. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para EntrySelectedBy para CustomEntry para a configuração (Format)

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
|[Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica uma propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que dispara a condição.|
|[Elemento TypeName para SelectionCondition para Controls para Configuration (formato)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Define os tipos .NET que usam essa entrada da definição de controle comum.|

## <a name="remarks"></a>Comentários

As diretrizes a seguir devem ser seguidas ao definir uma condição de seleção:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Elemento TypeName para SelectionCondition para Controls para Configuration (formato)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
