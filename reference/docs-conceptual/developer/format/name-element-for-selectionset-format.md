---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para SelectionSet (formato)
description: Elemento Name para SelectionSet (formato)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666444"
---
# <a name="name-element-for-selectionset-format"></a>Elemento Name para SelectionSet (formato)

Especifica o nome usado para fazer referência ao conjunto de seleção.

Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format) nomear elemento de SelectionSet (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Name` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionSet (formato)](./selectionset-element-format.md)|Define um único conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.|

## <a name="text-value"></a>Valor de texto

Especifique o nome para fazer referência ao conjunto de seleção. Não há restrições sobre quais caracteres podem ser usados.

## <a name="remarks"></a>Comentários

O nome especificado aqui é usado no `SelectionSetName` elemento. O conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `SelectionSet` elemento que define quatro tipos .net. O nome do conjunto de seleção é "FileSystemTypes".

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

[Elemento SelectionSet (formato)](./selectionset-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
