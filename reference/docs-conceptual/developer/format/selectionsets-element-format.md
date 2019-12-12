---
title: Elemento SelectionSets (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebbac73a-1c99-4388-9f47-703cd024dc6d
caps.latest.revision: 18
ms.openlocfilehash: a9356635d60d5f8c5d4dec4ec8b7d0aea2b037dd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361865"
---
# <a name="selectionsets-element-format"></a>Elemento SelectionSets (formato)

Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação. As exibições e os controles do arquivo de formatação podem fazer referência ao conjunto completo de objetos usando apenas o nome do conjunto de seleção.

Formato do elemento SelectionSets do elemento de configuração

## <a name="syntax"></a>Sintaxe

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `SelectionSets`. Cada elemento filho define um conjunto de objetos que podem ser referenciados pelo nome do conjunto. A ordem dos elementos filho não é significativa.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionSet (formato)](./selectionset-element-format.md)|Elemento obrigatório.<br /><br /> Define um único conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de configuração](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança. Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.

Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições. Nesses casos, o `SelectionSetName` elemento filho dos elementos `ViewSelectedBy` e `EntrySelectedBy` especifica o conjunto a ser usado. Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="see-also"></a>Consulte Também

[Elemento de configuração](./configuration-element-format.md)

[Definindo conjuntos de seleção](./defining-selection-sets.md)

[Elemento SelectionSet (formato)](./selectionset-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
