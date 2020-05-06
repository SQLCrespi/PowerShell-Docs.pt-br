---
title: Instalar o PowerShell no Linux
description: Informações sobre como instalar o PowerShell em várias distribuições do Linux
ms.date: 03/09/2020
ms.openlocfilehash: 6ad637bd30e5e40ccc9532bae6f1171ecf79734a
ms.sourcegitcommit: e0a737961280026832cff9c658ed1468dc904e80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "82605842"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="e6b55-103">Instalar o PowerShell no Linux</span><span class="sxs-lookup"><span data-stu-id="e6b55-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="e6b55-104">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="e6b55-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="e6b55-105">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="e6b55-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="e6b55-106">Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="e6b55-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-107">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="e6b55-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="e6b55-108">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="e6b55-109">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="e6b55-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="e6b55-110">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="e6b55-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="e6b55-111">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="e6b55-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="e6b55-112">Versões com suporte oficial</span><span class="sxs-lookup"><span data-stu-id="e6b55-112">Officially supported releases</span></span>

- <span data-ttu-id="e6b55-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="e6b55-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="e6b55-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="e6b55-115">Debian 8</span></span>
- <span data-ttu-id="e6b55-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="e6b55-116">Debian 9</span></span>
- <span data-ttu-id="e6b55-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e6b55-117">Debian 10</span></span>
- <span data-ttu-id="e6b55-118">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="e6b55-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-119">CentOS 7</span></span>
- <span data-ttu-id="e6b55-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="e6b55-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="e6b55-121">Fedora 28</span></span>
- <span data-ttu-id="e6b55-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="e6b55-122">Fedora 29</span></span>
- <span data-ttu-id="e6b55-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="e6b55-123">Fedora 30</span></span>
- <span data-ttu-id="e6b55-124">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e6b55-124">openSUSE 42.3</span></span>
- <span data-ttu-id="e6b55-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e6b55-125">openSUSE Leap 15</span></span>

<span data-ttu-id="e6b55-126">Versões com suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="e6b55-126">Community supported releases</span></span>

- <span data-ttu-id="e6b55-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="e6b55-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="e6b55-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="e6b55-129">Arch Linux</span></span>
- <span data-ttu-id="e6b55-130">Kali</span><span class="sxs-lookup"><span data-stu-id="e6b55-130">Kali</span></span>
- <span data-ttu-id="e6b55-131">Raspbian (experimental)</span><span class="sxs-lookup"><span data-stu-id="e6b55-131">Raspbian (experimental)</span></span>

<span data-ttu-id="e6b55-132">Métodos de instalação alternativos</span><span class="sxs-lookup"><span data-stu-id="e6b55-132">Alternate install methods</span></span>

- <span data-ttu-id="e6b55-133">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="e6b55-133">Snap Package</span></span>
- <span data-ttu-id="e6b55-134">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="e6b55-134">Binary Archives</span></span>
- <span data-ttu-id="e6b55-135">Ferramenta .NET Global</span><span class="sxs-lookup"><span data-stu-id="e6b55-135">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="e6b55-136">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-136">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="e6b55-137">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-137">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="e6b55-138">O PowerShell Core Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-138">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-139">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-139">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e6b55-140">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-140">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-141">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-141">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="e6b55-142">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-142">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="e6b55-143">Baixe o pacote Debian `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e6b55-143">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="e6b55-144">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-144">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="e6b55-145">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="e6b55-145">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="e6b55-146">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6b55-146">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="e6b55-147">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-147">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="e6b55-148">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-148">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="e6b55-149">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-149">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="e6b55-150">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-150">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-151">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-151">The preferred method is as follows:</span></span>

```sh
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

