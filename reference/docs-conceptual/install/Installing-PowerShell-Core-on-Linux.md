---
title: Instalar o PowerShell no Linux
description: Informações sobre como instalar o PowerShell em várias distribuições do Linux
ms.date: 07/30/2020
ms.openlocfilehash: f35366b5b1a0f54ce2c90d0e3cba59be7b9ce82c
ms.sourcegitcommit: 2ca12827dc64198b4263e8873a45b9466f22a67c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "92079788"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="bc1a7-103">Instalar o PowerShell no Linux</span><span class="sxs-lookup"><span data-stu-id="bc1a7-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="bc1a7-104">Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="bc1a7-105">Depois de instalar o pacote, execute `pwsh` em um terminal.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="bc1a7-106">Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-107">O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="bc1a7-108">A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="bc1a7-109">Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="bc1a7-110">Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="bc1a7-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="bc1a7-111">Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="bc1a7-112">Versões com suporte oficial</span><span class="sxs-lookup"><span data-stu-id="bc1a7-112">Officially supported releases</span></span>

- <span data-ttu-id="bc1a7-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="bc1a7-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="bc1a7-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="bc1a7-115">Debian 8</span></span>
- <span data-ttu-id="bc1a7-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="bc1a7-116">Debian 9</span></span>
- <span data-ttu-id="bc1a7-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-117">Debian 10</span></span>
- <span data-ttu-id="bc1a7-118">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="bc1a7-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-119">CentOS 7</span></span>
- <span data-ttu-id="bc1a7-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="bc1a7-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="bc1a7-121">Fedora 28</span></span>
- <span data-ttu-id="bc1a7-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="bc1a7-122">Fedora 29</span></span>
- <span data-ttu-id="bc1a7-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="bc1a7-123">Fedora 30</span></span>
- <span data-ttu-id="bc1a7-124">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="bc1a7-124">openSUSE 42.3</span></span>
- <span data-ttu-id="bc1a7-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="bc1a7-125">openSUSE Leap 15</span></span>

<span data-ttu-id="bc1a7-126">Versões com suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="bc1a7-126">Community supported releases</span></span>

- <span data-ttu-id="bc1a7-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="bc1a7-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="bc1a7-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="bc1a7-129">Arch Linux</span></span>
- <span data-ttu-id="bc1a7-130">Kali</span><span class="sxs-lookup"><span data-stu-id="bc1a7-130">Kali</span></span>
- <span data-ttu-id="bc1a7-131">Raspbian (experimental)</span><span class="sxs-lookup"><span data-stu-id="bc1a7-131">Raspbian (experimental)</span></span>

<span data-ttu-id="bc1a7-132">Métodos de instalação alternativos</span><span class="sxs-lookup"><span data-stu-id="bc1a7-132">Alternate install methods</span></span>

- <span data-ttu-id="bc1a7-133">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="bc1a7-133">Snap Package</span></span>
- <span data-ttu-id="bc1a7-134">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="bc1a7-134">Binary Archives</span></span>
- <span data-ttu-id="bc1a7-135">Ferramenta .NET Global</span><span class="sxs-lookup"><span data-stu-id="bc1a7-135">.NET Global tool</span></span>

<span data-ttu-id="bc1a7-136">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="bc1a7-136">Not currently supported</span></span>

- <span data-ttu-id="bc1a7-137">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-137">Ubuntu 20.04</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-138">O PowerShell pode somente dar suporte às distribuições com suporte do .NET.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-138">PowerShell can only support the distributions that are supported by .NET.</span></span> <span data-ttu-id="bc1a7-139">Confira as [notas sobre a versão do .NET Core][distros] para obter uma lista de distribuições com suporte.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-139">See the [.NET Core release notes][distros] for a list of supported distributions.</span></span> <span data-ttu-id="bc1a7-140">Caso haja uma distribuição com suporte do .NET não listada aqui, solicite a inclusão dela.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-140">If there is a distribution supported by .NET that is not listed here, you can request that support for the distribution be added.</span></span> <span data-ttu-id="bc1a7-141">Registre uma solicitação usando o modelo de [Solicitação de Suporte à Distribuição][].</span><span class="sxs-lookup"><span data-stu-id="bc1a7-141">Please file a request using the [Distribution Support Request][] template.</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="bc1a7-142">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-142">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="bc1a7-143">Instalação por meio do repositório de pacotes – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-143">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="bc1a7-144">O PowerShell Core Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-144">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-145">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-145">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https
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

