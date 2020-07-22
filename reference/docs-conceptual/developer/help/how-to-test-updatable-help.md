---
title: Como testar a ajuda atualizável
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892958"
---
# <a name="how-to-test-updatable-help"></a>Como testar a ajuda atualizável

Este tópico descreve as abordagens para testar a ajuda atualizável para um módulo.

## <a name="using-verbose-to-detect-errors"></a>Usando o modo detalhado para detectar erros

Depois de carregar o arquivo XML HelpInfo e os arquivos CAB para seu módulo, teste os arquivos executando um comando [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) com o parâmetro **Verbose** . O parâmetro **Verbose** direciona `Update-Help` para relatar as etapas críticas em suas ações, da leitura da chave **HelpInfoUri** no manifesto do módulo para validar os tipos de arquivo no arquivo CAB desempacotado e colocar os arquivos no diretório de módulo específico do idioma.

Quando todas as mensagens detalhadas forem resolvidas, execute um `Update-Help` comando com o parâmetro **debug** .
Esse parâmetro deve detectar quaisquer problemas restantes com os arquivos de ajuda atualizáveis.
