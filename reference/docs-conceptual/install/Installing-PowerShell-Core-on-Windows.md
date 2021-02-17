---
title: Instalar o PowerShell no Windows
description: Informações sobre a instalação do PowerShell no Windows
ms.date: 02/02/2021
ms.openlocfilehash: 12dedfed8349d243d3f2988fd7cb69c4cfc276bb
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563257"
---
# <a name="installing-powershell-on-windows"></a>Instalar o PowerShell no Windows

Há várias maneiras de instalar o PowerShell no Windows.

## <a name="prerequisites"></a>Pré-requisitos

A versão mais recente do PowerShell tem suporte no Windows 7 SP1, Server 2008 R2 e versões posteriores.

Para habilitar a comunicação remota do PowerShell pelo WSMan, os pré-requisitos a seguir precisam ser atendidos:

- Instale o [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) em versões do Windows anteriores ao Windows 10. Ele está disponível por meio do Windows Update ou de download direto. Os sistemas totalmente corrigidos já têm esse pacote instalado.
- Instale o Windows Management Framework (WMF) 4.0 ou mais recente no Windows 7 e no Windows Server 2008 R2. Saiba mais sobre o WMF em [Visão geral do WMF](/powershell/scripting/wmf/overview).

## <a name="download-the-installer-package"></a>Baixar o pacote do instalador

Para instalar o PowerShell no Windows, baixe o pacote de instalação [mais recente][] no GitHub. Também é possível encontrar a [versão prévia][] mais recente. Role a tela para baixo até a seção **Ativos** na página de Lançamentos. A seção **Ativos** pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.

## <a name="installing-the-msi-package"></a><a id="msi" />Instalando o pacote MSI

O arquivo MSI tem esta aparência `PowerShell-<version>-win-<os-arch>.msi`. Por exemplo: 

- `PowerShell-7.1.2-win-x64.msi`
- `PowerShell-7.1.2-win-x86.msi`

Após o download, clique duas vezes no instalador e siga os prompts.

O instalador cria um atalho no Menu Iniciar do Windows.

- Por padrão, o pacote é instalado em `$env:ProgramFiles\PowerShell\<version>`
- Você pode iniciar o PowerShell por meio do Menu Iniciar ou `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`

