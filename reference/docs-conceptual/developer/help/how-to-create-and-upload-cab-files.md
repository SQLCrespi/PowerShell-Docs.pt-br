---
title: Como criar e carregar arquivos CAB
ms.date: 09/13/2016
ms.openlocfilehash: 247ed70ba206d70be01155653efbe887bf603f53
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893026"
---
# <a name="how-to-create-and-upload-cab-files"></a>Como criar e carregar arquivos CAB

Este tópico explica como criar arquivos CAB de ajuda atualizáveis e carregá-los no local onde os cmdlets de ajuda atualizáveis podem encontrá-los.

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a>Como criar e carregar arquivos CAB de ajuda atualizáveis

Você pode usar o recurso de ajuda atualizável para fornecer arquivos de ajuda novos ou atualizados para um módulo em vários idiomas e culturas. Um pacote de ajuda atualizável para um módulo consiste em um arquivo XML HelpInfo e um ou mais arquivos cabinet ( `.CAB` ). Cada arquivo CAB contém arquivos de ajuda para o módulo em uma cultura de interface do usuário. Use o procedimento a seguir para criar arquivos CAB para obter ajuda atualizável.

1. Organize os arquivos de ajuda para o módulo por cultura de interface do usuário. Cada arquivo CAB de ajuda atualizável contém os arquivos de ajuda para um módulo em uma cultura de interface do usuário. Você pode entregar vários arquivos CAB de ajuda para o módulo, cada um para uma cultura de interface do usuário diferente.

1. Verifique se os arquivos de ajuda incluem apenas os tipos de arquivo permitidos para a ajuda atualizável e validá-los em um esquema de arquivo de ajuda. Se o `Update-Help` cmdlet encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do CAB. Para obter uma lista de tipos de arquivo permitidos, consulte [tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável](./file-types-permitted-in-an-updatable-help-cab-file.md).

1. Assine digitalmente os arquivos da ajuda. As assinaturas digitais não são necessárias, mas são uma prática recomendada.

1. Inclua todos os arquivos de ajuda para o módulo na cultura da interface do usuário, não apenas arquivos que são novos ou foram alterados. Se o arquivo CAB estiver incompleto, os usuários que baixarem os arquivos da ajuda pela primeira vez ou não baixarem todas as atualizações, não terão todos os arquivos de ajuda do módulo.

1. Use um utilitário que cria arquivos de gabinete, como `MakeCab.exe` . O PowerShell não inclui cmdlets que criam arquivos CAB.

1. Nomeie os arquivos CAB. Para obter mais informações, consulte [como nomear um arquivo CAB de ajuda atualizável](./how-to-name-an-updatable-help-cab-file.md).

1. Carregue os arquivos CAB para o módulo no local especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo para o módulo. Em seguida, carregue o arquivo XML HelpInfo no local especificado pela chave **HelpInfoUri** do manifesto do módulo. O **HelpContentUri** e o **HelpInfoUri** podem apontar para o mesmo local.

> [!CAUTION]
> O valor da chave **HelpInfoUri** e do elemento **HelpContentUri** deve começar com `http` ou `https` . O valor deve indicar um local de Internet e não deve incluir um nome de arquivo.
