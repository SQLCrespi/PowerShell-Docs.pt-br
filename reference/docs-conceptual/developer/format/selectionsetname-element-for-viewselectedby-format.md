---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para ViewSelectedBy (formato)
description: Elemento SelectionSetName para ViewSelectedBy (formato)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654902"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>Elemento SelectionSetName para ViewSelectedBy (formato)

Especifica um conjunto de objetos .NET que são exibidos pela exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento ViewSelectedBy Element (Format) SelectionSetName elemento para ViewSelectedBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSetName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ViewSelectedBy (formato)](./viewselectedby-element-format.md)|Define os objetos .NET que são exibidos pela exibição.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do conjunto de seleção definido pelo `Name` elemento para o conjunto de seleção.

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Para obter mais informações sobre como definir e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar um conjunto de seleção para uma exibição de lista. O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>Consulte Também

[Definir conjuntos de seleção](./defining-selection-sets.md)

[Elemento ViewSelectedBy (formato)](./viewselectedby-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
