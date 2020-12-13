---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomEntries para Controls para configuração (formato)
description: Elemento CustomEntry para CustomEntries para Controls para configuração (formato)
ms.openlocfilehash: a525b198c8f595e04dc0804d36b5533b94f43c6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646078"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>Elemento CustomEntry para CustomEntries para Controls para configuração (formato)

Fornece uma definição do controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.|
|[Elemento CustomItem para CustomEntry para Controls para View (formato)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Elemento necessário.<br /><br /> Define como o controle exibe os dados.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntries para CustomControl para View (formato)](./customentries-element-for-customcontrol-for-view-format.md)|Fornece as definições para o controle.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntries para CustomControl para View (formato)](./customentries-element-for-customcontrol-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
