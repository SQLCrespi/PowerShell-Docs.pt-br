---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para WideEntry (formato)
description: Elemento EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660241"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>Elemento EntrySelectedBy para WideEntry (formato)

Define os tipos .NET que usam essa definição da exibição larga ou a condição que deve existir para que essa definição seja usada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element for WideEntry (Format)

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
|[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para essa definição de exibição ampla ser usada.|
|[Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição de exibição ampla.|
|[Elemento TypeName para EntrySelectedBy para WideEntry (formato)](./typename-element-for-entryselectedby-for-wideentry-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição de exibição ampla.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição ampla. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou valor de script específico é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="see-also"></a>Consulte Também

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento TypeName para EntrySelectedBy para WideEntry (formato)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Definir condições para a exibição de dados](./defining-conditions-for-displaying-data.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
