---
title: Elemento Label para ListItem para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362885"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Elemento Label para ListItem para ListControl (formato)

Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para ListControl (Format) ListEntry Element para ListControl (Format) ListItems para o elemento ListEntry para ListControl ( Format) ListItem Element para ListItems para o elemento de rótulo ListControl (Format) para ListItem para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Label`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem para ListItems para ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="text-value"></a>Valor de Texto

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

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
