---
ms.date: 07/29/2020
keywords: powershell, cmdlet
title: Como usar a documentação do PowerShell
description: Este artigo explica como usar os recursos deste site, incluindo filtragem de pesquisa e seleção de versão.
ms.openlocfilehash: b7e036fce0abb12f6c1ab4c0092784321a41a916
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810293"
---
# <a name="how-to-use-the-powershell-documentation"></a>Como usar a documentação do PowerShell

Bem-vindo à documentação online do PowerShell. Este site contém a referência de cmdlet para as seguintes versões do PowerShell:

- PowerShell 7.2 (pré-lançamento)
- PowerShell 7.1 (atual)
- PowerShell 7.0 (LTS)
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>Localizar artigos e selecionar uma versão

Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão. Basta inserir uma palavra que aparece no título de um artigo. A página exibe uma lista de artigos correspondentes. Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.

Por padrão, o site exibe a documentação da última versão lançada do PowerShell. Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell. Verifique se você está visualizando a documentação da versão do PowerShell que está usando.

Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.

![Usar o seletor de versão](media/how-to-use-docs/version-search.gif)

Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`. O exemplo a seguir mostra a saída do Windows PowerShell 5.1.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

Se você for iniciante no PowerShell e precisar de ajuda para entender a sintaxe do comando, confira [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).

## <a name="finding-articles-for-previous-versions"></a>Localizar artigos de versões anteriores

A documentação de versões mais antigas do PowerShell foi arquivada em nosso site [Versões anteriores](https://aka.ms/PSLegacyDocs).

Ele contém a documentação dos seguintes tópicos:

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- PowerShell 6
- Fluxo de Trabalho do PowerShell
- Windows PowerShell Web Access
