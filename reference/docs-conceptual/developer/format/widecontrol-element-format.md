---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideControl (formato)
description: Elemento WideControl (formato)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651266"
---
# <a name="widecontrol-element-format"></a>Elemento WideControl (formato)

Define um formato de lista largo (valor único) para a exibição. Essa exibição mostra um valor de propriedade única ou um valor de script para cada objeto.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideControl` elemento. Você não pode especificar `AutoSize` os `ColumnNumber` elementos e ao mesmo tempo.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento AutoSize para WideControl (formato)](./autosize-element-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.|
|[Elemento ColumnNumber para WideControl (formato)](./columnnumber-element-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o número de colunas exibidas na exibição ampla.|
|[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)|Elemento necessário.<br /><br /> Fornece as definições da exibição ampla.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou, `ColumnNumber` mas não pode adicionar ambos.

Na maioria dos casos, apenas uma definição é necessária para cada exibição ampla, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes. Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `WideControl` elemento que é usado para exibir uma propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Elemento AutoSize para WideControl (Format)](./autosize-element-for-widecontrol-format.md)

[Elemento ColumnNumber para WideControl (formato)](./columnnumber-element-for-widecontrol-format.md)

[Elemento View (formato)](./view-element-format.md)

[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)

[Exibição ampla (Básica)](./wide-view-basic.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
