---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableHeaders (formato)
description: Elemento TableHeaders (formato)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659826"
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

As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do `TableHeaders` elemento. Deve haver um elemento filho para cada propriedade do objeto a ser exibido. As informações de cabeçalho de coluna são exibidas na ordem em que os elementos filho são especificados.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnHeader (formato)](./tablecolumnheader-element-format.md)|Elemento opcional.<br /><br /> Define o rótulo, a largura e o alinhamento dos dados para uma coluna de uma exibição de tabela.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableControl (formato)](./tablecontrol-element-format.md)|Define um formato de tabela para uma exibição.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `TableHeaders` elemento que define dois cabeçalhos de coluna.

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

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento TableColumnHeader (formato)](./tablecolumnheader-element-format.md)

[Elemento TableControl (formato)](./tablecontrol-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
