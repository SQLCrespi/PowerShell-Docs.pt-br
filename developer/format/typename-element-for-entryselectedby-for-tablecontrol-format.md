---
title: Elemento TypeName para EntrySelectedBy para TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083953"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>Elemento TypeName para EntrySelectedBy para TableControl (formato)

Especifica um tipo .NET que usa essa entrada da exibição de tabela. Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de tabela.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento TableControl (formato) elemento TableRowEntries (formato) elemento TableRowEntry (formato) elemento EntrySelectedBy (formato) TypeName elemento de configuração para EntrySelectedBy para TableRowEntry (formato)

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
|[Elemento EntrySelectedBy (formato)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Define os tipos de .NET que usam essa entrada ou a condição que deve existir para essa entrada a ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do tipo .NET.

## <a name="remarks"></a>Comentários

Cada entrada da lista deve ter pelo menos um nome de tipo, conjunto de seleção ou condição de seleção definida.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="see-also"></a>Consulte Também

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Elemento EntrySelectedBy (formato)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
