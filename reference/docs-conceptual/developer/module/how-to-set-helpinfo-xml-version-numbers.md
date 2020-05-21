---
title: Como definir números de versão do HelpInfo XML | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: 864372bfb0f43922f6066ff3db19956a7942db49
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560518"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a>Como definir os números de versão do XML HelpInfo

Este tópico explica como definir e aumentar os números de versão em um arquivo de informações de ajuda atualizável, normalmente conhecido como "arquivo XML HelpInfo".

## <a name="how-to-set-helpinfo-xml-version-numbers"></a>Como definir os números de versão do XML HelpInfo

Os números de versão em um arquivo XML HelpInfo são críticos para a operação de ajuda atualizável.
Os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) baixam novos arquivos de ajuda somente quando o número de versão de uma cultura de interface do usuário no arquivo XML HelpInfo remoto é maior que o número de versão para essa cultura de interface do usuário no XML HelpInfo local ou não há nenhum arquivo XML HelpInfo local.

O arquivo XML HelpInfo usa o número de versão de 4 partes que é definido na classe **System. Version** da estrutura de Microsoft .net. O formato é `N1.N2.N3.N4`. Os autores de módulo podem usar qualquer esquema de numeração de versão que seja permitido pela classe **System. Version** . A ajuda atualizável requer apenas que o número de versão de uma cultura de interface do usuário aumente quando uma nova versão do arquivo CAB para a cultura da interface do usuário for carregada no local especificado pelo elemento **HelpContentURI** no arquivo XML HelpInfo.

O exemplo a seguir mostra os elementos do arquivo XML HelpInfo para a cultura da interface do usuário do alemão (de-DE) quando a versão é 2.15.0.10.

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

O número de versão de uma cultura de interface do usuário reflete a versão do arquivo CAB para essa cultura de interface do usuário. O número de versão se aplica ao arquivo CAB inteiro. Não é possível definir números de versão diferentes para arquivos diferentes no arquivo CAB. O número de versão de cada cultura de interface do usuário é avaliado de forma independente e não precisa estar relacionado aos números de versão para outras culturas de interface do usuário às quais o módulo dá suporte.
