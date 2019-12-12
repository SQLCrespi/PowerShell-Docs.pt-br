---
title: Elemento ViewSelectedBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367965"
---
# <a name="viewselectedby-element-format"></a>Elemento ViewSelectedBy (formato)

Define os objetos .NET que são exibidos pela exibição. Cada exibição deve especificar pelo menos um objeto .NET.

Elemento ViewDefinitions (Format) View element (Format) ViewSelectedBy elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ViewSelectedBy`. Este elemento deve conter pelo menos um `TypeName` ou `SelectionSetName` elemento filho. Não há nenhum limite para o número de elementos filho que podem ser especificados, nem sua ordem significativa.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento TypeName para ViewSelectedBy (Format)](./typename-element-for-viewselectedby-format.md)|Elemento opcional.<br /><br /> Especifica um objeto .NET que é exibido pela exibição.|
|[Elemento SelectionSetName para ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de objetos .NET que são exibidos pela exibição.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que exibe um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [componentes de exibição de tabela](./creating-a-table-view.md), componentes de exibição de [lista](./creating-a-list-view.md), [componentes de exibição ampla](./creating-a-wide-view.md)e [componentes de controle personalizado](./creating-custom-controls.md).

O elemento `SelectionSetName` é usado quando o arquivo de formatação define um conjunto de objetos que são exibidos por vários modos de exibição. Para obter mais informações sobre como os conjuntos de seleção são definidos e referenciados, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) para uma exibição de lista. O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>Consulte Também

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Definindo conjuntos de seleção](./defining-selection-sets.md)

[Elemento SelectionSetName para ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)

[Elemento TypeName (formato)](./typename-element-for-viewselectedby-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
