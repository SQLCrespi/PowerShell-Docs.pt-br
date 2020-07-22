---
title: Como nomear um arquivo CAB de ajuda atualizável
ms.date: 09/12/2016
ms.openlocfilehash: 42486461d92f1f6fcff452a4539edf5be7a66f22
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892992"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Este tópico explica o formato de nome necessário para os arquivos do gabinete de ajuda atualizável ( `.CAB` ).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Um arquivo de gabinete atualizável ( `.CAB` ) deve ter um nome com o formato a seguir.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Os elementos do nome são os seguintes.

- `<ModuleName>`-O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.
- `<ModuleGUID>`-O valor da chave de **GUID** no manifesto do módulo.
- `<UICulture>`-A cultura da interface do usuário dos arquivos de ajuda no arquivo CAB. Esse valor deve corresponder ao valor de um dos elementos **UICulture** no arquivo XML HelpInfo para o módulo.

Por exemplo, se o nome do módulo for "TestModule", o GUID do módulo é 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 e a cultura da interface do usuário é "en-US", o nome do arquivo CAB seria:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
