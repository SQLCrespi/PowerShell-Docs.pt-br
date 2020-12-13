---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSet (formato)
description: Elemento SelectionSet (formato)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647874"
---
# <a name="selectionset-element-format"></a>Elemento SelectionSet (formato)

Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.

Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSet` elemento. Cada conjunto de seleção deve ter um nome e deve especificar os objetos .NET do conjunto.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Name para SelectionSet (formato)](./name-element-for-selectionset-format.md)|Elemento necessário.<br /><br /> Especifica o nome usado para fazer referência ao conjunto de seleção.|
|[Elemento Types (formato)](./types-element-for-selectionset-format.md)|Elemento necessário.<br /><br /> Define os objetos .NET que estão no conjunto de seleção.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Formato do elemento SelectionSets](./selectionsets-element-format.md)|Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.

Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições. Nesses casos, o `SelectionSetName` elemento filho dos `ViewSelectedBy` `EntrySelectedBy` elementos e especifica o conjunto a ser usado. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos .net.

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

## <a name="see-also"></a>Consulte Também

[Definir conjuntos de seleção](./defining-selection-sets.md)

[Elemento Name de SelectionSet (Format)](./name-element-for-selectionset-format.md)

[Elemento SelectionSets (formato)](./selectionsets-element-format.md)

[Elemento Types (formato)](./types-element-for-selectionset-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
