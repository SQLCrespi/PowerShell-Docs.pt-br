---
title: Elemento WideEntry para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780008"
---
# <a name="wideentry-element-for-widecontrol-format"></a>Elemento WideEntry para WideControl (formato)

Fornece uma definição da exibição ampla.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format)

## <a name="syntax"></a>Sintaxe

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntry` elemento. Você deve especificar um único `WideItem` elemento filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para WideEntry (formato)](./entryselectedby-element-for-wideentry-format.md)|Elemento opcional.<br /><br /> Define os tipos .NET que usam essa definição de entrada larga ou a condição que deve existir para que essa definição seja usada.|
|[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)|Elemento necessário.<br /><br /> Define a propriedade ou o script cujo valor é exibido.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)|Fornece as definições da exibição ampla.|

## <a name="remarks"></a>Comentários

Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto. Ao contrário de outros tipos de exibições, você pode especificar apenas um elemento item para cada definição de exibição. Para obter mais informações sobre os outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento. O `WideItem` elemento define a propriedade cujo valor é exibido na exibição.

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Elemento SelectionCondition para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento SelectionSetName para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Elemento TypeName para WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md)

[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
