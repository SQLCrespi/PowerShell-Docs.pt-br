---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para Controls para View (formato)
description: Elemento PropertyName para SelectionCondition para Controls para View (formato)
ms.openlocfilehash: 7783e5a9b7f8ec3d3077d87778e9f77ffe858a7f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665865"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a>Elemento PropertyName para SelectionCondition para Controls para View (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada é usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para controles para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para o elemento View (Format) PropertyName para SelectionCondition para controles para View (Format)

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
|[Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Define uma condição que deve existir para que a definição de controle seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade .NET.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos. Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
