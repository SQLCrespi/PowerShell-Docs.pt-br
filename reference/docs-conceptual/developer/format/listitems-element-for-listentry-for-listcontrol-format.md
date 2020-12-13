---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListItems para ListEntry para ListControl (formato)
description: Elemento ListItems para ListEntry para ListControl (formato)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666528"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>Elemento ListItems para ListEntry para ListControl (formato)

Define as propriedades e os scripts cujos valores são exibidos nas linhas da exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento de controle de lista (Format) ListEntry para o elemento ListControl (Format) ListItems para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListItems` elemento. Não há nenhum limite para o número de elementos filho que podem ser especificados. A ordem dos elementos filho define a ordem em que os valores são exibidos na exibição de lista.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Elemento necessário.<br /><br /> Define a propriedade ou o script cujo valor é exibido pela exibição de lista.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListEntry para ListControl (formato)](./listentry-element-for-listcontrol-format.md)|Fornece uma definição da exibição de lista.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre esse tipo de exibição, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra os elementos XML que definem três linhas da exibição de lista.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>Consulte Também

[Elemento ListEntry para ListControl (formato)](./listentry-element-for-listcontrol-format.md)

[Elemento ListItem para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
