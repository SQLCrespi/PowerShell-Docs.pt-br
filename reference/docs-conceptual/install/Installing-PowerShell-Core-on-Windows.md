---
title: Instalar o PowerShell Core no Windows
description: Informações sobre a instalação do PowerShell Core no Windows
ms.date: 08/06/2018
ms.openlocfilehash: 5a3c43e27f0027cfbeeefab33b045e618e0ff045
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854355"
---
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="d302a-103">Instalar o PowerShell Core no Windows</span><span class="sxs-lookup"><span data-stu-id="d302a-103">Installing PowerShell Core on Windows</span></span>

<span data-ttu-id="d302a-104">Há várias maneiras de instalar o PowerShell Core no Windows.</span><span class="sxs-lookup"><span data-stu-id="d302a-104">There are multiple ways to install PowerShell Core in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d302a-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d302a-105">Prerequisites</span></span>

<span data-ttu-id="d302a-106">Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="d302a-106">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="d302a-107">Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows antes do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d302a-107">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span> <span data-ttu-id="d302a-108">Ele está disponível por meio do Windows Update ou de download direto.</span><span class="sxs-lookup"><span data-stu-id="d302a-108">It is available via direct download or Windows Update.</span></span> <span data-ttu-id="d302a-109">Sistemas operacionais com suporte totalmente corrigidos (incluindo pacotes opcionais) já o terão instalado.</span><span class="sxs-lookup"><span data-stu-id="d302a-109">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="d302a-110">Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d302a-110">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="d302a-111">Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="d302a-111">For more information about WMF, see [WMF Overview](/powershell/wmf/overview).</span></span>

## <a name="a-idmsi-installing-the-msi-package"></a><span data-ttu-id="d302a-112"><a id="msi" />Instalando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="d302a-112"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="d302a-113">Para instalar o PowerShell em um cliente do Windows ou Windows Server (funciona no Windows 7 SP1, no Server 2008 R2 e posterior), baixe o pacote MSI da nossa página [versões][] no GitHub.</span><span class="sxs-lookup"><span data-stu-id="d302a-113">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][] page.</span></span> <span data-ttu-id="d302a-114">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="d302a-114">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="d302a-115">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="d302a-115">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="d302a-116">O arquivo MSI tem esta aparência – `PowerShell-<version>-win-<os-arch>.msi`</span><span class="sxs-lookup"><span data-stu-id="d302a-116">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`</span></span>
<!-- TODO: should be updated to point to the Download Center as well -->

<span data-ttu-id="d302a-117">Após o download, clique duas vezes no instalador e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="d302a-117">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="d302a-118">O instalador cria um atalho no Menu Iniciar do Windows.</span><span class="sxs-lookup"><span data-stu-id="d302a-118">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="d302a-119">Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="d302a-119">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="d302a-120">Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="d302a-120">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="d302a-121">Instalação administrativa a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="d302a-121">Administrative install from the command line</span></span>

<span data-ttu-id="d302a-122">É possível instalar os pacotes do MSI a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d302a-122">MSI packages can be installed from the command line.</span></span> <span data-ttu-id="d302a-123">Assim os administradores podem implantar pacotes sem interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="d302a-123">This allows administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="d302a-124">O pacote MSI para PowerShell inclui as seguintes propriedades para controlar as opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="d302a-124">The MSI package for PowerShell includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="d302a-125">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="d302a-125">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="d302a-126">**ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="d302a-126">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="d302a-127">**REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="d302a-127">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="d302a-128">Os exemplos a seguir mostram como instalar silenciosamente o PowerShell Core com todas as opções de instalação habilitadas.</span><span class="sxs-lookup"><span data-stu-id="d302a-128">The following examples shows how to silently install PowerShell Core with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="d302a-129">Confira a lista completa das opções de linha de comando para Msiexec.exe em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="d302a-129">For a full list of command line options for Msiexec.exe, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="a-idzip-installing-the-zip-package"></a><span data-ttu-id="d302a-130"><a id="zip" />Instalando o pacote ZIP</span><span class="sxs-lookup"><span data-stu-id="d302a-130"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="d302a-131">Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="d302a-131">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="d302a-132">Observe que, ao usar o arquivo ZIP, você não obtém a verificação de pré-requisitos, como ocorre no pacote MSI.</span><span class="sxs-lookup"><span data-stu-id="d302a-132">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span> <span data-ttu-id="d302a-133">Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de que você cumpriu os [pré-requisitos](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d302a-133">For remoting over WSMan to work properly,, ensure that you have met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="d302a-134">Implantar no Windows IoT</span><span class="sxs-lookup"><span data-stu-id="d302a-134">Deploying on Windows IoT</span></span>

