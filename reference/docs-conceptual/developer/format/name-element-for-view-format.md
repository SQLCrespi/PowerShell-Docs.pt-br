---
title: Elemento de nome para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362635"
---
# <a name="name-element-for-view-format"></a>Elemento Name para View (formato)

Especifica o nome que é usado para identificar a exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) nome Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Name`. Apenas um elemento `Name` é permitido para cada exibição.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que é usada para exibir os membros de um ou mais objetos .NET.|

## <a name="text-value"></a>Valor de Texto

Especifique um nome amigável exclusivo para a exibição. Esse nome pode incluir uma referência ao tipo da exibição (como uma exibição de tabela ou exibição de lista), qual objeto ou conjunto de objetos usa a exibição, qual comando retorna os objetos ou uma combinação deles.

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os diferentes tipos de exibições, consulte os seguintes tópicos: [exibição de tabela](./creating-a-table-view.md), [exibição de lista](./creating-a-list-view.md), exibição [ampla](./creating-a-wide-view.md)e [exibição personalizada](./creating-custom-controls.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um elemento `View` que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . O nome da exibição é "serviço".

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

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Elemento View (formato)](./view-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
