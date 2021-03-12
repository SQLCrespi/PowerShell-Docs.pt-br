---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: 3adfa4be7aae03120d2334a57c39d7e6351bcb16
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196204"
---
# Módulo PSReadLine

## Descrição

O módulo PSReadLine contém cmdlets que permitem personalizar o ambiente de edição de linha de comando no PowerShell. O PowerShell 7,1 foi fornecido com o PSReadLine v 2.1. Estes artigos documentam o PSReadLine v 2.1.

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

