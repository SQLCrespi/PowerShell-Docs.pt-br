---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Expand (formato)
description: Elemento Expand (formato)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667939"
---
# <a name="expand-element-format"></a>Elemento Expand (formato)

Especifica como o objeto de coleção é expandido para essa definição.

Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) Expand elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Expand` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EnumerableExpansion (formato)](./enumerableexpansion-element-format.md)|Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.|

## <a name="text-value"></a>Valor de texto

Especifique um dos seguintes valores:

- EnumOnly: exibe somente as propriedades dos objetos na coleção.

- CoreOnly: exibe somente as propriedades do objeto de coleção.

- Ambos: exibe as propriedades dos objetos na coleção e as propriedades do objeto da coleção.

## <a name="remarks"></a>Comentários

Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos. Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface  **System. Collections. ICollection** .

O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
