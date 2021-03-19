---
title: Instalar o PowerShell no Linux
description: Informações sobre como instalar o PowerShell em várias distribuições do Linux
ms.date: 02/02/2021
ms.openlocfilehash: b093e3ff20772016139999836adc5ec1b7a18197
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483342"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="a497e-103">Instalar o PowerShell no Linux</span><span class="sxs-lookup"><span data-stu-id="a497e-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="a497e-104">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="a497e-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="a497e-105">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="a497e-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="a497e-106">Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="a497e-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-107">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="a497e-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="a497e-108">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="a497e-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="a497e-109">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="a497e-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="a497e-110">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="a497e-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="a497e-111">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="a497e-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

<span data-ttu-id="a497e-112">Versões de plataforma com suporte oficial para o PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="a497e-112">Officially supported platform releases for PowerShell 7.1</span></span>

- <span data-ttu-id="a497e-113">Ubuntu 16.04/18.04/20.04 (incluindo ARM64)</span><span class="sxs-lookup"><span data-stu-id="a497e-113">Ubuntu 16.04/18.04/20.04 (including ARM64)</span></span>
- <span data-ttu-id="a497e-114">Ubuntu 19.10 (via pacote Snap)</span><span class="sxs-lookup"><span data-stu-id="a497e-114">Ubuntu 19.10 (via Snap package)</span></span>
- <span data-ttu-id="a497e-115">Debian 9/10</span><span class="sxs-lookup"><span data-stu-id="a497e-115">Debian 9/10</span></span>
- <span data-ttu-id="a497e-116">CentOS e RHEL 7/8</span><span class="sxs-lookup"><span data-stu-id="a497e-116">CentOS and RHEL 7/8</span></span>
- <span data-ttu-id="a497e-117">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="a497e-117">Fedora 30</span></span>
- <span data-ttu-id="a497e-118">Alpine 3.11+ (incluindo ARM64)</span><span class="sxs-lookup"><span data-stu-id="a497e-118">Alpine 3.11+ (including ARM64)</span></span>

<span data-ttu-id="a497e-119">Versões de plataforma com suporte oficial para o PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="a497e-119">Officially supported platform releases for PowerShell 7.0</span></span>

- <span data-ttu-id="a497e-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-120">Ubuntu 16.04</span></span>
- <span data-ttu-id="a497e-121">Ubuntu 18.04 e 20.04</span><span class="sxs-lookup"><span data-stu-id="a497e-121">Ubuntu 18.04 and 20.04</span></span>
- <span data-ttu-id="a497e-122">Debian 8</span><span class="sxs-lookup"><span data-stu-id="a497e-122">Debian 8</span></span>
- <span data-ttu-id="a497e-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="a497e-123">Debian 9</span></span>
- <span data-ttu-id="a497e-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="a497e-124">Debian 10</span></span>
- <span data-ttu-id="a497e-125">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="a497e-125">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="a497e-126">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-126">CentOS 7</span></span>
- <span data-ttu-id="a497e-127">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="a497e-127">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="a497e-128">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="a497e-128">Fedora 28</span></span>
- <span data-ttu-id="a497e-129">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="a497e-129">Fedora 29</span></span>
- <span data-ttu-id="a497e-130">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="a497e-130">Fedora 30</span></span>
- <span data-ttu-id="a497e-131">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="a497e-131">openSUSE 42.3</span></span>
- <span data-ttu-id="a497e-132">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="a497e-132">openSUSE Leap 15</span></span>

<span data-ttu-id="a497e-133">Versões com suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="a497e-133">Community supported releases</span></span>

- <span data-ttu-id="a497e-134">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="a497e-134">Ubuntu 18.10</span></span>
- <span data-ttu-id="a497e-135">Ubuntu 19.10 e 20.10</span><span class="sxs-lookup"><span data-stu-id="a497e-135">Ubuntu 19.10 and 20.10</span></span>
- <span data-ttu-id="a497e-136">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="a497e-136">Arch Linux</span></span>
- <span data-ttu-id="a497e-137">Kali</span><span class="sxs-lookup"><span data-stu-id="a497e-137">Kali</span></span>
- <span data-ttu-id="a497e-138">Raspbian (experimental)</span><span class="sxs-lookup"><span data-stu-id="a497e-138">Raspbian (experimental)</span></span>

<span data-ttu-id="a497e-139">Métodos de instalação alternativos</span><span class="sxs-lookup"><span data-stu-id="a497e-139">Alternate install methods</span></span>

