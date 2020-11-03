---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: a5f65a70ccb97db5338456cca50309b593b900c1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193046"
---
# <span data-ttu-id="7d50e-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="7d50e-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="7d50e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7d50e-104">SYNOPSIS</span></span>
<span data-ttu-id="7d50e-105">Converte uma cadeia de caracteres que contém um ou mais pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="7d50e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d50e-106">SYNTAX</span></span>

### <span data-ttu-id="7d50e-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="7d50e-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [[-Delimiter] <Char>] [<CommonParameters>]
```

## <span data-ttu-id="7d50e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7d50e-108">DESCRIPTION</span></span>

<span data-ttu-id="7d50e-109">O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres que contém um ou mais pares de chave e valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="7d50e-110">Como cada par chave-valor deve estar em uma linha separada, as cadeias de caracteres aqui são geralmente usadas como o formato de entrada.</span><span class="sxs-lookup"><span data-stu-id="7d50e-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="7d50e-111">Por padrão, a **chave** deve ser separada do **valor** por um caractere de sinal de igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="7d50e-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="7d50e-112">O `ConvertFrom-StringData` cmdlet é considerado um cmdlet seguro que pode ser usado na `DATA` seção de um script ou função.</span><span class="sxs-lookup"><span data-stu-id="7d50e-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="7d50e-113">Quando usado em uma `DATA` seção, o conteúdo da cadeia de caracteres deve estar de acordo com as regras para uma seção de dados.</span><span class="sxs-lookup"><span data-stu-id="7d50e-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="7d50e-114">Para obter mais informações, consulte [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="7d50e-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="7d50e-115">`ConvertFrom-StringData` dá suporte a sequências de caracteres de escape que são permitidas pelas ferramentas convencionais de tradução automática.</span><span class="sxs-lookup"><span data-stu-id="7d50e-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="7d50e-116">Ou seja, o cmdlet pode interpretar barras invertidas ( `\` ) como caracteres de escape nos dados da cadeia de caracteres usando o [método Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape), em vez do caractere de barra () do PowerShell \` que normalmente sinalizaria o final de uma linha em um script.</span><span class="sxs-lookup"><span data-stu-id="7d50e-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="7d50e-117">Dentro da cadeia de caracteres here, o caractere de acento grave não funciona.</span><span class="sxs-lookup"><span data-stu-id="7d50e-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="7d50e-118">Você também pode preservar uma barra invertida literal em seus resultados, recortando-a com uma barra invertida precedente, desta forma: `\\` .</span><span class="sxs-lookup"><span data-stu-id="7d50e-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="7d50e-119">Caracteres de barra invertida sem escape, como aqueles que geralmente são usados em caminhos de arquivo, podem ser processados como sequências de escape ilegais em seus resultados.</span><span class="sxs-lookup"><span data-stu-id="7d50e-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

<span data-ttu-id="7d50e-120">O PowerShell 7 adiciona o parâmetro **delimitador** .</span><span class="sxs-lookup"><span data-stu-id="7d50e-120">PowerShell 7 adds the **Delimiter** parameter.</span></span>

## <span data-ttu-id="7d50e-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7d50e-121">EXAMPLES</span></span>

### <span data-ttu-id="7d50e-122">Exemplo 1: converter uma cadeia de caracteres here entre aspas simples em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="7d50e-122">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="7d50e-123">Este exemplo converte uma cadeia de caracteres aqui entre aspas simples de mensagens de usuário em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-123">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="7d50e-124">Em uma cadeia de caracteres entre aspas simples, os valores não são substituídos por variáveis e as expressões não são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="7d50e-124">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="7d50e-125">O `ConvertFrom-StringData` cmdlet converte o valor na `$Here` variável em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-125">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

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

### <span data-ttu-id="7d50e-126">Exemplo 2: converter dados de cadeia de caracteres usando um delimitador diferente</span><span class="sxs-lookup"><span data-stu-id="7d50e-126">Example 2: Convert string data using a different delimiter</span></span>

<span data-ttu-id="7d50e-127">Este exemplo mostra como converter dados de cadeia de caracteres que usam um caractere diferente como um delimitador.</span><span class="sxs-lookup"><span data-stu-id="7d50e-127">This example shows how to convert string data that uses a different character as a delimiter.</span></span> <span data-ttu-id="7d50e-128">Neste exemplo, os dados de cadeia de caracteres estão usando o caractere de barra vertical ( `|` ) como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="7d50e-128">In this example the string data is using the pipe character (`|`) as the delimiter.</span></span>

```powershell
$StringData = @'
color|red
model|coupe
year|1965
condition|mint
'@
$carData = ConvertFrom-StringData -StringData $StringData -Delimiter '|'
$carData
```

```Output
Name                           Value
----                           -----
condition                      mint
model                          coupe
color                          red
year                           1965
```

### <span data-ttu-id="7d50e-129">Exemplo 3: converter uma cadeia de caracteres aqui contendo um comentário</span><span class="sxs-lookup"><span data-stu-id="7d50e-129">Example 3: Convert a here-string containing a comment</span></span>

<span data-ttu-id="7d50e-130">Este exemplo converte uma cadeia de caracteres aqui que contém um comentário e vários pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-130">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

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

<span data-ttu-id="7d50e-131">O valor do parâmetro **StringData** é uma cadeia de caracteres here, em vez de uma variável que contém uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="7d50e-131">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="7d50e-132">Qualquer um dos dois formatos é válido.</span><span class="sxs-lookup"><span data-stu-id="7d50e-132">Either format is valid.</span></span> <span data-ttu-id="7d50e-133">A cadeia de caracteres here inclui um comentário sobre uma das cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7d50e-133">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="7d50e-134">`ConvertFrom-StringData` ignora comentários de linha única, mas o `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="7d50e-134">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="7d50e-135">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="7d50e-135">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="7d50e-136">Exemplo 4: converter uma cadeia de caracteres em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="7d50e-136">Example 4: Convert a string to a hash table</span></span>

