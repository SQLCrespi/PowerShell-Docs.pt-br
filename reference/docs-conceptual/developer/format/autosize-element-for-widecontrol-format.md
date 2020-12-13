---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento AutoSize para WideControl (formato)
description: Elemento AutoSize para WideControl (formato)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650005"
---
# <a name="autosize-element-for-widecontrol-format"></a>Elemento AutoSize para WideControl (formato)

Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) AutoSize Element para WideControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `AutoSize` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

Nenhum

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (formato)](./widecontrol-element-format.md)|Define um formato de lista largo (valor único) para a exibição.|

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou o elemento [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) , mas não pode adicionar ambos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

Para obter um exemplo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento ColumnNumber para WideControl (formato)](./columnnumber-element-for-widecontrol-format.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Elemento WideControl (formato)](./widecontrol-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
