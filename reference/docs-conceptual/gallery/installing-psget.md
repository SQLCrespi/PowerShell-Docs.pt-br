---
ms.date: 09/19/2019
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Instalando o PowerShellGet
ms.openlocfilehash: f42eb0df101eb63a5dc267196fa9f666747b8e35
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83727788"
---
# <a name="installing-powershellget"></a><span data-ttu-id="e16d9-103">Instalando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e16d9-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="e16d9-104">PowerShellGet é um módulo nativo nas seguintes versões</span><span class="sxs-lookup"><span data-stu-id="e16d9-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="e16d9-105">[Windows 10](https://www.microsoft.com/windows) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e16d9-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="e16d9-106">[Windows Server 2016](/windows-server/windows-server) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e16d9-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="e16d9-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e16d9-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="e16d9-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="e16d9-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="e16d9-109">Obter a versão mais recente da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e16d9-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="e16d9-110">Antes de atualizar o **PowerShellGet**, você sempre deve instalar o provedor do **NuGet** mais recente.</span><span class="sxs-lookup"><span data-stu-id="e16d9-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="e16d9-111">Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e16d9-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="e16d9-112">Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente</span><span class="sxs-lookup"><span data-stu-id="e16d9-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="e16d9-113">Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="e16d9-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="e16d9-114">Use o `Update-Module` para obter versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e16d9-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="e16d9-115">Para computadores que executam o PowerShell 3.0 ou 4.0</span><span class="sxs-lookup"><span data-stu-id="e16d9-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="e16d9-116">Estas instruções se aplicam a computadores que têm a **Versão prévia de PackageManagement** instalada ou não têm nenhuma versão do **PowerShellGet** instalado.</span><span class="sxs-lookup"><span data-stu-id="e16d9-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="e16d9-117">O cmdlet `Save-Module` é usado em ambos os conjuntos de instruções.</span><span class="sxs-lookup"><span data-stu-id="e16d9-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="e16d9-118">`Save-Module` baixa e salva um módulo e quaisquer dependências de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="e16d9-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="e16d9-119">A versão mais atual do módulo é salva em um caminho especificado no computador local, mas não é instalada.</span><span class="sxs-lookup"><span data-stu-id="e16d9-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="e16d9-120">Para instalar os módulos no PowerShell 3.0 ou no 4.0, copie as pastas salvas do módulo em `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e16d9-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="e16d9-121">Para saber mais, confira [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="e16d9-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="e16d9-122">O PowerShell 3.0 e o 4.0 davam suporte a apenas uma versão de um módulo.</span><span class="sxs-lookup"><span data-stu-id="e16d9-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="e16d9-123">Do PowerShell 5.0 em diante, os módulos são instalados em `<modulename>\<version>`.</span><span class="sxs-lookup"><span data-stu-id="e16d9-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="e16d9-124">Isso permitia a instalação de várias versões lado a lado.</span><span class="sxs-lookup"><span data-stu-id="e16d9-124">This allowed you to install multiple versions side-by-side.</span></span> <span data-ttu-id="e16d9-125">Depois do download do módulo usando `Save-Module`, é necessário copiar os arquivos de `<modulename>\<version>` na pasta `<modulename>` no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="e16d9-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine.</span></span>

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="e16d9-126">Computadores com a versão prévia de PackageManagement instalada</span><span class="sxs-lookup"><span data-stu-id="e16d9-126">Computers with the PackageManagement Preview installed</span></span>

1. <span data-ttu-id="e16d9-127">Em uma sessão do PowerShell, use `Save-Module` para salvar os módulos em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="e16d9-127">From a PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e16d9-128">Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.</span><span class="sxs-lookup"><span data-stu-id="e16d9-128">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="e16d9-129">Exclua o conteúdo das pastas: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="e16d9-129">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="e16d9-130">Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e16d9-130">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="e16d9-131">Computadores sem PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e16d9-131">Computers without PowerShellGet</span></span>

<span data-ttu-id="e16d9-132">Para computadores sem qualquer versão do **PowerShellGet** instalada, é necessário ter um computador com o **PowerShellGet** instalado para baixar os módulos.</span><span class="sxs-lookup"><span data-stu-id="e16d9-132">For computer's without any version of **PowerShellGet** installed, a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="e16d9-133">No computador com o **PowerShellGet** instalado, use o `Save-Module` para baixar a versão atual do **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="e16d9-133">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="e16d9-134">Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="e16d9-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="e16d9-135">Cada pasta contém uma subpasta com um número de versão.</span><span class="sxs-lookup"><span data-stu-id="e16d9-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e16d9-136">Copie as pastas **PowerShellGet** e **PackageManagement** para o computador que não tem o **PowerShellGet** instalado.</span><span class="sxs-lookup"><span data-stu-id="e16d9-136">Copy the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed.</span></span>

   <span data-ttu-id="e16d9-137">O diretório de destino será: `$env:ProgramFiles\WindowsPowerShell\Modules`</span><span class="sxs-lookup"><span data-stu-id="e16d9-137">The destination directory is: `$env:ProgramFiles\WindowsPowerShell\Modules`</span></span>
