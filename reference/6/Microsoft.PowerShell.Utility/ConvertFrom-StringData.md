---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 8ffb7a33bb1b4b5409c48445b88a8eb58f9b93b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194524"
---
# <span data-ttu-id="b0912-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="b0912-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="b0912-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b0912-104">SYNOPSIS</span></span>
<span data-ttu-id="b0912-105">Converte uma cadeia de caracteres que contém um ou mais pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="b0912-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0912-106">SYNTAX</span></span>

### <span data-ttu-id="b0912-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="b0912-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## <span data-ttu-id="b0912-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0912-108">DESCRIPTION</span></span>

<span data-ttu-id="b0912-109">O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres que contém um ou mais pares de chave e valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="b0912-110">Como cada par chave-valor deve estar em uma linha separada, as cadeias de caracteres aqui são geralmente usadas como o formato de entrada.</span><span class="sxs-lookup"><span data-stu-id="b0912-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="b0912-111">Por padrão, a **chave** deve ser separada do **valor** por um caractere de sinal de igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="b0912-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="b0912-112">O `ConvertFrom-StringData` cmdlet é considerado um cmdlet seguro que pode ser usado na `DATA` seção de um script ou função.</span><span class="sxs-lookup"><span data-stu-id="b0912-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="b0912-113">Quando usado em uma `DATA` seção, o conteúdo da cadeia de caracteres deve estar de acordo com as regras para uma seção de dados.</span><span class="sxs-lookup"><span data-stu-id="b0912-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="b0912-114">Para obter mais informações, consulte [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="b0912-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="b0912-115">`ConvertFrom-StringData` dá suporte a sequências de caracteres de escape que são permitidas pelas ferramentas convencionais de tradução automática.</span><span class="sxs-lookup"><span data-stu-id="b0912-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="b0912-116">Ou seja, o cmdlet pode interpretar barras invertidas ( `\` ) como caracteres de escape nos dados da cadeia de caracteres usando o [método Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape), em vez do caractere de barra () do PowerShell \` que normalmente sinalizaria o final de uma linha em um script.</span><span class="sxs-lookup"><span data-stu-id="b0912-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="b0912-117">Dentro da cadeia de caracteres here, o caractere de acento grave não funciona.</span><span class="sxs-lookup"><span data-stu-id="b0912-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="b0912-118">Você também pode preservar uma barra invertida literal em seus resultados, recortando-a com uma barra invertida precedente, desta forma: `\\` .</span><span class="sxs-lookup"><span data-stu-id="b0912-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="b0912-119">Caracteres de barra invertida sem escape, como aqueles que geralmente são usados em caminhos de arquivo, podem ser processados como sequências de escape ilegais em seus resultados.</span><span class="sxs-lookup"><span data-stu-id="b0912-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

## <span data-ttu-id="b0912-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b0912-120">EXAMPLES</span></span>

### <span data-ttu-id="b0912-121">Exemplo 1: converter uma cadeia de caracteres here entre aspas simples em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="b0912-121">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="b0912-122">Este exemplo converte uma cadeia de caracteres aqui entre aspas simples de mensagens de usuário em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-122">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="b0912-123">Em uma cadeia de caracteres entre aspas simples, os valores não são substituídos por variáveis e as expressões não são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="b0912-123">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="b0912-124">O `ConvertFrom-StringData` cmdlet converte o valor na `$Here` variável em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-124">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="b0912-125">Exemplo 2: converter uma cadeia de caracteres aqui contendo um comentário</span><span class="sxs-lookup"><span data-stu-id="b0912-125">Example 2: Convert a here-string containing a comment</span></span>

<span data-ttu-id="b0912-126">Este exemplo converte uma cadeia de caracteres aqui que contém um comentário e vários pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-126">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="b0912-127">O valor do parâmetro **StringData** é uma cadeia de caracteres here, em vez de uma variável que contém uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="b0912-127">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="b0912-128">Qualquer um dos dois formatos é válido.</span><span class="sxs-lookup"><span data-stu-id="b0912-128">Either format is valid.</span></span> <span data-ttu-id="b0912-129">A cadeia de caracteres here inclui um comentário sobre uma das cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b0912-129">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="b0912-130">`ConvertFrom-StringData` ignora comentários de linha única, mas o `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="b0912-130">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="b0912-131">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="b0912-131">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="b0912-132">Exemplo 3: converter uma cadeia de caracteres em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="b0912-132">Example 3: Convert a string to a hash table</span></span>

<span data-ttu-id="b0912-133">Este exemplo converte uma cadeia de caracteres entre aspas duplas (não uma cadeia de caracteres aqui) em uma tabela de hash e a salva na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="b0912-133">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="b0912-134">Para satisfazer a condição de que cada par chave-valor deve estar em uma linha separada, a cadeia de caracteres usa o caractere de nova linha ( \` n) do PowerShell para separar os pares.</span><span class="sxs-lookup"><span data-stu-id="b0912-134">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="b0912-135">Exemplo 4: usar ConvertFrom-StringData na seção de dados de um script</span><span class="sxs-lookup"><span data-stu-id="b0912-135">Example 4: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="b0912-136">Este exemplo mostra um `ConvertFrom-StringData` comando usado na seção de dados de um script.</span><span class="sxs-lookup"><span data-stu-id="b0912-136">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="b0912-137">As instruções abaixo da seção DATA exibem o texto para o usuário.</span><span class="sxs-lookup"><span data-stu-id="b0912-137">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="b0912-138">Já que o texto inclui nomes de variáveis, ele deve ser colocado em uma cadeia de caracteres entre aspas simples, de modo que as variáveis sejam interpretadas literalmente e não expandidas.</span><span class="sxs-lookup"><span data-stu-id="b0912-138">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="b0912-139">Não são permitidas variáveis na seção **Data** .</span><span class="sxs-lookup"><span data-stu-id="b0912-139">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="b0912-140">Exemplo 5: usar o operador de pipeline para passar uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b0912-140">Example 5: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="b0912-141">Este exemplo mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="b0912-141">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="b0912-142">O valor da `$Here` variável é canalizado para `ConvertFrom-StringData` e o resultado na `$Hash` variável.</span><span class="sxs-lookup"><span data-stu-id="b0912-142">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="b0912-143">Exemplo 6: usar caracteres de escape para adicionar novas linhas e caracteres de retorno</span><span class="sxs-lookup"><span data-stu-id="b0912-143">Example 6: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="b0912-144">Este exemplo mostra o uso de caracteres de escape para criar novas linhas e caracteres de retorno em dados de origem.</span><span class="sxs-lookup"><span data-stu-id="b0912-144">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="b0912-145">A sequência de escape `\n` é usada para criar novas linhas dentro de um bloco de texto associado a um nome ou item na tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="b0912-145">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="b0912-146">Exemplo 7: usar o caractere de escape de barra invertida para renderizar corretamente um caminho de arquivo</span><span class="sxs-lookup"><span data-stu-id="b0912-146">Example 7: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="b0912-147">Este exemplo mostra como usar o caractere de escape de barra invertida nos dados de cadeia de caracteres para permitir que um caminho de arquivo seja renderizado corretamente na `ConvertFrom-StringData` tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="b0912-147">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="b0912-148">As duas barras invertidas garantem que os caracteres de barra invertida literal sejam processados corretamente na saída da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-148">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="b0912-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0912-149">PARAMETERS</span></span>

### <span data-ttu-id="b0912-150">-StringData</span><span class="sxs-lookup"><span data-stu-id="b0912-150">-StringData</span></span>

<span data-ttu-id="b0912-151">Especifica a cadeia de caracteres a ser convertida.</span><span class="sxs-lookup"><span data-stu-id="b0912-151">Specifies the string to be converted.</span></span> <span data-ttu-id="b0912-152">Você pode usar esse parâmetro ou canalizar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="b0912-152">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="b0912-153">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="b0912-153">The parameter name is optional.</span></span>

<span data-ttu-id="b0912-154">O valor desse parâmetro deve ser uma cadeia de caracteres que contenha um ou mais pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="b0912-154">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="b0912-155">Cada par chave-valor deve estar em uma linha separada, ou cada par deve ser separado por caracteres de nova linha ( \` n).</span><span class="sxs-lookup"><span data-stu-id="b0912-155">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="b0912-156">Você pode incluir comentários na cadeia de caracteres, mas os comentários não podem estar na mesma linha que um par chave-valor.</span><span class="sxs-lookup"><span data-stu-id="b0912-156">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="b0912-157">`ConvertFrom-StringData` ignora comentários de linha única.</span><span class="sxs-lookup"><span data-stu-id="b0912-157">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="b0912-158">O `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="b0912-158">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="b0912-159">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="b0912-159">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="b0912-160">Os comentários não são incluídos na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b0912-160">The comments are not included in the hash table.</span></span>

<span data-ttu-id="b0912-161">Uma cadeia de caracteres aqui é uma cadeia de caracteres que consiste em uma ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="b0912-161">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="b0912-162">As aspas na cadeia de caracteres aqui são interpretadas literalmente como parte dos dados da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b0912-162">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="b0912-163">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b0912-163">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b0912-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b0912-164">CommonParameters</span></span>

<span data-ttu-id="b0912-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0912-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0912-166">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b0912-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b0912-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b0912-167">INPUTS</span></span>

### <span data-ttu-id="b0912-168">System.String</span><span class="sxs-lookup"><span data-stu-id="b0912-168">System.String</span></span>

<span data-ttu-id="b0912-169">É possível canalizar uma cadeia de caracteres que contém um par chave-valor para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="b0912-169">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="b0912-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b0912-170">OUTPUTS</span></span>

### <span data-ttu-id="b0912-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="b0912-171">System.Collections.Hashtable</span></span>

<span data-ttu-id="b0912-172">Esse cmdlet retorna uma tabela de hash que ele cria a partir dos pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="b0912-172">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="b0912-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b0912-173">NOTES</span></span>

<span data-ttu-id="b0912-174">Uma cadeia de caracteres here é uma cadeia de caracteres com uma ou mais linhas, nas quais as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="b0912-174">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="b0912-175">Esse cmdlet pode ser útil em scripts que exibem mensagens do usuário em vários idiomas falados.</span><span class="sxs-lookup"><span data-stu-id="b0912-175">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="b0912-176">Você pode usar as tabelas de hash em estilo de dicionário para isolar as cadeias de caracteres de texto do código como ocorre em arquivos de recursos, além de formatar as cadeias de caracteres de texto para uso em ferramentas de tradução.</span><span class="sxs-lookup"><span data-stu-id="b0912-176">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="b0912-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b0912-177">RELATED LINKS</span></span>