> [!NOTE]
> O PowerShell 7.1 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.
> O PowerShell 7.1 é uma atualização in-loco que substitui o PowerShell 6.x. ou PowerShell 7.0.
>
> - O PowerShell 7.1 está instalado no `$env:ProgramFiles\PowerShell\7`
> - A pasta `$env:ProgramFiles\PowerShell\7` é adicionada ao `$env:PATH`
> - A pasta `$env:ProgramFiles\PowerShell\6` é excluída
>
> Se você precisar executar o PowerShell 7.1 lado a lado com outras versões, use o método [ZIP install](#zip) para instalar a outra versão em uma pasta diferente.

### <a name="administrative-install-from-the-command-line"></a>Instalação administrativa a partir da linha de comando

É possível instalar os pacotes MSI por linha de comando, permitindo que os administradores implantem pacotes sem interação do usuário. O pacote MSI inclui as seguintes propriedades para controlar as opções de instalação:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Abrir o PowerShell** ao menu de contexto no Windows Explorer.
- **ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL** – Esta propriedade controla a opção de adicionar o item **Executar com o PowerShell** ao menu de contexto no Windows Explorer.
- **ENABLE_PSREMOTING** – Esta propriedade controla a opção para habilitar a comunicação remota do PowerShell durante a instalação.
- **REGISTER_MANIFEST** – Esta propriedade controla a opção para registrar o manifesto do Log de eventos do Windows.

Os exemplos a seguir mostram como instalar silenciosamente o PowerShell com todas as opções de instalação habilitadas.

```powershell
msiexec.exe /package PowerShell-7.1.2-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

Confira a lista completa das opções de linha de comando para `Msiexec.exe` em [Opções de linha de comando](/windows/desktop/Msi/command-line-options).

### <a name="registry-keys-created-during-installation"></a>Chaves do Registro criadas durante a instalação

A partir do PowerShell 7.1, o pacote MSI cria chaves do Registro que armazenam o local de instalação e a versão do PowerShell. Esses valores estão localizados em `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`. O valor de `<GUID>` é único para cada tipo de build (versão ou versão prévia), versão principal e arquitetura.

|    Versão    | Arquitetura |                                          Chave do Registro                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| Versão 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| Versão 7.1.x |     x64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| Versão 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| Versão 7.1.x |     x64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

Isso pode ser usado por administradores e desenvolvedores para encontrar o caminho para o PowerShell. Os valores de `<GUID>` serão os mesmos em todas as versões prévias e secundárias. Os valores de `<GUID>` são alterados em cada versão principal.

## <a name="installing-the-zip-package"></a><a id="zip" />Instalando o pacote ZIP

Arquivos binários de ZIP do PowerShell são fornecidos para habilitar cenários de implantação avançada. Baixe um dos arquivos ZIP a seguir da página de [versões][versões].

- PowerShell-7.1.2-win-x64.zip
- PowerShell-7.1.2-win-x86.zip
- PowerShell-7.1.2-win-arm64.zip
- PowerShell-7.1.2-win-arm32.zip

Dependendo de como você baixar o arquivo, poderá ser necessário desbloqueá-lo usando o cmdlet `Unblock-File`. Descompacte o conteúdo para o local de sua escolha e execute `pwsh.exe` desse local. Ao contrário da instalação de pacotes MSI, a instalação do arquivo ZIP não verifica os pré-requisitos. Para que a comunicação remota pelo WSMan funcione corretamente, certifique-se de atender aos [pré-requisitos](#prerequisites).

Use esse método para instalar a versão baseada em ARM do PowerShell em computadores como o Microsoft Surface Pro X. Para obter melhores resultados, instale o PowerShell na pasta `$env:ProgramFiles\PowerShell\7`.

## <a name="deploying-on-windows-10-iot-enterprise"></a>Implantar no Windows 10 IoT Enterprise

O Windows 10 IoT Enterprise vem com o Windows PowerShell, que pode ser usado para implantar o PowerShell 7.

1. Crie `PSSession` no dispositivo de destino

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. Copie o pacote ZIP no dispositivo

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. Conecte-se ao dispositivo e expanda o arquivo

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. Configure a comunicação remota no PowerShell 7

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. Conectar-se ao ponto de extremidade do PowerShell 7 no dispositivo

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a>Implantar no Windows 10 IoT Core

O Windows 10 IoT Core adiciona o Windows PowerShell quando você inclui o recurso _IOT_POWERSHELL_, que pode ser usado para implantar o PowerShell 7. As etapas definidas acima para o Windows 10 IoT Enterprise também podem ser seguidas para o IoT Core.

Para adicionar o PowerShell mais recente na imagem de remessa, use o comando [Import-PSCoreRelease][] para incluir o pacote na área de trabalho e adicione o recurso _OPENSRC_POWERSHELL_ à imagem.

> [!NOTE]
> Para a arquitetura ARM64, o Windows PowerShell não é adicionado quando você inclui _IOT_POWERSHELL_. Portanto, a instalação baseada em zip não funcionará. Você precisará usar o comando `Import-PSCoreRelease` para adicioná-lo à imagem.

## <a name="deploying-on-nano-server"></a>Implantação no Nano Server

Essas instruções pressupõem que o Nano Server é um sistema operacional "sem periféricos" que tem uma versão do PowerShell já em execução. Confira mais informações na documentação do [Construtor de Imagens do Nano Server](/windows-server/get-started/deploy-nano-server).

Os binários do PowerShell podem ser implantados usando dois métodos diferentes.

1. Offline – monte o VHD do Nano Server e descompacte o conteúdo do arquivo zip para o local escolhido na imagem montada.
1. Online – transfira o arquivo zip em uma sessão do PowerShell e descompacte-o em seu local escolhido.

Em ambos os casos, você precisa do pacote de versão ZIP do Windows 10 x64. Execute os comandos em uma instância de "Administrador" do PowerShell.

### <a name="offline-deployment-of-powershell"></a>Implantação offline do PowerShell

1. Use o utilitário zip favorito para descompactar o pacote para um diretório na imagem montada do Nano Server.
1. Desmonte a imagem e inicialize-a.
1. Conecte-se à instância interna do Windows PowerShell.
1. Siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"][].

### <a name="online-deployment-of-powershell"></a>Implantação online do PowerShell

Implante o PowerShell no Nano Server usando as etapas a seguir.

- Conectar-se à instância interna do Windows PowerShell

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

- Se você deseja comunicação remota baseada no WSMan, siga as instruções para criar um ponto de extremidade de comunicação remota usando a ["outra técnica de instância"][].

## <a name="install-as-a-net-global-tool"></a>Instalar como uma ferramenta global do .NET

Se você já tiver o [SDK do .NET Core](/dotnet/core/sdk) instalado, será fácil instalar o PowerShell como uma [ferramenta global do .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

O instalador da ferramenta dotnet adiciona `$env:USERPROFILE\dotnet\tools` à sua variável de ambiente `$env:PATH`. No entanto, o shell atualmente em execução não tem o `$env:PATH` atualizado. Você pode iniciar o PowerShell em um novo shell digitando `pwsh`.

## <a name="install-powershell-via-winget"></a>Instalar o PowerShell por meio do Winget

A ferramenta de linha de comando `winget` permite que os desenvolvedores descubram, instalem, atualizem, removam e configurem aplicativos em computadores Windows 10. Essa ferramenta é a interface do cliente para o serviço Gerenciador de Pacotes do Windows.

> [!NOTE]
> Atualmente, a ferramenta `winget` está em versão prévia. Nem todas as funcionalidades planejadas estão disponíveis no momento.
> Não use esse método em um cenário de implantação de produção. Confira a documentação do [winget] para obter uma lista de requisitos do sistema e de instruções de instalação.

Os seguintes comandos podem ser usados para instalar o PowerShell com os pacotes do `winget` publicados:

1. Pesquisar a versão mais recente do PowerShell

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.2
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.2-preview.5
   ```

1. Instalar uma versão do PowerShell usando o parâmetro `--exact`

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><a id="msix" />Instalar pela Microsoft Store

O PowerShell 7.1 foi publicado na Microsoft Store. Você pode encontrar a versão do PowerShell no site da [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) ou no aplicativo da Store no Windows.

Benefícios do pacote da Microsoft Store:

- Atualizações automáticas integradas diretamente no Windows 10
- Integra-se a outros mecanismos de distribuição de software, como Intune e SCCM

Limitações:

Os pacotes MSIX são executados em uma área restrita do aplicativo que virtualiza o acesso a alguns sistemas de arquivos e locais de registro.

- Todas as alterações de registro em HKEY_CURRENT_USER são copiadas na gravação para uma localização privada, por usuário, por aplicativo. Portanto, esses valores não estão disponíveis para outros aplicativos.
- Nenhuma definição de configuração no nível do sistema armazenada em `$PSHOME` pode ser modificada. Isso inclui a configuração do WSMAN. Isso impede que as sessões remotas se conectem a instalações baseadas na Store do PowerShell. Há suporte para configurações no nível do usuário e para comunicação remota SSH.

Para obter mais informações, confira [Noções básicas sobre como os aplicativos da área de trabalho empacotados são executados no Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).

### <a name="using-the-msix-package"></a>Usar o pacote MSIX

> [!NOTE]
> Os builds de versão prévia do PowerShell incluem um pacote MSIX. O pacote MSIX não tem suporte oficial. O pacote é criado para fins de teste durante o período de versão prévia.

Para instalar manualmente o pacote MSIX em um cliente do Windows 10, baixe o pacote MSIX na nossa página de [versões][versões] do GitHub. Role a tela até a seção **Ativos** da versão que você deseja instalar. A seção Ativos pode estar recolhida e, portanto, talvez você precise clicar para expandi-la.

O arquivo MSIX tem esta aparência – `PowerShell-<version>-win-<os-arch>.msix`

Para instalar o pacote, você deve usar o cmdlet `Add-AppxPackage`.

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a>Como criar um ponto de extremidade de comunicação remota

O PowerShell dá suporte ao protocolo PSRP (comunicação remota do PowerShell) por WSMan e SSH. Para obter mais informações, consulte:

- [Comunicação remota do SSH no PowerShell Core][ssh-remoting]
- [Comunicação remota do WSMan no PowerShell Core][wsman-remoting]

## <a name="upgrading-an-existing-installation"></a>Atualizar uma instalação existente

Para obter melhores resultados ao atualizar, você deve usar o mesmo método de instalação usado ao instalar o PowerShell pela primeira vez. Cada método de instalação instala o PowerShell em um local diferente. Se você não tiver certeza de como o PowerShell foi instalado, compare o local de instalação às informações do pacote neste artigo. Se você instalou por meio do pacote MSI, essas informações serão exibidas no Painel de Controle de **Programas e Recursos**.

## <a name="installation-support"></a>Suporte à instalação

A Microsoft dá suporte aos métodos de instalação neste documento. Pode haver outros métodos de instalação disponíveis de outras fontes. Embora essas ferramentas e métodos possam funcionar, a Microsoft não pode dar suporte a esses métodos.

<!-- link references -->

[versão prévia]: https://aka.ms/powershell-release?tag=preview
[mais recente]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
["outra técnica de instância"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
