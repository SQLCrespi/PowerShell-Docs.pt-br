---
title: Instalar o PowerShell no Windows
description: Informações sobre a instalação do PowerShell no Windows
ms.date: 09/14/2020
ms.openlocfilehash: 8f1b60ef6bfef5c2434b0affabb5e0e7af392b96
ms.sourcegitcommit: 30c0c1563f8e840f24b65297e907f3583d90e677
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90574446"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="90ae3-103">Instalar o PowerShell no Windows</span><span class="sxs-lookup"><span data-stu-id="90ae3-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="90ae3-104">Há várias maneiras de instalar o PowerShell no Windows.</span><span class="sxs-lookup"><span data-stu-id="90ae3-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90ae3-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="90ae3-105">Prerequisites</span></span>

<span data-ttu-id="90ae3-106">A versão mais recente do PowerShell tem suporte no Windows 7 SP1, Server 2008 R2 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="90ae3-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="90ae3-107">Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="90ae3-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="90ae3-108">Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows anteriores ao Windows 10.</span><span class="sxs-lookup"><span data-stu-id="90ae3-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="90ae3-109">Ele está disponível por meio do Windows Update ou de download direto.</span><span class="sxs-lookup"><span data-stu-id="90ae3-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="90ae3-110">Os sistemas totalmente corrigidos já têm esse pacote instalado.</span><span class="sxs-lookup"><span data-stu-id="90ae3-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="90ae3-111">Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="90ae3-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="90ae3-112">Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="90ae3-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="90ae3-113">Baixar o pacote do instalador</span><span class="sxs-lookup"><span data-stu-id="90ae3-113">Download the installer package</span></span>

