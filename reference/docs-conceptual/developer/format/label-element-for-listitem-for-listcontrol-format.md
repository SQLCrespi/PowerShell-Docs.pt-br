---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para ListItem para ListControl (formato)
description: Elemento Label para ListItem para ListControl (formato)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666647"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Elemento Label para ListItem para ListControl (formato)

Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para ListControl (Format) ListEntry Element para ListControl (Format) ListItems para ListEntry para ListControl Element (Format) ListItem elemento para ListItems para o elemento de rótulo ListControl (Format) para ListItem para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem para ListItems para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o rótulo a ser exibido à esquerda do valor da propriedade ou do script.

## <a name="remarks"></a>Comentários

Se um rótulo não for especificado, o nome da propriedade ou do script será exibido. Para obter mais informações sobre como usar rótulos em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como adicionar um rótulo a uma linha.

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
