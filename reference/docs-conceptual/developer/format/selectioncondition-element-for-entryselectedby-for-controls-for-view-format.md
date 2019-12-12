---
title: Elemento SelectionCondition para EntrySelectedBy para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362045"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)

Define uma condição que deve existir para que a definição de controle seja usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View ( Ao

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionCondition`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para SelectionCondition para controles para View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica uma propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para SelectionCondition para controles para View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|
|[Elemento SelectionSetName para SelectionCondition para controles para View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o conjunto de tipos .NET que dispara a condição.|
|[Elemento TypeName para SelectionCondition para controles para View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que dispara a condição.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para controles para View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.|

## <a name="remarks"></a>Comentários

Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:

- A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para SelectionCondition para controles para View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[Elemento ScriptBlock para SelectionCondition para controles para View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[Elemento SelectionSetName para SelectionCondition para controles para View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[Elemento TypeName para SelectionCondition para controles para View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[Elemento EntrySelectedBy para CustomEntry para controles para View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
