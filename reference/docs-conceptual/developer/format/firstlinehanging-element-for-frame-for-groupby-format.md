---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FirstLineHanging para Frame para GroupBy (formato)
description: Elemento FirstLineHanging para Frame para GroupBy (formato)
ms.openlocfilehash: 6a4ded9cced484440636aee694cd8381b2889ba8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652271"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a>Elemento FirstLineHanging para Frame para GroupBy (formato)

Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento CustomItem de GroupBy (Format) para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para o elemento FirstLineHanging de GroupBy (Format) para o

## <a name="syntax"></a>Sintaxe

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elemento pai do `FirstLineHanging` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Frame para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)|Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.|

## <a name="text-value"></a>Valor de texto

Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.

## <a name="remarks"></a>Comentários

Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) .

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineIndent para Frame para GroupBy (formato)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Elemento Frame para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
