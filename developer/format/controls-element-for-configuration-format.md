---
title: Controla o elemento de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066865"
---
# <a name="controls-element-for-configuration-format"></a>Elemento Controls para Configuration (formato)

Define os controles comuns que podem ser usados por todos os modos de exibição do arquivo de formatação.

Elemento de controles de (formato) do elemento de configuração da configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `Controls` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de controle para controles de configuração (formato)](./control-element-for-controls-for-configuration-format.md)|Elemento necessário.<br /><br /> Define um controle comum que pode ser usado por todos os modos de exibição do arquivo de formatação.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de configuração (formato)](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode criar qualquer número de controles comuns. Para cada controle, você deve especificar o nome que é usado para referenciar o controle e os componentes do controle.

## <a name="see-also"></a>Consulte Também

[Elemento de configuração (formato)](./configuration-element-format.md)

[Elemento de controle para controles de configuração (formato)](./control-element-for-controls-for-configuration-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
