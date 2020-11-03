---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadline
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: 15295ffaac320d24a3c9c24c0419118ef2644f90
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196558"
---
# <span data-ttu-id="9983b-103">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="9983b-103">Set-PSReadLineOption</span></span>

## <span data-ttu-id="9983b-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="9983b-104">Synopsis</span></span>
<span data-ttu-id="9983b-105">Personaliza o comportamento da edição de linha de comando no **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-105">Customizes the behavior of command line editing in **PSReadLine** .</span></span>

## <span data-ttu-id="9983b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9983b-106">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="9983b-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9983b-107">Description</span></span>

<span data-ttu-id="9983b-108">O `Set-PSReadLineOption` cmdlet personaliza o comportamento do módulo **PSReadLine** quando você está editando a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9983b-108">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="9983b-109">Para exibir as configurações de **PSReadLine** , use `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="9983b-109">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="9983b-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9983b-110">Examples</span></span>

### <span data-ttu-id="9983b-111">Exemplo 1: definir cores de primeiro e segundo plano</span><span class="sxs-lookup"><span data-stu-id="9983b-111">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="9983b-112">Este exemplo define **PSReadLine** para exibir o token de **Comentário** com texto em primeiro plano verde em um plano de fundo cinza.</span><span class="sxs-lookup"><span data-stu-id="9983b-112">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="9983b-113">Na sequência de escape usada no exemplo, **32** representa a cor do primeiro plano e **47** representa a cor do plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="9983b-113">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="$([char]0x1b)[32;47m" }
```

<span data-ttu-id="9983b-114">Você pode optar por definir apenas uma cor de texto em primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="9983b-114">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="9983b-115">Por exemplo, uma cor de texto de primeiro plano verde brilhante para o token de **Comentário** : `"Comment"="$([char]0x1b)[92m"` .</span><span class="sxs-lookup"><span data-stu-id="9983b-115">For example, a bright green foreground text color for the **Comment** token: `"Comment"="$([char]0x1b)[92m"`.</span></span>

### <span data-ttu-id="9983b-116">Exemplo 2: definir estilo de sino</span><span class="sxs-lookup"><span data-stu-id="9983b-116">Example 2: Set bell style</span></span>

<span data-ttu-id="9983b-117">Neste exemplo, o **PSReadLine** responderá a erros ou condições que exigem a atenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="9983b-117">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="9983b-118">O **bellstyle** é definido para emitir um aviso sonoro em 1221 Hz para 60 ms.</span><span class="sxs-lookup"><span data-stu-id="9983b-118">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="9983b-119">Esse recurso pode não funcionar em todos os hosts em plataformas.</span><span class="sxs-lookup"><span data-stu-id="9983b-119">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="9983b-120">Exemplo 3: definir várias opções</span><span class="sxs-lookup"><span data-stu-id="9983b-120">Example 3: Set multiple options</span></span>

<span data-ttu-id="9983b-121">`Set-PSReadLineOption` pode definir várias opções com uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="9983b-121">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="9983b-122">A `$PSReadLineOptions` tabela de hash define as chaves e os valores.</span><span class="sxs-lookup"><span data-stu-id="9983b-122">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="9983b-123">`Set-PSReadLineOption` usa as chaves e valores com `@PSReadLineOptions` para atualizar as opções de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-123">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="9983b-124">Você pode exibir as chaves e os valores que inserem o nome da tabela de hash `$PSReadLineOptions` na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9983b-124">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="9983b-125">Exemplo 4: definir opções de várias cores</span><span class="sxs-lookup"><span data-stu-id="9983b-125">Example 4: Set multiple color options</span></span>

<span data-ttu-id="9983b-126">Este exemplo mostra como definir mais de um valor de cor em um único comando.</span><span class="sxs-lookup"><span data-stu-id="9983b-126">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="9983b-127">Exemplo 5: definir valores de cor para vários tipos</span><span class="sxs-lookup"><span data-stu-id="9983b-127">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="9983b-128">Este exemplo mostra três métodos diferentes para definir a cor dos tokens exibidos em **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-128">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine** .</span></span>

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

### <span data-ttu-id="9983b-129">Exemplo 6: usar ViModeChangeHandler para exibir as alterações do modo vi</span><span class="sxs-lookup"><span data-stu-id="9983b-129">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="9983b-130">Este exemplo emite uma alteração de cursor de VT escape em resposta a uma alteração no modo **vi** .</span><span class="sxs-lookup"><span data-stu-id="9983b-130">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "$([char]0x1b)[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "$([char]0x1b)[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

<span data-ttu-id="9983b-131">A função **OnViModeChange** define as opções de cursor para os modos **vi** : INSERT e Command.</span><span class="sxs-lookup"><span data-stu-id="9983b-131">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="9983b-132">**ViModeChangeHandler** usa o `Function:` provedor para fazer referência a **OnViModeChange** como um objeto de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="9983b-132">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="9983b-133">Para obter mais informações, consulte [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="9983b-133">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="9983b-134">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9983b-134">Parameters</span></span>

### <span data-ttu-id="9983b-135">-AddToHistoryHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-135">-AddToHistoryHandler</span></span>

<span data-ttu-id="9983b-136">Especifica um **scriptblock** que controla quais comandos são adicionados ao histórico de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-136">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="9983b-137">O **scriptblock** recebe a linha de comando como entrada.</span><span class="sxs-lookup"><span data-stu-id="9983b-137">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="9983b-138">Se o **scriptblock** retornar `$True` , a linha de comando será adicionada ao histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-138">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="9983b-139">-AnsiEscapeTimeout</span><span class="sxs-lookup"><span data-stu-id="9983b-139">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="9983b-140">Essa opção é específica ao Windows quando a entrada é redirecionada, por exemplo, ao ser executada em `tmux` ou `screen` .</span><span class="sxs-lookup"><span data-stu-id="9983b-140">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="9983b-141">Com a entrada redirecionada no Windows, muitas chaves são enviadas como uma sequência de caracteres começando com o caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="9983b-141">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="9983b-142">É impossível distinguir entre um único caractere de escape seguido de mais caracteres e uma sequência de escape válida.</span><span class="sxs-lookup"><span data-stu-id="9983b-142">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="9983b-143">A suposição é que o terminal possa enviar os caracteres mais rápido do que os tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="9983b-143">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="9983b-144">**PSReadLine** aguarda esse tempo limite antes de concluir que recebeu uma sequência de escape completa.</span><span class="sxs-lookup"><span data-stu-id="9983b-144">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="9983b-145">Se você vir caracteres aleatórios ou inesperados ao digitar, poderá ajustar esse tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9983b-145">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="9983b-146">-Bellstyle</span><span class="sxs-lookup"><span data-stu-id="9983b-146">-BellStyle</span></span>

<span data-ttu-id="9983b-147">Especifica como o **PSReadLine** responde a várias condições ambíguas e de erro.</span><span class="sxs-lookup"><span data-stu-id="9983b-147">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="9983b-148">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9983b-148">The valid values are as follows:</span></span>

- <span data-ttu-id="9983b-149">**Audível** : um breve bipe.</span><span class="sxs-lookup"><span data-stu-id="9983b-149">**Audible** : A short beep.</span></span>
- <span data-ttu-id="9983b-150">**Visual** : o texto pisca brevemente.</span><span class="sxs-lookup"><span data-stu-id="9983b-150">**Visual** : Text flashes briefly.</span></span>
- <span data-ttu-id="9983b-151">**Nenhum** : nenhum comentário.</span><span class="sxs-lookup"><span data-stu-id="9983b-151">**None** : No feedback.</span></span>

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

### <span data-ttu-id="9983b-152">-Cores</span><span class="sxs-lookup"><span data-stu-id="9983b-152">-Colors</span></span>

<span data-ttu-id="9983b-153">O parâmetro **Colors** especifica várias cores usadas pelo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-153">The **Colors** parameter specifies various colors used by **PSReadLine** .</span></span>

<span data-ttu-id="9983b-154">O argumento é uma tabela de hash em que as chaves especificam qual elemento e os valores especificam a cor.</span><span class="sxs-lookup"><span data-stu-id="9983b-154">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="9983b-155">Para obter mais informações, consulte [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="9983b-155">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="9983b-156">As cores podem ser um valor de **ConsoleColor** , por exemplo `[ConsoleColor]::Red` , ou uma sequência de escape ANSI válida.</span><span class="sxs-lookup"><span data-stu-id="9983b-156">Colors can be either a value from **ConsoleColor** , for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="9983b-157">As sequências de escape válidas dependem do seu terminal.</span><span class="sxs-lookup"><span data-stu-id="9983b-157">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="9983b-158">No PowerShell 5,0, uma sequência de escape de exemplo para texto vermelho é `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="9983b-158">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="9983b-159">No PowerShell 6 e acima, a mesma sequência de escape é `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="9983b-159">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="9983b-160">Você pode especificar outras sequências de escape, incluindo os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="9983b-160">You can specify other escape sequences including the following types:</span></span>

- <span data-ttu-id="9983b-161">cor de 256</span><span class="sxs-lookup"><span data-stu-id="9983b-161">256 color</span></span>
- <span data-ttu-id="9983b-162">cor de 24 bits</span><span class="sxs-lookup"><span data-stu-id="9983b-162">24-bit color</span></span>
- <span data-ttu-id="9983b-163">Primeiro plano, plano de fundo ou ambos</span><span class="sxs-lookup"><span data-stu-id="9983b-163">Foreground, background, or both</span></span>
- <span data-ttu-id="9983b-164">Inverso, negrito</span><span class="sxs-lookup"><span data-stu-id="9983b-164">Inverse, bold</span></span>

<span data-ttu-id="9983b-165">Para obter mais informações sobre códigos de cor ANSI, consulte [código de escape ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="9983b-165">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="9983b-166">As chaves válidas incluem:</span><span class="sxs-lookup"><span data-stu-id="9983b-166">The valid keys include:</span></span>

- <span data-ttu-id="9983b-167">**ContinuationPrompt** : a cor do prompt de continuação.</span><span class="sxs-lookup"><span data-stu-id="9983b-167">**ContinuationPrompt** : The color of the continuation prompt.</span></span>
- <span data-ttu-id="9983b-168">**Ênfase** : a cor de ênfase.</span><span class="sxs-lookup"><span data-stu-id="9983b-168">**Emphasis** : The emphasis color.</span></span> <span data-ttu-id="9983b-169">Por exemplo, o texto correspondente ao pesquisar o histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-169">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="9983b-170">**Erro** : a cor do erro.</span><span class="sxs-lookup"><span data-stu-id="9983b-170">**Error** : The error color.</span></span> <span data-ttu-id="9983b-171">Por exemplo, no prompt.</span><span class="sxs-lookup"><span data-stu-id="9983b-171">For example, in the prompt.</span></span>
- <span data-ttu-id="9983b-172">**Seleção** : a cor para realçar a seleção de menu ou o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="9983b-172">**Selection** : The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="9983b-173">**Padrão** : a cor padrão do token.</span><span class="sxs-lookup"><span data-stu-id="9983b-173">**Default** : The default token color.</span></span>
- <span data-ttu-id="9983b-174">**Comentário** : a cor do token de comentário.</span><span class="sxs-lookup"><span data-stu-id="9983b-174">**Comment** : The comment token color.</span></span>
- <span data-ttu-id="9983b-175">**Palavra-chave** : a cor do token de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="9983b-175">**Keyword** : The keyword token color.</span></span>
- <span data-ttu-id="9983b-176">**String** : a cor do token da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9983b-176">**String** : The string token color.</span></span>
- <span data-ttu-id="9983b-177">**Operador** : a cor do token do operador.</span><span class="sxs-lookup"><span data-stu-id="9983b-177">**Operator** : The operator token color.</span></span>
- <span data-ttu-id="9983b-178">**Variável** : a cor do token variável.</span><span class="sxs-lookup"><span data-stu-id="9983b-178">**Variable** : The variable token color.</span></span>
- <span data-ttu-id="9983b-179">**Comando** : a cor do token de comando.</span><span class="sxs-lookup"><span data-stu-id="9983b-179">**Command** : The command token color.</span></span>
- <span data-ttu-id="9983b-180">**Parâmetro** : a cor do token do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9983b-180">**Parameter** : The parameter token color.</span></span>
- <span data-ttu-id="9983b-181">**Tipo** : a cor do token de tipo.</span><span class="sxs-lookup"><span data-stu-id="9983b-181">**Type** : The type token color.</span></span>
- <span data-ttu-id="9983b-182">**Número** : a cor do token de número.</span><span class="sxs-lookup"><span data-stu-id="9983b-182">**Number** : The number token color.</span></span>
- <span data-ttu-id="9983b-183">**Membro** : a cor do token do nome do membro.</span><span class="sxs-lookup"><span data-stu-id="9983b-183">**Member** : The member name token color.</span></span>

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

### <span data-ttu-id="9983b-184">-CommandValidationHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-184">-CommandValidationHandler</span></span>

<span data-ttu-id="9983b-185">Especifica um **scriptblock** que é chamado de **ValidateAndAcceptLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-185">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine** .</span></span> <span data-ttu-id="9983b-186">Se uma exceção for lançada, a validação falhará e o erro será relatado.</span><span class="sxs-lookup"><span data-stu-id="9983b-186">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="9983b-187">Antes de lançar uma exceção, o manipulador de validação pode colocar o cursor no ponto do erro para facilitar a correção.</span><span class="sxs-lookup"><span data-stu-id="9983b-187">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="9983b-188">Um manipulador de validação também pode alterar a linha de comando, como para corrigir erros tipográficos comuns.</span><span class="sxs-lookup"><span data-stu-id="9983b-188">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="9983b-189">**ValidateAndAcceptLine** é usado para evitar a confusão de seu histórico com comandos que não funcionam.</span><span class="sxs-lookup"><span data-stu-id="9983b-189">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="9983b-190">-CompletionQueryItems</span><span class="sxs-lookup"><span data-stu-id="9983b-190">-CompletionQueryItems</span></span>

<span data-ttu-id="9983b-191">Especifica o número máximo de itens de conclusão que são mostrados sem solicitação.</span><span class="sxs-lookup"><span data-stu-id="9983b-191">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="9983b-192">Se o número de itens a serem mostrados for maior que esse valor, **PSReadLine** solicitará **Sim/não** antes de exibir os itens de conclusão.</span><span class="sxs-lookup"><span data-stu-id="9983b-192">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="9983b-193">-ContinuationPrompt</span><span class="sxs-lookup"><span data-stu-id="9983b-193">-ContinuationPrompt</span></span>

<span data-ttu-id="9983b-194">Especifica a cadeia de caracteres exibida no início das linhas subsequentes quando a entrada de várias linhas é inserida.</span><span class="sxs-lookup"><span data-stu-id="9983b-194">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="9983b-195">O padrão é duplo de sinais de maior que ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="9983b-195">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="9983b-196">Uma cadeia de caracteres vazia é válida.</span><span class="sxs-lookup"><span data-stu-id="9983b-196">An empty string is valid.</span></span>

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

### <span data-ttu-id="9983b-197">-DingDuration</span><span class="sxs-lookup"><span data-stu-id="9983b-197">-DingDuration</span></span>

<span data-ttu-id="9983b-198">Especifica a duração do aviso sonoro quando **bellstyle** é definido como **audível** .</span><span class="sxs-lookup"><span data-stu-id="9983b-198">Specifies the duration of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="9983b-199">-DingTone</span><span class="sxs-lookup"><span data-stu-id="9983b-199">-DingTone</span></span>

<span data-ttu-id="9983b-200">Especifica o Tom em Hertz (Hz) do bipe quando **bellstyle** é definido como **audível** .</span><span class="sxs-lookup"><span data-stu-id="9983b-200">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="9983b-201">-EditMode</span><span class="sxs-lookup"><span data-stu-id="9983b-201">-EditMode</span></span>

<span data-ttu-id="9983b-202">Especifica o modo de edição de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9983b-202">Specifies the command line editing mode.</span></span> <span data-ttu-id="9983b-203">O uso desse parâmetro redefine as associações de chave definidas por `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="9983b-203">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="9983b-204">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9983b-204">The valid values are as follows:</span></span>

