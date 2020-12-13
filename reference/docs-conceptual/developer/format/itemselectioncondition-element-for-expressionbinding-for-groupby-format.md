---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651983"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)

Define a condição que deve existir para que esse controle seja usado. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding de GroupBy (Format)

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
|[Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para GroupBy (formato)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="remarks"></a>Comentários

Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)

[Elemento ExpressionBinding para CustomItem para GroupBy (formato)](./expressionbinding-element-for-customitem-for-groupby-format.md)