<span data-ttu-id="bc1a7-146">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-146">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-147">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-147">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="bc1a7-148">Instalação por meio de download direto – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-148">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="bc1a7-149">Baixe o pacote Debian `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-149">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="bc1a7-150">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-150">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="bc1a7-151">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-151">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="bc1a7-152">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-152">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="bc1a7-153">Desinstalação – Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-153">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="bc1a7-154">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-154">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="bc1a7-155">Instalação por meio do repositório de pacotes – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-155">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="bc1a7-156">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-156">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-157">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-157">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https
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

<span data-ttu-id="bc1a7-158">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-158">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-159">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-159">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="bc1a7-160">Instalação por meio de download direto – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-160">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="bc1a7-161">Baixe o pacote Debian `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-161">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="bc1a7-162">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-162">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="bc1a7-163">O comando `dpkg -i` falha com dependências não atendidas.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-163">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="bc1a7-164">O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-164">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="bc1a7-165">Desinstalação – Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-165">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="bc1a7-166">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-166">Ubuntu 18.10</span></span>

<span data-ttu-id="bc1a7-167">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-167">Installation is supported via `snapd`.</span></span> <span data-ttu-id="bc1a7-168">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="bc1a7-168">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-169">O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-169">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="bc1a7-170">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-170">Ubuntu 19.04</span></span>

<span data-ttu-id="bc1a7-171">Só há suporte para instalações via `snapd`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-171">Installation is supported via `snapd`.</span></span> <span data-ttu-id="bc1a7-172">Para obter instruções, confira [Pacotes Snap][snap].</span><span class="sxs-lookup"><span data-stu-id="bc1a7-172">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-173">O Ubuntu 19.04 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-173">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-2004"></a><span data-ttu-id="bc1a7-174">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-174">Ubuntu 20.04</span></span>

