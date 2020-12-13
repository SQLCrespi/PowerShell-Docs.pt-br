---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)
description: Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 4177aace5a6a9374900e7339167c69b531c1e2e7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651667"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)

Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para o elemento de configuração (Format) SelectionSetName para SelectionCondition para controles para configuração (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Define uma condição que deve existir para que a definição de controle seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define. Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Definir conjuntos de seleção](./defining-selection-sets.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
