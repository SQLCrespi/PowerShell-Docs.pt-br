---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListItem para ListItems para ListControl (formato)
description: Elemento ListItem para ListItems para ListControl (formato)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666545"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>Elemento ListItem para ListItems para ListControl (formato)

Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems de ListControl (Format) ListItem para o elemento ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListItem` elemento. Somente uma propriedade ou script pode ser especificado.

### <a name="attributes"></a>Atributos

Nenhum

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento FormatString para ListItem para ListControl (formato)](./formatstring-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica uma cadeia de caracteres de formato que define como o valor de propriedade ou script é exibido.|
|[Elemento ItemSelectionCondition para ListItem para ListControl (formato)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para este item de lista ser usado.|
|[Elemento Label para ListItem para ListControl (formato)](./label-element-for-listitem-for-listcontrol-format.md)|Elemento opcional<br /><br /> Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.|
|[Elemento PropertyName para ListItem para ListControl (formato)](./propertyname-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET cujo valor é exibido na linha.|
|[Elemento ScriptBlock para ListItem para ListControl (formato)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido na linha.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItems para controle de lista (formato)](./listitems-element-for-listentry-for-listcontrol-format.md)|Define as propriedades e os scripts cujos valores são exibidos no modo de exibição de lista.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra os elementos XML que definem três linhas da exibição de lista. As duas primeiras linhas exibem o valor de uma propriedade do .NET e a última linha exibe um valor gerado por um script.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a>Consulte Também

[Elemento ListItems (formato)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Elemento FormatString para ListItem (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md)

[Elemento Label para ListItem (Format)](./label-element-for-listitem-for-listcontrol-format.md)

[Elemento PropertyName para ListItem (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Elemento ScriptBlock para ListItem (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
