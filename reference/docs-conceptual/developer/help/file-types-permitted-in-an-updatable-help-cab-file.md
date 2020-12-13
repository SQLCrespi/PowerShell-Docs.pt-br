---
ms.date: 03/22/2012
ms.topic: reference
title: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável
description: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável
ms.openlocfilehash: bb69b8b89a9a3a5c8c00059ec404a4d41a5db9a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654744"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável

O conteúdo do arquivo CAB não compactado é limitado a 1 GB por padrão. Para ignorar esse limite, os usuários precisam usar o parâmetro **Force** dos cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .

Para garantir a segurança dos arquivos de ajuda que são baixados da Internet, um arquivo CAB de ajuda atualizável pode incluir apenas os tipos de arquivo listados abaixo. O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) valida todos os arquivos em relação aos esquemas de tópicos da ajuda. Se o `Update-Help` cmdlet encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do cab no computador do usuário.

- Tópicos de ajuda baseados em XML para cmdlets.
- Tópicos de ajuda baseados em XML para scripts e funções.
- Tópicos de ajuda baseados em XML para provedores do PowerShell.
- Tópicos de ajuda baseados em texto, como sobre tópicos.

O [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifica o conteúdo do CAB ao descompactar o CAB. Se o `Update-Help` encontrar tipos de arquivo sem conformidade em um arquivo CAB de ajuda atualizável, ele gerará um erro de encerramento e interromperá a operação. Ele não instala arquivos de ajuda do CAB, mesmo os de tipos de arquivo em conformidade.
