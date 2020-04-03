---
title: Instalar o PowerShell no Windows
description: Informações sobre a instalação do PowerShell no Windows
ms.date: 08/06/2018
ms.openlocfilehash: ea5432725f4baea8c688fb8e67482910e2c3981e
ms.sourcegitcommit: b6cf10224eb9f32919a505cdffbe5968241c18a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "80374886"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="3093c-103">Instalar o PowerShell no Windows</span><span class="sxs-lookup"><span data-stu-id="3093c-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="3093c-104">Há várias maneiras de instalar o PowerShell no Windows.</span><span class="sxs-lookup"><span data-stu-id="3093c-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3093c-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3093c-105">Prerequisites</span></span>

<span data-ttu-id="3093c-106">A versão mais recente do PowerShell tem suporte no Windows 7 SP1, Server 2008 R2 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="3093c-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="3093c-107">Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="3093c-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="3093c-108">Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows anteriores ao Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3093c-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="3093c-109">Ele está disponível por meio do Windows Update ou de download direto.</span><span class="sxs-lookup"><span data-stu-id="3093c-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="3093c-110">Os sistemas totalmente corrigidos já têm esse pacote instalado.</span><span class="sxs-lookup"><span data-stu-id="3093c-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="3093c-111">Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="3093c-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="3093c-112">Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="3093c-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="3093c-113">Baixar o pacote do instalador</span><span class="sxs-lookup"><span data-stu-id="3093c-113">Download the installer package</span></span>

