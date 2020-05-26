---
title: Como atualizar os arquivos de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 35b3fd696419d0135fd6f662223e6c8586df443a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811645"
---
# <a name="how-to-update-help-files"></a>Como atualizar os arquivos de ajuda

Este tópico explica como atualizar arquivos de ajuda para um módulo que dá suporte à ajuda atualizável.

## <a name="updating-help-files"></a>Atualizando arquivos de ajuda

Há muitas razões para atualizar os arquivos de ajuda, como corrigir erros, esclarecer um conceito, responder a uma pergunta frequente, adicionar novos arquivos ou adicionar novos e melhores exemplos.

Para atualizar um arquivo de ajuda:

1. Altere os arquivos.

2. Traduza os arquivos em outras culturas de interface do usuário.

3. Coletar todos os arquivos de ajuda (novos, alterados e inalterados) para o módulo em cada cultura de interface do usuário.

4. Valide os arquivos em relação ao esquema XML.

5. Recrie os arquivos CAB para cada cultura de interface do usuário.

6. No arquivo XML HelpInfo, aumente os números de versão do arquivo CAB para cada cultura de interface do usuário.

7. Carregue os novos arquivos CAB no local especificado pelo valor do elemento **HelpContentUri** no arquivo XML HelpInfo. Substitua os arquivos CAB mais antigos pelos novos arquivos CAB.

8. Carregue o arquivo XML HelpInfo atualizado no local especificado pela chave **HelpInfoUri** no manifesto do módulo. Substitua o arquivo XML HelpInfo mais antigo pelo novo arquivo.
