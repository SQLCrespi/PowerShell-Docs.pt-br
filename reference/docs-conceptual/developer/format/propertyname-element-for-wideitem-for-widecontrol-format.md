---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para WideItem para WideControl (formato)
description: Elemento PropertyName para WideItem para WideControl (formato)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665610"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>Elemento PropertyName para WideItem para WideControl (formato)

Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) elemento WideItem Element (Format) NomeDaPropriedade Element for WideItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)|Define a propriedade ou o script cujo valor é exibido na exibição ampla.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade cujo valor é exibido.

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra uma exibição ampla que exibe o valor da propriedade ProcessName do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>Consulte Também

[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
