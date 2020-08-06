---
title: Elemento EntrySelectedBy para CustomEntry para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5c82e02d23b1694d05f7a32578ccc5d33686f13f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774245"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)

Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para os controles do elemento View (Format) EntrySelectedBy para CustomEntry para controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `EntrySelectedBy` elemento. Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que essa definição seja usada.|
|[Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição do controle.|
|[Elemento TypeName para EntrySelectedBy para Controls para View (formato)](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
