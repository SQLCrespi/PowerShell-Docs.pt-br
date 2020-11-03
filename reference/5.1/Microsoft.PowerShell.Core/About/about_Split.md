---
description: Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/20/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: e93f68265bf560b03ac503ca914a11dde1f6b061
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195959"
---
# <a name="about-split"></a><span data-ttu-id="512ec-104">Sobre divisão</span><span class="sxs-lookup"><span data-stu-id="512ec-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="512ec-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="512ec-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="512ec-106">Explica como usar o operador split para dividir uma ou mais cadeias de caracteres em subcadeias.</span><span class="sxs-lookup"><span data-stu-id="512ec-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="512ec-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="512ec-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="512ec-108">O operador Split divide uma ou mais cadeias de caracteres em subcadeias.</span><span class="sxs-lookup"><span data-stu-id="512ec-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="512ec-109">Você pode alterar os seguintes elementos da operação Split:</span><span class="sxs-lookup"><span data-stu-id="512ec-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="512ec-110">Delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-110">Delimiter.</span></span> <span data-ttu-id="512ec-111">O padrão é espaço em branco, mas você pode especificar caracteres, cadeias, padrões ou blocos de script que especificam o delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="512ec-112">O operador split no Windows PowerShell usa uma expressão regular no delimitador, em vez de um caractere simples.</span><span class="sxs-lookup"><span data-stu-id="512ec-112">The Split operator in Windows PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="512ec-113">Número máximo de subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-113">Maximum number of substrings.</span></span> <span data-ttu-id="512ec-114">O padrão é retornar todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-114">The default is to return all substrings.</span></span> <span data-ttu-id="512ec-115">Se você especificar um número menor que o número de subcadeias de caracteres, as subcadeias restantes serão concatenadas na última subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="512ec-116">Opções que especificam as condições sob as quais o delimitador é correspondido, como SimpleMatch e Multiline.</span><span class="sxs-lookup"><span data-stu-id="512ec-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="512ec-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="512ec-117">SYNTAX</span></span>

<span data-ttu-id="512ec-118">O diagrama a seguir mostra a sintaxe do operador-split.</span><span class="sxs-lookup"><span data-stu-id="512ec-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="512ec-119">Os nomes de parâmetro não aparecem no comando.</span><span class="sxs-lookup"><span data-stu-id="512ec-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="512ec-120">Inclua apenas os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="512ec-120">Include only the parameter values.</span></span> <span data-ttu-id="512ec-121">Os valores devem aparecer na ordem especificada no diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="512ec-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="512ec-122">Você pode substituir `-iSplit` ou `-cSplit` `-split` em qualquer instrução Split binária (uma instrução Split que inclui um delimitador ou bloco de script).</span><span class="sxs-lookup"><span data-stu-id="512ec-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="512ec-123">Os `-iSplit` operadores e não diferenciam `-split` maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="512ec-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="512ec-124">O `-cSplit` operador diferencia maiúsculas de minúsculas, o que significa que o caso é considerado quando as regras de delimitador são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="512ec-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="512ec-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="512ec-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="512ec-126">\<String\> ou \<String[]\></span><span class="sxs-lookup"><span data-stu-id="512ec-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="512ec-127">Especifica uma ou mais cadeias de caracteres a serem divididas.</span><span class="sxs-lookup"><span data-stu-id="512ec-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="512ec-128">Se você enviar várias cadeias de caracteres, todas as cadeias de caracteres serão divididas usando as mesmas regras de delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="512ec-129">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="512ec-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="512ec-130">Os caracteres que identificam o final de uma subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="512ec-131">O delimitador padrão é espaço em branco, incluindo espaços e caracteres não imprimíveis, como nova linha ( \` n) e tabulação ( \` t).</span><span class="sxs-lookup"><span data-stu-id="512ec-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="512ec-132">Quando as cadeias de caracteres são divididas, o delimitador é omitido de todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="512ec-133">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="512ec-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="512ec-134">Por padrão, o delimitador é omitido dos resultados.</span><span class="sxs-lookup"><span data-stu-id="512ec-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="512ec-135">Para preservar todo ou parte do delimitador, coloque entre parênteses a parte que você deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="512ec-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="512ec-136">Se o \<Max-substrings\> parâmetro for adicionado, isso terá precedência quando o comando dividir a coleção.</span><span class="sxs-lookup"><span data-stu-id="512ec-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="512ec-137">Se você optar por incluir um delimitador como parte da saída, o comando retornará o delimitador como parte da saída; no entanto, dividir a cadeia de caracteres para retornar o delimitador como parte da saída não conta como uma divisão.</span><span class="sxs-lookup"><span data-stu-id="512ec-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="512ec-138">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="512ec-138">Examples:</span></span>

