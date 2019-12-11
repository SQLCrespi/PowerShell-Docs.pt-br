---
ms.date: 09/19/2019
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Instalando o PowerShellGet
ms.openlocfilehash: 69dc851c54089b47fb19e5b32990d579d26effb9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328197"
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

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>Para computadores que executam o PowerShell 3.0 ou 4.0

Estas instruções se aplicam a computadores que têm a **Versão prévia de PackageManagement** instalada ou não têm nenhuma versão do **PowerShellGet** instalado.

O cmdlet `Save-Module` é usado em ambos os conjuntos de instruções. `Save-Module` baixa e salva um módulo e quaisquer dependências de um repositório registrado. A versão mais atual do módulo é salva em um caminho especificado no computador local, mas não é instalada. Para saber mais, confira [Save-Module](/powershell/module/PowershellGet/Save-Module).

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>Computadores com a versão prévia de PackageManagement instalada

1. Em uma sessão do PowerShell, use `Save-Module` para salvar os módulos em um diretório local.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.
1. Exclua o conteúdo das pastas: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.
1. Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a>Computadores sem PowerShellGet

Para computadores sem qualquer versão do **PowerShellGet** instalada, é necessário ter um computador com o **PowerShellGet** instalado para baixar os módulos.

1. No computador com o **PowerShellGet** instalado, use o `Save-Module` para baixar a versão atual do **PowerShellGet**. Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**. Cada pasta contém uma subpasta com um número de versão.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Copie as pastas **PowerShellGet** e **PackageManagement** para o computador que não tem o **PowerShellGet** instalado.

   O diretório de destino será: `$env:ProgramFiles\WindowsPowerShell\Modules`
