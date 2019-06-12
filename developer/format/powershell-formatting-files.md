---
title: Arquivos de formatação de PowerShell de Windows | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: 4ec9e10647b752cc62b1eabb897ada3dc03c93eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66830257"
---
# <a name="windows-powershell-formatting-files"></a>Arquivos de formatação do Windows PowerShell

Windows PowerShell fornece vários arquivos de formatação (. ps1xml) que estão localizados no diretório de instalação (`$pshome`). Cada um desses arquivos define a exibição padrão para um conjunto específico de objetos .NET. Esses arquivos nunca devem ser alterados. No entanto, você pode usá-los como uma referência para a criação de seus próprios arquivos de formatação personalizados.

`Certificate.Format.ps1xml` Define a exibição de objetos no repositório de certificados, como certificados x. 509 e repositórios de certificados.

`DotNetTypes.Format.ps1xml` Define a exibição de diversos objetos .NET, como objetos CultureInfo, FileVersionInfo e EventLogEntry.

`FileSystem.Format.ps1xml` Define a exibição de objetos do sistema de arquivos como objetos de diretório e arquivo.

`Help.Format.ps1xml` Define os diferentes modos de exibição usados pelas [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet, como as exibições detalhadas, de exemplo, parâmetros e completo.

`PowerShellCore.Format.ps1xml` Define a exibição dos objetos gerados pelos cmdlets do Windows PowerShell core, como os objetos retornados pela [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) e [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) cmdlets.

`PowerShellTrace.Format.ps1xml` Define a exibição de objetos de rastreamento, como aqueles gerados pela [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet.

`Registry.Format.ps1xml` Define a exibição de objetos do registro, como objetos de chave e de entrada.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
