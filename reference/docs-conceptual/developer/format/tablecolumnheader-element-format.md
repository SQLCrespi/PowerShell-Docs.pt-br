---
title: Elemento TableColumnHeader (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361845"
---
# <a name="tablecolumnheader-element-format"></a>Elemento TableColumnHeader (formato)

Define o rótulo, a largura da coluna e o alinhamento do rótulo para uma coluna da tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TableColumnHeader`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Label para TableColumnHeader para TableControl (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Define o rótulo que é exibido na parte superior da coluna. Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.|
|[Elemento Width para TableColumnHeader para TableControl (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento obrigatório.<br /><br /> Especifica a largura (em caracteres) da coluna.|
|[Elemento Alignment para TableColumnHeader para TableControl (Format)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica como o rótulo da coluna é exibido. Se nenhum alinhamento for especificado, o rótulo será alinhado à esquerda.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableHeaders (Format)](./tableheaders-element-format.md)|Define as colunas de uma exibição de tabela.|

## <a name="remarks"></a>Comentários

Especifique um cabeçalho para cada coluna da tabela. As colunas são exibidas na ordem em que os elementos `TableColumnHeader` são definidos.

Uma tabela deve ter o mesmo número de elementos `TableColumnHeader` que os elementos `TableRowEntry`. O cabeçalho da coluna define como o texto na parte superior da tabela é exibido. As entradas de linha definem quais dados são exibidos nas linhas da tabela.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra dois elementos `TableColumnHeader`. O primeiro elemento define uma coluna cujo rótulo é "Column 1", tem uma largura de 16 caracteres e cujo rótulo está alinhado à esquerda. O segundo elemento define uma coluna cujo rótulo é "coluna 2", tem uma largura de 10 caracteres e cujo rótulo é centralizado na coluna.

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

[Elemento Alignment para TableColumnHeader para TableControl (Format)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Elemento Label para TableColumnHeader para TableControl (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Elemento TableHeaders para TableControl (Format)](./tableheaders-element-format.md)

[Largura de TableColumnHeader para o elemento TableControl (formato)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
