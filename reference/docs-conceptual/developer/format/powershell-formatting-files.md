---
title: Arquivos de formatação do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365005"
---
# <a name="windows-powershell-formatting-files"></a>Arquivos de formatação do Windows PowerShell

O Windows PowerShell fornece vários arquivos de formatação (. Format. ps1xml) que estão localizados no diretório de instalação (`$pshome`). Cada um desses arquivos define a exibição padrão para um conjunto específico de objetos .NET. Esses arquivos nunca devem ser alterados. No entanto, você pode usá-los como uma referência para criar seus próprios arquivos de formatação personalizados.

`Certificate.Format.ps1xml` define a exibição de objetos no repositório de certificados, como certificados x. 509 e repositórios de certificados.

`DotNetTypes.Format.ps1xml` define a exibição de objetos .NET diversos, como objetos CultureInfo, FileVersionInfo e EventLogEntry.

`FileSystem.Format.ps1xml` define a exibição de objetos do sistema de arquivos, como objetos de arquivo e diretório.

`Help.Format.ps1xml` define as diferentes exibições usadas pelo cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) , como os modos de exibição detalhado, completo, parâmetros e exemplo.

`PowerShellCore.Format.ps1xml` define a exibição dos objetos gerados pelos cmdlets do Windows PowerShell Core, como os objetos retornados pelos cmdlets [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) e [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) .

`PowerShellTrace.Format.ps1xml` define a exibição de objetos de rastreamento, como os gerados pelo cmdlet [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) .

`Registry.Format.ps1xml` define a exibição de objetos do registro, como objetos de chave e de entrada.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
