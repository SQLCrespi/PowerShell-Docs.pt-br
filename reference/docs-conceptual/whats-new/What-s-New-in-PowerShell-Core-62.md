---
title: Novidades no PowerShell Core 6.2
description: Novos recursos e alterações liberados no PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 6a0da8a410e602ae3963e0bc7bace745317d7d4b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058090"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="9312e-103">Novidades no PowerShell Core 6.2</span><span class="sxs-lookup"><span data-stu-id="9312e-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="9312e-104">A versão 6.2 do PowerShell Core concentrou-se nas melhorias de desempenho, correções de bug e aprimoramentos secundários de cmdlet e linguagem que elevam a qualidade.</span><span class="sxs-lookup"><span data-stu-id="9312e-104">The PowerShell Core 6.2 release focused on performance improvements, bug fixes, and smaller cmdlet and language enhancements that improve the quality.</span></span> <span data-ttu-id="9312e-105">Para ver uma lista completa de melhorias, consulte nossos [logs de alterações](https://github.com/PowerShell/PowerShell/releases) no GitHub.</span><span class="sxs-lookup"><span data-stu-id="9312e-105">To see a full list of improvements, check out our detailed [changelogs](https://github.com/PowerShell/PowerShell/releases) on GitHub.</span></span>

## <a name="experimental-features"></a><span data-ttu-id="9312e-106">Recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="9312e-106">Experimental Features</span></span>

<span data-ttu-id="9312e-107">Anteriormente, habilitamos o suporte aos [Recursos experimentais][].</span><span class="sxs-lookup"><span data-stu-id="9312e-107">Previously, we enabled support for [Experimental Features][].</span></span> <span data-ttu-id="9312e-108">Na versão 6.2, temos quatro recursos experimentais para testar. Forneça seus comentários para que possamos fazer melhorias e decidir se vale a pena promover o recurso para a versão final.</span><span class="sxs-lookup"><span data-stu-id="9312e-108">In the 6.2 release, we have four experimental features to try out. Please provide feedback so we can make improvements and to decide whether the feature is worth promoting to mainstream status.</span></span>

<span data-ttu-id="9312e-109">Use `Get-ExperimentalFeature` para obter uma lista de recursos experimentais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9312e-109">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="9312e-110">Você pode habilitar ou desabilitar esses recursos com `Enable-ExperimentalFeature` e `Disable-ExperimentalFeature`.</span><span class="sxs-lookup"><span data-stu-id="9312e-110">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

### <a name="command-not-found-suggestions"></a><span data-ttu-id="9312e-111">Sugestões de comando não encontrado</span><span class="sxs-lookup"><span data-stu-id="9312e-111">Command Not Found Suggestions</span></span>

<span data-ttu-id="9312e-112">Esse recurso usa a correspondência difusa para localizar sugestões de comandos ou cmdlets que você possa ter digitado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="9312e-112">This feature uses fuzzy matching to find suggestions for commands or cmdlets you may have mistyped.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSCommandNotFoundSuggestion
```

#### <a name="example"></a><span data-ttu-id="9312e-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9312e-113">Example</span></span>

<span data-ttu-id="9312e-114">Neste exemplo, o nome do cmdlet grafado incorretamente tem correspondência difusa com várias sugestões, das mais prováveis às menos prováveis.</span><span class="sxs-lookup"><span data-stu-id="9312e-114">In this example, the misspelled cmdlet name is fuzzy matched to several suggestions from most likely to least likely.</span></span>

```powershell
Get-Commnd
```

```Output
Get-Commnd : The term 'Get-Commnd' is not recognized as the name of a cmdlet, function, script file, or operable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-Commnd
+ ~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (Get-Commnd:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CommandNotFoundException


Suggestion [4,General]: The most similar commands are: Get-Command, Get-Content, Get-Job, Get-Module, Get-Event, Get-Host, Get-Member, Get-Item, Set-Content.
```

### <a name="implicit-remoting-batching"></a><span data-ttu-id="9312e-115">Envio em lote para comunicação remota implícita</span><span class="sxs-lookup"><span data-stu-id="9312e-115">Implicit Remoting Batching</span></span>

<span data-ttu-id="9312e-116">Ao usar a [comunicação remota implícita](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) em um pipeline, o PowerShell trata cada comando no pipeline de maneira independente.</span><span class="sxs-lookup"><span data-stu-id="9312e-116">When using [implicit remoting](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) in a pipeline, PowerShell treats each command in the pipeline independently.</span></span> <span data-ttu-id="9312e-117">Os objetos são repetidamente serializados e `de-serialized` entre o sistema remoto e cliente durante a execução do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9312e-117">Objects are repeatedly serialized and `de-serialized` between the client and remote system over the execution of the pipeline.</span></span>

<span data-ttu-id="9312e-118">Com esse recurso, o PowerShell analisa o pipeline para determinar se o comando é seguro para execução e se existe no sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9312e-118">With this feature, PowerShell analyzes the pipeline to determine if the command is safe to run and it exists on the target system.</span></span> <span data-ttu-id="9312e-119">Em caso positivo, o PowerShell executa todo o pipeline remotamente e serializa e `de-serializes` os resultados de volta somente para o cliente.</span><span class="sxs-lookup"><span data-stu-id="9312e-119">When true, PowerShell executes the entire pipeline remotely and only serializes and `de-serializes` the results back to the client.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSImplicitRemotingBatching
```

<span data-ttu-id="9312e-120">Um teste real de `Get-Process | Sort-Object` pelo localhost diminui de 10 s a 15 segundos para 20 ms a 30 **milissegundos**.</span><span class="sxs-lookup"><span data-stu-id="9312e-120">A real-world test of `Get-Process | Sort-Object` over localhost decreases from 10-15 seconds to 20-30 **milliseconds**.</span></span> <span data-ttu-id="9312e-121">O recurso só precisa ser habilitado no cliente.</span><span class="sxs-lookup"><span data-stu-id="9312e-121">The feature only needs to be enabled on the client.</span></span> <span data-ttu-id="9312e-122">Não é preciso fazer qualquer alteração no servidor.</span><span class="sxs-lookup"><span data-stu-id="9312e-122">No changes are required on the server.</span></span>

### <a name="temp-drive"></a><span data-ttu-id="9312e-123">Unidade Temp</span><span class="sxs-lookup"><span data-stu-id="9312e-123">Temp Drive</span></span>

```powershell
Enable-ExperimentalFeature -Name PSTempDrive
```

<span data-ttu-id="9312e-124">Se estiver usando o PowerShell Core em diferentes sistemas operacionais, você descobrirá que a variável de ambiente para encontrar o diretório temporário é diferente no Windows, macOS e Linux!</span><span class="sxs-lookup"><span data-stu-id="9312e-124">If you're using PowerShell Core on different operating systems, you'll discover that the environment variable for finding the temporary directory is different on Windows, macOS, and Linux!</span></span> <span data-ttu-id="9312e-125">Com esse recurso, você obtém um [PSDrive][] chamado `Temp:` que é mapeado automaticamente para a pasta temporária do sistema operacional que você está usando.</span><span class="sxs-lookup"><span data-stu-id="9312e-125">With this feature, you get a [PSDrive][] called `Temp:` that is automatically mapped to the temporary folder for the operating system you are using.</span></span>

#### <a name="example"></a><span data-ttu-id="9312e-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9312e-126">Example</span></span>

```powershell
PS> "Hello World!" > Temp:/hello.txt
PS> `Get-Content` Temp:/hello.txt
Hello World!
```

<span data-ttu-id="9312e-127">Esteja ciente de que os comandos do arquivo nativo (como `ls` no Linux) não reconhecem PSDrives e não verão essa unidade `Temp:`.</span><span class="sxs-lookup"><span data-stu-id="9312e-127">Be aware that native file commands (like `ls` on Linux) are not aware of PSDrives and won't see this `Temp:` drive.</span></span>

### <a name="abbreviation-expansion"></a><span data-ttu-id="9312e-128">Expansão de abreviação</span><span class="sxs-lookup"><span data-stu-id="9312e-128">Abbreviation Expansion</span></span>

<span data-ttu-id="9312e-129">Os cmdlets do PowerShell costumam ter nomes descritivos.</span><span class="sxs-lookup"><span data-stu-id="9312e-129">PowerShell cmdlets are expected to have descriptive nouns.</span></span> <span data-ttu-id="9312e-130">Isso resulta em nomes longos que são mais difíceis de digitar.</span><span class="sxs-lookup"><span data-stu-id="9312e-130">This results in long names that are more difficult to type.</span></span> <span data-ttu-id="9312e-131">Esse recurso permite que você digite apenas os caracteres maiúsculos do cmdlet e use o preenchimento com Tab para encontrar uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="9312e-131">This feature allows you to just type the uppercase characters of the cmdlet and use tab-completion to find a match.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSUseAbbreviationExpansion
```

#### <a name="example"></a><span data-ttu-id="9312e-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9312e-132">Example</span></span>

```powershell
PS> i-arsavsf
```

<span data-ttu-id="9312e-133">Se você pressionar Tab e tiver o módulo [Az](https://www.powershellgallery.com/packages/Az) do Azure PowerShell instalado, o cmdlet será preenchido automaticamente desta forma:</span><span class="sxs-lookup"><span data-stu-id="9312e-133">If you hit tab, and have the Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az) module installed, it will autocomplete to:</span></span>

```Output
PS> Import-AzRecoveryServicesAsrVaultSettingsFile
```

> [!NOTE]
> <span data-ttu-id="9312e-134">Esse recurso deve ser usado de modo interativo.</span><span class="sxs-lookup"><span data-stu-id="9312e-134">This feature is intended to be used interactively.</span></span> <span data-ttu-id="9312e-135">As formas abreviadas dos cmdlets não podem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="9312e-135">Abbreviated forms of cmdlets can't be executed.</span></span>
> <span data-ttu-id="9312e-136">Esse recurso não é uma substituição de aliases.</span><span class="sxs-lookup"><span data-stu-id="9312e-136">This feature is not a replacement for aliases.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="9312e-137">Alterações da falha</span><span class="sxs-lookup"><span data-stu-id="9312e-137">Breaking Changes</span></span>

- <span data-ttu-id="9312e-138">Correção do comportamento `-NoEnumerate` em `Write-Output` para ser consistente com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9312e-138">Fix `-NoEnumerate` behavior in `Write-Output` to be consistent with Windows PowerShell.</span></span> <span data-ttu-id="9312e-139">(nº 9069)</span><span class="sxs-lookup"><span data-stu-id="9312e-139">(#9069)</span></span>
- <span data-ttu-id="9312e-140">Transformação do resultado de `Join-String -InputObject 1,2,3` para ser igual ao resultado de `1,2,3 | Join-String` (nº 8611) (Obrigado @sethvs!)</span><span class="sxs-lookup"><span data-stu-id="9312e-140">Make `Join-String -InputObject 1,2,3` result equal to `1,2,3 | Join-String` result (#8611) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="9312e-141">Adição de `-Stable` a `Sort-Object` e testes relacionados (nº 7862) (Obrigado @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="9312e-141">Add `-Stable` to `Sort-Object` and related tests (#7862) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="9312e-142">Aprimoramento do cmdlet `Start-Sleep` para aceitar fração de segundos (nº 8537) (Obrigado @Prototyyppi!)</span><span class="sxs-lookup"><span data-stu-id="9312e-142">Improve `Start-Sleep` cmdlet to accept fractional seconds (#8537) (Thanks @Prototyyppi!)</span></span>
- <span data-ttu-id="9312e-143">Alteração da tabela de hash para usar OrdinalIgnoreCase de modo a ser `case-insensitive` em todas as Culturas (nº 8566)</span><span class="sxs-lookup"><span data-stu-id="9312e-143">Change hashtable to use OrdinalIgnoreCase to be `case-insensitive` in all Cultures (#8566)</span></span>
- <span data-ttu-id="9312e-144">Correção de **LiteralPath** em `Import-Csv` para associação à saída `Get-ChildItem` (nº 8277) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-144">Fix **LiteralPath** in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-145">Não ignora mais uma coluna sem nome se o delimitador de aspas duplas for usado em `Import-Csv` (nº 7899) (Obrigado @Topping!)</span><span class="sxs-lookup"><span data-stu-id="9312e-145">No longer skips a column without name if double quote delimiter is used in `Import-Csv` (#7899) (Thanks @Topping!)</span></span>
- <span data-ttu-id="9312e-146">`Get-ExperimentalFeature` não tem mais a opção `-ListAvailable` (nº 8318)</span><span class="sxs-lookup"><span data-stu-id="9312e-146">`Get-ExperimentalFeature` no longer has `-ListAvailable` switch (#8318)</span></span>
- <span data-ttu-id="9312e-147">O parâmetro de depuração agora define `$DebugPreference` como **Continuar** ao invés de **Consultar** (nº 8195) (Obrigado @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="9312e-147">Debug parameter now sets `$DebugPreference` to **Continue** instead of **Inquire** (#8195) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="9312e-148">Cumprimento de `-OutputFormat` se especificado no comando não interativo, redirecionado, codificado usado com pwsh (nº 8115)</span><span class="sxs-lookup"><span data-stu-id="9312e-148">Honor `-OutputFormat` if specified in non-interactive, redirected, encoded command used with pwsh (#8115)</span></span>
- <span data-ttu-id="9312e-149">Carregamento do assembly do caminho base do módulo antes de tentar carregar do GAC (nº 8073)</span><span class="sxs-lookup"><span data-stu-id="9312e-149">Load assembly from module base path before trying to load from the GAC (#8073)</span></span>
- <span data-ttu-id="9312e-150">Remoção do til dos pacotes de visualização do Linux (nº 8244)</span><span class="sxs-lookup"><span data-stu-id="9312e-150">Remove tilde from Linux preview packages (#8244)</span></span>
- <span data-ttu-id="9312e-151">Movimentação do processamento de `-WorkingDirectory` antes do processamentos dos perfis (nº 8079)</span><span class="sxs-lookup"><span data-stu-id="9312e-151">Move processing of `-WorkingDirectory` before processing of profiles (#8079)</span></span>
- <span data-ttu-id="9312e-152">Não adicione a variável de ambiente `PATHEXT` no Unix (nº 7697) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-152">Do not add `PATHEXT` environment variable on Unix (#7697) (Thanks @iSazonov!)</span></span>

## <a name="known-issues"></a><span data-ttu-id="9312e-153">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="9312e-153">Known Issues</span></span>

- <span data-ttu-id="9312e-154">A comunicação remota em plataformas ARM do Windows IOT apresenta um problema de carregamento de módulos.</span><span class="sxs-lookup"><span data-stu-id="9312e-154">Remoting on Windows IOT ARM platforms has an issue loading modules.</span></span> <span data-ttu-id="9312e-155">Consulte (nº 8053)</span><span class="sxs-lookup"><span data-stu-id="9312e-155">See (#8053)</span></span>

## <a name="general-updates-and-fixes"></a><span data-ttu-id="9312e-156">Correções e atualizações gerais</span><span class="sxs-lookup"><span data-stu-id="9312e-156">General Updates and Fixes</span></span>

- <span data-ttu-id="9312e-157">Habilitação do preenchimento automático com Tab sem diferenciação entre maiúsculas e minúsculas para arquivos e pastas em sistemas de arquivos que diferenciam maiúsculas de minúsculas (nº 8128)</span><span class="sxs-lookup"><span data-stu-id="9312e-157">Enable case-insensitive tab completion for files and folders on case-sensitive filesystem (#8128)</span></span>
- <span data-ttu-id="9312e-158">Mudança de PSVersionInfo.PSVersion e PSVersionInfo.PSEdition para estado público (nº 8054) (Obrigado @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="9312e-158">Make PSVersionInfo.PSVersion and PSVersionInfo.PSEdition public (#8054) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="9312e-159">Adição de Inferência de Tipos para `$_` / `$PSItem` nos blocos `catch{ }` (nº 8020) (Obrigado @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="9312e-159">Add Type Inference for `$_` / `$PSItem` in `catch{ }` blocks (#8020) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="9312e-160">Correção da inferência de tipos da invocação de método estático (nº 8018) (Obrigado @SeeminglyScience!)</span><span class="sxs-lookup"><span data-stu-id="9312e-160">Fix static method invocation type inference (#8018) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="9312e-161">Criação de tipos deduzidos para `Select-Object`, `Group-Object`, **PSObject** e **Hashtable** (nº 7231) (Obrigado @powercode!)</span><span class="sxs-lookup"><span data-stu-id="9312e-161">Create inferred types for `Select-Object`, `Group-Object`, **PSObject** and **Hashtable** (#7231) (Thanks @powercode!)</span></span>
- <span data-ttu-id="9312e-162">Suporte ao método de chamada com parâmetros de tipo `ByRef-like` (nº 7721)</span><span class="sxs-lookup"><span data-stu-id="9312e-162">Support calling method with `ByRef-like` type parameters (#7721)</span></span>
- <span data-ttu-id="9312e-163">Tratamento de caso em que o caminho do módulo do Windows PowerShell já está no PSModulePath do ambiente (nº 7727)</span><span class="sxs-lookup"><span data-stu-id="9312e-163">Handle the case where the Windows PowerShell module path is already in the environment's PSModulePath (#7727)</span></span>
- <span data-ttu-id="9312e-164">Habilitação de cmdlets `SecureString` para sistemas diferentes do Windows pelo armazenamento do texto sem formatação (nº 9199)</span><span class="sxs-lookup"><span data-stu-id="9312e-164">Enable `SecureString` cmdlets for non-Windows by storing the plain text (#9199)</span></span>
- <span data-ttu-id="9312e-165">Aprimoramento da mensagem de erro em sistemas diferentes do Windows ao importar clixml com securestring (nº 7997)</span><span class="sxs-lookup"><span data-stu-id="9312e-165">Improve error message on non-Windows when importing clixml with securestring (#7997)</span></span>
- <span data-ttu-id="9312e-166">Adição do parâmetro ReplyTo a `Send-MailMessage` (nº 8727) (Obrigado @replicaJunction!)</span><span class="sxs-lookup"><span data-stu-id="9312e-166">Adding parameter ReplyTo to `Send-MailMessage` (#8727) (Thanks @replicaJunction!)</span></span>
- <span data-ttu-id="9312e-167">Adição da mensagem Obsoleto a `Send-MailMessage` (nº 9178)</span><span class="sxs-lookup"><span data-stu-id="9312e-167">Add Obsolete message to `Send-MailMessage` (#9178)</span></span>
- <span data-ttu-id="9312e-168">Correção de `Restart-Computer` para funcionar no `localhost` quando WinRM não estiver presente (nº 9160)</span><span class="sxs-lookup"><span data-stu-id="9312e-168">Fix `Restart-Computer` to work on `localhost` when WinRM is not present (#9160)</span></span>
- <span data-ttu-id="9312e-169">Fazer `Start-Job` lançar um erro de encerramento quando o PowerShell estiver sendo hospedado (nº 9128)</span><span class="sxs-lookup"><span data-stu-id="9312e-169">Make `Start-Job` throw terminating error when PowerShell is being hosted (#9128)</span></span>
- <span data-ttu-id="9312e-170">Adição de aceleradores e sufixos do tipo de estilo C# para ushort, uint, ulong e literais curtos (nº 7813) (Obrigado @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="9312e-170">Add C# style type accelerators and suffixes for ushort, uint, ulong, and short literals (#7813) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="9312e-171">Adição de novos sufixos para literais numéricos; consulte [about_Numeric_Literals][] (nº 7901) (Obrigado @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="9312e-171">Added new suffixes for numeric literals - see [about_Numeric_Literals][] (#7901) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="9312e-172">Relato correto do nível de impacto quando SupportsShouldProcess não é definido como 'true' (nº 8209) (Obrigado @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="9312e-172">Correctly Report impact level when SupportsShouldProcess is not set to 'true' (#8209) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="9312e-173">Correção dos problemas do conjunto de caracteres de solicitação nos cmdlets da Web (nº 8742) (Obrigado @markekraus!)</span><span class="sxs-lookup"><span data-stu-id="9312e-173">Fix Request Charset Issues in Web Cmdlets (#8742) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="9312e-174">Correção do problema de esperar `100-continue` com cmdlets da Web (nº 8679) (Obrigado @markekraus!)</span><span class="sxs-lookup"><span data-stu-id="9312e-174">Fix Expect `100-continue` issue with Web Cmdlets (#8679) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="9312e-175">Correção do problema de bloqueio de arquivo com cmdlets da Web (nº 7676) (Obrigado @Claustn!)</span><span class="sxs-lookup"><span data-stu-id="9312e-175">Fix file blocking issue with web cmdlets (#7676) (Thanks @Claustn!)</span></span>
- <span data-ttu-id="9312e-176">Correção do problema de análise da página de código em `Invoke-RestMethod` (nº 8694) (Obrigado @markekraus!)</span><span class="sxs-lookup"><span data-stu-id="9312e-176">Fix code page parsing issue in `Invoke-RestMethod` (#8694) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="9312e-177">Refatoração de `ConvertTo-Json` para exposição de JsonObject.ConvertToJson como uma API pública (nº 8682)</span><span class="sxs-lookup"><span data-stu-id="9312e-177">Refactor `ConvertTo-Json` to expose JsonObject.ConvertToJson as a public API (#8682)</span></span>
- <span data-ttu-id="9312e-178">Adição de profundidade máxima configurável em `ConvertFrom-Json` com -Depth (nº 8199) (Obrigado @louistio!)</span><span class="sxs-lookup"><span data-stu-id="9312e-178">Add configurable maximum depth in `ConvertFrom-Json` with -Depth (#8199) (Thanks @louistio!)</span></span>
- <span data-ttu-id="9312e-179">Adição do parâmetro EscapeHandling no cmdlet `ConvertTo-Json` (nº 7775) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-179">Add EscapeHandling parameter in `ConvertTo-Json` cmdlet (#7775) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-180">Adição de `-CustomPipeName` a pwsh e `Enter-PSHostProcess` (nº 8889)</span><span class="sxs-lookup"><span data-stu-id="9312e-180">Add `-CustomPipeName` to pwsh and `Enter-PSHostProcess` (#8889)</span></span>
- <span data-ttu-id="9312e-181">Habilitação da criação de links simbólicos relativos no Windows com `New-Item` (nº 8783)</span><span class="sxs-lookup"><span data-stu-id="9312e-181">Enable creating relative symbolic links on Windows with `New-Item` (#8783)</span></span>
- <span data-ttu-id="9312e-182">Permissão para que usuários do Windows no modo de desenvolvedor criem links simbólicos sem elevação (nº 8534)</span><span class="sxs-lookup"><span data-stu-id="9312e-182">Allow Windows users in developer mode to create symlinks without elevation (#8534)</span></span>
- <span data-ttu-id="9312e-183">Habilitação de `Write-Information` para aceitar `$null` (nº 8774)</span><span class="sxs-lookup"><span data-stu-id="9312e-183">Enable `Write-Information` to accept `$null` (#8774)</span></span>
- <span data-ttu-id="9312e-184">Correção de `Get-Help` para funções avançadas com conteúdo de ajuda MAML (nº 8353)</span><span class="sxs-lookup"><span data-stu-id="9312e-184">Fix `Get-Help` for advanced functions with MAML help content (#8353)</span></span>
- <span data-ttu-id="9312e-185">Correção do problema PSTypeName `Get-Help` com -Parameter quando apenas um parâmetro é declarado (nº 8754) (Obrigado @pougetat!)</span><span class="sxs-lookup"><span data-stu-id="9312e-185">Fix `Get-Help` PSTypeName issue with -Parameter when only one parameter is declared (#8754) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="9312e-186">Correção do cálculo do token para `Get-Help` executado em ScriptBlock para ajuda de comentário.</span><span class="sxs-lookup"><span data-stu-id="9312e-186">Token calculation fix for `Get-Help` executed on ScriptBlock for comment help.</span></span> <span data-ttu-id="9312e-187">(nº 8238) (Obrigado @hubuk!)</span><span class="sxs-lookup"><span data-stu-id="9312e-187">(#8238) (Thanks @hubuk!)</span></span>
- <span data-ttu-id="9312e-188">Alteração do parâmetro -Parameter do cmdlet `Get-Help` para que ele aceite matrizes de cadeia de caracteres (nº 8454) (Obrigado @sethvs!)</span><span class="sxs-lookup"><span data-stu-id="9312e-188">Change `Get-Help` cmdlet -Parameter parameter so it accepts string arrays (#8454) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="9312e-189">Resolução de PAGER se o caminho contiver espaços (nº 8571) (Obrigado @pougetat!)</span><span class="sxs-lookup"><span data-stu-id="9312e-189">Resolve PAGER if its path contains spaces (#8571) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="9312e-190">Adição de prompt ao uso de `less` na função 'help' para orientar o usuário sobre como encerrar (nº 7998)</span><span class="sxs-lookup"><span data-stu-id="9312e-190">Add prompt to the use of `less` in the function 'help' to instruct user how to quit (#7998)</span></span>
- <span data-ttu-id="9312e-191">Adição de enumeração e tipos de caractere de suporte no cmdlet `Format-Hex` (nº 8191) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-191">Add support enum and char types in `Format-Hex` cmdlet (#8191) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-192">Remoção de ShouldProcess de `Format-Hex` (nº 8178)</span><span class="sxs-lookup"><span data-stu-id="9312e-192">Remove ShouldProcess from `Format-Hex` (#8178)</span></span>
- <span data-ttu-id="9312e-193">Adição dos novos parâmetros Offset e Count a `Format-Hex` e refatoração do cmdlet (nº 7877) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-193">Add new Offset and Count parameters to `Format-Hex` and refactor the cmdlet (#7877) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-194">Permissão de 'name' como uma chave de alias para 'label' em `ConvertTo-Html`, permissão para que a entrada 'width' seja um inteiro (nº 8426) (Obrigado @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="9312e-194">Allow 'name' as an alias key for 'label' in `ConvertTo-Html`, allow the 'width' entry to be an integer (#8426) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="9312e-195">Propriedades calculadas com base em scriptblock voltam a funcionar em `ConvertTo-Html` (nº 8427) (Obrigado @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="9312e-195">Make scriptblock based calculated properties work again in `ConvertTo-Html` (#8427) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="9312e-196">Adição do cmdlet `Join-String` para criação de texto da entrada do pipeline (nº 7660) (Obrigado @powercode!)</span><span class="sxs-lookup"><span data-stu-id="9312e-196">Add cmdlet `Join-String` for creating text from pipeline input (#7660) (Thanks @powercode!)</span></span>
- <span data-ttu-id="9312e-197">Correção da lógica do parâmetro FormatString do cmdlet `Join-String` (nº 8449) (Obrigado @sethvs!)</span><span class="sxs-lookup"><span data-stu-id="9312e-197">Fix `Join-String` cmdlet FormatString parameter logic (#8449) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="9312e-198">Alteração de `Clear-Host` para usar `$RAWUI` e liberação para trabalhar por comunicação remota (nº 8609)</span><span class="sxs-lookup"><span data-stu-id="9312e-198">Change `Clear-Host` back to using `$RAWUI` and clear to work over remoting (#8609)</span></span>
- <span data-ttu-id="9312e-199">Alteração de `Clear-Host` para a chamada simples de `[console]::clear` e remoção do alias de limpeza do Unix (nº 8603)</span><span class="sxs-lookup"><span data-stu-id="9312e-199">Change `Clear-Host` to simply called `[console]::clear` and remove clear alias from Unix (#8603)</span></span>
- <span data-ttu-id="9312e-200">Correção de LiteralPath em `Import-Csv` para associação à saída `Get-ChildItem` (nº 8277) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-200">Fix LiteralPath in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-201">A função de ajuda não deve usar pager para AliasHelpInfo (nº 8552)</span><span class="sxs-lookup"><span data-stu-id="9312e-201">help function shouldn't use pager for AliasHelpInfo (#8552)</span></span>
- <span data-ttu-id="9312e-202">Adição de `-UseMinimalHeader` a `Start-Transcript` para minimizar um cabeçalho de transcrição (nº 8402) (Obrigado @lukexjeremy!)</span><span class="sxs-lookup"><span data-stu-id="9312e-202">Add `-UseMinimalHeader` to `Start-Transcript` to minimize transcript header (#8402) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="9312e-203">Adição dos cmdlets `Enable-ExperimentalFeature` e `Disable-ExperimentalFeature` (nº 8318)</span><span class="sxs-lookup"><span data-stu-id="9312e-203">Add `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature` cmdlets (#8318)</span></span>
- <span data-ttu-id="9312e-204">Exposição de todos os cmdlets de **PSDiagnostics** se logman.exe estiver disponível (nº 8366)</span><span class="sxs-lookup"><span data-stu-id="9312e-204">Expose all cmdlets from **PSDiagnostics** if logman.exe is available (#8366)</span></span>
- <span data-ttu-id="9312e-205">Remoção do parâmetro **Persist** de `New-PSDrive` em plataforma `non-Windows` (nº 8291) (Obrigado @lukexjeremy!)</span><span class="sxs-lookup"><span data-stu-id="9312e-205">Remove **Persist** parameter from `New-PSDrive` on `non-Windows` platform (#8291) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="9312e-206">Adição de suporte para `cd +` (nº 7206) (Obrigado @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="9312e-206">Add support for `cd +` (#7206) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="9312e-207">Habilitação de `Set-Location -LiteralPath` para trabalhar com pastas chamadas - e + (nº 8089)</span><span class="sxs-lookup"><span data-stu-id="9312e-207">Enable `Set-Location -LiteralPath` to work with folders named - and + (#8089)</span></span>
- <span data-ttu-id="9312e-208">`Test-Path` retorna `$false` quando é fornecido um valor de caminho vazio ou `$null` (nº 8080) (Obrigado @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="9312e-208">`Test-Path` returns `$false` when given an empty or `$null` path value (#8080) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="9312e-209">Permissão para que o parâmetro dinâmico seja retornado mesmo se o caminho não corresponder a qualquer provedor (nº 7957)</span><span class="sxs-lookup"><span data-stu-id="9312e-209">Allow dynamic parameter to be returned even if path does not match any provider (#7957)</span></span>
- <span data-ttu-id="9312e-210">Suporte a `Get-PSHostProcessInfo` e `Enter-PSHostProcess` em plataformas Unix (nº 8232)</span><span class="sxs-lookup"><span data-stu-id="9312e-210">Support `Get-PSHostProcessInfo` and `Enter-PSHostProcess` on Unix platforms (#8232)</span></span>
- <span data-ttu-id="9312e-211">Redução de alocações no cmdlet `Get-Content` (nº 8103) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-211">Reduce allocations in `Get-Content` cmdlet (#8103) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-212">Habilitação de `Add-Content` para compartilhar acesso de leitura com outras ferramentas durante a gravação de conteúdo (nº 8091)</span><span class="sxs-lookup"><span data-stu-id="9312e-212">Enable `Add-Content` to share read access with other tools while writing content (#8091)</span></span>
- <span data-ttu-id="9312e-213">`Get/Add-Content` gera erro aprimorado ao visar um contêiner (nº 7823) (Obrigado @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="9312e-213">`Get/Add-Content` throws improved error when targeting a container (#7823) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="9312e-214">Adição dos parâmetros `-Name`, `-NoUserOverrides` e `-ListAvailable` ao cmdlet `Get-Culture` (nº 7702) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-214">Add `-Name`, `-NoUserOverrides` and `-ListAvailable` parameters to `Get-Culture` cmdlet (#7702) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-215">Adição de atributo unificado para preenchimento do parâmetro **Encoding**.</span><span class="sxs-lookup"><span data-stu-id="9312e-215">Add unified attribute for completion for **Encoding** parameter.</span></span> <span data-ttu-id="9312e-216">(nº 7732) (Obrigado @ThreeFive-O!)</span><span class="sxs-lookup"><span data-stu-id="9312e-216">(#7732) (Thanks @ThreeFive-O!)</span></span>
- <span data-ttu-id="9312e-217">Permissão de Ids numéricas e nome de páginas de código registradas nos parâmetros **Encoding** (nº 7636) (Obrigado @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="9312e-217">Allow numeric Ids and name of registered code pages in **Encoding** parameters (#7636) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="9312e-218">Correção de `Rename-Item -Path` com o caractere curinga (nº 7398) (Obrigado @kwkam!)</span><span class="sxs-lookup"><span data-stu-id="9312e-218">Fix `Rename-Item -Path` with wildcard char (#7398) (Thanks @kwkam!)</span></span>
- <span data-ttu-id="9312e-219">Ao usar `Start-Transcript` e o arquivo existir, esvazie o arquivo em vez de excluir (nº 8131) (Obrigado @paalbra!)</span><span class="sxs-lookup"><span data-stu-id="9312e-219">When using `Start-Transcript` and file exists, empty file rather than deleting (#8131) (Thanks @paalbra!)</span></span>
- <span data-ttu-id="9312e-220">Criação explícita de arquivos de software livre `Add-Type` com **FileAccess.Read** e **FileShare.Read** (nº 7915) (Obrigado @IISResetMe!)</span><span class="sxs-lookup"><span data-stu-id="9312e-220">Make `Add-Type` open source files with **FileAccess.Read** and **FileShare.Read** explicitly (#7915) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="9312e-221">Correção de `Enter-PSSession -ContainerId` para o Windows mais recente (nº 7883)</span><span class="sxs-lookup"><span data-stu-id="9312e-221">Fix `Enter-PSSession -ContainerId` for the latest Windows (#7883)</span></span>
- <span data-ttu-id="9312e-222">Garantia de que a propriedade **NestedModules** seja preenchida por `Test-ModuleManifest` (nº 7859)</span><span class="sxs-lookup"><span data-stu-id="9312e-222">Ensure **NestedModules** property gets populated by `Test-ModuleManifest` (#7859)</span></span>
- <span data-ttu-id="9312e-223">Adição de `%F` a `Get-Date` -UFormat (nº 7630) (Obrigado @britishben!)</span><span class="sxs-lookup"><span data-stu-id="9312e-223">Add `%F` case to `Get-Date` -UFormat (#7630) (Thanks @britishben!)</span></span>
- <span data-ttu-id="9312e-224">Correção de `Set-Service -Status Stopped` para interrupção de serviços com dependências (nº 5525) (Obrigado @zhenggu!)</span><span class="sxs-lookup"><span data-stu-id="9312e-224">Fix `Set-Service -Status Stopped` to stop services with dependencies (#5525) (Thanks @zhenggu!)</span></span>

<!-- Link references -->
[about_Numeric_Literals]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[Recursos experimentais]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[PSDrive]: /powershell/module/microsoft.powershell.management/new-psdrive
