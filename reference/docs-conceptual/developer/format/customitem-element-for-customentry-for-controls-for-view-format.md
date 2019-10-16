---
title: Elemento CustomItem para CustomEntry para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363935"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Elemento CustomItem para CustomEntry para Controls para View (formato)

Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para View (Format) CustomItem Element for CustomEntry para Controls for View (Format)

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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomItem`. Para obter mais informações, consulte comentários.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define os dados que são exibidos pelo controle.|
|[Elemento frame para CustomItem para controles para View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|
|[Elemento de nova linha para CustomItem para controles para View (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Adiciona uma linha em branco à exibição do controle.|
|[Elemento Text para CustomItem para controles para View (Format)](./text-element-for-customitem-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Adiciona texto, como parênteses ou colchetes, à exibição do controle.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para controles para View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Fornece uma definição do controle.|

## <a name="remarks"></a>Comentários

Ao especificar os elementos filho do elemento `CustomItem`, tenha em mente o seguinte:

- Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding`, `NewLine`, `Text` e `Frame`.

- Não há nenhum limite máximo para o número de sequências que você pode especificar.

- Em cada sequência, não há nenhum limite máximo para o número de elementos `ExpressionBinding` que você pode usar.

## <a name="see-also"></a>Consulte Também

[Elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Elemento frame para CustomItem para controles para View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Elemento de nova linha para CustomItem para controles para View (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Elemento Text para CustomItem para controles para View (Format)](./text-element-for-customitem-for-controls-for-view-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
