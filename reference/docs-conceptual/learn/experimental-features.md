---
ms.date: 12/14/2020
title: Usar recursos experimentais no PowerShell
description: Lista os recursos experimentais disponíveis no momento e como usá-los.
ms.openlocfilehash: 828a962ca46e5563874ff1c941c46c8a0624f3d8
ms.sourcegitcommit: f6cc3752463b254f6ba7fc14c1e4532ad33f06bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "107216887"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="1326c-103">Usar recursos experimentais no PowerShell</span><span class="sxs-lookup"><span data-stu-id="1326c-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="1326c-104">O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1326c-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="1326c-105">Um recurso experimental é aquele em que o design não está finalizado.</span><span class="sxs-lookup"><span data-stu-id="1326c-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="1326c-106">O recurso está disponível para os usuários testarem e fornecerem comentários.</span><span class="sxs-lookup"><span data-stu-id="1326c-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="1326c-107">Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.</span><span class="sxs-lookup"><span data-stu-id="1326c-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="1326c-108">Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="1326c-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="1326c-109">Recursos experimentais não têm suporte oficialmente.</span><span class="sxs-lookup"><span data-stu-id="1326c-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="1326c-110">No entanto, agradecemos o envio de comentários e relatórios de bugs.</span><span class="sxs-lookup"><span data-stu-id="1326c-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="1326c-111">Você pode arquivar problemas no [repositório de origem do GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="1326c-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="1326c-112">Para obter mais informações sobre como habilitar ou desabilitar esses recursos, confira [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="1326c-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="1326c-113">Recursos disponíveis</span><span class="sxs-lookup"><span data-stu-id="1326c-113">Available features</span></span>

<span data-ttu-id="1326c-114">Este artigo descreve os recursos experimentais que estão disponíveis e como usar o recurso.</span><span class="sxs-lookup"><span data-stu-id="1326c-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="1326c-115">Nome</span><span class="sxs-lookup"><span data-stu-id="1326c-115">Name</span></span>                            |   <span data-ttu-id="1326c-116">6.2</span><span class="sxs-lookup"><span data-stu-id="1326c-116">6.2</span></span>   |   <span data-ttu-id="1326c-117">7.0</span><span class="sxs-lookup"><span data-stu-id="1326c-117">7.0</span></span>   |   <span data-ttu-id="1326c-118">7.1</span><span class="sxs-lookup"><span data-stu-id="1326c-118">7.1</span></span>   |   <span data-ttu-id="1326c-119">7.2</span><span class="sxs-lookup"><span data-stu-id="1326c-119">7.2</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| <span data-ttu-id="1326c-120">PSTempDrive (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="1326c-120">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |         |
| <span data-ttu-id="1326c-121">PSUseAbbreviationExpansion (base no PS 7.0+)</span><span class="sxs-lookup"><span data-stu-id="1326c-121">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |         |
| <span data-ttu-id="1326c-122">PSNullConditionalOperators (base no PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="1326c-122">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |         |
| <span data-ttu-id="1326c-123">PSUnixFileStat (somente não Windows – base no PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="1326c-123">PSUnixFileStat (non-Windows only - mainstream in PS 7.1+)</span></span>  |         | &check; |         |         |
| <span data-ttu-id="1326c-124">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="1326c-124">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; | &check; |
| <span data-ttu-id="1326c-125">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="1326c-125">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; | &check; |
| <span data-ttu-id="1326c-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="1326c-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; | &check; |
| <span data-ttu-id="1326c-127">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="1326c-127">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; | &check; |
| <span data-ttu-id="1326c-128">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="1326c-128">PSNativePSPathResolution</span></span>                                   |         |         | &check; | &check; |
| <span data-ttu-id="1326c-129">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="1326c-129">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; | &check; |
| <span data-ttu-id="1326c-130">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="1326c-130">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; | &check; |
| <span data-ttu-id="1326c-131">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="1326c-131">PSSubsystemPluginModel</span></span>                                     |         |         | &check; | &check; |
| <span data-ttu-id="1326c-132">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="1326c-132">PSAnsiProgress</span></span>                                             |         |         |         | &check; |
| <span data-ttu-id="1326c-133">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="1326c-133">PSAnsiRendering</span></span>                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="1326c-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="1326c-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="1326c-135">No PowerShell 7.0, o experimento habilita o parâmetro **BreakAll** nos cmdlets `Debug-Runspace` e `Debug-Job` para permitir que os usuários decidam se querem que o PowerShell seja interrompido imediatamente no local atual quando eles anexarem um depurador.</span><span class="sxs-lookup"><span data-stu-id="1326c-135">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="1326c-136">No PowerShell 7.1, esse experimento também adiciona o parâmetro **Runspace** aos cmdlets `*-PSBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="1326c-136">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="1326c-137">O parâmetro **Runspace** especifica um objeto **Runspace** para interagir com pontos de interrupção no runspace especificado.</span><span class="sxs-lookup"><span data-stu-id="1326c-137">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="1326c-138">Nesse exemplo, um trabalho é iniciado e um ponto de interrupção é definido para interromper quando `Set-PSBreakPoint` for executado.</span><span class="sxs-lookup"><span data-stu-id="1326c-138">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="1326c-139">O runspace é armazenado em uma variável e transmitido para o comando `Get-PSBreakPoint` com o parâmetro **Runspace**.</span><span class="sxs-lookup"><span data-stu-id="1326c-139">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="1326c-140">Em seguida, você pode inspecionar o ponto de interrupção na variável `$breakpoint`.</span><span class="sxs-lookup"><span data-stu-id="1326c-140">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="psansirendering"></a><span data-ttu-id="1326c-141">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="1326c-141">PSAnsiRendering</span></span>

<span data-ttu-id="1326c-142">O experimento foi adicionado no PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="1326c-142">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="1326c-143">O recurso permite alterar a forma como o mecanismo do PowerShell gera texto e adiciona a variável automática `$PSStyle` para controlar a renderização ANSI da saída da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1326c-143">The feature enables changes how the PowerShell engine outputs text and add the `$PSStyle` automatic variable to control ANSI rendering of string output.</span></span>

```powershell
PS> $PSStyle | Get-Member

   TypeName: System.Management.Automation.PSStyle

Name             MemberType Definition
----             ---------- ----------
Equals           Method     bool Equals(System.Object obj)
FormatHyperlink  Method     string FormatHyperlink(string text, uri link)
GetHashCode      Method     int GetHashCode()
GetType          Method     type GetType()
ToString         Method     string ToString()
Background       Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;}
Blink            Property   string Blink {get;}
BlinkOff         Property   string BlinkOff {get;}
Bold             Property   string Bold {get;}
BoldOff          Property   string BoldOff {get;}
Foreground       Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;}
Formatting       Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;}
Hidden           Property   string Hidden {get;}
HiddenOff        Property   string HiddenOff {get;}
Italic           Property   string Italic {get;}
ItalicOff        Property   string ItalicOff {get;}
OutputRendering  Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Progress         Property   System.Management.Automation.PSStyle+ProgressConfiguration Progress {get;}
Reset            Property   string Reset {get;}
Reverse          Property   string Reverse {get;}
ReverseOff       Property   string ReverseOff {get;}
Strikethrough    Property   string Strikethrough {get;}
StrikethroughOff Property   string StrikethroughOff {get;}
Underline        Property   string Underline {get;}
UnderlineOff     Property   string UnderlineOff {get;}
```

<span data-ttu-id="1326c-144">Os membros de base retornam cadeias de caracteres de sequências de escape ANSI mapeadas para seus nomes.</span><span class="sxs-lookup"><span data-stu-id="1326c-144">The base members return strings of ANSI escape sequences mapped to their names.</span></span> <span data-ttu-id="1326c-145">Os valores são configuráveis para permitir a personalização.</span><span class="sxs-lookup"><span data-stu-id="1326c-145">The values are settable to allow customization.</span></span>

<span data-ttu-id="1326c-146">Para obter mais informações, confira [about_Automatic_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="1326c-146">For more information, see [about_Automatic_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span></span>

> [!NOTE]
> <span data-ttu-id="1326c-147">Para desenvolvedores C#, você pode acessar `PSStyle` como um singleton.</span><span class="sxs-lookup"><span data-stu-id="1326c-147">For C# developers, you can access `PSStyle` as a singleton.</span></span> <span data-ttu-id="1326c-148">O uso terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="1326c-148">Usage will look like this:</span></span>
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> <span data-ttu-id="1326c-149">`PSStyle` existe no namespace System.Management.Automation.</span><span class="sxs-lookup"><span data-stu-id="1326c-149">`PSStyle` exists in the System.Management.Automation namespace.</span></span>

<span data-ttu-id="1326c-150">Junto com o acesso ao `$PSStyle`, isso apresenta alterações no mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1326c-150">Along with access to `$PSStyle`, this introduces changes to the PowerShell engine.</span></span> <span data-ttu-id="1326c-151">O sistema de formatação do PowerShell é atualizado para respeitar `$PSStyle.OutputRendering`.</span><span class="sxs-lookup"><span data-stu-id="1326c-151">The PowerShell formatting system is updated to respect `$PSStyle.OutputRendering`.</span></span>

- <span data-ttu-id="1326c-152">O tipo `StringDecorated` é adicionado para manipular cadeias de caracteres de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="1326c-152">`StringDecorated` type is added to handle ANSI escaped strings.</span></span>
- <span data-ttu-id="1326c-153">A propriedade booliana `string IsDecorated` é adicionada para retornar se a cadeia de caracteres contém sequências de escape ANSI com base em se a cadeia de caracteres contém ESC ou C1 CSI.</span><span class="sxs-lookup"><span data-stu-id="1326c-153">`string IsDecorated` boolean property is added to return if the string contains ANSI escape sequences based on if the string contains ESC or C1 CSI.</span></span>
- <span data-ttu-id="1326c-154">A propriedade `Length` retorna _apenas_ o comprimento do texto sem as sequências de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="1326c-154">The `Length` property returns _only_ the length for the text without the ANSI escape sequences.</span></span>
- <span data-ttu-id="1326c-155">O método `StringDecorated Substring(int contentLength)` retorna uma substring começando no índice 0 até o comprimento do conteúdo que não faz parte das sequências de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="1326c-155">`StringDecorated Substring(int contentLength)` method returns a substring starting at index 0 up to the content length that is not a part of ANSI escape sequences.</span></span> <span data-ttu-id="1326c-156">Isso é necessário para a formatação da tabela a fim de truncar cadeias de caracteres e preservar as sequências de escape ANSI que não ocupam espaço de caracteres imprimível.</span><span class="sxs-lookup"><span data-stu-id="1326c-156">This is needed for table formatting to truncate strings and preserve ANSI escape sequences that don't take up printable character space.</span></span>
- <span data-ttu-id="1326c-157">O método `string ToString()` permanece o mesmo e retorna a versão de texto não criptografado da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1326c-157">`string ToString()` method stays the same and returns the plaintext version of the string.</span></span>
- <span data-ttu-id="1326c-158">O método `string ToString(bool Ansi)` retornará a cadeia de caracteres ANSI bruta inserida se o parâmetro `Ansi` for true.</span><span class="sxs-lookup"><span data-stu-id="1326c-158">`string ToString(bool Ansi)` method returns the raw ANSI embedded string if the `Ansi` parameter is true.</span></span> <span data-ttu-id="1326c-159">Caso contrário, uma versão de texto não criptografado com sequências de escape ANSI removidas será retornada.</span><span class="sxs-lookup"><span data-stu-id="1326c-159">Otherwise, a plaintext version with ANSI escape sequences removed is returned.</span></span>

<span data-ttu-id="1326c-160">O `FormatHyperlink(string text, uri link)` retorna uma cadeia de caracteres contendo a sequência de escape ANSI usada para decorar hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="1326c-160">The `FormatHyperlink(string text, uri link)` returns a string containing ANSI escape sequence used to decorate hyperlinks.</span></span> <span data-ttu-id="1326c-161">Alguns hosts de terminal, como o [Terminal do Windows](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701), dão suporte a essa marcação, o que torna o texto renderizado clicável no terminal.</span><span class="sxs-lookup"><span data-stu-id="1326c-161">Some terminal hosts, like the [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701), support this markup, which makes the rendered text clickable in the terminal.</span></span>

## <a name="psansiprogress"></a><span data-ttu-id="1326c-162">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="1326c-162">PSAnsiProgress</span></span>

<span data-ttu-id="1326c-163">O experimento foi adicionado no PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="1326c-163">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="1326c-164">O recurso adiciona o membro `$PSStyle.Progress` e permite controlar a renderização da barra de exibição de progresso.</span><span class="sxs-lookup"><span data-stu-id="1326c-164">The feature adds the `$PSStyle.Progress` member and allows you to control progress view bar rendering.</span></span>

- <span data-ttu-id="1326c-165">`$PSStyle.Progress.Style` – uma cadeia de caracteres ANSI que define o estilo de renderização.</span><span class="sxs-lookup"><span data-stu-id="1326c-165">`$PSStyle.Progress.Style` - An ANSI string setting the rendering style.</span></span>
- <span data-ttu-id="1326c-166">`$PSStyle.Progress.MaxWidth` – define a largura máxima da exibição.</span><span class="sxs-lookup"><span data-stu-id="1326c-166">`$PSStyle.Progress.MaxWidth` - Sets the max width of the view.</span></span> <span data-ttu-id="1326c-167">Defina como `0` para a largura do console.</span><span class="sxs-lookup"><span data-stu-id="1326c-167">Set to `0` for console width.</span></span>
  <span data-ttu-id="1326c-168">Usa como padrão `120`</span><span class="sxs-lookup"><span data-stu-id="1326c-168">Defaults to `120`</span></span>
- <span data-ttu-id="1326c-169">`$PSStyle.Progress.View` – uma enumeração com valores `Minimal` e `Classic`.</span><span class="sxs-lookup"><span data-stu-id="1326c-169">`$PSStyle.Progress.View` - An enum with values, `Minimal` and `Classic`.</span></span> <span data-ttu-id="1326c-170">`Classic` é a renderização existente sem alterações.</span><span class="sxs-lookup"><span data-stu-id="1326c-170">`Classic` is the existing rendering with no changes.</span></span> <span data-ttu-id="1326c-171">`Minimal` é uma renderização mínima de linha única.</span><span class="sxs-lookup"><span data-stu-id="1326c-171">`Minimal` is a single line minimal rendering.</span></span> <span data-ttu-id="1326c-172">`Minimal` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="1326c-172">`Minimal` is the default.</span></span>

<span data-ttu-id="1326c-173">O exemplo a seguir atualiza o estilo de renderização para uma barra de progresso mínima.</span><span class="sxs-lookup"><span data-stu-id="1326c-173">The following example updates the rendering style to a minimal progress bar.</span></span>

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> <span data-ttu-id="1326c-174">O recurso experimental **PSAnsiRendering** deve estar habilitado para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="1326c-174">You must have the **PSAnsiRendering** experimental feature enabled to use this feature.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="1326c-175">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="1326c-175">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="1326c-176">Recomenda comandos potenciais com base na pesquisa de correspondência difusa após um **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="1326c-176">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

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

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="1326c-177">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="1326c-177">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="1326c-178">Quando o operando à esquerda em uma instrução do operador `-replace` não é uma cadeia de caracteres, esse operando é convertido em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1326c-178">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="1326c-179">Quando esse recurso está desabilitado, o operador `-replace` faz uma conversão de cadeia de caracteres sensível à cultura.</span><span class="sxs-lookup"><span data-stu-id="1326c-179">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="1326c-180">Por exemplo, se sua cultura for definida como francês (FR), o valor `1.2` será convertido para a cadeia de caracteres `1,2`.</span><span class="sxs-lookup"><span data-stu-id="1326c-180">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="1326c-181">Com o recurso habilitado:</span><span class="sxs-lookup"><span data-stu-id="1326c-181">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="1326c-182">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="1326c-182">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="1326c-183">Habilita a compilação para o formato MOF em sistemas que não são do Windows e permite o uso de `Invoke-DSCResource` sem um LCM.</span><span class="sxs-lookup"><span data-stu-id="1326c-183">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="1326c-184">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="1326c-184">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="1326c-185">Esse recurso examina o comando digitado no shell e, se todos os comandos forem comandos de proxy de comunicação remota implícitos que formam um pipeline simples, os comandos serão agrupados em lote e invocados como um único pipeline remoto.</span><span class="sxs-lookup"><span data-stu-id="1326c-185">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="1326c-186">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="1326c-186">Example:</span></span>

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

<span data-ttu-id="1326c-187">Como visto acima, com o recurso de envio em lote habilitado, todos os três comandos de proxy de comunicação remota implícito, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, executados na sessão remota e o resultado do pipeline são os únicos dados retornados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1326c-187">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="1326c-188">Isso diminui a quantidade de dados enviados entre o cliente e a sessão remota, além de reduzir a quantidade de serialização e desserialização de objetos.</span><span class="sxs-lookup"><span data-stu-id="1326c-188">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="1326c-189">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="1326c-189">PSNativePSPathResolution</span></span>

<span data-ttu-id="1326c-190">Se um caminho PSDrive que usa o provedor FileSystem for passado para um comando nativo, o caminho do arquivo resolvido será passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="1326c-190">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="1326c-191">Isso significa que um comando como `code temp:/test.txt` agora funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="1326c-191">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="1326c-192">Além disso, no Windows, se o caminho começar com `~`, isso será resolvido para o caminho completo e passado para o comando nativo.</span><span class="sxs-lookup"><span data-stu-id="1326c-192">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="1326c-193">Em ambos os casos, o caminho é normalizado para os separadores de diretório para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="1326c-193">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="1326c-194">Se o caminho não for um PSDrive ou `~` (no Windows), a normalização de caminho não ocorrerá</span><span class="sxs-lookup"><span data-stu-id="1326c-194">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="1326c-195">Se o caminho estiver entre aspas simples, ele não será resolvido e tratado como literal</span><span class="sxs-lookup"><span data-stu-id="1326c-195">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="1326c-196">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="1326c-196">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="1326c-197">Quando esse recurso experimental está habilitado, os registros de erro redirecionados de comandos nativos, como ao usar operadores de redirecionamento (`2>&1`), não são gravados na variável `$Error`, e a variável de preferência `$ErrorActionPreference` não afeta a saída redirecionada.</span><span class="sxs-lookup"><span data-stu-id="1326c-197">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="1326c-198">Muitos comandos nativos gravam em `stderr` como um fluxo alternativo para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="1326c-198">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="1326c-199">Esse comportamento pode causar confusão ao examinar erros, ou o usuário pode perder as informações de saída adicionais caso `$ErrorActionPreference` esteja definido como um estado que desativa a saída.</span><span class="sxs-lookup"><span data-stu-id="1326c-199">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="1326c-200">Quando um comando nativo tem um código de saída diferente de zero, `$?` é definido como `$false`.</span><span class="sxs-lookup"><span data-stu-id="1326c-200">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="1326c-201">Se o código de saída for zero, `$?` será definido como `$true`.</span><span class="sxs-lookup"><span data-stu-id="1326c-201">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="1326c-202">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="1326c-202">PSNullConditionalOperators</span></span>

<span data-ttu-id="1326c-203">Apresenta novos operadores para operadores de acesso a membros condicional nulo – `?.` e `?[]`.</span><span class="sxs-lookup"><span data-stu-id="1326c-203">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="1326c-204">Operadores de acesso a membros nulo podem ser usados em tipos escalares e tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="1326c-204">Null member access operators can be used on scalar types and array types.</span></span> <span data-ttu-id="1326c-205">Retorne o valor do membro acessado se a variável não for nula.</span><span class="sxs-lookup"><span data-stu-id="1326c-205">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="1326c-206">Se o valor da variável for nulo, retornará nulo.</span><span class="sxs-lookup"><span data-stu-id="1326c-206">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="1326c-207">A propriedade `propname` é acessada, e seu valor será retornado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="1326c-207">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="1326c-208">Da mesma forma, o indexador será usado somente se `$x` não for nulo.</span><span class="sxs-lookup"><span data-stu-id="1326c-208">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="1326c-209">Se `$x` for nulo, nulo será retornado.</span><span class="sxs-lookup"><span data-stu-id="1326c-209">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="1326c-210">Os operadores `?.` e `?[]` são operadores de acesso a membros e não permitem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="1326c-210">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="1326c-211">Como o PowerShell permite `?` como parte do nome da variável, a desambiguidade é necessária quando os operadores são usados sem um espaço entre o nome da variável e o operador.</span><span class="sxs-lookup"><span data-stu-id="1326c-211">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="1326c-212">Para desambiguar, as variáveis devem usar `{}` em volta do nome da variável, como: `${x?}?.propertyName` ou `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="1326c-212">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="1326c-213">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="1326c-213">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="1326c-214">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="1326c-214">PSTempDrive</span></span>