- <span data-ttu-id="9983b-205">**Windows** : associações de chave emulam o PowerShell, o cmd e o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9983b-205">**Windows** : Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="9983b-206">**Emacs** : associações de chave emulam bash ou Emacs.</span><span class="sxs-lookup"><span data-stu-id="9983b-206">**Emacs** : Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="9983b-207">**Vi** : associações de chave emulam vi.</span><span class="sxs-lookup"><span data-stu-id="9983b-207">**Vi** : Key bindings emulate Vi.</span></span>

<span data-ttu-id="9983b-208">Use `Get-PSReadLineKeyHandler` para ver as associações de chave para o **EditMode** configurado no momento.</span><span class="sxs-lookup"><span data-stu-id="9983b-208">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode** .</span></span>

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

### <span data-ttu-id="9983b-209">-ExtraPromptLineCount</span><span class="sxs-lookup"><span data-stu-id="9983b-209">-ExtraPromptLineCount</span></span>

<span data-ttu-id="9983b-210">Especifica o número de linhas extras.</span><span class="sxs-lookup"><span data-stu-id="9983b-210">Specifies the number of extra lines.</span></span>

<span data-ttu-id="9983b-211">Se o prompt se estender por mais de uma linha, especifique um valor para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9983b-211">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="9983b-212">Use esta opção quando desejar que linhas extras estejam disponíveis quando o **PSReadLine** exibir o prompt depois de mostrar alguma saída.</span><span class="sxs-lookup"><span data-stu-id="9983b-212">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="9983b-213">Por exemplo, **PSReadLine** retorna uma lista de conclusões.</span><span class="sxs-lookup"><span data-stu-id="9983b-213">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="9983b-214">Essa opção é necessária para menos do que nas versões anteriores do **PSReadLine** , mas é útil quando a `InvokePrompt` função é usada.</span><span class="sxs-lookup"><span data-stu-id="9983b-214">This option is needed less than in previous versions of **PSReadLine** , but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="9983b-215">-HistoryNoDuplicates</span><span class="sxs-lookup"><span data-stu-id="9983b-215">-HistoryNoDuplicates</span></span>

