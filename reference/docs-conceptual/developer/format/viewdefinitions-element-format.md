---
title: Elemento ViewDefinitions (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361415"
---
# <a name="viewdefinitions-element-format"></a>Elemento ViewDefinitions (formato)

Define as exibições usadas para exibir objetos .NET. Essas exibições podem exibir as propriedades e os valores de script de um objeto em um formato de tabela, formato de lista, formato largo e formato de controle personalizado.

Elemento de configuração (Format) ViewDefinitions (Format XML) Element

## <a name="syntax"></a>Sintaxe

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ViewDefinitions`. Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação e elas podem ser adicionadas em qualquer ordem.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Configuration (Format)](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes dos diferentes tipos de exibições, consulte os seguintes tópicos:

- [Criando uma exibição de tabela](./creating-a-table-view.md)

- [Criando um modo de exibição de lista](./creating-a-list-view.md)

- [Criando uma exibição ampla](./creating-a-wide-view.md)

- [Controles personalizados](./creating-custom-controls.md)

## <a name="example"></a>Exemplo

Este exemplo mostra um elemento `ViewDefinitions` que contém os elementos pai de uma exibição de tabela e uma exibição de lista.

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>Consulte Também

[Elemento Configuration (Format)](./configuration-element-format.md)

[Elemento View (formato)](./view-element-format.md)

[Criando uma exibição de tabela](./creating-a-table-view.md)

[Criando um modo de exibição de lista](./creating-a-list-view.md)

[Criando uma exibição ampla](./creating-a-wide-view.md)

[Controles personalizados](./creating-custom-controls.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
