---
description: Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.
Locale: en-US
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: b21ec1eb5ed0da52cf5eff01eaf3c220d117cf55
ms.sourcegitcommit: 364c3fe46b2069b810107d840be59fe519ea7b4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "100100709"
---
# <a name="about-special-characters"></a><span data-ttu-id="4b7cb-103">Sobre caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="4b7cb-103">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="4b7cb-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="4b7cb-104">Short description</span></span>

<span data-ttu-id="4b7cb-105">Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-105">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="4b7cb-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="4b7cb-106">Long description</span></span>

<span data-ttu-id="4b7cb-107">O PowerShell dá suporte a um conjunto de sequências de caracteres especiais que são usadas para representar caracteres que não fazem parte do conjunto de caracteres padrão.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-107">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="4b7cb-108">As sequências normalmente são conhecidas como _sequências de escape_.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-108">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="4b7cb-109">As seqüências de escape começam com o caractere de acento grave, conhecido como acentuação (ASCII 96), e diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-109">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="4b7cb-110">O caractere de acento grave também pode ser chamado de _caractere de escape_.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-110">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="4b7cb-111">As seqüências de escape são interpretadas somente quando contidas em cadeias de caracteres com aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="4b7cb-111">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="4b7cb-112">O PowerShell reconhece estas sequências de escape:</span><span class="sxs-lookup"><span data-stu-id="4b7cb-112">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="4b7cb-113">Sequência</span><span class="sxs-lookup"><span data-stu-id="4b7cb-113">Sequence</span></span>   |       <span data-ttu-id="4b7cb-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b7cb-114">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="4b7cb-115">Nulo</span><span class="sxs-lookup"><span data-stu-id="4b7cb-115">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="4b7cb-116">Alerta</span><span class="sxs-lookup"><span data-stu-id="4b7cb-116">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="4b7cb-117">Backspace</span><span class="sxs-lookup"><span data-stu-id="4b7cb-117">Backspace</span></span>               |
| `` `e ``    | <span data-ttu-id="4b7cb-118">Escape</span><span class="sxs-lookup"><span data-stu-id="4b7cb-118">Escape</span></span>                  |
| `` `f ``    | <span data-ttu-id="4b7cb-119">Avanço de formulário</span><span class="sxs-lookup"><span data-stu-id="4b7cb-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="4b7cb-120">Nova linha</span><span class="sxs-lookup"><span data-stu-id="4b7cb-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="4b7cb-121">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="4b7cb-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="4b7cb-122">Guia horizontal</span><span class="sxs-lookup"><span data-stu-id="4b7cb-122">Horizontal tab</span></span>          |
| `` `u{x} `` | <span data-ttu-id="4b7cb-123">Sequência de escape Unicode</span><span class="sxs-lookup"><span data-stu-id="4b7cb-123">Unicode escape sequence</span></span> |
| `` `v ``    | <span data-ttu-id="4b7cb-124">Guia vertical</span><span class="sxs-lookup"><span data-stu-id="4b7cb-124">Vertical tab</span></span>            |

<span data-ttu-id="4b7cb-125">O PowerShell também tem um token especial para marcar onde você deseja que a análise pare.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-125">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="4b7cb-126">Todos os caracteres que seguem esse token são usados como valores literais que não são interpretados.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-126">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="4b7cb-127">Token de análise especial:</span><span class="sxs-lookup"><span data-stu-id="4b7cb-127">Special parsing token:</span></span>

| <span data-ttu-id="4b7cb-128">Sequência</span><span class="sxs-lookup"><span data-stu-id="4b7cb-128">Sequence</span></span> |            <span data-ttu-id="4b7cb-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b7cb-129">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="4b7cb-130">Pare a análise de qualquer coisa que segue</span><span class="sxs-lookup"><span data-stu-id="4b7cb-130">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="4b7cb-131">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-131">Null (\`0)</span></span>

