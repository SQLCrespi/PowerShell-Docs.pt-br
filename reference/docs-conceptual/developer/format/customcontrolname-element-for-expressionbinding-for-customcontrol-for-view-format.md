---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)
description: Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)
ms.openlocfilehash: 24b27428c07d7178f0069f6d0e5b7ffc555efe34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666800"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)

Especifica o nome de um controle comum ou um controle de exibição. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento Viewbinding (Format) do CustomItem para o elemento CustomControlName (Format) para a associação de expressão para CustomItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Define os dados que são exibidos pelo controle.|

## <a name="text-value"></a>Valor de texto

Especifique o nome do controle.

## <a name="remarks"></a>Comentários

Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica. Os nomes desses controles são especificados pelos elementos a seguir.

- [Elemento Name para Control para Controls para Configuration (formato)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Elemento Name para Control para Controls para View (formato)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento Name para Control para Controls para Configuration (formato)](./name-element-for-control-for-controls-for-configuration-format.md)

[Elemento Name para Control para Controls para View (formato)](./name-element-for-control-for-controls-for-view-format.md)

[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
