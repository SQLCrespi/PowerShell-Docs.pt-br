---
description: Descreve regras para usar aspas simples e duplas no PowerShell.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: b100ff8ab4be84b7117efc5724119221351ba4bf
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490662"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="a8278-103">Sobre regras de cotação</span><span class="sxs-lookup"><span data-stu-id="a8278-103">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="a8278-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a8278-104">Short description</span></span>
<span data-ttu-id="a8278-105">Descreve regras para usar aspas simples e duplas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8278-105">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a8278-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a8278-106">Long description</span></span>

<span data-ttu-id="a8278-107">Aspas são usadas para especificar uma cadeia de caracteres literal.</span><span class="sxs-lookup"><span data-stu-id="a8278-107">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="a8278-108">Você pode colocar uma cadeia de caracteres entre aspas simples ( `'` ) ou aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="a8278-108">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="a8278-109">Aspas também são usadas para criar uma _cadeia de caracteres aqui_.</span><span class="sxs-lookup"><span data-stu-id="a8278-109">Quotation marks are also used to create a _here-string_.</span></span> <span data-ttu-id="a8278-110">Uma cadeia de caracteres aqui é uma cadeia de caracteres entre aspas simples ou com aspas duplas em que as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="a8278-110">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="a8278-111">Uma cadeia de caracteres aqui pode abranger várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a8278-111">A here-string can span multiple lines.</span></span> <span data-ttu-id="a8278-112">Todas as linhas em uma cadeia de caracteres aqui são interpretadas como cadeias de caracteres, mesmo que não sejam colocadas entre aspas.</span><span class="sxs-lookup"><span data-stu-id="a8278-112">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="a8278-113">Em comandos para computadores remotos, aspas definem as partes do comando que são executadas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a8278-113">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="a8278-114">Em uma sessão remota, as aspas também determinam se as variáveis em um comando são interpretadas primeiro no computador local ou no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a8278-114">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

## <a name="single-and-double-quoted-strings"></a><span data-ttu-id="a8278-115">Cadeias de caracteres de aspas simples e duplas</span><span class="sxs-lookup"><span data-stu-id="a8278-115">Single and double-quoted strings</span></span>

