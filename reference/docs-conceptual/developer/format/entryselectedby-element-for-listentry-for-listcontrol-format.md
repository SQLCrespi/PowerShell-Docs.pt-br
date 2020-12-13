---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para ListEntry para ListControl (formato)
description: Elemento EntrySelectedBy para ListEntry para ListControl (formato)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652291"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>Elemento EntrySelectedBy para ListEntry para ListControl (formato)

Define os tipos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada. Na maioria dos casos, apenas uma definição é necessária para uma exibição de lista. No entanto, você pode fornecer várias definições para o modo de exibição de lista se quiser usar a mesma exibição de lista para exibir dados diferentes para objetos diferentes.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntry para o elemento ListControl (Format) EntrySelectedBy para ListEntry para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `EntrySelectedBy` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para esta definição de exibição de lista ser usada.|
|[Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam esta definição de exibição de lista.|
|[Elemento TypeName para EntrySelectedBy para ListControl (formato)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição de exibição de lista.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListEntry para ListControl (formato)](./listentry-element-for-listcontrol-format.md)|Define como as linhas da lista são exibidas.|

## <a name="remarks"></a>Comentários

Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de lista. Não há nenhum limite máximo para o número de elementos filho que você pode usar.

As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` . Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como definir os objetos para um modo de exibição de lista usando o nome do tipo .NET.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>Consulte Também

[Elemento ListEntry para ListControl (formato)](./listentry-element-for-listcontrol-format.md)

[Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Elemento TypeName para EntrySelectedBy para ListControl (formato)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
