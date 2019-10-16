---
title: Elemento ListItem para ListItems para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365125"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>Elemento ListItem para ListItems para ListControl (formato)

Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems para ListControl (Format) ListItem para elemento ListControl (formato)

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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ListItem`. Somente uma propriedade ou script pode ser especificado.

### <a name="attributes"></a>Atributos

Não

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento FormatString para ListItem para ListControl (formato)](./formatstring-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica uma cadeia de caracteres de formato que define como o valor de propriedade ou script é exibido.|
|[Elemento ItemSelectionCondition para ListItem para ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para este item de lista ser usado.|
|[Elemento Label para ListItem para ListControl (Format)](./label-element-for-listitem-for-listcontrol-format.md)|Elemento opcional<br /><br /> Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.|
|[Elemento PropertyName para ListItem para ListControl (formato)](./propertyname-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET cujo valor é exibido na linha.|
|[Elemento ScriptBlock para ListItem para ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido na linha.|

### <a name="parent-elements"></a>Elementos pais

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

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
