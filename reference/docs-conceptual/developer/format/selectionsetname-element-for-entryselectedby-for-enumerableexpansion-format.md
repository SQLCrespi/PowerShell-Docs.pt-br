---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651887"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)

Especifica o conjunto de tipos .NET que são expandidos por essa definição.

Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)

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
|[Elemento EntrySelectedBy para EnumerableExpansion (formato)](./entryselectedby-element-for-enumerableexpansion-format.md)|Define os objetos da coleção .NET que são expandidos por essa definição.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção.

## <a name="remarks"></a>Comentários

Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.

Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições. Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos. Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).

## <a name="see-also"></a>Consulte Também

[Definir conjuntos de seleção](./defining-selection-sets.md)

[Elemento EntrySelectedBy para EnumerableExpansion (formato)](./entryselectedby-element-for-enumerableexpansion-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
