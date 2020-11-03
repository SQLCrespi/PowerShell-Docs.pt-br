---
description: Descreve os novos recursos que estão incluídos no Windows PowerShell 5,1.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196561"
---
# <a name="about_windows_powershell_51"></a><span data-ttu-id="fd354-104">about_Windows_PowerShell_5.1</span><span class="sxs-lookup"><span data-stu-id="fd354-104">about_Windows_PowerShell_5.1</span></span>

## <a name="short-description"></a><span data-ttu-id="fd354-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="fd354-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="fd354-106">Descreve os novos recursos que estão incluídos no Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="fd354-106">Describes new features that are included in Windows PowerShell 5.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="fd354-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="fd354-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="fd354-108">O Windows PowerShell 5,1 inclui recursos novos e significativos que estendem seu uso, melhoram sua usabilidade e permitem controlar e gerenciar ambientes baseados no Windows de forma mais fácil e abrangente.</span><span class="sxs-lookup"><span data-stu-id="fd354-108">Windows PowerShell 5.1 includes significant new features that extend its use, improve its usability, and allow you to control and manage Windows-based environments more easily and comprehensively.</span></span>

<span data-ttu-id="fd354-109">O Windows PowerShell 5,1 é compatível com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="fd354-109">Windows PowerShell 5.1 is backward-compatible.</span></span> <span data-ttu-id="fd354-110">Os cmdlets, provedores, módulos, snap-ins, scripts, funções e perfis que foram projetados para o Windows PowerShell 4,0, o Windows PowerShell 3,0 e o Windows PowerShell 2,0 geralmente funcionam no Windows PowerShell 5,1 sem alterações.</span><span class="sxs-lookup"><span data-stu-id="fd354-110">Cmdlets, providers, modules, snap-ins, scripts, functions, and profiles that were designed for Windows PowerShell 4.0, Windows PowerShell 3.0, and Windows PowerShell 2.0 generally work in Windows PowerShell 5.1 without changes.</span></span>