<span data-ttu-id="d302a-135">O Windows IoT já é fornecido com o Windows PowerShell, o qual usaremos para implantar o PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="d302a-135">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="d302a-136">Crie `PSSession` no dispositivo de destino</span><span class="sxs-lookup"><span data-stu-id="d302a-136">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="d302a-137">Copie o pacote ZIP no dispositivo</span><span class="sxs-lookup"><span data-stu-id="d302a-137">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="d302a-138">Conecte-se ao dispositivo e expanda o arquivo</span><span class="sxs-lookup"><span data-stu-id="d302a-138">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="d302a-139">Configuração de comunicação remota no PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="d302a-139">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="d302a-140">Conecte-se ao ponto de extremidade do PowerShell Core 6 no dispositivo</span><span class="sxs-lookup"><span data-stu-id="d302a-140">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="d302a-141">Implantação no Nano Server</span><span class="sxs-lookup"><span data-stu-id="d302a-141">Deploying on Nano Server</span></span>

<span data-ttu-id="d302a-142">Estas instruções pressupõem que uma versão do PowerShell já está em execução na imagem do Nano Server e que ela foi gerada pelo [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="d302a-142">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="d302a-143">Nano Server é um sistema operacional "sem periféricos".</span><span class="sxs-lookup"><span data-stu-id="d302a-143">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="d302a-144">Os principais binários podem ser implantados usando dois métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d302a-144">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="d302a-145">Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.</span><span class="sxs-lookup"><span data-stu-id="d302a-145">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="d302a-146">Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.</span><span class="sxs-lookup"><span data-stu-id="d302a-146">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="d302a-147">Em ambos os casos, você precisa do pacote da versão ZIP do Windows 10 x64 e precisa executar os comandos em uma instância "Administrador" do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d302a-147">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="d302a-148">Implantação offline do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d302a-148">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="d302a-149">Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.</span><span class="sxs-lookup"><span data-stu-id="d302a-149">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="d302a-150">Desmonte a imagem e inicialize-a.</span><span class="sxs-lookup"><span data-stu-id="d302a-150">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="d302a-151">Conecte-se à instância da caixa de entrada do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d302a-151">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="d302a-152">Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="d302a-152">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="d302a-153">Implantação online do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d302a-153">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="d302a-154">As etapas a seguir servem de orientação para a implantação do PowerShell Core em uma instância em execução do Nano Server, e a configuração do seu ponto de extremidade de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="d302a-154">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="d302a-155">Conectar-se à instância da caixa de entrada do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d302a-155">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="d302a-156">Copiar o arquivo para a instância do Nano Server</span><span class="sxs-lookup"><span data-stu-id="d302a-156">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="d302a-157">Entrar na sessão</span><span class="sxs-lookup"><span data-stu-id="d302a-157">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="d302a-158">Extrair o arquivo ZIP</span><span class="sxs-lookup"><span data-stu-id="d302a-158">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="d302a-159">Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="d302a-159">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="d302a-160">Como criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="d302a-160">How to create a remoting endpoint</span></span>

<span data-ttu-id="d302a-161">O PowerShell Core dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH.</span><span class="sxs-lookup"><span data-stu-id="d302a-161">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="d302a-162">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="d302a-162">For more information, see:</span></span>

- <span data-ttu-id="d302a-163">[Comunicação remota do SSH no PowerShell Core] [comunicação remota ssh]</span><span class="sxs-lookup"><span data-stu-id="d302a-163">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="d302a-164">[Comunicação remota do WSMan no PowerShell Core][comunicação remota do wsman]</span><span class="sxs-lookup"><span data-stu-id="d302a-164">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->
[versões]: https://github.com/PowerShell/PowerShell/releases [comunicação remota ssh]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md [comunicação remota wsman]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md [AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[releases]: https://github.com/PowerShell/PowerShell/releases [ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md [wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md [AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