<span data-ttu-id="9983b-216">Esta opção controla o comportamento de recuperação.</span><span class="sxs-lookup"><span data-stu-id="9983b-216">This option controls the recall behavior.</span></span> <span data-ttu-id="9983b-217">Comandos duplicados ainda são adicionados ao arquivo de histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-217">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="9983b-218">Quando essa opção é definida, somente a invocação mais recente é exibida durante a rechamada de comandos.</span><span class="sxs-lookup"><span data-stu-id="9983b-218">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="9983b-219">Comandos repetidos são adicionados ao histórico para preservar a ordenação durante a RECALL.</span><span class="sxs-lookup"><span data-stu-id="9983b-219">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="9983b-220">No entanto, normalmente você não deseja ver o comando várias vezes ao chamar ou pesquisar o histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-220">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="9983b-221">Por padrão, a propriedade **HistoryNoDuplicates** do objeto **PSConsoleReadLineOptions** global é definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-221">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="9983b-222">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-222">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="9983b-223">Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-223">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="9983b-224">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="9983b-224">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="9983b-225">-HistorySavePath</span><span class="sxs-lookup"><span data-stu-id="9983b-225">-HistorySavePath</span></span>

<span data-ttu-id="9983b-226">Especifica o caminho para o arquivo em que o histórico é salvo.</span><span class="sxs-lookup"><span data-stu-id="9983b-226">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="9983b-227">Computadores que executam plataformas Windows ou não Windows armazenam o arquivo em locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="9983b-227">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="9983b-228">O nome do arquivo é armazenado em uma variável `$($host.Name)_history.txt` , por exemplo `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="9983b-228">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="9983b-229">Se você não usar esse parâmetro, o caminho padrão será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9983b-229">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="9983b-230">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9983b-230">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="9983b-231">**Não Windows**</span><span class="sxs-lookup"><span data-stu-id="9983b-231">**non-Windows**</span></span>

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

### <span data-ttu-id="9983b-232">-HistorySaveStyle</span><span class="sxs-lookup"><span data-stu-id="9983b-232">-HistorySaveStyle</span></span>

<span data-ttu-id="9983b-233">Especifica como o **PSReadLine** salva o histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-233">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="9983b-234">Estes são os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="9983b-234">Valid values are as follows:</span></span>

- <span data-ttu-id="9983b-235">**SaveIncrementally** : salvar histórico depois que cada comando for executado e compartilhar entre várias instâncias do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9983b-235">**SaveIncrementally** : Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="9983b-236">**SaveAtExit** : acrescentar arquivo de histórico quando o PowerShell for encerrado.</span><span class="sxs-lookup"><span data-stu-id="9983b-236">**SaveAtExit** : Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="9983b-237">**SaveNothing** : não use um arquivo de histórico.</span><span class="sxs-lookup"><span data-stu-id="9983b-237">**SaveNothing** : Don't use a history file.</span></span>

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

### <span data-ttu-id="9983b-238">-HistorySearchCaseSensitive</span><span class="sxs-lookup"><span data-stu-id="9983b-238">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="9983b-239">Especifica que a pesquisa de histórico diferencia maiúsculas de minúsculas em funções como **ReverseSearchHistory** ou **HistorySearchBackward** .</span><span class="sxs-lookup"><span data-stu-id="9983b-239">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward** .</span></span>

<span data-ttu-id="9983b-240">Por padrão, a propriedade **HistorySearchCaseSensitive** do objeto **PSConsoleReadLineOptions** global é definida como `False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-240">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="9983b-241">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-241">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="9983b-242">Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-242">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="9983b-243">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="9983b-243">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="9983b-244">-HistorySearchCursorMovesToEnd</span><span class="sxs-lookup"><span data-stu-id="9983b-244">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="9983b-245">Indica que o cursor se move para o final dos comandos que você carrega do histórico usando uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9983b-245">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="9983b-246">Quando esse parâmetro é definido como `$False` , o cursor permanece na posição em que você pressionou as setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="9983b-246">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="9983b-247">Por padrão, a propriedade **HistorySearchCursorMovesToEnd** do objeto **PSConsoleReadLineOptions** global é definida como `False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-247">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="9983b-248">Usando este **SwitchParameter** , defina o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-248">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="9983b-249">Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-249">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="9983b-250">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="9983b-250">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="9983b-251">-MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="9983b-251">-MaximumHistoryCount</span></span>

<span data-ttu-id="9983b-252">Especifica o número máximo de comandos a serem salvos no histórico de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-252">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="9983b-253">O histórico de **PSReadLine** é separado do histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9983b-253">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="9983b-254">-MaximumKillRingCount</span><span class="sxs-lookup"><span data-stu-id="9983b-254">-MaximumKillRingCount</span></span>

<span data-ttu-id="9983b-255">Especifica o número máximo de itens armazenados no Kill Ring.</span><span class="sxs-lookup"><span data-stu-id="9983b-255">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="9983b-256">-PromptText</span><span class="sxs-lookup"><span data-stu-id="9983b-256">-PromptText</span></span>

<span data-ttu-id="9983b-257">Quando há um erro de análise, o **PSReadLine** altera uma parte do prompt vermelho.</span><span class="sxs-lookup"><span data-stu-id="9983b-257">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="9983b-258">O **PSReadLine** analisa sua função de prompt para determinar como alterar apenas a cor de parte do prompt.</span><span class="sxs-lookup"><span data-stu-id="9983b-258">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="9983b-259">Essa análise não é de 100% confiável.</span><span class="sxs-lookup"><span data-stu-id="9983b-259">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="9983b-260">Use esta opção se **PSReadLine** estiver alterando seu prompt de maneiras inesperadas.</span><span class="sxs-lookup"><span data-stu-id="9983b-260">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="9983b-261">Inclua qualquer espaço em branco à direita.</span><span class="sxs-lookup"><span data-stu-id="9983b-261">Include any trailing whitespace.</span></span>

<span data-ttu-id="9983b-262">Por exemplo, se a função de prompt se parecer com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9983b-262">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="9983b-263">Em seguida, defina:</span><span class="sxs-lookup"><span data-stu-id="9983b-263">Then set:</span></span>

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

### <span data-ttu-id="9983b-264">-Dicas de ferramentas</span><span class="sxs-lookup"><span data-stu-id="9983b-264">-ShowToolTips</span></span>

<span data-ttu-id="9983b-265">Ao exibir as conclusões possíveis, as dicas de ferramentas são mostradas na lista de conclusões.</span><span class="sxs-lookup"><span data-stu-id="9983b-265">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="9983b-266">Essa opção é habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9983b-266">This option is enabled by default.</span></span> <span data-ttu-id="9983b-267">Essa opção não foi habilitada por padrão nas versões anteriores do **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="9983b-267">This option wasn't enabled by default in prior versions of **PSReadLine** .</span></span> <span data-ttu-id="9983b-268">Para desabilitar, defina essa opção como `$False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-268">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="9983b-269">Por padrão, a propriedade **Extooltips** do objeto **PSConsoleReadLineOptions** global é definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-269">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="9983b-270">O uso desse **SwitchParameter** define o valor da propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="9983b-270">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="9983b-271">Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="9983b-271">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="9983b-272">Usando o comando a seguir, você pode definir o valor da propriedade diretamente:</span><span class="sxs-lookup"><span data-stu-id="9983b-272">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="9983b-273">-ViModeChangeHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-273">-ViModeChangeHandler</span></span>

