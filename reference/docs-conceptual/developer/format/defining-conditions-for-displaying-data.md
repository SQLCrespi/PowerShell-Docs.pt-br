---
title: Definindo condições para exibir dados | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 8a5b84b6a461e9fc340a5981578d95ca2ac6b9f7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363895"
---
# <a name="defining-conditions-for-displaying-data"></a>Definir condições para a exibição de dados

Ao definir quais dados são exibidos por uma exibição ou um controle, você pode especificar uma condição que deve existir para que os dados sejam exibidos. A condição pode ser disparada por uma propriedade específica ou quando um valor de script ou propriedade é avaliado como `true`. Quando a condição de seleção é atendida, a definição da exibição ou do controle é usada.

## <a name="specifying-a-selection-condition-for-a-definition"></a>Especificando uma condição de seleção para uma definição

Ao criar uma definição para um modo de exibição ou controle, o elemento `EntrySelectedBy` é usado para especificar quais objetos usarão a definição ou qual condição deve existir para que a definição seja usada. A condição é especificada pelo elemento `SelectionCondition`.

No exemplo a seguir, uma condição de seleção é especificada para uma definição de uma exibição de tabela. Neste exemplo, a definição é usada somente quando o script especificado é avaliado como `true`.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

Não há nenhum limite para o número de condições de seleção que você pode especificar para uma definição de um modo de exibição ou controle. Os únicos requisitos são os seguintes:

- A condição de seleção deve especificar um nome de propriedade ou script para disparar a condição, mas não pode especificar ambos.

- A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.

## <a name="specifying-a-selection-condition-for-an-item"></a>Especificando uma condição de seleção para um item

Você também pode especificar quando um item de um modo de exibição de lista ou controle é usado incluindo o elemento `ItemSelectionCondition` na definição de item. No exemplo a seguir, uma condição de seleção é especificada para um item de um modo de exibição de lista. Neste exemplo, o item é usado somente quando o script é avaliado como `true`.

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

Você pode especificar apenas uma condição de seleção para um item. E a condição deve especificar um nome de propriedade ou script para disparar a condição, mas não pode especificar ambos.

## <a name="xml-elements"></a>Elementos XML

 Os seguintes elementos XML são usados para criar uma condição de seleção.

- Os elementos a seguir especificam as condições de seleção para definições de exibição:

    - [Elemento SelectionCondition para EntrySelectedBy para TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [Elemento SelectionCondition para EntrySelectedBy para WideControl (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [Elemento SelectionCondition para EntrySelectedBy para CustomControl (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- Os elementos a seguir especificam as condições de seleção para as definições de controle comum e de exibição:

    - [Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- O elemento a seguir especifica a condição de seleção para expandir objetos de coleção:

    - [Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- O elemento a seguir especifica a condição de seleção para exibir um novo grupo de dados:

    - [Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- O elemento a seguir especifica uma condição de seleção de item para uma exibição de lista:

    - [Elemento ItemSelectionCondition para ListItem para ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- Os elementos a seguir especificam uma condição de seleção de item para controles:

    - [Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [Elemento ItemSelectionCondition para ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>Consulte Também

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
