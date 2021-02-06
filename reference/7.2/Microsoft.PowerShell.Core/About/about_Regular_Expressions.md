---
description: Descreve expressões regulares no PowerShell.
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 4dc6ac670a31cbea4c35ee6540ce3368ad9b02ca
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595961"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="9bc83-103">Sobre expressões regulares</span><span class="sxs-lookup"><span data-stu-id="9bc83-103">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="9bc83-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="9bc83-104">Short description</span></span>
<span data-ttu-id="9bc83-105">Descreve expressões regulares no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bc83-105">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9bc83-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="9bc83-106">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="9bc83-107">Este artigo mostrará a sintaxe e os métodos para usar expressões regulares no PowerShell, nem toda a sintaxe será discutida.</span><span class="sxs-lookup"><span data-stu-id="9bc83-107">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="9bc83-108">Para obter uma referência mais completa, consulte a [linguagem de expressão regular – referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="9bc83-108">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="9bc83-109">Uma expressão regular é um padrão usado para corresponder texto.</span><span class="sxs-lookup"><span data-stu-id="9bc83-109">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="9bc83-110">Ele pode ser composto por caracteres literais, operadores e outras construções.</span><span class="sxs-lookup"><span data-stu-id="9bc83-110">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="9bc83-111">Este artigo demonstra a sintaxe de expressão regular no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bc83-111">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="9bc83-112">O PowerShell tem vários operadores e cmdlets que usam expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="9bc83-112">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="9bc83-113">Você pode ler mais sobre sua sintaxe e uso nos links abaixo.</span><span class="sxs-lookup"><span data-stu-id="9bc83-113">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="9bc83-114">Select-String</span><span class="sxs-lookup"><span data-stu-id="9bc83-114">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="9bc83-115">operadores de correspondência e substituição</span><span class="sxs-lookup"><span data-stu-id="9bc83-115">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="9bc83-116">-Divisão</span><span class="sxs-lookup"><span data-stu-id="9bc83-116">-split</span></span>](about_Split.md)
- [<span data-ttu-id="9bc83-117">instrução switch com a opção-Regex</span><span class="sxs-lookup"><span data-stu-id="9bc83-117">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="9bc83-118">As expressões regulares do PowerShell não diferenciam maiúsculas de minúsculas por padrão.</span><span class="sxs-lookup"><span data-stu-id="9bc83-118">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="9bc83-119">Cada método mostrado acima tem uma maneira diferente de forçar a diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9bc83-119">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="9bc83-120">Método</span><span class="sxs-lookup"><span data-stu-id="9bc83-120">Method</span></span>       |                      <span data-ttu-id="9bc83-121">Diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="9bc83-121">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="9bc83-122">usar `-CaseSensitive` opção</span><span class="sxs-lookup"><span data-stu-id="9bc83-122">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="9bc83-123">Instrução `switch`</span><span class="sxs-lookup"><span data-stu-id="9bc83-123">`switch` statement</span></span> | <span data-ttu-id="9bc83-124">Use a `-casesensitive` opção</span><span class="sxs-lookup"><span data-stu-id="9bc83-124">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="9bc83-125">operadores</span><span class="sxs-lookup"><span data-stu-id="9bc83-125">operators</span></span>          | <span data-ttu-id="9bc83-126">prefixar com **' C'** ( `-cmatch` , `-csplit` ou `-creplace` )</span><span class="sxs-lookup"><span data-stu-id="9bc83-126">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="9bc83-127">Literais de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bc83-127">Character literals</span></span>

<span data-ttu-id="9bc83-128">Uma expressão regular pode ser um caractere literal ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-128">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="9bc83-129">A expressão faz com que o mecanismo corresponda exatamente ao texto especificado.</span><span class="sxs-lookup"><span data-stu-id="9bc83-129">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="9bc83-130">Classes de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bc83-130">Character classes</span></span>

<span data-ttu-id="9bc83-131">Enquanto os literais de caractere funcionam se você sabe o padrão exato, as classes de caractere permitem que você seja menos específico.</span><span class="sxs-lookup"><span data-stu-id="9bc83-131">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="9bc83-132">Grupos de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bc83-132">Character groups</span></span>

<span data-ttu-id="9bc83-133">`[character group]` permite que você corresponda a qualquer número de caracteres uma vez, enquanto `[^character group]` só corresponde a caracteres que não estão no grupo.</span><span class="sxs-lookup"><span data-stu-id="9bc83-133">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="9bc83-134">Se a lista de caracteres a corresponder incluir o caractere de hífen ( `-` ), ela deverá estar no início ou no final da lista para distingui-la de uma expressão de intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-134">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="9bc83-135">Intervalos de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bc83-135">Character ranges</span></span>

<span data-ttu-id="9bc83-136">Um padrão também pode ser um intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-136">A pattern can also be a range of characters.</span></span> <span data-ttu-id="9bc83-137">Os caracteres podem ser alfabéticos `[A-Z]` , numéricos `[0-9]` ou até mesmo baseados em ASCII `[ -~]` (todos os caracteres imprimíveis).</span><span class="sxs-lookup"><span data-stu-id="9bc83-137">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="9bc83-138">Números</span><span class="sxs-lookup"><span data-stu-id="9bc83-138">Numbers</span></span>

<span data-ttu-id="9bc83-139">A `\d` classe de caractere corresponderá a qualquer dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="9bc83-139">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="9bc83-140">Por outro lado, o `\D` coincidirá com qualquer dígito diferente de Decimal.</span><span class="sxs-lookup"><span data-stu-id="9bc83-140">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="9bc83-141">Caracteres de palavra</span><span class="sxs-lookup"><span data-stu-id="9bc83-141">Word characters</span></span>

<span data-ttu-id="9bc83-142">A `\w` classe de caractere corresponderá a qualquer caractere de palavra `[a-zA-Z_0-9]` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-142">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="9bc83-143">Para corresponder a qualquer caractere que não seja palavra, use `\W` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-143">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="9bc83-144">Curingas</span><span class="sxs-lookup"><span data-stu-id="9bc83-144">Wildcards</span></span>

<span data-ttu-id="9bc83-145">O period ( `.` ) é um caractere curinga em expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="9bc83-145">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="9bc83-146">Ele fará a correspondência de qualquer caractere, exceto uma nova linha ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="9bc83-146">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="9bc83-147">Espaço em branco</span><span class="sxs-lookup"><span data-stu-id="9bc83-147">Whitespace</span></span>

<span data-ttu-id="9bc83-148">O espaço em branco é correspondido usando a `\s` classe Character.</span><span class="sxs-lookup"><span data-stu-id="9bc83-148">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="9bc83-149">Qualquer caractere diferente de espaço em branco é correspondido usando `\S` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-149">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="9bc83-150">Os caracteres de espaço literal `' '` também podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="9bc83-150">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="9bc83-151">Quantificadores</span><span class="sxs-lookup"><span data-stu-id="9bc83-151">Quantifiers</span></span>

<span data-ttu-id="9bc83-152">Quantificadores controlam quantas instâncias de cada elemento devem estar presentes na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-152">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="9bc83-153">A seguir estão alguns dos quantificadores disponíveis no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9bc83-153">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="9bc83-154">Quantificador</span><span class="sxs-lookup"><span data-stu-id="9bc83-154">Quantifier</span></span> |                <span data-ttu-id="9bc83-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bc83-155">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="9bc83-156">Zero ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-156">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="9bc83-157">Uma ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-157">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="9bc83-158">Zero ou uma vez.</span><span class="sxs-lookup"><span data-stu-id="9bc83-158">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="9bc83-159">Pelo menos `n` , mas não mais do que `m` vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-159">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="9bc83-160">O asterisco ( `*` ) corresponde ao elemento anterior zero ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-160">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="9bc83-161">O resultado é que até mesmo uma cadeia de caracteres de entrada sem o elemento seria uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="9bc83-161">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="9bc83-162">O sinal de adição ( `+` ) corresponde ao elemento anterior uma ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-162">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="9bc83-163">O ponto de interrogação `?` corresponde ao elemento anterior zero ou uma vez.</span><span class="sxs-lookup"><span data-stu-id="9bc83-163">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="9bc83-164">Como `*` um asterisco, ele corresponderá até mesmo às cadeias de caracteres em que o elemento está ausente.</span><span class="sxs-lookup"><span data-stu-id="9bc83-164">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="9bc83-165">O `{n, m}` quantificador pode ser usado de várias maneiras diferentes para permitir o controle granular do quantificador.</span><span class="sxs-lookup"><span data-stu-id="9bc83-165">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="9bc83-166">O segundo elemento `m` e a vírgula `,` são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9bc83-166">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="9bc83-167">Quantificador</span><span class="sxs-lookup"><span data-stu-id="9bc83-167">Quantifier</span></span> |                <span data-ttu-id="9bc83-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bc83-168">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="9bc83-169">Corresponder exatamente ao `n` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-169">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="9bc83-170">Corresponder pelo menos `n` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-170">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="9bc83-171">Correspondência entre `n` e `m` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="9bc83-171">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="9bc83-172">Âncoras</span><span class="sxs-lookup"><span data-stu-id="9bc83-172">Anchors</span></span>

<span data-ttu-id="9bc83-173">As âncoras permitem que você cause uma correspondência com êxito ou falha com base na posição de correspondências dentro da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-173">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="9bc83-174">As duas âncoras comumente usadas são `^` e `$` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-174">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="9bc83-175">O cursor `^` corresponde ao início de uma cadeia de caracteres e `$` , que corresponde ao final de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-175">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="9bc83-176">As âncoras permitem que você corresponda ao texto em uma posição específica enquanto também descarta caracteres indesejados.</span><span class="sxs-lookup"><span data-stu-id="9bc83-176">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="9bc83-177">Ao definir um Regex contendo uma `$` âncora, certifique-se de colocar o Regex usando aspas simples ( `'` ) em vez de aspas duplas ( `"` ) ou o PowerShell expandirá a expressão como uma variável.</span><span class="sxs-lookup"><span data-stu-id="9bc83-177">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="9bc83-178">Ao usar âncoras no PowerShell, você deve entender a diferença entre as opções de expressão única de linhas **simples** e de **multilinha** .</span><span class="sxs-lookup"><span data-stu-id="9bc83-178">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="9bc83-179">**Multiline**: o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-179">**Multiline**: Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="9bc83-180">**Unificação**: o modo de única trata a cadeia de caracteres de entrada como uma **única**.</span><span class="sxs-lookup"><span data-stu-id="9bc83-180">**Singleline**: Singleline mode treats the input string as a **SingleLine**.</span></span>
  <span data-ttu-id="9bc83-181">Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-181">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="9bc83-182">Para ler mais sobre essas opções e como usá-las, visite a [linguagem de expressão regular-referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="9bc83-182">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="9bc83-183">Caracteres de escape</span><span class="sxs-lookup"><span data-stu-id="9bc83-183">Escaping characters</span></span>

<span data-ttu-id="9bc83-184">A barra invertida ( `\` ) é usada para escapar caracteres para que eles não sejam analisados pelo mecanismo de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="9bc83-184">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="9bc83-185">Os seguintes caracteres são reservados: `[]().\^$|?*+{}` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-185">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="9bc83-186">Você precisará escapar desses caracteres em seus padrões para que correspondam a eles nas cadeias de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-186">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="9bc83-187">Há um método estático da classe Regex que pode escapar do texto para você.</span><span class="sxs-lookup"><span data-stu-id="9bc83-187">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="9bc83-188">Isso escapa todos os caracteres de expressão regular reservados, incluindo barras invertidas existentes usadas em classes de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-188">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="9bc83-189">Certifique-se de usá-lo apenas na parte do padrão que você precisa escapar.</span><span class="sxs-lookup"><span data-stu-id="9bc83-189">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="9bc83-190">Outros escapes de caractere</span><span class="sxs-lookup"><span data-stu-id="9bc83-190">Other character escapes</span></span>

<span data-ttu-id="9bc83-191">Também há escapes de caractere reservado que você pode usar para corresponder a tipos de caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="9bc83-191">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="9bc83-192">A seguir estão alguns escapes de caractere usados com frequência:</span><span class="sxs-lookup"><span data-stu-id="9bc83-192">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="9bc83-193">Escape de caractere</span><span class="sxs-lookup"><span data-stu-id="9bc83-193">Character Escape</span></span>  |<span data-ttu-id="9bc83-194">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bc83-194">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="9bc83-195">Corresponde a uma tabulação</span><span class="sxs-lookup"><span data-stu-id="9bc83-195">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="9bc83-196">Corresponde a uma nova linha</span><span class="sxs-lookup"><span data-stu-id="9bc83-196">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="9bc83-197">Corresponde a um retorno de carro</span><span class="sxs-lookup"><span data-stu-id="9bc83-197">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="9bc83-198">Grupos, capturas e substituições</span><span class="sxs-lookup"><span data-stu-id="9bc83-198">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="9bc83-199">O agrupamento de construções separa uma cadeia de caracteres de entrada em subcadeias de caracteres que podem ser capturadas ou ignoradas.</span><span class="sxs-lookup"><span data-stu-id="9bc83-199">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="9bc83-200">Subcadeias de caracteres agrupadas são chamadas de subexpressões.</span><span class="sxs-lookup"><span data-stu-id="9bc83-200">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="9bc83-201">Por padrão, as subexpressões são capturadas em grupos numerados, embora você também possa atribuir nomes a elas.</span><span class="sxs-lookup"><span data-stu-id="9bc83-201">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="9bc83-202">Uma construção de agrupamento é uma expressão regular entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="9bc83-202">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="9bc83-203">Qualquer texto correspondido pela expressão regular embutida é capturado.</span><span class="sxs-lookup"><span data-stu-id="9bc83-203">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="9bc83-204">O exemplo a seguir quebrará o texto de entrada em dois grupos de captura.</span><span class="sxs-lookup"><span data-stu-id="9bc83-204">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="9bc83-205">Use a `$Matches` variável automática **Hashtable** para recuperar o texto capturado.</span><span class="sxs-lookup"><span data-stu-id="9bc83-205">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="9bc83-206">O texto que representa a correspondência inteira é armazenado na chave `0` .</span><span class="sxs-lookup"><span data-stu-id="9bc83-206">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="9bc83-207">As capturas são armazenadas em chaves de **inteiro** numéricos que aumentam da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="9bc83-207">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="9bc83-208">A captura `1` contém todo o texto até que o nome de usuário, Capture `2` contenha apenas o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="9bc83-208">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> <span data-ttu-id="9bc83-209">A `0` chave é um **número inteiro**.</span><span class="sxs-lookup"><span data-stu-id="9bc83-209">The `0` key is an **Integer**.</span></span> <span data-ttu-id="9bc83-210">Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.</span><span class="sxs-lookup"><span data-stu-id="9bc83-210">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```
> PS> 'Good Dog' -match 'Dog'
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

#### <a name="named-captures"></a><span data-ttu-id="9bc83-211">Capturas nomeadas</span><span class="sxs-lookup"><span data-stu-id="9bc83-211">Named Captures</span></span>

<span data-ttu-id="9bc83-212">Por padrão, as capturas são armazenadas em ordem numérica crescente, da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="9bc83-212">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="9bc83-213">Você também pode atribuir um **nome** a um grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="9bc83-213">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="9bc83-214">Esse **nome** se torna uma chave na `$Matches` variável automática de **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="9bc83-214">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="9bc83-215">Dentro de um grupo de captura, use `?<keyname>` para armazenar dados capturados em uma chave nomeada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-215">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

<span data-ttu-id="9bc83-216">O exemplo a seguir armazena a entrada de log mais recente no log de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="9bc83-216">The following example stores the newest log entry in the Windows Security Log.</span></span>
<span data-ttu-id="9bc83-217">A expressão regular fornecida extrai o nome de usuário e o domínio da mensagem e os armazena sob as chaves:**N** para nome e **D** para o domínio.</span><span class="sxs-lookup"><span data-stu-id="9bc83-217">The provided regular expression extracts the username and domain from the message and stores them under the keys:**N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

<span data-ttu-id="9bc83-218">Para obter mais informações, consulte [agrupando construções em expressões regulares](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="9bc83-218">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="9bc83-219">Substituições em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="9bc83-219">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="9bc83-220">Usar as expressões regulares com o `-replace` operador permite que você substitua dinamicamente o texto usando o texto capturado.</span><span class="sxs-lookup"><span data-stu-id="9bc83-220">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="9bc83-221">`<input>`: A cadeia de caracteres a ser pesquisada</span><span class="sxs-lookup"><span data-stu-id="9bc83-221">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="9bc83-222">`<original>`: Uma expressão regular usada para pesquisar a cadeia de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="9bc83-222">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="9bc83-223">`<substitute>`: Uma expressão de substituição de expressão regular para substituir as correspondências encontradas na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="9bc83-223">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="9bc83-224">Os `<original>` `<substitute>` operandos e estão sujeitos às regras do mecanismo de expressão regular, como saída de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-224">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="9bc83-225">Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bc83-225">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="9bc83-226">A substituição é feita usando o `$` caractere antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="9bc83-226">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="9bc83-227">Duas maneiras de fazer referência a grupos de captura são por **número** e por **nome**.</span><span class="sxs-lookup"><span data-stu-id="9bc83-227">Two ways to reference capturing groups are by **Number** and by **Name**.</span></span>

- <span data-ttu-id="9bc83-228">Por grupos de captura de **número** , são numerados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="9bc83-228">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="9bc83-229">Os grupos de captura de **nomes** também podem ser referenciados pelo nome.</span><span class="sxs-lookup"><span data-stu-id="9bc83-229">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="9bc83-230">A `$&` expressão representa todo o texto correspondido.</span><span class="sxs-lookup"><span data-stu-id="9bc83-230">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="9bc83-231">Como o `$` caractere é usado na expansão da cadeia de caracteres, você precisará usar cadeias literais com substituição ou escapar o `$` caractere ao usar aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="9bc83-231">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> <span data-ttu-id="9bc83-232">Além disso, se você quiser ter o `$` como um caractere literal, use `$$` em vez dos caracteres de escape normais.</span><span class="sxs-lookup"><span data-stu-id="9bc83-232">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="9bc83-233">Ao usar aspas duplas, ainda escapar de todas as instâncias do `$` para evitar a substituição incorreta.</span><span class="sxs-lookup"><span data-stu-id="9bc83-233">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

<span data-ttu-id="9bc83-234">Para obter mais informações, consulte [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="9bc83-234">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bc83-235">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9bc83-235">See also</span></span>

[<span data-ttu-id="9bc83-236">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="9bc83-236">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="9bc83-237">about_Operators</span><span class="sxs-lookup"><span data-stu-id="9bc83-237">about_Operators</span></span>](about_Operators.md)

