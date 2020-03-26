---
title: Instalar o PowerShell no Linux
description: Informações sobre como instalar o PowerShell em várias distribuições do Linux
ms.date: 03/09/2020
ms.openlocfilehash: 13b8583ed45f1201e61225b377112a59d2b26cb2
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082805"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="39615-103">Instalar o PowerShell no Linux</span><span class="sxs-lookup"><span data-stu-id="39615-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="39615-104">Dá suporte a [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [CentOS 7][cos], [RHEL (Red Hat Enterprise Linux) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] e [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="39615-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="39615-105">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="39615-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="39615-106">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="39615-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="39615-107">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="39615-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="39615-108">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="39615-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="39615-109">Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="39615-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="39615-110">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="39615-110">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="39615-111">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="39615-111">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="39615-112">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="39615-112">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[deb10]: #debian-10
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives


## <a name="installing-preview-releases"></a><span data-ttu-id="39615-113">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="39615-113">Installing Preview Releases</span></span>

<span data-ttu-id="39615-114">Ao instalar uma versão prévia do PowerShell para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="39615-114">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="39615-115">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="39615-115">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="39615-116">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="39615-116">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="39615-117">Distribuições</span><span class="sxs-lookup"><span data-stu-id="39615-117">Distribution(s)</span></span> |            <span data-ttu-id="39615-118">Comando estável</span><span class="sxs-lookup"><span data-stu-id="39615-118">Stable Command</span></span>            |               <span data-ttu-id="39615-119">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="39615-119">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="39615-120">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="39615-120">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="39615-121">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="39615-121">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="39615-122">Fedora</span><span class="sxs-lookup"><span data-stu-id="39615-122">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="ubuntu-1604"></a><span data-ttu-id="39615-123">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="39615-123">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="39615-124">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="39615-124">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="39615-125">O PowerShell Core Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-125">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="39615-126">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39615-126">The preferred method is as follows:</span></span>

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

<span data-ttu-id="39615-127">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-127">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-128">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-128">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="39615-129">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="39615-129">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="39615-130">Baixe o pacote Debian `powershell_7.0.0-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="39615-130">Download the Debian package `powershell_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="39615-131">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-131">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="39615-132">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="39615-132">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="39615-133">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39615-133">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="39615-134">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="39615-134">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="39615-135">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="39615-135">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="39615-136">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="39615-136">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="39615-137">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-137">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="39615-138">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39615-138">The preferred method is as follows:</span></span>

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

<span data-ttu-id="39615-139">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-139">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-140">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-140">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="39615-141">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="39615-141">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="39615-142">Baixe o pacote Debian `powershell_7.0.0-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="39615-142">Download the Debian package `powershell_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="39615-143">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-143">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="39615-144">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="39615-144">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="39615-145">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39615-145">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="39615-146">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="39615-146">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="39615-147">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="39615-147">Ubuntu 18.10</span></span>

<span data-ttu-id="39615-148">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="39615-148">Installation is supported via `snapd`.</span></span> <span data-ttu-id="39615-149">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="39615-149">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="39615-150">O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="39615-150">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="39615-151">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="39615-151">Ubuntu 19.04</span></span>

<span data-ttu-id="39615-152">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="39615-152">Installation is supported via `snapd`.</span></span> <span data-ttu-id="39615-153">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="39615-153">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="39615-154">O Ubuntu 19.04 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="39615-154">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="39615-155">Debian 8</span><span class="sxs-lookup"><span data-stu-id="39615-155">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="39615-156">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="39615-156">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="39615-157">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="39615-158">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39615-158">The preferred method is as follows:</span></span>

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

<span data-ttu-id="39615-159">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-160">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-160">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="39615-161">Debian 9</span><span class="sxs-lookup"><span data-stu-id="39615-161">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="39615-162">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="39615-162">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="39615-163">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-163">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="39615-164">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39615-164">The preferred method is as follows:</span></span>

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

<span data-ttu-id="39615-165">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-165">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-166">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-166">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="39615-167">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="39615-167">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="39615-168">Baixe o pacote Debian `powershell_7.0.0-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="39615-168">Download the Debian package `powershell_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="39615-169">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-169">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="39615-170">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="39615-170">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="39615-171">Debian 10</span><span class="sxs-lookup"><span data-stu-id="39615-171">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="39615-172">O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="39615-172">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="39615-173">Instalação por meio de download direto – Debian 10</span><span class="sxs-lookup"><span data-stu-id="39615-173">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="39615-174">Baixe o pacote tar.gz `powershell_7.0.0-linux-x64.tar.gz` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="39615-174">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="39615-175">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-175">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="39615-176">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="39615-176">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="39615-177">As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="39615-177">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="39615-178">Instalação por meio de download direto – Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="39615-178">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="39615-179">Baixe o pacote tar.gz `powershell-7.0.0-linux-alpine-x64.tar.gz` da página [versões][] no computador Alpine.</span><span class="sxs-lookup"><span data-stu-id="39615-179">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="39615-180">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-180">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="centos-7"></a><span data-ttu-id="39615-181">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="39615-181">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="39615-182">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="39615-182">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="39615-183">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="39615-183">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="39615-184">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-184">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="39615-185">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-185">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-186">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-186">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="39615-187">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="39615-187">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="39615-188">Usando o [CentOS 7][], baixe o pacote RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="39615-188">Using [CentOS 7][], download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="39615-189">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-189">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="39615-190">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="39615-190">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="39615-191">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="39615-191">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="39615-193">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="39615-193">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="39615-194">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="39615-194">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="39615-195">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-195">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="39615-196">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="39615-196">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="39615-197">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="39615-197">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="39615-198">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="39615-198">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="39615-199">Baixe o pacote RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="39615-199">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="39615-200">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-200">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="39615-201">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="39615-201">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="39615-202">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="39615-202">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="39615-203">openSUSE</span><span class="sxs-lookup"><span data-stu-id="39615-203">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="39615-204">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="39615-204">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="39615-205">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="39615-205">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="39615-206">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="39615-206">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="39615-207">Fedora</span><span class="sxs-lookup"><span data-stu-id="39615-207">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="39615-208">O Fedora 28 tem suporte apenas no PowerShell 6.1 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="39615-208">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="39615-209">As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="39615-209">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="39615-210">Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="39615-210">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="39615-211">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="39615-212">Instalação por meio de download direto – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="39615-212">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="39615-213">Baixe o pacote RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="39615-213">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="39615-214">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="39615-214">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="39615-215">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="39615-215">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="39615-216">Desinstalação – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="39615-216">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="39615-217">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="39615-217">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="39615-218">O suporte ao Arch não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="39615-218">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="39615-219">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="39615-219">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="39615-220">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="39615-220">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="39615-221">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="39615-221">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="39615-222">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="39615-222">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="39615-223">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="39615-223">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="39615-224">Para obter mais informações sobre a instalação de pacotes usando o AUR, veja a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou a comunidade [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="39615-224">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="39615-226">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="39615-226">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="39615-227">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="39615-227">Getting snapd</span></span>

<span data-ttu-id="39615-228">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="39615-228">`snapd` is required to run snaps.</span></span> <span data-ttu-id="39615-229">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="39615-229">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="39615-230">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="39615-230">Installation via Snap</span></span>

<span data-ttu-id="39615-231">O PowerShell para Linux é publicado no [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39615-231">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="39615-232">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39615-232">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="39615-233">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="39615-233">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="39615-234">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="39615-234">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="39615-235">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="39615-235">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="39615-236">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="39615-236">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="39615-237">ou</span><span class="sxs-lookup"><span data-stu-id="39615-237">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="39615-238">Kali</span><span class="sxs-lookup"><span data-stu-id="39615-238">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="39615-239">O suporte ao Kali não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="39615-239">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="39615-240">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="39615-240">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="39615-241">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="39615-241">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="39615-242">Raspbian</span><span class="sxs-lookup"><span data-stu-id="39615-242">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="39615-243">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="39615-243">Raspbian support is experimental.</span></span>

<span data-ttu-id="39615-244">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="39615-244">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="39615-245">O CoreCLR e o PowerShell funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="39615-245">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="39615-246">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="39615-246">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="39615-247">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="39615-247">Installation - Raspbian</span></span>

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

<span data-ttu-id="39615-248">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="39615-248">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="39615-249">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="39615-249">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="39615-250">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="39615-250">Install as a .NET Global tool</span></span>

<span data-ttu-id="39615-251">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="39615-251">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="39615-252">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="39615-252">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="39615-253">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="39615-253">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="39615-254">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="39615-254">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="39615-255">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="39615-255">Binary Archives</span></span>

<span data-ttu-id="39615-256">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="39615-256">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="39615-257">Dependências</span><span class="sxs-lookup"><span data-stu-id="39615-257">Dependencies</span></span>

<span data-ttu-id="39615-258">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="39615-258">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="39615-259">Porém o runtime do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="39615-259">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="39615-260">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="39615-260">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="39615-261">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="39615-261">OS</span></span>                 | <span data-ttu-id="39615-262">Dependências</span><span class="sxs-lookup"><span data-stu-id="39615-262">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="39615-263">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="39615-263">Ubuntu 16.04</span></span>       | <span data-ttu-id="39615-264">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="39615-264">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="39615-265">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="39615-265">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="39615-266">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="39615-266">Ubuntu 17.10</span></span>       | <span data-ttu-id="39615-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="39615-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="39615-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="39615-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="39615-269">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="39615-269">Ubuntu 18.04</span></span>       | <span data-ttu-id="39615-270">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="39615-270">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="39615-271">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="39615-271">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="39615-272">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="39615-272">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="39615-273">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="39615-273">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="39615-274">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="39615-274">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="39615-275">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="39615-275">Debian 9 (Stretch)</span></span> | <span data-ttu-id="39615-276">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="39615-276">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="39615-277">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="39615-277">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="39615-278">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="39615-278">CentOS 7</span></span> <br> <span data-ttu-id="39615-279">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="39615-279">Oracle Linux 7</span></span> <br> <span data-ttu-id="39615-280">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="39615-280">RHEL 7</span></span> | <span data-ttu-id="39615-281">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="39615-281">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="39615-282">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="39615-282">openSUSE 42.3</span></span> | <span data-ttu-id="39615-283">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="39615-283">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="39615-284">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="39615-284">openSUSE Leap 15</span></span> | <span data-ttu-id="39615-285">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="39615-285">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="39615-286">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="39615-286">Fedora 27</span></span> <br> <span data-ttu-id="39615-287">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="39615-287">Fedora 28</span></span> | <span data-ttu-id="39615-288">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="39615-288">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="39615-289">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="39615-289">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="39615-290">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="39615-290">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="39615-291">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="39615-291">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="39615-292">Linux</span><span class="sxs-lookup"><span data-stu-id="39615-292">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="39615-293">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="39615-293">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="39615-294">Caminhos</span><span class="sxs-lookup"><span data-stu-id="39615-294">Paths</span></span>

- <span data-ttu-id="39615-295">`$PSHOME` é `/opt/microsoft/powershell/7/`</span><span class="sxs-lookup"><span data-stu-id="39615-295">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="39615-296">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="39615-296">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="39615-297">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="39615-297">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="39615-298">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="39615-298">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="39615-299">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="39615-299">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="39615-300">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="39615-300">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="39615-301">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="39615-301">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="39615-302">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="39615-302">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="39615-303">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="39615-303">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
