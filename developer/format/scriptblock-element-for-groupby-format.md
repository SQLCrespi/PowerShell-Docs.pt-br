---
title: Elemento ScriptBlock para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229307"
---
# <a name="scriptblock-element-for-groupby-format"></a>Elemento ScriptBlock para GroupBy (formato)

Especifica o script que inicia um novo grupo sempre que seu valor é alterado.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) ScriptBlock elemento GroupBy (formato)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)|Define como um grupo de objetos do .NET é exibido.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

PowerShell inicia um novo grupo sempre que o valor desse script é alterado.

Quando esse elemento for especificado, é possível especificar o [PropertyName](propertyname-element-for-groupby-format.md) elemento para iniciar um novo grupo.

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para GroupBy (formato)](propertyname-element-for-groupby-format.md)

[Elemento GroupBy para exibição (formato)](groupby-element-for-view-format.md)

[Gravar um arquivo de formatação do PowerShell](writing-a-powershell-formatting-file.md)
