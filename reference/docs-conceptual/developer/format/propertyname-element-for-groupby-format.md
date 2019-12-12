---
title: Elemento PropertyName para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362515"
---
# <a name="propertyname-element-for-groupby-format"></a>Elemento PropertyName para GroupBy (formato)

Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) PropertyName para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)|Define como um grupo de objetos .NET é exibido.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome da propriedade .NET.

## <a name="remarks"></a>Comentários

O Windows PowerShell inicia um novo grupo sempre que o valor dessa propriedade é alterado.

Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-groupby-format.md) para iniciar um novo grupo.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como iniciar um novo grupo quando o valor de uma propriedade é alterado.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>Consulte Também

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

[Elemento ScriptBlock para GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
