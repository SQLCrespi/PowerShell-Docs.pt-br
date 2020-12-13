---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomControl para GroupBy (formato)
description: Elemento CustomEntry para CustomControl para GroupBy (formato)
ms.openlocfilehash: 0df2ff9c15308939e6d2552f51e2961bdabc59fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646063"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a>Elemento CustomEntry para CustomControl para GroupBy (formato)

Fornece uma definição do controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element para CustomControl para GroupBy (Format)

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
|[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Elemento opcional.<br /><br /> Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.|
|[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)|Elemento necessário.<br /><br /> Define como o controle exibe os dados.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntries para CustomControl para GroupBy (formato)](./customentries-element-for-customcontrol-for-groupby-format.md)|Fornece as definições para o controle.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)

[Elemento CustomEntries para CustomControl para GroupBy (formato)](./customentries-element-for-customcontrol-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
