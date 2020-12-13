---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomEntries para CustomControl para View (formato)
description: Elemento CustomEntry para CustomEntries para CustomControl para View (formato)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646050"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>Elemento CustomEntry para CustomEntries para CustomControl para View (formato)

Fornece uma definição da exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format) CustomEntry Element for CustomEntries para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntry` elemento. Você deve especificar os itens exibidos pela definição.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Define os tipos .NET que usam a definição do modo de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.|
|[Elemento CustomItem para CustomEntry para exibição (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Define um controle para a definição de controle personalizado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntries para CustomControl para View (formato)](./customentries-element-for-customcontrol-for-view-format.md)|Fornece as definições do modo de exibição de controle personalizado. A exibição de controle personalizado deve especificar uma ou mais definições.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle personalizado, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes. Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para View (formato)](./customcontrol-element-for-view-format.md)

[Elemento CustomItem para CustomEntry para exibição (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
