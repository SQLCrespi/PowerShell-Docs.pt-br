---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Width para TableColumnHeader para TableControl (formato)
description: Elemento Width para TableColumnHeader para TableControl (formato)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658251"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Elemento Width para TableColumnHeader para TableControl (formato)

Define a largura (em caracteres) de uma coluna.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element TableHeaders para TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Width` elemento usado ao definir cabeçalhos de coluna.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnHeader para TableHeaders para TableControl (Format)](./tablecolumnheader-element-format.md)|Define um rótulo, uma largura e um alinhamento dos dados para uma coluna da tabela.|

## <a name="text-value"></a>Valor de texto

Quando possível, especifique uma largura (em caracteres) que seja maior que o comprimento dos valores de propriedade exibidos.

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `TableColumnHeader` elemento cuja largura é 16 caracteres.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento TableColumnHeader para TableHeader para TableControl (Format)](./tablecolumnheader-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
