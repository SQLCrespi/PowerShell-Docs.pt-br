---
title: Elemento WideItem para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779889"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideItem` elemento. O elemento `FormatString` é opcional. No entanto, você deve especificar um `PropertyName` `ScriptBlock` elemento ou, mas não pode especificar ambos.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento FormatString para WideItem para WideControl (formato)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.|
|[Elemento PropertyName para WideItem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.|
|[Elemento ScriptBlock para WideItem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Especifica o script cujo valor é exibido na exibição ampla.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)|Fornece uma definição da exibição ampla.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento. O `WideItem` elemento define a propriedade ou o script cujo valor é exibido na exibição.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento FormatString para WideItem para WideControl (formato)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Elemento PropertyName para WideItem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Elemento ScriptBlock para WideItem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
