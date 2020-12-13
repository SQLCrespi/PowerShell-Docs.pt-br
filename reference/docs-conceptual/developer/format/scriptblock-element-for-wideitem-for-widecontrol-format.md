---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para WideItem para WideControl (formato)
description: Elemento ScriptBlock para WideItem para WideControl (formato)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659878"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Elemento ScriptBlock para WideItem para WideControl (formato)

Especifica o script cujo valor é exibido na exibição ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format) @ Element for WideItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)|Define a propriedade ou bloco de script cujo valor é exibido na exibição ampla.|

## <a name="text-value"></a>Valor de texto

Especifique o script cujo valor é exibido.

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `WideItem` elemento que define um script cujo valor é exibido na exibição.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>Consulte Também

[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
