---
title: Elemento PropertyName de ListItem para ListControl (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780824"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>Elemento PropertyName para ListItem para ListControl (formato)

Especifica a propriedade .NET cujo valor é exibido na lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) NomeDaPropriedade Element for ListItem (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido na linha da exibição de lista.|

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade cujo valor é exibido.

## <a name="remarks"></a>Comentários

Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .

Além de exibir o valor da propriedade, você também pode especificar um rótulo para o valor ou uma cadeia de caracteres de formato que possa ser usada para alterar a exibição do valor. Para obter mais informações sobre como especificar dados em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como especificar o rótulo e a propriedade cujo valor é exibido.

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>Consulte Também

[Elemento ScriptBlock para ListItem para ListControl (formato)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Criar uma exibição de lista](./creating-a-list-view.md)

[Elemento ListItem para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
