---
ms.date: 11/06/2018
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery,psget
title: Trabalhando com PSRepositories locais
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71327987"
---
# <a name="working-with-local-powershellget-repositories"></a>Trabalhando com repositórios locais do PowerShellGet

O módulo PowerShellGet dá suporte a repositórios diferentes da Galeria do PowerShell.
Esses cmdlets proporcionam os cenários a seguir:

- Dar suporte a um conjunto de módulos do PowerShell confiável e validado previamente para uso em seu ambiente
- Testar um pipeline de CI/CD que compila os módulos ou scripts do PowerShell
- Fornecer módulos e scripts do PowerShell para sistemas que não podem acessar a Internet

Este artigo descreve como configurar um repositório local do PowerShell. O artigo também aborda o módulo [OfflinePowerShellGetDeploy][] disponível na Galeria do PowerShell. Esse módulo contém cmdlets para instalar a versão mais recente do PowerShellGet no seu repositório local.

## <a name="local-repository-types"></a>Tipos de repositório local

Há duas maneiras de criar um PSRepository local: Servidor do NuGet ou compartilhamento de arquivos. Cada tipo tem vantagens e desvantagens:

Servidor do NuGet

| Vantagens| Desvantagens |
| --- | --- |
| Imita a funcionalidade da PowerShellGallery | Aplicativo de várias camadas requer planejamento de operações e suporte |
| O NuGet integra-se ao Visual Studio e a outras ferramentas | É necessário realizar o gerenciamento de contas do NuGet e do modelo de autenticação |
| O NuGet dá suporte a metadados em pacotes `.Nupkg` | A publicação requer manutenção e gerenciamento da chave de API |
| Fornece pesquisa, administração de pacote, etc. | |

Comp. de Arquivos

| Vantagens| Desvantagens |
| --- | --- |
| Fácil de configurar, fazer backup e manutenção | Os metadados usados pelo PowerShellGet não estão disponíveis |
| Modelo de segurança simples: permissões de usuário no compartilhamento | Nenhuma interface do usuário além do compartilhamento de arquivo básico |
| Não há restrições, como substituir itens existentes | Segurança limitada e sem gravação de quem atualiza o quê |

O PowerShellGet funciona com qualquer tipo e dá suporte à localização de versões e à instalação de dependências.
No entanto, alguns recursos que funcionam com a Galeria do PowerShell não estão disponíveis para servidores NuGet básicos ou compartilhamentos de arquivos.

- Tudo é um pacote, não há diferenciação de scripts, módulos, recursos DSC ou recursos de função.
- Os servidores de compartilhamento de arquivos não podem ver os metadados do pacote, incluindo as marcas.

## <a name="creating-a-local-repository"></a>Criando um repositório local

O artigo a seguir lista as etapas para configurar seu próprio servidor do NuGet.

- [NuGet.Server][]

