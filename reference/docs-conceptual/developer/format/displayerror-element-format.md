---
title: Elemento DisplayError (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774279"
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

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Por padrão, quando ocorre um erro durante a tentativa de exibir um dado, o local dos dados é deixado em branco. Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibida.

## <a name="see-also"></a>Consulte Também

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
