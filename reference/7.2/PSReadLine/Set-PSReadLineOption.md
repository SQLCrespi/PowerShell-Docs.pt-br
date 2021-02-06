---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: cac2c2bb8ce1f3a28c0d91c7503b3ac4d038ccad
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "99595563"
---
# <span data-ttu-id="b88b9-102">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b88b9-102">Set-PSReadLineOption</span></span>

## <span data-ttu-id="b88b9-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="b88b9-103">Synopsis</span></span>
<span data-ttu-id="b88b9-104">Personaliza o comportamento da edição de linha de comando no **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-104">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="b88b9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b88b9-105">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func`2[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action`1[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-PredictionSource <PredictionSource>]
 [-PredictionViewStyle <PredictionViewStyle>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="b88b9-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b88b9-106">Description</span></span>

<span data-ttu-id="b88b9-107">O `Set-PSReadLineOption` cmdlet personaliza o comportamento do módulo **PSReadLine** quando você está editando a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="b88b9-107">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="b88b9-108">Para exibir as configurações de **PSReadLine** , use `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-108">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="b88b9-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b88b9-109">Examples</span></span>

### <span data-ttu-id="b88b9-110">Exemplo 1: definir cores de primeiro e segundo plano</span><span class="sxs-lookup"><span data-stu-id="b88b9-110">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="b88b9-111">Este exemplo define **PSReadLine** para exibir o token de **Comentário** com texto em primeiro plano verde em um plano de fundo cinza.</span><span class="sxs-lookup"><span data-stu-id="b88b9-111">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="b88b9-112">Na sequência de escape usada no exemplo, **32** representa a cor do primeiro plano e **47** representa a cor do plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="b88b9-112">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="b88b9-113">Você pode optar por definir apenas uma cor de texto em primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="b88b9-113">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="b88b9-114">Por exemplo, uma cor de texto de primeiro plano verde brilhante para o token de **Comentário** : ``"Comment"="`e[92m"`` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-114">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="b88b9-115">Exemplo 2: definir estilo de sino</span><span class="sxs-lookup"><span data-stu-id="b88b9-115">Example 2: Set bell style</span></span>

<span data-ttu-id="b88b9-116">Neste exemplo, o **PSReadLine** responderá a erros ou condições que exigem a atenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="b88b9-116">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="b88b9-117">O **bellstyle** é definido para emitir um aviso sonoro em 1221 Hz para 60 ms.</span><span class="sxs-lookup"><span data-stu-id="b88b9-117">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="b88b9-118">Esse recurso pode não funcionar em todos os hosts em plataformas.</span><span class="sxs-lookup"><span data-stu-id="b88b9-118">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="b88b9-119">Exemplo 3: definir várias opções</span><span class="sxs-lookup"><span data-stu-id="b88b9-119">Example 3: Set multiple options</span></span>

<span data-ttu-id="b88b9-120">`Set-PSReadLineOption` pode definir várias opções com uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b88b9-120">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

<span data-ttu-id="b88b9-121">A `$PSReadLineOptions` tabela de hash define as chaves e os valores.</span><span class="sxs-lookup"><span data-stu-id="b88b9-121">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="b88b9-122">`Set-PSReadLineOption` usa as chaves e valores com `@PSReadLineOptions` para atualizar as opções de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="b88b9-122">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="b88b9-123">Você pode exibir as chaves e os valores que inserem o nome da tabela de hash `$PSReadLineOptions` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b88b9-123">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="b88b9-124">Exemplo 4: definir opções de várias cores</span><span class="sxs-lookup"><span data-stu-id="b88b9-124">Example 4: Set multiple color options</span></span>

<span data-ttu-id="b88b9-125">Este exemplo mostra como definir mais de um valor de cor em um único comando.</span><span class="sxs-lookup"><span data-stu-id="b88b9-125">This example shows how to set more than one color value in a single command.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### <span data-ttu-id="b88b9-126">Exemplo 5: definir valores de cor para vários tipos</span><span class="sxs-lookup"><span data-stu-id="b88b9-126">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="b88b9-127">Este exemplo mostra três métodos diferentes para definir a cor dos tokens exibidos em **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-127">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### <span data-ttu-id="b88b9-128">Exemplo 6: usar ViModeChangeHandler para exibir as alterações do modo vi</span><span class="sxs-lookup"><span data-stu-id="b88b9-128">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="b88b9-129">Este exemplo emite uma alteração de cursor de VT escape em resposta a uma alteração no modo **vi** .</span><span class="sxs-lookup"><span data-stu-id="b88b9-129">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

<span data-ttu-id="b88b9-130">A função **OnViModeChange** define as opções de cursor para os modos **vi** : INSERT e Command.</span><span class="sxs-lookup"><span data-stu-id="b88b9-130">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="b88b9-131">**ViModeChangeHandler** usa o `Function:` provedor para fazer referência a **OnViModeChange** como um objeto de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="b88b9-131">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="b88b9-132">Para obter mais informações, consulte [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="b88b9-132">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="b88b9-133">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b88b9-133">Parameters</span></span>

### <span data-ttu-id="b88b9-134">-AddToHistoryHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-134">-AddToHistoryHandler</span></span>

<span data-ttu-id="b88b9-135">Especifica um **scriptblock** que controla quais comandos são adicionados ao histórico de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="b88b9-135">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="b88b9-136">O **scriptblock** recebe a linha de comando como entrada.</span><span class="sxs-lookup"><span data-stu-id="b88b9-136">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="b88b9-137">Se o **scriptblock** retornar `$True` , a linha de comando será adicionada ao histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-137">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-138">-AnsiEscapeTimeout</span><span class="sxs-lookup"><span data-stu-id="b88b9-138">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="b88b9-139">Essa opção é específica ao Windows quando a entrada é redirecionada, por exemplo, ao ser executada em `tmux` ou `screen` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-139">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="b88b9-140">Com a entrada redirecionada no Windows, muitas chaves são enviadas como uma sequência de caracteres começando com o caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="b88b9-140">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="b88b9-141">É impossível distinguir entre um único caractere de escape seguido de mais caracteres e uma sequência de escape válida.</span><span class="sxs-lookup"><span data-stu-id="b88b9-141">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="b88b9-142">A suposição é que o terminal possa enviar os caracteres mais rápido do que os tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="b88b9-142">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="b88b9-143">**PSReadLine** aguarda esse tempo limite antes de concluir que recebeu uma sequência de escape completa.</span><span class="sxs-lookup"><span data-stu-id="b88b9-143">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="b88b9-144">Se você vir caracteres aleatórios ou inesperados ao digitar, poderá ajustar esse tempo limite.</span><span class="sxs-lookup"><span data-stu-id="b88b9-144">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-145">-Bellstyle</span><span class="sxs-lookup"><span data-stu-id="b88b9-145">-BellStyle</span></span>

<span data-ttu-id="b88b9-146">Especifica como o **PSReadLine** responde a várias condições ambíguas e de erro.</span><span class="sxs-lookup"><span data-stu-id="b88b9-146">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="b88b9-147">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b88b9-147">The valid values are as follows:</span></span>

- <span data-ttu-id="b88b9-148">**Audível**: um breve bipe.</span><span class="sxs-lookup"><span data-stu-id="b88b9-148">**Audible**: A short beep.</span></span>
- <span data-ttu-id="b88b9-149">**Visual**: o texto pisca brevemente.</span><span class="sxs-lookup"><span data-stu-id="b88b9-149">**Visual**: Text flashes briefly.</span></span>
- <span data-ttu-id="b88b9-150">**Nenhum**: nenhum comentário.</span><span class="sxs-lookup"><span data-stu-id="b88b9-150">**None**: No feedback.</span></span>

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-151">-Cores</span><span class="sxs-lookup"><span data-stu-id="b88b9-151">-Colors</span></span>

<span data-ttu-id="b88b9-152">O parâmetro **Colors** especifica várias cores usadas pelo **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-152">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="b88b9-153">O argumento é uma tabela de hash em que as chaves especificam qual elemento e os valores especificam a cor.</span><span class="sxs-lookup"><span data-stu-id="b88b9-153">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="b88b9-154">Para obter mais informações, consulte [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="b88b9-154">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="b88b9-155">As cores podem ser um valor de **ConsoleColor**, por exemplo `[ConsoleColor]::Red` , ou uma sequência de escape ANSI válida.</span><span class="sxs-lookup"><span data-stu-id="b88b9-155">Colors can be either a value from **ConsoleColor**, for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="b88b9-156">As sequências de escape válidas dependem do seu terminal.</span><span class="sxs-lookup"><span data-stu-id="b88b9-156">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="b88b9-157">No PowerShell 5,0, uma sequência de escape de exemplo para texto vermelho é `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-157">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="b88b9-158">No PowerShell 6 e acima, a mesma sequência de escape é `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-158">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="b88b9-159">Você pode especificar outras sequências de escape, incluindo os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="b88b9-159">You can specify other escape sequences including the following types:</span></span>

<span data-ttu-id="b88b9-160">Duas configurações de cores foram adicionadas para dar suporte à personalização do `ListView` no PSReadLine 2.2.0:</span><span class="sxs-lookup"><span data-stu-id="b88b9-160">Two color settings were added to support customization of the `ListView` in PSReadLine 2.2.0:</span></span>

- <span data-ttu-id="b88b9-161">**ListPredictionColor** -defina a cor do caractere à esquerda `>` e o nome da fonte à direita, por exemplo, `[History]` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-161">**ListPredictionColor** - set color for the leading `>` character and the trailing source name, e.g. `[History]`.</span></span> <span data-ttu-id="b88b9-162">Por padrão, ele usa `DarkYellow` como a cor de primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="b88b9-162">By default, it uses `DarkYellow` as the foreground color.</span></span>
- <span data-ttu-id="b88b9-163">**ListPredictionSelectedColor** -defina a cor para indicar que um item de lista está selecionado.</span><span class="sxs-lookup"><span data-stu-id="b88b9-163">**ListPredictionSelectedColor** - set color for indicating a list item is selected.</span></span> <span data-ttu-id="b88b9-164">Por padrão, ele usa `DarkBlack` como a cor do plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="b88b9-164">By default, it uses `DarkBlack` as the background color.</span></span>

- <span data-ttu-id="b88b9-165">cor de 256</span><span class="sxs-lookup"><span data-stu-id="b88b9-165">256 color</span></span>
- <span data-ttu-id="b88b9-166">cor de 24 bits</span><span class="sxs-lookup"><span data-stu-id="b88b9-166">24-bit color</span></span>
- <span data-ttu-id="b88b9-167">Primeiro plano, plano de fundo ou ambos</span><span class="sxs-lookup"><span data-stu-id="b88b9-167">Foreground, background, or both</span></span>
- <span data-ttu-id="b88b9-168">Inverso, negrito</span><span class="sxs-lookup"><span data-stu-id="b88b9-168">Inverse, bold</span></span>

<span data-ttu-id="b88b9-169">Para obter mais informações sobre códigos de cor ANSI, consulte [código de escape ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="b88b9-169">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="b88b9-170">As chaves válidas incluem:</span><span class="sxs-lookup"><span data-stu-id="b88b9-170">The valid keys include:</span></span>

- <span data-ttu-id="b88b9-171">**ContinuationPrompt**: a cor do prompt de continuação.</span><span class="sxs-lookup"><span data-stu-id="b88b9-171">**ContinuationPrompt**: The color of the continuation prompt.</span></span>
- <span data-ttu-id="b88b9-172">**Ênfase**: a cor de ênfase.</span><span class="sxs-lookup"><span data-stu-id="b88b9-172">**Emphasis**: The emphasis color.</span></span> <span data-ttu-id="b88b9-173">Por exemplo, o texto correspondente ao pesquisar o histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-173">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="b88b9-174">**Erro**: a cor do erro.</span><span class="sxs-lookup"><span data-stu-id="b88b9-174">**Error**: The error color.</span></span> <span data-ttu-id="b88b9-175">Por exemplo, no prompt.</span><span class="sxs-lookup"><span data-stu-id="b88b9-175">For example, in the prompt.</span></span>
- <span data-ttu-id="b88b9-176">**Seleção**: a cor para realçar a seleção de menu ou o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="b88b9-176">**Selection**: The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="b88b9-177">**Padrão**: a cor padrão do token.</span><span class="sxs-lookup"><span data-stu-id="b88b9-177">**Default**: The default token color.</span></span>
- <span data-ttu-id="b88b9-178">**Comentário**: a cor do token de comentário.</span><span class="sxs-lookup"><span data-stu-id="b88b9-178">**Comment**: The comment token color.</span></span>
- <span data-ttu-id="b88b9-179">**Palavra-chave**: a cor do token de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="b88b9-179">**Keyword**: The keyword token color.</span></span>
- <span data-ttu-id="b88b9-180">**String**: a cor do token da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b88b9-180">**String**: The string token color.</span></span>
- <span data-ttu-id="b88b9-181">**Operador**: a cor do token do operador.</span><span class="sxs-lookup"><span data-stu-id="b88b9-181">**Operator**: The operator token color.</span></span>
- <span data-ttu-id="b88b9-182">**Variável**: a cor do token variável.</span><span class="sxs-lookup"><span data-stu-id="b88b9-182">**Variable**: The variable token color.</span></span>
- <span data-ttu-id="b88b9-183">**Comando**: a cor do token de comando.</span><span class="sxs-lookup"><span data-stu-id="b88b9-183">**Command**: The command token color.</span></span>
- <span data-ttu-id="b88b9-184">**Parâmetro**: a cor do token do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b88b9-184">**Parameter**: The parameter token color.</span></span>
- <span data-ttu-id="b88b9-185">**Tipo**: a cor do token de tipo.</span><span class="sxs-lookup"><span data-stu-id="b88b9-185">**Type**: The type token color.</span></span>
- <span data-ttu-id="b88b9-186">**Número**: a cor do token de número.</span><span class="sxs-lookup"><span data-stu-id="b88b9-186">**Number**: The number token color.</span></span>
- <span data-ttu-id="b88b9-187">**Membro**: a cor do token do nome do membro.</span><span class="sxs-lookup"><span data-stu-id="b88b9-187">**Member**: The member name token color.</span></span>
- <span data-ttu-id="b88b9-188">**InlinePrediction**: a cor da exibição embutida da sugestão preditiva.</span><span class="sxs-lookup"><span data-stu-id="b88b9-188">**InlinePrediction**: The color for the inline view of the predictive suggestion.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-189">-CommandValidationHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-189">-CommandValidationHandler</span></span>

<span data-ttu-id="b88b9-190">Especifica um **scriptblock** que é chamado de **ValidateAndAcceptLine**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-190">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="b88b9-191">Se uma exceção for lançada, a validação falhará e o erro será relatado.</span><span class="sxs-lookup"><span data-stu-id="b88b9-191">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="b88b9-192">Antes de lançar uma exceção, o manipulador de validação pode colocar o cursor no ponto do erro para facilitar a correção.</span><span class="sxs-lookup"><span data-stu-id="b88b9-192">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="b88b9-193">Um manipulador de validação também pode alterar a linha de comando, como para corrigir erros tipográficos comuns.</span><span class="sxs-lookup"><span data-stu-id="b88b9-193">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="b88b9-194">**ValidateAndAcceptLine** é usado para evitar a confusão de seu histórico com comandos que não funcionam.</span><span class="sxs-lookup"><span data-stu-id="b88b9-194">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-195">-CompletionQueryItems</span><span class="sxs-lookup"><span data-stu-id="b88b9-195">-CompletionQueryItems</span></span>

<span data-ttu-id="b88b9-196">Especifica o número máximo de itens de conclusão que são mostrados sem solicitação.</span><span class="sxs-lookup"><span data-stu-id="b88b9-196">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="b88b9-197">Se o número de itens a serem mostrados for maior que esse valor, **PSReadLine** solicitará **Sim/não** antes de exibir os itens de conclusão.</span><span class="sxs-lookup"><span data-stu-id="b88b9-197">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-198">-ContinuationPrompt</span><span class="sxs-lookup"><span data-stu-id="b88b9-198">-ContinuationPrompt</span></span>

<span data-ttu-id="b88b9-199">Especifica a cadeia de caracteres exibida no início das linhas subsequentes quando a entrada de várias linhas é inserida.</span><span class="sxs-lookup"><span data-stu-id="b88b9-199">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="b88b9-200">O padrão é duplo de sinais de maior que ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="b88b9-200">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="b88b9-201">Uma cadeia de caracteres vazia é válida.</span><span class="sxs-lookup"><span data-stu-id="b88b9-201">An empty string is valid.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-202">-DingDuration</span><span class="sxs-lookup"><span data-stu-id="b88b9-202">-DingDuration</span></span>

<span data-ttu-id="b88b9-203">Especifica a duração do aviso sonoro quando **bellstyle** é definido como **audível**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-203">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-204">-DingTone</span><span class="sxs-lookup"><span data-stu-id="b88b9-204">-DingTone</span></span>

<span data-ttu-id="b88b9-205">Especifica o Tom em Hertz (Hz) do bipe quando **bellstyle** é definido como **audível**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-205">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-206">-EditMode</span><span class="sxs-lookup"><span data-stu-id="b88b9-206">-EditMode</span></span>

<span data-ttu-id="b88b9-207">Especifica o modo de edição de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="b88b9-207">Specifies the command line editing mode.</span></span> <span data-ttu-id="b88b9-208">O uso desse parâmetro redefine as associações de chave definidas por `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-208">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="b88b9-209">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b88b9-209">The valid values are as follows:</span></span>

- <span data-ttu-id="b88b9-210">**Windows**: associações de chave emulam o PowerShell, o cmd e o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b88b9-210">**Windows**: Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="b88b9-211">**Emacs**: associações de chave emulam bash ou Emacs.</span><span class="sxs-lookup"><span data-stu-id="b88b9-211">**Emacs**: Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="b88b9-212">**Vi**: associações de chave emulam vi.</span><span class="sxs-lookup"><span data-stu-id="b88b9-212">**Vi**: Key bindings emulate Vi.</span></span>

<span data-ttu-id="b88b9-213">Use `Get-PSReadLineKeyHandler` para ver as associações de chave para o **EditMode** configurado no momento.</span><span class="sxs-lookup"><span data-stu-id="b88b9-213">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-214">-ExtraPromptLineCount</span><span class="sxs-lookup"><span data-stu-id="b88b9-214">-ExtraPromptLineCount</span></span>

<span data-ttu-id="b88b9-215">Especifica o número de linhas extras.</span><span class="sxs-lookup"><span data-stu-id="b88b9-215">Specifies the number of extra lines.</span></span>

<span data-ttu-id="b88b9-216">Se o prompt se estender por mais de uma linha, especifique um valor para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b88b9-216">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="b88b9-217">Use esta opção quando desejar que linhas extras estejam disponíveis quando o **PSReadLine** exibir o prompt depois de mostrar alguma saída.</span><span class="sxs-lookup"><span data-stu-id="b88b9-217">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="b88b9-218">Por exemplo, **PSReadLine** retorna uma lista de conclusões.</span><span class="sxs-lookup"><span data-stu-id="b88b9-218">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="b88b9-219">Essa opção é necessária para menos do que nas versões anteriores do **PSReadLine**, mas é útil quando a `InvokePrompt` função é usada.</span><span class="sxs-lookup"><span data-stu-id="b88b9-219">This option is needed less than in previous versions of **PSReadLine**, but is useful when the `InvokePrompt` function is used.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-220">-HistoryNoDuplicates</span><span class="sxs-lookup"><span data-stu-id="b88b9-220">-HistoryNoDuplicates</span></span>

<span data-ttu-id="b88b9-221">Esta opção controla o comportamento de recuperação.</span><span class="sxs-lookup"><span data-stu-id="b88b9-221">This option controls the recall behavior.</span></span> <span data-ttu-id="b88b9-222">Comandos duplicados ainda são adicionados ao arquivo de histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-222">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="b88b9-223">Quando essa opção é definida, somente a invocação mais recente é exibida durante a rechamada de comandos.</span><span class="sxs-lookup"><span data-stu-id="b88b9-223">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="b88b9-224">Comandos repetidos são adicionados ao histórico para preservar a ordenação durante a RECALL.</span><span class="sxs-lookup"><span data-stu-id="b88b9-224">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="b88b9-225">No entanto, normalmente você não deseja ver o comando várias vezes ao chamar ou pesquisar o histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-225">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="b88b9-226">Por padrão, a propriedade **HistoryNoDuplicates** do objeto **PSConsoleReadLineOptions** global é definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-226">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b88b9-227">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-227">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b88b9-228">Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-228">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="b88b9-229">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="b88b9-229">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-230">-HistorySavePath</span><span class="sxs-lookup"><span data-stu-id="b88b9-230">-HistorySavePath</span></span>

<span data-ttu-id="b88b9-231">Especifica o caminho para o arquivo em que o histórico é salvo.</span><span class="sxs-lookup"><span data-stu-id="b88b9-231">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="b88b9-232">Computadores que executam plataformas Windows ou não Windows armazenam o arquivo em locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="b88b9-232">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="b88b9-233">O nome do arquivo é armazenado em uma variável `$($host.Name)_history.txt` , por exemplo `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-233">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="b88b9-234">Se você não usar esse parâmetro, o caminho padrão será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b88b9-234">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="b88b9-235">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b88b9-235">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="b88b9-236">**Não Windows**</span><span class="sxs-lookup"><span data-stu-id="b88b9-236">**non-Windows**</span></span>

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-237">-HistorySaveStyle</span><span class="sxs-lookup"><span data-stu-id="b88b9-237">-HistorySaveStyle</span></span>

<span data-ttu-id="b88b9-238">Especifica como o **PSReadLine** salva o histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-238">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="b88b9-239">Estes são os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="b88b9-239">Valid values are as follows:</span></span>

- <span data-ttu-id="b88b9-240">**SaveIncrementally**: salvar histórico depois que cada comando for executado e compartilhar entre várias instâncias do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b88b9-240">**SaveIncrementally**: Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="b88b9-241">**SaveAtExit**: acrescentar arquivo de histórico quando o PowerShell for encerrado.</span><span class="sxs-lookup"><span data-stu-id="b88b9-241">**SaveAtExit**: Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="b88b9-242">**SaveNothing**: não use um arquivo de histórico.</span><span class="sxs-lookup"><span data-stu-id="b88b9-242">**SaveNothing**: Don't use a history file.</span></span>

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-243">-HistorySearchCaseSensitive</span><span class="sxs-lookup"><span data-stu-id="b88b9-243">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="b88b9-244">Especifica que a pesquisa de histórico diferencia maiúsculas de minúsculas em funções como **ReverseSearchHistory** ou **HistorySearchBackward**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-244">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="b88b9-245">Por padrão, a propriedade **HistorySearchCaseSensitive** do objeto **PSConsoleReadLineOptions** global é definida como `False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-245">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b88b9-246">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-246">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b88b9-247">Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-247">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="b88b9-248">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="b88b9-248">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-249">-HistorySearchCursorMovesToEnd</span><span class="sxs-lookup"><span data-stu-id="b88b9-249">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="b88b9-250">Indica que o cursor se move para o final dos comandos que você carrega do histórico usando uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b88b9-250">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="b88b9-251">Quando esse parâmetro é definido como `$False` , o cursor permanece na posição em que você pressionou as setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="b88b9-251">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="b88b9-252">Por padrão, a propriedade **HistorySearchCursorMovesToEnd** do objeto **PSConsoleReadLineOptions** global é definida como `False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-252">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b88b9-253">Usando este **SwitchParameter** , defina o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-253">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="b88b9-254">Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-254">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="b88b9-255">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="b88b9-255">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-256">-MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="b88b9-256">-MaximumHistoryCount</span></span>

<span data-ttu-id="b88b9-257">Especifica o número máximo de comandos a serem salvos no histórico de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="b88b9-257">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="b88b9-258">O histórico de **PSReadLine** é separado do histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b88b9-258">**PSReadLine** history is separate from PowerShell history.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-259">-MaximumKillRingCount</span><span class="sxs-lookup"><span data-stu-id="b88b9-259">-MaximumKillRingCount</span></span>

<span data-ttu-id="b88b9-260">Especifica o número máximo de itens armazenados no Kill Ring.</span><span class="sxs-lookup"><span data-stu-id="b88b9-260">Specifies the maximum number of items stored in the kill ring.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-261">-PromptText</span><span class="sxs-lookup"><span data-stu-id="b88b9-261">-PromptText</span></span>

<span data-ttu-id="b88b9-262">Quando há um erro de análise, o **PSReadLine** altera uma parte do prompt vermelho.</span><span class="sxs-lookup"><span data-stu-id="b88b9-262">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="b88b9-263">O **PSReadLine** analisa sua função de prompt para determinar como alterar apenas a cor de parte do prompt.</span><span class="sxs-lookup"><span data-stu-id="b88b9-263">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="b88b9-264">Essa análise não é de 100% confiável.</span><span class="sxs-lookup"><span data-stu-id="b88b9-264">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="b88b9-265">Use esta opção se **PSReadLine** estiver alterando seu prompt de maneiras inesperadas.</span><span class="sxs-lookup"><span data-stu-id="b88b9-265">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="b88b9-266">Inclua qualquer espaço em branco à direita.</span><span class="sxs-lookup"><span data-stu-id="b88b9-266">Include any trailing whitespace.</span></span>

<span data-ttu-id="b88b9-267">Por exemplo, se a função de prompt se parecer com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="b88b9-267">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="b88b9-268">Em seguida, defina:</span><span class="sxs-lookup"><span data-stu-id="b88b9-268">Then set:</span></span>

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-269">-Dicas de ferramentas</span><span class="sxs-lookup"><span data-stu-id="b88b9-269">-ShowToolTips</span></span>

<span data-ttu-id="b88b9-270">Ao exibir as conclusões possíveis, as dicas de ferramentas são mostradas na lista de conclusões.</span><span class="sxs-lookup"><span data-stu-id="b88b9-270">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="b88b9-271">Essa opção é habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="b88b9-271">This option is enabled by default.</span></span> <span data-ttu-id="b88b9-272">Essa opção não foi habilitada por padrão nas versões anteriores do **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-272">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="b88b9-273">Para desabilitar, defina essa opção como `$False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-273">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="b88b9-274">Por padrão, a propriedade **Extooltips** do objeto **PSConsoleReadLineOptions** global é definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-274">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b88b9-275">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-275">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b88b9-276">Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-276">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="b88b9-277">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="b88b9-277">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-278">-ViModeChangeHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-278">-ViModeChangeHandler</span></span>

<span data-ttu-id="b88b9-279">Quando o **ViModeIndicator** é definido como `Script` , o bloco de script fornecido será invocado sempre que o modo for alterado.</span><span class="sxs-lookup"><span data-stu-id="b88b9-279">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="b88b9-280">O bloco de script recebe um argumento do tipo `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="b88b9-280">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="b88b9-281">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="b88b9-281">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-282">-ViModeIndicator</span><span class="sxs-lookup"><span data-stu-id="b88b9-282">-ViModeIndicator</span></span>

<span data-ttu-id="b88b9-283">Essa opção define a indicação visual para o modo **vi** atual.</span><span class="sxs-lookup"><span data-stu-id="b88b9-283">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="b88b9-284">O modo de inserção ou o modo de comando.</span><span class="sxs-lookup"><span data-stu-id="b88b9-284">Either insert mode or command mode.</span></span>

<span data-ttu-id="b88b9-285">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b88b9-285">The valid values are as follows:</span></span>

- <span data-ttu-id="b88b9-286">**Nenhum**: não há nenhuma indicação.</span><span class="sxs-lookup"><span data-stu-id="b88b9-286">**None**: There's no indication.</span></span>
- <span data-ttu-id="b88b9-287">**Prompt**: o prompt muda de cor.</span><span class="sxs-lookup"><span data-stu-id="b88b9-287">**Prompt**: The prompt changes color.</span></span>
- <span data-ttu-id="b88b9-288">**Cursor**: o tamanho das alterações do cursor.</span><span class="sxs-lookup"><span data-stu-id="b88b9-288">**Cursor**: The cursor changes size.</span></span>
- <span data-ttu-id="b88b9-289">**Script**: o texto especificado pelo usuário é impresso.</span><span class="sxs-lookup"><span data-stu-id="b88b9-289">**Script**: User-specified text is printed.</span></span>

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-290">-WordDelimiters</span><span class="sxs-lookup"><span data-stu-id="b88b9-290">-WordDelimiters</span></span>

<span data-ttu-id="b88b9-291">Especifica os caracteres que delimitam palavras para funções como **ForwardWord** ou **KillWord**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-291">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"---
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-292">-PredictionSource</span><span class="sxs-lookup"><span data-stu-id="b88b9-292">-PredictionSource</span></span>

<span data-ttu-id="b88b9-293">Especifica a fonte de PSReadLine para obter sugestões preditivas.</span><span class="sxs-lookup"><span data-stu-id="b88b9-293">Specifies the source for PSReadLine to get predictive suggestions.</span></span>

<span data-ttu-id="b88b9-294">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="b88b9-294">Valid values are:</span></span>

- <span data-ttu-id="b88b9-295">**Nenhum** – desabilite o recurso IntelliSense preditiva (padrão).</span><span class="sxs-lookup"><span data-stu-id="b88b9-295">**None** - disable the predictive IntelliSense feature (default).</span></span>
<span data-ttu-id="b88b9-296">-\`**Histórico** – habilite o recurso IntelliSense preditiva e use o histórico PSReadLine como a única fonte.</span><span class="sxs-lookup"><span data-stu-id="b88b9-296">-\`**History** - enable the predictive IntelliSense feature and use the PSReadLine history as the only source.</span></span>
- <span data-ttu-id="b88b9-297">**Plugin** – habilite o recurso IntelliSense preditiva e use os plug-ins ( `CommandPrediction` ) como a única fonte.</span><span class="sxs-lookup"><span data-stu-id="b88b9-297">**Plugin** - enable the predictive IntelliSense feature and use the plugins (`CommandPrediction`) as the only source.</span></span> <span data-ttu-id="b88b9-298">Esse valor foi adicionado em PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="b88b9-298">This value was added in PSReadLine 2.2.0</span></span>
- <span data-ttu-id="b88b9-299">**HistoryAndPlugin** -habilite o recurso IntelliSense preditiva e use o histórico e o plug-in como as fontes.</span><span class="sxs-lookup"><span data-stu-id="b88b9-299">**HistoryAndPlugin** - enable the predictive IntelliSense feature and use both history and plugin as the sources.</span></span> <span data-ttu-id="b88b9-300">Esse valor foi adicionado em PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="b88b9-300">This value was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-301">-PredictionViewStyle</span><span class="sxs-lookup"><span data-stu-id="b88b9-301">-PredictionViewStyle</span></span>

<span data-ttu-id="b88b9-302">Define o estilo da exibição do texto de previsão.</span><span class="sxs-lookup"><span data-stu-id="b88b9-302">Sets the style for the display of the predictive text.</span></span> <span data-ttu-id="b88b9-303">O padrão é **InlineView**.</span><span class="sxs-lookup"><span data-stu-id="b88b9-303">The default is **InlineView**.</span></span>

- <span data-ttu-id="b88b9-304">**InlineView** – o estilo como existente hoje, semelhante como no Shell de peixe e Zsh.</span><span class="sxs-lookup"><span data-stu-id="b88b9-304">**InlineView** - the style as existing today, similar as in fish shell and zsh.</span></span> <span data-ttu-id="b88b9-305">(padrão)</span><span class="sxs-lookup"><span data-stu-id="b88b9-305">(default)</span></span>
- <span data-ttu-id="b88b9-306">**ListView** -as sugestões são renderizadas em uma lista suspensa e os usuários podem selecionar usando <kbd>upseta</kbd> e <kbd>seta</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b88b9-306">**ListView** - suggestions are rendered in a drop down list, and users can select using <kbd>UpArrow</kbd> and <kbd>DownArrow</kbd>.</span></span>

<span data-ttu-id="b88b9-307">Esse parâmetro foi adicionado em PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="b88b9-307">This parameter was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionViewStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineView
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b88b9-308">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b88b9-308">CommonParameters</span></span>

<span data-ttu-id="b88b9-309">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b88b9-309">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b88b9-310">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b88b9-310">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b88b9-311">Entradas</span><span class="sxs-lookup"><span data-stu-id="b88b9-311">Inputs</span></span>

### <span data-ttu-id="b88b9-312">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b88b9-312">None</span></span>

<span data-ttu-id="b88b9-313">Não é possível canalizar objetos para `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="b88b9-313">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="b88b9-314">Saídas</span><span class="sxs-lookup"><span data-stu-id="b88b9-314">Outputs</span></span>

### <span data-ttu-id="b88b9-315">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b88b9-315">None</span></span>

<span data-ttu-id="b88b9-316">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b88b9-316">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b88b9-317">Observações</span><span class="sxs-lookup"><span data-stu-id="b88b9-317">Notes</span></span>

## <span data-ttu-id="b88b9-318">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="b88b9-318">Related links</span></span>

[<span data-ttu-id="b88b9-319">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b88b9-319">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="b88b9-320">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-320">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="b88b9-321">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b88b9-321">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="b88b9-322">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-322">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="b88b9-323">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="b88b9-323">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
