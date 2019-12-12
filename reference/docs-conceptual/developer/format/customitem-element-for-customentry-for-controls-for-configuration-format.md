---
title: Elemento CustomItem para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364025"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Elemento CustomItem para CustomEntry para Controls para Configuration (formato)

Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento Configuration (Format) CustomItem para CustomEntry para controles para a configuração

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomItem`. Para obter mais informações, consulte Remarks.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento frame para CustomItem para controles para configuração (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|
|[Elemento de nova linha para CustomItem para controles para configuração (formato)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para controles para configuração (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Adiciona texto, como parênteses ou colchetes, à exibição do controle.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para controles para configuração (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

Ao especificar os elementos filho do elemento `CustomItem`, tenha em mente o seguinte:

- Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding`, `NewLine`, `Text`e `Frame`.

- Não há nenhum limite máximo para o número de sequências que você pode especificar.

- Em cada sequência, não há nenhum limite máximo para o número de elementos `ExpressionBinding` que você pode usar.

## <a name="see-also"></a>Consulte Também

[Elemento ExpressionBinding para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento frame para CustomItem para controles para configuração (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento de nova linha para CustomItem para controles para configuração (formato)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento Text para CustomItem para controles para configuração (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
