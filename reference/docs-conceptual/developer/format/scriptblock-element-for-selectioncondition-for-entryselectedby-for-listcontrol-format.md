---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659901"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)

Especifica o script que dispara a condição. Quando esse script é avaliado como `true` , a condição é atendida e a entrada da lista é usada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format) o elemento EntrySelectedBy para SelectionCondition para EntrySelectedBy (Format) ListEntry Element for SelectionCondition for EntrySelectedBy (Format) o elemento do ScriptBlock para ListEntry para ListEntry (Format)

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
|[Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Define a condição que deve existir para que essa entrada de lista seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos. (Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada ou item de exibição é usado](./defining-conditions-for-displaying-data.md).)

Para obter mais informações sobre os outros componentes de um modo de exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).

## <a name="see-also"></a>Consulte Também

[Elemento ListEntry (Format)](./listentry-element-for-listcontrol-format.md)

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Exibição de lista](./creating-a-list-view.md)

[Definindo condições para quando uma entrada ou item de exibição é usado](./defining-conditions-for-displaying-data.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
