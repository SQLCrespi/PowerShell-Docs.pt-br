---
title: Elemento CustomItem para CustomEntry para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 747ea14e7118be62ebee00e7d80af2dccb5c8353
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785839"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Elemento CustomItem para CustomEntry para Controls para View (formato)

Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles do elemento View (Format) CustomItem para CustomEntry para os controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento. Para obter mais informações, consulte Comentários.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|
|[Elemento NewLine para CustomItem para Controls para View (formato)](./newline-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para Controls para View (formato)](./text-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Adiciona texto, como parênteses ou colchetes, à exibição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:

- Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .

- Não há nenhum limite máximo para o número de sequências que você pode especificar.

- Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.

## <a name="see-also"></a>Consulte Também

[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Elemento NewLine para CustomItem para Controls para View (formato)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Elemento Text para CustomItem para Controls para View (formato)](./text-element-for-customitem-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
