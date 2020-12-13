---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)
description: Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648186"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)

Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl para o elemento View (Format) CustomItem para CustomEntry para CustomControl para o elemento ExpressionBinding de exibição (Format) para CustomItem para CustomControl para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|`CustomControl Element`|Elemento opcional.<br /><br /> Define um controle que é usado por este controle.|
|[Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle comum ou um controle de exibição.|
|[Elemento EnumerateCollection para ExpressionBinding para CustomControl para View (formato)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especificado que os elementos das coleções são exibidos.|
|[Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que esse controle seja usado.|
|[Elemento PropertyName para ExpressionBinding para CustomControl para View (formato)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET cujo valor é exibido pelo controle.|
|[Elemento ScriptBlock para ExpressionBinding para CustomCustomControl para View (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido pelo controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para CustomControl para View (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento EnumerateCollection para ExpressionBinding para CustomControl para View (formato)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Elemento PropertyName para ExpressionBinding para CustomControl para View (formato)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento ScriptBlock para ExpressionBinding para CustomControl para View (formato)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento CustomItem para CustomEntry para CustomControl para View (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
