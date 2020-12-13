---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665128"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)

Especifica o script que dispara a condição. Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento ExpressionBinding View (Format) para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para o elemento ScriptBlock View (Format) para ItemSelectionCondition para CustomControl para View (Format)

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
|[Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Define a condição que deve existir para que esse controle seja usado.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) ao definir a condição de seleção.

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
