---
title: Como nomear um arquivo XML HelpInfo
ms.date: 09/12/2016
ms.openlocfilehash: 9505a7f66852a569d25ac0c1be86e68f870a7930
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892924"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>Como nomear um arquivo XML HelpInfo

Este tópico explica o formato de nome necessário para os arquivos de informações de ajuda atualizáveis, normalmente conhecidos como arquivos XML HelpInfo.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Como nomear um arquivo XML HelpInfo

Um arquivo XML HelpInfo deve ter um nome com o formato a seguir.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Os elementos do nome são os seguintes.

- `<ModuleName>`-O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.

- `<ModuleGUID>`-O valor da chave de **GUID** no manifesto do módulo.

Por exemplo, se o nome do módulo for "TestModule" e o GUID do módulo for 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, o nome do arquivo XML HelpInfo para o módulo seria:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
