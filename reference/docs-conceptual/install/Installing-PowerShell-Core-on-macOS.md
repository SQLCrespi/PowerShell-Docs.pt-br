---
title: Instalar o PowerShell no macOS
description: Informações sobre a instalação do PowerShell no macOS
ms.date: 12/12/2018
ms.openlocfilehash: 7f0d6a1aa275deb39a7d670546ee7e833b8ef315
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78404820"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="9a41e-103">Instalar o PowerShell no macOS</span><span class="sxs-lookup"><span data-stu-id="9a41e-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="9a41e-104">O PowerShell oferece suporte para macOS 10.12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9a41e-104">PowerShell supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="9a41e-105">Todos os pacotes estão disponíveis na nossa página [lançamentos][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="9a41e-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="9a41e-106">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="9a41e-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="9a41e-107">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="9a41e-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="9a41e-108">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="9a41e-109">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="9a41e-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

## <a name="about-brew"></a><span data-ttu-id="9a41e-110">Sobre Brew</span><span class="sxs-lookup"><span data-stu-id="9a41e-110">About Brew</span></span>

<span data-ttu-id="9a41e-111">[Homebrew][brew] é o gerenciador de pacotes preferido para macOS.</span><span class="sxs-lookup"><span data-stu-id="9a41e-111">[Homebrew][brew] is the preferred package manager for macOS.</span></span> <span data-ttu-id="9a41e-112">Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].</span><span class="sxs-lookup"><span data-stu-id="9a41e-112">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span> <span data-ttu-id="9a41e-113">Caso contrário, você poderá instalar o PowerShell por [Download direto](#installation-via-direct-download) ou pelos [Arquivos binários](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="9a41e-113">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="9a41e-114">Instalação da versão estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="9a41e-114">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="9a41e-115">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="9a41e-115">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="9a41e-116">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a41e-116">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="9a41e-117">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="9a41e-117">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="9a41e-118">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a41e-118">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="9a41e-119">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-119">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="9a41e-120">Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.12 ou superior</span><span class="sxs-lookup"><span data-stu-id="9a41e-120">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="9a41e-121">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="9a41e-121">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="9a41e-122">Depois de instalar o Homebrew, você pode instalar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a41e-122">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="9a41e-123">Primeiro, instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:</span><span class="sxs-lookup"><span data-stu-id="9a41e-123">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="9a41e-124">Agora, você pode instalar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a41e-124">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="9a41e-125">Por fim, verifique se a instalação está funcionando corretamente:</span><span class="sxs-lookup"><span data-stu-id="9a41e-125">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="9a41e-126">Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a41e-126">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="9a41e-127">Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="9a41e-127">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="9a41e-128">e atualizar os valores mostrados em `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-128">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="9a41e-129">Instalação por meio de download direto</span><span class="sxs-lookup"><span data-stu-id="9a41e-129">Installation via Direct Download</span></span>

<span data-ttu-id="9a41e-130">Baixe o pacote PKG `powershell-6.2.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="9a41e-130">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="9a41e-131">na página [Lançamentos][] no computador com macOS.</span><span class="sxs-lookup"><span data-stu-id="9a41e-131">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="9a41e-132">Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:</span><span class="sxs-lookup"><span data-stu-id="9a41e-132">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="9a41e-133">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="9a41e-133">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="9a41e-134">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a41e-134">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="9a41e-135">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="9a41e-135">Install as a .NET Global tool</span></span>

<span data-ttu-id="9a41e-136">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="9a41e-136">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

## <a name="binary-archives"></a><span data-ttu-id="9a41e-137">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="9a41e-137">Binary Archives</span></span>

<span data-ttu-id="9a41e-138">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="9a41e-138">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="9a41e-139">Instalação de arquivos binários no macOS</span><span class="sxs-lookup"><span data-stu-id="9a41e-139">Installing binary archives on macOS</span></span>

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

<span data-ttu-id="9a41e-140">Instalar [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="9a41e-140">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="9a41e-141">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a41e-141">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="9a41e-142">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="9a41e-142">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="9a41e-143">Instalar ferramentas da linha de comando XCode</span><span class="sxs-lookup"><span data-stu-id="9a41e-143">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="9a41e-144">Instalar o OpenSSL</span><span class="sxs-lookup"><span data-stu-id="9a41e-144">Install OpenSSL</span></span>

<span data-ttu-id="9a41e-145">O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a41e-145">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="9a41e-146">Você pode instalar por meio de MacPorts ou Brew.</span><span class="sxs-lookup"><span data-stu-id="9a41e-146">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="9a41e-147">Instalar o OpenSSL por meio de Brew</span><span class="sxs-lookup"><span data-stu-id="9a41e-147">Install OpenSSL via Brew</span></span>

<span data-ttu-id="9a41e-148">Confira [Sobre Brew](#about-brew) para obter mais informações sobre Brew.</span><span class="sxs-lookup"><span data-stu-id="9a41e-148">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="9a41e-149">Execute `brew install openssl` para instalar o OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="9a41e-149">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="9a41e-150">Instalar o OpenSSL por meio de MacPorts</span><span class="sxs-lookup"><span data-stu-id="9a41e-150">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="9a41e-151">Instale as [ferramentas da linha de comando XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="9a41e-151">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="9a41e-152">Instale MacPorts.</span><span class="sxs-lookup"><span data-stu-id="9a41e-152">Install MacPorts.</span></span>
   <span data-ttu-id="9a41e-153">Se precisar de instruções, confira o [guia de instalação](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="9a41e-153">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="9a41e-154">Atualize o MacPorts executando `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-154">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="9a41e-155">Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-155">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="9a41e-156">Instale o OpenSSL executando `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-156">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="9a41e-157">Vincule as bibliotecas para disponibilizá-las para o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a41e-157">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell"></a><span data-ttu-id="9a41e-158">Desinstalar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a41e-158">Uninstalling PowerShell</span></span>

<span data-ttu-id="9a41e-159">Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:</span><span class="sxs-lookup"><span data-stu-id="9a41e-159">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="9a41e-160">Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:</span><span class="sxs-lookup"><span data-stu-id="9a41e-160">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="9a41e-161">Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-161">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="9a41e-162">Isso não é necessário se você tiver instalado usando o Homebrew.</span><span class="sxs-lookup"><span data-stu-id="9a41e-162">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="9a41e-163">Caminhos</span><span class="sxs-lookup"><span data-stu-id="9a41e-163">Paths</span></span>

* <span data-ttu-id="9a41e-164">`$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`</span><span class="sxs-lookup"><span data-stu-id="9a41e-164">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="9a41e-165">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="9a41e-165">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="9a41e-166">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="9a41e-166">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="9a41e-167">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="9a41e-167">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="9a41e-168">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="9a41e-168">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="9a41e-169">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="9a41e-169">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="9a41e-170">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="9a41e-170">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="9a41e-171">Os perfis respeitam a configuração por host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a41e-171">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="9a41e-172">Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.</span><span class="sxs-lookup"><span data-stu-id="9a41e-172">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="9a41e-173">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.</span><span class="sxs-lookup"><span data-stu-id="9a41e-173">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="9a41e-174">Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-174">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="9a41e-175">Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/6.2.0/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="9a41e-175">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a41e-176">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9a41e-176">Additional Resources</span></span>

* <span data-ttu-id="9a41e-177">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="9a41e-177">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="9a41e-178">[Repositório do Homebrew no Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="9a41e-178">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="9a41e-179">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="9a41e-179">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[lançamentos]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
