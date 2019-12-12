---
title: Elemento SelectionSet (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368375"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `SelectionSet`. Cada conjunto de seleção deve ter um nome e deve especificar os objetos .NET do conjunto.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Name para SelectionSet (Format)](./name-element-for-selectionset-format.md)|Elemento obrigatório.<br /><br /> Especifica o nome usado para fazer referência ao conjunto de seleção.|
|[Elemento Types (formato)](./types-element-for-selectionset-format.md)|Elemento obrigatório.<br /><br /> Define os objetos .NET que estão no conjunto de seleção.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Formato do elemento SelectionSets](./selectionsets-element-format.md)|Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.

Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições. Nesses casos, o `SelectionSetName` elemento filho dos elementos `ViewSelectedBy` e `EntrySelectedBy` especifica o conjunto a ser usado. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `SelectionSet` que define quatro tipos .NET.

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

[Definindo conjuntos de seleção](./defining-selection-sets.md)

[Elemento Name de SelectionSet (Format)](./name-element-for-selectionset-format.md)

[Elemento SelectionSets (Format)](./selectionsets-element-format.md)

[Elemento Types (formato)](./types-element-for-selectionset-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
