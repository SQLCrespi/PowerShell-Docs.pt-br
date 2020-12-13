---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para CustomControl para View (formato)
description: Elemento CustomItem para CustomEntry para CustomControl para View (formato)
ms.openlocfilehash: 9090a3ada5316ba5ddb4a9c46eee37c11982ae6e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666732"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>Elemento CustomItem para CustomEntry para CustomControl para View (formato)

Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para View (Format)

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
|[Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento Frame para CustomItem para CustomControl para View (formato)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.|
|[Elemento de nova linha para CustomItem para controle personalizado para exibição (formato)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento de texto para CustomItem para CustomControl para exibição (formato)](./text-element-for-customitem-for-customview-for-view-format.md)|Elemento opcional.<br /><br /> Especifica texto adicional para os dados exibidos pelo controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para CustomControl para View (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Fornece uma definição da exibição de controle personalizado.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[Elemento Frame para CustomItem para CustomControl para View (formato)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Elemento NewLine para CustomItem para CustomControl para View (formato)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[Elemento de texto para CustomItem para CustomControl para exibição (formato)](./text-element-for-customitem-for-customview-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
