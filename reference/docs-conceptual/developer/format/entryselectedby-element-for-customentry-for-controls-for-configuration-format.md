---
title: Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9467c8c2d80e46c0a47c31569efbddbabe25bb1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774262"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)

Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para a configuração (Format)

## <a name="syntax"></a>Sintaxe

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Define a condição que deve existir para que a definição de controle comum seja usada.|
|[Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica um conjunto de tipos .NET que usam essa definição do controle comum.|
|[Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica um tipo .NET que usa essa definição do controle comum.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para Controls para Configuration (formato)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Fornece uma definição do controle comum.|

## <a name="remarks"></a>Comentários

No mínimo, cada definição deve ter pelo menos um tipo .NET, um conjunto de seleção ou uma condição de seleção especificada. Não há nenhum limite máximo para o número de tipos, conjuntos de seleção ou condições de seleção que você pode especificar.

## <a name="see-also"></a>Consulte Também

[Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Elemento CustomEntry para CustomControl para Controls para Configuration (formato)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Elemento TypeName para EntrySelectedBy para Controls para Configuration (formato)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
