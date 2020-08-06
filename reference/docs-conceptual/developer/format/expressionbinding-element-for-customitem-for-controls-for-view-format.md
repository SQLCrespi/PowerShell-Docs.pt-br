---
title: Elemento ExpressionBinding para CustomItem para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773803"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>Elemento ExpressionBinding para CustomItem para Controls para View (formato)

Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format)

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

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|`CustomControl Element`|Elemento opcional.<br /><br /> Define um controle que é usado por este controle.|
|[Elemento CustomControlName para ExpressionBinding para Controls para View (formato)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle comum ou um controle de exibição.|
|[Elemento EnumerateCollection para ExpressionBinding para Controls para View (formato)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica que os elementos das coleções são exibidos.|
|[Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que esse controle seja usado.|
|[Elemento PropertyName para ExpressionBinding para Controls para View (formato)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET cujo valor é exibido pelo controle.|
|[Elemento ScriptBlock para ExpressionBinding para Controls para View (formato)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido pelo controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para Controls para View (formato)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Define quais dados são exibidos pelo controle e como eles são exibidos.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomItem para CustomEntry para Controls para View (formato)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para Controls para View (formato)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento EnumerateCollection para ExpressionBinding para Controls para View (formato)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento PropertyName para ExpressionBinding para Controls para View (formato)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento ScriptBlock para ExpressionBinding para Controls para View (formato)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
