---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,instalação
title: Notas de versão do WMF 5.x
ms.openlocfilehash: 8924240a4bbedcd34bc68b7cacdd23189a3716d6
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147576"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a><span data-ttu-id="afc84-103">Notas de versão do Windows Management Framework (WMF) 5.x</span><span class="sxs-lookup"><span data-stu-id="afc84-103">Windows Management Framework (WMF) 5.x Release Notes</span></span>

## <a name="wmf-50-changes"></a><span data-ttu-id="afc84-104">Alterações do WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="afc84-104">WMF 5.0 Changes</span></span>

- <span data-ttu-id="afc84-105">O PowerShell 5.0 adiciona um novo fluxo **Information** estruturado</span><span class="sxs-lookup"><span data-stu-id="afc84-105">PowerShell 5.0 adds a new structured **Information** stream</span></span>
- <span data-ttu-id="afc84-106">Aprimoramentos do DSC, incluindo quatro novos recursos de DSC:</span><span class="sxs-lookup"><span data-stu-id="afc84-106">Improvements to DSC including four new DSC resources:</span></span>
  - <span data-ttu-id="afc84-107">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="afc84-107">WindowsFeatureSet</span></span>
  - <span data-ttu-id="afc84-108">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="afc84-108">WindowsOptionalFeatureSet</span></span>
  - <span data-ttu-id="afc84-109">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="afc84-109">ServiceSet</span></span>
  - <span data-ttu-id="afc84-110">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="afc84-110">ProcessSet</span></span>
- <span data-ttu-id="afc84-111">Foi adicionada a Administração Suficiente para permitir a administração baseada em funções por meio da comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-111">Added Just Enough Administration to enable role-based administration through PowerShell remoting</span></span>
- <span data-ttu-id="afc84-112">O PowerShell 5.0 estende a linguagem para incluir enumerações e classes definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="afc84-112">PowerShell 5.0 extends the language to include user-defined classes and enumerations</span></span>
- <span data-ttu-id="afc84-113">Os recursos de depuração no ISE do PowerShell foram aprimorados e a depuração remota foi adicionada</span><span class="sxs-lookup"><span data-stu-id="afc84-113">Improved debugging features in PowerShell ISE and added remote debugging</span></span>
- <span data-ttu-id="afc84-114">Os módulos PowerShellGet e PackageManagement foram adicionados</span><span class="sxs-lookup"><span data-stu-id="afc84-114">Added the PowerShellGet and PackageManagement modules</span></span>
- <span data-ttu-id="afc84-115">As transcrições e logs de script do PowerShell foram aprimorados</span><span class="sxs-lookup"><span data-stu-id="afc84-115">Enhanced PowerShell script logging and transcripts</span></span>
- <span data-ttu-id="afc84-116">Foram adicionados cmdlets da CMS (Sintaxe de Mensagem Criptografada)</span><span class="sxs-lookup"><span data-stu-id="afc84-116">Add Cryptographic Message Syntax cmdlets</span></span>
- <span data-ttu-id="afc84-117">O WMF 5.0 inclui o módulo NetworkSwitchManager para o Windows</span><span class="sxs-lookup"><span data-stu-id="afc84-117">WMF 5.0 includes the NetworkSwitchManager module for Windows</span></span>
- <span data-ttu-id="afc84-118">Adicionado o módulo Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="afc84-118">Added the Microsoft.PowerShell.ODataUtils module</span></span>
- <span data-ttu-id="afc84-119">Adicionado suporte para SIL (Log de Inventário de Software)</span><span class="sxs-lookup"><span data-stu-id="afc84-119">Added support for Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="afc84-120">Cmdlets novos ou atualizados do servidor em resposta às questões e solicitações dos usuários</span><span class="sxs-lookup"><span data-stu-id="afc84-120">Sever new or update cmdlets in response to user requests and issues</span></span>

## <a name="wmf-51-changes"></a><span data-ttu-id="afc84-121">Alterações do WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="afc84-121">WMF 5.1 Changes</span></span>

