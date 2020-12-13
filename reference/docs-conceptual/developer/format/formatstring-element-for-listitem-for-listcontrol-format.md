---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para ListItem para ListControl (formato)
description: Elemento FormatString para ListItem para ListControl (formato)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667905"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a>Elemento FormatString para ListItem para ListControl (formato)

Especifica um padrão de formato que define como o valor de propriedade ou script é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems para o elemento ListControl (Format) ListItem de ListControl (Format) FormatString para ListItem para ListControl (Format)

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
|[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o padrão usado para formatar os dados. Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.

## <a name="remarks"></a>Comentários

Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas. Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).

Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições de lista, consulte [criando exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a>Consulte Também

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
