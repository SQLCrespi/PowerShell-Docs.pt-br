---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665063"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)

Especifica o script que dispara a condição. Quando esse script é avaliado como `true` , a condição é atendida e o item de lista é usado. Esse elemento é usado ao definir um modo de exibição de lista.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems do elemento de controle de lista (Format) ItemSelectionCondition para o elemento de ListItem para ListControl (Format) para ItemSelectionCondition para

## <a name="syntax"></a>Sintaxe

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e os elementos pai do `ScriptBlock` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento ItemSelectionCondition para ListItem para ListControl (formato)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Define a condição que deve existir para este item de lista ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o script que é avaliado.

## <a name="remarks"></a>Comentários

Se esse elemento for usado, você não poderá especificar o `PropertyName` elemento ao definir a condição de seleção.

## <a name="see-also"></a>Consulte Também

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
