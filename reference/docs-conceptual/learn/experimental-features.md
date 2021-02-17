---
ms.date: 12/14/2020
title: Usar recursos experimentais no PowerShell
description: Lista os recursos experimentais disponíveis no momento e como usá-los.
ms.openlocfilehash: 556ae8d877b670b119b7b5b958a52488aad16241
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500116"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="198b3-103">Usar recursos experimentais no PowerShell</span><span class="sxs-lookup"><span data-stu-id="198b3-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="198b3-104">O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="198b3-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="198b3-105">Um recurso experimental é aquele em que o design não está finalizado.</span><span class="sxs-lookup"><span data-stu-id="198b3-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="198b3-106">O recurso está disponível para os usuários testarem e fornecerem comentários.</span><span class="sxs-lookup"><span data-stu-id="198b3-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="198b3-107">Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.</span><span class="sxs-lookup"><span data-stu-id="198b3-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="198b3-108">Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="198b3-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="198b3-109">Recursos experimentais não têm suporte oficialmente.</span><span class="sxs-lookup"><span data-stu-id="198b3-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="198b3-110">No entanto, agradecemos o envio de comentários e relatórios de bugs.</span><span class="sxs-lookup"><span data-stu-id="198b3-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="198b3-111">Você pode arquivar problemas no [repositório de origem do GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="198b3-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="198b3-112">Para obter mais informações sobre como habilitar ou desabilitar esses recursos, confira [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="198b3-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="198b3-113">Recursos disponíveis</span><span class="sxs-lookup"><span data-stu-id="198b3-113">Available features</span></span>

<span data-ttu-id="198b3-114">Este artigo descreve os recursos experimentais que estão disponíveis e como usar o recurso.</span><span class="sxs-lookup"><span data-stu-id="198b3-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="198b3-115">Nome</span><span class="sxs-lookup"><span data-stu-id="198b3-115">Name</span></span>                            |   <span data-ttu-id="198b3-116">6.2</span><span class="sxs-lookup"><span data-stu-id="198b3-116">6.2</span></span>   |   <span data-ttu-id="198b3-117">7.0</span><span class="sxs-lookup"><span data-stu-id="198b3-117">7.0</span></span>   |   <span data-ttu-id="198b3-118">7.1</span><span class="sxs-lookup"><span data-stu-id="198b3-118">7.1</span></span>   |   <span data-ttu-id="198b3-119">7.2</span><span class="sxs-lookup"><span data-stu-id="198b3-119">7.2</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| <span data-ttu-id="198b3-120">PSTempDrive (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="198b3-120">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |         |
| <span data-ttu-id="198b3-121">PSUseAbbreviationExpansion (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="198b3-121">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |         |
| <span data-ttu-id="198b3-122">PSNullConditionalOperators (base no PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="198b3-122">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |         |
| <span data-ttu-id="198b3-123">PSUnixFileStat (somente não Windows – base no PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="198b3-123">PSUnixFileStat (non-Windows only - mainstream in PS 7.1+)</span></span>  |         | &check; |         |         |
| <span data-ttu-id="198b3-124">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="198b3-124">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; | &check; |
| <span data-ttu-id="198b3-125">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="198b3-125">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; | &check; |
| <span data-ttu-id="198b3-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="198b3-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; | &check; |
| <span data-ttu-id="198b3-127">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="198b3-127">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; | &check; |
| <span data-ttu-id="198b3-128">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="198b3-128">PSNativePSPathResolution</span></span>                                   |         |         | &check; | &check; |
| <span data-ttu-id="198b3-129">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="198b3-129">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; | &check; |
| <span data-ttu-id="198b3-130">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="198b3-130">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; | &check; |
| <span data-ttu-id="198b3-131">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="198b3-131">PSSubsystemPluginModel</span></span>                                     |         |         | &check; | &check; |
| <span data-ttu-id="198b3-132">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="198b3-132">PSAnsiProgress</span></span>                                             |         |         |         | &check; |
| <span data-ttu-id="198b3-133">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="198b3-133">PSAnsiRendering</span></span>                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="198b3-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="198b3-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="198b3-135">No PowerShell 7.0, o experimento habilita o parâmetro **BreakAll** nos cmdlets `Debug-Runspace` e `Debug-Job` para permitir que os usuários decidam se querem que o PowerShell seja interrompido imediatamente no local atual quando eles anexarem um depurador.</span><span class="sxs-lookup"><span data-stu-id="198b3-135">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="198b3-136">No PowerShell 7.1, esse experimento também adiciona o parâmetro **Runspace** aos cmdlets `*-PSBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="198b3-136">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="198b3-137">O parâmetro **Runspace** especifica um objeto **Runspace** para interagir com pontos de interrupção no runspace especificado.</span><span class="sxs-lookup"><span data-stu-id="198b3-137">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="198b3-138">Nesse exemplo, um trabalho é iniciado e um ponto de interrupção é definido para interromper quando `Set-PSBreakPoint` for executado.</span><span class="sxs-lookup"><span data-stu-id="198b3-138">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="198b3-139">O runspace é armazenado em uma variável e transmitido para o comando `Get-PSBreakPoint` com o parâmetro **Runspace**.</span><span class="sxs-lookup"><span data-stu-id="198b3-139">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="198b3-140">Em seguida, você pode inspecionar o ponto de interrupção na variável `$breakpoint`.</span><span class="sxs-lookup"><span data-stu-id="198b3-140">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="psansirendering"></a><span data-ttu-id="198b3-141">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="198b3-141">PSAnsiRendering</span></span>

<span data-ttu-id="198b3-142">O experimento foi adicionado no PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="198b3-142">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="198b3-143">O recurso permite alterar a forma como o mecanismo do PowerShell gera texto e adiciona a variável automática `$PSStyle` para controlar a renderização ANSI da saída da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="198b3-143">The feature enables changes how the PowerShell engine outputs text and add the `$PSStyle` automatic variable to control ANSI rendering of string output.</span></span>

```powershell
PS> $PSStyle

Name            MemberType Definition
----            ---------- ----------
Reset           Property   string AttributesOff {get;set;}
Background      Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;set;}
Blink           Property   string Blink {get;set;}
BlinkOff        Property   string BlinkOff {get;set;}
Bold            Property   string Bold {get;set;}
BoldOff         Property   string BoldOff {get;set;}
Foreground      Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;set;}
Formatting      Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;set;}
Hidden          Property   string Hidden {get;set;}
HiddenOff       Property   string HiddenOff {get;set;}
OutputRendering Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Reverse         Property   string Reverse {get;set;}
ReverseOff      Property   string ReverseOff {get;set;}
Italic          Property   string Standout {get;set;}
ItalicOff       Property   string StandoutOff {get;set;}
Underline       Property   string Underlined {get;set;}
Underline Off   Property   string UnderlinedOff {get;set;}
```

<span data-ttu-id="198b3-144">Os membros de base retornam cadeias de caracteres de sequências de escape ANSI mapeadas para seus nomes.</span><span class="sxs-lookup"><span data-stu-id="198b3-144">The base members return strings of ANSI escape sequences mapped to their names.</span></span> <span data-ttu-id="198b3-145">Os valores são configuráveis para permitir a personalização.</span><span class="sxs-lookup"><span data-stu-id="198b3-145">The values are settable to allow customization.</span></span>

<span data-ttu-id="198b3-146">Para obter mais informações, confira [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="198b3-146">For more information, see [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span></span>

> [!NOTE]
> <span data-ttu-id="198b3-147">Para desenvolvedores C#, você pode acessar `PSStyle` como um singleton.</span><span class="sxs-lookup"><span data-stu-id="198b3-147">For C# developers, you can access `PSStyle` as a singleton.</span></span> <span data-ttu-id="198b3-148">O uso terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="198b3-148">Usage will look like this:</span></span>
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> <span data-ttu-id="198b3-149">`PSStyle` existe no namespace System.Management.Automation.</span><span class="sxs-lookup"><span data-stu-id="198b3-149">`PSStyle` exists in the System.Management.Automation namespace.</span></span>

<span data-ttu-id="198b3-150">Junto com o acesso ao `$PSStyle`, isso apresenta alterações no mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="198b3-150">Along with access to `$PSStyle`, this introduces changes to the PowerShell engine.</span></span> <span data-ttu-id="198b3-151">O sistema de formatação do PowerShell é atualizado para respeitar `$PSStyle.OutputRendering`.</span><span class="sxs-lookup"><span data-stu-id="198b3-151">The PowerShell formatting system is updated to respect `$PSStyle.OutputRendering`.</span></span>

- <span data-ttu-id="198b3-152">O tipo `StringDecorated` é adicionado para manipular cadeias de caracteres de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="198b3-152">`StringDecorated` type is added to handle ANSI escaped strings.</span></span>
- <span data-ttu-id="198b3-153">A propriedade booliana `string IsDecorated` é adicionada para retornar se a cadeia de caracteres contém sequências de escape ANSI com base em se a cadeia de caracteres contém ESC ou C1 CSI.</span><span class="sxs-lookup"><span data-stu-id="198b3-153">`string IsDecorated` boolean property is added to return if the string contains ANSI escape sequences based on if the string contains ESC or C1 CSI.</span></span>
- <span data-ttu-id="198b3-154">A propriedade `Length` retorna _apenas_ o comprimento do texto sem as sequências de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="198b3-154">The `Length` property returns _only_ the length for the text without the ANSI escape sequences.</span></span>
- <span data-ttu-id="198b3-155">O método `StringDecorated Substring(int contentLength)` retorna uma substring começando no índice 0 até o comprimento do conteúdo que não faz parte das sequências de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="198b3-155">`StringDecorated Substring(int contentLength)` method returns a substring starting at index 0 up to the content length that is not a part of ANSI escape sequences.</span></span> <span data-ttu-id="198b3-156">Isso é necessário para a formatação da tabela a fim de truncar cadeias de caracteres e preservar as sequências de escape ANSI que não ocupam espaço de caracteres imprimível.</span><span class="sxs-lookup"><span data-stu-id="198b3-156">This is needed for table formatting to truncate strings and preserve ANSI escape sequences that don't take up printable character space.</span></span>
- <span data-ttu-id="198b3-157">O método `string ToString()` permanece o mesmo e retorna a versão de texto não criptografado da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="198b3-157">`string ToString()` method stays the same and returns the plaintext version of the string.</span></span>
- <span data-ttu-id="198b3-158">O método `string ToString(bool Ansi)` retornará a cadeia de caracteres ANSI bruta inserida se o parâmetro `Ansi` for true.</span><span class="sxs-lookup"><span data-stu-id="198b3-158">`string ToString(bool Ansi)` method returns the raw ANSI embedded string if the `Ansi` parameter is true.</span></span> <span data-ttu-id="198b3-159">Caso contrário, uma versão de texto não criptografado com sequências de escape ANSI removidas será retornada.</span><span class="sxs-lookup"><span data-stu-id="198b3-159">Otherwise, a plaintext version with ANSI escape sequences removed is returned.</span></span>

## <a name="psansiprogress"></a><span data-ttu-id="198b3-160">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="198b3-160">PSAnsiProgress</span></span>

<span data-ttu-id="198b3-161">O experimento foi adicionado no PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="198b3-161">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="198b3-162">O recurso adiciona o membro `$PSStyle.Progress` e permite controlar a renderização da barra de exibição de progresso.</span><span class="sxs-lookup"><span data-stu-id="198b3-162">The feature adds the `$PSStyle.Progress` member and allows you to control progress view bar rendering.</span></span>

- <span data-ttu-id="198b3-163">`$PSStyle.Progress.Style` – uma cadeia de caracteres ANSI que define o estilo de renderização.</span><span class="sxs-lookup"><span data-stu-id="198b3-163">`$PSStyle.Progress.Style` - An ANSI string setting the rendering style.</span></span>
- <span data-ttu-id="198b3-164">`$PSStyle.Progress.MaxWidth` – define a largura máxima da exibição.</span><span class="sxs-lookup"><span data-stu-id="198b3-164">`$PSStyle.Progress.MaxWidth` - Sets the max width of the view.</span></span> <span data-ttu-id="198b3-165">Defina como `0` para a largura do console.</span><span class="sxs-lookup"><span data-stu-id="198b3-165">Set to `0` for console width.</span></span>
  <span data-ttu-id="198b3-166">Usa como padrão `120`</span><span class="sxs-lookup"><span data-stu-id="198b3-166">Defaults to `120`</span></span>
- <span data-ttu-id="198b3-167">`$PSStyle.Progress.View` – uma enumeração com valores `Minimal` e `Classic`.</span><span class="sxs-lookup"><span data-stu-id="198b3-167">`$PSStyle.Progress.View` - An enum with values, `Minimal` and `Classic`.</span></span> <span data-ttu-id="198b3-168">`Classic` é a renderização existente sem alterações.</span><span class="sxs-lookup"><span data-stu-id="198b3-168">`Classic` is the existing rendering with no changes.</span></span> <span data-ttu-id="198b3-169">`Minimal` é uma renderização mínima de linha única.</span><span class="sxs-lookup"><span data-stu-id="198b3-169">`Minimal` is a single line minimal rendering.</span></span> <span data-ttu-id="198b3-170">`Minimal` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="198b3-170">`Minimal` is the default.</span></span>

<span data-ttu-id="198b3-171">O exemplo a seguir atualiza o estilo de renderização para uma barra de progresso mínima.</span><span class="sxs-lookup"><span data-stu-id="198b3-171">The following example updates the rendering style to a minimal progress bar.</span></span>

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> <span data-ttu-id="198b3-172">O recurso experimental **PSAnsiRendering** deve estar habilitado para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="198b3-172">You must have the **PSAnsiRendering** experimental feature enabled to use this feature.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="198b3-173">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="198b3-173">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="198b3-174">Recomenda comandos potenciais com base na pesquisa de correspondência difusa após um **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="198b3-174">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

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

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="198b3-175">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="198b3-175">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="198b3-176">Quando o operando à esquerda em uma instrução do operador `-replace` não é uma cadeia de caracteres, esse operando é convertido em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="198b3-176">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="198b3-177">Quando esse recurso está desabilitado, o operador `-replace` faz uma conversão de cadeia de caracteres sensível à cultura.</span><span class="sxs-lookup"><span data-stu-id="198b3-177">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="198b3-178">Por exemplo, se sua cultura for definida como francês (FR), o valor `1.2` será convertido para a cadeia de caracteres `1,2`.</span><span class="sxs-lookup"><span data-stu-id="198b3-178">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="198b3-179">Com o recurso habilitado:</span><span class="sxs-lookup"><span data-stu-id="198b3-179">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="198b3-180">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="198b3-180">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="198b3-181">Habilita a compilação para o formato MOF em sistemas que não são do Windows e permite o uso de `Invoke-DSCResource` sem um LCM.</span><span class="sxs-lookup"><span data-stu-id="198b3-181">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="198b3-182">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="198b3-182">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="198b3-183">Esse recurso examina o comando digitado no shell e, se todos os comandos forem comandos de proxy de comunicação remota implícitos que formam um pipeline simples, os comandos serão agrupados em lote e invocados como um único pipeline remoto.</span><span class="sxs-lookup"><span data-stu-id="198b3-183">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="198b3-184">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="198b3-184">Example:</span></span>

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

<span data-ttu-id="198b3-185">Como visto acima, com o recurso de envio em lote habilitado, todos os três comandos de proxy de comunicação remota implícito, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, executados na sessão remota e o resultado do pipeline são os únicos dados retornados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="198b3-185">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="198b3-186">Isso diminui a quantidade de dados enviados entre o cliente e a sessão remota, além de reduzir a quantidade de serialização e desserialização de objetos.</span><span class="sxs-lookup"><span data-stu-id="198b3-186">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="198b3-187">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="198b3-187">PSNativePSPathResolution</span></span>

<span data-ttu-id="198b3-188">Se um caminho PSDrive que usa o provedor FileSystem for passado para um comando nativo, o caminho do arquivo resolvido será passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="198b3-188">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="198b3-189">Isso significa que um comando como `code temp:/test.txt` agora funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="198b3-189">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="198b3-190">Além disso, no Windows, se o caminho começar com `~`, isso será resolvido para o caminho completo e passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="198b3-190">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="198b3-191">Em ambos os casos, o caminho é normalizado para os separadores de diretório para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="198b3-191">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="198b3-192">Se o caminho não for um PSDrive ou `~` (no Windows), a normalização de caminho não ocorrerá</span><span class="sxs-lookup"><span data-stu-id="198b3-192">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="198b3-193">Se o caminho estiver entre aspas simples, ele não será resolvido e tratado como literal</span><span class="sxs-lookup"><span data-stu-id="198b3-193">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="198b3-194">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="198b3-194">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="198b3-195">Quando esse recurso experimental está habilitado, os registros de erro redirecionados de comandos nativos, como ao usar operadores de redirecionamento (`2>&1`), não são gravados na variável `$Error`, e a variável de preferência `$ErrorActionPreference` não afeta a saída redirecionada.</span><span class="sxs-lookup"><span data-stu-id="198b3-195">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="198b3-196">Muitos comandos nativos gravam em `stderr` como um fluxo alternativo para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="198b3-196">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="198b3-197">Esse comportamento pode causar confusão ao examinar erros, ou o usuário pode perder as informações de saída adicionais caso `$ErrorActionPreference` esteja definido como um estado que desativa a saída.</span><span class="sxs-lookup"><span data-stu-id="198b3-197">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="198b3-198">Quando um comando nativo tem um código de saída diferente de zero, `$?` é definido como `$false`.</span><span class="sxs-lookup"><span data-stu-id="198b3-198">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="198b3-199">Se o código de saída for zero, `$?` será definido como `$true`.</span><span class="sxs-lookup"><span data-stu-id="198b3-199">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="198b3-200">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="198b3-200">PSNullConditionalOperators</span></span>

<span data-ttu-id="198b3-201">Apresenta novos operadores para operadores de acesso a membros condicional nulo – `?.` e `?[]`.</span><span class="sxs-lookup"><span data-stu-id="198b3-201">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="198b3-202">Operadores de acesso a membros nulo podem ser usados em tipos escalares e tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="198b3-202">Null member access operators can be used on scalar types and array types.</span></span> <span data-ttu-id="198b3-203">Retorne o valor do membro acessado se a variável não for nula.</span><span class="sxs-lookup"><span data-stu-id="198b3-203">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="198b3-204">Se o valor da variável for nulo, retornará nulo.</span><span class="sxs-lookup"><span data-stu-id="198b3-204">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="198b3-205">A propriedade `propname` é acessada, e seu valor será retornado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="198b3-205">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="198b3-206">Da mesma forma, o indexador será usado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="198b3-206">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="198b3-207">Se `$x` for nulo, nulo será retornado.</span><span class="sxs-lookup"><span data-stu-id="198b3-207">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="198b3-208">Os operadores `?.` e `?[]` são operadores de acesso a membros e não permitem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="198b3-208">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="198b3-209">Como o PowerShell permite `?` como parte do nome da variável, a desambiguidade é necessária quando os operadores são usados sem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="198b3-209">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="198b3-210">Para desambiguar, as variáveis devem usar `{}` em volta do nome da variável, como: `${x?}?.propertyName` ou `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="198b3-210">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="198b3-211">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="198b3-211">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="198b3-212">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="198b3-212">PSTempDrive</span></span>

<span data-ttu-id="198b3-213">Cria o PSDrive `TEMP:` mapeado para o caminho do diretório temporário do usuário.</span><span class="sxs-lookup"><span data-stu-id="198b3-213">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="198b3-214">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="198b3-214">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="198b3-215">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="198b3-215">PSUnixFileStat</span></span>

<span data-ttu-id="198b3-216">Esse recurso fornece um novo comportamento para incluir dados da API **stat** do UNIX na saída do provedor do sistema de arquivos para facilitar uma listagem de arquivos semelhante ao UNIX.</span><span class="sxs-lookup"><span data-stu-id="198b3-216">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="198b3-217">Ele adiciona uma nova propriedade de anotação no provedor filesystem chamado **UnixStat** que inclui uma expressão comum da API `stat(2)` do sistema de tipos UNIX subjacente.</span><span class="sxs-lookup"><span data-stu-id="198b3-217">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="198b3-218">A saída de `Get-ChildItem` deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="198b3-218">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> <span data-ttu-id="198b3-219">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="198b3-219">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="198b3-220">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="198b3-220">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="198b3-221">Esse recurso permite o preenchimento com Tab de funções e cmdlets abreviados:</span><span class="sxs-lookup"><span data-stu-id="198b3-221">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="198b3-222">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="198b3-222">For example:</span></span>

- <span data-ttu-id="198b3-223">`i-psdf<tab>` retorna `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="198b3-223">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="198b3-224">`u-akvmssdr<tab>` retorna `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="198b3-224">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="198b3-225">Isso só funciona para preenchimento com Tab (uso interativo), portanto, `i-psdf` não é um nome de cmdlet válido em um script.</span><span class="sxs-lookup"><span data-stu-id="198b3-225">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="198b3-226">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="198b3-226">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="198b3-227">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="198b3-227">PSSubsystemPluginModel</span></span>

<span data-ttu-id="198b3-228">Esse recurso habilita o modelo de plug-in do subsistema no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="198b3-228">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="198b3-229">Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly.</span><span class="sxs-lookup"><span data-stu-id="198b3-229">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="198b3-230">Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="198b3-230">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="198b3-231">Atualmente, há suporte apenas para o subsistema **CommandPredictor**.</span><span class="sxs-lookup"><span data-stu-id="198b3-231">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="198b3-232">Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados.</span><span class="sxs-lookup"><span data-stu-id="198b3-232">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="198b3-233">No futuro, será possível dividir **Job**, **CommandCompleter**, **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="198b3-233">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="198b3-234">O recurso experimental inclui um novo cmdlet, o [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span><span class="sxs-lookup"><span data-stu-id="198b3-234">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="198b3-235">Esse cmdlet só está disponível quando o recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="198b3-235">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="198b3-236">Esse cmdlet retorna informações sobre os subsistemas disponíveis no sistema.</span><span class="sxs-lookup"><span data-stu-id="198b3-236">This cmdlet returns information about the subsystems that are available on the system.</span></span>
