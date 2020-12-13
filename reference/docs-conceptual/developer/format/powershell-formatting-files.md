---
ms.date: 09/13/2016
ms.topic: reference
title: Arquivos de formatação do Windows PowerShell
description: Arquivos de formatação do Windows PowerShell
ms.openlocfilehash: 7fa58a3463dc4b2a23d38d161d83387744334d44
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666358"
---
# <a name="windows-powershell-formatting-files"></a>Arquivos de formatação do Windows PowerShell

O Windows PowerShell fornece vários arquivos de formatação (.format.ps1XML) localizados no diretório de instalação ( `$pshome` ). Cada um desses arquivos define a exibição padrão para um conjunto específico de objetos .NET. Esses arquivos nunca devem ser alterados. No entanto, você pode usá-los como uma referência para criar seus próprios arquivos de formatação personalizados.

`Certificate.Format.ps1xml` Define a exibição de objetos no repositório de certificados, como certificados x. 509 e repositórios de certificados.

`DotNetTypes.Format.ps1xml` Define a exibição de objetos .NET diversos, como objetos CultureInfo, FileVersionInfo e EventLogEntry.

`FileSystem.Format.ps1xml` Define a exibição de objetos do sistema de arquivos, como objetos de arquivo e diretório.

`Help.Format.ps1xml` Define as diferentes exibições usadas pelo cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) , como os modos de exibição detalhados, completos, parâmetros e de exemplo.

`PowerShellCore.Format.ps1xml` Define a exibição dos objetos gerados pelos cmdlets do Windows PowerShell Core, como os objetos retornados pelos cmdlets [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) e [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) .

`PowerShellTrace.Format.ps1xml` Define a exibição de objetos de rastreamento, como os gerados pelo cmdlet [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) .

`Registry.Format.ps1xml` Define a exibição de objetos do registro, como objetos de chave e de entrada.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
