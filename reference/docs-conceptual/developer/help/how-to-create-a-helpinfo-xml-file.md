---
title: Como criar um arquivo XML HelpInfo
ms.date: 09/13/2016
ms.openlocfilehash: e395746e51309477bbcbff51b4591de3f73ce0db
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893298"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a>Como criar um arquivo XML HelpInfo

Estes tópicos nesta seção explicam como criar e popular um arquivo de informações de ajuda, normalmente conhecido como "arquivo XML HelpInfo", para o recurso de ajuda atualizável do PowerShell.

## <a name="helpinfo-xml-file-overview"></a>Visão geral do arquivo XML HelpInfo

O arquivo XML HelpInfo é a principal fonte de informações sobre a ajuda atualizável para o módulo. Ele inclui o local dos arquivos de ajuda para os módulos, as culturas de interface do usuário com suporte e os números de versão que a ajuda atualizável usa para determinar se o usuário tem os arquivos de ajuda mais recentes.

Cada módulo tem apenas um arquivo XML HelpInfo, mesmo que o módulo inclua vários arquivos de ajuda para várias culturas de interface do usuário. O autor do módulo cria o arquivo XML HelpInfo e o coloca no local da Internet que é especificado pela chave **HelpInfoUri** no manifesto do módulo. Quando os arquivos de ajuda do módulo são atualizados e carregados, o autor do módulo atualiza o arquivo XML HelpInfo e substitui o arquivo XML HelpInfo original pela nova versão.

É importante que o arquivo XML HelpInfo seja cuidadosamente mantido. Se você carregar novos arquivos, mas esquecer de incrementar os números de versão, a ajuda atualizável não baixará os novos arquivos nos computadores dos usuários. Se você adicionar arquivos de ajuda para uma nova cultura de interface do usuário, mas não atualizar o arquivo XML HelpInfo ou colocá-lo no local correto, a ajuda atualizável não baixará os novos arquivos.

## <a name="in-this-section"></a>Nesta seção

Esta seção inclui os seguintes tópicos.

- [Esquema XML HelpInfo](./helpinfo-xml-schema.md)

- [Arquivo de exemplo XML HelpInfo](./helpinfo-xml-sample-file.md)

- [Como nomear um arquivo XML HelpInfo](./how-to-name-a-helpinfo-xml-file.md)

- [Como definir os números de versão do XML HelpInfo](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a>Consulte Também

[Suporte à ajuda atualizável](./supporting-updatable-help.md)
