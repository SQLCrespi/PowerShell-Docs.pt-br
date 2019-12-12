---
title: Elemento View (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361455"
---
# <a name="view-element-format"></a>Elemento View (formato)

Define uma exibição que exibe um ou mais objetos .NET. Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `View`. Você deve especificar um e apenas um dos elementos filho do controle, e deve especificar o nome da exibição e os objetos que usam a exibição. Definir controles personalizados, como agrupar objetos e especificar se a exibição está fora de banda é opcional.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Controls para View (Format)](./controls-element-for-view-format.md)|Elemento opcional.<br /><br /> Define um conjunto de controles que podem ser referenciados por seu nome de dentro da exibição.|
|[Elemento CustomControl (Format)](./customcontrol-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Define um formato de controle personalizado para a exibição.|
|[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)|Elemento opcional.<br /><br /> Define como os membros dos objetos .NET são agrupados.|
|[Elemento ListControl (formato)](./listcontrol-element-format.md)|Elemento opcional.<br /><br /> Define um formato de lista para a exibição.|
|[Elemento de nome para exibição (formato)](./name-element-for-view-format.md)|Elemento obrigatório.<br /><br /> Especifica o nome usado para fazer referência à exibição.|
|[Elemento TableControl (Format)](./tablecontrol-element-format.md)|Elemento opcional.<br /><br /> Define um formato de tabela para a exibição.|
|[Elemento ViewSelectedBy para exibição (formato)](./viewselectedby-element-format.md)|Elemento obrigatório.<br /><br /> Define os objetos .NET exibidos por essa exibição.|
|[Elemento WideControl (Format)](./widecontrol-element-format.md)|Elemento opcional.<br /><br /> Define um formato de lista largo (valor único) para a exibição.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ViewDefinitions (Format)](./viewdefinitions-element-format.md)|Define as exibições usadas para exibir objetos.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes de diferentes exibições e controles personalizados, consulte os seguintes tópicos:

- [Componentes de exibição de tabela](./creating-a-table-view.md)

- [Componentes de exibição de lista](./creating-a-list-view.md)

- [Componentes de exibição ampla](./creating-a-wide-view.md)

- [Controles personalizados](./creating-custom-controls.md)

## <a name="example"></a>Exemplo

Este exemplo mostra um elemento `View` que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>Consulte Também

[Elemento ViewDefinitions (Format)](./viewdefinitions-element-format.md)

[Elemento de nome para exibição (formato)](./name-element-for-view-format.md)

[Elemento ViewSelectedBy (Format)](./viewselectedby-element-format.md)

[Elemento Controls para View (Format)](./controls-element-for-view-format.md)

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

[Elemento TableControl (Format)](./tablecontrol-element-format.md)

[Elemento ListControl (formato)](./listcontrol-element-format.md)

[Elemento WideControl (Format)](./widecontrol-element-format.md)

[Elemento CustomControl (Format)](./customcontrol-element-for-groupby-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