Siga as etapas até o ponto de adição de pacotes. As etapas para [publicar um pacote](#publishing-to-a-local-repository) são abordadas posteriormente neste artigo.

Para um repositório com base em compartilhamento de arquivo, verifique se os usuários têm permissões para acessar o compartilhamento de arquivos.

## <a name="registering-a-local-repository"></a>Registrando um repositório local

Antes de poder usar um repositório, ele deve ser registrado usando o comando `Register-PSRepository`.
Nos exemplos a seguir, **InstallationPolicy** é definido como *Confiável*, supondo que você confie no seu próprio repositório.

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

Observe a diferença entre como os dois comandos tratam **ScriptSourceLocation**. Para um repositório baseado em compartilhamento de arquivo, **SourceLocation** e **ScriptSourceLocation** devem corresponder. Para um repositório baseado na Web, eles devem ser diferentes; portanto, neste exemplo à direita "/" é adicionado a **SourceLocation**.

Se você quiser que o PSRepository recém-criado seja o repositório padrão, cancele o registro de todos os outros PSRepositories. Por exemplo:

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> O nome de repositório 'PSGallery' é reservado para uso pela Galeria do PowerShell. Você pode cancelar o registro de PSGallery, mas não é possível reutilizar esse nome para outro repositório.

Se você precisar restaurar a PSGallery, execute o seguinte comando:

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a>Publicando em um repositório local

Depois de registrar o PSRepository local, é possível publicar em seu PSRepository local. Há dois cenários principais de publicação: publicar seu próprio módulo e publicar um módulo de PSGallery.

### <a name="publishing-a-module-you-authored"></a>Publicando um módulo criado por você

Use `Publish-Module` e `Publish-Script` para publicar seu módulo no PSRepository local da mesma maneira que faria com a Galeria do PowerShell.

- Especifique o local para seu código
- Forneça uma chave de API
- Especifique o nome do repositório. Por exemplo, `-PSRepository LocalPSRepo`

> [!NOTE]
> Você deve criar uma conta no servidor do NuGet e entrar para gerar e salvar a chave de API.
> Para um compartilhamento de arquivos, use qualquer cadeia de caracteres não vazia para o valor de NuGetApiKey.

Exemplos:

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> Para garantir a segurança, as chaves de API não devem ser codificadas em scripts. Use um sistema seguro de gerenciamento de chaves.

### <a name="publishing-a-module-from-the-psgallery"></a>Publicando um módulo de PSGallery

Para publicar um módulo de PSGallery em seu PSRepository local, use o cmdlet 'Save-Package'.

- Especifique o nome do pacote
- Especifique 'NuGet' como o provedor
- Especifique o local de PSGallery como a origem (https://www.powershellgallery.com/api/v2)
- Especifique o caminho para seu repositório local

Exemplo:

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

Se o seu PSRepository local é baseado na Web, ele exige uma etapa adicional que usa nuget.exe para publicar.

Consulte a documentação para usar [nuget.exe][].

## <a name="installing-powershellget-on-a-disconnected-system"></a>Instalando o PowerShellGet em um sistema desconectado

Implantar o PowerShellGet é difícil em ambientes que exigem que os sistemas sejam desconectados da Internet. O PowerShellGet tem um processo de inicialização que instala a versão mais recente na primeira vez que ele é usado. O módulo OfflinePowerShellGetDeploy na Galeria do PowerShell fornece cmdlets que dão suporte a esse processo de inicialização.

Para iniciar uma implantação offline, você precisa:

- Baixar e instalar o OfflinePowerShellGetDeploy em seu sistema conectado à Internet e seus sistemas desconectados
- Baixe o PowerShellGet e suas dependências no sistema conectado à Internet usando o cmdlet `Save-PowerShellGetForOffline`
- Copie o PowerShellGet e suas dependências do sistema conectado à Internet para o sistema desconectado
- Use `Install-PowerShellGetOffline` no sistema desconectado para colocar o PowerShellGet e suas dependências nas pastas apropriadas

Os seguintes comandos usam `Save-PowerShellGetForOffline` para colocar todos os componentes em uma pasta `f:\OfflinePowerShellGet`

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

Neste ponto, você deve tornar o conteúdo de `F:\OfflinePowerShellGet` disponível para seus sistemas desconectados. Execute o cmdlet `Install-PowerShellGetOffline` para instalar o PowerShellGet no sistema desconectado.

> [!NOTE]
> É importante que você não execute o PowerShellGet na sessão do PowerShell antes de executar esses comandos. Depois de carregar o PowerShellGet na sessão, os componentes não podem ser atualizados. Se você iniciar o PowerShellGet por engano, saia e reinicie o PowerShell.

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

Depois de executar esses comandos, você está pronto para publicar o PowerShellGet em seu repositório local.

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> Para garantir a segurança, as chaves de API não devem ser codificadas em scripts. Use um sistema seguro de gerenciamento de chaves.

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
