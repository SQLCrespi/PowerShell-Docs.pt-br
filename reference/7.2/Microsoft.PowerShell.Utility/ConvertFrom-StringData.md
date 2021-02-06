---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: c95ebca6307d58668c31faf3e492617f49ddebf4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599037"
---
# <span data-ttu-id="254f9-102">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="254f9-102">ConvertFrom-StringData</span></span>

## <span data-ttu-id="254f9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="254f9-103">SYNOPSIS</span></span>
<span data-ttu-id="254f9-104">Converte uma cadeia de caracteres que contém um ou mais pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-104">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="254f9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="254f9-105">SYNTAX</span></span>

### <span data-ttu-id="254f9-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="254f9-106">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [[-Delimiter] <Char>] [<CommonParameters>]
```

## <span data-ttu-id="254f9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="254f9-107">DESCRIPTION</span></span>

<span data-ttu-id="254f9-108">O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres que contém um ou mais pares de chave e valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-108">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="254f9-109">Como cada par chave-valor deve estar em uma linha separada, as cadeias de caracteres aqui são geralmente usadas como o formato de entrada.</span><span class="sxs-lookup"><span data-stu-id="254f9-109">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="254f9-110">Por padrão, a **chave** deve ser separada do **valor** por um caractere de sinal de igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="254f9-110">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="254f9-111">O `ConvertFrom-StringData` cmdlet é considerado um cmdlet seguro que pode ser usado na `DATA` seção de um script ou função.</span><span class="sxs-lookup"><span data-stu-id="254f9-111">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="254f9-112">Quando usado em uma `DATA` seção, o conteúdo da cadeia de caracteres deve estar de acordo com as regras para uma seção de dados.</span><span class="sxs-lookup"><span data-stu-id="254f9-112">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="254f9-113">Para obter mais informações, consulte [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="254f9-113">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="254f9-114">`ConvertFrom-StringData` dá suporte a sequências de caracteres de escape que são permitidas pelas ferramentas convencionais de tradução automática.</span><span class="sxs-lookup"><span data-stu-id="254f9-114">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="254f9-115">Ou seja, o cmdlet pode interpretar barras invertidas ( `\` ) como caracteres de escape nos dados da cadeia de caracteres usando o [método Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape), em vez do caractere de barra () do PowerShell \` que normalmente sinalizaria o final de uma linha em um script.</span><span class="sxs-lookup"><span data-stu-id="254f9-115">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="254f9-116">Dentro da cadeia de caracteres here, o caractere de acento grave não funciona.</span><span class="sxs-lookup"><span data-stu-id="254f9-116">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="254f9-117">Você também pode preservar uma barra invertida literal em seus resultados, recortando-a com uma barra invertida precedente, desta forma: `\\` .</span><span class="sxs-lookup"><span data-stu-id="254f9-117">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="254f9-118">Caracteres de barra invertida sem escape, como aqueles que geralmente são usados em caminhos de arquivo, podem ser processados como sequências de escape ilegais em seus resultados.</span><span class="sxs-lookup"><span data-stu-id="254f9-118">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

<span data-ttu-id="254f9-119">O PowerShell 7 adiciona o parâmetro **delimitador** .</span><span class="sxs-lookup"><span data-stu-id="254f9-119">PowerShell 7 adds the **Delimiter** parameter.</span></span>

## <span data-ttu-id="254f9-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="254f9-120">EXAMPLES</span></span>

### <span data-ttu-id="254f9-121">Exemplo 1: converter uma cadeia de caracteres here entre aspas simples em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="254f9-121">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="254f9-122">Este exemplo converte uma cadeia de caracteres aqui entre aspas simples de mensagens de usuário em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-122">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="254f9-123">Em uma cadeia de caracteres entre aspas simples, os valores não são substituídos por variáveis e as expressões não são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="254f9-123">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="254f9-124">O `ConvertFrom-StringData` cmdlet converte o valor na `$Here` variável em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-124">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

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

### <span data-ttu-id="254f9-125">Exemplo 2: converter dados de cadeia de caracteres usando um delimitador diferente</span><span class="sxs-lookup"><span data-stu-id="254f9-125">Example 2: Convert string data using a different delimiter</span></span>

<span data-ttu-id="254f9-126">Este exemplo mostra como converter dados de cadeia de caracteres que usam um caractere diferente como um delimitador.</span><span class="sxs-lookup"><span data-stu-id="254f9-126">This example shows how to convert string data that uses a different character as a delimiter.</span></span> <span data-ttu-id="254f9-127">Neste exemplo, os dados de cadeia de caracteres estão usando o caractere de barra vertical ( `|` ) como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="254f9-127">In this example the string data is using the pipe character (`|`) as the delimiter.</span></span>

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

### <span data-ttu-id="254f9-128">Exemplo 3: converter uma cadeia de caracteres aqui contendo um comentário</span><span class="sxs-lookup"><span data-stu-id="254f9-128">Example 3: Convert a here-string containing a comment</span></span>

<span data-ttu-id="254f9-129">Este exemplo converte uma cadeia de caracteres aqui que contém um comentário e vários pares de chave/valor em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-129">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

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

<span data-ttu-id="254f9-130">O valor do parâmetro **StringData** é uma cadeia de caracteres here, em vez de uma variável que contém uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="254f9-130">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="254f9-131">Qualquer um dos dois formatos é válido.</span><span class="sxs-lookup"><span data-stu-id="254f9-131">Either format is valid.</span></span> <span data-ttu-id="254f9-132">A cadeia de caracteres here inclui um comentário sobre uma das cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="254f9-132">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="254f9-133">`ConvertFrom-StringData` ignora comentários de linha única, mas o `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="254f9-133">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="254f9-134">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="254f9-134">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="254f9-135">Exemplo 4: converter uma cadeia de caracteres em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="254f9-135">Example 4: Convert a string to a hash table</span></span>

