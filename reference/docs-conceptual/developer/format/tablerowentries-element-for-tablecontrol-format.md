---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableRowEntries para TableControl (formato)
description: Elemento TableRowEntries para TableControl (formato)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651475"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>Elemento TableRowEntries para TableControl (formato)

Define as linhas da tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento TableControl Element (Format) TableRowEntries elemento para TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableRowEntries` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableRowEntry para TableRowEntries para TableControl (formato)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Elemento necessário.<br /><br /> Define os dados que são exibidos em uma linha da tabela.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableControl (formato)](./tablecontrol-element-format.md)|Define um formato de tabela para uma exibição.|

## <a name="remarks"></a>Comentários

Você deve especificar um ou mais `TableRowEntry` elementos para a exibição de tabela. Não há nenhum limite máximo para o número de `TableRowEntry` elementos que podem ser adicionados, nem sua ordem significativa.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `TableRowEntries` elemento que define uma linha que exibe os valores de duas propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento TableControl (formato)](./tablecontrol-element-format.md)

[Elemento TableRowEntry (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
