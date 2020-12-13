---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)
description: Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)
ms.openlocfilehash: 9fb7a21e19338dbf59dab14291e1b02736835040
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645814"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a>Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e o controle é usado. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para o elemento View (Format) ItemSelectionCondition de ExpressionBinding para controles para View (Format) elemento PropertyName para ItemSelectionCondition para controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Define a condição que deve existir para que esse controle seja usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da Propriedade do .NET que dispara a condição.

## <a name="remarks"></a>Comentários

Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) ao definir a condição de seleção.

## <a name="see-also"></a>Consulte Também

[Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
