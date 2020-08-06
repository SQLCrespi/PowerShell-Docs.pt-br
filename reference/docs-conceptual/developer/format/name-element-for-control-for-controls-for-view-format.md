---
title: Elemento Name para controle de controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 109f3a40606dbe82322decf0c69d2367c75175f6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781079"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>Elemento Name para Control para Controls para View (formato)

Especifica o nome do controle.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format) Name Element para Control para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Control para controles para View (Format)](./control-element-for-controls-for-view-format.md)|Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.|

## <a name="text-value"></a>Valor de texto

Especifique o nome que é usado para referenciar o controle.

## <a name="remarks"></a>Comentários

O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.

- Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

- Ao criar outro controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)

[Elemento ExpressionBinding para CustomItem para Controls para View (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Elemento Control para controles para View (Format)](./control-element-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
