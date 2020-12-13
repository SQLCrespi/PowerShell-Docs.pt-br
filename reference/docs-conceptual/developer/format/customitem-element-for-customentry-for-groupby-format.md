---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para GroupBy (formato)
description: Elemento CustomItem para CustomEntry para GroupBy (formato)
ms.openlocfilehash: 5db23ad4dad5bd66ea64b9c6e91b8224a4aa4eca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645980"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>Elemento CustomItem para CustomEntry para GroupBy (formato)

Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomItem Element para CustomEntry para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para GroupBy (formato)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento Frame para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.|
|[Elemento NewLine para CustomItem para GroupBy (formato)](./newline-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para GroupBy (formato)](./text-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica texto adicional para os dados exibidos pelo controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para GroupBy (formato)](./customentry-element-for-customcontrol-for-groupby-format.md)|Fornece uma definição da exibição de controle personalizado.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomControl para GroupBy (formato)](./customentry-element-for-customcontrol-for-groupby-format.md)

[Elemento ExpressionBinding para CustomItem para GroupBy (formato)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Elemento Frame para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)

[Elemento NewLine para CustomItem para GroupBy (formato)](./newline-element-for-customitem-for-groupby-format.md)

[Elemento Text para CustomItem para GroupBy (formato)](./text-element-for-customitem-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
