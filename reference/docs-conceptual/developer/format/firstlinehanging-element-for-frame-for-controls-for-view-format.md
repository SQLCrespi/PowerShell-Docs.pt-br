---
title: Elemento FirstLineHanging para frame para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 88c64619715c935089eb6c5a771584e4f69171d3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773616"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a>Elemento FirstLineHanging para Frame para Controls para View (formato)

Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl for View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para o elemento View (Format) FirstLineHanging do quadro de controles de View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `FirstLineHanging` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)|Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|

## <a name="text-value"></a>Valor de texto

Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.

## <a name="remarks"></a>Comentários

Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) .

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineIndent para Frame para Controls para View (formato)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[Elemento Frame para CustomItem para Controls para View (formato)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
