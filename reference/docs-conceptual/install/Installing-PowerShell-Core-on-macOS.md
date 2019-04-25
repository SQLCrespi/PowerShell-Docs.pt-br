---
title: Instalar o PowerShell Core no macOS
description: Informações sobre a instalação do PowerShell Core no macOS
ms.date: 12/12/2018
ms.openlocfilehash: 7db8ca0cb6d13db8ce7f11b4a4b03b7d3f9b6feb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086452"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="3d3b0-103">Instalar o PowerShell Core no macOS</span><span class="sxs-lookup"><span data-stu-id="3d3b0-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="3d3b0-104">O PowerShell Core oferece suporte para macOS 10.12 e superior.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="3d3b0-105">Todos os pacotes estão disponíveis na nossa página [lançamentos][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="3d3b0-106">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="3d3b0-107">Sobre Brew</span><span class="sxs-lookup"><span data-stu-id="3d3b0-107">About Brew</span></span>

<span data-ttu-id="3d3b0-108">[Homebrew][brew] é o gerenciador de pacotes preferido para macOS.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="3d3b0-109">Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].</span><span class="sxs-lookup"><span data-stu-id="3d3b0-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="3d3b0-110">Instalação da versão estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="3d3b0-110">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="3d3b0-111">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-111">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3d3b0-112">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-112">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="3d3b0-113">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-113">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="3d3b0-114">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-114">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="3d3b0-115">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-115">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="3d3b0-116">Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="3d3b0-116">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="3d3b0-117">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-117">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3d3b0-118">Depois de instalar o Homebrew, você pode instalar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-118">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="3d3b0-119">Primeiro instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-119">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="3d3b0-120">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="3d3b0-121">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="3d3b0-122">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="3d3b0-123">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="3d3b0-124">e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-124">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="3d3b0-125">Instalação por meio de download direto</span><span class="sxs-lookup"><span data-stu-id="3d3b0-125">Installation via Direct Download</span></span>

<span data-ttu-id="3d3b0-126">Baixe o pacote PKG `powershell-6.2.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-126">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="3d3b0-127">na página [Lançamentos][] no computador com macOS.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="3d3b0-128">Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="3d3b0-129">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-129">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="3d3b0-130">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-130">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="3d3b0-131">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="3d3b0-131">Binary Archives</span></span>

<span data-ttu-id="3d3b0-132">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-132">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="3d3b0-133">Instalação de arquivos binários no macOS</span><span class="sxs-lookup"><span data-stu-id="3d3b0-133">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.2.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="3d3b0-134">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-134">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="3d3b0-135">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-135">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="3d3b0-136">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="3d3b0-136">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="3d3b0-137">Instalar ferramentas da linha de comando XCode</span><span class="sxs-lookup"><span data-stu-id="3d3b0-137">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="3d3b0-138">Instalar OpenSSL</span><span class="sxs-lookup"><span data-stu-id="3d3b0-138">Install OpenSSL</span></span>

<span data-ttu-id="3d3b0-139">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-139">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="3d3b0-140">Você pode instalar por meio de MacPorts ou Brew.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-140">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="3d3b0-141">Instalar o OpenSSL por meio de Brew</span><span class="sxs-lookup"><span data-stu-id="3d3b0-141">Install OpenSSL via Brew</span></span>

<span data-ttu-id="3d3b0-142">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-142">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3d3b0-143">Execute `brew install openssl` para instalar o OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-143">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="3d3b0-144">Instalar o OpenSSL por meio de MacPorts</span><span class="sxs-lookup"><span data-stu-id="3d3b0-144">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="3d3b0-145">Instale as [ferramentas da linha de comando XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-145">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="3d3b0-146">Instale MacPorts.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-146">Install MacPorts.</span></span>
   <span data-ttu-id="3d3b0-147">Se precisar de instruções, confira o [guia de instalação](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-147">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="3d3b0-148">Atualize o MacPorts executando `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-148">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="3d3b0-149">Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-149">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="3d3b0-150">Instale o OpenSSL executando `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-150">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="3d3b0-151">Vincule as bibliotecas para disponibilizá-las para o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-151">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="3d3b0-152">Desinstalação do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="3d3b0-152">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="3d3b0-153">Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-153">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="3d3b0-154">Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-154">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="3d3b0-155">Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-155">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="3d3b0-156">Isso não é necessário se você tiver instalado usando o Homebrew.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-156">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="3d3b0-157">Caminhos</span><span class="sxs-lookup"><span data-stu-id="3d3b0-157">Paths</span></span>

* <span data-ttu-id="3d3b0-158">`$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-158">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="3d3b0-159">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-159">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="3d3b0-160">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-160">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="3d3b0-161">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-161">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="3d3b0-162">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-162">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="3d3b0-163">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-163">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="3d3b0-164">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="3d3b0-164">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="3d3b0-165">Os perfis respeitam a configuração por host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-165">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="3d3b0-166">Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-166">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="3d3b0-167">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-167">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="3d3b0-168">Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-168">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="3d3b0-169">Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-169">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d3b0-170">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3d3b0-170">Additional Resources</span></span>

* <span data-ttu-id="3d3b0-171">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="3d3b0-171">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="3d3b0-172">[Repositório do Homebrew no Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="3d3b0-172">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="3d3b0-173">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="3d3b0-173">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[lançamentos]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
