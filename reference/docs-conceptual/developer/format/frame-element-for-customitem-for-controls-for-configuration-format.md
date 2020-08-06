---
title: Elemento frame para CustomItem para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781470"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Elemento Frame para CustomItem para Controls para Configuration (formato)

Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para os controles do elemento de quadro de configuração para CustomItem para controles para configuração

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

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|`CustomItem Element`|Elemento obrigatório|
|[Elemento FirstLineHanging para Frame para Controls para Configuration (formato)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.|
|[Elemento FirstLineIndent para Frame para Controls para Configuration (formato)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.|
|[Elemento LeftIndent para Frame para Controls para Configuration (formato)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.|
|[Elemento RightIndent para Frame para Controls para Configuration (formato)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|Elemento opcional.<br /><br /> Especifica quantos caracteres os dados são deslocados para fora da margem direita.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomItem para CustomEntry para controles de configuração](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Define quais dados são exibidos pelo controle e como eles são exibidos.|

## <a name="remarks"></a>Comentários

Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) no mesmo `Frame` elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineHanging para Frame para Controls para Configuration (formato)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Elemento FirstLineIndent para Frame para Controls para Configuration (formato)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Elemento LeftIndent para Frame para Controls para Configuration (formato)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Elemento RightIndent para Frame para Controls para Configuration (formato)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[Elemento CustomItem para CustomEntry para controles de configuração](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
