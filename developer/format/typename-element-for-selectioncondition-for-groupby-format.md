---
title: Elemento TypeName para SelectionCondition para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083766"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a>Elemento TypeName para SelectionCondition para GroupBy (formato)

Especifica um tipo .NET que dispara a condição. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) EntrySelectedBy CustomEntry para elemento de GroupBy (formato) SelectionCondition EntrySelectedBy para elemento de TypeName GroupBy (formato) SelectionCondition para GroupBy (formato)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Define uma condição que deve existir para a definição de controle a ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Comentários

Quando esse elemento for especificado, é possível especificar o `SelectionSetName` elemento. Para obter mais informações sobre como definir as condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
