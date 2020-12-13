---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListControl (formato)
description: Elemento ListControl (formato)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666579"
---
# <a name="listcontrol-element-format"></a>Elemento ListControl (formato)

Define um formato de lista para a exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListControl` elemento. Este elemento deve conter apenas um único elemento filho.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListEntries (formato)](./listentries-element-for-listcontrol-format.md)|Elemento necessário.<br /><br /> Fornece as definições da exibição de lista.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que é usada para exibir os membros de um ou mais objetos.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre como criar um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra um modo de exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>Consulte Também

[Elemento View (formato)](./view-element-format.md)

[Elemento ListEntries (formato)](./listentries-element-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
