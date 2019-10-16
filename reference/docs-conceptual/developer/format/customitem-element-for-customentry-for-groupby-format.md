---
title: Elemento CustomItem para CustomEntry para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363875"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>Elemento CustomItem para CustomEntry para GroupBy (formato)

Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomItem para CustomEntry para GroupBy (Format)

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomItem`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento frame para CustomItem para GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.|
|[Elemento de nova linha para CustomItem para GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica texto adicional para os dados exibidos pelo controle.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Fornece uma definição da exibição de controle personalizado.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomControl para GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)

[Elemento ExpressionBinding para CustomItem para GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Elemento frame para CustomItem para GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)

[Elemento de nova linha para CustomItem para GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)

[Elemento Text para CustomItem para GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
