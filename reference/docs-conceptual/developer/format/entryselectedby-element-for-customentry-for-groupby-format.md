---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)
description: Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652353"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)

Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy elemento para CustomEntry para GroupBy (Format)

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

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que essa definição seja usada.|
|[Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição do controle.|
|[Elemento TypeName para EntrySelectedBy para GroupBy (formato)](./typename-element-for-entryselectedby-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para GroupBy (formato)](./customentry-element-for-customcontrol-for-groupby-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[Elemento TypeName para EntrySelectedBy para GroupBy (formato)](./typename-element-for-entryselectedby-for-groupby-format.md)

[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
