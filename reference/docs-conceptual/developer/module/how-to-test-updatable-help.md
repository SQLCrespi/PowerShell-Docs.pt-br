---
title: Como testar a ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560501"
---
# <a name="how-to-test-updatable-help"></a>Como testar a ajuda atualizável

Este tópico descreve as abordagens para testar a ajuda atualizável para um módulo.

## <a name="using-verbose-to-detect-errors"></a>Usando o modo detalhado para detectar erros

Depois de carregar o arquivo XML HelpInfo e os arquivos CAB para seu módulo, teste os arquivos executando um comando [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) com o parâmetro **Verbose** . O parâmetro **Verbose** direciona `Update-Help` para relatar as etapas críticas em suas ações, da leitura da chave **HelpInfoUri** no manifesto do módulo para validar os tipos de arquivo no arquivo CAB desempacotado e colocar os arquivos no diretório de módulo específico do idioma.

Quando todas as mensagens detalhadas forem resolvidas, execute um `Update-Help` comando com o parâmetro **debug** . Esse parâmetro deve detectar quaisquer problemas restantes com os arquivos de ajuda atualizáveis.
