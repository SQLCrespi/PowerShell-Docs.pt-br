---
title: Elemento CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363355"
---
# <a name="customcontrol-element-for-view-format"></a>Elemento CustomControl para View (formato)

Define um formato de controle personalizado para a exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControl`. Você deve especificar um elemento filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntries para CustomControl para exibição (formato)](./customentries-element-for-customcontrol-for-view-format.md)|Elemento obrigatório.<br /><br /> Fornece as definições do modo de exibição de controle personalizado.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle, mas é possível fornecer várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes. Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntries para CustomControl para exibição (formato)](./customentries-element-for-customcontrol-for-view-format.md)

[Elemento View (formato)](./view-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