```
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

<span data-ttu-id="512ec-139">No exemplo a seguir, \<Max-substrings\> é definido como 3.</span><span class="sxs-lookup"><span data-stu-id="512ec-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="512ec-140">Isso resulta em três divisões dos valores de cadeia de caracteres, mas um total de cinco cadeias na saída resultante; o delimitador é incluído após as divisões, até que o máximo de três subcadeias de caracteres seja atingido.</span><span class="sxs-lookup"><span data-stu-id="512ec-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="512ec-141">Delimitadores adicionais na Subcadeia de caracteres final tornam-se parte da subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-141">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

<span data-ttu-id="512ec-142">Especifica o número máximo de vezes que uma cadeia de caracteres é dividida.</span><span class="sxs-lookup"><span data-stu-id="512ec-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="512ec-143">O padrão é todas as subcadeias de caracteres divididas pelo delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="512ec-144">Se houver mais subcadeias de caracteres, elas serão concatenadas à subcadeia de caracteres final.</span><span class="sxs-lookup"><span data-stu-id="512ec-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="512ec-145">Se houver menos subcadeias de caracteres, todas as subcadeias de caracteres serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="512ec-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="512ec-146">Um valor de 0 e valores negativos retornam todas as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-146">A value of 0 and negative values return all the substrings.</span></span>

<span data-ttu-id="512ec-147">Max-subcadeias de caracteres não especifica o número máximo de objetos retornados; seu valor é igual ao número máximo de vezes que uma cadeia de caracteres é dividida.</span><span class="sxs-lookup"><span data-stu-id="512ec-147">Max-substrings does not specify the maximum number of objects that are returned; its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="512ec-148">Se você enviar mais de uma cadeia de caracteres (uma matriz de cadeias de caracteres) para o operador de divisão, o limite máx. de subcadeias de caracteres será aplicado a cada cadeia de caracteres separadamente.</span><span class="sxs-lookup"><span data-stu-id="512ec-148">If you submit more than one string (an array of strings) to the Split operator , the Max-substrings limit is applied to each string separately.</span></span>

<span data-ttu-id="512ec-149">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="512ec-149">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="512ec-150">Uma expressão que especifica regras para aplicar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-150">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="512ec-151">A expressão deve ser avaliada como $true ou $false.</span><span class="sxs-lookup"><span data-stu-id="512ec-151">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="512ec-152">Coloque o bloco de script entre chaves.</span><span class="sxs-lookup"><span data-stu-id="512ec-152">Enclose the script block in braces.</span></span>

<span data-ttu-id="512ec-153">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="512ec-153">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="512ec-154">Coloque o nome da opção entre aspas.</span><span class="sxs-lookup"><span data-stu-id="512ec-154">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="512ec-155">As opções são válidas somente quando o \<Max-substrings\> parâmetro é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="512ec-155">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="512ec-156">A sintaxe para o parâmetro options é:</span><span class="sxs-lookup"><span data-stu-id="512ec-156">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="512ec-157">As opções de SimpleMatch são:</span><span class="sxs-lookup"><span data-stu-id="512ec-157">The SimpleMatch options are:</span></span>

- <span data-ttu-id="512ec-158">**SimpleMatch** : Use a comparação de cadeia de caracteres simples ao avaliar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-158">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="512ec-159">Não pode ser usado com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="512ec-159">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="512ec-160">**IgnoreCase** : força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.</span><span class="sxs-lookup"><span data-stu-id="512ec-160">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="512ec-161">As opções de RegexMatch são:</span><span class="sxs-lookup"><span data-stu-id="512ec-161">The RegexMatch options are:</span></span>

- <span data-ttu-id="512ec-162">**RegexMatch** : Use a correspondência de expressão regular para avaliar o delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-162">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="512ec-163">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="512ec-163">This is the default behavior.</span></span> <span data-ttu-id="512ec-164">Não pode ser usado com SimpleMatch.</span><span class="sxs-lookup"><span data-stu-id="512ec-164">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="512ec-165">**IgnoreCase** : força a correspondência que não diferencia maiúsculas de minúsculas, mesmo que o operador-csplit seja especificado.</span><span class="sxs-lookup"><span data-stu-id="512ec-165">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="512ec-166">**CultureInvariant** : ignora diferenças culturais em linguagem quando evaluting o delimitador.</span><span class="sxs-lookup"><span data-stu-id="512ec-166">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="512ec-167">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="512ec-167">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="512ec-168">**IgnorePatternWhitespace** : ignora o espaço em branco e os comentários sem escape marcados com o sinal numérico (#).</span><span class="sxs-lookup"><span data-stu-id="512ec-168">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="512ec-169">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="512ec-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="512ec-170">**Multiline** : o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="512ec-170">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="512ec-171">**Unificação** : o modo de única trata a cadeia de caracteres de entrada como uma *única* .</span><span class="sxs-lookup"><span data-stu-id="512ec-171">**Singleline** : Singleline mode treats the input string as a *SingleLine* .</span></span>
  <span data-ttu-id="512ec-172">Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .</span><span class="sxs-lookup"><span data-stu-id="512ec-172">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="512ec-173">**ExplicitCapture** : ignora grupos de correspondências não nomeados para que apenas grupos de captura explícitos sejam retornados na lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="512ec-173">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="512ec-174">Válido somente com RegexMatch.</span><span class="sxs-lookup"><span data-stu-id="512ec-174">Valid only with RegexMatch.</span></span>

> [!NOTE]
> <span data-ttu-id="512ec-175">A única é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="512ec-175">SingleLine is the default behavior.</span></span> <span data-ttu-id="512ec-176">Uni e Multiline não podem ser usadas junto com o parâmetro options.</span><span class="sxs-lookup"><span data-stu-id="512ec-176">Singleline and Multiline cannot be used together with the options parameter.</span></span> <span data-ttu-id="512ec-177">Isso foi resolvido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="512ec-177">This was resolved in PowerShell 6.0.</span></span>
> <span data-ttu-id="512ec-178">A solução alternativa é usar *modificadores de modo* em sua expressão regular.</span><span class="sxs-lookup"><span data-stu-id="512ec-178">The work around is by using *Mode-Modifiers* in your regular expression.</span></span>
> <span data-ttu-id="512ec-179">Você pode ler mais sobre modificadores de modo em [Opções de expressão regular](/dotnet/standard/base-types/regular-expression-options)</span><span class="sxs-lookup"><span data-stu-id="512ec-179">You can read more about mode modifiers in [Regular Expression Options](/dotnet/standard/base-types/regular-expression-options)</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="512ec-180">OPERADORES unários e de divisão binária</span><span class="sxs-lookup"><span data-stu-id="512ec-180">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="512ec-181">O operador de divisão unário ( `-split <string>` ) tem precedência mais alta do que uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="512ec-181">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="512ec-182">Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador de divisão unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será dividida.</span><span class="sxs-lookup"><span data-stu-id="512ec-182">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="512ec-183">Use um dos seguintes padrões para dividir mais de uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="512ec-183">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="512ec-184">Usar o operador de divisão binária ( \<string[]\> -Split \<delimiter\> )</span><span class="sxs-lookup"><span data-stu-id="512ec-184">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="512ec-185">Coloque todas as cadeias de caracteres entre parênteses</span><span class="sxs-lookup"><span data-stu-id="512ec-185">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="512ec-186">Armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para o operador de divisão</span><span class="sxs-lookup"><span data-stu-id="512ec-186">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="512ec-187">Considere o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="512ec-187">Consider the following example:</span></span>

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

## <a name="examples"></a><span data-ttu-id="512ec-188">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="512ec-188">EXAMPLES</span></span>

<span data-ttu-id="512ec-189">A instrução a seguir divide a cadeia de caracteres em espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="512ec-189">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="512ec-190">A instrução a seguir divide a cadeia de caracteres em qualquer vírgula.</span><span class="sxs-lookup"><span data-stu-id="512ec-190">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="512ec-191">A instrução a seguir divide a cadeia de caracteres no padrão "er".</span><span class="sxs-lookup"><span data-stu-id="512ec-191">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="512ec-192">A instrução a seguir executa uma divisão com diferenciação de maiúsculas e minúsculas na letra "N".</span><span class="sxs-lookup"><span data-stu-id="512ec-192">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="512ec-193">A instrução a seguir divide a cadeia de caracteres em "e" e "t".</span><span class="sxs-lookup"><span data-stu-id="512ec-193">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```output
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

