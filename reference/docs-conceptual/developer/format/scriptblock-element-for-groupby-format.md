---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para GroupBy (formato)
description: Elemento ScriptBlock para GroupBy (formato)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665243"
---
# <a name="scriptblock-element-for-groupby-format"></a>Elemento ScriptBlock para GroupBy (formato)

Especifica o script que inicia um novo grupo sempre que seu valor é alterado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) ScriptBlock para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)|Define como um grupo de objetos .NET é exibido.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

O PowerShell inicia um novo grupo sempre que o valor desse script é alterado.

Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](propertyname-element-for-groupby-format.md) para iniciar um novo grupo.

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para GroupBy (formato)](propertyname-element-for-groupby-format.md)

[Elemento GroupBy para View (formato)](groupby-element-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](writing-a-powershell-formatting-file.md)
