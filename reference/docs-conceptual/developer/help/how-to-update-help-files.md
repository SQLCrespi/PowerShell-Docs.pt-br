---
ms.date: 09/12/2016
ms.topic: reference
title: Como atualizar os arquivos de ajuda
description: Como atualizar os arquivos de ajuda
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649593"
---
# <a name="how-to-update-help-files"></a>Como atualizar os arquivos de ajuda

Este tópico explica como atualizar arquivos de ajuda para um módulo que dá suporte à ajuda atualizável.

## <a name="updating-help-files"></a>Atualizando arquivos de ajuda

Há muitas razões para atualizar os arquivos de ajuda, como corrigir erros, esclarecer um conceito, responder a uma pergunta frequente, adicionar novos arquivos ou adicionar novos e melhores exemplos.

Para atualizar um arquivo de ajuda:

1. Altere os arquivos.
1. Traduza os arquivos em outras culturas de interface do usuário.
1. Coletar todos os arquivos de ajuda (novos, alterados e inalterados) para o módulo em cada cultura de interface do usuário.
1. Valide os arquivos em relação ao esquema XML.
1. Recrie os arquivos CAB para cada cultura de interface do usuário.
1. No arquivo XML HelpInfo, aumente os números de versão do arquivo CAB para cada cultura de interface do usuário.
1. Carregue os novos arquivos CAB no local especificado pelo valor do elemento **HelpContentUri** no arquivo XML HelpInfo. Substitua os arquivos CAB mais antigos pelos novos arquivos CAB.
1. Carregue o arquivo XML HelpInfo atualizado no local especificado pela chave **HelpInfoUri** no manifesto do módulo. Substitua o arquivo XML HelpInfo mais antigo pelo novo arquivo.
