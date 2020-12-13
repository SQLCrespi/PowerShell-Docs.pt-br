---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para GroupBy (formato)
description: Elemento PropertyName para GroupBy (formato)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666137"
---
# <a name="propertyname-element-for-groupby-format"></a>Elemento PropertyName para GroupBy (formato)

Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) PropertyName para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)|Define como um grupo de objetos .NET é exibido.|

## <a name="text-value"></a>Valor de texto

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

[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)

[Elemento ScriptBlock para GroupBy (formato)](./scriptblock-element-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
