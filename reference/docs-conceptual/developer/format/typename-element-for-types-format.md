---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para Types (formato)
description: Elemento TypeName para Types (formato)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664611"
---
# <a name="typename-element-for-types-format"></a>Elemento TypeName para Types (formato)

Especifica o tipo .NET de um objeto que pertence ao conjunto de seleção.

Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) tipos de elemento de tipo (Format) elemento TypeName dos tipos (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TypeName` elemento. Pelo menos um `TypeName` elemento deve ser incluído no conjunto de seleção.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Types (formato)](./types-element-for-selectionset-format.md)|Define os objetos .NET que estão no conjunto de seleção.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado para o tipo .NET.

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.

Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação. Nesses casos, o `SelectionSetName` elemento filho do elemento da `ViewSelectedBy` exibição especifica o conjunto. No entanto, entradas diferentes de uma exibição também podem especificar um conjunto de seleção que se aplica somente a essa entrada da exibição. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos .net.

```
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

[Elemento SelectionSets (formato)](./selectionsets-element-format.md)

[Elemento Types (formato)](./types-element-for-selectionset-format.md)

[Escrever um arquivo de formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
