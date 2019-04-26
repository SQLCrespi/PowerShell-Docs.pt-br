---
title: Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065800"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)

Define a condição que deve existir para esse controle a ser usado. Não há nenhum limite para o número de condições de seleção que pode ser especificado para um item de controle. Esse elemento é usado ao definir uma exibição de controle personalizado.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para elemento CustomItem de exibição (formato) CustomEntry para elemento de exibição (formato) ExpressionBinding CustomItem para CustomControl para exibição (formato) ItemSelectionCondition elemento de associação de expressão para CustomControl para exibição (formato)

## <a name="syntax"></a>Sintaxe

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para ItemSelectionCondition para CustomControl (formato de exibição](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade do .NET que dispara a condição.|
|[Elemento ScriptBlock para ItemSelectionCondition para CustomControl para exibição (formato)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="remarks"></a>Comentários

Você pode especificar um nome de propriedade ou um script para essa condição, mas não é possível especificar ambos.

## <a name="see-also"></a>Consulte Também

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)

[Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
