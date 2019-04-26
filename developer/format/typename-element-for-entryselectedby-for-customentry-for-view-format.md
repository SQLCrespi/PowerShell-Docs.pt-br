---
title: Elemento TypeName para EntrySelectedBy para CustomEntry para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083970"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)

Especifica um tipo .NET que usa essa definição da exibição de controle personalizado. Não há nenhum limite para o número de tipos que podem ser especificados para uma definição.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para EntrySelectedBy de exibição (formato) Elemento para CustomEntry para elemento de exibição (formato) TypeName EntrySelectedBy para CustomEntry para exibição (formato)

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
|[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Define os tipos de .NET que usam essa definição de exibição do controle personalizado ou a condição que deve existir para essa definição a ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Comentários

Cada definição de exibição do controle personalizado deve ter pelo menos um nome de tipo, conjunto de seleção ou condição de seleção definida.

Para obter mais informações sobre os componentes de uma exibição de controle personalizado, consulte [criação de controles personalizados](./creating-custom-controls.md).

## <a name="see-also"></a>Consulte Também

[Criação de controles personalizados](./creating-custom-controls.md)

[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