<span data-ttu-id="9983b-274">Quando o **ViModeIndicator** é definido como `Script` , o bloco de script fornecido será invocado sempre que o modo for alterado.</span><span class="sxs-lookup"><span data-stu-id="9983b-274">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="9983b-275">O bloco de script recebe um argumento do tipo `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="9983b-275">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="9983b-276">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="9983b-276">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="9983b-277">-ViModeIndicator</span><span class="sxs-lookup"><span data-stu-id="9983b-277">-ViModeIndicator</span></span>

<span data-ttu-id="9983b-278">Essa opção define a indicação visual para o modo **vi** atual.</span><span class="sxs-lookup"><span data-stu-id="9983b-278">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="9983b-279">O modo de inserção ou o modo de comando.</span><span class="sxs-lookup"><span data-stu-id="9983b-279">Either insert mode or command mode.</span></span>

<span data-ttu-id="9983b-280">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9983b-280">The valid values are as follows:</span></span>

- <span data-ttu-id="9983b-281">**Nenhum** : não há nenhuma indicação.</span><span class="sxs-lookup"><span data-stu-id="9983b-281">**None** : There's no indication.</span></span>
- <span data-ttu-id="9983b-282">**Prompt** : o prompt muda de cor.</span><span class="sxs-lookup"><span data-stu-id="9983b-282">**Prompt** : The prompt changes color.</span></span>
- <span data-ttu-id="9983b-283">**Cursor** : o tamanho das alterações do cursor.</span><span class="sxs-lookup"><span data-stu-id="9983b-283">**Cursor** : The cursor changes size.</span></span>
- <span data-ttu-id="9983b-284">**Script** : o texto especificado pelo usuário é impresso.</span><span class="sxs-lookup"><span data-stu-id="9983b-284">**Script** : User-specified text is printed.</span></span>

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

### <span data-ttu-id="9983b-285">-WordDelimiters</span><span class="sxs-lookup"><span data-stu-id="9983b-285">-WordDelimiters</span></span>

<span data-ttu-id="9983b-286">Especifica os caracteres que delimitam palavras para funções como **ForwardWord** ou **KillWord** .</span><span class="sxs-lookup"><span data-stu-id="9983b-286">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord** .</span></span>

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

### <span data-ttu-id="9983b-287">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9983b-287">CommonParameters</span></span>

<span data-ttu-id="9983b-288">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9983b-288">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9983b-289">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9983b-289">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9983b-290">Entradas</span><span class="sxs-lookup"><span data-stu-id="9983b-290">Inputs</span></span>

### <span data-ttu-id="9983b-291">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9983b-291">None</span></span>

<span data-ttu-id="9983b-292">Não é possível canalizar objetos para `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="9983b-292">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="9983b-293">Saídas</span><span class="sxs-lookup"><span data-stu-id="9983b-293">Outputs</span></span>

### <span data-ttu-id="9983b-294">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9983b-294">None</span></span>

<span data-ttu-id="9983b-295">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="9983b-295">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9983b-296">Observações</span><span class="sxs-lookup"><span data-stu-id="9983b-296">Notes</span></span>

## <span data-ttu-id="9983b-297">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="9983b-297">Related links</span></span>

[<span data-ttu-id="9983b-298">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="9983b-298">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="9983b-299">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-299">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="9983b-300">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="9983b-300">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="9983b-301">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-301">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="9983b-302">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="9983b-302">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
