---
ms.date: 11/06/2018
title: Trabalhando com PSRepositories locais
description: O módulo PowerShellGet dá suporte a repositórios diferentes da Galeria do PowerShell. Este artigo descreve como configurar um repositório local do PowerShell.
ms.openlocfilehash: 24a2fd23124b3897952d64a347d103d9ee10248f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662347"
---
# <a name="working-with-private-powershellget-repositories"></a><span data-ttu-id="0c568-104">Trabalhar com repositórios privados do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="0c568-104">Working with Private PowerShellGet Repositories</span></span>

<span data-ttu-id="0c568-105">O módulo PowerShellGet dá suporte a repositórios diferentes da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-105">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="0c568-106">Esses cmdlets proporcionam os cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="0c568-106">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="0c568-107">Dar suporte a um conjunto de módulos do PowerShell confiável e validado previamente para uso em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="0c568-107">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="0c568-108">Testar um pipeline de CI/CD que compila os módulos ou scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c568-108">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="0c568-109">Fornecer módulos e scripts do PowerShell para sistemas que não podem acessar a Internet</span><span class="sxs-lookup"><span data-stu-id="0c568-109">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>
- <span data-ttu-id="0c568-110">Oferecer scripts e módulos do PowerShell disponíveis apenas para sua organização</span><span class="sxs-lookup"><span data-stu-id="0c568-110">Deliver PowerShell scripts and modules only available to your organization</span></span>

<span data-ttu-id="0c568-111">Este artigo descreve como configurar um repositório local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-111">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="0c568-112">O artigo também aborda o módulo [OfflinePowerShellGetDeploy][] disponível na Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-112">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="0c568-113">Esse módulo contém cmdlets para instalar a versão mais recente do PowerShellGet no seu repositório local.</span><span class="sxs-lookup"><span data-stu-id="0c568-113">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="0c568-114">Tipos de repositório local</span><span class="sxs-lookup"><span data-stu-id="0c568-114">Local repository types</span></span>

<span data-ttu-id="0c568-115">Há duas maneiras de criar um PSRepository local: Servidor do NuGet ou compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0c568-115">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="0c568-116">Cada tipo tem vantagens e desvantagens:</span><span class="sxs-lookup"><span data-stu-id="0c568-116">Each type has advantages and disadvantages:</span></span>

### <a name="nuget-server"></a><span data-ttu-id="0c568-117">Servidor do NuGet</span><span class="sxs-lookup"><span data-stu-id="0c568-117">NuGet Server</span></span>

| <span data-ttu-id="0c568-118">Vantagens</span><span class="sxs-lookup"><span data-stu-id="0c568-118">Advantages</span></span>| <span data-ttu-id="0c568-119">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="0c568-119">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="0c568-120">Imita a funcionalidade da PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="0c568-120">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="0c568-121">Aplicativo de várias camadas requer planejamento de operações e suporte</span><span class="sxs-lookup"><span data-stu-id="0c568-121">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="0c568-122">O NuGet integra-se ao Visual Studio e a outras ferramentas</span><span class="sxs-lookup"><span data-stu-id="0c568-122">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="0c568-123">É necessário realizar o gerenciamento de contas do NuGet e do modelo de autenticação</span><span class="sxs-lookup"><span data-stu-id="0c568-123">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="0c568-124">O NuGet dá suporte a metadados em pacotes `.Nupkg`</span><span class="sxs-lookup"><span data-stu-id="0c568-124">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="0c568-125">A publicação requer manutenção e gerenciamento da chave de API</span><span class="sxs-lookup"><span data-stu-id="0c568-125">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="0c568-126">Fornece pesquisa, administração de pacote, etc.</span><span class="sxs-lookup"><span data-stu-id="0c568-126">Provides search, package administration, etc.</span></span> | |

### <a name="file-share"></a><span data-ttu-id="0c568-127">Comp. de Arquivos</span><span class="sxs-lookup"><span data-stu-id="0c568-127">File Share</span></span>