<span data-ttu-id="e6b55-152">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-152">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-153">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-153">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="e6b55-154">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-154">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="e6b55-155">Baixe o pacote Debian `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e6b55-155">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="e6b55-156">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-156">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="e6b55-157">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="e6b55-157">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="e6b55-158">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6b55-158">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="e6b55-159">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-159">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="e6b55-160">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-160">Ubuntu 18.10</span></span>

<span data-ttu-id="e6b55-161">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-161">Installation is supported via `snapd`.</span></span> <span data-ttu-id="e6b55-162">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="e6b55-162">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-163">O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="e6b55-163">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="e6b55-164">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-164">Ubuntu 19.04</span></span>

<span data-ttu-id="e6b55-165">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-165">Installation is supported via `snapd`.</span></span> <span data-ttu-id="e6b55-166">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="e6b55-166">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-167">O Ubuntu 19.04 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="e6b55-167">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="e6b55-168">Debian 8</span><span class="sxs-lookup"><span data-stu-id="e6b55-168">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="e6b55-169">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="e6b55-169">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="e6b55-170">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-170">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-171">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-171">The preferred method is as follows:</span></span>

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

<span data-ttu-id="e6b55-172">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-172">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-173">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-173">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="e6b55-174">Debian 9</span><span class="sxs-lookup"><span data-stu-id="e6b55-174">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="e6b55-175">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="e6b55-175">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="e6b55-176">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-176">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-177">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-177">The preferred method is as follows:</span></span>

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

<span data-ttu-id="e6b55-178">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-178">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-179">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-179">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="e6b55-180">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="e6b55-180">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="e6b55-181">Baixe o pacote Debian `powershell-lts_7.0.0-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="e6b55-181">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="e6b55-182">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-182">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="e6b55-183">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="e6b55-183">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="e6b55-184">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e6b55-184">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-185">O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e6b55-185">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="e6b55-186">Instalação por meio do repositório de pacotes – Debian 10</span><span class="sxs-lookup"><span data-stu-id="e6b55-186">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="e6b55-187">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-188">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-188">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="e6b55-189">Instalação por meio de download direto – Debian 10</span><span class="sxs-lookup"><span data-stu-id="e6b55-189">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="e6b55-190">Baixe o pacote tar.gz `powershell_7.0.0-linux-x64.tar.gz` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="e6b55-190">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="e6b55-191">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-191">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="e6b55-192">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-192">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-193">As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e6b55-193">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="e6b55-194">Instalação por meio de download direto – Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-194">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="e6b55-195">Baixe o pacote tar.gz `powershell-7.0.0-linux-alpine-x64.tar.gz` da página [versões][] no computador Alpine.</span><span class="sxs-lookup"><span data-stu-id="e6b55-195">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="e6b55-196">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-196">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="e6b55-197">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-197">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-198">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="e6b55-198">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="e6b55-199">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-199">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="e6b55-200">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-200">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e6b55-201">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-201">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-202">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-202">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="e6b55-203">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-203">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="e6b55-204">Usando o [CentOS 7][], baixe o pacote RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="e6b55-204">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="e6b55-205">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-205">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e6b55-206">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="e6b55-206">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="e6b55-207">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-207">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e6b55-209">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-209">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e6b55-210">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-210">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="e6b55-211">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e6b55-212">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="e6b55-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e6b55-213">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e6b55-214">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-214">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="e6b55-215">Baixe o pacote RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="e6b55-215">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="e6b55-216">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e6b55-217">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="e6b55-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e6b55-218">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-218">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="e6b55-219">openSUSE</span><span class="sxs-lookup"><span data-stu-id="e6b55-219">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="e6b55-220">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e6b55-220">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="e6b55-221">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="e6b55-221">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="e6b55-222">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e6b55-222">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="e6b55-223">Fedora</span><span class="sxs-lookup"><span data-stu-id="e6b55-223">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-224">O Fedora 28 tem suporte apenas no PowerShell 6.1 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="e6b55-224">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-225">As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e6b55-225">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="e6b55-226">Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="e6b55-226">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="e6b55-227">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-227">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="e6b55-228">Instalação por meio de download direto – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="e6b55-228">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="e6b55-229">Baixe o pacote RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="e6b55-229">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="e6b55-230">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="e6b55-230">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e6b55-231">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="e6b55-231">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="e6b55-232">Desinstalação – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="e6b55-232">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="e6b55-233">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="e6b55-233">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-234">O suporte ao Arch não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="e6b55-234">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="e6b55-235">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="e6b55-235">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="e6b55-236">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="e6b55-236">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="e6b55-237">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="e6b55-237">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="e6b55-238">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="e6b55-238">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="e6b55-239">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="e6b55-239">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="e6b55-240">Para obter mais informações sobre a instalação de pacotes usando o AUR, confira a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou [Como usar o PowerShell no Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="e6b55-240">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="e6b55-242">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="e6b55-242">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="e6b55-243">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="e6b55-243">Getting snapd</span></span>

<span data-ttu-id="e6b55-244">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="e6b55-244">`snapd` is required to run snaps.</span></span> <span data-ttu-id="e6b55-245">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="e6b55-245">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="e6b55-246">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="e6b55-246">Installation via Snap</span></span>