<span data-ttu-id="1326c-215">Cria o PSDrive `TEMP:` mapeado para o caminho do diretório temporário do usuário.</span><span class="sxs-lookup"><span data-stu-id="1326c-215">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="1326c-216">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="1326c-216">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="1326c-217">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="1326c-217">PSUnixFileStat</span></span>

<span data-ttu-id="1326c-218">Esse recurso fornece um novo comportamento para incluir dados da API **stat** do UNIX na saída do provedor do sistema de arquivos para facilitar uma listagem de arquivos semelhante ao UNIX.</span><span class="sxs-lookup"><span data-stu-id="1326c-218">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="1326c-219">Ele adiciona uma nova propriedade de anotação no provedor filesystem chamado **UnixStat** que inclui uma expressão comum da API `stat(2)` do sistema de tipos UNIX subjacente.</span><span class="sxs-lookup"><span data-stu-id="1326c-219">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="1326c-220">A saída de `Get-ChildItem` deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="1326c-220">The output from `Get-ChildItem` should look something like this:</span></span>

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
> <span data-ttu-id="1326c-221">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="1326c-221">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="1326c-222">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="1326c-222">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="1326c-223">Esse recurso permite o preenchimento com Tab de funções e cmdlets abreviados:</span><span class="sxs-lookup"><span data-stu-id="1326c-223">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="1326c-224">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="1326c-224">For example:</span></span>

