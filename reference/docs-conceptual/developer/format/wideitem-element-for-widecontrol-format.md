---
title: Elemento WideItem para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361395"
---
# <a name="wideitem-element-for-widecontrol-format"></a>Elemento WideItem para WideControl (formato)

Define a propriedade ou o script cujo valor é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideItem`. O elemento `FormatString` é opcional. No entanto, você deve especificar um elemento `PropertyName` ou `ScriptBlock`, mas não pode especificar ambos.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento FormatString para WideItem para WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.|
|[Elemento PropertyName para WideItem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.|
|[Elemento ScriptBlock para WideItem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Especifica o script cujo valor é exibido na exibição ampla.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `WideEntry` que define um único elemento `WideItem`. O elemento `WideItem` define a propriedade ou o script cujo valor é exibido na exibição.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento FormatString para WideItem para WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Elemento PropertyName para WideItem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Elemento ScriptBlock para WideItem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
