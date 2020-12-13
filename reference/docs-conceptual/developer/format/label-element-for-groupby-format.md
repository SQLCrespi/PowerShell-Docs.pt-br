---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para GroupBy (formato)
description: Elemento Label para GroupBy (formato)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649795"
---
# <a name="label-element-for-groupby-format"></a>Elemento Label para GroupBy (formato)

Especifica um rótulo que é exibido quando um novo grupo é encontrado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de rótulo View (Format) para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)|Define como um novo grupo de objetos é exibido.|

## <a name="text-value"></a>Valor de texto

Especifique o texto que será exibido sempre que o Windows PowerShell encontrar uma nova propriedade ou um novo valor de script.

## <a name="remarks"></a>Comentários

Além do texto especificado por esse elemento, o Windows PowerShell exibe o novo valor que inicia o grupo e adiciona uma linha em branco antes e depois do grupo.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra o rótulo de um novo grupo. O rótulo exibido seria semelhante a este: `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>Consulte Também

[Elemento GroupBy para View (formato)](./groupby-element-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
