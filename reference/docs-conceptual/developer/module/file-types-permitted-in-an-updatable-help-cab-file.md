---
title: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 3562804157ebdfca561445a8671d726b55cc4efd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367255"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável

Este tópico lista e descreve os requisitos de conteúdo para arquivos CAB de ajuda atualizáveis.

## <a name="updatable-help-cab-file-requirements"></a>Requisitos de arquivo CAB de ajuda atualizável

O conteúdo do arquivo CAB não compactado é limitado a 1 GB por padrão. Para ignorar esse limite, os usuários precisam usar o parâmetro **Force** dos cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .

Para garantir a segurança dos arquivos de ajuda que são baixados da Internet, um arquivo CAB de ajuda atualizável pode incluir apenas os tipos de arquivo listados abaixo. O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) valida todos os arquivos em relação aos esquemas de tópicos da ajuda. Se o cmdlet `Update-Help` encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do CAB no computador do usuário.

- Tópicos de ajuda baseados em XML para cmdlets.

- Tópicos de ajuda baseados em XML para scripts e funções.

- Tópicos de ajuda baseados em XML para provedores do Windows PowerShell.

- Tópicos de ajuda baseados em texto, como sobre tópicos.

O [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifica o conteúdo do CAB ao descompactar o CAB. Se `Update-Help` localizar tipos de arquivo sem conformidade em um arquivo CAB de ajuda atualizável, ele gerará um erro de encerramento e interromperá a operação. Ele não instala arquivos de ajuda do CAB, mesmo os de tipos de arquivo em conformidade.