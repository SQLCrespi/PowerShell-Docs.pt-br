---
ms.date: 10/20/2019
keywords: powershell, cmdlet
title: Como usar a documentação do PowerShell
ms.openlocfilehash: 50b054ddc21d55946969414688306fc0d15a5adf
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80082828"
---
# <a name="how-to-use-the-powershell-documentation"></a>Como usar a documentação do PowerShell

Bem-vindo à documentação online do PowerShell. Este site contém a referência de cmdlet para as seguintes versões do PowerShell:

- PowerShell 7
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>Localizar artigos e selecionar uma versão

Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão. Basta inserir uma palavra que aparece no título de um artigo. A página exibe uma lista de artigos correspondentes. Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.

Por padrão, o site exibe a documentação da última versão lançada do PowerShell. Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell. Verifique se você está visualizando a documentação da versão do PowerShell que está usando.

Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.

![seletor de versão](media/how-to-use-docs/version-search.gif)

Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`. O exemplo a seguir mostra a saída do Windows PowerShell v5.1.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```
