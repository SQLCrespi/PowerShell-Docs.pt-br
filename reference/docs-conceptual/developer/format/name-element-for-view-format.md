---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para View (formato)
description: Elemento Name para View (formato)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666443"
---
# <a name="name-element-for-view-format"></a>Elemento Name para View (formato)

Especifica o nome que é usado para identificar a exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) nome Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento. Somente um `Name` elemento é permitido para cada exibição.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que é usada para exibir os membros de um ou mais objetos .NET.|

## <a name="text-value"></a>Valor de texto

Especifique um nome amigável exclusivo para a exibição. Esse nome pode incluir uma referência ao tipo da exibição (como uma exibição de tabela ou exibição de lista), qual objeto ou conjunto de objetos usa a exibição, qual comando retorna os objetos ou uma combinação deles.

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os diferentes tipos de exibições, consulte os seguintes tópicos: [exibição de tabela](./creating-a-table-view.md), [exibição de lista](./creating-a-list-view.md), exibição [ampla](./creating-a-wide-view.md)e [exibição personalizada](./creating-custom-controls.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `View` elemento que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . O nome da exibição é "serviço".

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de lista](./creating-a-list-view.md)

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Elemento View (formato)](./view-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
