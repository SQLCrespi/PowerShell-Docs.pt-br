---
title: Elemento Controls para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368995"
---
# <a name="controls-element-for-configuration-format"></a>Elemento Controls para Configuration (formato)

Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.

Elemento de configuração (Format) controla o elemento de configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Controls`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Control para controles para configuração (Format)](./control-element-for-controls-for-configuration-format.md)|Elemento obrigatório.<br /><br /> Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Configuration (Format)](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

Você pode criar qualquer número de controles comuns. Para cada controle, você deve especificar o nome que é usado para referenciar o controle e os componentes do controle.

## <a name="see-also"></a>Consulte Também

[Elemento Configuration (Format)](./configuration-element-format.md)

[Elemento Control para controles para configuração (Format)](./control-element-for-controls-for-configuration-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
