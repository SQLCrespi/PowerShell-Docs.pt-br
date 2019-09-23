---
ms.date: 06/12/2017
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Instalando o PowerShellGet
ms.openlocfilehash: a0ef46a9ee4bbf668a58067256d098967bde48c5
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143602"
---
# <a name="installing-powershellget"></a>Instalando o PowerShellGet

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet é um módulo nativo nas seguintes versões

- [Windows 10](https://www.microsoft.com/windows) ou mais recente
- [Windows Server 2016](/windows-server/windows-server) ou mais recente
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a>Obter a versão mais recente da Galeria do PowerShell

Antes de atualizar o **PowerShellGet**, você sempre deve instalar o provedor do **NuGet** mais recente. Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente

Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

Use o `Update-Module` para obter versões mais recentes.

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a>Para sistemas que executam o PowerShell 3 ou o PowerShell 4 que tenham a Versão Prévia do PackageManagement instalada

1. Em uma sessão do PowerShell com privilégios elevados, use `Save-Module` para salvar os módulos em um diretório local.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.
1. Exclua o conteúdo das pastas: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.
1. Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