<span data-ttu-id="7d50e-137">Este exemplo converte uma cadeia de caracteres entre aspas duplas (não uma cadeia de caracteres aqui) em uma tabela de hash e a salva na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="7d50e-137">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

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

<span data-ttu-id="7d50e-138">Para satisfazer a condição de que cada par chave-valor deve estar em uma linha separada, a cadeia de caracteres usa o caractere de nova linha ( \` n) do PowerShell para separar os pares.</span><span class="sxs-lookup"><span data-stu-id="7d50e-138">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="7d50e-139">Exemplo 5: usar ConvertFrom-StringData na seção de dados de um script</span><span class="sxs-lookup"><span data-stu-id="7d50e-139">Example 5: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="7d50e-140">Este exemplo mostra um `ConvertFrom-StringData` comando usado na seção de dados de um script.</span><span class="sxs-lookup"><span data-stu-id="7d50e-140">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="7d50e-141">As instruções abaixo da seção DATA exibem o texto para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7d50e-141">The statements below the DATA section display the text to the user.</span></span>

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

<span data-ttu-id="7d50e-142">Já que o texto inclui nomes de variáveis, ele deve ser colocado em uma cadeia de caracteres entre aspas simples, de modo que as variáveis sejam interpretadas literalmente e não expandidas.</span><span class="sxs-lookup"><span data-stu-id="7d50e-142">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="7d50e-143">Não são permitidas variáveis na seção **Data** .</span><span class="sxs-lookup"><span data-stu-id="7d50e-143">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="7d50e-144">Exemplo 6: usar o operador de pipeline para passar uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7d50e-144">Example 6: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="7d50e-145">Este exemplo mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="7d50e-145">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="7d50e-146">O valor da `$Here` variável é canalizado para `ConvertFrom-StringData` e o resultado na `$Hash` variável.</span><span class="sxs-lookup"><span data-stu-id="7d50e-146">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

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

### <span data-ttu-id="7d50e-147">Exemplo 7: usar caracteres de escape para adicionar novas linhas e caracteres de retorno</span><span class="sxs-lookup"><span data-stu-id="7d50e-147">Example 7: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="7d50e-148">Este exemplo mostra o uso de caracteres de escape para criar novas linhas e caracteres de retorno em dados de origem.</span><span class="sxs-lookup"><span data-stu-id="7d50e-148">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="7d50e-149">A sequência de escape `\n` é usada para criar novas linhas dentro de um bloco de texto associado a um nome ou item na tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="7d50e-149">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

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

### <span data-ttu-id="7d50e-150">Exemplo 8: usar o caractere de escape de barra invertida para renderizar corretamente um caminho de arquivo</span><span class="sxs-lookup"><span data-stu-id="7d50e-150">Example 8: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="7d50e-151">Este exemplo mostra como usar o caractere de escape de barra invertida nos dados de cadeia de caracteres para permitir que um caminho de arquivo seja renderizado corretamente na `ConvertFrom-StringData` tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="7d50e-151">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="7d50e-152">As duas barras invertidas garantem que os caracteres de barra invertida literal sejam processados corretamente na saída da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-152">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="7d50e-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d50e-153">PARAMETERS</span></span>

### <span data-ttu-id="7d50e-154">-StringData</span><span class="sxs-lookup"><span data-stu-id="7d50e-154">-StringData</span></span>

<span data-ttu-id="7d50e-155">Especifica a cadeia de caracteres a ser convertida.</span><span class="sxs-lookup"><span data-stu-id="7d50e-155">Specifies the string to be converted.</span></span> <span data-ttu-id="7d50e-156">Você pode usar esse parâmetro ou canalizar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="7d50e-156">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="7d50e-157">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="7d50e-157">The parameter name is optional.</span></span>

<span data-ttu-id="7d50e-158">O valor desse parâmetro deve ser uma cadeia de caracteres que contenha um ou mais pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="7d50e-158">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="7d50e-159">Cada par chave-valor deve estar em uma linha separada, ou cada par deve ser separado por caracteres de nova linha ( \` n).</span><span class="sxs-lookup"><span data-stu-id="7d50e-159">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="7d50e-160">Você pode incluir comentários na cadeia de caracteres, mas os comentários não podem estar na mesma linha que um par chave-valor.</span><span class="sxs-lookup"><span data-stu-id="7d50e-160">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="7d50e-161">`ConvertFrom-StringData` ignora comentários de linha única.</span><span class="sxs-lookup"><span data-stu-id="7d50e-161">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="7d50e-162">O `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="7d50e-162">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="7d50e-163">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="7d50e-163">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="7d50e-164">Os comentários não são incluídos na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="7d50e-164">The comments are not included in the hash table.</span></span>

<span data-ttu-id="7d50e-165">Uma cadeia de caracteres aqui é uma cadeia de caracteres que consiste em uma ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="7d50e-165">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="7d50e-166">As aspas na cadeia de caracteres aqui são interpretadas literalmente como parte dos dados da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7d50e-166">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="7d50e-167">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="7d50e-167">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7d50e-168">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="7d50e-168">-Delimiter</span></span>

<span data-ttu-id="7d50e-169">O caractere usado para separar a **chave** dos dados de **valor** na cadeia de caracteres que está sendo convertida.</span><span class="sxs-lookup"><span data-stu-id="7d50e-169">The character used to separate the **key** from the **value** data in the string being converted.</span></span>
<span data-ttu-id="7d50e-170">O delimitador padrão é o caractere de sinal de igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="7d50e-170">The default delimiter is the equals sign (`=`) character.</span></span> <span data-ttu-id="7d50e-171">Esse parâmetro foi adicionado no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="7d50e-171">This parameter was added in PowerShell 7.</span></span>

```yaml
Type: System.Char
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: '='
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d50e-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7d50e-172">CommonParameters</span></span>

<span data-ttu-id="7d50e-173">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d50e-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d50e-174">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="7d50e-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7d50e-175">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7d50e-175">INPUTS</span></span>

### <span data-ttu-id="7d50e-176">System.String</span><span class="sxs-lookup"><span data-stu-id="7d50e-176">System.String</span></span>

<span data-ttu-id="7d50e-177">É possível canalizar uma cadeia de caracteres que contém um par chave-valor para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="7d50e-177">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="7d50e-178">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7d50e-178">OUTPUTS</span></span>

### <span data-ttu-id="7d50e-179">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="7d50e-179">System.Collections.Hashtable</span></span>

<span data-ttu-id="7d50e-180">Esse cmdlet retorna uma tabela de hash que ele cria a partir dos pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="7d50e-180">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="7d50e-181">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7d50e-181">NOTES</span></span>

<span data-ttu-id="7d50e-182">Uma cadeia de caracteres here é uma cadeia de caracteres com uma ou mais linhas, nas quais as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="7d50e-182">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="7d50e-183">Esse cmdlet pode ser útil em scripts que exibem mensagens do usuário em vários idiomas falados.</span><span class="sxs-lookup"><span data-stu-id="7d50e-183">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="7d50e-184">Você pode usar as tabelas de hash em estilo de dicionário para isolar as cadeias de caracteres de texto do código como ocorre em arquivos de recursos, além de formatar as cadeias de caracteres de texto para uso em ferramentas de tradução.</span><span class="sxs-lookup"><span data-stu-id="7d50e-184">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="7d50e-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7d50e-185">RELATED LINKS</span></span>
