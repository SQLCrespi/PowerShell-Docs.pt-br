---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648042"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)

Define a condição que deve existir para que esse controle seja usado. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento View (Format) ExpressionBinding para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para a exibição (Format)

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
|[Elemento PropertyName para ItemSelectionCondition para CustomControl para exibição (formato](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="remarks"></a>Comentários

Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)

[Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
