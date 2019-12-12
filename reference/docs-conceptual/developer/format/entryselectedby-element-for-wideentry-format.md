---
title: Elemento EntrySelectedBy para WideEntry (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363325"
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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para essa definição de exibição ampla ser usada.|
|[Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição de exibição ampla.|
|[Elemento TypeName para EntrySelectedBy para WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição de exibição ampla.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição ampla. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade específico ou um valor de script é avaliado como `true`. Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="see-also"></a>Consulte Também

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento TypeName para EntrySelectedBy para WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Definindo condições para exibir dados](./defining-conditions-for-displaying-data.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
