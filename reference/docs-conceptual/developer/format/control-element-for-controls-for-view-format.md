---
title: Elemento Control para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363465"
---
# <a name="control-element-for-controls-for-view--format"></a>Elemento Control para Controls para View (formato)

Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Control`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Name para Control para View (Format)](./name-element-for-control-for-controls-for-view-format.md)|Elemento obrigatório.<br /><br /> Especifica o nome do controle.|
|[Elemento CustomControl para controle de controles para View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Elemento obrigatório.<br /><br /> Define o controle usado por essa exibição.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Controls (formato)](./controls-element-for-view-format.md)|Define os controles de exibição que podem ser usados por uma exibição específica.|

## <a name="remarks"></a>Comentários

Esse controle pode ser especificado pelos seguintes elementos:

- [Elemento CustomControlName para ExpressionBinding para controles para View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Elemento CustomControlName para ExpressionBinding para GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Elemento CustomControlName para GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para controle de controles para View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para controles para View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Elemento CustomControlName para ExpressionBinding para GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Elemento Controls (formato)](./controls-element-for-view-format.md)

[Elemento Name para controle de controles para View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
