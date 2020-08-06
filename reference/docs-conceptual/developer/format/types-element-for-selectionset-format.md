---
title: Elemento types para SelectionSet (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772511"
---
# <a name="types-element-for-selectionset-format"></a>Elemento Types para SelectionSet (formato)

Define os objetos .NET que estão no conjunto de seleção.

Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) elemento Types (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Types` elemento. Deve haver pelo menos um elemento filho, mas não há um limite máximo para o número de elementos filho que podem ser adicionados.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TypeName de tipos (Format)](./typename-element-for-types-format.md)|Elemento necessário.<br /><br /> Especifica o objeto .NET que pertence ao conjunto de seleção.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionSet (formato)](./selectionset-element-format.md)|Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.|

## <a name="remarks"></a>Comentários

Os objetos definidos por esse elemento compõem um conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.  Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `SelectionSet` elemento que define quatro tipos .net.

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

[Definindo conjuntos de objetos](./defining-selection-sets.md)

[Elemento SelectionSet (formato)](./selectionset-element-format.md)

[Elemento TypeName de tipos (Format)](./typename-element-for-types-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
