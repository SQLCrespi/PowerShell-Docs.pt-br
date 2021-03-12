---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: 9425f72ce4002fa871ef6b687d76f92ddf6b489e
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193903"
---
# Módulo PSReadLine

## Descrição

O módulo PSReadLine contém cmdlets que permitem personalizar o ambiente de edição de linha de comando no PowerShell. Estes artigos documentam a versão beta atual do PSReadLine v 2.2.0.

> [!NOTE]
> A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado. Atualmente, o PSReadLine não funciona bem com os leitores de tela. A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente. Você pode carregar o módulo manualmente, se necessário.

## Cmdlets PSReadLine

### [PSConsoleHostReadLine](PSConsoleHostReadLine.md)
O ponto de entrada principal para PSReadLine.

### [Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)
Obtém as funções de chave associadas para o módulo PSReadLine.

### [Get-PSReadLineOption](Get-PSReadLineOption.md)
Obtém valores para as opções que podem ser configuradas.

### [PSConsoleHostReadLine](PSConsoleHostReadLine.md)
Essa função é o ponto de entrada principal para PSReadLine.

### [Remove-PSReadLineKeyHandler](Remove-PSReadLineKeyHandler.md)
Remove uma associação de chave.

### [Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
Associa as chaves às funções de manipulador de chave definidas pelo usuário ou PSReadLine.

### [Set-PSReadLineOption](Set-PSReadLineOption.md)
Personaliza o comportamento da edição de linha de comando no **PSReadLine**.

