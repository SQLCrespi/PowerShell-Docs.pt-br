---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FirstLineIndent para Frame para Controls para View (formato)
description: Elemento FirstLineIndent para Frame para Controls para View (formato)
ms.openlocfilehash: 425cd9ccafb2cbe36f238177fc73923da048f924
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660150"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a>Elemento FirstLineIndent para Frame para Controls para View (formato)

Especifica quantos caracteres a primeira linha de dados é deslocada para a direita. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl for View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para o elemento View (Format) FirstLineIndent do quadro de controles de View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `FirstLineIndent` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)|Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|

## <a name="text-value"></a>Valor de texto

Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.

## <a name="remarks"></a>Comentários

Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) .

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging para Frame para Controls para View (formato)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
