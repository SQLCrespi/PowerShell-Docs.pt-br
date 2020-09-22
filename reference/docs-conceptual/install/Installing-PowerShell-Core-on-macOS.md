---
title: Instalar o PowerShell no macOS
description: Informações sobre a instalação do PowerShell no macOS
ms.date: 08/24/2020
ms.openlocfilehash: 8f38d573d9d67276dbc95cfb70f1fde80af62bb6
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88857900"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="9ae2a-103">Instalar o PowerShell no macOS</span><span class="sxs-lookup"><span data-stu-id="9ae2a-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="9ae2a-104">O PowerShell oferece suporte para macOS 10.12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-104">PowerShell supports macOS 10.12 and higher.</span></span> <span data-ttu-id="9ae2a-105">O PowerShell 7.0.3 ou versões superiores e a versão prévia do PowerShell 7.1.0 ou versões superiores exigem o macOS 10.13 e versões superiores.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-105">PowerShell 7.0.3 or higher and PowerShell Preview 7.1.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="9ae2a-106">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-106">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="9ae2a-107">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-107">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae2a-108">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-108">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="9ae2a-109">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-109">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="9ae2a-110">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-110">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="9ae2a-111">Existem várias maneiras de instalar o PowerShell no macOS.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-111">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="9ae2a-112">Use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-112">Choose one of the following methods:</span></span>

