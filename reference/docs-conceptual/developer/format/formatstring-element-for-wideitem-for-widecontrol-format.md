---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para WideItem para WideControl (formato)
description: Elemento FormatString para WideItem para WideControl (formato)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667871"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>Elemento FormatString para WideItem para WideControl (formato)

Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento para WideControl (Format) WideItem Element para WideControl (Format) FormatString Element for WideItem for WideControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `FormatString` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento WideItem para WideControl (formato)](./wideitem-element-for-widecontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o padrão usado para formatar os dados. Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.

## <a name="remarks"></a>Comentários

Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas. Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).

Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições amplas, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição ampla](./creating-a-wide-view.md)

[Elemento WideItem para WideControl (formato)](./wideitem-element-for-widecontrol-format.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
