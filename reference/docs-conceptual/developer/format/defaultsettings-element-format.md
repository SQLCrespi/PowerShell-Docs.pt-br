---
title: Elemento DefaultSettings (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787726"
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

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DefaultSettings` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DisplayError (formato)](./displayerror-element-format.md)|Elemento opcional.<br /><br /> Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.|
|[Elemento EnumerableExpansions (formato)](./enumerableexpansions-element-format.md)|Elemento opcional.<br /><br /> Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.|
|[PropertyCountForTable (formato)](./propertycountfortable-element-format.md)|Elemento opcional.<br /><br /> Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.|
|[Elemento ShowError (formato)](./showerror-element-format.md)|Elemento opcional.<br /><br /> Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.|
|[Elemento WrapTables (formato)](./wraptables-element-format.md)|Elemento opcional.<br /><br /> Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de configuração](./configuration-element-format.md)|Representa o elemento de nível superior de um arquivo de formatação.|

## <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte Também

[Elemento de configuração](./configuration-element-format.md)

[Elemento DisplayError (formato)](./displayerror-element-format.md)

[Elemento EnumerableExpansions (formato)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (formato)](./propertycountfortable-element-format.md)

[Elemento ShowError (formato)](./showerror-element-format.md)

[Elemento WrapTables (formato)](./wraptables-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
