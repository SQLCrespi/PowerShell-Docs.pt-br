---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ListItem para ListControl (formato)
description: Elemento PropertyName para ListItem para ListControl (formato)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665967"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>Elemento PropertyName para ListItem para ListControl (formato)

Especifica a propriedade .NET cujo valor é exibido na lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) NomeDaPropriedade Element for ListItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido na linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade cujo valor é exibido.

## <a name="remarks"></a>Comentários

Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .

Além de exibir o valor da propriedade, você também pode especificar um rótulo para o valor ou uma cadeia de caracteres de formato que possa ser usada para alterar a exibição do valor. Para obter mais informações sobre como especificar dados em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar o rótulo e a propriedade cujo valor é exibido.

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>Consulte Também

[Elemento ScriptBlock para ListItem para ListControl (formato)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento ListItem para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
