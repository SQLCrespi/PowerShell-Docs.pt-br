---
title: Instalar o PowerShell no Windows
description: Informações sobre a instalação do PowerShell no Windows
ms.date: 08/06/2018
ms.openlocfilehash: ea5432725f4baea8c688fb8e67482910e2c3981e
ms.sourcegitcommit: b6cf10224eb9f32919a505cdffbe5968241c18a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "80374886"
---
# <a name="installing-powershell-on-windows"></a>Instalar o PowerShell no Windows

Há várias maneiras de instalar o PowerShell no Windows.

## <a name="prerequisites"></a>Pré-requisitos

A versão mais recente do PowerShell tem suporte no Windows 7 SP1, Server 2008 R2 e versões posteriores.

Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:

- Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows anteriores ao Windows 10. Ele está disponível por meio do Windows Update ou de download direto. Os sistemas totalmente corrigidos já têm esse pacote instalado.
- Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2. Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).

## <a name="download-the-installer-package"></a>Baixar o pacote do instalador

Para instalar o PowerShell no Windows, baixe o pacote de instalação na página de [lançamentos][releases] do GitHub. Role a tela para baixo até a seção **Ativos** na página de Lançamentos. A seção **Ativos** pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.

## <a name="installing-the-msi-package"></a><a id="msi" />Instalando o pacote MSI

O arquivo MSI tem esta aparência `PowerShell-<version>-win-<os-arch>.msi`. Por exemplo:

- `PowerShell-7.0.0-win-x64.msi`
- `PowerShell-7.0.0-win-x86.msi`

Após o download, clique duas vezes no instalador e siga os prompts.

O instalador cria um atalho no Menu Iniciar do Windows.

- Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`
- Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`

> [!NOTE]
> O PowerShell 7 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1. Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.
>
> - O PowerShell 7 é instalado em `$env:ProgramFiles\PowerShell\7`
> - A pasta `$env:ProgramFiles\PowerShell\7` é adicionada ao `$env:PATH`
> - A pasta `$env:ProgramFiles\PowerShell\6` é excluída
>
> Se você precisar executar o PowerShell 6 lado a lado com o PowerShell 7, reinstale o PowerShell 6 usando o método de [instalação por ZIP](#zip).

### <a name="administrative-install-from-the-command-line"></a>Instalação administrativa a partir da linha de comando

É possível instalar os pacotes MSI por linha de comando, permitindo que os administradores implantem pacotes sem interação do usuário. O pacote MSI inclui as seguintes propriedades para controlar as opções de instalação:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.
- **ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.
- **REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.

Os exemplos a seguir mostram como instalar silenciosamente o PowerShell com todas as opções de instalação habilitadas.

```powershell
msiexec.exe /package PowerShell-7.0.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

Confira a lista completa das opções de linha de comando para `Msiexec.exe` em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).

## <a name="installing-the-msix-package"></a><a id="msix" />Instalação do pacote MSIX

Para instalar manualmente o pacote MSIX em um cliente Windows 10, baixe o pacote MSIX na nossa página de [versões][releases] do GitHub. Role a tela até a seção **Ativos** da versão que você deseja instalar. A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.

O arquivo MSIX tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`

Para instalar o pacote, você deve usar o cmdlet `Add-AppxPackage`.

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> O pacote MSIX ainda não foi liberado. Quando lançado, o pacote estará disponível na Microsoft Store e na página de [lançamentos][releases] do GitHub.

## <a name="installing-the-zip-package"></a><a id="zip" />Instalando o pacote ZIP

Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada. A instalação do arquivo ZIP não verifica os pré-requisitos como os pacotes MSI fazem. Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de atender aos [pré-requisitos](#prerequisites).

## <a name="deploying-on-windows-iot"></a>Implantar no Windows IoT

O Windows IoT é fornecido com o Windows PowerShell, que podemos usar para implantar o PowerShell 7.

1. Crie `PSSession` no dispositivo de destino

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. Copie o pacote ZIP no dispositivo

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. Conecte-se ao dispositivo e expanda o arquivo

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. Configure a comunicação remota no PowerShell 7

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. Conectar-se ao ponto de extremidade do PowerShell 7 no dispositivo

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a>Implantação no Nano Server

Essas instruções pressupõem que o Nano Server é um sistema operacional "sem periféricos" que tem uma versão do PowerShell já em execução. Confira mais informações na documentação do [Construtor de Imagens do Nano Server](/windows-server/get-started/deploy-nano-server).

Os binários do PowerShell podem ser implantados usando dois métodos diferentes.

1. Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.
2. Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.

Em ambos os casos, você precisa do pacote de versão ZIP do Windows 10 x64. Execute os comandos em uma instância de "Administrador" do PowerShell.

### <a name="offline-deployment-of-powershell"></a>Implantação offline do PowerShell

1. Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.
2. Desmonte a imagem e inicialize-a.
3. Conecte-se à instância da caixa de entrada do Windows PowerShell.
4. Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

### <a name="online-deployment-of-powershell"></a>Implantação online do PowerShell

Implante o PowerShell no Nano Server usando as etapas a seguir.

- Conectar-se à instância da caixa de entrada do Windows PowerShell

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- Copiar o arquivo para a instância do Nano Server

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- Entrar na sessão

  ```powershell
  Enter-PSSession $session
  ```

- Extrair o arquivo ZIP

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

## <a name="install-as-a-net-global-tool"></a>Instalar como uma ferramenta global do .NET

Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

O instalador da ferramenta dotnet adiciona `$env:USERPROFILE\dotnet\tools` à sua variável de ambiente `$env:PATH`. No entanto, o shell atualmente em execução não tem o `$env:PATH` atualizado. Você pode iniciar o PowerShell em um novo shell digitando `pwsh`.

## <a name="how-to-create-a-remoting-endpoint"></a>Como criar um ponto de extremidade de comunicação remota

O PowerShell dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH. Para obter mais informações, consulte:

- [Comunicação remota do SSH no PowerShell Core][ssh-remoting]
- [Comunicação remota do WSMan no PowerShell Core][wsman-remoting]

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
