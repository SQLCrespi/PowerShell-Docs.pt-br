---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ViewDefinitions (formato)
description: Elemento ViewDefinitions (formato)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664579"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ViewDefinitions` elemento. Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação e elas podem ser adicionadas em qualquer ordem.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Configuration (formato)](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre os componentes dos diferentes tipos de exibições, consulte os seguintes tópicos:

- [Criar uma exibição de tabela](./creating-a-table-view.md)

- [Criar uma exibição de lista](./creating-a-list-view.md)

- [Criar uma exibição ampla](./creating-a-wide-view.md)

- [Controles personalizados](./creating-custom-controls.md)

## <a name="example"></a>Exemplo

Este exemplo mostra um `ViewDefinitions` elemento que contém os elementos pai para uma exibição de tabela e um modo de exibição de lista.

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

[Elemento Configuration (formato)](./configuration-element-format.md)

[Elemento View (formato)](./view-element-format.md)

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Controles personalizados](./creating-custom-controls.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
