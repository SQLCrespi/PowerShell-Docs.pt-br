---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para ViewSelectedBy (formato)
description: Elemento TypeName para ViewSelectedBy (formato)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667718"
---
# <a name="typename-element-for-viewselectedby-format"></a>Elemento TypeName para ViewSelectedBy (formato)

Especifica um objeto .NET que é exibido pela exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e os elementos pai do `TypeName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ViewSelectedBy (formato)](./viewselectedby-element-format.md)|Define os objetos .NET que são exibidos pela exibição.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Comentários

Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [criando uma exibição de tabela](./creating-a-table-view.md), [criando uma exibição de lista](./creating-a-list-view.md), [criando uma exibição ampla](./creating-a-wide-view.md)e [componentes de exibição personalizada](./creating-custom-controls.md).

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

[Criar uma exibição de lista](./creating-a-list-view.md)

[Criar uma exibição de tabela](./creating-a-table-view.md)

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Criar controles personalizados](./creating-custom-controls.md)

[Elemento ViewSelectedBy (formato)](./viewselectedby-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