| <span data-ttu-id="0c568-128">Vantagens</span><span class="sxs-lookup"><span data-stu-id="0c568-128">Advantages</span></span>| <span data-ttu-id="0c568-129">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="0c568-129">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="0c568-130">Fácil de configurar, fazer backup e manutenção</span><span class="sxs-lookup"><span data-stu-id="0c568-130">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="0c568-131">Os metadados usados pelo PowerShellGet não estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="0c568-131">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="0c568-132">Modelo de segurança simples: permissões de usuário no compartilhamento</span><span class="sxs-lookup"><span data-stu-id="0c568-132">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="0c568-133">Nenhuma interface do usuário além do compartilhamento de arquivo básico</span><span class="sxs-lookup"><span data-stu-id="0c568-133">No UI beyond basic file share</span></span> |
| <span data-ttu-id="0c568-134">Não há restrições, como substituir itens existentes</span><span class="sxs-lookup"><span data-stu-id="0c568-134">No constraints such as replacing existing items</span></span> | <span data-ttu-id="0c568-135">Segurança limitada e sem gravação de quem atualiza o quê</span><span class="sxs-lookup"><span data-stu-id="0c568-135">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="0c568-136">O PowerShellGet funciona com qualquer tipo e dá suporte à localização de versões e à instalação de dependências.</span><span class="sxs-lookup"><span data-stu-id="0c568-136">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="0c568-137">No entanto, alguns recursos que funcionam com a Galeria do PowerShell não estão disponíveis para servidores NuGet básicos ou compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0c568-137">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="0c568-138">Tudo é um pacote, não há diferenciação de scripts, módulos, recursos DSC ou recursos de função.</span><span class="sxs-lookup"><span data-stu-id="0c568-138">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="0c568-139">Os servidores de compartilhamento de arquivos não podem ver os metadados do pacote, incluindo as marcas.</span><span class="sxs-lookup"><span data-stu-id="0c568-139">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="0c568-140">Criando um repositório local</span><span class="sxs-lookup"><span data-stu-id="0c568-140">Creating a local repository</span></span>

<span data-ttu-id="0c568-141">O artigo a seguir lista as etapas para configurar seu próprio servidor do NuGet.</span><span class="sxs-lookup"><span data-stu-id="0c568-141">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="0c568-142">[NuGet.Server][]</span><span class="sxs-lookup"><span data-stu-id="0c568-142">[NuGet.Server][]</span></span>