<span data-ttu-id="3093c-114">Para instalar o PowerShell no Windows, baixe o pacote de instalação na página de [lançamentos][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="3093c-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="3093c-115">Role a tela para baixo até a seção **Ativos** na página de Lançamentos.</span><span class="sxs-lookup"><span data-stu-id="3093c-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="3093c-116">A seção **Ativos** pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="3093c-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="3093c-117"><a id="msi" />Instalando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="3093c-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="3093c-118">O arquivo MSI tem esta aparência `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="3093c-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="3093c-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3093c-119">For example:</span></span>

- `PowerShell-7.0.0-win-x64.msi`
- `PowerShell-7.0.0-win-x86.msi`

<span data-ttu-id="3093c-120">Após o download, clique duas vezes no instalador e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="3093c-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="3093c-121">O instalador cria um atalho no Menu Iniciar do Windows.</span><span class="sxs-lookup"><span data-stu-id="3093c-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="3093c-122">Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`</span><span class="sxs-lookup"><span data-stu-id="3093c-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="3093c-123">Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="3093c-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="3093c-124">O PowerShell 7 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="3093c-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="3093c-125">Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="3093c-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="3093c-126">O PowerShell 7 é instalado em `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="3093c-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="3093c-127">A pasta `$env:ProgramFiles\PowerShell\7` é adicionada ao `$env:PATH`</span><span class="sxs-lookup"><span data-stu-id="3093c-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="3093c-128">A pasta `$env:ProgramFiles\PowerShell\6` é excluída</span><span class="sxs-lookup"><span data-stu-id="3093c-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="3093c-129">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [instalação por ZIP](#zip).</span><span class="sxs-lookup"><span data-stu-id="3093c-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="3093c-130">Instalação administrativa a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="3093c-130">Administrative install from the command line</span></span>

<span data-ttu-id="3093c-131">É possível instalar os pacotes MSI por linha de comando, permitindo que os administradores implantem pacotes sem interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="3093c-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="3093c-132">O pacote MSI inclui as seguintes propriedades para controlar as opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="3093c-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="3093c-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="3093c-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="3093c-134">**ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="3093c-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="3093c-135">**REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="3093c-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="3093c-136">Os exemplos a seguir mostram como instalar silenciosamente o PowerShell com todas as opções de instalação habilitadas.</span><span class="sxs-lookup"><span data-stu-id="3093c-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="3093c-137">Confira a lista completa das opções de linha de comando para `Msiexec.exe` em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="3093c-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="3093c-138"><a id="msix" />Instalação do pacote MSIX</span><span class="sxs-lookup"><span data-stu-id="3093c-138"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="3093c-139">Para instalar manualmente o pacote MSIX em um cliente Windows 10, baixe o pacote MSIX na nossa página de [versões][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="3093c-139">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="3093c-140">Role a tela até a seção **Ativos** da versão que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="3093c-140">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="3093c-141">A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="3093c-141">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="3093c-142">O arquivo MSIX tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="3093c-142">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="3093c-143">Para instalar o pacote, você deve usar o cmdlet `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="3093c-143">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> <span data-ttu-id="3093c-144">O pacote MSIX ainda não foi liberado.</span><span class="sxs-lookup"><span data-stu-id="3093c-144">The MSIX package has not been released yet.</span></span> <span data-ttu-id="3093c-145">Quando lançado, o pacote estará disponível na Microsoft Store e na página de [lançamentos][releases] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="3093c-145">When released, the package will be available in the Microsoft Store and from the GitHub [releases][releases] page.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="3093c-146"><a id="zip" />Instalando o pacote ZIP</span><span class="sxs-lookup"><span data-stu-id="3093c-146"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="3093c-147">Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="3093c-147">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="3093c-148">A instalação do arquivo ZIP não verifica os pré-requisitos como os pacotes MSI fazem.</span><span class="sxs-lookup"><span data-stu-id="3093c-148">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="3093c-149">Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de atender aos [pré-requisitos](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3093c-149">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="3093c-150">Implantar no Windows IoT</span><span class="sxs-lookup"><span data-stu-id="3093c-150">Deploying on Windows IoT</span></span>

<span data-ttu-id="3093c-151">O Windows IoT é fornecido com o Windows PowerShell, que podemos usar para implantar o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="3093c-151">Windows IoT comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="3093c-152">Crie `PSSession` no dispositivo de destino</span><span class="sxs-lookup"><span data-stu-id="3093c-152">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="3093c-153">Copie o pacote ZIP no dispositivo</span><span class="sxs-lookup"><span data-stu-id="3093c-153">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="3093c-154">Conecte-se ao dispositivo e expanda o arquivo</span><span class="sxs-lookup"><span data-stu-id="3093c-154">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="3093c-155">Configure a comunicação remota no PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="3093c-155">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="3093c-156">Conectar-se ao ponto de extremidade do PowerShell 7 no dispositivo</span><span class="sxs-lookup"><span data-stu-id="3093c-156">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="3093c-157">Implantação no Nano Server</span><span class="sxs-lookup"><span data-stu-id="3093c-157">Deploying on Nano Server</span></span>

<span data-ttu-id="3093c-158">Essas instruções pressupõem que o Nano Server é um sistema operacional "sem periféricos" que tem uma versão do PowerShell já em execução.</span><span class="sxs-lookup"><span data-stu-id="3093c-158">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="3093c-159">Confira mais informações na documentação do [Construtor de Imagens do Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="3093c-159">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="3093c-160">Os binários do PowerShell podem ser implantados usando dois métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3093c-160">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="3093c-161">Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.</span><span class="sxs-lookup"><span data-stu-id="3093c-161">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="3093c-162">Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.</span><span class="sxs-lookup"><span data-stu-id="3093c-162">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="3093c-163">Em ambos os casos, você precisa do pacote de versão ZIP do Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="3093c-163">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="3093c-164">Execute os comandos em uma instância de "Administrador" do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3093c-164">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="3093c-165">Implantação offline do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3093c-165">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="3093c-166">Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.</span><span class="sxs-lookup"><span data-stu-id="3093c-166">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="3093c-167">Desmonte a imagem e inicialize-a.</span><span class="sxs-lookup"><span data-stu-id="3093c-167">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="3093c-168">Conecte-se à instância da caixa de entrada do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3093c-168">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="3093c-169">Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="3093c-169">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="3093c-170">Implantação online do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3093c-170">Online Deployment of PowerShell</span></span>

<span data-ttu-id="3093c-171">Implante o PowerShell no Nano Server usando as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3093c-171">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="3093c-172">Conectar-se à instância da caixa de entrada do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3093c-172">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="3093c-173">Copiar o arquivo para a instância do Nano Server</span><span class="sxs-lookup"><span data-stu-id="3093c-173">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="3093c-174">Entrar na sessão</span><span class="sxs-lookup"><span data-stu-id="3093c-174">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="3093c-175">Extrair o arquivo ZIP</span><span class="sxs-lookup"><span data-stu-id="3093c-175">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="3093c-176">Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="3093c-176">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="3093c-177">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="3093c-177">Install as a .NET Global tool</span></span>

<span data-ttu-id="3093c-178">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="3093c-178">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="3093c-179">O instalador da ferramenta dotnet adiciona `$env:USERPROFILE\dotnet\tools` à sua variável de ambiente `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="3093c-179">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="3093c-180">No entanto, o shell atualmente em execução não tem o `$env:PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="3093c-180">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="3093c-181">Você pode iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="3093c-181">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="3093c-182">Como criar um ponto de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="3093c-182">How to create a remoting endpoint</span></span>

<span data-ttu-id="3093c-183">O PowerShell dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH.</span><span class="sxs-lookup"><span data-stu-id="3093c-183">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="3093c-184">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3093c-184">For more information, see:</span></span>

- <span data-ttu-id="3093c-185">[Comunicação remota do SSH no PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="3093c-185">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="3093c-186">[Comunicação remota do WSMan no PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="3093c-186">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
