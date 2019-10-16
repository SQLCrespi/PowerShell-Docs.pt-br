---
title: Elemento ColumnNumber para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364215"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Elemento ColumnNumber para WideControl (formato)

Especifica o número de colunas exibidas na exibição ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) ColumnNumber elemento para WideControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ColumnNumber`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (Format)](./widecontrol-element-format.md)|Define um formato de lista largo (valor único) para a exibição.|

## <a name="text-value"></a>Valor de texto

Especifique um valor inteiro positivo.

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o elemento `AutoSize` ou o elemento `ColumnNumber`, mas não pode adicionar ambos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

Para obter um exemplo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento AutoSize para WideControl (Format)](./autosize-element-for-widecontrol-format.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Exibição ampla (básica)](./wide-view-basic.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
