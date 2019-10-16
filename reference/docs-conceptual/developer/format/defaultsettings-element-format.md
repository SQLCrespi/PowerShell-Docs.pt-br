---
title: Elemento DefaultSettings (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363865"
---
# <a name="defaultsettings-element-format"></a>Elemento DefaultSettings (formato)

Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação. As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.

Elemento Configuration (formato) DefaultSettings Element (Format)

## <a name="syntax"></a>Sintaxe

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `DefaultSettings`.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DisplayError (Format)](./displayerror-element-format.md)|Elemento opcional.<br /><br /> Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.|
|[Elemento EnumerableExpansions (Format)](./enumerableexpansions-element-format.md)|Elemento opcional.<br /><br /> Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.|
|[PropertyCountForTable (formato)](./propertycountfortable-element-format.md)|Elemento opcional.<br /><br /> Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.|
|[Elemento TextError (formato)](./showerror-element-format.md)|Elemento opcional.<br /><br /> Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.|
|[Elemento WrapTables (Format)](./wraptables-element-format.md)|Elemento opcional.<br /><br /> Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de configuração](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento de configuração](./configuration-element-format.md)

[Elemento DisplayError (Format)](./displayerror-element-format.md)

[Elemento EnumerableExpansions (Format)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (formato)](./propertycountfortable-element-format.md)

[Elemento TextError (formato)](./showerror-element-format.md)

[Elemento WrapTables (Format)](./wraptables-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