<span data-ttu-id="afc84-122">O WMF 5.1 inclui os componentes PowerShell, WMI, WinRM e SIL (Log de Inventário de Software) que foram lançados com o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="afc84-122">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span> <span data-ttu-id="afc84-123">O WMF 5.1 pode ser instalado no Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 e 2012 R2 e fornece diversos aprimoramentos para o WMF 5.0, incluindo:</span><span class="sxs-lookup"><span data-stu-id="afc84-123">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides several improvements over WMF 5.0 including:</span></span>

- <span data-ttu-id="afc84-124">Novos cmdlets</span><span class="sxs-lookup"><span data-stu-id="afc84-124">New cmdlets</span></span>
- <span data-ttu-id="afc84-125">Os aprimoramentos do PowerShellGet incluem a imposição de módulos assinados e a instalação de módulos JEA</span><span class="sxs-lookup"><span data-stu-id="afc84-125">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="afc84-126">Suporte acrescentado para o PackageManagement para Contêineres, Configuração de CBS, configuração baseada em EXE, pacotes CAB</span><span class="sxs-lookup"><span data-stu-id="afc84-126">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="afc84-127">Melhorias de depuração para classes DSC e PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-127">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="afc84-128">Aprimoramentos de segurança, incluindo a imposição de módulos de catálogo assinado provenientes do Servidor de Recepção e ao usar cmdlets do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="afc84-128">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="afc84-129">Respostas para diversos problemas e solicitações de usuários</span><span class="sxs-lookup"><span data-stu-id="afc84-129">Responses to a number of user requests and issues</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc84-130">Antes de instalar o WMF 5.1 no Windows Server 2008 ou no Windows 7, confirme se o WMF 3.0 não está instalado.</span><span class="sxs-lookup"><span data-stu-id="afc84-130">Before you install WMF 5.1 on Windows Server 2008 or Windows 7, confirm that WMF 3.0 isn't installed.</span></span> <span data-ttu-id="afc84-131">Para obter mais informações, confira [Pré-requisitos do WMF 5.1 para Windows Server 2008 R2 SP1 e Windows 7 SP1](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1).</span><span class="sxs-lookup"><span data-stu-id="afc84-131">For more information, see [WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1).</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="afc84-132">Edições do PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-132">PowerShell Editions</span></span>

<span data-ttu-id="afc84-133">Da versão 5.1 em diante, o PowerShell está disponível em edições diferentes que denotam diferentes conjuntos de recursos e compatibilidade de plataforma.</span><span class="sxs-lookup"><span data-stu-id="afc84-133">Starting with version 5.1, PowerShell is available in different editions that denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="afc84-134">**Desktop Edition:** criada no .NET Framework, fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="afc84-134">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="afc84-135">**Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="afc84-135">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="learn-more-about-using-powershell-editions"></a><span data-ttu-id="afc84-136">Saiba mais sobre como usar as edições do PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-136">Learn more about using PowerShell Editions</span></span>

