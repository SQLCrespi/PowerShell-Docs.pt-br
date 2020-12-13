---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para CustomControl para View (formato)
description: Elemento Frame para CustomItem para CustomControl para View (formato)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652194"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Elemento Frame para CustomItem para CustomControl para View (formato)

Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento de quadro CustomControlView (Format) para CustomItem para CustomControl para View (Format)

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
|[Elemento FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.|
|[Elemento FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.|
|[Elemento LeftIndent](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.|
|[Elemento RightIndent](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem direita.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para exibição (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Define quais dados são exibidos pelo controle e como eles são exibidos.|

## <a name="remarks"></a>Comentários

Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) no mesmo `Frame` elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Elemento FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Elemento LeftIndent](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[Elemento RightIndent](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[Elemento CustomItem para CustomEntry para exibição (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
