---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para TableControl (formato)
description: Elemento TypeName para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651430"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>Elemento TypeName para EntrySelectedBy para TableControl (formato)

Especifica um tipo .NET que usa essa entrada da exibição de tabela. Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Define os tipos .NET que usam essa entrada ou a condição que deve existir para que essa entrada seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do tipo .NET.

## <a name="remarks"></a>Comentários

Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento EntrySelectedBy (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
