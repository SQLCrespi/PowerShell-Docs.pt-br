---
title: Elemento TypeName para tipos (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368025"
---
# <a name="typename-element-for-types-format"></a>Elemento TypeName para Types (formato)

Especifica o tipo .NET de um objeto que pertence ao conjunto de seleção.

Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) tipos de elemento de tipo (Format) elemento TypeName dos tipos (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `TypeName`. Pelo menos um elemento de `TypeName` deve ser incluído no conjunto de seleção.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Types (formato)](./types-element-for-selectionset-format.md)|Define os objetos .NET que estão no conjunto de seleção.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome totalmente qualificado para o tipo .NET.

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.

Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação. Nesses casos, o elemento filho `SelectionSetName` do elemento `ViewSelectedBy` da exibição especifica o conjunto. No entanto, entradas diferentes de uma exibição também podem especificar um conjunto de seleção que se aplica somente a essa entrada da exibição. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `SelectionSet` que define quatro tipos .NET.

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

[Definindo conjuntos de seleção](./defining-selection-sets.md)

[Elemento SelectionSet (formato)](./selectionset-element-format.md)

[Elemento SelectionSets (Format)](./selectionsets-element-format.md)

[Elemento Types (formato)](./types-element-for-selectionset-format.md)

[Escrevendo um arquivo de formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
