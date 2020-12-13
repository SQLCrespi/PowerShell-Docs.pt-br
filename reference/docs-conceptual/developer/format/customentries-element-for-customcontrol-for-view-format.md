---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para View (formato)
description: Elemento CustomEntries para CustomControl para View (formato)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649975"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Elemento CustomEntries para CustomControl para View (formato)

Fornece as definições do modo de exibição de controle personalizado. A exibição de controle personalizado deve especificar uma ou mais definições.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlEntries` elemento. Você deve especificar um ou mais elementos filho.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Elemento necessário.<br /><br /> Fornece uma definição da exibição de controle personalizado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para View (formato)](./customcontrol-element-for-view-format.md)|Elemento necessário.<br /><br /> Define um formato de controle personalizado para a exibição.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento. No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET. Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para View (formato)](./customcontrol-element-for-view-format.md)

[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
