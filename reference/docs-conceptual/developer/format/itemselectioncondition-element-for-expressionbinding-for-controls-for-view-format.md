---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648059"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)

Define a condição que deve existir para que esse controle seja usado. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento viewbinding de exibição (Format) para CustomItem para controles para o elemento View (Format) ItemSelectionCondition de ExpressionBinding para controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="remarks"></a>Comentários

Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
