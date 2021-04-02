---
description: Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: fcf7568cfc2055331cc6025622352eee9711f4ec
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072433"
---
# <a name="about-split"></a><span data-ttu-id="04012-103">Sobre divisão</span><span class="sxs-lookup"><span data-stu-id="04012-103">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="04012-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="04012-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="04012-105">Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.</span><span class="sxs-lookup"><span data-stu-id="04012-105">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="04012-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="04012-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="04012-107">O operador Split divide uma ou mais cadeias de caracteres em subcadeias.</span><span class="sxs-lookup"><span data-stu-id="04012-107">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="04012-108">Você pode alterar os seguintes elementos da operação Split:</span><span class="sxs-lookup"><span data-stu-id="04012-108">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="04012-109">Delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-109">Delimiter.</span></span> <span data-ttu-id="04012-110">O padrão é espaço em branco, mas você pode especificar caracteres, cadeias, padrões ou blocos de script que especificam o delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-110">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="04012-111">O operador split no PowerShell usa uma expressão regular no delimitador, em vez de um caractere simples.</span><span class="sxs-lookup"><span data-stu-id="04012-111">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="04012-112">Número máximo de subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-112">Maximum number of substrings.</span></span> <span data-ttu-id="04012-113">O padrão é retornar todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-113">The default is to return all substrings.</span></span> <span data-ttu-id="04012-114">Se você especificar um número menor que o número de subcadeias de caracteres, as subcadeias restantes serão concatenadas na última subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-114">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="04012-115">Opções que especificam as condições sob as quais o delimitador é correspondido, como SimpleMatch e Multiline.</span><span class="sxs-lookup"><span data-stu-id="04012-115">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="04012-116">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04012-116">SYNTAX</span></span>

<span data-ttu-id="04012-117">O diagrama a seguir mostra a sintaxe do operador-split.</span><span class="sxs-lookup"><span data-stu-id="04012-117">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="04012-118">Os nomes de parâmetro não aparecem no comando.</span><span class="sxs-lookup"><span data-stu-id="04012-118">The parameter names do not appear in the command.</span></span> <span data-ttu-id="04012-119">Inclua apenas os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="04012-119">Include only the parameter values.</span></span> <span data-ttu-id="04012-120">Os valores devem aparecer na ordem especificada no diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="04012-120">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="04012-121">Você pode substituir `-iSplit` ou `-cSplit` `-split` em qualquer instrução Split binária (uma instrução Split que inclui um delimitador ou bloco de script).</span><span class="sxs-lookup"><span data-stu-id="04012-121">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="04012-122">Os `-iSplit` operadores e não diferenciam `-split` maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="04012-122">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="04012-123">O `-cSplit` operador diferencia maiúsculas de minúsculas, o que significa que o caso é considerado quando as regras de delimitador são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="04012-123">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="04012-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04012-124">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="04012-125">\<String\> ou \<String[]\></span><span class="sxs-lookup"><span data-stu-id="04012-125">\<String\> or \<String[]\></span></span>

