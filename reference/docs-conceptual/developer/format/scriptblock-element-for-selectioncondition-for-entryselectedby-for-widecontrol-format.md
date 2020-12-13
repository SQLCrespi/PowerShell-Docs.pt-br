---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651961"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)

Especifica o script que dispara a condição. Quando esse script é avaliado como `true` , a condição é atendida e a definição de entrada larga é usada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Define a condição que deve existir para que essa definição seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