- <span data-ttu-id="a497e-140">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="a497e-140">Snap Package</span></span>
- <span data-ttu-id="a497e-141">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="a497e-141">Binary Archives</span></span>
- <span data-ttu-id="a497e-142">Ferramenta .NET Global</span><span class="sxs-lookup"><span data-stu-id="a497e-142">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="a497e-143">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-143">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="a497e-144">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-144">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="a497e-145">O PowerShell Core Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-145">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-146">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-146">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
sudo apt-get update
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-147">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-147">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-148">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-148">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="a497e-149">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-149">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="a497e-150">Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a497e-150">Download the Debian package `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="a497e-151">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-151">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="a497e-152">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="a497e-152">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="a497e-153">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a497e-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="a497e-154">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-154">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="a497e-155">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="a497e-155">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="a497e-156">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="a497e-156">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="a497e-157">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-158">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-158">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-159">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-160">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-160">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="a497e-161">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="a497e-161">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="a497e-162">Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a497e-162">Download the Debian package `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="a497e-163">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-163">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="a497e-164">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="a497e-164">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="a497e-165">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a497e-165">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="a497e-166">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="a497e-166">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a><span data-ttu-id="a497e-167">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="a497e-167">Ubuntu 20.04</span></span>

### <a name="installation-via-package-repository---ubuntu-2004"></a><span data-ttu-id="a497e-168">Instalação por meio do repositório de pacotes – Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="a497e-168">Installation via Package Repository - Ubuntu 20.04</span></span>

<span data-ttu-id="a497e-169">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-169">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-170">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-170">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-171">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-172">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-172">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-2004"></a><span data-ttu-id="a497e-173">Instalação por meio de download direto – Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="a497e-173">Installation via Direct Download - Ubuntu 20.04</span></span>

<span data-ttu-id="a497e-174">Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a497e-174">Download the Debian package `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="a497e-175">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="a497e-176">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="a497e-176">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="a497e-177">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a497e-177">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-2004"></a><span data-ttu-id="a497e-178">Desinstalação – Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="a497e-178">Uninstallation - Ubuntu 20.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="a497e-179">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="a497e-179">Ubuntu 18.10</span></span>

<span data-ttu-id="a497e-180">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="a497e-180">Installation is supported via `snapd`.</span></span> <span data-ttu-id="a497e-181">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="a497e-181">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-182">O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="a497e-182">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1910-and-2010"></a><span data-ttu-id="a497e-183">Ubuntu 19.10 e 20.10</span><span class="sxs-lookup"><span data-stu-id="a497e-183">Ubuntu 19.10 and 20.10</span></span>

<span data-ttu-id="a497e-184">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="a497e-184">Installation is supported via `snapd`.</span></span> <span data-ttu-id="a497e-185">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="a497e-185">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-186">O Ubuntu 19.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) que tem [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="a497e-186">Ubuntu 19.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="a497e-187">Debian 8</span><span class="sxs-lookup"><span data-stu-id="a497e-187">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="a497e-188">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="a497e-188">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="a497e-189">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-189">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-190">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-190">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-191">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-191">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-192">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-192">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="a497e-193">Debian 9</span><span class="sxs-lookup"><span data-stu-id="a497e-193">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="a497e-194">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="a497e-194">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="a497e-195">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-195">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-196">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-196">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-197">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-197">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-198">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-198">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="a497e-199">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="a497e-199">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="a497e-200">Baixe o pacote Debian `powershell_7.1.3-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="a497e-200">Download the Debian package `powershell_7.1.3-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="a497e-201">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-201">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="a497e-202">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="a497e-202">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="a497e-203">Debian 10</span><span class="sxs-lookup"><span data-stu-id="a497e-203">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-204">O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="a497e-204">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="a497e-205">Instalação por meio do repositório de pacotes – Debian 10</span><span class="sxs-lookup"><span data-stu-id="a497e-205">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="a497e-206">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-206">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="a497e-207">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-207">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="a497e-208">Instalação por meio de download direto – Debian 10</span><span class="sxs-lookup"><span data-stu-id="a497e-208">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="a497e-209">Baixe o pacote tar.gz `powershell-7.1.3-linux-x64.tar.gz` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="a497e-209">Download the tar.gz package `powershell-7.1.3-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="a497e-210">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-210">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo apt-get update
# install the requirements
sudo apt-get install -y \
        less \
        locales \
        ca-certificates \
        libicu63 \
        libssl1.1 \
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        liblttng-ust0 \
        libstdc++6 \
        zlib1g \
        curl

