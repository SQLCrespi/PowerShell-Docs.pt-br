---
title: Como testar a Ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082310"
---
# <a name="how-to-test-updatable-help"></a>Como testar a ajuda atualizável

Este tópico descreve abordagens para testar a Ajuda atualizável para um módulo.

## <a name="using-verbose-to-detect-errors"></a>Uso detalhado para detectar erros

Depois de carregar o arquivo XML HelpInfo e os arquivos CAB para o seu módulo, os arquivos de teste, executando uma [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) com o **detalhado** parâmetro. O **Verbose** parâmetro direciona `Update-Help` para relatar as etapas essenciais em suas ações, de leitura a **HelpInfoUri** chave no manifesto de módulo para validar os tipos de arquivo no arquivo CAB descompactado e colocar os arquivos no diretório do módulo de idioma específico.

Quando todas as mensagens detalhadas são resolvidas, executar uma `Update-Help` com o **depurar** parâmetro. Esse parâmetro deve detectar problemas restantes com os arquivos de ajuda atualizável.