---
title: Elemento FirstLineIndent de quadro para controles de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065981"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a>Elemento FirstLineIndent para Frame para Controls para Configuration (formato)

Especifica quantos caracteres, a primeira linha de dados é deslocada para a direita. Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de CustomControl de configuração (formato) para o controle para o elemento de configuração (formato) de CustomEntries para CustomControl para configuração ( Elemento de CustomEntry Format) para CustomControl para controles para configuração (formato) elemento CustomItem CustomEntry controles para o elemento de quadro de configuração para CustomItem controles para o elemento de configuração (formato) de FirstLineIndent para quadro para controles de configuração (formato)

## <a name="syntax"></a>Sintaxe

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FirstLineIndent` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de quadro para CustomItem para controles de configuração (formato)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.|

## <a name="text-value"></a>Valor de texto

Especifique o número de caracteres que você deseja deslocar a primeira linha dos dados.

## <a name="remarks"></a>Comentários

Se esse elemento for especificado, não é possível especificar o [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging de quadro para controles de configuração (formato)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Elemento de quadro para CustomItem para controles de configuração (formato)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
