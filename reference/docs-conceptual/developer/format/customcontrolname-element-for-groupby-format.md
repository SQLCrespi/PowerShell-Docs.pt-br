---
title: Elemento CustomControlName para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368875"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Elemento CustomControlName para GroupBy (formato)

Especifica o nome de um controle personalizado que é usado para exibir o novo grupo. Esse elemento é usado ao definir uma tabela, lista, exibição de controle largo ou personalizada.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControlName element de GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do elemento `CustomControlName`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

Nenhum.

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)|Define como o Windows PowerShell exibe um novo grupo de objetos.|

## <a name="text-value"></a>Valor de Texto

Especifique o nome do controle personalizado usado para exibir um novo grupo.

## <a name="remarks"></a>Comentários

Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica. Os seguintes elementos especificam os nomes desses controles personalizados:

- [Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Elemento Name para controle de controles para View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Consulte Também

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)

[Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Elemento Name para controle de controles para View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