# Download the powershell '.tar.gz' archive
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="a497e-211">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="a497e-211">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-212">As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="a497e-212">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="a497e-213">Instalação por meio de download direto – Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="a497e-213">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="a497e-214">Baixe o pacote tar.gz `powershell-7.1.3-linux-alpine-x64.tar.gz` da página [versões][] no computador Alpine.</span><span class="sxs-lookup"><span data-stu-id="a497e-214">Download the tar.gz package `powershell-7.1.3-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="a497e-215">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-215">Then, in the terminal, execute the following commands:</span></span>

```sh
# install the requirements
sudo apk add --no-cache \
    ca-certificates \
    less \
    ncurses-terminfo-base \
    krb5-libs \
    libgcc \
    libintl \
    libssl1.1 \
    libstdc++ \
    tzdata \
    userspace-rcu \
    zlib \
    icu-libs \
    curl

sudo apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache \
    lttng-ust

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="centos-7"></a><span data-ttu-id="a497e-216">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-216">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-217">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="a497e-217">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="a497e-218">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-218">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="a497e-219">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-219">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-220">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-220">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-221">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-221">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="a497e-222">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-222">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="a497e-223">Usando o [CentOS 7][], baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="a497e-223">Using [CentOS 7][], download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="a497e-224">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-224">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="a497e-225">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="a497e-225">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="a497e-226">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-226">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="a497e-228">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="a497e-228">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="a497e-229">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="a497e-229">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="a497e-230">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-230">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-231">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="a497e-231">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="a497e-232">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="a497e-232">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="a497e-233">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="a497e-233">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="a497e-234">Baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-234">Download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="a497e-235">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-235">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="a497e-236">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="a497e-236">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="a497e-237">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="a497e-237">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="a497e-238">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a497e-238">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="a497e-239">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="a497e-239">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="a497e-240">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="a497e-240">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="a497e-241">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="a497e-241">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="a497e-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="a497e-242">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-243">O Fedora 28 tem suporte apenas no PowerShell 6.1 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="a497e-243">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-244">As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="a497e-244">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="a497e-245">Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="a497e-245">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="a497e-246">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-246">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf check-update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="a497e-247">Instalação por meio de download direto – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="a497e-247">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="a497e-248">Baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="a497e-248">Download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="a497e-249">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="a497e-249">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="a497e-250">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="a497e-250">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="a497e-251">Desinstalação – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="a497e-251">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="a497e-252">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="a497e-252">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-253">O suporte ao Arch não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="a497e-253">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="a497e-254">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="a497e-254">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="a497e-255">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="a497e-255">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="a497e-256">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="a497e-256">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="a497e-257">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="a497e-257">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="a497e-258">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="a497e-258">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="a497e-259">Para obter mais informações sobre a instalação de pacotes usando o AUR, confira a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou [Como usar o PowerShell no Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="a497e-259">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="a497e-261">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="a497e-261">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="a497e-262">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="a497e-262">Getting snapd</span></span>

<span data-ttu-id="a497e-263">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="a497e-263">`snapd` is required to run snaps.</span></span> <span data-ttu-id="a497e-264">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="a497e-264">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="a497e-265">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="a497e-265">Installation via Snap</span></span>

<span data-ttu-id="a497e-266">O PowerShell para Linux é publicado no [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a497e-266">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="a497e-267">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a497e-267">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="a497e-268">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="a497e-268">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="a497e-269">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a497e-269">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="a497e-270">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="a497e-270">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="a497e-271">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="a497e-271">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="a497e-272">ou</span><span class="sxs-lookup"><span data-stu-id="a497e-272">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="a497e-273">Kali</span><span class="sxs-lookup"><span data-stu-id="a497e-273">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-274">O suporte ao Kali não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="a497e-274">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="a497e-275">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="a497e-275">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="a497e-276">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="a497e-276">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="support-for-arm-processors"></a><span data-ttu-id="a497e-277">Suporte para processadores ARM</span><span class="sxs-lookup"><span data-stu-id="a497e-277">Support for Arm processors</span></span>

<span data-ttu-id="a497e-278">O PowerShell pode ser instalado em algumas distribuições do Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-278">PowerShell can be installed on some Linux distributions.</span></span> <span data-ttu-id="a497e-279">O PowerShell depende do suporte .NET do ARM.</span><span class="sxs-lookup"><span data-stu-id="a497e-279">PowerShell is dependent on .NET support of Arm.</span></span> <span data-ttu-id="a497e-280">O PowerShell tem suporte nas seguintes distribuições:</span><span class="sxs-lookup"><span data-stu-id="a497e-280">PowerShell is supported on the following distributions:</span></span>

- <span data-ttu-id="a497e-281">Alpine Linux v3.11+: .NET dá suporte a Arm64, mas não há nenhum pacote instalável para o PowerShell no momento</span><span class="sxs-lookup"><span data-stu-id="a497e-281">Alpine Linux v3.11+ - .NET supports Arm64 but there is no installable package for PowerShell at this time</span></span>
- <span data-ttu-id="a497e-282">Raspbian: confira as instruções de instalação abaixo</span><span class="sxs-lookup"><span data-stu-id="a497e-282">Raspbian - see the installation instructions below</span></span>
- <span data-ttu-id="a497e-283">Debian v9+: dá suporte a Arm32 e Arm64 usando o método de instalação de [Arquivo Binário](#binary-archives)</span><span class="sxs-lookup"><span data-stu-id="a497e-283">Debian v9+ - supports Arm32 and Arm64 using the [Binary Archive](#binary-archives) installation method</span></span>
- <span data-ttu-id="a497e-284">Ubuntu 20.10, 20.04, 18.04, 16.04: dá suporte a Arm32 e Arm64 usando o método de instalação de [Arquivo Binário](#binary-archives)</span><span class="sxs-lookup"><span data-stu-id="a497e-284">Ubuntu 20.10, 20.04, 18.04, 16.04 - supports Arm32 and Arm64 using the [Binary Archive](#binary-archives) installation method</span></span>

## <a name="raspbian"></a><span data-ttu-id="a497e-285">Raspbian</span><span class="sxs-lookup"><span data-stu-id="a497e-285">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-286">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="a497e-286">Raspbian support is experimental.</span></span>

<span data-ttu-id="a497e-287">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="a497e-287">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="a497e-288">O CoreCLR e o PowerShell funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="a497e-288">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="a497e-289">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="a497e-289">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="a497e-290">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="a497e-290">Installation - Raspbian</span></span>

```sh
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
# Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="a497e-291">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="a497e-291">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="a497e-292">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="a497e-292">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="a497e-293">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="a497e-293">Installing Preview Releases</span></span>

