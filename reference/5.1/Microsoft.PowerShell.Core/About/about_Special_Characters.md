---
description: Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 875a1c3c63e759151c3c64b5396312b030955cb7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195964"
---
# <a name="about-special-characters"></a><span data-ttu-id="56e78-104">Sobre caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="56e78-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="56e78-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="56e78-105">Short description</span></span>

<span data-ttu-id="56e78-106">Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.</span><span class="sxs-lookup"><span data-stu-id="56e78-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="56e78-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="56e78-107">Long description</span></span>

<span data-ttu-id="56e78-108">O PowerShell dá suporte a um conjunto de sequências de caracteres especiais que são usadas para representar caracteres que não fazem parte do conjunto de caracteres padrão.</span><span class="sxs-lookup"><span data-stu-id="56e78-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="56e78-109">As sequências normalmente são conhecidas como _sequências de escape_ .</span><span class="sxs-lookup"><span data-stu-id="56e78-109">The sequences are commonly known as _escape sequences_ .</span></span>

<span data-ttu-id="56e78-110">As seqüências de escape começam com o caractere de acento grave, conhecido como acentuação (ASCII 96), e diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="56e78-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="56e78-111">O caractere de acento grave também pode ser chamado de _caractere de escape_ .</span><span class="sxs-lookup"><span data-stu-id="56e78-111">The backtick character can also be referred to as the _escape character_ .</span></span>

<span data-ttu-id="56e78-112">As seqüências de escape são interpretadas somente quando contidas em cadeias de caracteres com aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="56e78-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="56e78-113">O PowerShell reconhece estas sequências de escape:</span><span class="sxs-lookup"><span data-stu-id="56e78-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="56e78-114">Sequência</span><span class="sxs-lookup"><span data-stu-id="56e78-114">Sequence</span></span>   |       <span data-ttu-id="56e78-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="56e78-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="56e78-116">Nulo</span><span class="sxs-lookup"><span data-stu-id="56e78-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="56e78-117">Alerta</span><span class="sxs-lookup"><span data-stu-id="56e78-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="56e78-118">Backspace</span><span class="sxs-lookup"><span data-stu-id="56e78-118">Backspace</span></span>               |
| `` `f ``    | <span data-ttu-id="56e78-119">Avanço de formulário</span><span class="sxs-lookup"><span data-stu-id="56e78-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="56e78-120">Nova linha</span><span class="sxs-lookup"><span data-stu-id="56e78-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="56e78-121">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="56e78-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="56e78-122">Guia horizontal</span><span class="sxs-lookup"><span data-stu-id="56e78-122">Horizontal tab</span></span>          |
| `` `v ``    | <span data-ttu-id="56e78-123">Guia vertical</span><span class="sxs-lookup"><span data-stu-id="56e78-123">Vertical tab</span></span>            |

<span data-ttu-id="56e78-124">O PowerShell também tem um token especial para marcar onde você deseja que a análise pare.</span><span class="sxs-lookup"><span data-stu-id="56e78-124">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="56e78-125">Todos os caracteres que seguem esse token são usados como valores literais que não são interpretados.</span><span class="sxs-lookup"><span data-stu-id="56e78-125">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="56e78-126">Token de análise especial:</span><span class="sxs-lookup"><span data-stu-id="56e78-126">Special parsing token:</span></span>

| <span data-ttu-id="56e78-127">Sequência</span><span class="sxs-lookup"><span data-stu-id="56e78-127">Sequence</span></span> |            <span data-ttu-id="56e78-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="56e78-128">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="56e78-129">Pare a análise de qualquer coisa que segue</span><span class="sxs-lookup"><span data-stu-id="56e78-129">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="56e78-130">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="56e78-130">Null (\`0)</span></span>

