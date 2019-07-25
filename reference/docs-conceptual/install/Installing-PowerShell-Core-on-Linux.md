---
title: Instalar o PowerShell Core no Linux
description: Informações sobre a instalação do PowerShell Core em diversas distribuições Linux
ms.date: 07/19/2019
ms.openlocfilehash: 929b153ef784f3203cd31a0e2fc52e744a07532f
ms.sourcegitcommit: 118eb294d5a84a772e6449d42a9d9324e18ef6b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68372189"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="7d1e5-103">Instalar o PowerShell Core no Linux</span><span class="sxs-lookup"><span data-stu-id="7d1e5-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="7d1e5-104">Compatível com [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 9][deb9],
 [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] e [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="7d1e5-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 9][deb9],
 [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="7d1e5-105">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="7d1e5-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="7d1e5-106">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="7d1e5-107">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="7d1e5-108">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-108">After the package is installed, run `pwsh` from a terminal.</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="7d1e5-109">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="7d1e5-109">Installing Preview Releases</span></span>

<span data-ttu-id="7d1e5-110">Ao instalar uma versão prévia do PowerShell Core para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="7d1e5-111">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-111">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="7d1e5-112">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-112">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="7d1e5-113">Distribuições</span><span class="sxs-lookup"><span data-stu-id="7d1e5-113">Distribution(s)</span></span>|<span data-ttu-id="7d1e5-114">Comando estável</span><span class="sxs-lookup"><span data-stu-id="7d1e5-114">Stable Command</span></span> | <span data-ttu-id="7d1e5-115">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="7d1e5-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="7d1e5-116">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="7d1e5-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="7d1e5-117">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="7d1e5-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="7d1e5-118">Fedora</span><span class="sxs-lookup"><span data-stu-id="7d1e5-118">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="7d1e5-119">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-119">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="7d1e5-120">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-120">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="7d1e5-121">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-121">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d1e5-122">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-122">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7d1e5-123">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-123">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-124">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-124">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="7d1e5-125">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-125">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="7d1e5-126">Baixe o pacote Debian `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-126">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7d1e5-127">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-127">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7d1e5-128">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-128">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7d1e5-129">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-129">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="7d1e5-130">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-130">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="7d1e5-131">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-131">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="7d1e5-132">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-132">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="7d1e5-133">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-133">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d1e5-134">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-134">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7d1e5-135">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-135">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-136">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-136">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="7d1e5-137">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-137">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="7d1e5-138">Baixe o pacote Debian `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-138">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7d1e5-139">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-139">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7d1e5-140">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-140">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7d1e5-141">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-141">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="7d1e5-142">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-142">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="7d1e5-143">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="7d1e5-143">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="7d1e5-144">Como a versão 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle), ela tem apenas [suporte da comunidade](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="7d1e5-144">As 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle), it is only [community supported](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6).</span></span>

<span data-ttu-id="7d1e5-145">A instalação no 18.10 é compatível por meio do `snapd`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-145">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="7d1e5-146">Confira [Pacote Snap][snap] para obter instruções completas;</span><span class="sxs-lookup"><span data-stu-id="7d1e5-146">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="7d1e5-147">Debian 8</span><span class="sxs-lookup"><span data-stu-id="7d1e5-147">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="7d1e5-148">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="7d1e5-148">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="7d1e5-149">O PowerShell Core para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-149">PowerShell Core, for Linux, is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d1e5-150">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-150">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl apt-transport-https

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

<span data-ttu-id="7d1e5-151">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-151">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-152">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-152">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="7d1e5-153">Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d1e5-153">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="7d1e5-154">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d1e5-154">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="7d1e5-155">O PowerShell Core para Linux é publicado nos repositórios de pacotes para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-155">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d1e5-156">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-156">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl gnupg apt-transport-https

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

<span data-ttu-id="7d1e5-157">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-157">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-158">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-158">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="7d1e5-159">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d1e5-159">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="7d1e5-160">Baixe o pacote Debian `powershell_6.2.0-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-160">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="7d1e5-161">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-161">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="7d1e5-162">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d1e5-162">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="7d1e5-163">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-163">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="7d1e5-164">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-164">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="7d1e5-165">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-165">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="7d1e5-166">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-166">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7d1e5-167">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-167">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-168">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-168">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="7d1e5-169">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-169">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="7d1e5-170">Usando o [CentOS 7][], baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-170">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="7d1e5-171">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-171">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d1e5-172">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-172">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="7d1e5-173">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-173">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d1e5-175">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-175">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d1e5-176">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-176">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7d1e5-177">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-177">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7d1e5-178">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-178">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d1e5-179">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-179">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d1e5-180">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-180">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7d1e5-181">Baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-181">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="7d1e5-182">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-182">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d1e5-183">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-183">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d1e5-184">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-184">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="7d1e5-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7d1e5-185">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="7d1e5-186">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7d1e5-186">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="7d1e5-187">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d1e5-187">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="7d1e5-188">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d1e5-188">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="7d1e5-189">Fedora</span><span class="sxs-lookup"><span data-stu-id="7d1e5-189">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="7d1e5-190">O Fedora 28 é compatível apenas com o PowerShell Core 6.1 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-190">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="7d1e5-191">Instalação por meio do repositório de pacotes (preferencial) – Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d1e5-191">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="7d1e5-192">O PowerShell Core para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-192">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="7d1e5-193">Instalação por meio de download direto – Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d1e5-193">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="7d1e5-194">Baixe o pacote RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-194">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="7d1e5-195">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-195">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d1e5-196">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-196">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="7d1e5-197">Desinstalação – Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d1e5-197">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="7d1e5-198">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="7d1e5-198">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="7d1e5-199">O suporte para o Arch é experimental.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-199">Arch support is experimental.</span></span>

<span data-ttu-id="7d1e5-200">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="7d1e5-200">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="7d1e5-201">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="7d1e5-201">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="7d1e5-202">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="7d1e5-202">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="7d1e5-203">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="7d1e5-203">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="7d1e5-204">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-204">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="7d1e5-205">Para obter mais informações sobre a instalação de pacotes usando o AUR, veja a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou a comunidade [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="7d1e5-205">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="7d1e5-207">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="7d1e5-207">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="7d1e5-208">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="7d1e5-208">Getting snapd</span></span>

<span data-ttu-id="7d1e5-209">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-209">`snapd` is required to run snaps.</span></span> <span data-ttu-id="7d1e5-210">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-210">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="7d1e5-211">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="7d1e5-211">Installation via Snap</span></span>

<span data-ttu-id="7d1e5-212">O PowerShell Core para Linux é publicado na [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-212">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="7d1e5-213">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-213">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="7d1e5-214">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="7d1e5-214">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="7d1e5-215">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-215">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="7d1e5-216">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-216">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="7d1e5-217">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="7d1e5-217">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="7d1e5-218">ou</span><span class="sxs-lookup"><span data-stu-id="7d1e5-218">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="7d1e5-219">Kali</span><span class="sxs-lookup"><span data-stu-id="7d1e5-219">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="7d1e5-220">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="7d1e5-220">Installation - Kali</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="7d1e5-221">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="7d1e5-221">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="7d1e5-222">Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d1e5-222">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="7d1e5-223">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-223">Raspbian support is experimental.</span></span>

<span data-ttu-id="7d1e5-224">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-224">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="7d1e5-225">O CoreCLR e o PowerShell Core funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-225">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="7d1e5-226">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-226">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="7d1e5-227">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d1e5-227">Installation - Raspbian</span></span>

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

<span data-ttu-id="7d1e5-228">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-228">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="7d1e5-229">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d1e5-229">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="7d1e5-230">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="7d1e5-230">Binary Archives</span></span>

<span data-ttu-id="7d1e5-231">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-231">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="7d1e5-232">Dependências</span><span class="sxs-lookup"><span data-stu-id="7d1e5-232">Dependencies</span></span>

<span data-ttu-id="7d1e5-233">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-233">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="7d1e5-234">Porém o tempo de execução do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-234">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="7d1e5-235">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-235">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="7d1e5-236">SO</span><span class="sxs-lookup"><span data-stu-id="7d1e5-236">OS</span></span>                 | <span data-ttu-id="7d1e5-237">Dependências</span><span class="sxs-lookup"><span data-stu-id="7d1e5-237">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="7d1e5-238">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-238">Ubuntu 16.04</span></span>       | <span data-ttu-id="7d1e5-239">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d1e5-239">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d1e5-240">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="7d1e5-240">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="7d1e5-241">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="7d1e5-241">Ubuntu 17.10</span></span>       | <span data-ttu-id="7d1e5-242">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d1e5-242">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d1e5-243">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="7d1e5-243">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="7d1e5-244">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d1e5-244">Ubuntu 18.04</span></span>       | <span data-ttu-id="7d1e5-245">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d1e5-245">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d1e5-246">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="7d1e5-246">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="7d1e5-247">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="7d1e5-247">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="7d1e5-248">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d1e5-248">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d1e5-249">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="7d1e5-249">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="7d1e5-250">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="7d1e5-250">Debian 9 (Stretch)</span></span> | <span data-ttu-id="7d1e5-251">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d1e5-251">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d1e5-252">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="7d1e5-252">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="7d1e5-253">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-253">CentOS 7</span></span> <br> <span data-ttu-id="7d1e5-254">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-254">Oracle Linux 7</span></span> <br> <span data-ttu-id="7d1e5-255">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="7d1e5-255">RHEL 7</span></span> | <span data-ttu-id="7d1e5-256">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="7d1e5-256">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="7d1e5-257">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7d1e5-257">openSUSE 42.3</span></span> | <span data-ttu-id="7d1e5-258">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="7d1e5-258">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="7d1e5-259">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d1e5-259">openSUSE Leap 15</span></span> | <span data-ttu-id="7d1e5-260">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="7d1e5-260">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="7d1e5-261">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="7d1e5-261">Fedora 27</span></span> <br> <span data-ttu-id="7d1e5-262">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d1e5-262">Fedora 28</span></span> | <span data-ttu-id="7d1e5-263">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="7d1e5-263">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="7d1e5-264">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-264">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="7d1e5-265">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-265">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="7d1e5-266">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="7d1e5-266">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="7d1e5-267">Linux</span><span class="sxs-lookup"><span data-stu-id="7d1e5-267">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="7d1e5-268">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="7d1e5-268">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="7d1e5-269">Caminhos</span><span class="sxs-lookup"><span data-stu-id="7d1e5-269">Paths</span></span>

* <span data-ttu-id="7d1e5-270">`$PSHOME` é `/opt/microsoft/powershell/6.2.0/`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-270">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="7d1e5-271">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-271">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="7d1e5-272">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-272">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="7d1e5-273">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-273">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="7d1e5-274">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-274">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="7d1e5-275">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-275">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="7d1e5-276">Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="7d1e5-276">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="7d1e5-277">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-277">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="7d1e5-278">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="7d1e5-278">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
