---
title: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável
ms.date: 03/22/2012
ms.openlocfilehash: 2a8e97edf8daaed915ea1a3e04565d996a2e15fd
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893128"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável

O conteúdo do arquivo CAB não compactado é limitado a 1 GB por padrão. Para ignorar esse limite, os usuários precisam usar o parâmetro **Force** dos cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .

Para garantir a segurança dos arquivos de ajuda que são baixados da Internet, um arquivo CAB de ajuda atualizável pode incluir apenas os tipos de arquivo listados abaixo. O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) valida todos os arquivos em relação aos esquemas de tópicos da ajuda. Se o `Update-Help` cmdlet encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do cab no computador do usuário.

- Tópicos de ajuda baseados em XML para cmdlets.
- Tópicos de ajuda baseados em XML para scripts e funções.
- Tópicos de ajuda baseados em XML para provedores do PowerShell.
- Tópicos de ajuda baseados em texto, como sobre tópicos.

O [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifica o conteúdo do CAB ao descompactar o CAB. Se o `Update-Help` encontrar tipos de arquivo sem conformidade em um arquivo CAB de ajuda atualizável, ele gerará um erro de encerramento e interromperá a operação. Ele não instala arquivos de ajuda do CAB, mesmo os de tipos de arquivo em conformidade.