<span data-ttu-id="254f9-136">Este exemplo converte uma cadeia de caracteres entre aspas duplas (não uma cadeia de caracteres aqui) em uma tabela de hash e a salva na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="254f9-136">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

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

<span data-ttu-id="254f9-137">Para satisfazer a condição de que cada par chave-valor deve estar em uma linha separada, a cadeia de caracteres usa o caractere de nova linha ( \` n) do PowerShell para separar os pares.</span><span class="sxs-lookup"><span data-stu-id="254f9-137">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="254f9-138">Exemplo 5: usar ConvertFrom-StringData na seção de dados de um script</span><span class="sxs-lookup"><span data-stu-id="254f9-138">Example 5: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="254f9-139">Este exemplo mostra um `ConvertFrom-StringData` comando usado na seção de dados de um script.</span><span class="sxs-lookup"><span data-stu-id="254f9-139">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="254f9-140">As instruções abaixo da seção DATA exibem o texto para o usuário.</span><span class="sxs-lookup"><span data-stu-id="254f9-140">The statements below the DATA section display the text to the user.</span></span>

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

<span data-ttu-id="254f9-141">Já que o texto inclui nomes de variáveis, ele deve ser colocado em uma cadeia de caracteres entre aspas simples, de modo que as variáveis sejam interpretadas literalmente e não expandidas.</span><span class="sxs-lookup"><span data-stu-id="254f9-141">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="254f9-142">Não são permitidas variáveis na seção **Data** .</span><span class="sxs-lookup"><span data-stu-id="254f9-142">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="254f9-143">Exemplo 6: usar o operador de pipeline para passar uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="254f9-143">Example 6: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="254f9-144">Este exemplo mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="254f9-144">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="254f9-145">O valor da `$Here` variável é canalizado para `ConvertFrom-StringData` e o resultado na `$Hash` variável.</span><span class="sxs-lookup"><span data-stu-id="254f9-145">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

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

### <span data-ttu-id="254f9-146">Exemplo 7: usar caracteres de escape para adicionar novas linhas e caracteres de retorno</span><span class="sxs-lookup"><span data-stu-id="254f9-146">Example 7: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="254f9-147">Este exemplo mostra o uso de caracteres de escape para criar novas linhas e caracteres de retorno em dados de origem.</span><span class="sxs-lookup"><span data-stu-id="254f9-147">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="254f9-148">A sequência de escape `\n` é usada para criar novas linhas dentro de um bloco de texto associado a um nome ou item na tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="254f9-148">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

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

### <span data-ttu-id="254f9-149">Exemplo 8: usar o caractere de escape de barra invertida para renderizar corretamente um caminho de arquivo</span><span class="sxs-lookup"><span data-stu-id="254f9-149">Example 8: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="254f9-150">Este exemplo mostra como usar o caractere de escape de barra invertida nos dados de cadeia de caracteres para permitir que um caminho de arquivo seja renderizado corretamente na `ConvertFrom-StringData` tabela de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="254f9-150">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="254f9-151">As duas barras invertidas garantem que os caracteres de barra invertida literal sejam processados corretamente na saída da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-151">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="254f9-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="254f9-152">PARAMETERS</span></span>

### <span data-ttu-id="254f9-153">-StringData</span><span class="sxs-lookup"><span data-stu-id="254f9-153">-StringData</span></span>

<span data-ttu-id="254f9-154">Especifica a cadeia de caracteres a ser convertida.</span><span class="sxs-lookup"><span data-stu-id="254f9-154">Specifies the string to be converted.</span></span> <span data-ttu-id="254f9-155">Você pode usar esse parâmetro ou canalizar uma cadeia de caracteres para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="254f9-155">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="254f9-156">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="254f9-156">The parameter name is optional.</span></span>

<span data-ttu-id="254f9-157">O valor desse parâmetro deve ser uma cadeia de caracteres que contenha um ou mais pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="254f9-157">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="254f9-158">Cada par chave-valor deve estar em uma linha separada, ou cada par deve ser separado por caracteres de nova linha ( \` n).</span><span class="sxs-lookup"><span data-stu-id="254f9-158">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="254f9-159">Você pode incluir comentários na cadeia de caracteres, mas os comentários não podem estar na mesma linha que um par chave-valor.</span><span class="sxs-lookup"><span data-stu-id="254f9-159">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="254f9-160">`ConvertFrom-StringData` ignora comentários de linha única.</span><span class="sxs-lookup"><span data-stu-id="254f9-160">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="254f9-161">O `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="254f9-161">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="254f9-162">Todos os caracteres na linha após o `#` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="254f9-162">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="254f9-163">Os comentários não são incluídos na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="254f9-163">The comments are not included in the hash table.</span></span>

<span data-ttu-id="254f9-164">Uma cadeia de caracteres aqui é uma cadeia de caracteres que consiste em uma ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="254f9-164">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="254f9-165">As aspas na cadeia de caracteres aqui são interpretadas literalmente como parte dos dados da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="254f9-165">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="254f9-166">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="254f9-166">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="254f9-167">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="254f9-167">-Delimiter</span></span>

<span data-ttu-id="254f9-168">O caractere usado para separar a **chave** dos dados de **valor** na cadeia de caracteres que está sendo convertida.</span><span class="sxs-lookup"><span data-stu-id="254f9-168">The character used to separate the **key** from the **value** data in the string being converted.</span></span>
<span data-ttu-id="254f9-169">O delimitador padrão é o caractere de sinal de igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="254f9-169">The default delimiter is the equals sign (`=`) character.</span></span> <span data-ttu-id="254f9-170">Esse parâmetro foi adicionado no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="254f9-170">This parameter was added in PowerShell 7.</span></span>

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

### <span data-ttu-id="254f9-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="254f9-171">CommonParameters</span></span>

<span data-ttu-id="254f9-172">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="254f9-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="254f9-173">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="254f9-173">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="254f9-174">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="254f9-174">INPUTS</span></span>

### <span data-ttu-id="254f9-175">System.String</span><span class="sxs-lookup"><span data-stu-id="254f9-175">System.String</span></span>

<span data-ttu-id="254f9-176">É possível canalizar uma cadeia de caracteres que contém um par chave-valor para `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="254f9-176">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="254f9-177">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="254f9-177">OUTPUTS</span></span>

### <span data-ttu-id="254f9-178">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="254f9-178">System.Collections.Hashtable</span></span>

<span data-ttu-id="254f9-179">Esse cmdlet retorna uma tabela de hash que ele cria a partir dos pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="254f9-179">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="254f9-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="254f9-180">NOTES</span></span>

<span data-ttu-id="254f9-181">Uma cadeia de caracteres here é uma cadeia de caracteres com uma ou mais linhas, nas quais as aspas são interpretadas literalmente.</span><span class="sxs-lookup"><span data-stu-id="254f9-181">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="254f9-182">Esse cmdlet pode ser útil em scripts que exibem mensagens do usuário em vários idiomas falados.</span><span class="sxs-lookup"><span data-stu-id="254f9-182">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="254f9-183">Você pode usar as tabelas de hash em estilo de dicionário para isolar as cadeias de caracteres de texto do código como ocorre em arquivos de recursos, além de formatar as cadeias de caracteres de texto para uso em ferramentas de tradução.</span><span class="sxs-lookup"><span data-stu-id="254f9-183">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="254f9-184">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="254f9-184">RELATED LINKS</span></span>

