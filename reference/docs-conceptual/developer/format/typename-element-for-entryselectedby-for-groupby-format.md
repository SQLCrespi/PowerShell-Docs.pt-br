---
title: Elemento TypeName para EntrySelectedBy para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e62762cf142bd2d20b21ad8f4249285bd3679280
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780256"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a>Elemento TypeName para EntrySelectedBy para GroupBy (formato)

Especifica um tipo .NET que usa essa definição do controle personalizado. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element para CustomEntry para o elemento GroupBy (Format) TypeName para EntrySelectedBy para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.|

## <a name="text-value"></a>Valor de texto

Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Comentários

Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.

Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).

## <a name="see-also"></a>Consulte Também

[Criar controles personalizados](./creating-custom-controls.md)

[Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