<span data-ttu-id="512ec-194">A instrução a seguir divide a cadeia de caracteres em "e" e "r", mas limita as subcadeias de caracteres resultantes a seis subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-194">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="512ec-195">A instrução a seguir divide uma cadeia de caracteres em três subcadeias.</span><span class="sxs-lookup"><span data-stu-id="512ec-195">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="512ec-196">A instrução a seguir divide duas cadeias de caracteres em três subcadeias.</span><span class="sxs-lookup"><span data-stu-id="512ec-196">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="512ec-197">(O limite é aplicado a cada cadeia de caracteres de forma independente.)</span><span class="sxs-lookup"><span data-stu-id="512ec-197">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="512ec-198">A instrução a seguir divide cada linha na cadeia de caracteres here no primeiro dígito.</span><span class="sxs-lookup"><span data-stu-id="512ec-198">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="512ec-199">Ele usa a opção MultiLine para reconhecer o início de cada linha e cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="512ec-199">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="512ec-200">O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings.</span><span class="sxs-lookup"><span data-stu-id="512ec-200">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="512ec-201">Você pode usar opções, como MultiLine, somente quando o valor Max-substrings for especificado.</span><span class="sxs-lookup"><span data-stu-id="512ec-201">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="512ec-202">A instrução a seguir usa o caractere de barra invertida para escapar do delimitador de ponto (.).</span><span class="sxs-lookup"><span data-stu-id="512ec-202">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="512ec-203">Com o padrão, RegexMatch, o ponto entre aspas (".") é interpretado para corresponder a qualquer caractere, exceto para um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="512ec-203">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="512ec-204">Como resultado, a instrução Split retorna uma linha em branco para cada caractere, exceto nova linha.</span><span class="sxs-lookup"><span data-stu-id="512ec-204">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```output
This
is
a
test
```

<span data-ttu-id="512ec-205">A instrução a seguir usa a opção SimpleMatch para direcionar o operador-split para interpretar o delimitador de ponto (.) literalmente.</span><span class="sxs-lookup"><span data-stu-id="512ec-205">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="512ec-206">O 0 representa o valor de "retornar tudo" do parâmetro Max-substrings.</span><span class="sxs-lookup"><span data-stu-id="512ec-206">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="512ec-207">Você pode usar opções, como SimpleMatch, somente quando o valor Max-substrings for especificado.</span><span class="sxs-lookup"><span data-stu-id="512ec-207">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```output
This
is
a
test
```

<span data-ttu-id="512ec-208">A instrução a seguir divide a cadeia de caracteres em um dos dois delimitadores, dependendo do valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="512ec-208">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="512ec-209">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="512ec-209">SEE ALSO</span></span>

[<span data-ttu-id="512ec-210">Split-Path</span><span class="sxs-lookup"><span data-stu-id="512ec-210">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="512ec-211">about_Operators</span><span class="sxs-lookup"><span data-stu-id="512ec-211">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="512ec-212">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="512ec-212">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="512ec-213">about_Join</span><span class="sxs-lookup"><span data-stu-id="512ec-213">about_Join</span></span>](about_Join.md)
