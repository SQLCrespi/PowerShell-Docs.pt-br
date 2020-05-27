---
ms.date: 04/28/2020
title: Usar recursos experimentais no PowerShell
description: Lista os recursos experimentais disponíveis no momento e como usá-los.
ms.openlocfilehash: 72a4309d6eeede4cd2ff7c38ce8e99ce3ace30eb
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809182"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="2adb9-103">Usar recursos experimentais no PowerShell</span><span class="sxs-lookup"><span data-stu-id="2adb9-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="2adb9-104">O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2adb9-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="2adb9-105">Um recurso experimental é aquele em que o design não está finalizado.</span><span class="sxs-lookup"><span data-stu-id="2adb9-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="2adb9-106">O recurso está disponível para os usuários testarem e fornecerem comentários.</span><span class="sxs-lookup"><span data-stu-id="2adb9-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="2adb9-107">Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.</span><span class="sxs-lookup"><span data-stu-id="2adb9-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="2adb9-108">Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="2adb9-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="2adb9-109">Recursos experimentais não têm suporte oficialmente.</span><span class="sxs-lookup"><span data-stu-id="2adb9-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="2adb9-110">No entanto, agradecemos o envio de comentários e relatórios de bugs.</span><span class="sxs-lookup"><span data-stu-id="2adb9-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="2adb9-111">Você pode arquivar problemas no [repositório de origem do GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="2adb9-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="2adb9-112">Para obter mais informações sobre como habilitar ou desabilitar esses recursos, confira [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="2adb9-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="2adb9-113">Recursos disponíveis</span><span class="sxs-lookup"><span data-stu-id="2adb9-113">Available features</span></span>

<span data-ttu-id="2adb9-114">Este artigo descreve os recursos experimentais que estão disponíveis e como usar o recurso.</span><span class="sxs-lookup"><span data-stu-id="2adb9-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="2adb9-115">Nome</span><span class="sxs-lookup"><span data-stu-id="2adb9-115">Name</span></span>                            |   <span data-ttu-id="2adb9-116">6.2</span><span class="sxs-lookup"><span data-stu-id="2adb9-116">6.2</span></span>   |   <span data-ttu-id="2adb9-117">7.0</span><span class="sxs-lookup"><span data-stu-id="2adb9-117">7.0</span></span>   | <span data-ttu-id="2adb9-118">7.1 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="2adb9-118">7.1 (preview)</span></span> |
| ---------------------------------------------------------- | :-----: | :-----: | :-----------: |
| <span data-ttu-id="2adb9-119">PSTempDrive (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="2adb9-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |               |
| <span data-ttu-id="2adb9-120">PSUseAbbreviationExpansion (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="2adb9-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |               |
| <span data-ttu-id="2adb9-121">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="2adb9-121">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; |    &check;    |
| <span data-ttu-id="2adb9-122">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="2adb9-122">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; |    &check;    |
| <span data-ttu-id="2adb9-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="2adb9-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; |    &check;    |
| <span data-ttu-id="2adb9-124">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="2adb9-124">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; |    &check;    |
| <span data-ttu-id="2adb9-125">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="2adb9-125">PSNullConditionalOperators</span></span>                                 |         | &check; |    &check;    |
| <span data-ttu-id="2adb9-126">PSUnixFileStat (somente não Windows)</span><span class="sxs-lookup"><span data-stu-id="2adb9-126">PSUnixFileStat (non-Windows only)</span></span>                          |         | &check; |    &check;    |
| <span data-ttu-id="2adb9-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="2adb9-127">PSNativePSPathResolution</span></span>                                   |         |         |    &check;    |
| <span data-ttu-id="2adb9-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="2adb9-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         |    &check;    |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="2adb9-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="2adb9-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="2adb9-130">Habilita o parâmetro **BreakAll** nos cmdlets `Debug-Runspace` e `Debug-Job` para permitir que os usuários decidam se querem que o PowerShell seja interrompido imediatamente no local atual quando eles anexarem um depurador.</span><span class="sxs-lookup"><span data-stu-id="2adb9-130">Enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="2adb9-131">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="2adb9-131">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="2adb9-132">Recomenda comandos potenciais com base na pesquisa de correspondência difusa após um **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="2adb9-132">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="2adb9-133">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="2adb9-133">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="2adb9-134">Quando o operando à esquerda em uma instrução do operador `-replace` não é uma cadeia de caracteres, esse operando é convertido em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2adb9-134">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="2adb9-135">Quando esse recurso está desabilitado, o operador `-replace` faz uma conversão de cadeia de caracteres sensível à cultura.</span><span class="sxs-lookup"><span data-stu-id="2adb9-135">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="2adb9-136">Por exemplo, se sua cultura for definida como francês (FR), o valor `1.2` será convertido para a cadeia de caracteres `1,2`.</span><span class="sxs-lookup"><span data-stu-id="2adb9-136">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="2adb9-137">Com o recurso habilitado:</span><span class="sxs-lookup"><span data-stu-id="2adb9-137">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="2adb9-138">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="2adb9-138">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="2adb9-139">Habilita a compilação para o formato MOF em sistemas que não são do Windows e permite o uso de `Invoke-DSCResource` sem um LCM.</span><span class="sxs-lookup"><span data-stu-id="2adb9-139">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="2adb9-140">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="2adb9-140">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="2adb9-141">Esse recurso examina o comando digitado no shell e, se todos os comandos forem comandos de proxy de comunicação remota implícitos que formam um pipeline simples, os comandos serão agrupados em lote e invocados como um único pipeline remoto.</span><span class="sxs-lookup"><span data-stu-id="2adb9-141">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="2adb9-142">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="2adb9-142">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="2adb9-143">Como visto acima, com o recurso de envio em lote habilitado, todos os três comandos de proxy de comunicação remota implícito, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, executados na sessão remota e o resultado do pipeline são os únicos dados retornados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2adb9-143">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="2adb9-144">Isso diminui a quantidade de dados enviados entre o cliente e a sessão remota, além de reduzir a quantidade de serialização e desserialização de objetos.</span><span class="sxs-lookup"><span data-stu-id="2adb9-144">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="2adb9-145">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="2adb9-145">PSNativePSPathResolution</span></span>

<span data-ttu-id="2adb9-146">Se um caminho PSDrive que usa o provedor FileSystem for passado para um comando nativo, o caminho do arquivo resolvido será passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="2adb9-146">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="2adb9-147">Isso significa que um comando como `code temp:/test.txt` agora funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="2adb9-147">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="2adb9-148">Além disso, no Windows, se o caminho começar com `~`, isso será resolvido para o caminho completo e passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="2adb9-148">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="2adb9-149">Em ambos os casos, o caminho é normalizado para os separadores de diretório para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="2adb9-149">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="2adb9-150">Se o caminho não for um PSDrive ou `~` (no Windows), a normalização de caminho não ocorrerá</span><span class="sxs-lookup"><span data-stu-id="2adb9-150">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="2adb9-151">Se o caminho estiver entre aspas simples, ele não será resolvido e tratado como literal</span><span class="sxs-lookup"><span data-stu-id="2adb9-151">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="2adb9-152">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="2adb9-152">PSNullConditionalOperators</span></span>

<span data-ttu-id="2adb9-153">Apresenta novos operadores para operadores de acesso a membros condicional nulo – `?.` e `?[]`.</span><span class="sxs-lookup"><span data-stu-id="2adb9-153">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="2adb9-154">Operadores de acesso a membros nulo podem ser usados em tipos escalares e tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="2adb9-154">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="2adb9-155">Retorne o valor do membro acessado se a variável não for nula.</span><span class="sxs-lookup"><span data-stu-id="2adb9-155">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="2adb9-156">Se o valor da variável for nulo, retornará nulo.</span><span class="sxs-lookup"><span data-stu-id="2adb9-156">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="2adb9-157">A propriedade `propname` é acessada, e seu valor será retornado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="2adb9-157">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="2adb9-158">Da mesma forma, o indexador será usado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="2adb9-158">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="2adb9-159">Se `$x` for nulo, nulo será retornado.</span><span class="sxs-lookup"><span data-stu-id="2adb9-159">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="2adb9-160">Os operadores `?.` e `?[]` são operadores de acesso a membros e não permitem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="2adb9-160">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="2adb9-161">Como o PowerShell permite `?` como parte do nome da variável, a desambiguidade é necessária quando os operadores são usados sem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="2adb9-161">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="2adb9-162">Para desambiguar, as variáveis devem usar `{}` em volta do nome da variável, como: `${x?}?.propertyName` ou `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="2adb9-162">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="2adb9-163">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="2adb9-163">PSTempDrive</span></span>

<span data-ttu-id="2adb9-164">Cria o PSDrive `TEMP:` mapeado para o caminho do diretório temporário do usuário.</span><span class="sxs-lookup"><span data-stu-id="2adb9-164">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="2adb9-165">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="2adb9-165">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="2adb9-166">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="2adb9-166">PSUnixFileStat</span></span>

<span data-ttu-id="2adb9-167">Esse recurso fornece um novo comportamento para incluir dados da API **stat** do UNIX na saída do provedor do sistema de arquivos para facilitar uma listagem de arquivos semelhante ao UNIX.</span><span class="sxs-lookup"><span data-stu-id="2adb9-167">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="2adb9-168">Ele adiciona uma nova propriedade de anotação no provedor filesystem chamado **UnixStat** que inclui uma expressão comum da API `stat(2)` do sistema de tipos UNIX subjacente.</span><span class="sxs-lookup"><span data-stu-id="2adb9-168">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="2adb9-169">A saída de `Get-ChildItem` deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="2adb9-169">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
PS> dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="2adb9-170">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="2adb9-170">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="2adb9-171">Esse recurso permite o preenchimento com Tab de funções e cmdlets abreviados:</span><span class="sxs-lookup"><span data-stu-id="2adb9-171">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="2adb9-172">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="2adb9-172">For example:</span></span>

- <span data-ttu-id="2adb9-173">`i-psdf<tab>` retorna `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="2adb9-173">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="2adb9-174">`u-akvmssdr<tab>` retorna `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="2adb9-174">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="2adb9-175">Isso só funciona para preenchimento com Tab (uso interativo), portanto, `i-psdf` não é um nome de cmdlet válido em um script.</span><span class="sxs-lookup"><span data-stu-id="2adb9-175">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="2adb9-176">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="2adb9-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>
