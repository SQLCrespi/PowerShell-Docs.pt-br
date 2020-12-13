---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ListItem para ListControl (formato)
description: Elemento ScriptBlock para ListItem para ListControl (formato)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664978"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Elemento ScriptBlock para ListItem para ListControl (formato)

Especifica o script cujo valor é exibido na linha.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ScriptBlock (Format) para ListItem para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
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
|[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o script cujo valor é exibido na linha.

## <a name="remarks"></a>Comentários

Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .

Para obter mais informações sobre como especificar scripts em uma exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar a propriedade cujo valor é exibido.

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para ListItem para ListControl (formato)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento ListItem para ListItems para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