<span data-ttu-id="bc1a7-175">O Ubuntu 20.04 é uma versão LTS.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-175">Ubuntu 20.04 is an LTS release.</span></span> <span data-ttu-id="bc1a7-176">Atualmente, o PowerShell não dá suporte a essa versão.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-176">PowerShell does not currently support this version.</span></span> <span data-ttu-id="bc1a7-177">O suporte para essa versão do Ubuntu está sendo considerado para a versão 7.1 do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-177">Support for this version is being considered for the PowerShell 7.1 release.</span></span> <span data-ttu-id="bc1a7-178">Se você gostaria de suporte para o Ubuntu 20.04, vote a favor nesta [solicitação](https://github.com/PowerShell/PowerShell/issues/12626).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-178">Please upvote this [request](https://github.com/PowerShell/PowerShell/issues/12626) if you would like support for Ubuntu 20.04.</span></span>

## <a name="debian-8"></a><span data-ttu-id="bc1a7-179">Debian 8</span><span class="sxs-lookup"><span data-stu-id="bc1a7-179">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="bc1a7-180">Instalação por meio do repositório de pacotes – Debian 8</span><span class="sxs-lookup"><span data-stu-id="bc1a7-180">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="bc1a7-181">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-181">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-182">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-182">The preferred method is as follows:</span></span>

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

<span data-ttu-id="bc1a7-183">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-183">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-184">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-184">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="bc1a7-185">Debian 9</span><span class="sxs-lookup"><span data-stu-id="bc1a7-185">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="bc1a7-186">Instalação por meio do repositório de pacotes – Debian 9</span><span class="sxs-lookup"><span data-stu-id="bc1a7-186">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="bc1a7-187">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-188">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-188">The preferred method is as follows:</span></span>

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

<span data-ttu-id="bc1a7-189">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-189">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-190">Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-190">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="bc1a7-191">Instalação por meio de download direto – Debian 9</span><span class="sxs-lookup"><span data-stu-id="bc1a7-191">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="bc1a7-192">Baixe o pacote Debian `powershell-lts_7.0.3-1.debian.9_amd64.deb` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-192">Download the Debian package `powershell-lts_7.0.3-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="bc1a7-193">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-193">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="bc1a7-194">Desinstalação – Debian 9</span><span class="sxs-lookup"><span data-stu-id="bc1a7-194">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="bc1a7-195">Debian 10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-195">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-196">O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-196">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="bc1a7-197">Instalação por meio do repositório de pacotes – Debian 10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-197">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="bc1a7-198">O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-198">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-199">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-199">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="bc1a7-200">Instalação por meio de download direto – Debian 10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-200">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="bc1a7-201">Baixe o pacote tar.gz `powershell-7.0.3-linux-x64.tar.gz` da página [versões][] no computador Debian.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-201">Download the tar.gz package `powershell-7.0.3-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="bc1a7-202">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-202">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="bc1a7-203">Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-203">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-204">As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-204">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="bc1a7-205">Instalação por meio de download direto – Alpine 3.9 e 3.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-205">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="bc1a7-206">Baixe o pacote tar.gz `powershell-7.0.3-linux-alpine-x64.tar.gz` da página [versões][] no computador Alpine.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-206">Download the tar.gz package `powershell-7.0.3-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="bc1a7-207">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-207">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="bc1a7-208">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-208">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-209">Este pacote funciona no Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-209">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="bc1a7-210">Instalação por meio do repositório de pacotes (preferencial) – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-210">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="bc1a7-211">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="bc1a7-212">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-213">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="bc1a7-214">Instalação por meio de download direto – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-214">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="bc1a7-215">Usando o [CentOS 7][], baixe o pacote RPM `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-215">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="bc1a7-216">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="bc1a7-217">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="bc1a7-218">Desinstalação – CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-218">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="bc1a7-220">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-220">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="bc1a7-221">Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-221">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="bc1a7-222">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-222">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="bc1a7-223">Como superusuário, registre o repositório da Microsoft uma vez.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-223">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="bc1a7-224">Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-224">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="bc1a7-225">Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-225">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="bc1a7-226">Baixe o pacote RPM `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-226">Download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="bc1a7-227">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-227">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="bc1a7-228">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-228">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="bc1a7-229">Desinstalação – Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-229">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="bc1a7-230">openSUSE</span><span class="sxs-lookup"><span data-stu-id="bc1a7-230">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="bc1a7-231">Instalação – openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="bc1a7-231">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="bc1a7-232">Instalação – openSUSE 42.3 Leap 15</span><span class="sxs-lookup"><span data-stu-id="bc1a7-232">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="bc1a7-233">Desinstalação – openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="bc1a7-233">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="bc1a7-234">Fedora</span><span class="sxs-lookup"><span data-stu-id="bc1a7-234">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-235">O Fedora 28 tem suporte apenas no PowerShell 6.1 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-235">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-236">As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-236">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="bc1a7-237">Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="bc1a7-237">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="bc1a7-238">O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-238">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="bc1a7-239">Instalação por meio de download direto – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="bc1a7-239">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="bc1a7-240">Baixe o pacote RPM `powershell-7.0.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-240">Download the RPM package `powershell-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="bc1a7-241">Em seguida, execute os seguintes comandos no terminal:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-241">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="bc1a7-242">Você pode instalar o RPM sem a etapa intermediária de baixá-lo:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-242">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="bc1a7-243">Desinstalação – Fedora 28, 29 e 30</span><span class="sxs-lookup"><span data-stu-id="bc1a7-243">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="bc1a7-244">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="bc1a7-244">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-245">O suporte ao Arch não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-245">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="bc1a7-246">O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-246">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="bc1a7-247">Ele pode ser compilado com a [última versão marcada][arch-release]</span><span class="sxs-lookup"><span data-stu-id="bc1a7-247">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="bc1a7-248">Ele pode ser compilado com base no [último commit no mestre][arch-git]</span><span class="sxs-lookup"><span data-stu-id="bc1a7-248">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="bc1a7-249">Ele pode ser instalado usando o [binário da última versão][arch-bin]</span><span class="sxs-lookup"><span data-stu-id="bc1a7-249">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="bc1a7-250">Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-250">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="bc1a7-251">Para obter mais informações sobre a instalação de pacotes usando o AUR, confira a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou [Como usar o PowerShell no Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-251">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="bc1a7-253">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="bc1a7-253">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="bc1a7-254">Usando o Snap</span><span class="sxs-lookup"><span data-stu-id="bc1a7-254">Getting snapd</span></span>

<span data-ttu-id="bc1a7-255">O `snapd` é necessário para executar snaps.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-255">`snapd` is required to run snaps.</span></span> <span data-ttu-id="bc1a7-256">Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-256">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="bc1a7-257">Instalação por meio do Snap</span><span class="sxs-lookup"><span data-stu-id="bc1a7-257">Installation via Snap</span></span>

<span data-ttu-id="bc1a7-258">O PowerShell para Linux é publicado no [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-258">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="bc1a7-259">O método preferencial é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-259">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="bc1a7-260">Para instalar a versão prévia, use o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-260">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="bc1a7-261">Após a instalação, o Snap será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-261">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="bc1a7-262">Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-262">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="bc1a7-263">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="bc1a7-263">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="bc1a7-264">ou</span><span class="sxs-lookup"><span data-stu-id="bc1a7-264">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="bc1a7-265">Kali</span><span class="sxs-lookup"><span data-stu-id="bc1a7-265">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-266">O suporte ao Kali não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-266">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="bc1a7-267">Instalação – Kali</span><span class="sxs-lookup"><span data-stu-id="bc1a7-267">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="bc1a7-268">Desinstalação – Kali</span><span class="sxs-lookup"><span data-stu-id="bc1a7-268">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="bc1a7-269">Raspbian</span><span class="sxs-lookup"><span data-stu-id="bc1a7-269">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="bc1a7-270">O suporte para o Raspbian é experimental.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-270">Raspbian support is experimental.</span></span>

<span data-ttu-id="bc1a7-271">Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-271">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="bc1a7-272">O CoreCLR e o PowerShell funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-272">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="bc1a7-273">Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-273">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="bc1a7-274">Instalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="bc1a7-274">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="bc1a7-275">Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-275">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="bc1a7-276">Desinstalação – Raspbian</span><span class="sxs-lookup"><span data-stu-id="bc1a7-276">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="bc1a7-277">Instalando versões prévias</span><span class="sxs-lookup"><span data-stu-id="bc1a7-277">Installing Preview Releases</span></span>

<span data-ttu-id="bc1a7-278">Ao instalar uma versão prévia do PowerShell para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-278">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="bc1a7-279">A instalação por download direito não é alterada, somente o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-279">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="bc1a7-280">A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:</span><span class="sxs-lookup"><span data-stu-id="bc1a7-280">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="bc1a7-281">Distribuições</span><span class="sxs-lookup"><span data-stu-id="bc1a7-281">Distribution(s)</span></span> |            <span data-ttu-id="bc1a7-282">Comando estável</span><span class="sxs-lookup"><span data-stu-id="bc1a7-282">Stable Command</span></span>            |               <span data-ttu-id="bc1a7-283">Comando de versão prévia</span><span class="sxs-lookup"><span data-stu-id="bc1a7-283">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="bc1a7-284">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="bc1a7-284">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="bc1a7-285">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="bc1a7-285">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="bc1a7-286">Fedora</span><span class="sxs-lookup"><span data-stu-id="bc1a7-286">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="bc1a7-287">Instalar como uma ferramenta global do .NET</span><span class="sxs-lookup"><span data-stu-id="bc1a7-287">Install as a .NET Global tool</span></span>

<span data-ttu-id="bc1a7-288">Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="bc1a7-288">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="bc1a7-289">O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-289">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="bc1a7-290">No entanto, o shell em execução no momento não tem o `PATH` atualizado.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-290">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="bc1a7-291">Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-291">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="bc1a7-292">Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="bc1a7-292">Binary Archives</span></span>

<span data-ttu-id="bc1a7-293">Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-293">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="bc1a7-294">Dependências</span><span class="sxs-lookup"><span data-stu-id="bc1a7-294">Dependencies</span></span>

<span data-ttu-id="bc1a7-295">O PowerShell cria binários portáteis para todas as distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-295">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="bc1a7-296">Porém o runtime do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-296">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="bc1a7-297">O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-297">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="bc1a7-298">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="bc1a7-298">OS</span></span>                 | <span data-ttu-id="bc1a7-299">Dependências</span><span class="sxs-lookup"><span data-stu-id="bc1a7-299">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="bc1a7-300">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-300">Ubuntu 16.04</span></span>       | <span data-ttu-id="bc1a7-301">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="bc1a7-301">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="bc1a7-302">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="bc1a7-302">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="bc1a7-303">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-303">Ubuntu 17.10</span></span>       | <span data-ttu-id="bc1a7-304">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="bc1a7-304">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="bc1a7-305">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="bc1a7-305">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="bc1a7-306">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bc1a7-306">Ubuntu 18.04</span></span>       | <span data-ttu-id="bc1a7-307">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="bc1a7-307">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="bc1a7-308">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="bc1a7-308">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="bc1a7-309">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="bc1a7-309">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="bc1a7-310">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="bc1a7-310">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="bc1a7-311">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="bc1a7-311">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="bc1a7-312">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="bc1a7-312">Debian 9 (Stretch)</span></span> | <span data-ttu-id="bc1a7-313">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="bc1a7-313">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="bc1a7-314">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="bc1a7-314">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="bc1a7-315">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-315">CentOS 7</span></span> <br> <span data-ttu-id="bc1a7-316">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-316">Oracle Linux 7</span></span> <br> <span data-ttu-id="bc1a7-317">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="bc1a7-317">RHEL 7</span></span> | <span data-ttu-id="bc1a7-318">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="bc1a7-318">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="bc1a7-319">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="bc1a7-319">openSUSE 42.3</span></span> | <span data-ttu-id="bc1a7-320">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="bc1a7-320">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="bc1a7-321">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="bc1a7-321">openSUSE Leap 15</span></span> | <span data-ttu-id="bc1a7-322">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="bc1a7-322">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="bc1a7-323">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="bc1a7-323">Fedora 27</span></span> <br> <span data-ttu-id="bc1a7-324">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="bc1a7-324">Fedora 28</span></span> | <span data-ttu-id="bc1a7-325">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="bc1a7-325">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="bc1a7-326">Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-326">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="bc1a7-327">Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-327">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="bc1a7-328">Instalação – Arquivos binários</span><span class="sxs-lookup"><span data-stu-id="bc1a7-328">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="bc1a7-329">Linux</span><span class="sxs-lookup"><span data-stu-id="bc1a7-329">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="bc1a7-330">Desinstalação de arquivos binários</span><span class="sxs-lookup"><span data-stu-id="bc1a7-330">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="bc1a7-331">Caminhos</span><span class="sxs-lookup"><span data-stu-id="bc1a7-331">Paths</span></span>

- <span data-ttu-id="bc1a7-332">`$PSHOME` é `/opt/microsoft/powershell/7/`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-332">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="bc1a7-333">Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-333">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="bc1a7-334">Perfis padrão serão lidos de `$PSHOME/profile.ps1`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-334">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="bc1a7-335">Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-335">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="bc1a7-336">Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-336">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="bc1a7-337">Módulos padrão serão lidos de `$PSHOME/Modules`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-337">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="bc1a7-338">O histórico do PSReadLine será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="bc1a7-338">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="bc1a7-339">Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-339">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="bc1a7-340">O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-340">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="bc1a7-341">Suporte à instalação</span><span class="sxs-lookup"><span data-stu-id="bc1a7-341">Installation support</span></span>

<span data-ttu-id="bc1a7-342">A Microsoft dá suporte aos métodos de instalação neste documento.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-342">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="bc1a7-343">Pode haver outros métodos de instalação disponíveis de outras fontes.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-343">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="bc1a7-344">Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.</span><span class="sxs-lookup"><span data-stu-id="bc1a7-344">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[versões]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Solicitação de suporte à distribuição]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
