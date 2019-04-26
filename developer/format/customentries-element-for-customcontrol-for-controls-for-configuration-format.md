---
title: Elemento CustomEntries para CustomControl para controles de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066593"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Elemento CustomEntries para CustomControl para Controls para Configuration (formato)

Fornece as definições de um controle comum. Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de CustomControl de configuração (formato) para o controle para o elemento de configuração (formato) de CustomEntries para CustomControl para configuração ( Formato)

## <a name="syntax"></a>Sintaxe

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntries` elemento. Você deve especificar um ou mais elementos filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomEntry para CustomControl para controles de configuração (formato)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Fornece uma definição do controle comum.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para controle de configuração (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Define um controle comum.|

## <a name="remarks"></a>Comentários

Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento. No entanto é possível ter várias definições, se você quiser usar o mesmo controle para exibir objetos diferentes do .NET. Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControl para controle de configuração (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Elemento CustomEntry para CustomControl para controles de configuração (formato)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
