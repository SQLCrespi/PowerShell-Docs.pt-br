---
title: Instalar o PowerShell Core no Windows
description: Informações sobre a instalação do PowerShell Core no Windows
ms.date: 08/06/2018
ms.openlocfilehash: 00a1d8064a3c1ec6608a46415bbabb8d98d880f0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416768"
---
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="cbe57-103">Instalar o PowerShell Core no Windows</span><span class="sxs-lookup"><span data-stu-id="cbe57-103">Installing PowerShell Core on Windows</span></span>

<span data-ttu-id="cbe57-104">Há várias maneiras de instalar o PowerShell Core no Windows.</span><span class="sxs-lookup"><span data-stu-id="cbe57-104">There are multiple ways to install PowerShell Core in Windows.</span></span>

> [!TIP]
> <span data-ttu-id="cbe57-105">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="cbe57-105">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it’s easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>
>
> ```
> dotnet tool install --global PowerShell
> ```

## <a name="prerequisites"></a><span data-ttu-id="cbe57-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="cbe57-106">Prerequisites</span></span>

<span data-ttu-id="cbe57-107">Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="cbe57-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="cbe57-108">Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows antes do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cbe57-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span> <span data-ttu-id="cbe57-109">Ele está disponível por meio do Windows Update ou de download direto.</span><span class="sxs-lookup"><span data-stu-id="cbe57-109">It is available via direct download or Windows Update.</span></span> <span data-ttu-id="cbe57-110">Sistemas operacionais com suporte totalmente corrigidos (incluindo pacotes opcionais) já o terão instalado.</span><span class="sxs-lookup"><span data-stu-id="cbe57-110">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="cbe57-111">Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="cbe57-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="cbe57-112">Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="cbe57-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="a-idmsi-installing-the-msi-package"></a><span data-ttu-id="cbe57-113"><a id="msi" />Instalando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="cbe57-113"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="cbe57-114">Para instalar o PowerShell em um cliente do Windows ou Windows Server (funciona no Windows 7 SP1, no Server 2008 R2 e posterior), baixe o pacote MSI da nossa página [versões][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="cbe57-114">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="cbe57-115">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="cbe57-115">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="cbe57-116">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="cbe57-116">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="cbe57-117">O arquivo MSI tem esta aparência – `PowerShell-<version>-win-<os-arch>.msi`</span><span class="sxs-lookup"><span data-stu-id="cbe57-117">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`</span></span>
<!-- TODO: should be updated to point to the Download Center as well -->

<span data-ttu-id="cbe57-118">Após o download, clique duas vezes no instalador e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="cbe57-118">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="cbe57-119">O instalador cria um atalho no Menu Iniciar do Windows.</span><span class="sxs-lookup"><span data-stu-id="cbe57-119">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="cbe57-120">Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="cbe57-120">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="cbe57-121">Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="cbe57-121">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="cbe57-122">Instalação administrativa a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="cbe57-122">Administrative install from the command line</span></span>

