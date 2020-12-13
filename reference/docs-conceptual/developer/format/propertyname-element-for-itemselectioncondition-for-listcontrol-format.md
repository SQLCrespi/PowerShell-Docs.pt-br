---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para ListControl (formato)
description: Elemento PropertyName para ItemSelectionCondition para ListControl (formato)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665984"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>Elemento PropertyName para ItemSelectionCondition para ListControl (formato)

Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a exibição é usada. Esse elemento é usado ao definir um modo de exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) o elemento ListEntry do elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem for ListControls PropertyName Element para ItemSelectionCondition para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e os elementos pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ItemSelectionCondition para ListItem para ListControl (formato)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>Valor de texto

Especifique o nome da propriedade cujo valor é exibido.

## <a name="remarks"></a>Comentários

Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) ao definir a condição de seleção.

## <a name="see-also"></a>Consulte Também

[Elemento ScriptBlock para ItemSelectionCondition para ListIControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Elemento ItemSelectionCondition para ListItem para ListControl (formato)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