- [<span data-ttu-id="afc84-137">Determinar a edição em execução do PowerShell usando $PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="afc84-137">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="afc84-138">Filtrar resultados de Get-Module por CompatiblePSEditions usando o parâmetro PSEdition</span><span class="sxs-lookup"><span data-stu-id="afc84-138">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="afc84-139">Impedir a execução do script, a menos que seja ele executado em uma edição compatível do PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-139">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="afc84-140">Declarar a compatibilidade de um módulo para versões específicas do PowerShell</span><span class="sxs-lookup"><span data-stu-id="afc84-140">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a><span data-ttu-id="afc84-141">Cache de análise do módulo</span><span class="sxs-lookup"><span data-stu-id="afc84-141">Module Analysis Cache</span></span>

<span data-ttu-id="afc84-142">Do WMF 5.1 em diante, o PowerShell fornece controle sobre o arquivo que é usado para cache de dados sobre um módulo, como os comandos que exporta.</span><span class="sxs-lookup"><span data-stu-id="afc84-142">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="afc84-143">Por padrão, esse cache é armazenado no arquivo `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="afc84-143">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="afc84-144">O cache normalmente é lido na inicialização ao procurar um comando e é gravado em um thread em segundo plano em algum momento após a importação de um módulo.</span><span class="sxs-lookup"><span data-stu-id="afc84-144">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="afc84-145">Para alterar o local padrão do cache, defina a variável de ambiente `$env:PSModuleAnalysisCachePath` antes de iniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afc84-145">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="afc84-146">As alterações a esta variável de ambiente afetarão apenas processos filhos.</span><span class="sxs-lookup"><span data-stu-id="afc84-146">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="afc84-147">O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos.</span><span class="sxs-lookup"><span data-stu-id="afc84-147">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="afc84-148">Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="afc84-148">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="afc84-149">Isso define o caminho para um dispositivo inválido.</span><span class="sxs-lookup"><span data-stu-id="afc84-149">This sets the path to an invalid device.</span></span> <span data-ttu-id="afc84-150">Se o PowerShell não conseguir gravar no caminho, nenhum erro será retornado, mas você poderá ver relatórios de erro usando um rastreamento:</span><span class="sxs-lookup"><span data-stu-id="afc84-150">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="afc84-151">Ao gravar o cache, o PowerShell verificará se há módulos que não existem mais para evitar um cache desnecessariamente grande.</span><span class="sxs-lookup"><span data-stu-id="afc84-151">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="afc84-152">Às vezes, essas verificações não são desejáveis, o que, nesse caso, você pode desativá-las configurando:</span><span class="sxs-lookup"><span data-stu-id="afc84-152">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="afc84-153">Definir essa variável de ambiente entrará em vigor imediatamente no processo atual.</span><span class="sxs-lookup"><span data-stu-id="afc84-153">Setting this environment variable will take effect immediately in the current process.</span></span>

## <a name="specifying-module-version"></a><span data-ttu-id="afc84-154">Especificando a versão do módulo</span><span class="sxs-lookup"><span data-stu-id="afc84-154">Specifying module version</span></span>

<span data-ttu-id="afc84-155">No WMF 5.1, o `using module` comporta-se da mesma maneira que outras construções relacionadas ao módulo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afc84-155">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span>
<span data-ttu-id="afc84-156">Anteriormente, não era possível especificar uma versão de módulo específica; se houvesse várias versões presentes, isso resultaria em um erro.</span><span class="sxs-lookup"><span data-stu-id="afc84-156">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="afc84-157">No WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="afc84-157">In WMF 5.1:</span></span>

- <span data-ttu-id="afc84-158">Você pode usar o [Construtor ModuleSpecification (tabela de hash)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="afc84-158">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

  <span data-ttu-id="afc84-159">Essa tabela de hash tem o mesmo formato que `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="afc84-159">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="afc84-160">**Exemplo:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="afc84-160">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

- <span data-ttu-id="afc84-161">Se houver várias versões do módulo, o PowerShell usará a **mesma lógica de resolução** que `Import-Module` e não retornará um erro – o mesmo comportamento que `Import-Module` e `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="afc84-161">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

## <a name="improvements-to-pester"></a><span data-ttu-id="afc84-162">Melhorias no Pester</span><span class="sxs-lookup"><span data-stu-id="afc84-162">Improvements to Pester</span></span>

<span data-ttu-id="afc84-163">No WMF 5.1, a versão do Pester fornecida com o PowerShell foi atualizada de 3.3.5 para 3.4.0.</span><span class="sxs-lookup"><span data-stu-id="afc84-163">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0.</span></span>
<span data-ttu-id="afc84-164">Essa atualização permite melhorar o comportamento do Pester no Nano Server.</span><span class="sxs-lookup"><span data-stu-id="afc84-164">This update enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="afc84-165">As alterações no Pester podem ser analisadas inspecionando o [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) no repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="afc84-165">You can review the changes in Pest by inspecting the [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) in the GitHub repository.</span></span>
