---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ColumnNumber para WideControl (formato)
description: Elemento ColumnNumber para WideControl (formato)
ms.openlocfilehash: 1ddbbfbd5b53065afcc6c1326d6abf1fadedc67b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648394"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Elemento ColumnNumber para WideControl (formato)

Especifica o número de colunas exibidas na exibição ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) ColumnNumber elemento para WideControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ColumnNumber` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (formato)](./widecontrol-element-format.md)|Define um formato de lista largo (valor único) para a exibição.|

## <a name="text-value"></a>Valor de texto

Especifique um valor inteiro positivo.

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou o `ColumnNumber` elemento, mas não pode adicionar ambos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

Para obter um exemplo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento AutoSize para WideControl (Format)](./autosize-element-for-widecontrol-format.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Exibição ampla (Básica)](./wide-view-basic.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