- <span data-ttu-id="1326c-225">`i-psdf<tab>` retorna `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="1326c-225">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="1326c-226">`u-akvmssdr<tab>` retorna `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="1326c-226">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="1326c-227">Isso só funciona para preenchimento com Tab (uso interativo), portanto, `i-psdf` não é um nome de cmdlet válido em um script.</span><span class="sxs-lookup"><span data-stu-id="1326c-227">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="1326c-228">Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.</span><span class="sxs-lookup"><span data-stu-id="1326c-228">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="1326c-229">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="1326c-229">PSSubsystemPluginModel</span></span>

<span data-ttu-id="1326c-230">Esse recurso habilita o modelo de plug-in do subsistema no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1326c-230">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="1326c-231">Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly.</span><span class="sxs-lookup"><span data-stu-id="1326c-231">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="1326c-232">Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1326c-232">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="1326c-233">Atualmente, há suporte apenas para o subsistema **CommandPredictor**.</span><span class="sxs-lookup"><span data-stu-id="1326c-233">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="1326c-234">Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados.</span><span class="sxs-lookup"><span data-stu-id="1326c-234">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="1326c-235">No futuro, será possível dividir **Job**, **CommandCompleter**, **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="1326c-235">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="1326c-236">O recurso experimental inclui um novo cmdlet, o [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span><span class="sxs-lookup"><span data-stu-id="1326c-236">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="1326c-237">Esse cmdlet só está disponível quando o recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1326c-237">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="1326c-238">Esse cmdlet retorna informações sobre os subsistemas disponíveis no sistema.</span><span class="sxs-lookup"><span data-stu-id="1326c-238">This cmdlet returns information about the subsystems that are available on the system.</span></span>
