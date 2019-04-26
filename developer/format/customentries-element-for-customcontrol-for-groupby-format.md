---
title: Elemento CustomEntries para CustomControl para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066525"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>Elemento CustomEntries para CustomControl para GroupBy (formato)

Fornece as definições para o controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para GroupBy (formato)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e elementos pai do `CustomEntries` elemento. Não há nenhum limite máximo ao número de elementos filho que podem ser especificados.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para GroupBy (formato)](./customentry-element-for-customcontrol-for-groupby-format.md)|Elemento necessário.<br /><br /> Fornece uma definição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para GroupBy (formato)](./customcontrol-element-for-groupby-format.md)|Define o controle personalizado que exibe o novo grupo.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único `CustomEntry` elemento. No entanto, é possível fornecer várias definições, se você quiser usar o mesmo controle para exibir os grupos diferentes. Nesses casos, você pode definir um `CustomEntry` elemento para um grupo.

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomEntries controles para exibição (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Elemento CustomControl para GroupBy (formato)](./customcontrol-element-for-groupby-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