<span data-ttu-id="90ae3-114">Para instalar o PowerShell no Windows, baixe o pacote de instalação na página de [lançamentos][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="90ae3-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="90ae3-115">Role a tela para baixo até a seção **Ativos** na página de Lançamentos.</span><span class="sxs-lookup"><span data-stu-id="90ae3-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="90ae3-116">A seção **Ativos** pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="90ae3-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="90ae3-117"><a id="msi" />Instalando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="90ae3-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="90ae3-118">O arquivo MSI tem esta aparência `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="90ae3-119">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="90ae3-119">For example:</span></span>

- `PowerShell-7.0.3-win-x64.msi`
- `PowerShell-7.0.3-win-x86.msi`

<span data-ttu-id="90ae3-120">Após o download, clique duas vezes no instalador e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="90ae3-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="90ae3-121">O instalador cria um atalho no Menu Iniciar do Windows.</span><span class="sxs-lookup"><span data-stu-id="90ae3-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="90ae3-122">Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="90ae3-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="90ae3-123">Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="90ae3-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="90ae3-124">O PowerShell 7 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="90ae3-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="90ae3-125">Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="90ae3-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="90ae3-126">O PowerShell 7 é instalado em `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="90ae3-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="90ae3-127">A pasta `$env:ProgramFiles\PowerShell\7` é adicionada ao `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="90ae3-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="90ae3-128">A pasta `$env:ProgramFiles\PowerShell\6` é excluída</span><span class="sxs-lookup"><span data-stu-id="90ae3-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="90ae3-129">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [instalação por ZIP](#zip).</span><span class="sxs-lookup"><span data-stu-id="90ae3-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="90ae3-130">Instalação administrativa a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="90ae3-130">Administrative install from the command line</span></span>

<span data-ttu-id="90ae3-131">É possível instalar os pacotes MSI por linha de comando, permitindo que os administradores implantem pacotes sem interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="90ae3-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="90ae3-132">O pacote MSI inclui as seguintes propriedades para controlar as opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="90ae3-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="90ae3-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="90ae3-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="90ae3-134">**ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="90ae3-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="90ae3-135">**REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="90ae3-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="90ae3-136">Os exemplos a seguir mostram como instalar silenciosamente o PowerShell com todas as opções de instalação habilitadas.</span><span class="sxs-lookup"><span data-stu-id="90ae3-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="90ae3-137">Confira a lista completa das opções de linha de comando para `Msiexec.exe` em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="90ae3-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="90ae3-138">Chaves do Registro criadas durante a instalação</span><span class="sxs-lookup"><span data-stu-id="90ae3-138">Registry keys created during installation</span></span>

<span data-ttu-id="90ae3-139">A partir do PowerShell 7.1, o pacote MSI cria chaves do Registro que armazenam o local de instalação e a versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90ae3-139">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="90ae3-140">Esses valores estão localizados em `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-140">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="90ae3-141">O valor de `<GUID>` é único para cada tipo de build (versão ou versão prévia), versão principal e arquitetura.</span><span class="sxs-lookup"><span data-stu-id="90ae3-141">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="90ae3-142">Versão</span><span class="sxs-lookup"><span data-stu-id="90ae3-142">Release</span></span>    | <span data-ttu-id="90ae3-143">Arquitetura</span><span class="sxs-lookup"><span data-stu-id="90ae3-143">Architecture</span></span> |                                          <span data-ttu-id="90ae3-144">Chave do Registro</span><span class="sxs-lookup"><span data-stu-id="90ae3-144">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="90ae3-145">Versão 7.1.x</span><span class="sxs-lookup"><span data-stu-id="90ae3-145">7.1.x Release</span></span> |     <span data-ttu-id="90ae3-146">x86</span><span class="sxs-lookup"><span data-stu-id="90ae3-146">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="90ae3-147">Versão 7.1.x</span><span class="sxs-lookup"><span data-stu-id="90ae3-147">7.1.x Release</span></span> |     <span data-ttu-id="90ae3-148">x64</span><span class="sxs-lookup"><span data-stu-id="90ae3-148">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="90ae3-149">Versão 7.1.x</span><span class="sxs-lookup"><span data-stu-id="90ae3-149">7.1.x Preview</span></span> |     <span data-ttu-id="90ae3-150">x86</span><span class="sxs-lookup"><span data-stu-id="90ae3-150">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="90ae3-151">Versão 7.1.x</span><span class="sxs-lookup"><span data-stu-id="90ae3-151">7.1.x Preview</span></span> |     <span data-ttu-id="90ae3-152">x64</span><span class="sxs-lookup"><span data-stu-id="90ae3-152">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="90ae3-153">Isso pode ser usado por administradores e desenvolvedores para encontrar o caminho para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90ae3-153">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="90ae3-154">Os valores de `<GUID>` serão os mesmos em todas as versões prévias e secundárias.</span><span class="sxs-lookup"><span data-stu-id="90ae3-154">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="90ae3-155">Os valores de `<GUID>` são alterados em cada versão principal.</span><span class="sxs-lookup"><span data-stu-id="90ae3-155">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="90ae3-156"><a id="msix" />Instalação do pacote MSIX</span><span class="sxs-lookup"><span data-stu-id="90ae3-156"><a id="msix" />Installing the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="90ae3-157">No momento, o pacote MSIX não tem suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="90ae3-157">The MSIX package is not officially supported at this time.</span></span> <span data-ttu-id="90ae3-158">Continuamos a criar o pacote apenas para fins de teste interno.</span><span class="sxs-lookup"><span data-stu-id="90ae3-158">We continue to build the package for internal testing purposes only.</span></span>

<span data-ttu-id="90ae3-159">Para instalar manualmente o pacote MSIX em um cliente Windows 10, baixe o pacote MSIX na nossa página de [versões][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="90ae3-159">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="90ae3-160">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="90ae3-160">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="90ae3-161">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="90ae3-161">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="90ae3-162">O arquivo MSIX tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="90ae3-162">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="90ae3-163">Para instalar o pacote, você deve usar o cmdlet `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-163">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><span data-ttu-id="90ae3-164"><a id="zip" />Instalando o pacote ZIP</span><span class="sxs-lookup"><span data-stu-id="90ae3-164"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="90ae3-165">Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="90ae3-165">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="90ae3-166">A instalação do arquivo ZIP não verifica os pré-requisitos como os pacotes MSI fazem.</span><span class="sxs-lookup"><span data-stu-id="90ae3-166">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="90ae3-167">Baixe o arquivo ZIP na página de [versões][releases].</span><span class="sxs-lookup"><span data-stu-id="90ae3-167">Download the ZIP archive from the [releases][releases] page.</span></span> <span data-ttu-id="90ae3-168">Dependendo de como você baixar o arquivo, poderá ser necessário desbloqueá-lo usando o cmdlet `Unblock-File`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-168">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="90ae3-169">Descompacte o conteúdo para o local de sua escolha e execute `pwsh.exe` desse local.</span><span class="sxs-lookup"><span data-stu-id="90ae3-169">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="90ae3-170">Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de atender aos [pré-requisitos](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="90ae3-170">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="90ae3-171">Implantar no Windows 10 IoT Enterprise</span><span class="sxs-lookup"><span data-stu-id="90ae3-171">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="90ae3-172">O Windows 10 IoT Enterprise vem com o Windows PowerShell, que pode ser usado para implantar o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="90ae3-172">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="90ae3-173">Crie `PSSession` no dispositivo de destino</span><span class="sxs-lookup"><span data-stu-id="90ae3-173">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="90ae3-174">Copie o pacote ZIP no dispositivo</span><span class="sxs-lookup"><span data-stu-id="90ae3-174">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="90ae3-175">Conecte-se ao dispositivo e expanda o arquivo</span><span class="sxs-lookup"><span data-stu-id="90ae3-175">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="90ae3-176">Configure a comunicação remota no PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="90ae3-176">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

1. <span data-ttu-id="90ae3-177">Conectar-se ao ponto de extremidade do PowerShell 7 no dispositivo</span><span class="sxs-lookup"><span data-stu-id="90ae3-177">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="90ae3-178">Implantar no Windows 10 IoT Core</span><span class="sxs-lookup"><span data-stu-id="90ae3-178">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="90ae3-179">O Windows 10 IoT Core adiciona o Windows PowerShell quando você inclui o recurso *IOT_POWERSHELL*, que pode ser usado para implantar o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="90ae3-179">Windows 10 IoT Core adds Windows PowerShell when you include *IOT_POWERSHELL* feature, which we can use to deploy PowerShell 7.</span></span>
<span data-ttu-id="90ae3-180">As etapas definidas acima para o Windows 10 IoT Enterprise também podem ser seguidas para o IoT Core.</span><span class="sxs-lookup"><span data-stu-id="90ae3-180">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="90ae3-181">Para adicionar o PowerShell mais recente na imagem de remessa, use o comando [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) para incluir o pacote na área de trabalho e adicione o recurso *OPENSRC_POWERSHELL* à imagem.</span><span class="sxs-lookup"><span data-stu-id="90ae3-181">For adding the latest powershell in the shipping image, use [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) command to include the package in the workarea and add *OPENSRC_POWERSHELL* feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="90ae3-182">Para a arquitetura ARM64, o Windows PowerShell não é adicionado quando você inclui *IOT_POWERSHELL*.</span><span class="sxs-lookup"><span data-stu-id="90ae3-182">For ARM64 architecture, Windows Powershell is not added when you include *IOT_POWERSHELL*.</span></span> <span data-ttu-id="90ae3-183">Portanto, a instalação baseada em zip não funcionará.</span><span class="sxs-lookup"><span data-stu-id="90ae3-183">So the zip based install will not work.</span></span>
> <span data-ttu-id="90ae3-184">Você precisará usar o comando Import-PSCoreRelease para adicioná-lo à imagem.</span><span class="sxs-lookup"><span data-stu-id="90ae3-184">You will need to use Import-PSCoreRelease command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="90ae3-185">Implantação no Nano Server</span><span class="sxs-lookup"><span data-stu-id="90ae3-185">Deploying on Nano Server</span></span>

<span data-ttu-id="90ae3-186">Essas instruções pressupõem que o Nano Server é um sistema operacional "sem periféricos" que tem uma versão do PowerShell já em execução.</span><span class="sxs-lookup"><span data-stu-id="90ae3-186">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="90ae3-187">Confira mais informações na documentação do [Construtor de Imagens do Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="90ae3-187">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="90ae3-188">Os binários do PowerShell podem ser implantados usando dois métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="90ae3-188">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="90ae3-189">Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.</span><span class="sxs-lookup"><span data-stu-id="90ae3-189">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="90ae3-190">Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.</span><span class="sxs-lookup"><span data-stu-id="90ae3-190">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="90ae3-191">Em ambos os casos, você precisa do pacote de versão ZIP do Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="90ae3-191">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="90ae3-192">Execute os comandos em uma instância de "Administrador" do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90ae3-192">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="90ae3-193">Implantação offline do PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae3-193">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="90ae3-194">Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.</span><span class="sxs-lookup"><span data-stu-id="90ae3-194">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="90ae3-195">Desmonte a imagem e inicialize-a.</span><span class="sxs-lookup"><span data-stu-id="90ae3-195">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="90ae3-196">Conecte-se à instância interna do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90ae3-196">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="90ae3-197">Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="90ae3-197">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="90ae3-198">Implantação online do PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae3-198">Online Deployment of PowerShell</span></span>

<span data-ttu-id="90ae3-199">Implante o PowerShell no Nano Server usando as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="90ae3-199">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="90ae3-200">Conectar-se à instância interna do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae3-200">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="90ae3-201">Copiar o arquivo para a instância do Nano Server</span><span class="sxs-lookup"><span data-stu-id="90ae3-201">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="90ae3-202">Entrar na sessão</span><span class="sxs-lookup"><span data-stu-id="90ae3-202">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="90ae3-203">Extrair o arquivo ZIP</span><span class="sxs-lookup"><span data-stu-id="90ae3-203">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="90ae3-204">Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="90ae3-204">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="90ae3-205">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="90ae3-205">Install as a .NET Global tool</span></span>

<span data-ttu-id="90ae3-206">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="90ae3-206">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="90ae3-207">O instalador da ferramenta dotnet adiciona `$env:USERPROFILE\dotnet\tools` à sua variável de ambiente `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-207">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="90ae3-208">No entanto, o shell atualmente em execução não tem o `$env:PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="90ae3-208">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="90ae3-209">Você pode iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="90ae3-209">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="90ae3-210">Instalar o PowerShell por meio do Winget</span><span class="sxs-lookup"><span data-stu-id="90ae3-210">Install PowerShell via Winget</span></span>

<span data-ttu-id="90ae3-211">A ferramenta de linha de comando `winget` permite que os desenvolvedores descubram, instalem, atualizem, removam e configurem aplicativos em computadores Windows 10.</span><span class="sxs-lookup"><span data-stu-id="90ae3-211">The `winget` command-line tool enables developers to discover, install, upgrade, remove and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="90ae3-212">Essa ferramenta é a interface do cliente para o serviço Gerenciador de Pacotes do Windows.</span><span class="sxs-lookup"><span data-stu-id="90ae3-212">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="90ae3-213">Atualmente, a ferramenta `winget` está em versão prévia.</span><span class="sxs-lookup"><span data-stu-id="90ae3-213">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="90ae3-214">Nem todas as funcionalidades planejadas estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="90ae3-214">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="90ae3-215">As opções e os recursos da ferramenta estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="90ae3-215">The tool's options and features are subject to change.</span></span> <span data-ttu-id="90ae3-216">Não use esse método em um cenário de implantação de produção.</span><span class="sxs-lookup"><span data-stu-id="90ae3-216">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="90ae3-217">Confira a documentação do [winget] para obter uma lista de requisitos do sistema e de instruções de instalação.</span><span class="sxs-lookup"><span data-stu-id="90ae3-217">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="90ae3-218">Os seguintes comandos podem ser usados para instalar o PowerShell com os pacotes do `winget` publicados:</span><span class="sxs-lookup"><span data-stu-id="90ae3-218">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="90ae3-219">Pesquisar a versão mais recente do PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae3-219">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.0.3
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="90ae3-220">Instalar uma versão do PowerShell usando o parâmetro `--exact`</span><span class="sxs-lookup"><span data-stu-id="90ae3-220">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="90ae3-221">Como criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="90ae3-221">How to create a remoting endpoint</span></span>

<span data-ttu-id="90ae3-222">O PowerShell dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH.</span><span class="sxs-lookup"><span data-stu-id="90ae3-222">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="90ae3-223">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="90ae3-223">For more information, see:</span></span>

- <span data-ttu-id="90ae3-224">[Comunicação remota do SSH no PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="90ae3-224">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="90ae3-225">[Comunicação remota do WSMan no PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="90ae3-225">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="installation-support"></a><span data-ttu-id="90ae3-226">Suporte à instalação</span><span class="sxs-lookup"><span data-stu-id="90ae3-226">Installation support</span></span>

<span data-ttu-id="90ae3-227">A Microsoft dá suporte aos métodos de instalação neste documento.</span><span class="sxs-lookup"><span data-stu-id="90ae3-227">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="90ae3-228">Pode haver outros métodos de instalação disponíveis de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="90ae3-228">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="90ae3-229">Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.</span><span class="sxs-lookup"><span data-stu-id="90ae3-229">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
