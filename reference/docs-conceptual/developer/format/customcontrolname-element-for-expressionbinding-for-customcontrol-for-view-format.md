---
title: Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364105"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)

Especifica o nome de um controle comum ou um controle de exibição. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Elemento para CustomEntry para o elemento ExpressionBinding View (Format) para o elemento CustomItem (Format) CustomControlName para a associação de expressão para CustomItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControlName`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome do controle.

## <a name="remarks"></a>Comentários

Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica. Os nomes desses controles são especificados pelos elementos a seguir.

- [Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Elemento Name para controle de controles para View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Elemento Name para controle de controles para View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
