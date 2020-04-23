---
ms.date: 09/19/2019
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Instalando o PowerShellGet
ms.openlocfilehash: 69dc851c54089b47fb19e5b32990d579d26effb9
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71328197"
---
# <a name="installing-powershellget"></a><span data-ttu-id="01df2-103">Instalando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="01df2-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="01df2-104">PowerShellGet é um módulo nativo nas seguintes versões</span><span class="sxs-lookup"><span data-stu-id="01df2-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="01df2-105">[Windows 10](https://www.microsoft.com/windows) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="01df2-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="01df2-106">[Windows Server 2016](/windows-server/windows-server) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="01df2-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="01df2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="01df2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="01df2-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="01df2-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="01df2-109">Obter a versão mais recente da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="01df2-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="01df2-110">Antes de atualizar o **PowerShellGet**, você sempre deve instalar o provedor do **NuGet** mais recente.</span><span class="sxs-lookup"><span data-stu-id="01df2-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="01df2-111">Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="01df2-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="01df2-112">Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente</span><span class="sxs-lookup"><span data-stu-id="01df2-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="01df2-113">Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="01df2-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="01df2-114">Use o `Update-Module` para obter versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="01df2-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="01df2-115">Para computadores que executam o PowerShell 3.0 ou 4.0</span><span class="sxs-lookup"><span data-stu-id="01df2-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="01df2-116">Estas instruções se aplicam a computadores que têm a **Versão prévia de PackageManagement** instalada ou não têm nenhuma versão do **PowerShellGet** instalado.</span><span class="sxs-lookup"><span data-stu-id="01df2-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="01df2-117">O cmdlet `Save-Module` é usado em ambos os conjuntos de instruções.</span><span class="sxs-lookup"><span data-stu-id="01df2-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="01df2-118">`Save-Module` baixa e salva um módulo e quaisquer dependências de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="01df2-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="01df2-119">A versão mais atual do módulo é salva em um caminho especificado no computador local, mas não é instalada.</span><span class="sxs-lookup"><span data-stu-id="01df2-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="01df2-120">Para saber mais, confira [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="01df2-120">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="01df2-121">Computadores com a versão prévia de PackageManagement instalada</span><span class="sxs-lookup"><span data-stu-id="01df2-121">Computers with the PackageManagement Preview installed</span></span>

1. <span data-ttu-id="01df2-122">Em uma sessão do PowerShell, use `Save-Module` para salvar os módulos em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="01df2-122">From a PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="01df2-123">Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.</span><span class="sxs-lookup"><span data-stu-id="01df2-123">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="01df2-124">Exclua o conteúdo das pastas: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="01df2-124">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="01df2-125">Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="01df2-125">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="01df2-126">Computadores sem PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="01df2-126">Computers without PowerShellGet</span></span>

<span data-ttu-id="01df2-127">Para computadores sem qualquer versão do **PowerShellGet** instalada, é necessário ter um computador com o **PowerShellGet** instalado para baixar os módulos.</span><span class="sxs-lookup"><span data-stu-id="01df2-127">For computer's without any version of **PowerShellGet** installed, a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="01df2-128">No computador com o **PowerShellGet** instalado, use o `Save-Module` para baixar a versão atual do **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="01df2-128">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="01df2-129">Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="01df2-129">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="01df2-130">Cada pasta contém uma subpasta com um número de versão.</span><span class="sxs-lookup"><span data-stu-id="01df2-130">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="01df2-131">Copie as pastas **PowerShellGet** e **PackageManagement** para o computador que não tem o **PowerShellGet** instalado.</span><span class="sxs-lookup"><span data-stu-id="01df2-131">Copy the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed.</span></span>

   <span data-ttu-id="01df2-132">O diretório de destino será: `$env:ProgramFiles\WindowsPowerShell\Modules`</span><span class="sxs-lookup"><span data-stu-id="01df2-132">The destination directory is: `$env:ProgramFiles\WindowsPowerShell\Modules`</span></span>
