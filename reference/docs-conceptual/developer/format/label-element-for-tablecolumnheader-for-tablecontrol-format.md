---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para TableColumnHeader para TableControl (formato)
description: Elemento Label para TableColumnHeader para TableControl (formato)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667786"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Elemento Label para TableColumnHeader para TableControl (formato)

Define o rótulo que é exibido na parte superior de uma coluna. Esse elemento é usado ao definir um modo de exibição de tabela.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element para TableHeaders para TableControl (Format) rótulo Element para TableColumnHeader para TableControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento. Apenas um rótulo é permitido para cada coluna.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TableColumnHeader para TableHeaders para TableControl (Format)](./tablecolumnheader-element-format.md)|Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.|

## <a name="text-value"></a>Valor de texto

Especifique o texto que é exibido na parte superior da coluna da tabela. Não há caracteres restritos para o rótulo de coluna.

## <a name="remarks"></a>Comentários

Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.

Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um `TableColumnHeader` elemento cujo rótulo é "coluna 1".

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Elemento TableColumnHeader (formato)](./tablecolumnheader-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
