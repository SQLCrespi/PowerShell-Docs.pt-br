---
title: Elemento EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774041"
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

Nenhum.

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

Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos. Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .

O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
