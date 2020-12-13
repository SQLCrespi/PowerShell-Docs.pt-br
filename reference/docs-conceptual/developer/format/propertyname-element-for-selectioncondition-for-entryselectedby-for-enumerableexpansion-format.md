---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665831"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a definição é usada.

Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Define a condição que deve existir para expandir os objetos de coleção dessa definição.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade .NET.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
