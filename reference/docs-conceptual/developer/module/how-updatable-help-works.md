---
title: Como funciona a ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7674636e-a0f2-4587-bfc5-dd3e6ce5489e
caps.latest.revision: 6
ms.openlocfilehash: 5b6ae54ee6c843996c875189b6ee553be5e4f614
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367075"
---
# <a name="how-updatable-help-works"></a>Como a ajuda atualizável funciona

Este tópico explica como a ajuda atualizável processa o arquivo XML HelpInfo e os arquivos CAB para cada módulo e instala a ajuda atualizada para os usuários.

## <a name="the-update-help-process"></a>O processo de atualização-ajuda

A lista a seguir descreve as ações do cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) quando um usuário executa um comando para atualizar os arquivos de ajuda para um módulo em uma cultura de interface do usuário específica.

1. `Update-Help` Obtém o arquivo XML HelpInfo remoto do local especificado pelo valor da chave **HelpInfoURI** no manifesto do módulo e valida o arquivo em relação ao esquema. (Para exibir o esquema, consulte [HELPINFO XML Schema](./helpinfo-xml-schema.md).) Em seguida, `Update-Help` procura um arquivo XML HelpInfo local para o módulo no diretório do módulo no computador do usuário.

2. `Update-Help` compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais para o módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local ou se não houver nenhum arquivo XML HelpInfo local para o módulo, o `Update-Help` se preparar para baixar novos arquivos de ajuda.

3. `Update-Help` seleciona o arquivo CAB para o módulo a partir do local especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo remoto. Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

4. `Update-Help` baixa o arquivo CAB, o desempacota, valida os arquivos de conteúdo da ajuda e salva os arquivos de conteúdo da ajuda no subdiretório específico do idioma do diretório do módulo no computador do usuário.

5. `Update-Help` cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele instalou. Em seguida, ele salva o arquivo XML HelpInfo local no diretório do módulo e conclui a atualização.

## <a name="the-save-help-process"></a>O processo de salvar-ajuda

A lista a seguir descreve as ações dos cmdlets [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) e [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) quando um usuário executa comandos para atualizar os arquivos de ajuda em um compartilhamento de arquivos e, em seguida, usa esses arquivos para atualizar os arquivos de ajuda no computador do usuário.

O cmdlet `Save-Help` executa as seguintes ações em resposta a um comando para salvar os arquivos de ajuda de um módulo em um compartilhamento de arquivos que é especificado pelo parâmetro **DestinationPath** .

1. `Save-Help` Obtém o arquivo XML HelpInfo remoto do local especificado pelo valor da chave **HelpInfoURI** no manifesto do módulo e valida o arquivo em relação ao esquema. (Para exibir o esquema, consulte [HELPINFO XML Schema](./helpinfo-xml-schema.md).) Em seguida, `Save-Help` procura um arquivo XML HelpInfo local no diretório especificado pelo parâmetro **DestinationPath** no comando `Save-Help`.

2. `Save-Help` compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais para o módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local, ou se não houver nenhum arquivo XML HelpInfo local para o módulo no diretório **DestinationPath** , `Save-Help` se preparar para baixar novos arquivos de ajuda.

3. `Save-Help` seleciona o arquivo CAB para o módulo a partir do local especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo remoto. Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

4. `Save-Help` baixa o arquivo CAB e o salva no diretório **DestinationPath** (Ele não cria subdiretórios específicos do idioma.)

5. `Save-Help` cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele salvou. Em seguida, ele salva o arquivo XML HelpInfo local no diretório **DestinationPath** e conclui a atualização.

   O cmdlet `Update-Help` executa as seguintes ações em resposta a um comando para atualizar os arquivos de ajuda no computador de um usuário a partir dos arquivos em um compartilhamento de arquivo especificado pelo parâmetro **SourcePath** .

1. `Update-Help` Obtém o arquivo XML HelpInfo remoto do diretório **SourcePath** . Em seguida, ele procura um arquivo XML HelpInfo local no diretório do módulo no computador do usuário.

2. `Update-Help` compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais para o módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local, ou se não houver nenhum arquivo XML HelpInfo local, `Update-Help` se preparar para instalar novos arquivos de ajuda.

3. `Update-Help` seleciona o arquivo CAB para o módulo do diretório **SourcePath** . Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

4. `Update-Help` desempacota o arquivo CAB, valida os arquivos de conteúdo da ajuda e salva os arquivos de conteúdo da ajuda no subdiretório específico do idioma do diretório do módulo no computador do usuário.

5. `Update-Help` cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele instalou. Em seguida, ele salva o arquivo XML HelpInfo local no diretório do módulo e conclui a atualização.