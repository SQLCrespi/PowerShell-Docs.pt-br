---
title: Instalar o PowerShell Core no macOS
description: Informações sobre a instalação do PowerShell Core no macOS
ms.date: 12/12/2018
ms.openlocfilehash: 70f5d64aa8a697a9011d07fbcb2bb821463827e1
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229743"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="50398-103">Instalar o PowerShell Core no macOS</span><span class="sxs-lookup"><span data-stu-id="50398-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="50398-104">O PowerShell Core oferece suporte para macOS 10.12 e superior.</span><span class="sxs-lookup"><span data-stu-id="50398-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="50398-105">Todos os pacotes estão disponíveis na nossa página [lançamentos][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="50398-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="50398-106">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="50398-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="50398-107">Sobre Brew</span><span class="sxs-lookup"><span data-stu-id="50398-107">About Brew</span></span>

<span data-ttu-id="50398-108">[Homebrew][brew] é o gerenciador de pacotes preferido para macOS.</span><span class="sxs-lookup"><span data-stu-id="50398-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="50398-109">Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].</span><span class="sxs-lookup"><span data-stu-id="50398-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>
<span data-ttu-id="50398-110">Caso contrário, você poderá instalar o PowerShell por [Download direto](#installation-via-direct-download) ou pelos [Arquivos binários](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="50398-110">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="50398-111">Instalação da versão estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="50398-111">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="50398-112">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="50398-112">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="50398-113">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50398-113">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="50398-114">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="50398-114">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="50398-115">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50398-115">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="50398-116">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="50398-116">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="50398-117">Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="50398-117">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="50398-118">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="50398-118">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="50398-119">Depois de instalar o Homebrew, você pode instalar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50398-119">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="50398-120">Primeiro instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:</span><span class="sxs-lookup"><span data-stu-id="50398-120">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="50398-121">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50398-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="50398-122">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="50398-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="50398-123">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50398-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="50398-124">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="50398-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="50398-125">e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="50398-125">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="50398-126">Instalação por meio de download direto</span><span class="sxs-lookup"><span data-stu-id="50398-126">Installation via Direct Download</span></span>

<span data-ttu-id="50398-127">Baixe o pacote PKG `powershell-6.2.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="50398-127">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="50398-128">na página [Lançamentos][] no computador com macOS.</span><span class="sxs-lookup"><span data-stu-id="50398-128">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="50398-129">Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:</span><span class="sxs-lookup"><span data-stu-id="50398-129">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="50398-130">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="50398-130">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="50398-131">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50398-131">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="50398-132">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="50398-132">Binary Archives</span></span>

<span data-ttu-id="50398-133">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="50398-133">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="50398-134">Instalação de arquivos binários no macOS</span><span class="sxs-lookup"><span data-stu-id="50398-134">Installing binary archives on macOS</span></span>

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

<span data-ttu-id="50398-135">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="50398-135">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="50398-136">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50398-136">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="50398-137">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="50398-137">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="50398-138">Instalar ferramentas da linha de comando XCode</span><span class="sxs-lookup"><span data-stu-id="50398-138">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="50398-139">Instalar OpenSSL</span><span class="sxs-lookup"><span data-stu-id="50398-139">Install OpenSSL</span></span>

<span data-ttu-id="50398-140">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50398-140">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="50398-141">Você pode instalar por meio de MacPorts ou Brew.</span><span class="sxs-lookup"><span data-stu-id="50398-141">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="50398-142">Instalar o OpenSSL por meio de Brew</span><span class="sxs-lookup"><span data-stu-id="50398-142">Install OpenSSL via Brew</span></span>

<span data-ttu-id="50398-143">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="50398-143">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="50398-144">Execute `brew install openssl` para instalar o OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="50398-144">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="50398-145">Instalar o OpenSSL por meio de MacPorts</span><span class="sxs-lookup"><span data-stu-id="50398-145">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="50398-146">Instale as [ferramentas da linha de comando XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="50398-146">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="50398-147">Instale MacPorts.</span><span class="sxs-lookup"><span data-stu-id="50398-147">Install MacPorts.</span></span>
   <span data-ttu-id="50398-148">Se precisar de instruções, confira o [guia de instalação](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="50398-148">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="50398-149">Atualize o MacPorts executando `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="50398-149">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="50398-150">Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="50398-150">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="50398-151">Instale o OpenSSL executando `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="50398-151">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="50398-152">Vincule as bibliotecas para disponibilizá-las para o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50398-152">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="50398-153">Desinstalação do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="50398-153">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="50398-154">Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:</span><span class="sxs-lookup"><span data-stu-id="50398-154">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="50398-155">Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:</span><span class="sxs-lookup"><span data-stu-id="50398-155">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="50398-156">Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="50398-156">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="50398-157">Isso não é necessário se você tiver instalado usando o Homebrew.</span><span class="sxs-lookup"><span data-stu-id="50398-157">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="50398-158">Caminhos</span><span class="sxs-lookup"><span data-stu-id="50398-158">Paths</span></span>

* <span data-ttu-id="50398-159">`$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`</span><span class="sxs-lookup"><span data-stu-id="50398-159">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="50398-160">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="50398-160">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="50398-161">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="50398-161">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="50398-162">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="50398-162">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="50398-163">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="50398-163">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="50398-164">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="50398-164">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="50398-165">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="50398-165">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="50398-166">Os perfis respeitam a configuração por host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50398-166">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="50398-167">Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.</span><span class="sxs-lookup"><span data-stu-id="50398-167">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="50398-168">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.</span><span class="sxs-lookup"><span data-stu-id="50398-168">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="50398-169">Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`.</span><span class="sxs-lookup"><span data-stu-id="50398-169">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="50398-170">Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="50398-170">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50398-171">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="50398-171">Additional Resources</span></span>

* <span data-ttu-id="50398-172">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="50398-172">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="50398-173">[Repositório do Homebrew no Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="50398-173">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="50398-174">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="50398-174">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[lançamentos]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
