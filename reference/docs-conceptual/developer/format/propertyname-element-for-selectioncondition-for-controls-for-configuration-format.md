---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)
description: Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 5e4368a9546307c5ff223ae42ecaa1d2872bc587
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665950"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada é usada. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para CustomEntry para o elemento de configuração (Format) PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)

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
|[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Define uma condição que deve existir para que uma definição de controle comum seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade .NET.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos. Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
