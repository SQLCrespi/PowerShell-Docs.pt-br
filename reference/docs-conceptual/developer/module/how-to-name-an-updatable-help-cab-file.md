---
title: Como nomear um arquivo CAB de ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: a253f98d213f797a659affb1560907bb99a045d3
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560552"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Este tópico explica o formato de nome necessário para o gabinete de ajuda atualizável (. Arquivos CAB).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Um gabinete atualizável (. CAB) deve ter um nome com o formato a seguir.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Os elementos do nome são os seguintes.

ModuleName o valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.

ModuleGUID o valor da chave **GUID** no manifesto do módulo.

UICulture a cultura da interface do usuário dos arquivos de ajuda no arquivo CAB. Esse valor deve corresponder ao valor de um dos elementos **UICulture** no arquivo XML HelpInfo para o módulo.

Por exemplo, se o nome do módulo for "TestModule", o GUID do módulo é 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 e a cultura da interface do usuário é "en-US", o nome do arquivo CAB seria:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