<span data-ttu-id="e6b55-247">O PowerShell para Linux é publicado no [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="e6b55-247">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="e6b55-248">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6b55-248">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="e6b55-249">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="e6b55-249">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="e6b55-250">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6b55-250">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="e6b55-251">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-251">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="e6b55-252">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="e6b55-252">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="e6b55-253">ou</span><span class="sxs-lookup"><span data-stu-id="e6b55-253">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="e6b55-254">Kali</span><span class="sxs-lookup"><span data-stu-id="e6b55-254">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-255">O suporte ao Kali não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="e6b55-255">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="e6b55-256">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="e6b55-256">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="e6b55-257">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="e6b55-257">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="e6b55-258">Raspbian</span><span class="sxs-lookup"><span data-stu-id="e6b55-258">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="e6b55-259">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="e6b55-259">Raspbian support is experimental.</span></span>

<span data-ttu-id="e6b55-260">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="e6b55-260">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="e6b55-261">O CoreCLR e o PowerShell funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="e6b55-261">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="e6b55-262">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="e6b55-262">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="e6b55-263">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="e6b55-263">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="e6b55-264">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-264">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="e6b55-265">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="e6b55-265">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="e6b55-266">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="e6b55-266">Installing Preview Releases</span></span>

<span data-ttu-id="e6b55-267">Ao instalar uma versão prévia do PowerShell para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-267">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="e6b55-268">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e6b55-268">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="e6b55-269">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="e6b55-269">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="e6b55-270">Distribuições</span><span class="sxs-lookup"><span data-stu-id="e6b55-270">Distribution(s)</span></span> |            <span data-ttu-id="e6b55-271">Comando estável</span><span class="sxs-lookup"><span data-stu-id="e6b55-271">Stable Command</span></span>            |               <span data-ttu-id="e6b55-272">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="e6b55-272">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="e6b55-273">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="e6b55-273">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="e6b55-274">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="e6b55-274">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="e6b55-275">Fedora</span><span class="sxs-lookup"><span data-stu-id="e6b55-275">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="e6b55-276">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="e6b55-276">Install as a .NET Global tool</span></span>

<span data-ttu-id="e6b55-277">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="e6b55-277">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="e6b55-278">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-278">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="e6b55-279">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="e6b55-279">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="e6b55-280">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="e6b55-280">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="e6b55-281">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="e6b55-281">Binary Archives</span></span>

<span data-ttu-id="e6b55-282">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="e6b55-282">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="e6b55-283">Dependências</span><span class="sxs-lookup"><span data-stu-id="e6b55-283">Dependencies</span></span>

<span data-ttu-id="e6b55-284">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="e6b55-284">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="e6b55-285">Porém o runtime do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="e6b55-285">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="e6b55-286">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="e6b55-286">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="e6b55-287">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="e6b55-287">OS</span></span>                 | <span data-ttu-id="e6b55-288">Dependências</span><span class="sxs-lookup"><span data-stu-id="e6b55-288">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="e6b55-289">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-289">Ubuntu 16.04</span></span>       | <span data-ttu-id="e6b55-290">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="e6b55-290">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e6b55-291">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="e6b55-291">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="e6b55-292">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="e6b55-292">Ubuntu 17.10</span></span>       | <span data-ttu-id="e6b55-293">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="e6b55-293">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e6b55-294">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="e6b55-294">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="e6b55-295">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e6b55-295">Ubuntu 18.04</span></span>       | <span data-ttu-id="e6b55-296">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="e6b55-296">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e6b55-297">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="e6b55-297">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="e6b55-298">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="e6b55-298">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="e6b55-299">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="e6b55-299">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e6b55-300">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="e6b55-300">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="e6b55-301">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="e6b55-301">Debian 9 (Stretch)</span></span> | <span data-ttu-id="e6b55-302">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="e6b55-302">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e6b55-303">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="e6b55-303">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="e6b55-304">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-304">CentOS 7</span></span> <br> <span data-ttu-id="e6b55-305">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-305">Oracle Linux 7</span></span> <br> <span data-ttu-id="e6b55-306">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="e6b55-306">RHEL 7</span></span> | <span data-ttu-id="e6b55-307">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="e6b55-307">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="e6b55-308">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e6b55-308">openSUSE 42.3</span></span> | <span data-ttu-id="e6b55-309">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="e6b55-309">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="e6b55-310">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e6b55-310">openSUSE Leap 15</span></span> | <span data-ttu-id="e6b55-311">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="e6b55-311">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="e6b55-312">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="e6b55-312">Fedora 27</span></span> <br> <span data-ttu-id="e6b55-313">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="e6b55-313">Fedora 28</span></span> | <span data-ttu-id="e6b55-314">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="e6b55-314">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="e6b55-315">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="e6b55-315">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="e6b55-316">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="e6b55-316">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="e6b55-317">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="e6b55-317">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="e6b55-318">Linux</span><span class="sxs-lookup"><span data-stu-id="e6b55-318">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="e6b55-319">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="e6b55-319">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="e6b55-320">Caminhos</span><span class="sxs-lookup"><span data-stu-id="e6b55-320">Paths</span></span>

- <span data-ttu-id="e6b55-321">`$PSHOME` é `/opt/microsoft/powershell/7/`</span><span class="sxs-lookup"><span data-stu-id="e6b55-321">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="e6b55-322">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="e6b55-322">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="e6b55-323">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="e6b55-323">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="e6b55-324">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="e6b55-324">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e6b55-325">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="e6b55-325">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e6b55-326">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="e6b55-326">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="e6b55-327">O histórico do PSReadLine será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="e6b55-327">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="e6b55-328">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="e6b55-328">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="e6b55-329">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="e6b55-329">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
