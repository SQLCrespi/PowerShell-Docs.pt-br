---
title: Elemento Control para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369005"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Elemento Control para Controls para Configuration (formato)

Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.

Elemento de configuração (Format) controla o elemento de configuração (formato) elemento de controle para controles para configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Control`. Você deve especificar apenas um de cada elemento filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para controle de controles para configuração (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Elemento obrigatório.<br /><br /> Define o controle.|
|[Elemento Name para controle de configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Elemento obrigatório.<br /><br /> Especifica o nome usado para referenciar o controle.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Controla o elemento de configuração (formato)](./controls-element-for-configuration-format.md)|Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação ou por outros controles.|

## <a name="remarks"></a>Comentários

O nome fornecido a este controle pode ser referenciado nos seguintes elementos:

- [Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Controla o elemento de configuração (formato)](./controls-element-for-configuration-format.md)

[Elemento CustomControl para controle de configuração (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Elemento ExpressionBinding para CustomItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

[Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
