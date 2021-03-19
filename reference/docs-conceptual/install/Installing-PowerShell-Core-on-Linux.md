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
# <a name="installing-powershell-on-linux"></a>Instalar o PowerShell no Linux

Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub. Depois de instalar o pacote, execute `pwsh` em um terminal. Execute `pwsh-preview` se você instalou uma [versão prévia](#installing-preview-releases).

> [!NOTE]
> O PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.
>
> A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.
>
> Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [arquivo binário](#binary-archives).

Para distribuições Linux sem suporte oficial, você pode tentar instalar o PowerShell usando o [Pacote Snap do PowerShell][snap]. Você também poderá tentar implantar binários do PowerShell diretamente usando o [arquivo `tar.gz`][tar] do Linux, mas precisará configurar as dependências necessárias com base no sistema operacional em etapas separadas.

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

Versões de plataforma com suporte oficial para o PowerShell 7.1

- Ubuntu 16.04/18.04/20.04 (incluindo ARM64)
- Ubuntu 19.10 (via pacote Snap)
- Debian 9/10
- CentOS e RHEL 7/8
- Fedora 30
- Alpine 3.11+ (incluindo ARM64)

Versões de plataforma com suporte oficial para o PowerShell 7.0

- Ubuntu 16.04
- Ubuntu 18.04 e 20.04
- Debian 8
- Debian 9
- Debian 10
- Alpine 3.9 e 3.10
- CentOS 7
- Red Hat Enterprise Linux (RHEL) 7
- Fedora 28
- Fedora 29
- Fedora 30
- OpenSUSE 42.3
- openSUSE Leap 15

Versões com suporte da comunidade

- Ubuntu 18.10
- Ubuntu 19.10 e 20.10
- Arch Linux
- Kali
- Raspbian (experimental)

Métodos de instalação alternativos

- Pacote Snap
- Arquivos binários
- Ferramenta .NET Global

## <a name="ubuntu-1604"></a>Ubuntu 16.04

### <a name="installation-via-package-repository---ubuntu-1604"></a>Instalação por meio do repositório de pacotes – Ubuntu 16.04

O PowerShell Core Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-1604"></a>Instalação por meio de download direto – Ubuntu 16.04

Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` da página [versões][] no computador Ubuntu.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> O comando `dpkg -i` falha com dependências não atendidas. O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.

### <a name="uninstallation---ubuntu-1604"></a>Desinstalação – Ubuntu 16.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a>Ubuntu 18.04

### <a name="installation-via-package-repository---ubuntu-1804"></a>Instalação por meio do repositório de pacotes – Ubuntu 18.04

O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-1804"></a>Instalação por meio de download direto – Ubuntu 18.04

Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` da página [versões][] no computador Ubuntu.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> O comando `dpkg -i` falha com dependências não atendidas. O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.

### <a name="uninstallation---ubuntu-1804"></a>Desinstalação – Ubuntu 18.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a>Ubuntu 20.04

### <a name="installation-via-package-repository---ubuntu-2004"></a>Instalação por meio do repositório de pacotes – Ubuntu 20.04

O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-2004"></a>Instalação por meio de download direto – Ubuntu 20.04

Baixe o pacote Debian `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` da página [versões][] no computador Ubuntu.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> O comando `dpkg -i` falha com dependências não atendidas. O próximo comando, `apt-get install -f`, resolve esses problemas e, em seguida, conclui a configuração do pacote do PowerShell.

### <a name="uninstallation---ubuntu-2004"></a>Desinstalação – Ubuntu 20.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a>Ubuntu 18.10

Só há suporte para instalações via `snapd`. Para obter instruções, confira [Pacotes Snap][snap].

> [!NOTE]
> O Ubuntu 18.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) e tem apenas [suporte da comunidade](../powershell-support-lifecycle.md).

## <a name="ubuntu-1910-and-2010"></a>Ubuntu 19.10 e 20.10

Só há suporte para instalações via `snapd`. Para obter instruções, confira [Pacotes Snap][snap].

> [!NOTE]
> O Ubuntu 19.10 é uma [versão provisória](https://www.ubuntu.com/about/release-cycle) que tem [suporte da comunidade](../powershell-support-lifecycle.md).

## <a name="debian-8"></a>Debian 8

### <a name="installation-via-package-repository---debian-8"></a>Instalação por meio do repositório de pacotes – Debian 8

O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.

## <a name="debian-9"></a>Debian 9

### <a name="installation-via-package-repository---debian-9"></a>Instalação por meio do repositório de pacotes – Debian 9

O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---debian-9"></a>Instalação por meio de download direto – Debian 9

Baixe o pacote Debian `powershell_7.1.3-1.debian.9_amd64.deb` da página [versões][] no computador Debian.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo dpkg -i powershell_7.1.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a>Desinstalação – Debian 9

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a>Debian 10

> [!NOTE]
> O Debian 10 é compatível apenas com o PowerShell 7.0 e mais recentes.

### <a name="installation-via-package-repository---debian-10"></a>Instalação por meio do repositório de pacotes – Debian 10

O PowerShell para Linux é publicado nos repositórios de pacote para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

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

### <a name="installation-via-direct-download---debian-10"></a>Instalação por meio de download direto – Debian 10

Baixe o pacote tar.gz `powershell-7.1.3-linux-x64.tar.gz` da página [versões][] no computador Debian.

Em seguida, execute os seguintes comandos no terminal:

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

## <a name="alpine-39-and-310"></a>Alpine 3.9 e 3.10

> [!NOTE]
> As versões 3.9 e 3.10 do Alpine são compatíveis somente com o PowerShell 7.0 e mais recentes.

### <a name="installation-via-direct-download---alpine-39-and-310"></a>Instalação por meio de download direto – Alpine 3.9 e 3.10

Baixe o pacote tar.gz `powershell-7.1.3-linux-alpine-x64.tar.gz` da página [versões][] no computador Alpine.

Em seguida, execute os seguintes comandos no terminal:

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

## <a name="centos-7"></a>CentOS 7

> [!NOTE]
> Este pacote funciona no Oracle Linux 7.

### <a name="installation-via-package-repository-preferred---centos-7"></a>Instalação por meio do repositório de pacotes (preferencial) – CentOS 7

O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.

### <a name="installation-via-direct-download---centos-7"></a>Instalação por meio de download direto – CentOS 7

Usando o [CentOS 7][], baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador CentOS.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Você pode instalar o RPM sem a etapa intermediária de baixá-lo:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a>Desinstalação – CentOS 7

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a>Red Hat Enterprise Linux (RHEL) 7

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a>Instalação por meio do repositório de pacotes (preferencial) – Red Hat Enterprise Linux (RHEL) 7

O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Como superusuário, registre o repositório da Microsoft uma vez. Após o registro, você pode atualizar o PowerShell com o `sudo yum update powershell`.

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a>Instalação por meio de download direto – Red Hat Enterprise Linux (RHEL) 7

Baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Red Hat Enterprise Linux.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Você pode instalar o RPM sem a etapa intermediária de baixá-lo:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a>Desinstalação – Red Hat Enterprise Linux (RHEL) 7

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a>openSUSE

### <a name="installation---opensuse-423"></a>Instalação – openSUSE 42.3

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

### <a name="installation---opensuse-leap-15"></a>Instalação – openSUSE 42.3 Leap 15

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a>Desinstalação – openSUSE 42.3, openSUSE Leap 15

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a>Fedora

> [!NOTE]
> O Fedora 28 tem suporte apenas no PowerShell 6.1 e mais recente.

> [!NOTE]
> As versões 29 e 30 do Fedora são compatíveis somente com o PowerShell 7.0 e mais recentes.

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a>Instalação por meio do repositório de pacotes (preferencial) – Fedora 28, 29 e 30

O PowerShell para Linux é publicado nos repositórios oficiais da Microsoft para facilitar a instalação e as atualizações.

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a>Instalação por meio de download direto – Fedora 28, 29 e 30

Baixe o pacote RPM `powershell-7.1.3-1.rhel.7.x86_64.rpm` da página [versões][] no computador Fedora.

Em seguida, execute os seguintes comandos no terminal:

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Você pode instalar o RPM sem a etapa intermediária de baixá-lo:

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a>Desinstalação – Fedora 28, 29 e 30

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a>Arch Linux

> [!NOTE]
> O suporte ao Arch não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.

O PowerShell está disponível no AUR (Repositório de Usuários do [Arch Linux][]).

- Ele pode ser compilado com a [última versão marcada][arch-release]
- Ele pode ser compilado com base no [último commit no mestre][arch-git]
- Ele pode ser instalado usando o [binário da última versão][arch-bin]

Pacotes no AUR são mantidos pela comunidade, e não há suporte oficial.

Para obter mais informações sobre a instalação de pacotes usando o AUR, confira a [wiki do Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) ou [Como usar o PowerShell no Docker](powershell-in-docker.md).

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a>Pacote Snap

### <a name="getting-snapd"></a>Usando o Snap

O `snapd` é necessário para executar snaps. Use [estas instruções](https://docs.snapcraft.io/core/install) para garantir que você tem o `snapd` instalado.

### <a name="installation-via-snap"></a>Instalação por meio do Snap

O PowerShell para Linux é publicado no [Snap Store](https://snapcraft.io/store) para facilitar a instalação e as atualizações.

O método preferencial é o seguinte:

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

Para instalar a versão prévia, use o seguinte método:

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

Após a instalação, o Snap será atualizado automaticamente. Você pode disparar uma atualização usando o `sudo snap refresh powershell` ou o `sudo snap refresh powershell-preview`.

### <a name="uninstallation"></a>Desinstalação

```sh
sudo snap remove powershell
```

ou

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a>Kali

> [!NOTE]
> O suporte ao Kali não é reconhecido oficialmente pela Microsoft e é mantido pela comunidade.

### <a name="installation---kali"></a>Instalação – Kali

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a>Desinstalação – Kali

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="support-for-arm-processors"></a>Suporte para processadores ARM

O PowerShell pode ser instalado em algumas distribuições do Linux. O PowerShell depende do suporte .NET do ARM. O PowerShell tem suporte nas seguintes distribuições:

- Alpine Linux v3.11+: .NET dá suporte a Arm64, mas não há nenhum pacote instalável para o PowerShell no momento
- Raspbian: confira as instruções de instalação abaixo
- Debian v9+: dá suporte a Arm32 e Arm64 usando o método de instalação de [Arquivo Binário](#binary-archives)
- Ubuntu 20.10, 20.04, 18.04, 16.04: dá suporte a Arm32 e Arm64 usando o método de instalação de [Arquivo Binário](#binary-archives)

## <a name="raspbian"></a>Raspbian

> [!NOTE]
> O suporte para o Raspbian é experimental.

Atualmente, o PowerShell tem suporte apenas no Raspbian Stretch.

O CoreCLR e o PowerShell funcionam apenas em dispositivos Pi 2 e Pi 3 porque outros dispositivos, como [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), têm um processador sem suporte.

Faça o download do [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) e siga as [instruções de instalação](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) para instalá-lo em seu Pi.

### <a name="installation---raspbian"></a>Instalação – Raspbian

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

Opcionalmente, você pode criar um link simbólico para iniciar o PowerShell sem especificar o caminho até o binário `pwsh`.

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a>Desinstalação – Raspbian

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a>Instalando versões prévias

Ao instalar uma versão prévia do PowerShell para Linux por meio de um Repositório de Pacotes, o nome do pacote é alterado de `powershell` para `powershell-preview`.

A instalação por download direito não é alterada, somente o nome do arquivo.

A tabela a seguir contém os comandos para instalar os pacotes estáveis e de versão prévia usando vários gerenciadores de pacotes:

| Distribuições |            Comando estável            |               Comando de versão prévia                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| Ubuntu, Debian  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| CentOS, RedHat  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| Fedora          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a>Instalar como uma ferramenta global do .NET

Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`. No entanto, o shell em execução no momento não tem o `PATH` atualizado. Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.

## <a name="binary-archives"></a>Arquivos binários

Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas Linux a fim de habilitar cenários de implantação avançada.

> [!NOTE]
> Você pode usar esse método para instalar qualquer versão do PowerShell, incluindo a mais recente:
> - Versão estável: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)
> - Versão prévia: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)
> - Versão LTS: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)

### <a name="dependencies"></a>Dependências

O PowerShell cria binários portáteis para todas as distribuições Linux. Porém o runtime do .NET Core exige dependências diferentes em diferentes distribuições, portanto, o PowerShell faz o mesmo.

O gráfico a seguir mostra as dependências do .NET Core 2.0 com suporte oficial em diferentes distribuições Linux.

| Sistema operacional                 | Dependências |
| ------------------ | ------------ |
| Ubuntu 16.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55 |
| Ubuntu 17.10       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57 |
| Ubuntu 18.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60 |
| Debian 8 (Jessie)  | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Debian 9 (Stretch) | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57 |
| CentOS 7 <br> Oracle Linux 7 <br> RHEL 7 | libunwind, libcurl, openssl-libs, libicu |
| OpenSUSE 42.3 | libcurl4, libopenssl1_0_0, libicu52_1 |
| openSUSE Leap 15 | libcurl4, libopenssl1_0_0, libicu60_2 |
| Fedora 27 <br> Fedora 28 | libunwind, libcurl, openssl-libs, libicu, compat-openssl10 |

Para implantar binários do PowerShell em distribuições Linux sem suporte oficial, instale as dependências necessárias para o sistema operacional de destino em etapas separadas. Por exemplo, nosso [dockerfile do Amazon Linux][amazon-dockerfile] instala as dependências primeiro e, em seguida, extrai o arquivo `tar.gz` Linux.

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a>Instalação – Arquivos binários

O seguinte exemplo mostra as etapas para instalar o arquivo binário x64. Você deve escolher o arquivo binário correto correspondente ao tipo de processador para sua plataforma.

- powershell-7.1.3-linux-arm32.tar.gz
- powershell-7.1.3-linux-arm64.tar.gz
- powershell-7.1.3-linux-x64.tar.gz

#### <a name="linux"></a>Linux

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

### <a name="uninstalling-binary-archives"></a>Desinstalação de arquivos binários

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a>Caminhos

- `$PSHOME` é `/opt/microsoft/powershell/7/`
- Os perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`
- Os perfis padrão serão lidos de `$PSHOME/profile.ps1`
- Os módulos de usuário serão lidos de `~/.local/share/powershell/Modules`
- Os módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`
- Os módulos padrão serão lidos de `$PSHOME/Modules`
- O histórico do PSReadLine será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis específicos do host padrão existem em `Microsoft.PowerShell_profile.ps1` nos mesmos locais.

O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no Linux.

## <a name="installation-support"></a>Suporte à instalação

A Microsoft dá suporte aos métodos de instalação neste documento. Pode haver outros métodos de instalação disponíveis de outras fontes. Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.

<!-- link references -->
[versões]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
