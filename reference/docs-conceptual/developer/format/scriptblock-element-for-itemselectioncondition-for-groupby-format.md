---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)
ms.openlocfilehash: fe366fa31b93e8d69409cc49c3fe2c350d4d06d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665090"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a>Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)

Especifica o script que dispara a condição. Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para o elemento de CustomEntry GroupBy (Format) para CustomControl para GroupBy (Format) o elemento CustomItem para CustomEntry para o elemento ExpressionBinding GroupBy (Format) para CustomItem para o elemento GroupBy (Format) ItemSelectionCondition para ExpressionBinding para o elemento ScriptBlock (Format) de GroupBy para ItemSelectionCondition para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Define a condição que deve existir para que esse controle seja usado.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) ao definir a condição de seleção.

## <a name="see-also"></a>Consulte Também

[Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
