---
title: Elemento TableHeaders (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361815"
---
# <a name="tableheaders-element-format"></a>Elemento TableHeaders (formato)

Define os cabeçalhos para as colunas de uma tabela.

Elemento ViewDefinitions (Format) View element (Format) o elemento TableControl (Format) elemento TableHeaders para TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do elemento `TableHeaders`. Deve haver um elemento filho para cada propriedade do objeto a ser exibido. As informações de cabeçalho de coluna são exibidas na ordem em que os elementos filho são especificados.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnHeader (Format)](./tablecolumnheader-element-format.md)|Elemento opcional.<br /><br /> Define o rótulo, a largura e o alinhamento dos dados para uma coluna de uma exibição de tabela.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableControl (Format)](./tablecontrol-element-format.md)|Define um formato de tabela para uma exibição.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um elemento `TableHeaders` que define dois cabeçalhos de coluna.

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a>Consulte Também

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Elemento TableColumnHeader (Format)](./tablecolumnheader-element-format.md)

[Elemento TableControl (Format)](./tablecontrol-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
