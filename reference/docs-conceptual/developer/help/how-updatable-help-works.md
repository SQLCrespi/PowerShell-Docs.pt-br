---
title: Como a ajuda atualizável funciona
ms.date: 09/13/2016
ms.openlocfilehash: 4849ce81e31171c6822a9078a77ebb45729185a3
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893281"
---
# <a name="how-updatable-help-works"></a>Como a ajuda atualizável funciona

Este tópico explica como a ajuda atualizável processa o arquivo XML HelpInfo e os arquivos CAB para cada módulo e instala a ajuda atualizada para os usuários.

## <a name="the-update-help-process"></a>O processo de atualização-ajuda

A lista a seguir descreve as ações do cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) quando um usuário executa um comando para atualizar os arquivos de ajuda para um módulo em uma cultura de interface do usuário específica.

1. `Update-Help`Obtém o arquivo XML HelpInfo remoto do local especificado pelo valor da chave **HelpInfoURI** no manifesto do módulo e valida o arquivo em relação ao esquema. (Para exibir o esquema, consulte [HELPINFO XML Schema](./helpinfo-xml-schema.md).) Em seguida, `Update-Help` procura um arquivo XML HelpInfo local para o módulo no diretório do módulo no computador do usuário.

1. `Update-Help`compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais do módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local ou se não houver nenhum arquivo XML HelpInfo local para o módulo, o `Update-Help` se prepara para baixar novos arquivos de ajuda.

1. `Update-Help`seleciona o arquivo CAB para o módulo a partir do local especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo remoto. Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

1. `Update-Help`Baixa o arquivo CAB, descompacta-o, valida os arquivos de conteúdo da ajuda e salva os arquivos de conteúdo da ajuda no subdiretório específico do idioma do diretório do módulo no computador do usuário.

1. `Update-Help`Cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele instalou.
   Em seguida, ele salva o arquivo XML HelpInfo local no diretório do módulo e conclui a atualização.

## <a name="the-save-help-process"></a>O processo de salvar-ajuda

A lista a seguir descreve as ações dos cmdlets [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) e [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) quando um usuário executa comandos para atualizar os arquivos de ajuda em um compartilhamento de arquivos e, em seguida, usa esses arquivos para atualizar os arquivos de ajuda no computador do usuário.

O `Save-Help` cmdlet executa as seguintes ações em resposta a um comando para salvar os arquivos de ajuda de um módulo em um compartilhamento de arquivos que é especificado pelo parâmetro **DestinationPath** .

1. `Save-Help`Obtém o arquivo XML HelpInfo remoto do local especificado pelo valor da chave **HelpInfoURI** no manifesto do módulo e valida o arquivo em relação ao esquema. (Para exibir o esquema, consulte [HELPINFO XML Schema](./helpinfo-xml-schema.md).) Em seguida, `Save-Help` procura um arquivo XML HelpInfo local no diretório que é especificado pelo parâmetro **DestinationPath** no `Save-Help` comando.

1. `Save-Help`compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais do módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local, ou se não houver nenhum arquivo XML HelpInfo local para o módulo no diretório **DestinationPath** , o `Save-Help` se prepara para baixar novos arquivos de ajuda.

1. `Save-Help`seleciona o arquivo CAB para o módulo a partir do local especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo remoto. Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

1. `Save-Help`Baixa o arquivo CAB e o salva no diretório **DestinationPath** (Ele não cria subdiretórios específicos do idioma.)

1. `Save-Help`Cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele salvou.
   Em seguida, ele salva o arquivo XML HelpInfo local no diretório **DestinationPath** e conclui a atualização.

   O `Update-Help` cmdlet executa as seguintes ações em resposta a um comando para atualizar os arquivos de ajuda no computador de um usuário a partir dos arquivos em um compartilhamento de arquivo especificado pelo parâmetro **SourcePath** .

1. `Update-Help`Obtém o arquivo XML HelpInfo remoto do diretório **SourcePath** . Em seguida, ele procura um arquivo XML HelpInfo local no diretório do módulo no computador do usuário.

1. `Update-Help`compara o número de versão dos arquivos de ajuda para a cultura da interface do usuário especificada nos arquivos XML HelpInfo remotos e locais do módulo. Se o número de versão no arquivo remoto for maior que o número de versão no arquivo local ou se não houver nenhum arquivo XML HelpInfo local, o `Update-Help` se prepara para instalar novos arquivos de ajuda.

1. `Update-Help`seleciona o arquivo CAB para o módulo do diretório **SourcePath** . Ele usa o nome do módulo, o GUID do módulo e a cultura da interface do usuário para identificar o arquivo CAB.

1. `Update-Help`descompacta o arquivo CAB, valida os arquivos de conteúdo da ajuda e salva os arquivos de conteúdo da ajuda no subdiretório específico do idioma do diretório do módulo no computador do usuário.

1. `Update-Help`Cria um arquivo XML HelpInfo local copiando o arquivo XML HelpInfo remoto. Ele edita o arquivo XML HelpInfo local para que ele inclua elementos somente para o arquivo CAB que ele instalou.
   Em seguida, ele salva o arquivo XML HelpInfo local no diretório do módulo e conclui a atualização.
