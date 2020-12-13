---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Control para Controls para View (formato)
description: Elemento Control para Controls para View (formato)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668075"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Control` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Name para Control para View (Format)](./name-element-for-control-for-controls-for-view-format.md)|Elemento necessário.<br /><br /> Especifica o nome do controle.|
|[Elemento CustomControl para Control para Controls para View (formato)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Elemento necessário.<br /><br /> Define o controle usado por essa exibição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Controls (formato)](./controls-element-for-view-format.md)|Define os controles de exibição que podem ser usados por uma exibição específica.|

## <a name="remarks"></a>Comentários

Esse controle pode ser especificado pelos seguintes elementos:

- [Elemento CustomControlName para ExpressionBinding para Controls para View (formato)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Elemento CustomControlName para ExpressionBinding para GroupBy (formato)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Elemento CustomControlName para GroupBy (formato)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para Control para Controls para View (formato)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para Controls para View (formato)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Elemento CustomControlName para ExpressionBinding para GroupBy (formato)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Elemento CustomControlName para ExpressionBinding para GroupBy (formato)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Elemento Controls (formato)](./controls-element-for-view-format.md)

[Elemento Name para Control para Controls para View (formato)](./name-element-for-control-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
