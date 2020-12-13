---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para GroupBy (formato)
description: Elemento Frame para CustomItem para GroupBy (formato)
ms.openlocfilehash: 86b51766974ebfcae06583ade237a77c6db92866
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652174"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Elemento Frame para CustomItem para GroupBy (formato)

Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries de GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento CustomItem de GroupBy (Format) para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|`CustomItem Element`|Elemento obrigatório|
|[Elemento FirstLineHanging para Frame para GroupBy (formato)](./firstlinehanging-element-for-frame-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.|
|[Elemento FirstLineIndent para Frame para GroupBy (formato)](./firstlineindent-element-for-frame-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.|
|[Elemento LeftIndent para Frame para GroupBy (formato)](./leftindent-element-for-frame-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.|
|[Elemento RightIndent para frame para GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Elemento RightIndent|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem direita.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)|Define quais dados são exibidos pelo controle e como eles são exibidos.|

## <a name="remarks"></a>Comentários

Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) no mesmo `Frame` elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging para Frame para GroupBy (formato)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Elemento FirstLineIndent para Frame para GroupBy (formato)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Elemento LeftIndent para Frame para GroupBy (formato)](./leftindent-element-for-frame-for-groupby-format.md)

[Elemento RightIndent para Frame para GroupBy (formato)](./rightindent-element-for-frame-for-groupby-format.md)

[Elemento CustomItem para CustomEntry para GroupBy (formato)](./customitem-element-for-customentry-for-groupby-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
