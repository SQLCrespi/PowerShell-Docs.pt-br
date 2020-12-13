---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideEntries para WideControl (formato)
description: Elemento WideEntries para WideControl (formato)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651235"
---
# <a name="wideentries-element-for-widecontrol-format"></a>Elemento WideEntries para WideControl (formato)

Fornece as definições da exibição ampla. A exibição ampla deve especificar uma ou mais definições.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) WideEntries elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntries` elemento. Pelo menos um elemento filho deve ser especificado.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (formato)](./widecontrol-element-format.md)|Define um formato de lista largo (valor único) para a exibição.|

## <a name="remarks"></a>Comentários

Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto. Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `WideEntries` elemento que define um único `WideEntry` elemento. O `WideEntry` elemento contém um único `WideItem` elemento que define qual valor de propriedade ou script é exibido na exibição.

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Elemento WideControl (formato)](./widecontrol-element-format.md)

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
