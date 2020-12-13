---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento DisplayError (formato)
description: Elemento DisplayError (formato)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649922"
---
# <a name="displayerror-element-format"></a>Elemento DisplayError (formato)

Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.

Elemento de configuração (Format) DefaultSettings Element (Format) elemento DisplayError (Format)

## <a name="syntax"></a>Sintaxe

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DisplayError` elemento.

### <a name="attributes"></a>Atributos

nenhuma.

### <a name="child-elements"></a>Elementos filho

nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Por padrão, quando ocorre um erro durante a tentativa de exibir um dado, o local dos dados é deixado em branco. Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibida.

## <a name="see-also"></a>Consulte Também

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
