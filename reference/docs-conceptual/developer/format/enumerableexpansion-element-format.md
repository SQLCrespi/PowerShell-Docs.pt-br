---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EnumerableExpansion (formato)
description: Elemento EnumerableExpansion (formato)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668007"
---
# <a name="enumerableexpansion-element-format"></a>Elemento EnumerableExpansion (formato)

Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.

Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansion` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para EnumerableExpansion (formato)](./entryselectedby-element-for-enumerableexpansion-format.md)|Elemento opcional.<br /><br /> Define quais objetos de coleção .NET são expandidos por essa definição.|
|[Elemento Expand (formato)](./expand-element-format.md)|Especifica como o objeto de coleção é expandido para essa definição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EnumerableExpansions (formato)](./enumerableexpansions-element-format.md)|Define as diferentes maneiras como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.|

## <a name="remarks"></a>Comentários

Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos. Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface  **System. Collections. ICollection** .

O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
