---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ListItem para ListControl (formato)
description: Elemento ItemSelectionCondition para ListItem para ListControl (formato)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667803"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>Elemento ItemSelectionCondition para ListItem para ListControl (formato)

Define a condição que deve existir para este item de lista ser usado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem para ListControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento PropertyName para ItemSelectionCondition para ListControl (formato)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que dispara a condição.|
|[Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|Elemento opcional.<br /><br /> Especifica o script que dispara a condição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ListItem para ListItems para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)|Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.|

## <a name="remarks"></a>Comentários

Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Elemento ListItem para ListItems para ListControl (formato)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Elemento PropertyName para ItemSelectionCondition para ListControl (formato)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
