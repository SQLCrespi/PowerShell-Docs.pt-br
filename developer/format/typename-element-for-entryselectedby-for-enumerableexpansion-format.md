---
title: Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0506928-db92-4ec4-855f-6f3592a383ae
caps.latest.revision: 6
ms.openlocfilehash: 5ead806d956ebbef95eeffc42bb39ef784208017
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083987"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a>Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato)

Especifica um tipo .NET que é expandido por essa definição. Esse elemento é usado ao definir uma configuração padrão.

Elemento (formato) elemento DefaultSettings (formato) elemento EnumerableExpansions (formato) elemento EnumerableExpansion (formato) EntrySelectedBy elemento de configuração para elemento de TypeName EnumerableExpansion (formato) EntrySelectedBy para EnumerableExpansion (formato)

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
|[Elemento EntrySelectedBy para EnumerableExpansion (formato)](./entryselectedby-element-for-enumerableexpansion-format.md)|Define os tipos de .NET que usam essa definição ou a condição que deve existir para essa definição a ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento EntrySelectedBy para EnumerableExpansion (formato)](./entryselectedby-element-for-enumerableexpansion-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
