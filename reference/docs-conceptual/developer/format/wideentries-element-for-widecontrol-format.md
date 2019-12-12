---
title: Elemento WideEntries para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361425"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideEntries`. Pelo menos um elemento filho deve ser especificado.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideControl (Format)](./widecontrol-element-format.md)|Define um formato de lista largo (valor único) para a exibição.|

## <a name="remarks"></a>Comentários

Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto. Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `WideEntries` que define um único elemento `WideEntry`. O elemento `WideEntry` contém um único elemento `WideItem` que define qual valor de propriedade ou script é exibido na exibição.

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

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Elemento WideControl (Format)](./widecontrol-element-format.md)

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
