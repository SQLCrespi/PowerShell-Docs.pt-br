---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para Control para Controls para Configuration (formato)
description: Elemento Name para Control para Controls para Configuration (formato)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666494"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Elemento Name para Control para Controls para Configuration (formato)

Especifica o nome do controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de nome de configuração (formato) para controle para controles para configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Control para Controls para Configuration (formato)](./control-element-for-controls-for-configuration-format.md)|Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.|

## <a name="text-value"></a>Valor de texto

Especifique o nome que é usado para fazer referência a esse controle.

## <a name="remarks"></a>Comentários

O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.

- Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

- Ao criar outro controle comum, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- Ao criar um controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento Control para Controls para Configuration (formato)](./control-element-for-controls-for-configuration-format.md)

[Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
