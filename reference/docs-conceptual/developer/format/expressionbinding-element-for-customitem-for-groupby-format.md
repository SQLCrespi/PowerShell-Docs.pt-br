---
title: Elemento ExpressionBinding para CustomItem para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5b0017e487aab4ffcbf901cd44aad9b275b22832
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773718"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>Elemento ExpressionBinding para CustomItem para GroupBy (formato)

Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding GroupBy (Format) para CustomItem para GroupBy (Format)

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
|[Elemento CustomControlName para ExpressionBinding para GroupBy (formato)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle comum ou um controle de exibição.|
|[Elemento enumeracollection para ExpressionBinding para GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Elemento enumeracollection para ExpressionBinding para GroupBy (Format)|Elemento opcional.<br /><br /> Especificado que os elementos das coleções são exibidos.|
|[Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que esse controle seja usado.|
|[Elemento PropertyName para ExpressionBinding para GroupBy (formato)](./propertyname-element-for-expressionbinding-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET cujo valor é exibido pelo controle.|
|[Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script cujo valor é exibido pelo controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)|Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.|

## <a name="see-also"></a>Consulte Também

[Elemento CustomControlName para ExpressionBinding para GroupBy (formato)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Elemento EnumerateCollection para ExpressionBinding para GroupBy (formato)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Elemento PropertyName para ExpressionBinding para GroupBy (formato)](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
