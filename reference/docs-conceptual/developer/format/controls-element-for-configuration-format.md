---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Controls para Configuration (formato)
description: Elemento Controls para Configuration (formato)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668092"
---
# <a name="controls-element-for-configuration-format"></a>Elemento Controls para Configuration (formato)

Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.

Elemento de configuração (Format) controla o elemento de configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Controls` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Control para Controls para Configuration (formato)](./control-element-for-controls-for-configuration-format.md)|Elemento necessário.<br /><br /> Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Configuration (formato)](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode criar qualquer número de controles comuns. Para cada controle, você deve especificar o nome que é usado para referenciar o controle e os componentes do controle.

## <a name="see-also"></a>Consulte Também

[Elemento Configuration (formato)](./configuration-element-format.md)

[Elemento Control para Controls para Configuration (formato)](./control-element-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