<span data-ttu-id="a497e-294">Ao instalar uma versão prévia do PowerShell para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="a497e-294">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="a497e-295">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a497e-295">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="a497e-296">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="a497e-296">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="a497e-297">Distribuições</span><span class="sxs-lookup"><span data-stu-id="a497e-297">Distribution(s)</span></span> |            <span data-ttu-id="a497e-298">Comando estável</span><span class="sxs-lookup"><span data-stu-id="a497e-298">Stable Command</span></span>            |               <span data-ttu-id="a497e-299">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="a497e-299">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="a497e-300">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="a497e-300">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="a497e-301">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="a497e-301">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="a497e-302">Fedora</span><span class="sxs-lookup"><span data-stu-id="a497e-302">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="a497e-303">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="a497e-303">Install as a .NET Global tool</span></span>

<span data-ttu-id="a497e-304">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="a497e-304">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="a497e-305">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="a497e-305">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="a497e-306">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="a497e-306">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="a497e-307">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="a497e-307">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="a497e-308">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="a497e-308">Binary Archives</span></span>

<span data-ttu-id="a497e-309">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="a497e-309">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="a497e-310">Você pode usar esse método para instalar qualquer versão do PowerShell, incluindo a mais recente:</span><span class="sxs-lookup"><span data-stu-id="a497e-310">You can use this method to install any version of PowerShell including the latest:</span></span>
> - <span data-ttu-id="a497e-311">Versão estável: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span><span class="sxs-lookup"><span data-stu-id="a497e-311">Stable release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span></span>
> - <span data-ttu-id="a497e-312">Versão prévia: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span><span class="sxs-lookup"><span data-stu-id="a497e-312">Preview release: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span></span>
> - <span data-ttu-id="a497e-313">Versão LTS: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span><span class="sxs-lookup"><span data-stu-id="a497e-313">LTS release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span></span>

### <a name="dependencies"></a><span data-ttu-id="a497e-314">Dependências</span><span class="sxs-lookup"><span data-stu-id="a497e-314">Dependencies</span></span>

