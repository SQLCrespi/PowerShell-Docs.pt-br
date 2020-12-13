---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)
description: Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655344"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)

Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que essa definição seja usada.|
|[Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição do modo de exibição de controle.|
|[Elemento TypeName para EntrySelectedBy para CustomEntry (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição do modo de exibição de controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Define os controles usados por objetos .NET específicos.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para a entrada a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [modo de exibição de controle personalizado](./creating-custom-controls.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[Elemento TypeName para EntrySelectedBy para CustomEntry (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Exibição de controle personalizado](./creating-custom-controls.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
