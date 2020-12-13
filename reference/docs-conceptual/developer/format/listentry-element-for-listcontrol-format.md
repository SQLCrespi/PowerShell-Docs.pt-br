---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListEntry para ListControl (formato)
description: Elemento ListEntry para ListControl (formato)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666562"
---
# <a name="listentry-element-for-listcontrol-format"></a>Elemento ListEntry para ListControl (formato)

Fornece uma definição da exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListEntry` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Define os objetos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada.|
|[Elemento ListItems (formato)](./listitems-element-for-listentry-for-listcontrol-format.md)|Elemento necessário.<br /><br /> Define as propriedades e os scripts cujos valores são exibidos pela exibição de lista.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListEntries (formato)](./listentries-element-for-listcontrol-format.md)|Fornece as definições da exibição de lista.|

## <a name="remarks"></a>Comentários

Uma exibição de lista é um formato de lista que exibe valores de propriedade ou valores de script para cada objeto. Para obter mais informações sobre exibições de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

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

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento EntrySelectedBy para ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Elemento ListEntries (formato)](./listentries-element-for-listcontrol-format.md)

[Elemento ListItems (formato)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
