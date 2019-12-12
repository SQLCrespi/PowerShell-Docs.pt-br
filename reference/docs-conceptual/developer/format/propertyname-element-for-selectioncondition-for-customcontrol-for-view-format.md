---
title: Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362345"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>Elemento PropertyName para SelectionCondition para CustomControl para View (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl for View ( Format) elemento CustomItem para CustomEntry para CustomControl para o elemento View (Format) EntrySelectedBy para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para View (Format) PropertyName Elemento para SelectionCondition para CustomControl para exibição (formato)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Define uma condição que deve existir para que a definição de controle seja usada.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome da propriedade .NET.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos. Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
