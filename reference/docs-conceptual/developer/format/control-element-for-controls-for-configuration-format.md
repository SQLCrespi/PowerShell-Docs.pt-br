---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Control para Controls para Configuration (formato)
description: Elemento Control para Controls para Configuration (formato)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655655"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Elemento Control para Controls para Configuration (formato)

Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.

Elemento de configuração (Format) controla o elemento de configuração (formato) elemento de controle para controles para configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Control` elemento. Você deve especificar apenas um de cada elemento filho.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para Control para Controls para Configuration (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Elemento necessário.<br /><br /> Define o controle.|
|[Elemento Name para controle de configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Elemento necessário.<br /><br /> Especifica o nome usado para referenciar o controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Controla o elemento de configuração (formato)](./controls-element-for-configuration-format.md)|Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação ou por outros controles.|

## <a name="remarks"></a>Comentários

O nome fornecido a este controle pode ser referenciado nos seguintes elementos:

- [Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Controla o elemento de configuração (formato)](./controls-element-for-configuration-format.md)

[Elemento CustomControl para controle de configuração (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

[Elemento Name para Control para Controls para Configuration (formato)](./name-element-for-control-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