<span data-ttu-id="0c568-143">Siga as etapas até o ponto de adição de pacotes.</span><span class="sxs-lookup"><span data-stu-id="0c568-143">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="0c568-144">As etapas para [publicar um pacote](#publishing-to-a-local-repository) são abordadas posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0c568-144">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="0c568-145">Para um repositório com base em compartilhamento de arquivo, verifique se os usuários têm permissões para acessar o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0c568-145">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="0c568-146">Registrando um repositório local</span><span class="sxs-lookup"><span data-stu-id="0c568-146">Registering a local repository</span></span>

<span data-ttu-id="0c568-147">Antes de poder usar um repositório, ele deve ser registrado usando o comando `Register-PSRepository`.</span><span class="sxs-lookup"><span data-stu-id="0c568-147">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="0c568-148">Nos exemplos a seguir, **InstallationPolicy** é definido como *Confiável* , supondo que você confie no seu próprio repositório.</span><span class="sxs-lookup"><span data-stu-id="0c568-148">In the examples below, the **InstallationPolicy** is set to *Trusted* , on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="0c568-149">Observe a diferença entre como os dois comandos tratam **ScriptSourceLocation** .</span><span class="sxs-lookup"><span data-stu-id="0c568-149">Take note of the difference between how the two commands handle **ScriptSourceLocation** .</span></span> <span data-ttu-id="0c568-150">Para um repositório baseado em compartilhamento de arquivo, **SourceLocation** e **ScriptSourceLocation** devem corresponder.</span><span class="sxs-lookup"><span data-stu-id="0c568-150">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="0c568-151">Para um repositório baseado na Web, eles devem ser diferentes; portanto, neste exemplo à direita "/" é adicionado a **SourceLocation** .</span><span class="sxs-lookup"><span data-stu-id="0c568-151">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation** .</span></span>

<span data-ttu-id="0c568-152">Se você quiser que o PSRepository recém-criado seja o repositório padrão, cancele o registro de todos os outros PSRepositories.</span><span class="sxs-lookup"><span data-stu-id="0c568-152">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="0c568-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0c568-153">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="0c568-154">O nome de repositório 'PSGallery' é reservado para uso pela Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-154">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="0c568-155">Você pode cancelar o registro de PSGallery, mas não é possível reutilizar esse nome para outro repositório.</span><span class="sxs-lookup"><span data-stu-id="0c568-155">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="0c568-156">Se você precisar restaurar a PSGallery, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0c568-156">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="0c568-157">Publicando em um repositório local</span><span class="sxs-lookup"><span data-stu-id="0c568-157">Publishing to a local repository</span></span>

<span data-ttu-id="0c568-158">Depois de registrar o PSRepository local, é possível publicar em seu PSRepository local.</span><span class="sxs-lookup"><span data-stu-id="0c568-158">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="0c568-159">Há dois cenários principais de publicação: publicar seu próprio módulo e publicar um módulo de PSGallery.</span><span class="sxs-lookup"><span data-stu-id="0c568-159">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="0c568-160">Publicando um módulo criado por você</span><span class="sxs-lookup"><span data-stu-id="0c568-160">Publishing a module you authored</span></span>

<span data-ttu-id="0c568-161">Use `Publish-Module` e `Publish-Script` para publicar seu módulo no PSRepository local da mesma maneira que faria com a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-161">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="0c568-162">Especifique o local para seu código</span><span class="sxs-lookup"><span data-stu-id="0c568-162">Specify the location for your code</span></span>
- <span data-ttu-id="0c568-163">Forneça uma chave de API</span><span class="sxs-lookup"><span data-stu-id="0c568-163">Supply an API key</span></span>
- <span data-ttu-id="0c568-164">Especifique o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="0c568-164">Specify the repository name.</span></span> <span data-ttu-id="0c568-165">Por exemplo, `-PSRepository LocalPSRepo`</span><span class="sxs-lookup"><span data-stu-id="0c568-165">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="0c568-166">Você deve criar uma conta no servidor do NuGet e entrar para gerar e salvar a chave de API.</span><span class="sxs-lookup"><span data-stu-id="0c568-166">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="0c568-167">Para um compartilhamento de arquivos, use qualquer cadeia de caracteres não vazia para o valor de NuGetApiKey.</span><span class="sxs-lookup"><span data-stu-id="0c568-167">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="0c568-168">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="0c568-168">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey $nuGetApiKey
```

> [!IMPORTANT]
> <span data-ttu-id="0c568-169">Para garantir a segurança, as chaves de API não devem ser codificadas em scripts.</span><span class="sxs-lookup"><span data-stu-id="0c568-169">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="0c568-170">Use um sistema seguro de gerenciamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="0c568-170">Use a secure key management system.</span></span> <span data-ttu-id="0c568-171">Quando um comando é executado manualmente, as chaves de API não devem ser passadas como texto sem formatação para evitar que ele seja registrado. O cmdlet `Read-Host` pode ser usado para passar com segurança o valor da chave de API.</span><span class="sxs-lookup"><span data-stu-id="0c568-171">When executing a command manually, API keys should not be passed as plain-text to avoid it being logged, the `Read-Host` cmdlet can be used to safely pass the value of the API key.</span></span>

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="0c568-172">Publicando um módulo de PSGallery</span><span class="sxs-lookup"><span data-stu-id="0c568-172">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="0c568-173">Para publicar um módulo de PSGallery em seu PSRepository local, use o cmdlet 'Save-Package'.</span><span class="sxs-lookup"><span data-stu-id="0c568-173">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="0c568-174">Especifique o nome do pacote</span><span class="sxs-lookup"><span data-stu-id="0c568-174">Specify the Name of the Package</span></span>
- <span data-ttu-id="0c568-175">Especifique 'NuGet' como o provedor</span><span class="sxs-lookup"><span data-stu-id="0c568-175">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="0c568-176">Especifique o local de PSGallery como a origem (https://www.powershellgallery.com/api/v2)</span><span class="sxs-lookup"><span data-stu-id="0c568-176">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="0c568-177">Especifique o caminho para seu repositório local</span><span class="sxs-lookup"><span data-stu-id="0c568-177">Specify the path to your local Repository</span></span>

<span data-ttu-id="0c568-178">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="0c568-178">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider NuGet -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="0c568-179">Se o seu PSRepository local é baseado na Web, ele exige uma etapa adicional que usa nuget.exe para publicar.</span><span class="sxs-lookup"><span data-stu-id="0c568-179">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="0c568-180">Consulte a documentação para usar [nuget.exe][].</span><span class="sxs-lookup"><span data-stu-id="0c568-180">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="0c568-181">Instalando o PowerShellGet em um sistema desconectado</span><span class="sxs-lookup"><span data-stu-id="0c568-181">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="0c568-182">Implantar o PowerShellGet é difícil em ambientes que exigem que os sistemas sejam desconectados da Internet.</span><span class="sxs-lookup"><span data-stu-id="0c568-182">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="0c568-183">O PowerShellGet tem um processo de inicialização que instala a versão mais recente na primeira vez que ele é usado.</span><span class="sxs-lookup"><span data-stu-id="0c568-183">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="0c568-184">O módulo OfflinePowerShellGetDeploy na Galeria do PowerShell fornece cmdlets que dão suporte a esse processo de inicialização.</span><span class="sxs-lookup"><span data-stu-id="0c568-184">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="0c568-185">Para iniciar uma implantação offline, você precisa:</span><span class="sxs-lookup"><span data-stu-id="0c568-185">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="0c568-186">Baixar e instalar o OfflinePowerShellGetDeploy em seu sistema conectado à Internet e seus sistemas desconectados</span><span class="sxs-lookup"><span data-stu-id="0c568-186">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="0c568-187">Baixe o PowerShellGet e suas dependências no sistema conectado à Internet usando o cmdlet `Save-PowerShellGetForOffline`</span><span class="sxs-lookup"><span data-stu-id="0c568-187">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="0c568-188">Copie o PowerShellGet e suas dependências do sistema conectado à Internet para o sistema desconectado</span><span class="sxs-lookup"><span data-stu-id="0c568-188">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="0c568-189">Use `Install-PowerShellGetOffline` no sistema desconectado para colocar o PowerShellGet e suas dependências nas pastas apropriadas</span><span class="sxs-lookup"><span data-stu-id="0c568-189">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="0c568-190">Os seguintes comandos usam `Save-PowerShellGetForOffline` para colocar todos os componentes em uma pasta `f:\OfflinePowerShellGet`</span><span class="sxs-lookup"><span data-stu-id="0c568-190">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="0c568-191">Neste ponto, você deve tornar o conteúdo de `F:\OfflinePowerShellGet` disponível para seus sistemas desconectados.</span><span class="sxs-lookup"><span data-stu-id="0c568-191">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="0c568-192">Execute o cmdlet `Install-PowerShellGetOffline` para instalar o PowerShellGet no sistema desconectado.</span><span class="sxs-lookup"><span data-stu-id="0c568-192">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="0c568-193">É importante que você não execute o PowerShellGet na sessão do PowerShell antes de executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="0c568-193">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="0c568-194">Depois de carregar o PowerShellGet na sessão, os componentes não podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="0c568-194">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="0c568-195">Se você iniciar o PowerShellGet por engano, saia e reinicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c568-195">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="0c568-196">Depois de executar esses comandos, você está pronto para publicar o PowerShellGet em seu repositório local.</span><span class="sxs-lookup"><span data-stu-id="0c568-196">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey $nuGetApiKey
```

> [!IMPORTANT]
> <span data-ttu-id="0c568-197">Para garantir a segurança, as chaves de API não devem ser codificadas em scripts.</span><span class="sxs-lookup"><span data-stu-id="0c568-197">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="0c568-198">Use um sistema seguro de gerenciamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="0c568-198">Use a secure key management system.</span></span> <span data-ttu-id="0c568-199">Quando um comando é executado manualmente, as chaves de API não devem ser passadas como texto sem formatação para evitar que ele seja registrado. O cmdlet `Read-Host` pode ser usado para passar com segurança o valor da chave de API.</span><span class="sxs-lookup"><span data-stu-id="0c568-199">When executing a command manually, API keys should not be passed as plain-text to avoid it being logged, the `Read-Host` cmdlet can be used to safely pass the value of the API key.</span></span>

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

## <a name="use-packaging-solutions-to-host-powershellget-repositories"></a><span data-ttu-id="0c568-200">Usar soluções de Empacotamento para hospedar repositórios do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="0c568-200">Use Packaging solutions to host PowerShellGet repositories</span></span>

<span data-ttu-id="0c568-201">Você também pode usar soluções de empacotamento como o Azure Artifacts para hospedar um repositório público ou privado do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="0c568-201">You can also use packaging solutions like Azure Artifacts to host a private or public PowerShellGet repository.</span></span> <span data-ttu-id="0c568-202">Para obter mais informações e instruções, confira a [documentação do Azure Artifacts](/azure/devops/artifacts/tutorials/private-powershell-library).</span><span class="sxs-lookup"><span data-stu-id="0c568-202">For more information and instructions, see the [Azure Artifacts documentation](/azure/devops/artifacts/tutorials/private-powershell-library).</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
