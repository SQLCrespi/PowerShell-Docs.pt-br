---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para Controls para View (formato)
description: Elemento CustomEntries para CustomControl para Controls para View (formato)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652379"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>Elemento CustomEntries para CustomControl para Controls para View (formato)

Fornece as definições para o controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para Controls for View (Format)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elementos pai do `CustomEntries` elemento. Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Elemento necessário.<br /><br /> Fornece uma definição do controle.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para Control para Controls para View (formato)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Define o controle usado pela exibição.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único `CustomEntry` elemento. No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET. Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomEntry para CustomEntries para Controls para configuração (formato)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Elemento CustomControl para Control para Controls para View (formato)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
