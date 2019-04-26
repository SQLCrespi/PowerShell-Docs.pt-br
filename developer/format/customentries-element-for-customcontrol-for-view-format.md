---
title: Elemento CustomEntries para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066508"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Elemento CustomEntries para CustomControl para View (formato)

Fornece as definições do modo de exibição de controle personalizado. O modo de exibição do controle personalizado deve especificar uma ou mais definições.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para exibição (formato)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlEntries` elemento. Você deve especificar um ou mais elementos filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Elemento necessário.<br /><br /> Fornece uma definição da exibição de controle personalizado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para exibição (formato)](./customcontrol-element-for-view-format.md)|Elemento necessário.<br /><br /> Define um formato de controle personalizado para o modo de exibição.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento. No entanto é possível ter várias definições, se você quiser usar o mesmo controle para exibir objetos diferentes do .NET. Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para exibição (formato)](./customcontrol-element-for-view-format.md)

[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
