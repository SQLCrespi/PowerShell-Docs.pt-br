---
title: Elemento CustomEntries para CustomControl para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364085"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>Elemento CustomEntries para CustomControl para GroupBy (formato)

Fornece as definições para o controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elementos pai do elemento `CustomEntries`. Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Elemento obrigatório.<br /><br /> Fornece uma definição do controle.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Define o controle personalizado que exibe o novo grupo.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único elemento `CustomEntry`. No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes grupos. Nesses casos, você pode definir um elemento `CustomEntry` para um grupo.

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomEntries para controles para View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Elemento CustomControl para GroupBy (Format)](./customcontrol-element-for-groupby-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
