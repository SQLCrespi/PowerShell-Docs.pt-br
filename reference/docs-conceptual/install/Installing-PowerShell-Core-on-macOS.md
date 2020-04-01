---
title: Instalar o PowerShell no macOS
description: Informações sobre a instalação do PowerShell no macOS
ms.date: 12/12/2018
ms.openlocfilehash: 3a5e71d0f69d0c39f9b7f3fa667863d7ec0a31dd
ms.sourcegitcommit: bf71c8c5e2a4fc7d5c3a67a537db1285089d03a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2020
ms.locfileid: "80395002"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="f1ab0-103">Instalar o PowerShell no macOS</span><span class="sxs-lookup"><span data-stu-id="f1ab0-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="f1ab0-104">O PowerShell oferece suporte para macOS 10.12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-104">PowerShell supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="f1ab0-105">Todos os pacotes estão disponíveis na nossa página [lançamentos][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="f1ab0-106">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="f1ab0-107">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="f1ab0-108">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="f1ab0-109">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

## <a name="about-brew"></a><span data-ttu-id="f1ab0-110">Sobre Brew</span><span class="sxs-lookup"><span data-stu-id="f1ab0-110">About Brew</span></span>

<span data-ttu-id="f1ab0-111">[Homebrew][brew] é o gerenciador de pacotes preferido para macOS.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-111">[Homebrew][brew] is the preferred package manager for macOS.</span></span> <span data-ttu-id="f1ab0-112">Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].</span><span class="sxs-lookup"><span data-stu-id="f1ab0-112">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span> <span data-ttu-id="f1ab0-113">Caso contrário, você poderá instalar o PowerShell por [Download direto](#installation-via-direct-download) ou pelos [Arquivos binários](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-113">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="f1ab0-114">Instalação da versão estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="f1ab0-114">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="f1ab0-115">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-115">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="f1ab0-116">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-116">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="f1ab0-117">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-117">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="f1ab0-118">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-118">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="f1ab0-119">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-119">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="f1ab0-120">Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="f1ab0-120">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="f1ab0-121">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-121">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="f1ab0-122">Depois de instalar o Homebrew, você pode instalar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-122">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="f1ab0-123">Primeiro, instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-123">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="f1ab0-124">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-124">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="f1ab0-125">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-125">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="f1ab0-126">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-126">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="f1ab0-127">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-127">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="f1ab0-128">e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-128">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="f1ab0-129">Instalação por meio de download direto</span><span class="sxs-lookup"><span data-stu-id="f1ab0-129">Installation via Direct Download</span></span>

<span data-ttu-id="f1ab0-130">Baixe o pacote PKG `powershell-lts-7.0.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-130">Download the PKG package `powershell-lts-7.0.0-osx-x64.pkg`</span></span>
<span data-ttu-id="f1ab0-131">na página [Lançamentos][] no computador com macOS.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-131">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="f1ab0-132">Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-132">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.0-osx-x64.pkg -target /
```

<span data-ttu-id="f1ab0-133">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-133">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="f1ab0-134">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-134">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="f1ab0-135">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="f1ab0-135">Install as a .NET Global tool</span></span>

<span data-ttu-id="f1ab0-136">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-136">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="f1ab0-137">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-137">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="f1ab0-138">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-138">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="f1ab0-139">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-139">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="f1ab0-140">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="f1ab0-140">Binary Archives</span></span>

<span data-ttu-id="f1ab0-141">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-141">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="f1ab0-142">Instalação de arquivos binários no macOS</span><span class="sxs-lookup"><span data-stu-id="f1ab0-142">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="f1ab0-143">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-143">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="f1ab0-144">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-144">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="f1ab0-145">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="f1ab0-145">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="f1ab0-146">Instalar ferramentas da linha de comando XCode</span><span class="sxs-lookup"><span data-stu-id="f1ab0-146">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="f1ab0-147">Instalar o OpenSSL</span><span class="sxs-lookup"><span data-stu-id="f1ab0-147">Install OpenSSL</span></span>

<span data-ttu-id="f1ab0-148">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-148">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="f1ab0-149">Você pode instalar por meio de MacPorts ou Brew.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-149">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="f1ab0-150">Instalar o OpenSSL por meio de Brew</span><span class="sxs-lookup"><span data-stu-id="f1ab0-150">Install OpenSSL via Brew</span></span>

<span data-ttu-id="f1ab0-151">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-151">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="f1ab0-152">Execute `brew install openssl` para instalar o OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-152">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="f1ab0-153">Instalar o OpenSSL por meio de MacPorts</span><span class="sxs-lookup"><span data-stu-id="f1ab0-153">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="f1ab0-154">Instale as [ferramentas da linha de comando XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-154">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="f1ab0-155">Instale MacPorts.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-155">Install MacPorts.</span></span>
   <span data-ttu-id="f1ab0-156">Se precisar de instruções, confira o [guia de instalação](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="f1ab0-156">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="f1ab0-157">Atualize o MacPorts executando `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-157">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="f1ab0-158">Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-158">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="f1ab0-159">Instale o OpenSSL executando `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-159">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="f1ab0-160">Vincule as bibliotecas para disponibilizá-las para o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-160">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell"></a><span data-ttu-id="f1ab0-161">Desinstalar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ab0-161">Uninstalling PowerShell</span></span>

<span data-ttu-id="f1ab0-162">Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-162">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="f1ab0-163">Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:</span><span class="sxs-lookup"><span data-stu-id="f1ab0-163">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="f1ab0-164">Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-164">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="f1ab0-165">Isso não é necessário se você tiver instalado usando o Homebrew.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-165">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="f1ab0-166">Caminhos</span><span class="sxs-lookup"><span data-stu-id="f1ab0-166">Paths</span></span>

* <span data-ttu-id="f1ab0-167">`$PSHOME` é `/usr/local/microsoft/powershell/7.0.0/`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-167">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.0/`</span></span>
* <span data-ttu-id="f1ab0-168">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-168">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="f1ab0-169">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-169">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="f1ab0-170">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-170">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="f1ab0-171">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-171">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="f1ab0-172">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-172">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="f1ab0-173">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="f1ab0-173">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="f1ab0-174">Os perfis respeitam a configuração por host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-174">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="f1ab0-175">Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-175">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="f1ab0-176">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-176">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="f1ab0-177">Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-177">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="f1ab0-178">Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/7.0.0/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f1ab0-178">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f1ab0-179">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f1ab0-179">Additional Resources</span></span>

* <span data-ttu-id="f1ab0-180">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="f1ab0-180">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="f1ab0-181">[Repositório do Homebrew no Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="f1ab0-181">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="f1ab0-182">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="f1ab0-182">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[lançamentos]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