<span data-ttu-id="56e78-131">O caractere nulo ( `` `0 `` ) aparece como um espaço vazio na saída do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56e78-131">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="56e78-132">Essa funcionalidade permite que você use o PowerShell para ler e processar arquivos de texto que usam caracteres nulos, como a terminação de cadeia de caracteres ou indicadores de encerramento de registro.</span><span class="sxs-lookup"><span data-stu-id="56e78-132">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="56e78-133">O caractere especial nulo não é equivalente à `$null` variável, que armazena um valor **nulo** .</span><span class="sxs-lookup"><span data-stu-id="56e78-133">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="56e78-134">Alerta (' a)</span><span class="sxs-lookup"><span data-stu-id="56e78-134">Alert (\`a)</span></span>

<span data-ttu-id="56e78-135">O caractere alerta ( `` `a `` ) envia um sinal de bipe para o palestrante do computador.</span><span class="sxs-lookup"><span data-stu-id="56e78-135">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="56e78-136">Você pode usar esse caractere para avisar um usuário sobre uma ação iminente.</span><span class="sxs-lookup"><span data-stu-id="56e78-136">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="56e78-137">O exemplo a seguir envia dois sinais de bipe para o palestrante do computador local.</span><span class="sxs-lookup"><span data-stu-id="56e78-137">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="56e78-138">Backspace (' b)</span><span class="sxs-lookup"><span data-stu-id="56e78-138">Backspace (\`b)</span></span>

<span data-ttu-id="56e78-139">O caractere de Backspace ( `` `b `` ) move o cursor para trás, mas não exclui nenhum caractere.</span><span class="sxs-lookup"><span data-stu-id="56e78-139">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="56e78-140">O exemplo grava a palavra **backup** e, em seguida, move o cursor duas vezes.</span><span class="sxs-lookup"><span data-stu-id="56e78-140">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="56e78-141">Em seguida, na nova posição, o grava um espaço seguido pela palavra de **saída** .</span><span class="sxs-lookup"><span data-stu-id="56e78-141">Then, at the new position, writes a space followed by the word **out** .</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="form-feed-f"></a><span data-ttu-id="56e78-142">Feed de formulário (' f)</span><span class="sxs-lookup"><span data-stu-id="56e78-142">Form feed (\`f)</span></span>

<span data-ttu-id="56e78-143">O caractere de feed de formulário ( `` `f `` ) é uma instrução de impressão que ejeta a página atual e continua imprimindo na próxima página.</span><span class="sxs-lookup"><span data-stu-id="56e78-143">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="56e78-144">O caractere de feed de formulário afeta apenas os documentos impressos.</span><span class="sxs-lookup"><span data-stu-id="56e78-144">The form feed character only affects printed documents.</span></span> <span data-ttu-id="56e78-145">Ele não afeta a saída da tela.</span><span class="sxs-lookup"><span data-stu-id="56e78-145">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="56e78-146">Nova linha (' n)</span><span class="sxs-lookup"><span data-stu-id="56e78-146">New line (\`n)</span></span>

<span data-ttu-id="56e78-147">O caractere de nova linha ( `` `n `` ) insere uma quebra de linha imediatamente após o caractere.</span><span class="sxs-lookup"><span data-stu-id="56e78-147">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="56e78-148">Este exemplo mostra como usar o caractere de nova linha para criar quebras de linha em um `Write-Host` comando.</span><span class="sxs-lookup"><span data-stu-id="56e78-148">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="56e78-149">Retorno de carro (' r)</span><span class="sxs-lookup"><span data-stu-id="56e78-149">Carriage return (\`r)</span></span>

<span data-ttu-id="56e78-150">O caractere de retorno de carro ( `` `r `` ) move o cursor de saída para o início da linha atual e continua gravando.</span><span class="sxs-lookup"><span data-stu-id="56e78-150">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="56e78-151">Todos os caracteres na linha atual são substituídos.</span><span class="sxs-lookup"><span data-stu-id="56e78-151">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="56e78-152">Neste exemplo, o texto antes do retorno de carro é substituído.</span><span class="sxs-lookup"><span data-stu-id="56e78-152">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="56e78-153">Observe que o texto antes do `` `r `` caractere não é excluído, ele é substituído.</span><span class="sxs-lookup"><span data-stu-id="56e78-153">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="56e78-154">Guia horizontal (t)</span><span class="sxs-lookup"><span data-stu-id="56e78-154">Horizontal tab (\`t)</span></span>

<span data-ttu-id="56e78-155">O caractere de tabulação horizontal ( `` `t `` ) avança para a próxima parada de tabulação e continua gravando nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="56e78-155">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="56e78-156">Por padrão, o console do PowerShell tem uma parada de tabulação em cada oitavo espaço.</span><span class="sxs-lookup"><span data-stu-id="56e78-156">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="56e78-157">Este exemplo insere duas guias entre cada coluna.</span><span class="sxs-lookup"><span data-stu-id="56e78-157">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="vertical-tab-v"></a><span data-ttu-id="56e78-158">Guia vertical (' v)</span><span class="sxs-lookup"><span data-stu-id="56e78-158">Vertical tab (\`v)</span></span>

<span data-ttu-id="56e78-159">O caractere de tabulação horizontal ( `` `v `` ) avança para a próxima parada de tabulação vertical e grava a saída restante nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="56e78-159">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="56e78-160">Isso não tem efeito no console do Windows padrão.</span><span class="sxs-lookup"><span data-stu-id="56e78-160">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="56e78-161">O exemplo a seguir mostra a saída que você obteria em uma impressora ou em um host de console diferente.</span><span class="sxs-lookup"><span data-stu-id="56e78-161">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="56e78-162">Token de análise de parada (--%)</span><span class="sxs-lookup"><span data-stu-id="56e78-162">Stop-parsing token (--%)</span></span>

<span data-ttu-id="56e78-163">O token Stop-analisation ( `--%` ) impede que o PowerShell interprete cadeias de caracteres como comandos e expressões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56e78-163">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="56e78-164">Isso permite que essas cadeias de caracteres sejam passadas para outros programas para interpretação.</span><span class="sxs-lookup"><span data-stu-id="56e78-164">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="56e78-165">Coloque o token de análise de parada após o nome do programa e os argumentos do programa que podem causar erros.</span><span class="sxs-lookup"><span data-stu-id="56e78-165">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="56e78-166">Neste exemplo, o `Icacls` comando usa o token de interrupção de análise.</span><span class="sxs-lookup"><span data-stu-id="56e78-166">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="56e78-167">O PowerShell envia a cadeia de caracteres a seguir para `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="56e78-167">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="56e78-168">Veja a seguir outro exemplo.</span><span class="sxs-lookup"><span data-stu-id="56e78-168">Here is another example.</span></span> <span data-ttu-id="56e78-169">A função **adargs** gera os valores passados para ele.</span><span class="sxs-lookup"><span data-stu-id="56e78-169">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="56e78-170">Neste exemplo, passamos a variável chamada `$HOME` para a função duas vezes.</span><span class="sxs-lookup"><span data-stu-id="56e78-170">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Você pode ver na saída que, para o primeiro parâmetro, a variável `$HOME` é interpretada pelo PowerShell para que o valor da variável seja passado para a função. <span data-ttu-id="56e78-172">O segundo uso do `$HOME` vem após o token de análise de parada, portanto, a cadeia de caracteres "$Home" é passada para a função sem interpretação.</span><span class="sxs-lookup"><span data-stu-id="56e78-172">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="56e78-173">Para obter mais informações sobre o token da análise de parada, consulte [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="56e78-173">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56e78-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="56e78-174">See also</span></span>

[<span data-ttu-id="56e78-175">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="56e78-175">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
