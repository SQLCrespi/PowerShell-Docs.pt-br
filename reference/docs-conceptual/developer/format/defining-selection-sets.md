---
ms.date: 09/13/2016
ms.topic: reference
title: Definir conjuntos de seleção
description: Definir conjuntos de seleção
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648262"
---
# <a name="defining-selection-sets"></a>Definir conjuntos de seleção

Ao criar vários modos de exibição e controles, você pode definir conjuntos de objetos que são chamados de conjuntos de seleção. Um conjunto de seleção permite que você defina os objetos uma vez, sem precisar defini-los repetidamente para cada exibição ou controle. Normalmente, os conjuntos de seleção são usados quando você tem um conjunto de objetos .NET relacionados. Por exemplo, o `FileSystem` arquivo de formatação (FileSystem.format.ps1XML) define um conjunto de seleção dos tipos de sistema de arquivos que várias exibições usam.

## <a name="where-selection-sets-are-defined-and-referenced"></a>Onde os conjuntos de seleção são definidos e referenciados

Você define conjuntos de seleção como parte dos dados comuns que podem ser usados por todos os modos de exibição e controles definidos no arquivo de formatação. O exemplo a seguir mostra como definir três conjuntos de seleção.

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

Você pode fazer referência a um conjunto de seleção das seguintes maneiras:

- Cada exibição tem um `ViewSelectedBy` elemento que define quais objetos são exibidos usando a exibição. O `ViewSelectedBy` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que todas as definições da exibição usam. Não há nenhuma restrição quanto ao número de conjuntos de seleção que você pode referenciar em uma exibição.

- Em cada definição de um modo de exibição ou controle, o `EntrySelectedBy` elemento define quais objetos são exibidos usando essa definição. Normalmente, um modo de exibição ou controle tem apenas uma definição para que os objetos sejam definidos pelo `ViewSelectedBy` elemento. O `EntrySelectedBy` elemento da definição tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção. Se você especificar o conjunto de seleção para uma definição, não poderá especificar nenhum dos outros elementos filho do `EntrySelectedBy` elemento.

- Em cada definição de um modo de exibição ou controle, o `SelectionCondition` elemento pode ser usado para especificar uma condição para quando a definição é usada. O `SelectionCondition` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que dispara a condição. A condição é disparada quando qualquer um dos objetos definidos no conjunto de seleção é exibido. Para obter mais informações sobre como definir essas condições, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).

## <a name="selection-set-example"></a>Exemplo de conjunto de seleção

O exemplo a seguir mostra um conjunto de seleção que é obtido diretamente do `FileSystem` arquivo de formatação fornecido pelo Windows PowerShell. Para obter mais informações sobre outros arquivos de formatação do Windows PowerShell, consulte [arquivos de formatação do Windows PowerShell](./powershell-formatting-files.md).

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

O conjunto de seleção anterior é referenciado no `ViewSelectedBy` elemento de uma exibição de tabela.

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a>Elementos XML

 Não há nenhum limite para o número de conjuntos de seleção que você pode definir. Os seguintes elementos XML são usados para criar um conjunto de seleção.

- O elemento [SelectionSets](./selectionsets-element-format.md) define os conjuntos de objetos .NET que são referenciados pelas exibições e pelos controles do arquivo de formatação.

- O elemento [SelectionSet](./selectionset-element-format.md) define um único conjunto de objetos .net.

- O elemento [Name](./name-element-for-selectionset-format.md) especifica o nome que é usado para referenciar o conjunto de seleção.

- O elemento [Types](./types-element-for-selectionset-format.md) especifica os tipos .net dos objetos do conjunto de seleção. (Em arquivos de formatação, os objetos são especificados por seu tipo .NET.)

 Os seguintes elementos XML são usados para especificar um conjunto de seleção.

- O elemento a seguir especifica o conjunto de seleção a ser usado em todas as definições da exibição:

  - [Elemento SelectionSetName para ViewSelectedBy (formato)](./selectionsetname-element-for-viewselectedby-format.md)

  - [Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- Os elementos a seguir especificam o conjunto de seleção usado por uma única definição de exibição:

  - [Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- Os elementos a seguir especificam o conjunto de seleção usado pelas definições de controle comum e de exibição:

  - [Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- Os seguintes elementos especificam o conjunto de seleção usado quando você define qual objeto expandir:

  - [Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Os elementos a seguir especificam o conjunto de seleção usado por condições de seleção.

  - [Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [Elemento SelectionSetName para SelectionCondition para Controls para View (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [Elemento SelectionSetName para SelectionCondition para CustomControl para View (formato)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [Elemento SelectionSetName para SelectionCondition para GroupBy (formato)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>Consulte Também

[SelectionSets](./selectionsets-element-format.md)

[Selecionador de seleção](./selectionset-element-format.md)

[Nome](./name-element-for-selectionset-format.md)

[Types](./types-element-for-selectionset-format.md)

[Arquivos de formatação do PowerShell](./powershell-formatting-files.md)

[Definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md)

[Gravando um arquivo de tipos e formatação do PowerShell](./writing-a-powershell-formatting-file.md)