- <span data-ttu-id="9ae2a-113">Instale o usando Homebrew.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-113">Install using Homebrew.</span></span> <span data-ttu-id="9ae2a-114">Homebrew é o gerenciador de pacotes preferido para macOS.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-114">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="9ae2a-115">Instale o PowerShell por meio do [Download Direto](#installation-via-direct-download)</span><span class="sxs-lookup"><span data-stu-id="9ae2a-115">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="9ae2a-116">Instale por meio dos [arquivos binários](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-116">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="9ae2a-117">Depois de instalar o PowerShell, você precisa instalar o [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-117">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="9ae2a-118">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-118">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="9ae2a-119">Instalação da versão estável mais recente por meio do Homebrew no macOS 10.13 ou superior</span><span class="sxs-lookup"><span data-stu-id="9ae2a-119">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="9ae2a-120">Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].</span><span class="sxs-lookup"><span data-stu-id="9ae2a-120">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="9ae2a-121">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="9ae2a-122">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="9ae2a-123">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="9ae2a-124">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="9ae2a-125">Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.13 ou superior</span><span class="sxs-lookup"><span data-stu-id="9ae2a-125">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="9ae2a-126">Depois de instalar o Homebrew, você pode instalar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-126">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="9ae2a-127">Primeiro instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-127">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="9ae2a-128">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-128">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="9ae2a-129">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="9ae2a-130">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-130">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="9ae2a-131">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="9ae2a-132">e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-132">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="9ae2a-133">É possível instalar o PowerShell usando o método de toque do Homebrew em versões LTS e estáveis.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-133">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="9ae2a-134">Agora você pode verificar sua instalação</span><span class="sxs-lookup"><span data-stu-id="9ae2a-134">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="9ae2a-135">Quando novas versões do PowerShell são lançadas, basta executar o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-135">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="9ae2a-136">Se você usar o método cask ou de toque, ao atualizar para uma versão mais recente do PowerShell, siga o mesmo método usado para instalar o PowerShell na primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-136">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="9ae2a-137">Se você usar um método diferente, abrir uma nova sessão de push continuará a usar a versão mais antiga do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-137">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="9ae2a-138">Se você decidir usar métodos diferentes, há maneiras de corrigir o problema usando o [método de link do Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-138">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="9ae2a-139">Instalação por meio de download direto</span><span class="sxs-lookup"><span data-stu-id="9ae2a-139">Installation via Direct Download</span></span>

<span data-ttu-id="9ae2a-140">Faça o download do pacote PKG `powershell-lts-7.0.3-osx-x64.pkg` da página [versões][] em seu computador com macOS.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-140">Download the PKG package `powershell-lts-7.0.3-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="9ae2a-141">Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-141">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.3-osx-x64.pkg -target /
```

<span data-ttu-id="9ae2a-142">Instalar [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-142">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="9ae2a-143">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-143">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="9ae2a-144">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="9ae2a-144">Install as a .NET Global tool</span></span>

<span data-ttu-id="9ae2a-145">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-145">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="9ae2a-146">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-146">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="9ae2a-147">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-147">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="9ae2a-148">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-148">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="9ae2a-149">Instalar [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-149">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="9ae2a-150">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-150">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="9ae2a-151">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="9ae2a-151">Binary Archives</span></span>

<span data-ttu-id="9ae2a-152">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-152">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="9ae2a-153">Ao instalar o usando esse método, você também deve instalar manualmente quaisquer dependências.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-153">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="9ae2a-154">Instalar [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-154">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="9ae2a-155">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-155">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="9ae2a-156">Instalação de arquivos binários no macOS</span><span class="sxs-lookup"><span data-stu-id="9ae2a-156">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="9ae2a-157">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="9ae2a-157">Installing dependencies</span></span>

<span data-ttu-id="9ae2a-158">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-158">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="9ae2a-159">É possível instalar o OpenSSL por meio de MacPorts, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-159">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae2a-160">O MacPorts e o Homebrew podem ter problemas quando usados juntos no mesmo sistema.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-160">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="9ae2a-161">No entanto, o Homebrew não tem um pacote para o OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-161">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="9ae2a-162">Para saber mais, confira as [Perguntas frequentes sobre o MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-162">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="9ae2a-163">Instale as ferramentas de linha de comando Xcode.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-163">Install the Xcode command-line tools.</span></span> <span data-ttu-id="9ae2a-164">As ferramentas do Xcode são exigidas pelo MacPorts.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-164">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="9ae2a-165">Instale MacPorts.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-165">Install MacPorts.</span></span> <span data-ttu-id="9ae2a-166">Se precisar de instruções, confira o [guia de instalação](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="9ae2a-166">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="9ae2a-167">Atualize o MacPorts executando `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-167">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="9ae2a-168">Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-168">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="9ae2a-169">Instale o OpenSSL executando `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-169">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="9ae2a-170">Vincule as bibliotecas para disponibilizá-las para o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-170">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="9ae2a-171">Desinstalar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ae2a-171">Uninstalling PowerShell</span></span>

<span data-ttu-id="9ae2a-172">Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-172">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="9ae2a-173">Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:</span><span class="sxs-lookup"><span data-stu-id="9ae2a-173">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="9ae2a-174">Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-174">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae2a-175">Isso não é necessário se você tiver instalado usando o Homebrew.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-175">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="9ae2a-176">Caminhos</span><span class="sxs-lookup"><span data-stu-id="9ae2a-176">Paths</span></span>

- <span data-ttu-id="9ae2a-177">`$PSHOME` é `/usr/local/microsoft/powershell/7.0.3/`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-177">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`</span></span>
- <span data-ttu-id="9ae2a-178">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-178">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="9ae2a-179">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-179">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="9ae2a-180">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-180">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="9ae2a-181">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-181">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="9ae2a-182">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-182">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="9ae2a-183">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="9ae2a-183">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="9ae2a-184">Os perfis respeitam a configuração por host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-184">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="9ae2a-185">Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-185">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="9ae2a-186">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-186">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="9ae2a-187">Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-187">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="9ae2a-188">Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/7.0.3/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-188">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="9ae2a-189">Suporte à instalação</span><span class="sxs-lookup"><span data-stu-id="9ae2a-189">Installation support</span></span>

<span data-ttu-id="9ae2a-190">A Microsoft dá suporte aos métodos de instalação neste documento.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-190">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="9ae2a-191">Pode haver outros métodos de instalação disponíveis de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-191">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="9ae2a-192">Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.</span><span class="sxs-lookup"><span data-stu-id="9ae2a-192">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ae2a-193">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9ae2a-193">Additional Resources</span></span>

- <span data-ttu-id="9ae2a-194">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="9ae2a-194">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="9ae2a-195">[Repositório do Homebrew no Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="9ae2a-195">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="9ae2a-196">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="9ae2a-196">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
