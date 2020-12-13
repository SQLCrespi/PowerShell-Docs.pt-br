---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableColumnItem para TableColumnItems para TableControl (formato)
description: Elemento TableColumnItem para TableColumnItems para TableControl (formato)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659861"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>Elemento TableColumnItem para TableColumnItems para TableControl (formato)

Define a propriedade ou o script cujo valor é exibido na coluna da linha.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element para TableRowEntries para TableControl (Format) TableColumnItems Element para TableControlEntry para TableControl (Format) TableColumnItem Element para TableColumnItems para TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableColumnItem` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Alignment para TableColumnItem para TableControl (formato)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Define como os dados em uma coluna da linha são exibidos.|
|[Elemento FormatString para TableColumnItem para TableControl (formato)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|Especifica um padrão de formato que é usado para formatar os dados na coluna da linha.|
|[Elemento PropertyName para TableColumnItem para TableControl (formato)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o nome da propriedade cujo valor é exibido.|
|[Elemento ScriptBlock para TableColumnItem para TableControl (formato)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido na coluna de uma linha.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnItems para TableControlEntry para TableControl (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Define as propriedades ou os scripts cujos valores são exibidos na linha.|

## <a name="remarks"></a>Comentários

Você pode especificar uma propriedade de um objeto ou um script em cada coluna da linha. Se nenhum elemento filho for especificado, o item será um espaço reservado e nenhum dado será exibido.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `TableColumnItem` elemento que exibe o valor da `Status` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento Alignment para TableColumnItem para TableControl (formato)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Elemento TableColumnItems (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Elemento FormatString para TableColumnItem para TableControl (formato)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Elemento PropertyName para TableColumnItem para TableControl (formato)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Elemento ScriptBlock para TableColumnItem para TableControl (formato)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
