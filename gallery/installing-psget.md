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
# <a name="installing-powershellget"></a><span data-ttu-id="fe5df-103">Instalando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="fe5df-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="fe5df-104">PowerShellGet é um módulo nativo nas seguintes versões</span><span class="sxs-lookup"><span data-stu-id="fe5df-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="fe5df-105">[Windows 10](https://www.microsoft.com/windows) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="fe5df-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="fe5df-106">[Windows Server 2016](/windows-server/windows-server) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="fe5df-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="fe5df-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="fe5df-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="fe5df-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="fe5df-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="fe5df-109">Obter a versão mais recente da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5df-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="fe5df-110">Antes de atualizar o **PowerShellGet**, você sempre deve instalar o provedor do **NuGet** mais recente.</span><span class="sxs-lookup"><span data-stu-id="fe5df-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="fe5df-111">Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe5df-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="fe5df-112">Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente</span><span class="sxs-lookup"><span data-stu-id="fe5df-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="fe5df-113">Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="fe5df-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="fe5df-114">Use o `Update-Module` para obter versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="fe5df-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a><span data-ttu-id="fe5df-115">Para sistemas que executam o PowerShell 3 ou o PowerShell 4 que tenham a Versão Prévia do PackageManagement instalada</span><span class="sxs-lookup"><span data-stu-id="fe5df-115">For systems running PowerShell 3 or PowerShell 4, that have installed the PackageManagement Preview</span></span>

1. <span data-ttu-id="fe5df-116">Em uma sessão do PowerShell com privilégios elevados, use `Save-Module` para salvar os módulos em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="fe5df-116">From an elevated PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. <span data-ttu-id="fe5df-117">Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.</span><span class="sxs-lookup"><span data-stu-id="fe5df-117">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="fe5df-118">Exclua o conteúdo das pastas: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="fe5df-118">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="fe5df-119">Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe5df-119">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
