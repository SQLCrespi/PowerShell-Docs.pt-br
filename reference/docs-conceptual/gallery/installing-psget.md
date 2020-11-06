---
ms.date: 09/19/2019
title: Instalando o PowerShellGet
description: Este artigo explica como instalar o módulo do PowerShellGet em várias versões do PowerShell.
ms.openlocfilehash: 06ec331446849784bb8464912fbce0e5a940823f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662153"
---
# <a name="installing-powershellget"></a>Instalando o PowerShellGet

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet é um módulo nativo nas seguintes versões

- [Windows 10](https://www.microsoft.com/windows) ou mais recente
- [Windows Server 2016](/windows-server/windows-server) ou mais recente
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a>Obter a versão mais recente da Galeria do PowerShell

Antes de atualizar o **PowerShellGet** , você sempre deve instalar o provedor do **NuGet** mais recente. Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente

Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.

```powershell
Install-Module -Name PowerShellGet -Force
```

Use o `Update-Module` para obter versões mais recentes.

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>Para computadores que executam o PowerShell 3.0 ou 4.0

Estas instruções se aplicam a computadores que têm a **Versão prévia de PackageManagement** instalada ou não têm nenhuma versão do **PowerShellGet** instalado.

O cmdlet `Save-Module` é usado em ambos os conjuntos de instruções. `Save-Module` baixa e salva um módulo e quaisquer dependências de um repositório registrado. A versão mais atual do módulo é salva em um caminho especificado no computador local, mas não é instalada. Para instalar os módulos no PowerShell 3.0 ou no 4.0, copie as pastas salvas do módulo em `$env:ProgramFiles\WindowsPowerShell\Modules`.

Para saber mais, confira [Save-Module](/powershell/module/PowershellGet/Save-Module).

> [!NOTE]
> O PowerShell 3.0 e o 4.0 davam suporte a apenas uma versão de um módulo. Do PowerShell 5.0 em diante, os módulos são instalados em `<modulename>\<version>`. Isso permite instalar várias versões lado a lado. Depois do download do módulo usando `Save-Module`, é necessário copiar os arquivos de `<modulename>\<version>` na pasta `<modulename>` no computador de destino, conforme mostrado nas instruções abaixo.

#### <a name="preparatory-step-on-computers-running-powershell-30"></a>Etapa preparatória em computadores com o PowerShell 3.0

As instruções nas seções a seguir instalam os módulos no diretório `$env:ProgramFiles\WindowsPowerShell\Modules`.
No PowerShell 3.0, esse diretório não está listado em `$env:PSModulePath` por padrão. Portanto, você precisará adicioná-lo para que os módulos sejam carregados automaticamente.

Abra uma sessão do PowerShell com privilégios elevados e execute o seguinte comando (que entrará em vigor em sessões futuras):

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>Computadores com a versão prévia de PackageManagement instalada

> [!NOTE]
> A versão prévia do PackageManagement era um componente baixável que disponibilizava o PowerShellGet para as versões 3 e 4 do PowerShell. Porém, ela não está mais disponível.
> Para testar se ela foi instalada em um computador específico, execute `Get-Module -ListAvailable PowerShellGet`.

1. Em uma sessão do PowerShell, use `Save-Module` para baixar a versão atual do **PowerShellGet**. Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**. Cada pasta contém uma subpasta com um número de versão.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.

1. Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a>Computadores sem PowerShellGet

Para computadores sem qualquer versão do **PowerShellGet** instalada (teste com `Get-Module -ListAvailable PowerShellGet`), é necessário ter um computador com o **PowerShellGet** instalado para baixar os módulos.

1. No computador com o **PowerShellGet** instalado, use o `Save-Module` para baixar a versão atual do **PowerShellGet**. Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**. Cada pasta contém uma subpasta com um número de versão.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Copie a subpasta `<version>` nas pastas **PowerShellGet** e **PackageManagement** para o computador que não tem o **PowerShellGet** instalado, para as pastas `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`, respectivamente, o que exige uma sessão com privilégios.

1. Por exemplo, se for possível acessar a pasta de download no outro computador (`ws1`) no computador de destino por meio de um caminho UNC (`\\ws1\C$\LocalFolder`), abra um console do PowerShell com permissões elevadas e execute o seguinte comando:

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
