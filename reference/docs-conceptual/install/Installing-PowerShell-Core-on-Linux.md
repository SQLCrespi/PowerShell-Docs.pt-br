---
title: Instalar o PowerShell Core no Linux
description: Informações sobre a instalação do PowerShell Core em diversas distribuições Linux
ms.date: 07/19/2019
ms.openlocfilehash: fc5a278f0fc10733a0d60fb856d0400332ba2719
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72350205"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="effe9-103">Instalar o PowerShell Core no Linux</span><span class="sxs-lookup"><span data-stu-id="effe9-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="effe9-104">É compatível com [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] e [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="effe9-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8],  [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="effe9-105">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="effe9-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="effe9-106">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="effe9-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="effe9-107">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="effe9-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="effe9-108">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="effe9-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="effe9-109">Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="effe9-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="effe9-110">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="effe9-110">Installing Preview Releases</span></span>

<span data-ttu-id="effe9-111">Ao instalar uma versão prévia do PowerShell Core para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="effe9-111">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="effe9-112">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="effe9-112">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="effe9-113">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="effe9-113">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="effe9-114">Distribuições</span><span class="sxs-lookup"><span data-stu-id="effe9-114">Distribution(s)</span></span>|<span data-ttu-id="effe9-115">Comando estável</span><span class="sxs-lookup"><span data-stu-id="effe9-115">Stable Command</span></span> | <span data-ttu-id="effe9-116">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="effe9-116">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="effe9-117">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="effe9-117">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="effe9-118">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="effe9-118">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="effe9-119">Fedora</span><span class="sxs-lookup"><span data-stu-id="effe9-119">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="effe9-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="effe9-120">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="effe9-121">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="effe9-121">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="effe9-122">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-122">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="effe9-123">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="effe9-123">The preferred method is as follows:</span></span>

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

<span data-ttu-id="effe9-124">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-124">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-125">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-125">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="effe9-126">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="effe9-126">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="effe9-127">Baixe o pacote Debian `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="effe9-127">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="effe9-128">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-128">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="effe9-129">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="effe9-129">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="effe9-130">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="effe9-130">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="effe9-131">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="effe9-131">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="effe9-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="effe9-132">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="effe9-133">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="effe9-133">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="effe9-134">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-134">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="effe9-135">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="effe9-135">The preferred method is as follows:</span></span>

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

<span data-ttu-id="effe9-136">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-136">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-137">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-137">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="effe9-138">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="effe9-138">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="effe9-139">Baixe o pacote Debian `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="effe9-139">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="effe9-140">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-140">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="effe9-141">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="effe9-141">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="effe9-142">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="effe9-142">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="effe9-143">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="effe9-143">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="effe9-144">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="effe9-144">Ubuntu 18.10</span></span>

<span data-ttu-id="effe9-145">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="effe9-145">Installation is supported via `snapd`.</span></span> <span data-ttu-id="effe9-146">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="effe9-146">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-147">O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="effe9-147">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="effe9-148">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="effe9-148">Ubuntu 19.04</span></span>

<span data-ttu-id="effe9-149">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="effe9-149">Installation is supported via `snapd`.</span></span> <span data-ttu-id="effe9-150">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="effe9-150">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-151">O Ubuntu 19.04 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="effe9-151">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="effe9-152">Debian 8</span><span class="sxs-lookup"><span data-stu-id="effe9-152">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="effe9-153">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="effe9-153">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="effe9-154">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-154">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="effe9-155">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="effe9-155">The preferred method is as follows:</span></span>

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

<span data-ttu-id="effe9-156">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-156">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-157">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-157">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="effe9-158">Debian 9</span><span class="sxs-lookup"><span data-stu-id="effe9-158">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="effe9-159">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="effe9-159">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="effe9-160">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-160">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="effe9-161">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="effe9-161">The preferred method is as follows:</span></span>

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

<span data-ttu-id="effe9-162">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-162">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-163">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-163">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="effe9-164">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="effe9-164">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="effe9-165">Baixe o pacote Debian `powershell_6.2.0-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="effe9-165">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="effe9-166">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-166">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="effe9-167">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="effe9-167">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="effe9-168">Debian 10</span><span class="sxs-lookup"><span data-stu-id="effe9-168">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-169">O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="effe9-169">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="effe9-170">Instalação por meio de download direto – Debian 10</span><span class="sxs-lookup"><span data-stu-id="effe9-170">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="effe9-171">Baixe o pacote tar.gz `powershell_7.0.0-preview-7-linux-x64.tar.gz` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="effe9-171">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="effe9-172">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-172">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="effe9-173">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="effe9-173">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-174">As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="effe9-174">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="effe9-175">Instalação por meio de download direto – Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="effe9-175">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="effe9-176">Baixe o pacote tar.gz `powershell_7.0.0-preview-7-linux-x64.tar.gz` da página [versões][] no computador Alpine.</span><span class="sxs-lookup"><span data-stu-id="effe9-176">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="effe9-177">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-177">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="centos-7"></a><span data-ttu-id="effe9-178">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="effe9-178">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-179">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="effe9-179">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="effe9-180">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="effe9-180">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="effe9-181">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-181">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="effe9-182">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-182">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-183">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-183">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="effe9-184">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="effe9-184">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="effe9-185">Usando o [CentOS 7][], baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="effe9-185">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="effe9-186">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-186">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="effe9-187">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="effe9-187">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="effe9-188">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="effe9-188">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="effe9-190">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="effe9-190">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="effe9-191">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="effe9-191">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="effe9-192">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-192">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="effe9-193">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="effe9-193">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="effe9-194">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="effe9-194">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="effe9-195">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="effe9-195">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="effe9-196">Baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="effe9-196">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="effe9-197">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-197">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="effe9-198">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="effe9-198">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="effe9-199">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="effe9-199">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="effe9-200">openSUSE</span><span class="sxs-lookup"><span data-stu-id="effe9-200">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="effe9-201">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="effe9-201">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="effe9-202">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="effe9-202">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="effe9-203">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="effe9-203">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="effe9-204">Fedora</span><span class="sxs-lookup"><span data-stu-id="effe9-204">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-205">O Fedora 28 é compatível apenas com o PowerShell Core 6.1 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="effe9-205">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-206">As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="effe9-206">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="effe9-207">Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="effe9-207">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="effe9-208">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-208">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="effe9-209">Instalação por meio de download direto – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="effe9-209">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="effe9-210">Baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="effe9-210">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="effe9-211">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="effe9-211">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="effe9-212">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="effe9-212">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="effe9-213">Desinstalação – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="effe9-213">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="effe9-214">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="effe9-214">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-215">O suporte para o Arch é experimental.</span><span class="sxs-lookup"><span data-stu-id="effe9-215">Arch support is experimental.</span></span>

<span data-ttu-id="effe9-216">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="effe9-216">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="effe9-217">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="effe9-217">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="effe9-218">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="effe9-218">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="effe9-219">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="effe9-219">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="effe9-220">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="effe9-220">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="effe9-221">Para obter mais informações sobre a instalação de pacotes usando o AUR, veja a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou a comunidade [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="effe9-221">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="effe9-223">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="effe9-223">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="effe9-224">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="effe9-224">Getting snapd</span></span>

<span data-ttu-id="effe9-225">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="effe9-225">`snapd` is required to run snaps.</span></span> <span data-ttu-id="effe9-226">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="effe9-226">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="effe9-227">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="effe9-227">Installation via Snap</span></span>

<span data-ttu-id="effe9-228">O PowerShell Core para Linux é publicado na [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="effe9-228">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="effe9-229">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="effe9-229">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="effe9-230">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="effe9-230">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="effe9-231">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="effe9-231">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="effe9-232">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="effe9-232">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="effe9-233">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="effe9-233">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="effe9-234">ou</span><span class="sxs-lookup"><span data-stu-id="effe9-234">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="effe9-235">Kali</span><span class="sxs-lookup"><span data-stu-id="effe9-235">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="effe9-236">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="effe9-236">Installation - Kali</span></span>

```sh
# Download & Install prerequisites
wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu57_57.1-6+deb9u2_amd64.deb
dpkg -i libicu57_57.1-6+deb9u2_amd64.deb
apt-get update && apt-get install -y curl gnupg apt-transport-https

# Add Microsoft public repository key to APT
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

# Add Microsoft package repository to the source list
echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" | tee /etc/apt/sources.list.d/powershell.list

# Install PowerShell package
apt-get update && apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="effe9-237">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="effe9-237">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="effe9-238">Raspbian</span><span class="sxs-lookup"><span data-stu-id="effe9-238">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="effe9-239">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="effe9-239">Raspbian support is experimental.</span></span>

<span data-ttu-id="effe9-240">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="effe9-240">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="effe9-241">O CoreCLR e o PowerShell Core funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="effe9-241">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="effe9-242">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="effe9-242">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="effe9-243">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="effe9-243">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.2.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="effe9-244">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="effe9-244">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="effe9-245">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="effe9-245">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="effe9-246">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="effe9-246">Binary Archives</span></span>

<span data-ttu-id="effe9-247">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="effe9-247">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="effe9-248">Dependências</span><span class="sxs-lookup"><span data-stu-id="effe9-248">Dependencies</span></span>

<span data-ttu-id="effe9-249">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="effe9-249">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="effe9-250">Porém o tempo de execução do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="effe9-250">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="effe9-251">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="effe9-251">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="effe9-252">SO</span><span class="sxs-lookup"><span data-stu-id="effe9-252">OS</span></span>                 | <span data-ttu-id="effe9-253">Dependências</span><span class="sxs-lookup"><span data-stu-id="effe9-253">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="effe9-254">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="effe9-254">Ubuntu 16.04</span></span>       | <span data-ttu-id="effe9-255">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="effe9-255">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="effe9-256">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="effe9-256">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="effe9-257">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="effe9-257">Ubuntu 17.10</span></span>       | <span data-ttu-id="effe9-258">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="effe9-258">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="effe9-259">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="effe9-259">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="effe9-260">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="effe9-260">Ubuntu 18.04</span></span>       | <span data-ttu-id="effe9-261">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="effe9-261">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="effe9-262">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="effe9-262">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="effe9-263">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="effe9-263">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="effe9-264">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="effe9-264">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="effe9-265">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="effe9-265">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="effe9-266">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="effe9-266">Debian 9 (Stretch)</span></span> | <span data-ttu-id="effe9-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="effe9-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="effe9-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="effe9-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="effe9-269">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="effe9-269">CentOS 7</span></span> <br> <span data-ttu-id="effe9-270">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="effe9-270">Oracle Linux 7</span></span> <br> <span data-ttu-id="effe9-271">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="effe9-271">RHEL 7</span></span> | <span data-ttu-id="effe9-272">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="effe9-272">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="effe9-273">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="effe9-273">openSUSE 42.3</span></span> | <span data-ttu-id="effe9-274">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="effe9-274">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="effe9-275">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="effe9-275">openSUSE Leap 15</span></span> | <span data-ttu-id="effe9-276">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="effe9-276">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="effe9-277">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="effe9-277">Fedora 27</span></span> <br> <span data-ttu-id="effe9-278">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="effe9-278">Fedora 28</span></span> | <span data-ttu-id="effe9-279">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="effe9-279">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="effe9-280">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="effe9-280">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="effe9-281">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="effe9-281">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="effe9-282">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="effe9-282">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="effe9-283">Linux</span><span class="sxs-lookup"><span data-stu-id="effe9-283">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="effe9-284">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="effe9-284">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="effe9-285">Caminhos</span><span class="sxs-lookup"><span data-stu-id="effe9-285">Paths</span></span>

* <span data-ttu-id="effe9-286">`$PSHOME` é `/opt/microsoft/powershell/6.2.0/`</span><span class="sxs-lookup"><span data-stu-id="effe9-286">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="effe9-287">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="effe9-287">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="effe9-288">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="effe9-288">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="effe9-289">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="effe9-289">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="effe9-290">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="effe9-290">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="effe9-291">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="effe9-291">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="effe9-292">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="effe9-292">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="effe9-293">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="effe9-293">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="effe9-294">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="effe9-294">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
