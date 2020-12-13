---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para Controls para View (formato)
description: Elemento Frame para CustomItem para Controls para View (formato)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652197"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>Elemento Frame para CustomItem para Controls para View (formato)

Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para View (Format)

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
|[Elemento FirstLineHanging do quadro de controles de View (Format)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha é deslocada para a esquerda.|
|[Elemento FirstLineIndent do quadro de controles de View (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha é deslocada para a direita.|
|[Elemento LeftIndent do quadro de controles de View (Format)](./leftindent-element-for-frame-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.|
|[Elemento RightIndent do quadro de controles de View (Format)](./rightindent-element-for-frame-for-controls-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem direita.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para Controls para View (formato)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Define quais dados são exibidos pelo controle e como eles são exibidos.|

## <a name="remarks"></a>Comentários

Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) no mesmo `Frame` elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging do quadro de controles de View (Format)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[Elemento FirstLineIndent do quadro de controles de View (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[Elemento LeftIndent do quadro de controles de View (Format)](./leftindent-element-for-frame-for-controls-for-view-format.md)

[Elemento RightIndent do quadro de controles de View (Format)](./rightindent-element-for-frame-for-controls-for-view-format.md)

[Elemento CustomItem para CustomEntry para Controls para View (formato)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
