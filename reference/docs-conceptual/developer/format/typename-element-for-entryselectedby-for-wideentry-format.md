---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para WideEntry (formato)
description: Elemento TypeName para EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654788"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a>Elemento TypeName para EntrySelectedBy para WideEntry (formato)

Especifica um tipo .NET para a definição. A definição é usada sempre que este objeto é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) TypeName Element for WideEntry (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TypeName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para WideEntry (formato)](./entryselectedby-element-for-wideentry-format.md)|Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Comentários

Cada entrada larga deve especificar um ou mais tipos .NET, um conjunto de seleção ou a condição de seleção que deve existir para a definição a ser usada.

Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Elemento EntrySelectedBy para WideEntry (formato)](./entryselectedby-element-for-wideentry-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
