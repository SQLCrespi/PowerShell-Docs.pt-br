---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652326"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>Elemento EntrySelectedBy para EnumerableExpansion (formato)

Define os tipos .NET que usam essa definição ou a condição que deve existir para que essa definição seja usada.

Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para expandir os objetos de coleção dessa definição.|
|[Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição de como os objetos de coleção são expandidos.|
|[Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição de como os objetos de coleção são expandidos.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EnumerableExpansion (formato)](./enumerableexpansion-element-format.md)|Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada de definição. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Definir condições para a exibição de dados](./defining-conditions-for-displaying-data.md)

[Elemento EnumerableExpansion (formato)](./enumerableexpansion-element-format.md)

[Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
