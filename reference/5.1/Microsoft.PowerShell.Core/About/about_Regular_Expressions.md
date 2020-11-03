---
description: Descreve expressões regulares no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 84eefe224912cca96e6637eb6e3f239ef66b25bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196165"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="a2f2c-104">Sobre expressões regulares</span><span class="sxs-lookup"><span data-stu-id="a2f2c-104">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="a2f2c-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a2f2c-105">Short description</span></span>
<span data-ttu-id="a2f2c-106">Descreve expressões regulares no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-106">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a2f2c-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a2f2c-107">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="a2f2c-108">Este artigo mostrará a sintaxe e os métodos para usar expressões regulares no PowerShell, nem toda a sintaxe será discutida.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-108">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="a2f2c-109">Para obter uma referência mais completa, consulte a [linguagem de expressão regular – referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-109">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="a2f2c-110">Uma expressão regular é um padrão usado para corresponder texto.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-110">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="a2f2c-111">Ele pode ser composto por caracteres literais, operadores e outras construções.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-111">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="a2f2c-112">Este artigo demonstra a sintaxe de expressão regular no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-112">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="a2f2c-113">O PowerShell tem vários operadores e cmdlets que usam expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-113">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="a2f2c-114">Você pode ler mais sobre sua sintaxe e uso nos links abaixo.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-114">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="a2f2c-115">Select-String</span><span class="sxs-lookup"><span data-stu-id="a2f2c-115">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="a2f2c-116">operadores de correspondência e substituição</span><span class="sxs-lookup"><span data-stu-id="a2f2c-116">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="a2f2c-117">-Divisão</span><span class="sxs-lookup"><span data-stu-id="a2f2c-117">-split</span></span>](about_Split.md)
- [<span data-ttu-id="a2f2c-118">instrução switch com a opção-Regex</span><span class="sxs-lookup"><span data-stu-id="a2f2c-118">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="a2f2c-119">As expressões regulares do PowerShell não diferenciam maiúsculas de minúsculas por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-119">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="a2f2c-120">Cada método mostrado acima tem uma maneira diferente de forçar a diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-120">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="a2f2c-121">Método</span><span class="sxs-lookup"><span data-stu-id="a2f2c-121">Method</span></span>       |                      <span data-ttu-id="a2f2c-122">Diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="a2f2c-122">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="a2f2c-123">usar `-CaseSensitive` opção</span><span class="sxs-lookup"><span data-stu-id="a2f2c-123">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="a2f2c-124">Instrução `switch`</span><span class="sxs-lookup"><span data-stu-id="a2f2c-124">`switch` statement</span></span> | <span data-ttu-id="a2f2c-125">Use a `-casesensitive` opção</span><span class="sxs-lookup"><span data-stu-id="a2f2c-125">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="a2f2c-126">operadores</span><span class="sxs-lookup"><span data-stu-id="a2f2c-126">operators</span></span>          | <span data-ttu-id="a2f2c-127">prefixar com **' C'** ( `-cmatch` , `-csplit` ou `-creplace` )</span><span class="sxs-lookup"><span data-stu-id="a2f2c-127">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="a2f2c-128">Literais de caracteres</span><span class="sxs-lookup"><span data-stu-id="a2f2c-128">Character literals</span></span>

<span data-ttu-id="a2f2c-129">Uma expressão regular pode ser um caractere literal ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-129">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="a2f2c-130">A expressão faz com que o mecanismo corresponda exatamente ao texto especificado.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-130">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="a2f2c-131">Classes de caracteres</span><span class="sxs-lookup"><span data-stu-id="a2f2c-131">Character classes</span></span>

<span data-ttu-id="a2f2c-132">Enquanto os literais de caractere funcionam se você sabe o padrão exato, as classes de caractere permitem que você seja menos específico.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-132">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="a2f2c-133">Grupos de caracteres</span><span class="sxs-lookup"><span data-stu-id="a2f2c-133">Character groups</span></span>

<span data-ttu-id="a2f2c-134">`[character group]` permite que você corresponda a qualquer número de caracteres uma vez, enquanto `[^character group]` só corresponde a caracteres que não estão no grupo.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-134">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="a2f2c-135">Se a lista de caracteres a corresponder incluir o caractere de hífen ( `-` ), ela deverá estar no início ou no final da lista para distingui-la de uma expressão de intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-135">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="a2f2c-136">Intervalos de caracteres</span><span class="sxs-lookup"><span data-stu-id="a2f2c-136">Character ranges</span></span>

<span data-ttu-id="a2f2c-137">Um padrão também pode ser um intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-137">A pattern can also be a range of characters.</span></span> <span data-ttu-id="a2f2c-138">Os caracteres podem ser alfabéticos `[A-Z]` , numéricos `[0-9]` ou até mesmo baseados em ASCII `[ -~]` (todos os caracteres imprimíveis).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-138">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="a2f2c-139">Números</span><span class="sxs-lookup"><span data-stu-id="a2f2c-139">Numbers</span></span>

<span data-ttu-id="a2f2c-140">A `\d` classe de caractere corresponderá a qualquer dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-140">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="a2f2c-141">Por outro lado, o `\D` coincidirá com qualquer dígito diferente de Decimal.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-141">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="a2f2c-142">Caracteres de palavra</span><span class="sxs-lookup"><span data-stu-id="a2f2c-142">Word characters</span></span>

<span data-ttu-id="a2f2c-143">A `\w` classe de caractere corresponderá a qualquer caractere de palavra `[a-zA-Z_0-9]` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-143">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="a2f2c-144">Para corresponder a qualquer caractere que não seja palavra, use `\W` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-144">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="a2f2c-145">Curingas</span><span class="sxs-lookup"><span data-stu-id="a2f2c-145">Wildcards</span></span>

<span data-ttu-id="a2f2c-146">O period ( `.` ) é um caractere curinga em expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-146">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="a2f2c-147">Ele fará a correspondência de qualquer caractere, exceto uma nova linha ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-147">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="a2f2c-148">Espaço em branco</span><span class="sxs-lookup"><span data-stu-id="a2f2c-148">Whitespace</span></span>

<span data-ttu-id="a2f2c-149">O espaço em branco é correspondido usando a `\s` classe Character.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-149">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="a2f2c-150">Qualquer caractere diferente de espaço em branco é correspondido usando `\S` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-150">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="a2f2c-151">Os caracteres de espaço literal `' '` também podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-151">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="a2f2c-152">Quantificadores</span><span class="sxs-lookup"><span data-stu-id="a2f2c-152">Quantifiers</span></span>

<span data-ttu-id="a2f2c-153">Quantificadores controlam quantas instâncias de cada elemento devem estar presentes na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-153">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="a2f2c-154">A seguir estão alguns dos quantificadores disponíveis no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2f2c-154">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="a2f2c-155">Quantificador</span><span class="sxs-lookup"><span data-stu-id="a2f2c-155">Quantifier</span></span> |                <span data-ttu-id="a2f2c-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2f2c-156">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="a2f2c-157">Zero ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-157">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="a2f2c-158">Uma ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-158">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="a2f2c-159">Zero ou uma vez.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-159">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="a2f2c-160">Pelo menos `n` , mas não mais do que `m` vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-160">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="a2f2c-161">O asterisco ( `*` ) corresponde ao elemento anterior zero ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-161">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="a2f2c-162">O resultado é que até mesmo uma cadeia de caracteres de entrada sem o elemento seria uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-162">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="a2f2c-163">O sinal de adição ( `+` ) corresponde ao elemento anterior uma ou mais vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-163">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="a2f2c-164">O ponto de interrogação `?` corresponde ao elemento anterior zero ou uma vez.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-164">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="a2f2c-165">Como `*` um asterisco, ele corresponderá até mesmo às cadeias de caracteres em que o elemento está ausente.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-165">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="a2f2c-166">O `{n, m}` quantificador pode ser usado de várias maneiras diferentes para permitir o controle granular do quantificador.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-166">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="a2f2c-167">O segundo elemento `m` e a vírgula `,` são opcionais.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-167">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="a2f2c-168">Quantificador</span><span class="sxs-lookup"><span data-stu-id="a2f2c-168">Quantifier</span></span> |                <span data-ttu-id="a2f2c-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2f2c-169">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="a2f2c-170">Corresponder exatamente ao `n` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-170">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="a2f2c-171">Corresponder pelo menos `n` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-171">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="a2f2c-172">Correspondência entre `n` e `m` número de vezes.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-172">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="a2f2c-173">Âncoras</span><span class="sxs-lookup"><span data-stu-id="a2f2c-173">Anchors</span></span>

<span data-ttu-id="a2f2c-174">As âncoras permitem que você cause uma correspondência com êxito ou falha com base na posição de correspondências dentro da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-174">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="a2f2c-175">As duas âncoras comumente usadas são `^` e `$` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-175">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="a2f2c-176">O cursor `^` corresponde ao início de uma cadeia de caracteres e `$` , que corresponde ao final de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-176">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="a2f2c-177">As âncoras permitem que você corresponda ao texto em uma posição específica enquanto também descarta caracteres indesejados.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-177">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="a2f2c-178">Ao definir um Regex contendo uma `$` âncora, certifique-se de colocar o Regex usando aspas simples ( `'` ) em vez de aspas duplas ( `"` ) ou o PowerShell expandirá a expressão como uma variável.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-178">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="a2f2c-179">Ao usar âncoras no PowerShell, você deve entender a diferença entre as opções de expressão única de linhas **simples** e de **multilinha** .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-179">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="a2f2c-180">**Multiline** : o modo multilinha força `^` e `$` corresponde à extremidade inicial de cada linha em vez do início e do fim da cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-180">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="a2f2c-181">**Unificação** : o modo de única trata a cadeia de caracteres de entrada como uma **única** .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-181">**Singleline** : Singleline mode treats the input string as a **SingleLine** .</span></span>
  <span data-ttu-id="a2f2c-182">Ele força o `.` caractere a corresponder a cada caractere (incluindo novas linhas), em vez de corresponder a cada caractere, exceto a nova linha `\n` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-182">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="a2f2c-183">Para ler mais sobre essas opções e como usá-las, visite a [linguagem de expressão regular-referência rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-183">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="a2f2c-184">Caracteres de escape</span><span class="sxs-lookup"><span data-stu-id="a2f2c-184">Escaping characters</span></span>

<span data-ttu-id="a2f2c-185">A barra invertida ( `\` ) é usada para escapar caracteres para que eles não sejam analisados pelo mecanismo de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-185">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="a2f2c-186">Os seguintes caracteres são reservados: `[]().\^$|?*+{}` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-186">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="a2f2c-187">Você precisará escapar desses caracteres em seus padrões para que correspondam a eles nas cadeias de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-187">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="a2f2c-188">Há um método estático da classe Regex que pode escapar do texto para você.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-188">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="a2f2c-189">Isso escapa todos os caracteres de expressão regular reservados, incluindo barras invertidas existentes usadas em classes de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-189">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="a2f2c-190">Certifique-se de usá-lo apenas na parte do padrão que você precisa escapar.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-190">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="a2f2c-191">Outros escapes de caractere</span><span class="sxs-lookup"><span data-stu-id="a2f2c-191">Other character escapes</span></span>

<span data-ttu-id="a2f2c-192">Também há escapes de caractere reservado que você pode usar para corresponder a tipos de caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-192">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="a2f2c-193">A seguir estão alguns escapes de caractere usados com frequência:</span><span class="sxs-lookup"><span data-stu-id="a2f2c-193">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="a2f2c-194">Escape de caractere</span><span class="sxs-lookup"><span data-stu-id="a2f2c-194">Character Escape</span></span>  |<span data-ttu-id="a2f2c-195">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2f2c-195">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="a2f2c-196">Corresponde a uma tabulação</span><span class="sxs-lookup"><span data-stu-id="a2f2c-196">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="a2f2c-197">Corresponde a uma nova linha</span><span class="sxs-lookup"><span data-stu-id="a2f2c-197">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="a2f2c-198">Corresponde a um retorno de carro</span><span class="sxs-lookup"><span data-stu-id="a2f2c-198">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="a2f2c-199">Grupos, capturas e substituições</span><span class="sxs-lookup"><span data-stu-id="a2f2c-199">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="a2f2c-200">O agrupamento de construções separa uma cadeia de caracteres de entrada em subcadeias de caracteres que podem ser capturadas ou ignoradas.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-200">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="a2f2c-201">Subcadeias de caracteres agrupadas são chamadas de subexpressões.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-201">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="a2f2c-202">Por padrão, as subexpressões são capturadas em grupos numerados, embora você também possa atribuir nomes a elas.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-202">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="a2f2c-203">Uma construção de agrupamento é uma expressão regular entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-203">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="a2f2c-204">Qualquer texto correspondido pela expressão regular embutida é capturado.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-204">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="a2f2c-205">O exemplo a seguir quebrará o texto de entrada em dois grupos de captura.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-205">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="a2f2c-206">Use a `$Matches` variável automática **Hashtable** para recuperar o texto capturado.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-206">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="a2f2c-207">O texto que representa a correspondência inteira é armazenado na chave `0` .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-207">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="a2f2c-208">As capturas são armazenadas em chaves de **inteiro** numéricos que aumentam da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-208">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="a2f2c-209">A captura `1` contém todo o texto até que o nome de usuário, Capture `2` contenha apenas o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-209">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

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
> <span data-ttu-id="a2f2c-210">A `0` chave é um **número inteiro** .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-210">The `0` key is an **Integer** .</span></span> <span data-ttu-id="a2f2c-211">Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-211">You can use any **Hashtable** method to access the value stored.</span></span>
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

#### <a name="named-captures"></a><span data-ttu-id="a2f2c-212">Capturas nomeadas</span><span class="sxs-lookup"><span data-stu-id="a2f2c-212">Named Captures</span></span>

<span data-ttu-id="a2f2c-213">Por padrão, as capturas são armazenadas em ordem numérica crescente, da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-213">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="a2f2c-214">Você também pode atribuir um **nome** a um grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-214">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="a2f2c-215">Esse **nome** se torna uma chave na `$Matches` variável automática de **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-215">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="a2f2c-216">Dentro de um grupo de captura, use `?<keyname>` para armazenar dados capturados em uma chave nomeada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-216">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

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

<span data-ttu-id="a2f2c-217">O exemplo a seguir armazena o **SuccessAudit** mais recente do log de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-217">The following example stores the latest **SuccessAudit** from the Windows Security Log.</span></span> <span data-ttu-id="a2f2c-218">A expressão regular fornecida extrai o nome de usuário e o domínio da mensagem e os armazena sob as chaves: **N** para nome e **D** para o domínio.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-218">The provided regular expression extracts the username and domain from the message and stores them under the keys: **N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-EventLog -LogName Security -Newest 1 -InstanceId 4689).message
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

<span data-ttu-id="a2f2c-219">Para obter mais informações, consulte [agrupando construções em expressões regulares](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-219">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="a2f2c-220">Substituições em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="a2f2c-220">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="a2f2c-221">Usar as expressões regulares com o `-replace` operador permite que você substitua dinamicamente o texto usando o texto capturado.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-221">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="a2f2c-222">`<input>`: A cadeia de caracteres a ser pesquisada</span><span class="sxs-lookup"><span data-stu-id="a2f2c-222">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="a2f2c-223">`<original>`: Uma expressão regular usada para pesquisar a cadeia de caracteres de entrada</span><span class="sxs-lookup"><span data-stu-id="a2f2c-223">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="a2f2c-224">`<substitute>`: Uma expressão de substituição de expressão regular para substituir as correspondências encontradas na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-224">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f2c-225">Os `<original>` `<substitute>` operandos e estão sujeitos às regras do mecanismo de expressão regular, como saída de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-225">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="a2f2c-226">Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-226">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="a2f2c-227">A substituição é feita usando o `$` caractere antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-227">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="a2f2c-228">Duas maneiras de fazer referência a grupos de captura são por **número** e por **nome** .</span><span class="sxs-lookup"><span data-stu-id="a2f2c-228">Two ways to reference capturing groups are by **Number** and by **Name** .</span></span>

- <span data-ttu-id="a2f2c-229">Por grupos de captura de **número** , são numerados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-229">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="a2f2c-230">Os grupos de captura de **nomes** também podem ser referenciados pelo nome.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-230">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="a2f2c-231">A `$&` expressão representa todo o texto correspondido.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-231">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="a2f2c-232">Como o `$` caractere é usado na expansão da cadeia de caracteres, você precisará usar cadeias literais com substituição ou escapar o `$` caractere ao usar aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-232">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
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
> <span data-ttu-id="a2f2c-233">Além disso, se você quiser ter o `$` como um caractere literal, use `$$` em vez dos caracteres de escape normais.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-233">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="a2f2c-234">Ao usar aspas duplas, ainda escapar de todas as instâncias do `$` para evitar a substituição incorreta.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-234">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
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

<span data-ttu-id="a2f2c-235">Para obter mais informações, consulte [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-235">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2f2c-236">Confira também</span><span class="sxs-lookup"><span data-stu-id="a2f2c-236">See also</span></span>

[<span data-ttu-id="a2f2c-237">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="a2f2c-237">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="a2f2c-238">about_Operators</span><span class="sxs-lookup"><span data-stu-id="a2f2c-238">about_Operators</span></span>](about_Operators.md)