<span data-ttu-id="4b7cb-132">O caractere nulo ( `` `0 `` ) aparece como um espaço vazio na saída do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-132">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="4b7cb-133">Essa funcionalidade permite que você use o PowerShell para ler e processar arquivos de texto que usam caracteres nulos, como a terminação de cadeia de caracteres ou indicadores de encerramento de registro.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-133">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="4b7cb-134">O caractere especial nulo não é equivalente à `$null` variável, que armazena um valor **nulo** .</span><span class="sxs-lookup"><span data-stu-id="4b7cb-134">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="4b7cb-135">Alerta (' a)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-135">Alert (\`a)</span></span>

<span data-ttu-id="4b7cb-136">O caractere alerta ( `` `a `` ) envia um sinal de bipe para o palestrante do computador.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-136">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="4b7cb-137">Você pode usar esse caractere para avisar um usuário sobre uma ação iminente.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-137">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="4b7cb-138">O exemplo a seguir envia dois sinais de bipe para o palestrante do computador local.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-138">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="4b7cb-139">Backspace (' b)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-139">Backspace (\`b)</span></span>

<span data-ttu-id="4b7cb-140">O caractere de Backspace ( `` `b `` ) move o cursor para trás, mas não exclui nenhum caractere.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-140">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="4b7cb-141">O exemplo grava a palavra **backup** e, em seguida, move o cursor duas vezes.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-141">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="4b7cb-142">Em seguida, na nova posição, o grava um espaço seguido pela palavra de **saída**.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-142">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a><span data-ttu-id="4b7cb-143">Escape (' e)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-143">Escape (\`e)</span></span>

<span data-ttu-id="4b7cb-144">O caractere de escape ( `` `e `` ) é usado com mais frequência para especificar uma sequência de terminais virtual (sequência de escape ANSI) que modifica a cor do texto e outros atributos de texto, como negrito e sublinhado.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-144">The escape (`` `e ``) character is most commonly used to specify a virtual terminal sequence (ANSI escape sequence) that modifies the color of text and other text attributes such as bolding and underlining.</span></span> <span data-ttu-id="4b7cb-145">Essas sequências também podem ser usadas para posicionamento e rolagem do cursor.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-145">These sequences can also be used for cursor positioning and scrolling.</span></span> <span data-ttu-id="4b7cb-146">O host do PowerShell deve dar suporte a sequências de terminais virtuais.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-146">The PowerShell host must support virtual terminal sequences.</span></span> <span data-ttu-id="4b7cb-147">Você pode verificar o valor booliano de `$Host.UI.SupportsVirtualTerminal` para determinar se essas sequências ANSI têm suporte.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-147">You can check the boolean value of `$Host.UI.SupportsVirtualTerminal` to determine if these ANSI sequences are supported.</span></span>

<span data-ttu-id="4b7cb-148">Para obter mais informações sobre sequências de escape ANSI, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="4b7cb-148">For more information about ANSI escape sequences, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

