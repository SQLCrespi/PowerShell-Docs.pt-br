---
ms.date: 09/19/2019
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Instalando o PowerShellGet
ms.openlocfilehash: 4a10699be9ff2b64e5848c6749bdd3dedf55e3c7
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162504"
---
# <a name="installing-powershellget"></a><span data-ttu-id="e90d1-103">Instalando o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e90d1-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="e90d1-104">PowerShellGet é um módulo nativo nas seguintes versões</span><span class="sxs-lookup"><span data-stu-id="e90d1-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="e90d1-105">[Windows 10](https://www.microsoft.com/windows) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e90d1-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="e90d1-106">[Windows Server 2016](/windows-server/windows-server) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e90d1-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="e90d1-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) ou mais recente</span><span class="sxs-lookup"><span data-stu-id="e90d1-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="e90d1-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="e90d1-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="e90d1-109">Obter a versão mais recente da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e90d1-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="e90d1-110">Antes de atualizar o **PowerShellGet**, você sempre deve instalar o provedor do **NuGet** mais recente.</span><span class="sxs-lookup"><span data-stu-id="e90d1-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="e90d1-111">Em uma sessão do PowerShell com privilégios elevados, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e90d1-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="e90d1-112">Para sistemas com o PowerShell 5.0 (ou mais recente), você pode instalar o PowerShellGet mais recente</span><span class="sxs-lookup"><span data-stu-id="e90d1-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="e90d1-113">Para instalar o PowerShellGet no Windows 10, no Windows Server 2016, em qualquer sistema com o WMF 5.0 ou 5.1 instalado ou em qualquer sistema com o PowerShell 6, execute os comandos a seguir em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="e90d1-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
```

<span data-ttu-id="e90d1-114">Use o `Update-Module` para obter versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e90d1-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="e90d1-115">Para computadores que executam o PowerShell 3.0 ou 4.0</span><span class="sxs-lookup"><span data-stu-id="e90d1-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="e90d1-116">Estas instruções se aplicam a computadores que têm a **Versão prévia de PackageManagement** instalada ou não têm nenhuma versão do **PowerShellGet** instalado.</span><span class="sxs-lookup"><span data-stu-id="e90d1-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="e90d1-117">O cmdlet `Save-Module` é usado em ambos os conjuntos de instruções.</span><span class="sxs-lookup"><span data-stu-id="e90d1-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="e90d1-118">`Save-Module` baixa e salva um módulo e quaisquer dependências de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="e90d1-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="e90d1-119">A versão mais atual do módulo é salva em um caminho especificado no computador local, mas não é instalada.</span><span class="sxs-lookup"><span data-stu-id="e90d1-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="e90d1-120">Para instalar os módulos no PowerShell 3.0 ou no 4.0, copie as pastas salvas do módulo em `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e90d1-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="e90d1-121">Para saber mais, confira [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="e90d1-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="e90d1-122">O PowerShell 3.0 e o 4.0 davam suporte a apenas uma versão de um módulo.</span><span class="sxs-lookup"><span data-stu-id="e90d1-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="e90d1-123">Do PowerShell 5.0 em diante, os módulos são instalados em `<modulename>\<version>`.</span><span class="sxs-lookup"><span data-stu-id="e90d1-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="e90d1-124">Isso permite instalar várias versões lado a lado.</span><span class="sxs-lookup"><span data-stu-id="e90d1-124">This allows you to install multiple versions side-by-side.</span></span> <span data-ttu-id="e90d1-125">Depois do download do módulo usando `Save-Module`, é necessário copiar os arquivos de `<modulename>\<version>` na pasta `<modulename>` no computador de destino, conforme mostrado nas instruções abaixo.</span><span class="sxs-lookup"><span data-stu-id="e90d1-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine, as shown in the instructions below.</span></span>

#### <a name="preparatory-step-on-computers-running-powershell-30"></a><span data-ttu-id="e90d1-126">Etapa preparatória em computadores com o PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="e90d1-126">Preparatory Step on computers running PowerShell 3.0</span></span>

<span data-ttu-id="e90d1-127">As instruções nas seções a seguir instalam os módulos no diretório `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e90d1-127">The instructions in the sections below install the modules in directory `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>
<span data-ttu-id="e90d1-128">No PowerShell 3.0, esse diretório não está listado em `$env:PSModulePath` por padrão. Portanto, você precisará adicioná-lo para que os módulos sejam carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e90d1-128">In PowerShell 3.0, this directory isn't listed in `$env:PSModulePath` by default, so you'll need to add it in order for the modules to be auto-loaded.</span></span> 

<span data-ttu-id="e90d1-129">Abra uma sessão do PowerShell com privilégios elevados e execute o seguinte comando (que entrará em vigor em sessões futuras):</span><span class="sxs-lookup"><span data-stu-id="e90d1-129">Open an elevated PowerShell session and run the following command (which will take effect in future sessions):</span></span>

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="e90d1-130">Computadores com a versão prévia de PackageManagement instalada</span><span class="sxs-lookup"><span data-stu-id="e90d1-130">Computers with the PackageManagement Preview installed</span></span>

> [!NOTE] 
> <span data-ttu-id="e90d1-131">A versão prévia do PackageManagement era um componente baixável que disponibilizava o PowerShellGet para as versões 3 e 4 do PowerShell. Porém, ela não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="e90d1-131">PackageManagement Preview was a downloadable component that made PowerShellGet available to PowerShell versions 3 and 4, but it is no longer available.</span></span>
> <span data-ttu-id="e90d1-132">Para testar se ela foi instalada em um computador específico, execute `Get-Module -ListAvailable PowerShellGet`.</span><span class="sxs-lookup"><span data-stu-id="e90d1-132">To test if it was installed on a given computer, run `Get-Module -ListAvailable PowerShellGet`.</span></span>

1. <span data-ttu-id="e90d1-133">Em uma sessão do PowerShell, use `Save-Module` para baixar a versão atual do **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="e90d1-133">From a PowerShell session, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="e90d1-134">Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="e90d1-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="e90d1-135">Cada pasta contém uma subpasta com um número de versão.</span><span class="sxs-lookup"><span data-stu-id="e90d1-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e90d1-136">Verifique se os módulos **PowerShellGet** e **PackageManagement** não estão carregados em nenhum outro processo.</span><span class="sxs-lookup"><span data-stu-id="e90d1-136">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>

1. <span data-ttu-id="e90d1-137">Reabra o console do PowerShell com permissões elevadas e execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e90d1-137">Reopen the PowerShell console with elevated permissions and run the following command.</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % { 
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="e90d1-138">Computadores sem PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e90d1-138">Computers without PowerShellGet</span></span>

<span data-ttu-id="e90d1-139">Para computadores sem qualquer versão do **PowerShellGet** instalada (teste com `Get-Module -ListAvailable PowerShellGet`), é necessário ter um computador com o **PowerShellGet** instalado para baixar os módulos.</span><span class="sxs-lookup"><span data-stu-id="e90d1-139">For computers without any version of **PowerShellGet** installed (test with `Get-Module -ListAvailable PowerShellGet`), a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="e90d1-140">No computador com o **PowerShellGet** instalado, use o `Save-Module` para baixar a versão atual do **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="e90d1-140">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="e90d1-141">Duas pastas serão baixadas: **PowerShellGet** e **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="e90d1-141">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="e90d1-142">Cada pasta contém uma subpasta com um número de versão.</span><span class="sxs-lookup"><span data-stu-id="e90d1-142">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e90d1-143">Copie a subpasta `<version>` nas pastas **PowerShellGet** e **PackageManagement** para o computador que não tem o **PowerShellGet** instalado, para as pastas `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` e `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`, respectivamente, o que exige uma sessão com privilégios.</span><span class="sxs-lookup"><span data-stu-id="e90d1-143">Copy the respective `<version>` subfolder in the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed, into folders `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` respectively, which requires an elevated session.</span></span>
   
1. <span data-ttu-id="e90d1-144">Por exemplo, se for possível acessar a pasta de download no outro computador (`ws1`) no computador de destino por meio de um caminho UNC (`\\ws1\C$\LocalFolder`), abra um console do PowerShell com permissões elevadas e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e90d1-144">For instance, if you can access the download folder on the other computer, say `ws1`, from the target computer via a UNC path, say `\\ws1\C$\LocalFolder`, open a PowerShell console with elevated permissions and run the following command:</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
