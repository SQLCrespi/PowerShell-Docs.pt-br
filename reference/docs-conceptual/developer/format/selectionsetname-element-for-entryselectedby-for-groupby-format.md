---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)
description: Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: 7ebe5d884061243c8b4af196788187d84c15a92e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651847"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a>Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)

Especifica um conjunto de objetos .NET para a entrada de lista. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionSetName GroupBy (Format) para EntrySelectedBy para GroupBy (Format)

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
|[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

Cada definição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições. Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos. Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).

Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).

## <a name="see-also"></a>Consulte Também

[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
