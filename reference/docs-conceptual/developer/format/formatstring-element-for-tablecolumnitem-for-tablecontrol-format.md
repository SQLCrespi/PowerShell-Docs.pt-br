---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para TableColumnItem para TableControl (formato)
description: Elemento FormatString para TableColumnItem para TableControl (formato)
ms.openlocfilehash: 3d386e61ac321c05e0b298019c2298f76b391b21
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667888"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>Elemento FormatString para TableColumnItem para TableControl (formato)

Especifica um padrão de formato que define como o valor de propriedade ou script da tabela é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableRowEntries elemento (Format) TableRowEntry Element (Format) TableColumnItems elemento (Format) TableColumnItem Element (Format) @ Element for TableColumnItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FormatString` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnItem (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Define a propriedade ou o script cujo valor é exibido na coluna da linha.|

## <a name="text-value"></a>Valor de texto

Especifique o padrão usado para formatar os dados. Por exemplo, esse padrão pode ser usado para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.

## <a name="remarks"></a>Comentários

Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas. Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Formatar os dados exibidos](./formatting-displayed-data.md)

[Elemento TableColumnItem (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
