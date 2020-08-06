---
title: Arquivos de formatação do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 54fae12163f8d439c2acc24df17ed140a556cba0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783493"
---
# <a name="windows-powershell-formatting-files"></a>Arquivos de formatação do Windows PowerShell

O Windows PowerShell fornece vários arquivos de formatação (.format.ps1XML) localizados no diretório de instalação ( `$pshome` ). Cada um desses arquivos define a exibição padrão para um conjunto específico de objetos .NET. Esses arquivos nunca devem ser alterados. No entanto, você pode usá-los como uma referência para criar seus próprios arquivos de formatação personalizados.

`Certificate.Format.ps1xml`Define a exibição de objetos no repositório de certificados, como certificados x. 509 e repositórios de certificados.

`DotNetTypes.Format.ps1xml`Define a exibição de objetos .NET diversos, como objetos CultureInfo, FileVersionInfo e EventLogEntry.

`FileSystem.Format.ps1xml`Define a exibição de objetos do sistema de arquivos, como objetos de arquivo e diretório.

`Help.Format.ps1xml`Define as diferentes exibições usadas pelo cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) , como os modos de exibição detalhados, completos, parâmetros e de exemplo.

`PowerShellCore.Format.ps1xml`Define a exibição dos objetos gerados pelos cmdlets do Windows PowerShell Core, como os objetos retornados pelos cmdlets [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) e [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) .

`PowerShellTrace.Format.ps1xml`Define a exibição de objetos de rastreamento, como os gerados pelo cmdlet [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) .

`Registry.Format.ps1xml`Define a exibição de objetos do registro, como objetos de chave e de entrada.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