<span data-ttu-id="a8278-116">Uma cadeia de caracteres entre aspas duplas é uma cadeia de caracteres _expansível_ .</span><span class="sxs-lookup"><span data-stu-id="a8278-116">A string enclosed in double quotation marks is an _expandable_ string.</span></span> <span data-ttu-id="a8278-117">Os nomes de variáveis precedidos por um cifrão ( `$` ) são substituídos pelo valor da variável antes que a cadeia de caracteres seja passada para o comando para processamento.</span><span class="sxs-lookup"><span data-stu-id="a8278-117">Variable names preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="a8278-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="a8278-119">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="a8278-120">Além disso, em uma cadeia de caracteres com aspas duplas, as expressões são avaliadas e o resultado é inserido na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a8278-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="a8278-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="a8278-122">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="a8278-123">Uma cadeia de caracteres entre aspas simples é uma cadeia de caracteres _textual_ .</span><span class="sxs-lookup"><span data-stu-id="a8278-123">A string enclosed in single-quotation marks is a _verbatim_ string.</span></span> <span data-ttu-id="a8278-124">A cadeia de caracteres é passada para o comando exatamente conforme você o digita.</span><span class="sxs-lookup"><span data-stu-id="a8278-124">The string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="a8278-125">Nenhuma substituição é executada.</span><span class="sxs-lookup"><span data-stu-id="a8278-125">No substitution is performed.</span></span>
<span data-ttu-id="a8278-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-126">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="a8278-127">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-127">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="a8278-128">Da mesma forma, as expressões em cadeias de caracteres entre aspas simples não são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="a8278-128">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="a8278-129">Eles são interpretados como literais.</span><span class="sxs-lookup"><span data-stu-id="a8278-129">They are interpreted as literals.</span></span> <span data-ttu-id="a8278-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-130">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="a8278-131">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-131">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="a8278-132">Para evitar a substituição de um valor de variável em uma cadeia de caracteres com aspas duplas, use o caractere de acento grave ( `` ` `` ) (ASCII 96), que é o caractere de escape do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8278-132">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="a8278-133">No exemplo a seguir, o caractere de acento grave que precede a primeira `$i` variável impede que o PowerShell substitua o nome da variável por seu valor.</span><span class="sxs-lookup"><span data-stu-id="a8278-133">In the following example, the backtick character that precedes the first `$i` variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="a8278-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-134">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="a8278-135">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-135">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="a8278-136">Para que as aspas duplas apareçam em uma cadeia de caracteres, coloque a cadeia de caracteres inteira entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="a8278-136">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="a8278-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-137">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="a8278-138">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-138">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="a8278-139">Você também pode colocar uma cadeia de caracteres entre aspas simples em uma cadeia de caracteres com aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="a8278-139">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="a8278-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-140">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="a8278-141">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-141">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="a8278-142">Ou, clique duas vezes nas aspas ao contrário de uma frase entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="a8278-142">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="a8278-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-143">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="a8278-144">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-144">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="a8278-145">Para incluir uma aspa simples em uma cadeia de caracteres entre aspas simples, use uma segunda aspa simples consecutiva.</span><span class="sxs-lookup"><span data-stu-id="a8278-145">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="a8278-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-146">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="a8278-147">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-147">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="a8278-148">Para forçar o PowerShell a interpretar uma aspa dupla literalmente, use um caractere de acento grave.</span><span class="sxs-lookup"><span data-stu-id="a8278-148">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="a8278-149">Isso impede que o PowerShell interprete a aspa como um delimitador de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a8278-149">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="a8278-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-150">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="a8278-151">Como o conteúdo das cadeias de caracteres entre aspas simples é interpretado literalmente, o caractere de acento grave é tratado como um caractere literal e exibido na saída.</span><span class="sxs-lookup"><span data-stu-id="a8278-151">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

## <a name="here-strings"></a><span data-ttu-id="a8278-152">Aqui-cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="a8278-152">Here-strings</span></span>

<span data-ttu-id="a8278-153">As regras de cotação para as cadeias de caracteres aqui são um pouco diferentes.</span><span class="sxs-lookup"><span data-stu-id="a8278-153">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="a8278-154">Uma cadeia de caracteres aqui é uma cadeia de caracteres entre aspas simples ou com aspas duplas em que as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="a8278-154">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="a8278-155">Uma cadeia de caracteres aqui pode abranger várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a8278-155">A here-string can span multiple lines.</span></span> <span data-ttu-id="a8278-156">Todas as linhas em uma cadeia de caracteres aqui são interpretadas como cadeias de texto, mesmo que não sejam colocadas entre aspas.</span><span class="sxs-lookup"><span data-stu-id="a8278-156">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="a8278-157">Como cadeias de caracteres regulares, as variáveis são substituídas por seus valores em cadeias de caracteres aqui com aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="a8278-157">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="a8278-158">Em cadeias de caracteres aqui entre aspas simples, as variáveis não são substituídas por seus valores.</span><span class="sxs-lookup"><span data-stu-id="a8278-158">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="a8278-159">Você pode usar as cadeias de caracteres aqui para qualquer texto, mas elas são particularmente úteis para os seguintes tipos de texto:</span><span class="sxs-lookup"><span data-stu-id="a8278-159">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="a8278-160">Texto que contém aspas literais</span><span class="sxs-lookup"><span data-stu-id="a8278-160">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="a8278-161">Várias linhas de texto, como o texto em um HTML ou XML</span><span class="sxs-lookup"><span data-stu-id="a8278-161">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="a8278-162">O texto de ajuda para um documento de script ou função</span><span class="sxs-lookup"><span data-stu-id="a8278-162">The Help text for a script or function document</span></span>

<span data-ttu-id="a8278-163">Uma cadeia de caracteres here pode ter qualquer um dos formatos a seguir, onde `<Enter>` representa o caractere oculto de linhagem ou novas linhas que é adicionado quando você pressiona a tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="a8278-163">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="a8278-164">Aspas duplas:</span><span class="sxs-lookup"><span data-stu-id="a8278-164">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="a8278-165">Aspas simples:</span><span class="sxs-lookup"><span data-stu-id="a8278-165">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="a8278-166">Em qualquer formato, a aspa de fechamento deve ser o primeiro caractere na linha.</span><span class="sxs-lookup"><span data-stu-id="a8278-166">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="a8278-167">Uma cadeia de caracteres aqui contém todo o texto entre os dois caracteres ocultos.</span><span class="sxs-lookup"><span data-stu-id="a8278-167">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="a8278-168">Na cadeia de caracteres here, todas as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="a8278-168">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="a8278-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-169">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="a8278-170">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-170">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="a8278-171">O uso de uma cadeia de caracteres aqui pode simplificar o uso de uma cadeia de caracteres em um comando.</span><span class="sxs-lookup"><span data-stu-id="a8278-171">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="a8278-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-172">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="a8278-173">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-173">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="a8278-174">Em cadeias de caracteres aqui entre aspas simples, as variáveis são interpretadas literalmente e reproduzidas exatamente.</span><span class="sxs-lookup"><span data-stu-id="a8278-174">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="a8278-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-175">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="a8278-176">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-176">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="a8278-177">Em cadeias de caracteres com aspas duplas, as variáveis são substituídas por seus valores.</span><span class="sxs-lookup"><span data-stu-id="a8278-177">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="a8278-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8278-178">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="a8278-179">A saída desse comando é:</span><span class="sxs-lookup"><span data-stu-id="a8278-179">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="a8278-180">Aqui – as cadeias de caracteres normalmente são usadas para atribuir várias linhas a uma variável.</span><span class="sxs-lookup"><span data-stu-id="a8278-180">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="a8278-181">Por exemplo, a cadeia de caracteres aqui a seguir atribui uma página de XML à variável $page.</span><span class="sxs-lookup"><span data-stu-id="a8278-181">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

<span data-ttu-id="a8278-182">Aqui-as cadeias de caracteres também são um formato conveniente para entrada para o `ConvertFrom-StringData` cmdlet, que converte as cadeias de caracteres aqui em tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="a8278-182">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="a8278-183">Para obter mais informações, consulte `ConvertFrom-StringData`.</span><span class="sxs-lookup"><span data-stu-id="a8278-183">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8278-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="a8278-184">See also</span></span>

[<span data-ttu-id="a8278-185">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="a8278-185">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="a8278-186">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="a8278-186">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
