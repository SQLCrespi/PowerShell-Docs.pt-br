---
ms.date: 09/12/2016
ms.topic: reference
title: Como nomear um arquivo XML HelpInfo
description: Como nomear um arquivo XML HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659040"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>Como nomear um arquivo XML HelpInfo

Este tópico explica o formato de nome necessário para os arquivos de informações de ajuda atualizáveis, normalmente conhecidos como arquivos XML HelpInfo.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Como nomear um arquivo XML HelpInfo

Um arquivo XML HelpInfo deve ter um nome com o formato a seguir.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Os elementos do nome são os seguintes.

- `<ModuleName>` -O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.

- `<ModuleGUID>` -O valor da chave de **GUID** no manifesto do módulo.

Por exemplo, se o nome do módulo for "TestModule" e o GUID do módulo for 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, o nome do arquivo XML HelpInfo para o módulo seria:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