- <span data-ttu-id="fd354-111">Novos cmdlets: usuários e grupos locais; Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="fd354-111">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="fd354-112">Os aprimoramentos do PowerShellGet incluem a imposição de módulos assinados e a instalação de módulos JEA</span><span class="sxs-lookup"><span data-stu-id="fd354-112">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="fd354-113">Suporte acrescentado para o PackageManagement para Contêineres, Configuração de CBS, configuração baseada em EXE, pacotes CAB</span><span class="sxs-lookup"><span data-stu-id="fd354-113">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="fd354-114">Melhorias de depuração para classes DSC e PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd354-114">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="fd354-115">Aprimoramentos de segurança, incluindo a imposição de módulos de catálogo assinado provenientes do Servidor de Recepção e ao usar cmdlets do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="fd354-115">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="fd354-116">Respostas para diversos problemas e solicitações de usuários</span><span class="sxs-lookup"><span data-stu-id="fd354-116">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="fd354-117">O Windows PowerShell 5,1 é instalado por padrão no Windows Server 2016 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fd354-117">Windows PowerShell 5.1 is installed by default on Windows Server 2016 and Windows 10.</span></span> <span data-ttu-id="fd354-118">Para instalar o Windows PowerShell 5,1 no Windows Server 2012 R2, Windows 8.1 Enterprise ou Windows 8.1 Pro, consulte [instalar e configurar o WMF 5,1](/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="fd354-118">To install Windows PowerShell 5.1 on Windows Server 2012 R2, Windows 8.1 Enterprise, or Windows 8.1 Pro, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
<span data-ttu-id="fd354-119">Certifique-se de ler os detalhes do download e atender a todos os requisitos do sistema antes de instalar o Windows Management Framework 5,1.</span><span class="sxs-lookup"><span data-stu-id="fd354-119">Be sure to read the download details, and meet all system requirements, before you install Windows Management Framework 5.1.</span></span>

<span data-ttu-id="fd354-120">Você também pode ler sobre as alterações no Windows PowerShell 5,1 em [novidades do Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span><span class="sxs-lookup"><span data-stu-id="fd354-120">You can also read about changes to Windows PowerShell 5.1 in [What's New in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span></span>

## <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="fd354-121">Novos cenários e recursos no WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="fd354-121">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="fd354-122">Observação: essas informações são preliminares e estão sujeitas a alteração.</span><span class="sxs-lookup"><span data-stu-id="fd354-122">Note: This information is preliminary and subject to change.</span></span>

### <a name="powershell-editions"></a><span data-ttu-id="fd354-123">Edições do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd354-123">PowerShell Editions</span></span>
<span data-ttu-id="fd354-124">A partir da versão 5.1, o PowerShell está disponível em diferentes edições que denotam os vários conjuntos de recursos e compatibilidades de plataforma.</span><span class="sxs-lookup"><span data-stu-id="fd354-124">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="fd354-125">**Desktop Edition:** Criado no .NET Framework; fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="fd354-125">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="fd354-126">**Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="fd354-126">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="fd354-127">**Saiba mais sobre como usar as edições do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fd354-127">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="fd354-128">Determinar a edição em execução do PowerShell usando $PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="fd354-128">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="fd354-129">Filtrar resultados de Get-Module por CompatiblePSEditions usando o parâmetro PSEdition</span><span class="sxs-lookup"><span data-stu-id="fd354-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="fd354-130">Impedir a execução do script, a menos que seja ele executado em uma edição compatível do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd354-130">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="fd354-131">Declarar a compatibilidade de um módulo para versões específicas do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd354-131">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a><span data-ttu-id="fd354-132">Cmdlets de Catálogo</span><span class="sxs-lookup"><span data-stu-id="fd354-132">Catalog Cmdlets</span></span>

<span data-ttu-id="fd354-133">Dois novos cmdlets foram adicionados no módulo [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)); eles geram e validam os arquivos de catálogo do Windows.</span><span class="sxs-lookup"><span data-stu-id="fd354-133">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) module; these generate and validate Windows catalog files.</span></span>

#### <a name="new-filecatalog"></a><span data-ttu-id="fd354-134">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="fd354-134">New-FileCatalog</span></span>

<span data-ttu-id="fd354-135">New-FileCatalog cria um arquivo de catálogo do Windows para o conjunto de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="fd354-135">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="fd354-136">Este arquivo de catálogo contém hashes para todos os arquivos nos caminhos especificados.</span><span class="sxs-lookup"><span data-stu-id="fd354-136">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="fd354-137">Os usuários podem distribuir o conjunto de pastas juntamente com o arquivo de catálogo correspondente que representa essas pastas.</span><span class="sxs-lookup"><span data-stu-id="fd354-137">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="fd354-138">Essas informações são úteis para validar se as alterações foram feitas nas pastas desde a hora de criação do catálogo.</span><span class="sxs-lookup"><span data-stu-id="fd354-138">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="fd354-139">Há suporte para as versões 1 e 2 do catálogo.</span><span class="sxs-lookup"><span data-stu-id="fd354-139">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="fd354-140">A versão 1 usa o algoritmo de hash SHA1 para criar hashes de arquivo; a versão 2 usa SHA256.</span><span class="sxs-lookup"><span data-stu-id="fd354-140">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="fd354-141">Não há suporte para a versão 2 do catálogo no *Windows Server 2008 R2* ou no *Windows 7* .</span><span class="sxs-lookup"><span data-stu-id="fd354-141">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7* .</span></span> <span data-ttu-id="fd354-142">Você deve usar a versão 2 do catálogo no *Windows 8* , no *Windows Server 2012* e nos sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="fd354-142">You should use catalog version 2 on *Windows 8* , *Windows Server 2012* , and later operating systems.</span></span>

<span data-ttu-id="fd354-143">Para verificar a integridade do arquivo de catálogo (Pester.cat, no exemplo acima), assine-o usando o cmdlet [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature).</span><span class="sxs-lookup"><span data-stu-id="fd354-143">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet.</span></span>

#### <a name="test-filecatalog"></a><span data-ttu-id="fd354-144">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="fd354-144">Test-FileCatalog</span></span>

<span data-ttu-id="fd354-145">Test-FileCatalog valida o catálogo que representa um conjunto de pastas.</span><span class="sxs-lookup"><span data-stu-id="fd354-145">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="fd354-146">Este cmdlet compara todos os hashes de arquivos e seus caminhos relativos encontrados no *catálogo* com aqueles no *disco* .</span><span class="sxs-lookup"><span data-stu-id="fd354-146">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk* .</span></span> <span data-ttu-id="fd354-147">Se detectar qualquer incompatibilidade entre os hashes e os caminhos de arquivo, o status será retornado como *ValidationFailed* .</span><span class="sxs-lookup"><span data-stu-id="fd354-147">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed* .</span></span> <span data-ttu-id="fd354-148">Os usuários podem recuperar todas essas informações usando o parâmetro *-Detailed* .</span><span class="sxs-lookup"><span data-stu-id="fd354-148">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="fd354-149">Ele também exibe o status da assinatura do catálogo na propriedade *Signature* , que é equivalente a chamar o cmdlet [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) no arquivo de catálogo.</span><span class="sxs-lookup"><span data-stu-id="fd354-149">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet on the catalog file.</span></span> <span data-ttu-id="fd354-150">Os usuários também podem ignorar qualquer arquivo durante a validação usando o parâmetro *-FilesToSkip* .</span><span class="sxs-lookup"><span data-stu-id="fd354-150">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

### <a name="module-analysis-cache"></a><span data-ttu-id="fd354-151">Cache de análise do módulo</span><span class="sxs-lookup"><span data-stu-id="fd354-151">Module Analysis Cache</span></span>

<span data-ttu-id="fd354-152">Do WMF 5.1 em diante, o PowerShell fornece controle sobre o arquivo que é usado para cache de dados sobre um módulo, como os comandos que exporta.</span><span class="sxs-lookup"><span data-stu-id="fd354-152">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="fd354-153">Por padrão, esse cache é armazenado no arquivo `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="fd354-153">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="fd354-154">O cache normalmente é lido na inicialização ao procurar um comando e é gravado em um thread em segundo plano em algum momento após a importação de um módulo.</span><span class="sxs-lookup"><span data-stu-id="fd354-154">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="fd354-155">Para alterar o local padrão do cache, defina a variável de ambiente `$env:PSModuleAnalysisCachePath` antes de iniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd354-155">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="fd354-156">As alterações a esta variável de ambiente afetarão apenas processos filhos.</span><span class="sxs-lookup"><span data-stu-id="fd354-156">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="fd354-157">O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos.</span><span class="sxs-lookup"><span data-stu-id="fd354-157">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="fd354-158">Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fd354-158">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="fd354-159">Isso define o caminho para um dispositivo inválido.</span><span class="sxs-lookup"><span data-stu-id="fd354-159">This sets the path to an invalid device.</span></span> <span data-ttu-id="fd354-160">Se o PowerShell não conseguir gravar no caminho, nenhum erro será retornado, mas você poderá ver relatórios de erro usando um rastreamento:</span><span class="sxs-lookup"><span data-stu-id="fd354-160">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

<span data-ttu-id="fd354-161">Ao gravar o cache, o PowerShell verificará se há módulos que não existem mais para evitar um cache desnecessariamente grande.</span><span class="sxs-lookup"><span data-stu-id="fd354-161">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="fd354-162">Às vezes, essas verificações não são desejáveis, o que, nesse caso, você pode desativá-las configurando:</span><span class="sxs-lookup"><span data-stu-id="fd354-162">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="fd354-163">Definir essa variável de ambiente entrará em vigor imediatamente no processo atual.</span><span class="sxs-lookup"><span data-stu-id="fd354-163">Setting this environment variable will take effect immediately in the current process.</span></span>

### <a name="specifying-module-version"></a><span data-ttu-id="fd354-164">Especificando a versão do módulo</span><span class="sxs-lookup"><span data-stu-id="fd354-164">Specifying module version</span></span>

<span data-ttu-id="fd354-165">No WMF 5.1, o `using module` comporta-se da mesma maneira que outras construções relacionadas ao módulo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd354-165">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="fd354-166">Anteriormente, não era possível especificar uma versão de módulo específica; se houvesse várias versões presentes, isso resultaria em um erro.</span><span class="sxs-lookup"><span data-stu-id="fd354-166">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="fd354-167">No WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="fd354-167">In WMF 5.1:</span></span>

* <span data-ttu-id="fd354-168">Você pode usar o [Construtor ModuleSpecification (tabela de hash)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span><span class="sxs-lookup"><span data-stu-id="fd354-168">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span></span>
  <span data-ttu-id="fd354-169">Essa tabela de hash tem o mesmo formato que `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="fd354-169">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="fd354-170">**Exemplo:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="fd354-170">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="fd354-171">Se houver várias versões do módulo, o PowerShell usará a **mesma lógica de resolução** que `Import-Module` e não retornará um erro – o mesmo comportamento que `Import-Module` e `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="fd354-171">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

### <a name="improvements-to-pester"></a><span data-ttu-id="fd354-172">Melhorias no Pester</span><span class="sxs-lookup"><span data-stu-id="fd354-172">Improvements to Pester</span></span>

<span data-ttu-id="fd354-173">No WMF 5,1, a versão do Pester que acompanha o PowerShell foi atualizada de 3.3.5 para 3.4.0, com a adição do GitHub [PR # 484](https://github.com/pester/Pester/pull/484), que permite um melhor comportamento para Pester no nano Server.</span><span class="sxs-lookup"><span data-stu-id="fd354-173">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of GitHub [PR# 484](https://github.com/pester/Pester/pull/484), which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="fd354-174">Você pode revisar as alterações nas versões 3.3.5 a 3.4.0 inspecionando o arquivo ChangeLog.md em: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span><span class="sxs-lookup"><span data-stu-id="fd354-174">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>

## <a name="keywords"></a><span data-ttu-id="fd354-175">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="fd354-175">KEYWORDS</span></span>

<span data-ttu-id="fd354-176">O que há de novo no Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="fd354-176">What's New in Windows PowerShell 5.1</span></span>
