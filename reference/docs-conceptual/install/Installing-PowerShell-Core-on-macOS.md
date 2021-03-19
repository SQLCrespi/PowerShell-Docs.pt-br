---
title: Instalar o PowerShell no macOS
description: Informações sobre a instalação do PowerShell no macOS
ms.date: 03/15/2021
ms.openlocfilehash: e69a757e761039799fe399c0e59c31c800a5094a
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483448"
---
# <a name="installing-powershell-on-macos"></a>Instalar o PowerShell no macOS

O PowerShell 7.0 ou posterior requer macOS 10.13 e posterior. Todos os pacotes estão disponíveis na nossa página [versões][] do GitHub. Depois de instalar o pacote, execute `pwsh` em um terminal.

> [!NOTE]
> O PowerShell 7.1 é uma atualização in-loco que remove o PowerShell Core 6.x e 7.0.
>
> A pasta `/usr/local/microsoft/powershell/6` é substituída por `/usr/local/microsoft/powershell/7`.
>
> Se você precisar executar uma versão mais antiga do PowerShell Core lado a lado com o PowerShell 7.1, instale a versão desejada usando o método [arquivo binário](#binary-archives).

Existem várias maneiras de instalar o PowerShell no macOS. Use um dos seguintes métodos:

- Instale o usando Homebrew. Homebrew é o gerenciador de pacotes preferido para macOS.
- Instale o PowerShell por meio do [Download Direto](#installation-via-direct-download)
- Instale por meio dos [arquivos binários](#binary-archives).

Depois de instalar o PowerShell, você precisa instalar o [OpenSSL](#installing-dependencies). O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a>Instalação da versão estável mais recente por meio do Homebrew no macOS 10.13 ou superior

Se o comando `brew` não for encontrado, será necessário instalar o Homebrew seguindo [as instruções][brew].

Agora, você pode instalar o PowerShell:

```sh
brew install --cask powershell
```

Por fim, verifique se a instalação está funcionando corretamente:

```sh
pwsh
```

Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir o upgrade e atualizar os valores mostrados em `$PSVersionTable`.

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a>Instalação da versão prévia estável mais recente por meio do Homebrew no macOS 10.13 ou superior

Depois de instalar o Homebrew, você pode instalar o PowerShell. Primeiro instale o pacote [Cask-Versions][cask-versions] que permite instalar versões alternativas de pacotes cask:

```sh
brew tap homebrew/cask-versions
```

Agora, você pode instalar o PowerShell:

```sh
brew install --cask powershell-preview
```

Por fim, verifique se a instalação está funcionando corretamente:

```sh
pwsh-preview
```

Quando novas versões do PowerShell forem lançadas, atualize a fórmula do Homebrew e faça upgrade do PowerShell:

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> Os comandos acima podem ser chamados por meio de um host do PowerShell (pwsh), mas será necessário sair e entrar novamente no shell do PowerShell para concluir a atualização.
> e atualizar os valores mostrados em `$PSVersionTable`.

É possível instalar o PowerShell usando o método de toque do Homebrew em versões LTS e estáveis.

```sh
brew install powershell/tap/powershell
```

Agora você pode verificar sua instalação

```sh
pwsh
```

Quando novas versões do PowerShell são lançadas, basta executar o comando a seguir.

```sh
brew upgrade powershell
```

> [!NOTE]
> Se você usar o método cask ou de toque, ao atualizar para uma versão mais recente do PowerShell, siga o mesmo método usado para instalar o PowerShell na primeira vez. Se você usar um método diferente, abrir uma nova sessão de push continuará a usar a versão mais antiga do PowerShell.
>
> Se você decidir usar métodos diferentes, há maneiras de corrigir o problema usando o [método de link do Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula).

## <a name="installation-via-direct-download"></a>Instalação por meio de download direto

Faça o download do pacote PKG `powershell-7.1.3-osx-x64.pkg` da página [versões][] em seu computador com macOS.

Clique duas vezes no arquivo e siga os prompts, ou instale-o do terminal:

```sh
sudo installer -pkg powershell-7.1.3-osx-x64.pkg -target /
```

Instalar [OpenSSL](#installing-dependencies). O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.

## <a name="install-as-a-net-global-tool"></a>Instalar como uma ferramenta global do .NET

Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

O instalador da ferramenta dotnet adiciona `~/.dotnet/tools` à sua variável de ambiente `PATH`. No entanto, o shell em execução no momento não tem o `PATH` atualizado. Você deve conseguir iniciar o PowerShell em um novo shell digitando `pwsh`.

Instalar [OpenSSL](#installing-dependencies). O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.

## <a name="binary-archives"></a>Arquivos binários

Os arquivos binários `tar.gz` do PowerShell são fornecidos para plataformas macOS a fim de habilitar cenários de implantação avançada. Ao instalar o usando esse método, você também deve instalar manualmente quaisquer dependências.

Instalar [OpenSSL](#installing-dependencies). O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell.

> [!NOTE]
> Você pode usar esse método para instalar qualquer versão do PowerShell, incluindo a mais recente:
> - Versão estável: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)
> - Versão prévia: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)
> - Versão LTS: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)

### <a name="installing-binary-archives-on-macos"></a>Instalação de arquivos binários no macOS

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a>Instalar dependências

O OpenSSL é necessário para operações CIM e comunicação remota do PowerShell. É possível instalar o OpenSSL por meio de MacPorts, se necessário.

> [!NOTE]
> O MacPorts e o Homebrew podem ter problemas quando usados juntos no mesmo sistema. No entanto, o Homebrew não tem um pacote para o OpenSSL 1.0. Para saber mais, confira as [Perguntas frequentes sobre o MacPorts](https://trac.macports.org/wiki/FAQ).

1. Instale as ferramentas de linha de comando Xcode. As ferramentas do Xcode são exigidas pelo MacPorts.

   ```sh
   xcode-select --install
   ```

1. Instale MacPorts. Se precisar de instruções, confira o [guia de instalação](https://www.macports.org/install.php).
1. Atualize o MacPorts executando `sudo port selfupdate`.
1. Atualize os pacotes de MacPorts executando `sudo port upgrade outdated`.
1. Instale o OpenSSL executando `sudo port install openssl10`.
1. Vincule as bibliotecas para disponibilizá-las para o PowerShell:

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a>Desinstalar o PowerShell

Se você instalou o PowerShell com Homebrew, use o comando a seguir para desinstalar:

```sh
brew cask uninstall powershell
```

Se você instalou o PowerShell por meio de download direto, o PowerShell deve ser removido manualmente:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Para remover os caminhos adicionais do PowerShell, confira a seção [caminhos](#paths) neste documento e remova os caminhos com `sudo rm`.

> [!NOTE]
> Isso não é necessário se você tiver instalado usando o Homebrew.

## <a name="paths"></a>Caminhos

- `$PSHOME` é `/usr/local/microsoft/powershell/7.1.3/`
- Perfis de usuário serão lidos de `~/.config/powershell/profile.ps1`
- Perfis padrão serão lidos de `$PSHOME/profile.ps1`
- Módulos de usuário serão lidos de `~/.local/share/powershell/Modules`
- Módulos compartilhados serão lidos de `/usr/local/share/powershell/Modules`
- Módulos padrão serão lidos de `$PSHOME/Modules`
- Histórico de PSReadline será gravado em `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

Os perfis respeitam a configuração por host do PowerShell. Assim, os perfis de hosts específicos padrão existem no `Microsoft.PowerShell_profile.ps1` nas mesmas localizações.

O PowerShell respeita a [Especificação de Diretório Base XDG][xdg-bds] no macOS.

Como o macOS é uma derivação do BSD, o prefixo `/usr/local` é usado em vez de `/opt`. Portanto, `$PSHOME` é `/usr/local/microsoft/powershell/7.1.3/`, e o link simbólico é colocado em `/usr/local/bin/pwsh`.

## <a name="installation-support"></a>Suporte à instalação

A Microsoft dá suporte aos métodos de instalação neste documento. Pode haver outros métodos de instalação disponíveis de outras fontes. Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.

## <a name="additional-resources"></a>Recursos adicionais

- [Homebrew Web][brew]
- [Repositório do Homebrew no Github][GitHub]
- [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[versões]: https://aka.ms/powershell-release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
