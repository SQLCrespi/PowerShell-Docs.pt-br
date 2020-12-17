---
title: Instalar o PowerShell Core no Arm
description: Instalar o PowerShell Core em sistemas baseados em Arm
ms.date: 11/11/2020
ms.openlocfilehash: 85a2cccb18341ffee8c81430bc8490e5d3e97b41
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892065"
---
# <a name="powershell-core-on-arm"></a>PowerShell Core no Arm

O suporte do PowerShell no Arm é baseado nas **Políticas de ciclo de vida de sistema operacional com suporte do .NET Core**.

O PowerShell 7.1 baseia-se na [Política de ciclo de vida de sistema operacional com suporte do .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) e dá suporte às seguintes plataformas:

|         Sistema operacional          |          Versão           | Arquiteturas |          Ciclo de vida           |
| ------------------- | -------------------------- | ------------- | ---------------------------- |
| Windows Nano Server | Versão 1803+              | Arm32         | [Windows][Windows-lifecycle] |
| Alpine Linux        | 3.10+                      | Arm64         | [Alpine][Alpine-lifecycle]   |
| Debian              | 9 e posterior                         | Arm32, Arm64  | [Debian][Debian-lifecycle]   |
| Ubuntu              | 20.10, 20.04, 18.04, 16.04 | Arm32, Arm64  | [Ubuntu][Ubuntu-lifecycle]   |

O PowerShell 7.0 baseia-se na [Política de ciclo de vida de sistema operacional com suporte do .NET Core 5.0](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) e dá suporte às seguintes plataformas:

|        Sistema operacional         |          Versão           | Arquiteturas |          Ciclo de vida           |
| ----------------- | -------------------------- | ------------- | ---------------------------- |
| Cliente do Windows 10 | Versão 1607+              | Arm64         | [Windows][Windows-lifecycle] |
| Alpine Linux      | 3.11+                      | Arm64         | [Alpine][Alpine-lifecycle]   |
| Debian            | 9 e posterior                         | Arm32, Arm64  | [Debian][Debian-lifecycle]   |
| Ubuntu            | 20.10, 20.04, 18.04, 16.04 | Arm32, Arm64  | [Ubuntu][Ubuntu-lifecycle]   |

[Windows-lifecycle]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[Alpine-lifecycle]: https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases
[Debian-lifecycle]: https://wiki.debian.org/DebianReleases
[Ubuntu-lifecycle]: https://wiki.ubuntu.com/Releases

Para obter instruções de instalação, confira os seguintes artigos:

- [Windows 10 no Arm](installing-powershell-core-on-windows.md#installing-the-zip-package)
- [Windows 10 IoT Enterprise](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-enterprise)
- [Windows 10 IoT Core](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-core)
- [Raspbian](installing-powershell-core-on-linux.md#raspbian)