<span data-ttu-id="04012-126">Especifica uma ou mais cadeias de caracteres a serem divididas.</span><span class="sxs-lookup"><span data-stu-id="04012-126">Specifies one or more strings to be split.</span></span> <span data-ttu-id="04012-127">Se você enviar várias cadeias de caracteres, todas as cadeias de caracteres serão divididas usando as mesmas regras de delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-127">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="04012-128">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="04012-128">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="04012-129">Os caracteres que identificam o final de uma subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-129">The characters that identify the end of a substring.</span></span> <span data-ttu-id="04012-130">O delimitador padrão é espaço em branco, incluindo espaços e caracteres não imprimíveis, como nova linha ( \` n) e tabulação ( \` t).</span><span class="sxs-lookup"><span data-stu-id="04012-130">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="04012-131">Quando as cadeias de caracteres são divididas, o delimitador é omitido de todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-131">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="04012-132">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="04012-132">Example:</span></span>

```powershell
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="04012-133">Por padrão, o delimitador é omitido dos resultados.</span><span class="sxs-lookup"><span data-stu-id="04012-133">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="04012-134">Para preservar todo ou parte do delimitador, coloque entre parênteses a parte que você deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="04012-134">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="04012-135">Se o `<Max-substrings>` parâmetro for adicionado, isso terá precedência quando o comando dividir a coleção.</span><span class="sxs-lookup"><span data-stu-id="04012-135">If the `<Max-substrings>` parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="04012-136">Se você optar por incluir um delimitador como parte da saída, o comando retornará o delimitador como parte da saída; no entanto, dividir a cadeia de caracteres para retornar o delimitador como parte da saída não conta como uma divisão.</span><span class="sxs-lookup"><span data-stu-id="04012-136">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="04012-137">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="04012-137">Examples:</span></span>

```powershell
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

### `<Max-substrings>`

<span data-ttu-id="04012-138">Especifica o número máximo de subcadeias de caracteres retornado pela operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="04012-138">Specifies the maximum number of substrings returned by the split operation.</span></span> <span data-ttu-id="04012-139">O padrão é todas as subcadeias de caracteres divididas pelo delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-139">The default is all substrings split by the delimiter.</span></span> <span data-ttu-id="04012-140">Se houver mais subcadeias de caracteres, elas serão concatenadas à subcadeia de caracteres final.</span><span class="sxs-lookup"><span data-stu-id="04012-140">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="04012-141">Se houver menos subcadeias de caracteres, todas as subcadeias serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="04012-141">If there are fewer substrings, all substrings are returned.</span></span> <span data-ttu-id="04012-142">Um valor de 0 retorna todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-142">A value of 0 returns all the substrings.</span></span>

<span data-ttu-id="04012-143">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="04012-143">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="04012-144">Se você enviar mais de uma cadeia de caracteres (uma matriz de cadeias de caracteres) para o `-split` operador, o `Max-substrings` limite será aplicado a cada cadeia de caracteres separadamente.</span><span class="sxs-lookup"><span data-stu-id="04012-144">If you submit more than one string (an array of strings) to the `-split` operator, the `Max-substrings` limit is applied to each string separately.</span></span>

```powershell
$c = 'a,b,c','1,2,3,4,5'
$c -split ',', 3

a
b
c
1
2
3,4,5
```

<span data-ttu-id="04012-145">`<Max-substrings>` não especifica o número máximo de objetos retornados.</span><span class="sxs-lookup"><span data-stu-id="04012-145">`<Max-substrings>` does not specify the maximum number of objects that are returned.</span></span> <span data-ttu-id="04012-146">No exemplo a seguir, `<Max-substrings>` é definido como 3.</span><span class="sxs-lookup"><span data-stu-id="04012-146">In the following example, `<Max-substrings>` is set to 3.</span></span>
<span data-ttu-id="04012-147">Isso resulta em três valores de subcadeias de caracteres, mas um total de cinco cadeias de caracteres na saída resultante.</span><span class="sxs-lookup"><span data-stu-id="04012-147">This results in three substring values, but a total of five strings in the resulting output.</span></span> <span data-ttu-id="04012-148">O delimitador é incluído após as divisões até que o máximo de três subcadeias de caracteres seja atingido.</span><span class="sxs-lookup"><span data-stu-id="04012-148">The delimiter is included after the splits until the maximum of three substrings is reached.</span></span> <span data-ttu-id="04012-149">Delimitadores adicionais na Subcadeia de caracteres final tornam-se parte da subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-149">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

<span data-ttu-id="04012-150">Valores negativos retornam a quantidade de subcadeias de caracteres solicitadas a partir do final da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="04012-150">Negative values return the amount of substrings requested starting from the end of the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="04012-151">O suporte para valores negativos foi adicionado no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="04012-151">Support for negative values was added in PowerShell 7.</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="04012-152">Uma expressão que especifica regras para aplicar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-152">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="04012-153">A expressão deve ser avaliada como $true ou $false.</span><span class="sxs-lookup"><span data-stu-id="04012-153">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="04012-154">Coloque o bloco de script entre chaves.</span><span class="sxs-lookup"><span data-stu-id="04012-154">Enclose the script block in braces.</span></span>

<span data-ttu-id="04012-155">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="04012-155">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="04012-156">Coloque o nome da opção entre aspas.</span><span class="sxs-lookup"><span data-stu-id="04012-156">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="04012-157">As opções são válidas somente quando o \<Max-substrings\> parâmetro é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="04012-157">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="04012-158">A sintaxe para o parâmetro options é:</span><span class="sxs-lookup"><span data-stu-id="04012-158">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="04012-159">As opções de SimpleMatch são:</span><span class="sxs-lookup"><span data-stu-id="04012-159">The SimpleMatch options are:</span></span>

- <span data-ttu-id="04012-160">**SimpleMatch**: Use a comparação de cadeia de caracteres simples ao avaliar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-160">**SimpleMatch**: Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="04012-161">Não pode ser usado com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="04012-161">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="04012-162">**IgnoreCase**: força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.</span><span class="sxs-lookup"><span data-stu-id="04012-162">**IgnoreCase**: Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="04012-163">As opções de RegexMatch são:</span><span class="sxs-lookup"><span data-stu-id="04012-163">The RegexMatch options are:</span></span>

- <span data-ttu-id="04012-164">**RegexMatch**: Use a correspondência de expressão regular para avaliar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-164">**RegexMatch**: Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="04012-165">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="04012-165">This is the default behavior.</span></span> <span data-ttu-id="04012-166">Não pode ser usado com SimpleMatch.</span><span class="sxs-lookup"><span data-stu-id="04012-166">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="04012-167">**IgnoreCase**: força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.</span><span class="sxs-lookup"><span data-stu-id="04012-167">**IgnoreCase**: Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="04012-168">**CultureInvariant**: ignora diferenças culturais em linguagem quando evaluting o delimitador.</span><span class="sxs-lookup"><span data-stu-id="04012-168">**CultureInvariant**: Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="04012-169">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="04012-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="04012-170">**IgnorePatternWhitespace**: ignora o espaço em branco e os comentários sem escape marcados com o sinal numérico (#).</span><span class="sxs-lookup"><span data-stu-id="04012-170">**IgnorePatternWhitespace**: Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="04012-171">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="04012-171">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="04012-172">**Multiline**: o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="04012-172">**Multiline**: Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="04012-173">**Unificação**: o modo de única trata a cadeia de caracteres de entrada como uma *única*.</span><span class="sxs-lookup"><span data-stu-id="04012-173">**Singleline**: Singleline mode treats the input string as a *SingleLine*.</span></span>
  <span data-ttu-id="04012-174">Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .</span><span class="sxs-lookup"><span data-stu-id="04012-174">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="04012-175">**ExplicitCapture**: ignora grupos de correspondências não nomeados para que apenas grupos de captura explícitos sejam retornados na lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="04012-175">**ExplicitCapture**: Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="04012-176">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="04012-176">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="04012-177">OPERADORES unários e de divisão binária</span><span class="sxs-lookup"><span data-stu-id="04012-177">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="04012-178">O operador de divisão unário ( `-split <string>` ) tem precedência mais alta do que uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="04012-178">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="04012-179">Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador de divisão unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será dividida.</span><span class="sxs-lookup"><span data-stu-id="04012-179">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="04012-180">Use um dos seguintes padrões para dividir mais de uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="04012-180">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="04012-181">Usar o operador de divisão binária ( \<string[]\> -Split \<delimiter\> )</span><span class="sxs-lookup"><span data-stu-id="04012-181">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="04012-182">Coloque todas as cadeias de caracteres entre parênteses</span><span class="sxs-lookup"><span data-stu-id="04012-182">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="04012-183">Armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para o operador de divisão</span><span class="sxs-lookup"><span data-stu-id="04012-183">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="04012-184">Considere o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="04012-184">Consider the following example:</span></span>

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a><span data-ttu-id="04012-185">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="04012-185">EXAMPLES</span></span>

<span data-ttu-id="04012-186">A instrução a seguir divide a cadeia de caracteres em espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="04012-186">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="04012-187">A instrução a seguir divide a cadeia de caracteres em qualquer vírgula.</span><span class="sxs-lookup"><span data-stu-id="04012-187">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="04012-188">A instrução a seguir divide a cadeia de caracteres no padrão "er".</span><span class="sxs-lookup"><span data-stu-id="04012-188">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="04012-189">A instrução a seguir executa uma divisão com diferenciação de maiúsculas e minúsculas na letra "N".</span><span class="sxs-lookup"><span data-stu-id="04012-189">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="04012-190">A instrução a seguir divide a cadeia de caracteres em "e" e "t".</span><span class="sxs-lookup"><span data-stu-id="04012-190">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

<span data-ttu-id="04012-191">A instrução a seguir divide a cadeia de caracteres em "e" e "r", mas limita as subcadeias de caracteres resultantes a seis subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-191">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="04012-192">A instrução a seguir divide uma cadeia de caracteres em três subcadeias.</span><span class="sxs-lookup"><span data-stu-id="04012-192">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="04012-193">A instrução a seguir divide uma cadeia de caracteres em três subcadeias de caracteres começando do final da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-193">The following statement splits a string into three substrings starting from the end of the string.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

<span data-ttu-id="04012-194">A instrução a seguir divide duas cadeias de caracteres em três subcadeias.</span><span class="sxs-lookup"><span data-stu-id="04012-194">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="04012-195">(O limite é aplicado a cada cadeia de caracteres de forma independente.)</span><span class="sxs-lookup"><span data-stu-id="04012-195">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="04012-196">A instrução a seguir divide cada linha na cadeia de caracteres here no primeiro dígito.</span><span class="sxs-lookup"><span data-stu-id="04012-196">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="04012-197">Ele usa a opção MultiLine para reconhecer o início de cada linha e cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="04012-197">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="04012-198">O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings.</span><span class="sxs-lookup"><span data-stu-id="04012-198">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="04012-199">Você pode usar opções, como MultiLine, somente quando o valor Max-substrings for especificado.</span><span class="sxs-lookup"><span data-stu-id="04012-199">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="04012-200">A instrução a seguir usa o caractere de barra invertida para escapar do delimitador de ponto (.).</span><span class="sxs-lookup"><span data-stu-id="04012-200">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="04012-201">Com o padrão, RegexMatch, o ponto entre aspas (".") é interpretado para corresponder a qualquer caractere, exceto para um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="04012-201">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="04012-202">Como resultado, a instrução Split retorna uma linha em branco para cada caractere, exceto nova linha.</span><span class="sxs-lookup"><span data-stu-id="04012-202">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

<span data-ttu-id="04012-203">A instrução a seguir usa a opção SimpleMatch para direcionar o operador-split para interpretar o delimitador de ponto (.) literalmente.</span><span class="sxs-lookup"><span data-stu-id="04012-203">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="04012-204">O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings.</span><span class="sxs-lookup"><span data-stu-id="04012-204">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="04012-205">Você pode usar opções, como SimpleMatch, somente quando o valor Max-substrings for especificado.</span><span class="sxs-lookup"><span data-stu-id="04012-205">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

<span data-ttu-id="04012-206">A instrução a seguir divide a cadeia de caracteres em um dos dois delimitadores, dependendo do valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="04012-206">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="04012-207">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="04012-207">SEE ALSO</span></span>

[<span data-ttu-id="04012-208">Split-Path</span><span class="sxs-lookup"><span data-stu-id="04012-208">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="04012-209">about_Operators</span><span class="sxs-lookup"><span data-stu-id="04012-209">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="04012-210">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="04012-210">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="04012-211">about_Join</span><span class="sxs-lookup"><span data-stu-id="04012-211">about_Join</span></span>](about_Join.md)
