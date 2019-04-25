---
title: Elemento AutoSize para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066916"
---
# <a name="autosize-element-for-widecontrol-format"></a>Elemento AutoSize para WideControl (formato)

Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento WideControl (formato) Autosize elemento de configuração para WideControl (formato)

## <a name="syntax"></a>Sintaxe

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `AutoSize` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Não

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (formato)](./widecontrol-element-format.md)|Define uma ampla (único valor) formato de lista para o modo de exibição.|

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou o [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) elemento, mas você não pode adicionar ambos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

Para obter um exemplo de uma exibição ampla, consulte [exibição ampla (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento ColumnNumber para WideControl (formato)](./columnnumber-element-for-widecontrol-format.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Elemento WideControl (formato)](./widecontrol-element-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
