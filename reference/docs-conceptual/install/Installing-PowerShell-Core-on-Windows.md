---
title: Instalar o PowerShell no Windows
description: Informações sobre a instalação do PowerShell no Windows
ms.date: 05/21/2020
ms.openlocfilehash: 864f297e4f569030439bd6b581ef593d36f8b910
ms.sourcegitcommit: fd6a33b9fac973b3554fecfea7f51475e650a606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83791481"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="8bc50-103">Instalar o PowerShell no Windows</span><span class="sxs-lookup"><span data-stu-id="8bc50-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="8bc50-104">Há várias maneiras de instalar o PowerShell no Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc50-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8bc50-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8bc50-105">Prerequisites</span></span>

<span data-ttu-id="8bc50-106">A versão mais recente do PowerShell tem suporte no Windows 7 SP1, Server 2008 R2 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="8bc50-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="8bc50-107">Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="8bc50-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="8bc50-108">Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows anteriores ao Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8bc50-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="8bc50-109">Ele está disponível por meio do Windows Update ou de download direto.</span><span class="sxs-lookup"><span data-stu-id="8bc50-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="8bc50-110">Os sistemas totalmente corrigidos já têm esse pacote instalado.</span><span class="sxs-lookup"><span data-stu-id="8bc50-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="8bc50-111">Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="8bc50-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="8bc50-112">Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="8bc50-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="8bc50-113">Baixar o pacote do instalador</span><span class="sxs-lookup"><span data-stu-id="8bc50-113">Download the installer package</span></span>

