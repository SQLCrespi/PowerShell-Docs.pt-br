---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomControl para View (formato)
description: Elemento CustomControl para View (formato)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655464"
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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControl` elemento. Você deve especificar um elemento filho.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntries para CustomControl para View (formato)](./customentries-element-for-customcontrol-for-view-format.md)|Elemento necessário.<br /><br /> Fornece as definições do modo de exibição de controle personalizado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição usada para exibir um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle, mas é possível fornecer várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes. Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntries para CustomControl para View (formato)](./customentries-element-for-customcontrol-for-view-format.md)

[Elemento View (formato)](./view-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
