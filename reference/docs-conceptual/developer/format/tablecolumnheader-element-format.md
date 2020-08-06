---
title: Elemento TableColumnHeader (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6296aea5c567663b1c3c0a2cf0a57b21aa5394de
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785176"
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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TableColumnHeader` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Label para TableColumnHeader para TableControl (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Define o rótulo que é exibido na parte superior da coluna. Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.|
|[Elemento Width para TableColumnHeader para TableControl (formato)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento necessário.<br /><br /> Especifica a largura (em caracteres) da coluna.|
|[Elemento Alignment para TableColumnHeader para TableControl (formato)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica como o rótulo da coluna é exibido. Se nenhum alinhamento for especificado, o rótulo será alinhado à esquerda.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableHeaders (formato)](./tableheaders-element-format.md)|Define as colunas de uma exibição de tabela.|

## <a name="remarks"></a>Comentários

Especifique um cabeçalho para cada coluna da tabela. As colunas são exibidas na ordem em que os `TableColumnHeader` elementos são definidos.

Uma tabela deve ter o mesmo número de `TableColumnHeader` elementos que os `TableRowEntry` elementos. O cabeçalho da coluna define como o texto na parte superior da tabela é exibido. As entradas de linha definem quais dados são exibidos nas linhas da tabela.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra dois `TableColumnHeader` elementos. O primeiro elemento define uma coluna cujo rótulo é "Column 1", tem uma largura de 16 caracteres e cujo rótulo está alinhado à esquerda. O segundo elemento define uma coluna cujo rótulo é "coluna 2", tem uma largura de 10 caracteres e cujo rótulo é centralizado na coluna.

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

[Elemento Alignment para TableColumnHeader para TableControl (formato)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento Label para TableColumnHeader para TableControl (formato)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Elemento TableHeaders para TableControl (Format)](./tableheaders-element-format.md)

[Largura de TableColumnHeader para o elemento TableControl (formato)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
