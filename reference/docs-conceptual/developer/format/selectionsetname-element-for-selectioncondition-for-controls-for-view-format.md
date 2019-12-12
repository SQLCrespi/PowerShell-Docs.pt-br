---
title: Elemento SelectionSetName para SelectionCondition para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: daea8c6f-873a-4639-9eee-599642822958
caps.latest.revision: 6
ms.openlocfilehash: 697f2ea284393ebddd77a862c408f27f3d332900
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361965"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a>Elemento SelectionSetName para SelectionCondition para Controls para View (formato)

Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View ( Format) elemento SelectionSetName para SelectionCondition para controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Define uma condição que deve existir para que a definição de controle seja usada.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define. Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).

A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Definindo conjuntos de seleção](./defining-selection-sets.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