<span data-ttu-id="8bc50-114">Para instalar o PowerShell no Windows, baixe o pacote de instalação na página de [lançamentos][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="8bc50-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="8bc50-115">Role a tela para baixo até a seção **Ativos** na página de Lançamentos.</span><span class="sxs-lookup"><span data-stu-id="8bc50-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="8bc50-116">A seção **Ativos** pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="8bc50-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="8bc50-117"><a id="msi" />Instalando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="8bc50-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="8bc50-118">O arquivo MSI tem esta aparência `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="8bc50-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="8bc50-119">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="8bc50-119">For example:</span></span>

- `PowerShell-7.0.1-win-x64.msi`
- `PowerShell-7.0.1-win-x86.msi`

<span data-ttu-id="8bc50-120">Após o download, clique duas vezes no instalador e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="8bc50-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="8bc50-121">O instalador cria um atalho no Menu Iniciar do Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc50-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="8bc50-122">Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="8bc50-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="8bc50-123">Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="8bc50-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="8bc50-124">O PowerShell 7 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="8bc50-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="8bc50-125">Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="8bc50-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="8bc50-126">O PowerShell 7 é instalado em `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="8bc50-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="8bc50-127">A pasta `$env:ProgramFiles\PowerShell\7` é adicionada ao `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="8bc50-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="8bc50-128">A pasta `$env:ProgramFiles\PowerShell\6` é excluída</span><span class="sxs-lookup"><span data-stu-id="8bc50-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="8bc50-129">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [instalação por ZIP](#zip).</span><span class="sxs-lookup"><span data-stu-id="8bc50-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="8bc50-130">Instalação administrativa a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="8bc50-130">Administrative install from the command line</span></span>

<span data-ttu-id="8bc50-131">É possível instalar os pacotes MSI por linha de comando, permitindo que os administradores implantem pacotes sem interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="8bc50-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="8bc50-132">O pacote MSI inclui as seguintes propriedades para controlar as opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="8bc50-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="8bc50-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="8bc50-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="8bc50-134">**ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="8bc50-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="8bc50-135">**REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc50-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="8bc50-136">Os exemplos a seguir mostram como instalar silenciosamente o PowerShell com todas as opções de instalação habilitadas.</span><span class="sxs-lookup"><span data-stu-id="8bc50-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="8bc50-137">Confira a lista completa das opções de linha de comando para `Msiexec.exe` em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="8bc50-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="8bc50-138"><a id="msix" />Instalação do pacote MSIX</span><span class="sxs-lookup"><span data-stu-id="8bc50-138"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="8bc50-139">Para instalar manualmente o pacote MSIX em um cliente Windows 10, baixe o pacote MSIX na nossa página de [versões][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="8bc50-139">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="8bc50-140">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="8bc50-140">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="8bc50-141">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="8bc50-141">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="8bc50-142">O arquivo MSIX tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="8bc50-142">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="8bc50-143">Para instalar o pacote, você deve usar o cmdlet `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="8bc50-143">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> <span data-ttu-id="8bc50-144">O pacote MSIX ainda não foi liberado.</span><span class="sxs-lookup"><span data-stu-id="8bc50-144">The MSIX package has not been released yet.</span></span> <span data-ttu-id="8bc50-145">Quando lançado, o pacote estará disponível na Microsoft Store e na página de [lançamentos][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="8bc50-145">When released, the package will be available in the Microsoft Store and from the GitHub [releases][releases] page.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="8bc50-146"><a id="zip" />Instalando o pacote ZIP</span><span class="sxs-lookup"><span data-stu-id="8bc50-146"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="8bc50-147">Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="8bc50-147">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="8bc50-148">A instalação do arquivo ZIP não verifica os pré-requisitos como os pacotes MSI fazem.</span><span class="sxs-lookup"><span data-stu-id="8bc50-148">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="8bc50-149">Baixe o arquivo ZIP na página de [versões][releases].</span><span class="sxs-lookup"><span data-stu-id="8bc50-149">Download the ZIP archive from the [releases][releases] page.</span></span> <span data-ttu-id="8bc50-150">Dependendo de como você baixar o arquivo, poderá ser necessário desbloqueá-lo usando o cmdlet `Unblock-File`.</span><span class="sxs-lookup"><span data-stu-id="8bc50-150">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="8bc50-151">Descompacte o conteúdo para o local de sua escolha e execute `pwsh.exe` desse local.</span><span class="sxs-lookup"><span data-stu-id="8bc50-151">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="8bc50-152">Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de atender aos [pré-requisitos](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="8bc50-152">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="8bc50-153">Implantar no Windows 10 IoT Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bc50-153">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="8bc50-154">O Windows 10 IoT Enterprise vem com o Windows PowerShell, que pode ser usado para implantar o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="8bc50-154">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="8bc50-155">Crie `PSSession` no dispositivo de destino</span><span class="sxs-lookup"><span data-stu-id="8bc50-155">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="8bc50-156">Copie o pacote ZIP no dispositivo</span><span class="sxs-lookup"><span data-stu-id="8bc50-156">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="8bc50-157">Conecte-se ao dispositivo e expanda o arquivo</span><span class="sxs-lookup"><span data-stu-id="8bc50-157">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="8bc50-158">Configure a comunicação remota no PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="8bc50-158">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="8bc50-159">Conectar-se ao ponto de extremidade do PowerShell 7 no dispositivo</span><span class="sxs-lookup"><span data-stu-id="8bc50-159">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="8bc50-160">Implantar no Windows 10 IoT Core</span><span class="sxs-lookup"><span data-stu-id="8bc50-160">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="8bc50-161">O Windows 10 IoT Core adiciona o Windows PowerShell quando você inclui o recurso *IOT_POWERSHELL*, que pode ser usado para implantar o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="8bc50-161">Windows 10 IoT Core adds Windows PowerShell when you include *IOT_POWERSHELL* feature, which we can use to deploy PowerShell 7.</span></span>
<span data-ttu-id="8bc50-162">As etapas definidas acima para o Windows 10 IoT Enterprise também podem ser seguidas para o IoT Core.</span><span class="sxs-lookup"><span data-stu-id="8bc50-162">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="8bc50-163">Para adicionar o PowerShell mais recente na imagem de remessa, use o comando [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) para incluir o pacote na área de trabalho e adicione o recurso *OPENSRC_POWERSHELL* à imagem.</span><span class="sxs-lookup"><span data-stu-id="8bc50-163">For adding the latest powershell in the shipping image, use [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) command to include the package in the workarea and add *OPENSRC_POWERSHELL* feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc50-164">Para a arquitetura ARM64, o Windows PowerShell não é adicionado quando você inclui *IOT_POWERSHELL*.</span><span class="sxs-lookup"><span data-stu-id="8bc50-164">For ARM64 architecture, Windows Powershell is not added when you include *IOT_POWERSHELL*.</span></span> <span data-ttu-id="8bc50-165">Portanto, a instalação baseada em zip não funcionará.</span><span class="sxs-lookup"><span data-stu-id="8bc50-165">So the zip based install will not work.</span></span>
> <span data-ttu-id="8bc50-166">Você precisará usar o comando Import-PSCoreRelease para adicioná-lo à imagem.</span><span class="sxs-lookup"><span data-stu-id="8bc50-166">You will need to use Import-PSCoreRelease command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="8bc50-167">Implantação no Nano Server</span><span class="sxs-lookup"><span data-stu-id="8bc50-167">Deploying on Nano Server</span></span>

<span data-ttu-id="8bc50-168">Essas instruções pressupõem que o Nano Server é um sistema operacional "sem periféricos" que tem uma versão do PowerShell já em execução.</span><span class="sxs-lookup"><span data-stu-id="8bc50-168">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="8bc50-169">Confira mais informações na documentação do [Construtor de Imagens do Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="8bc50-169">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="8bc50-170">Os binários do PowerShell podem ser implantados usando dois métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="8bc50-170">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="8bc50-171">Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.</span><span class="sxs-lookup"><span data-stu-id="8bc50-171">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="8bc50-172">Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.</span><span class="sxs-lookup"><span data-stu-id="8bc50-172">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="8bc50-173">Em ambos os casos, você precisa do pacote de versão ZIP do Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="8bc50-173">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="8bc50-174">Execute os comandos em uma instância de "Administrador" do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bc50-174">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="8bc50-175">Implantação offline do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bc50-175">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="8bc50-176">Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.</span><span class="sxs-lookup"><span data-stu-id="8bc50-176">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="8bc50-177">Desmonte a imagem e inicialize-a.</span><span class="sxs-lookup"><span data-stu-id="8bc50-177">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="8bc50-178">Conecte-se à instância da caixa de entrada do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bc50-178">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="8bc50-179">Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="8bc50-179">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="8bc50-180">Implantação online do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bc50-180">Online Deployment of PowerShell</span></span>

<span data-ttu-id="8bc50-181">Implante o PowerShell no Nano Server usando as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bc50-181">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="8bc50-182">Conectar-se à instância da caixa de entrada do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bc50-182">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="8bc50-183">Copiar o arquivo para a instância do Nano Server</span><span class="sxs-lookup"><span data-stu-id="8bc50-183">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="8bc50-184">Entrar na sessão</span><span class="sxs-lookup"><span data-stu-id="8bc50-184">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="8bc50-185">Extrair o arquivo ZIP</span><span class="sxs-lookup"><span data-stu-id="8bc50-185">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="8bc50-186">Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="8bc50-186">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="8bc50-187">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="8bc50-187">Install as a .NET Global tool</span></span>

<span data-ttu-id="8bc50-188">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="8bc50-188">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="8bc50-189">O instalador da ferramenta dotnet adiciona `$env:USERPROFILE\dotnet\tools` à sua variável de ambiente `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="8bc50-189">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="8bc50-190">No entanto, o shell atualmente em execução não tem o `$env:PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="8bc50-190">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="8bc50-191">Você pode iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="8bc50-191">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="8bc50-192">Como criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="8bc50-192">How to create a remoting endpoint</span></span>

<span data-ttu-id="8bc50-193">O PowerShell dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH.</span><span class="sxs-lookup"><span data-stu-id="8bc50-193">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="8bc50-194">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="8bc50-194">For more information, see:</span></span>

- <span data-ttu-id="8bc50-195">[Comunicação remota do SSH no PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="8bc50-195">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="8bc50-196">[Comunicação remota do WSMan no PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="8bc50-196">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
