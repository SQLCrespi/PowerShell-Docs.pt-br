---
title: Elemento ScriptBlock para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364925"
---
# <a name="scriptblock-element-for-groupby-format"></a>Elemento ScriptBlock para GroupBy (formato)

Especifica o script que inicia um novo grupo sempre que seu valor é alterado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) ScriptBlock para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)|Define como um grupo de objetos .NET é exibido.|

## <a name="text-value"></a>Valor de Texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

O PowerShell inicia um novo grupo sempre que o valor desse script é alterado.

Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](propertyname-element-for-groupby-format.md) para iniciar um novo grupo.

## <a name="see-also"></a>Consulte Também

[Elemento PropertyName para GroupBy (Format)](propertyname-element-for-groupby-format.md)

[Elemento GroupBy para exibição (formato)](groupby-element-for-view-format.md)

[Gravando um arquivo de formatação do PowerShell](writing-a-powershell-formatting-file.md)
