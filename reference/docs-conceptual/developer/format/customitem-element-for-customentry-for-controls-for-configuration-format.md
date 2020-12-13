---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para Controls para Configuration (formato)
description: Elemento CustomItem para CustomEntry para Controls para Configuration (formato)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666766"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Elemento CustomItem para CustomEntry para Controls para Configuration (formato)

Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para a configuração

## <a name="syntax"></a>Sintaxe

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento. Para obter mais informações, consulte Comentários.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento Frame para CustomItem para Controls para Configuration (formato)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|
|[Elemento NewLine para CustomItem para Controls para Configuration (formato)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para Controls para Configuration (formato)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Adiciona texto, como parênteses ou colchetes, à exibição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para Controls para Configuration (formato)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:

- Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .

- Não há nenhum limite máximo para o número de sequências que você pode especificar.

- Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.

## <a name="see-also"></a>Consulte Também

[Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento Frame para CustomItem para Controls para Configuration (formato)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento NewLine para CustomItem para Controls para Configuration (formato)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento Text para CustomItem para Controls para Configuration (formato)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