<span data-ttu-id="cbe57-123">É possível instalar os pacotes do MSI a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="cbe57-123">MSI packages can be installed from the command line.</span></span> <span data-ttu-id="cbe57-124">Assim os administradores podem implantar pacotes sem interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="cbe57-124">This allows administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="cbe57-125">O pacote MSI para PowerShell inclui as seguintes propriedades para controlar as opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="cbe57-125">The MSI package for PowerShell includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="cbe57-126">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="cbe57-126">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="cbe57-127">**ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="cbe57-127">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="cbe57-128">**REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="cbe57-128">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="cbe57-129">Os exemplos a seguir mostram como instalar silenciosamente o PowerShell Core com todas as opções de instalação habilitadas.</span><span class="sxs-lookup"><span data-stu-id="cbe57-129">The following examples shows how to silently install PowerShell Core with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="cbe57-130">Confira a lista completa das opções de linha de comando para Msiexec.exe em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="cbe57-130">For a full list of command line options for Msiexec.exe, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="a-idmsix-installing-the-msix-package"></a><span data-ttu-id="cbe57-131"><a id="msix" />Instalação do pacote MSIX</span><span class="sxs-lookup"><span data-stu-id="cbe57-131"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="cbe57-132">Para instalar manualmente o pacote MSIX em um cliente Windows 10, baixe o pacote MSIX na nossa página de [versões][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="cbe57-132">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="cbe57-133">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="cbe57-133">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="cbe57-134">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="cbe57-134">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="cbe57-135">O arquivo MSI tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="cbe57-135">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="cbe57-136">Após o download, você não pode simplesmente clicar duas vezes no instalador porque esse pacote requer o uso de recursos não virtualizados.</span><span class="sxs-lookup"><span data-stu-id="cbe57-136">Once downloaded, you cannot simply double-click on the installer as this package requires use of un-virtualized resources.</span></span>  <span data-ttu-id="cbe57-137">Para instalar, você deve usar o cmdlet `Add-AppxPackage`:</span><span class="sxs-lookup"><span data-stu-id="cbe57-137">To install, you must use the `Add-AppxPackage` cmdlet:</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="a-idzip-installing-the-zip-package"></a><span data-ttu-id="cbe57-138"><a id="zip" />Instalando o pacote ZIP</span><span class="sxs-lookup"><span data-stu-id="cbe57-138"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="cbe57-139">Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="cbe57-139">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="cbe57-140">Observe que, ao usar o arquivo ZIP, você não obtém a verificação de pré-requisitos, como ocorre no pacote MSI.</span><span class="sxs-lookup"><span data-stu-id="cbe57-140">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span> <span data-ttu-id="cbe57-141">Para que a comunicação remota pelo WSMan funcione corretamente, verifique se você cumpriu os [pré-requisitos](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="cbe57-141">For remoting over WSMan to work properly, ensure that you have met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="cbe57-142">Implantar no Windows IoT</span><span class="sxs-lookup"><span data-stu-id="cbe57-142">Deploying on Windows IoT</span></span>

<span data-ttu-id="cbe57-143">O Windows IoT já é fornecido com o Windows PowerShell, o qual usaremos para implantar o PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="cbe57-143">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="cbe57-144">Crie `PSSession` no dispositivo de destino</span><span class="sxs-lookup"><span data-stu-id="cbe57-144">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="cbe57-145">Copie o pacote ZIP no dispositivo</span><span class="sxs-lookup"><span data-stu-id="cbe57-145">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="cbe57-146">Conecte-se ao dispositivo e expanda o arquivo</span><span class="sxs-lookup"><span data-stu-id="cbe57-146">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="cbe57-147">Configuração de comunicação remota no PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="cbe57-147">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="cbe57-148">Conecte-se ao ponto de extremidade do PowerShell Core 6 no dispositivo</span><span class="sxs-lookup"><span data-stu-id="cbe57-148">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="cbe57-149">Implantação no Nano Server</span><span class="sxs-lookup"><span data-stu-id="cbe57-149">Deploying on Nano Server</span></span>

<span data-ttu-id="cbe57-150">Estas instruções pressupõem que uma versão do PowerShell já está em execução na imagem do Nano Server e que ela foi gerada pelo [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="cbe57-150">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="cbe57-151">Nano Server é um sistema operacional "sem periféricos".</span><span class="sxs-lookup"><span data-stu-id="cbe57-151">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="cbe57-152">Os principais binários podem ser implantados usando dois métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cbe57-152">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="cbe57-153">Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.</span><span class="sxs-lookup"><span data-stu-id="cbe57-153">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="cbe57-154">Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.</span><span class="sxs-lookup"><span data-stu-id="cbe57-154">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="cbe57-155">Em ambos os casos, você precisa do pacote da versão ZIP do Windows 10 x64 e precisa executar os comandos em uma instância "Administrador" do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbe57-155">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="cbe57-156">Implantação offline do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="cbe57-156">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="cbe57-157">Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.</span><span class="sxs-lookup"><span data-stu-id="cbe57-157">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="cbe57-158">Desmonte a imagem e inicialize-a.</span><span class="sxs-lookup"><span data-stu-id="cbe57-158">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="cbe57-159">Conecte-se à instância da caixa de entrada do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbe57-159">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="cbe57-160">Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="cbe57-160">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="cbe57-161">Implantação online do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="cbe57-161">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="cbe57-162">As etapas a seguir servem de orientação para a implantação do PowerShell Core em uma instância em execução do Nano Server, e a configuração do seu ponto de extremidade de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="cbe57-162">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="cbe57-163">Conectar-se à instância da caixa de entrada do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbe57-163">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="cbe57-164">Copiar o arquivo para a instância do Nano Server</span><span class="sxs-lookup"><span data-stu-id="cbe57-164">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="cbe57-165">Entrar na sessão</span><span class="sxs-lookup"><span data-stu-id="cbe57-165">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="cbe57-166">Extrair o arquivo ZIP</span><span class="sxs-lookup"><span data-stu-id="cbe57-166">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="cbe57-167">Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="cbe57-167">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="cbe57-168">Como criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="cbe57-168">How to create a remoting endpoint</span></span>

<span data-ttu-id="cbe57-169">O PowerShell Core dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH.</span><span class="sxs-lookup"><span data-stu-id="cbe57-169">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="cbe57-170">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="cbe57-170">For more information, see:</span></span>

- <span data-ttu-id="cbe57-171">[Comunicação remota do SSH no PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="cbe57-171">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="cbe57-172">[Comunicação remota do WSMan no PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="cbe57-172">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