<span data-ttu-id="a497e-315">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-315">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="a497e-316">Porém o runtime do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="a497e-316">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="a497e-317">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-317">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="a497e-318">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="a497e-318">OS</span></span>                 | <span data-ttu-id="a497e-319">Dependências</span><span class="sxs-lookup"><span data-stu-id="a497e-319">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="a497e-320">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="a497e-320">Ubuntu 16.04</span></span>       | <span data-ttu-id="a497e-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="a497e-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="a497e-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="a497e-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="a497e-323">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="a497e-323">Ubuntu 17.10</span></span>       | <span data-ttu-id="a497e-324">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="a497e-324">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="a497e-325">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="a497e-325">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="a497e-326">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="a497e-326">Ubuntu 18.04</span></span>       | <span data-ttu-id="a497e-327">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="a497e-327">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="a497e-328">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="a497e-328">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="a497e-329">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="a497e-329">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="a497e-330">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="a497e-330">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="a497e-331">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="a497e-331">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="a497e-332">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="a497e-332">Debian 9 (Stretch)</span></span> | <span data-ttu-id="a497e-333">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="a497e-333">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="a497e-334">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="a497e-334">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="a497e-335">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a497e-335">CentOS 7</span></span> <br> <span data-ttu-id="a497e-336">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="a497e-336">Oracle Linux 7</span></span> <br> <span data-ttu-id="a497e-337">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="a497e-337">RHEL 7</span></span> | <span data-ttu-id="a497e-338">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="a497e-338">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="a497e-339">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="a497e-339">openSUSE 42.3</span></span> | <span data-ttu-id="a497e-340">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="a497e-340">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="a497e-341">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="a497e-341">openSUSE Leap 15</span></span> | <span data-ttu-id="a497e-342">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="a497e-342">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="a497e-343">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="a497e-343">Fedora 27</span></span> <br> <span data-ttu-id="a497e-344">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="a497e-344">Fedora 28</span></span> | <span data-ttu-id="a497e-345">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="a497e-345">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="a497e-346">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="a497e-346">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="a497e-347">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-347">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="a497e-348">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="a497e-348">Installation - Binary Archives</span></span>

<span data-ttu-id="a497e-349">O seguinte exemplo mostra as etapas para instalar o arquivo binário x64.</span><span class="sxs-lookup"><span data-stu-id="a497e-349">The following example shows the steps for installing the x64 binary archive.</span></span> <span data-ttu-id="a497e-350">Você deve escolher o arquivo binário correto correspondente ao tipo de processador para sua plataforma.</span><span class="sxs-lookup"><span data-stu-id="a497e-350">You must choose the correct binary archive that matches the processor type for your platform.</span></span>

- <span data-ttu-id="a497e-351">powershell-7.1.3-linux-arm32.tar.gz</span><span class="sxs-lookup"><span data-stu-id="a497e-351">powershell-7.1.3-linux-arm32.tar.gz</span></span>
- <span data-ttu-id="a497e-352">powershell-7.1.3-linux-arm64.tar.gz</span><span class="sxs-lookup"><span data-stu-id="a497e-352">powershell-7.1.3-linux-arm64.tar.gz</span></span>
- <span data-ttu-id="a497e-353">powershell-7.1.3-linux-x64.tar.gz</span><span class="sxs-lookup"><span data-stu-id="a497e-353">powershell-7.1.3-linux-x64.tar.gz</span></span>

#### <a name="linux"></a><span data-ttu-id="a497e-354">Linux</span><span class="sxs-lookup"><span data-stu-id="a497e-354">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="a497e-355">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="a497e-355">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="a497e-356">Caminhos</span><span class="sxs-lookup"><span data-stu-id="a497e-356">Paths</span></span>

- <span data-ttu-id="a497e-357">`$PSHOME` é `/opt/microsoft/powershell/7/`</span><span class="sxs-lookup"><span data-stu-id="a497e-357">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="a497e-358">Os perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="a497e-358">User profiles are read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="a497e-359">Os perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="a497e-359">Default profiles are read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="a497e-360">Os módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="a497e-360">User modules are read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="a497e-361">Os módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="a497e-361">Shared modules are read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="a497e-362">Os módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="a497e-362">Default modules are read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="a497e-363">O histórico do PSReadLine será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="a497e-363">PSReadLine history is recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="a497e-364">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="a497e-364">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="a497e-365">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="a497e-365">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="a497e-366">Suporte à instalação</span><span class="sxs-lookup"><span data-stu-id="a497e-366">Installation support</span></span>

<span data-ttu-id="a497e-367">A Microsoft dá suporte aos métodos de instalação neste documento.</span><span class="sxs-lookup"><span data-stu-id="a497e-367">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="a497e-368">Pode haver outros métodos de instalação disponíveis de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="a497e-368">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="a497e-369">Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.</span><span class="sxs-lookup"><span data-stu-id="a497e-369">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[versões]: https://aka.ms/PowerShell-Release?tag=stable
[releases]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
