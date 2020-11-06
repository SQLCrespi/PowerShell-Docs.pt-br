---
ms.date: 06/12/2017
title: Sintaxe de pesquisa da Galeria
description: Este artigo descreve a interface do usuário usada para pesquisar conteúdo na Galeria do PowerShell.
ms.openlocfilehash: 7ad486095647f99056b37c2ca1a50db099a166c0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661364"
---
# <a name="gallery-search-syntax"></a>Sintaxe de pesquisa da Galeria

Você pode pesquisar a Galeria do PowerShell usando o [site da Galeria do PowerShell](https://www.powershellgallery.com/). O site da Galeria do PowerShell oferece uma caixa de pesquisa de texto em que você pode usar palavras, frases e expressões de palavra-chave para refinar os resultados da pesquisa.

## <a name="search-by-keywords"></a>Pesquisa com palavras-chave

```Syntax
dsc azure sql
```

A pesquisa tenta encontrar documentos relevantes contendo as três palavras-chave e retorna os documentos correspondentes.

## <a name="search-using-phrases-and-keywords"></a>Pesquisa usando frases e palavras-chave

```Syntax
"azure sql" deployment
```

Inserir uma frase entre aspas ("") altera a pesquisa para procurar pela frase específica, em vez de palavras-chave separadas. Documentos correspondentes normalmente devem conter exatamente a frase "azure sql", incluindo variações nas maiúsculas e minúsculas, como "Azure SQL" e geralmente também contêm a palavra “deployment".

## <a name="filtering-on-fields"></a>Filtrando pelos campos

Você pode pesquisar pela ID de um pacote específico (ou "Id" ou "id") ou por alguns outros campos, prefixando os termos de pesquisa com o nome do campo.

Atualmente, os campos pesquisáveis são "Id", "Version", "Tags", "Author", "Owner", "Functions", "Cmdlets", "DscResources" e "PowerShellVersion".

- ID é o nome que você usa no console.
- O título é mostrado na parte superior da página do pacote nos resultados da pesquisa.

## <a name="examples"></a>Exemplos

```Syntax
ID:PSReadline
```

Localiza pacotes com uma ID que contém "PSReadline".

```Syntax
Id:"AzureRM.Profile"
```

é outra maneira de localizar pacotes com "AzureRM.Profile" no campo de ID.

O filtro "Id" é correspondente a uma subcadeia, de modo que se pesquisar pelo seguinte:

```Syntax
Id:"azure"
```

Isso fornece resultados que incluem 'AzureRM.Profile' e 'Azure.Storage'.

Você também pode pesquisar por várias palavras-chave em um único campo.

```Syntax
id:azure tags:intellisense
```

E você pode fazer pesquisas por frase usando aspas duplas:

```Syntax
id:"azure.storage"
```

Para pesquisar todos os pacotes com a marca DSC.

```Syntax
Tags:DSC
```

Para pesquisar todos os pacotes com a função especificada.

```Syntax
Functions:Get-TreeSize
```

Para pesquisar todos os pacotes com o cmdlet especificado.

```Syntax
Cmdlets:Get-AzureRmEnvironment
```

Para pesquisar todos os pacotes com o nome do Recurso de DSC especificado.

```Syntax
DscResources:xArchive
```

Para pesquisar todos os pacotes com o PowerShellVersion especificado

```Syntax
PowerShellVersion:2.0
```

Por fim, se você usar um campo para o qual não há suporte, como "commands", vamos ignorá-lo e pesquisar em todos os campos. Sendo assim, a seguinte consulta

```Syntax
commands:blobs storage
```

É interpretada exatamente como esta consulta:

```Syntax
blobs storage
```