<span data-ttu-id="4b7cb-149">O exemplo a seguir gera um texto com uma cor de primeiro plano verde.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-149">The following example outputs text with a green foreground color.</span></span>

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a><span data-ttu-id="4b7cb-150">Feed de formulário (' f)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-150">Form feed (\`f)</span></span>

<span data-ttu-id="4b7cb-151">O caractere de feed de formulário ( `` `f `` ) é uma instrução de impressão que ejeta a página atual e continua imprimindo na próxima página.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-151">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="4b7cb-152">O caractere de feed de formulário afeta apenas os documentos impressos.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-152">The form feed character only affects printed documents.</span></span> <span data-ttu-id="4b7cb-153">Ele não afeta a saída da tela.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-153">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="4b7cb-154">Nova linha (' n)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-154">New line (\`n)</span></span>

<span data-ttu-id="4b7cb-155">O caractere de nova linha ( `` `n `` ) insere uma quebra de linha imediatamente após o caractere.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-155">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="4b7cb-156">Este exemplo mostra como usar o caractere de nova linha para criar quebras de linha em um `Write-Host` comando.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-156">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="4b7cb-157">Retorno de carro (' r)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-157">Carriage return (\`r)</span></span>

<span data-ttu-id="4b7cb-158">O caractere de retorno de carro ( `` `r `` ) move o cursor de saída para o início da linha atual e continua gravando.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-158">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="4b7cb-159">Todos os caracteres na linha atual são substituídos.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-159">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="4b7cb-160">Neste exemplo, o texto antes do retorno de carro é substituído.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-160">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="4b7cb-161">Observe que o texto antes do `` `r `` caractere não é excluído, ele é substituído.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-161">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="4b7cb-162">Guia horizontal (t)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-162">Horizontal tab (\`t)</span></span>

<span data-ttu-id="4b7cb-163">O caractere de tabulação horizontal ( `` `t `` ) avança para a próxima parada de tabulação e continua gravando nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-163">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="4b7cb-164">Por padrão, o console do PowerShell tem uma parada de tabulação em cada oitavo espaço.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-164">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="4b7cb-165">Este exemplo insere duas guias entre cada coluna.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-165">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a><span data-ttu-id="4b7cb-166">Caractere Unicode (' u {x})</span><span class="sxs-lookup"><span data-stu-id="4b7cb-166">Unicode character (\`u{x})</span></span>

<span data-ttu-id="4b7cb-167">A sequência de escape Unicode ( `` `u{x} `` ) permite que você especifique qualquer caractere Unicode pela representação hexadecimal de seu ponto de código.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-167">The Unicode escape sequence (`` `u{x} ``) allows you to specify any Unicode character by the hexadecimal representation of its code point.</span></span> <span data-ttu-id="4b7cb-168">Isso inclui caracteres Unicode acima do plano multilíngue básico (> `0xFFFF` ), que inclui os caracteres de Emoji como o caractere de **polegar para cima** ( `` `u{1F44D} `` ).</span><span class="sxs-lookup"><span data-stu-id="4b7cb-168">This includes Unicode characters above the Basic Multilingual Plane (> `0xFFFF`) which includes emoji characters such as the **thumbs up** (`` `u{1F44D} ``) character.</span></span> <span data-ttu-id="4b7cb-169">A sequência de escape Unicode requer pelo menos um dígito hexadecimal e dá suporte a até seis dígitos hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-169">The Unicode escape sequence requires at least one hexadecimal digit and supports up to six hexadecimal digits.</span></span> <span data-ttu-id="4b7cb-170">O valor hexadecimal máximo para a sequência é `10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="4b7cb-170">The maximum hexadecimal value for the sequence is `10FFFF`.</span></span>

<span data-ttu-id="4b7cb-171">Este exemplo gera o símbolo de **seta para cima** (&#x2195;).</span><span class="sxs-lookup"><span data-stu-id="4b7cb-171">This example outputs the **up down arrow** (&#x2195;) symbol.</span></span>

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a><span data-ttu-id="4b7cb-172">Guia vertical (' v)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-172">Vertical tab (\`v)</span></span>

<span data-ttu-id="4b7cb-173">O caractere de tabulação vertical ( `` `v `` ) avança para a próxima parada de tabulação vertical e grava a saída restante nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-173">The vertical tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="4b7cb-174">O processamento da guia vertical é dependente do dispositivo e do terminal.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-174">The rendering of the the vertical tab is device and terminal dependent.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="4b7cb-175">Os exemplos a seguir mostram a saída renderizada da guia vertical em alguns ambientes comuns.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-175">The following examples show the rendered output of the vertical tab in some common environments.</span></span>

<span data-ttu-id="4b7cb-176">O aplicativo host do console do Windows interpreta ( `` `v `` ) como um caractere especial sem nenhum espaçamento adicional adicionado.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-176">The Windows Console host application interprets (`` `v ``) as a special character with no extra spacing added.</span></span>

```Output
There is a vertical tab♂between the words.
```

<span data-ttu-id="4b7cb-177">O [terminal do Windows](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) renderiza o caractere de tabulação vertical como um retorno de carro e alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-177">The [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) renders the vertical tab character as a carriage return and line feed.</span></span> <span data-ttu-id="4b7cb-178">O restante da saída é impresso no início da próxima linha.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-178">The rest of the output is printed at the beginning of the next line.</span></span>

```Output
There is a vertical tab
between the words.
```

<span data-ttu-id="4b7cb-179">Em impressoras ou em consoles baseados em UNIX, o caractere de tabulação vertical avança para a próxima linha e grava a saída restante nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-179">On printers or in a unix-based consoles, the vertical tab character advances to the next line and writes the remaining output at that point.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="4b7cb-180">Token de análise de parada (--%)</span><span class="sxs-lookup"><span data-stu-id="4b7cb-180">Stop-parsing token (--%)</span></span>

<span data-ttu-id="4b7cb-181">O token Stop-analisation ( `--%` ) impede que o PowerShell interprete cadeias de caracteres como comandos e expressões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-181">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="4b7cb-182">Isso permite que essas cadeias de caracteres sejam passadas para outros programas para interpretação.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-182">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="4b7cb-183">Coloque o token de análise de parada após o nome do programa e os argumentos do programa que podem causar erros.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-183">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="4b7cb-184">Neste exemplo, o `Icacls` comando usa o token de interrupção de análise.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-184">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="4b7cb-185">O PowerShell envia a cadeia de caracteres a seguir para `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="4b7cb-185">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="4b7cb-186">Veja a seguir outro exemplo.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-186">Here is another example.</span></span> <span data-ttu-id="4b7cb-187">A função **adargs** gera os valores passados para ele.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-187">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="4b7cb-188">Neste exemplo, passamos a variável chamada `$HOME` para a função duas vezes.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-188">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Você pode ver na saída que, para o primeiro parâmetro, a variável `$HOME` é interpretada pelo PowerShell para que o valor da variável seja passado para a função. <span data-ttu-id="4b7cb-190">O segundo uso do `$HOME` vem após o token de análise de parada, portanto, a cadeia de caracteres "$Home" é passada para a função sem interpretação.</span><span class="sxs-lookup"><span data-stu-id="4b7cb-190">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="4b7cb-191">Para obter mais informações sobre o token da análise de parada, consulte [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="4b7cb-191">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b7cb-192">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4b7cb-192">See also</span></span>

[<span data-ttu-id="4b7cb-193">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="4b7cb-193">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

