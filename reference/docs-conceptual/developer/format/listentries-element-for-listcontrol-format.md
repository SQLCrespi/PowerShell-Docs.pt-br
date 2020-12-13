---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListEntries para ListControl (formato)
description: Elemento ListEntries para ListControl (formato)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666596"
---
# <a name="listentries-element-for-listcontrol-format"></a>Elemento ListEntries para ListControl (formato)

Fornece as definições da exibição de lista. A exibição de lista deve especificar uma ou mais definições.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListEntries` elemento. Pelo menos um elemento filho deve ser especificado.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListEntry (Format)](./listentry-element-for-listcontrol-format.md)|Fornece uma definição da exibição de lista.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListControl (formato)](./listcontrol-element-format.md)|Define um formato de lista para a exibição.|

## <a name="remarks"></a>Comentários

Para obter mais informações sobre exibições de lista, consulte [exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

Este exemplo mostra os elementos XML que definem a exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>Consulte Também

[Elemento ListControl (formato)](./listcontrol-element-format.md)

[Elemento ListEntry (Format)](./listentry-element-for-listcontrol-format.md)

[Exibição de lista](./creating-a-list-view.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
