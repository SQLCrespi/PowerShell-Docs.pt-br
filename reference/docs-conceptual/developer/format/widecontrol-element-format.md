---
title: Elemento WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367985"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideControl`. Você não pode especificar os elementos `AutoSize` e `ColumnNumber` ao mesmo tempo.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento AutoSize para WideControl (Format)](./autosize-element-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.|
|[Elemento ColumnNumber para WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)|Elemento opcional.<br /><br /> Especifica o número de colunas exibidas na exibição ampla.|
|[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)|Elemento obrigatório.<br /><br /> Fornece as definições da exibição ampla.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Ao definir uma exibição ampla, você pode adicionar o elemento `AutoSize` ou o `ColumnNumber`, mas não pode adicionar ambos.

Na maioria dos casos, apenas uma definição é necessária para cada exibição ampla, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes. Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.

Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `WideControl` que é usado para exibir uma propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

[Elemento ColumnNumber para WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)

[Elemento View (formato)](./view-element-format.md)

[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)

[Exibição ampla (básica)](./wide-view-basic.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
