---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193853"
---
# <span data-ttu-id="fd97a-103">Convert-String</span><span class="sxs-lookup"><span data-stu-id="fd97a-103">Convert-String</span></span>

## <span data-ttu-id="fd97a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fd97a-104">SYNOPSIS</span></span>
<span data-ttu-id="fd97a-105">Formata uma cadeia de caracteres para fazer a correspondência de exemplos.</span><span class="sxs-lookup"><span data-stu-id="fd97a-105">Formats a string to match examples.</span></span>

## <span data-ttu-id="fd97a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd97a-106">SYNTAX</span></span>

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## <span data-ttu-id="fd97a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd97a-107">DESCRIPTION</span></span>

<span data-ttu-id="fd97a-108">O cmdlet **Convert-String** formata uma cadeia de caracteres para corresponder ao formato dos exemplos.</span><span class="sxs-lookup"><span data-stu-id="fd97a-108">The **Convert-String** cmdlet formats a string to match the format of examples.</span></span>

## <span data-ttu-id="fd97a-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fd97a-109">EXAMPLES</span></span>

### <span data-ttu-id="fd97a-110">Exemplo 1: converter o formato de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fd97a-110">Example 1: Convert format of a string</span></span>

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

<span data-ttu-id="fd97a-111">O primeiro comando cria uma matriz que contém o nome e o sobrenome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-111">The first command creates an array that contains first and last names.</span></span>

<span data-ttu-id="fd97a-112">O segundo comando formata os nomes de acordo com o exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd97a-112">The second command formats the names according to the example.</span></span>
<span data-ttu-id="fd97a-113">Ele coloca o sobrenome primeiro na saída, seguido por um inicial.</span><span class="sxs-lookup"><span data-stu-id="fd97a-113">It puts the surname first in the output, followed by an initial.</span></span>

### <span data-ttu-id="fd97a-114">Exemplo 2: simplificar o formato de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fd97a-114">Example 2: Simplify format of a string</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

<span data-ttu-id="fd97a-115">O primeiro comando cria uma matriz que contém nome, meio e sobrenome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-115">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="fd97a-116">Observe que a última entrada não tem um segundo nome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-116">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="fd97a-117">O segundo comando formata os nomes de acordo com o exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd97a-117">The second command formats the names according to the example.</span></span>
<span data-ttu-id="fd97a-118">Ele coloca o sobrenome primeiro na saída, seguido pelo primeiro nome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-118">It puts the last name first in the output, followed by the first name.</span></span>
<span data-ttu-id="fd97a-119">Todos os nomes de meio removidos; a entrada sem o nome do meio é manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="fd97a-119">All middle names removed; entry without middle name is handled correctly.</span></span>

### <span data-ttu-id="fd97a-120">Exemplo 3: gerenciamento de saída quando cadeias de caracteres não correspondem ao exemplo</span><span class="sxs-lookup"><span data-stu-id="fd97a-120">Example 3: Output management when strings don't match example</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

<span data-ttu-id="fd97a-121">O primeiro comando cria uma matriz que contém nome, meio e sobrenome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-121">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="fd97a-122">Observe que a última entrada não tem um segundo nome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-122">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="fd97a-123">O segundo comando formata os nomes de acordo com o exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd97a-123">The second command formats the names according to the example.</span></span>
<span data-ttu-id="fd97a-124">Ele coloca o **nome do meio** primeiro na saída, seguido pelo primeiro nome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-124">It puts the **middle name** first in the output, followed by the first name.</span></span>
<span data-ttu-id="fd97a-125">A última entrada em **$Composers** é ignorada porque não corresponde ao padrão de exemplo: ela não tem um nome de meio.</span><span class="sxs-lookup"><span data-stu-id="fd97a-125">The last entry in **$Composers** is skipped, because it doesn't match the sample pattern: it has no middle name.</span></span>

### <span data-ttu-id="fd97a-126">Exemplo 4: cuidado com espaços de beleza</span><span class="sxs-lookup"><span data-stu-id="fd97a-126">Example 4: Caution with beauty spaces</span></span>

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

<span data-ttu-id="fd97a-127">O primeiro comando cria uma matriz de nome e sobrenome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-127">The first command creates an array of first and last names.</span></span>
<span data-ttu-id="fd97a-128">Observe que o segundo e o quarto itens têm um espaço à direita extra, após o último nome.</span><span class="sxs-lookup"><span data-stu-id="fd97a-128">Note that second and fourth items have an extra trailing space, after the last name.</span></span>

<span data-ttu-id="fd97a-129">O segundo comando converte todas as cadeias de caracteres que correspondem ao padrão de exemplo: _Word, espaço, palavra e espaço final à direita_ , tudo isso antes do sinal de igual.</span><span class="sxs-lookup"><span data-stu-id="fd97a-129">The second command converts all strings that match the sample pattern: _word, space, word, and final trailing space_ , all of this before the equal sign.</span></span>
<span data-ttu-id="fd97a-130">Além disso, observe o espaço à esquerda na saída.</span><span class="sxs-lookup"><span data-stu-id="fd97a-130">Also, note the leading space in the output.</span></span>

### <span data-ttu-id="fd97a-131">Exemplo 5: Formatar informações de processo com vários padrões</span><span class="sxs-lookup"><span data-stu-id="fd97a-131">Example 5: Format process information with multiple patterns</span></span>

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

<span data-ttu-id="fd97a-132">**$ExamplePatterns** define diferentes padrões esperados nos dados, por meio de exemplos.</span><span class="sxs-lookup"><span data-stu-id="fd97a-132">**$ExamplePatterns** defines different expected patterns in the data, through examples.</span></span>

<span data-ttu-id="fd97a-133">O primeiro padrão, `@{before='"Hello","World"'; after='World: Hello'}` , lido da seguinte maneira: _espera-se cadeias de caracteres em que uma palavra é colocada entre aspas duplas, depois uma vírgula_ 
 _e, em seguida, a segunda e última, palavra entre aspas;_ 
 _sem espaços na cadeia de caracteres. Na saída: Coloque a segunda palavra primeiro,_ 
 _sem aspas, um único espaço e, em seguida, a primeira palavra, sem aspas._</span><span class="sxs-lookup"><span data-stu-id="fd97a-133">The first pattern, `@{before='"Hello","World"'; after='World: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then the second, and last, word enclosed in quotes;_
_with no spaces in the string. On the output: place second word first,_
_without quotes, then a single space, and then the first word, without quotes._</span></span>

<span data-ttu-id="fd97a-134">O segundo padrão, `@{before='"Hello","1"'; after='1: Hello'}` , lê da seguinte maneira: _espera-se cadeias de caracteres em que uma palavra é colocada entre aspas duplas, depois uma vírgula_ 
 _e um número entre aspas;_ 
 _sem espaços na cadeia de caracteres. Na saída: Coloque o número primeiro,_ 
 _sem aspas, um único espaço e, em seguida, a palavra, sem aspas._</span><span class="sxs-lookup"><span data-stu-id="fd97a-134">The second pattern, `@{before='"Hello","1"'; after='1: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then a number enclosed in quotes;_
_with no spaces in the string. On the output: place the number first,_
_without quotes, then a single space, and then the word, without quotes._</span></span>

<span data-ttu-id="fd97a-135">O terceiro padrão, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , lido da seguinte maneira: espera-se _cadeias de caracteres em que duas palavras com um hífen entre elas ficam entre_ 
 _aspas duplas, depois uma vírgula e um número entre aspas;_ 
 _sem espaços entre a vírgula e a terceira aspa dupla._ 
 _Na saída: Coloque o número primeiro, sem aspas, um único espaço,_ 
 _e, em seguida, as palavras hifenizadas, sem aspas._</span><span class="sxs-lookup"><span data-stu-id="fd97a-135">The third pattern, `@{before='"Hello-World","22"'; after='22: Hello-World'}`, reads as follows: _expect strings where two words with a hyphen in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the hyphenated words, without quotes._</span></span>

<span data-ttu-id="fd97a-136">O quarto e último padrão, `@{before='"hello world","333"'; after='333: hello world'}` , leituras da seguinte maneira: espera-se _cadeias de caracteres em que duas palavras com um espaço entre elas são colocadas entre_ 
 _aspas duplas, depois uma vírgula e um número entre aspas;_ 
 _sem espaços entre a vírgula e a terceira aspa dupla._ 
 _Na saída: Coloque o número primeiro, sem aspas, um único espaço,_ 
 _e, em seguida, as palavras com o espaço entre entre aspas._</span><span class="sxs-lookup"><span data-stu-id="fd97a-136">The fourth, and final, pattern, `@{before='"hello world","333"'; after='333: hello world'}`, reads as follows: _expect strings where two words with a space in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the words with the space in between, without quotes._</span></span>

<span data-ttu-id="fd97a-137">O primeiro comando obtém todos os processos usando o cmdlet Get-Process.</span><span class="sxs-lookup"><span data-stu-id="fd97a-137">The first command gets all processes by using the Get-Process cmdlet.</span></span>
<span data-ttu-id="fd97a-138">O comando os passa para o cmdlet Select-Object, que seleciona o nome do processo e a ID do processo.</span><span class="sxs-lookup"><span data-stu-id="fd97a-138">The command passes them to the Select-Object cmdlet, which selects the process name and process ID.</span></span> <span data-ttu-id="fd97a-139">No final do pipeline, o comando converte a saída em valores separados por vírgula, sem informações de tipo, usando o cmdlet ConvertTo-Csv.</span><span class="sxs-lookup"><span data-stu-id="fd97a-139">At the end of the pipeline, the command converts the output to comma separated values, without type information, by using the ConvertTo-Csv cmdlet.</span></span>
<span data-ttu-id="fd97a-140">O comando armazena os resultados na variável **$Processes** .</span><span class="sxs-lookup"><span data-stu-id="fd97a-140">The command stores the results in the **$Processes** variable.</span></span>
<span data-ttu-id="fd97a-141">Agora **$Processes** contém nomes de processo e PID.</span><span class="sxs-lookup"><span data-stu-id="fd97a-141">**$Processes** now contains process names and PID.</span></span>

<span data-ttu-id="fd97a-142">O segundo comando especifica uma variável de exemplo que altera a ordem dos itens de entrada.</span><span class="sxs-lookup"><span data-stu-id="fd97a-142">The second command specifies an example variable that changes the order of the input items.</span></span>
<span data-ttu-id="fd97a-143">O comando reverte cada cadeia de caracteres em **$Processes** .</span><span class="sxs-lookup"><span data-stu-id="fd97a-143">The command coverts each string in **$Processes** .</span></span>

><span data-ttu-id="fd97a-144">**Observação** O quarto padrão indica implicitamente que duas ou mais palavras separadas por espaços são correspondidas.</span><span class="sxs-lookup"><span data-stu-id="fd97a-144">**Note** The fourth pattern implicitly says that two or more words separated by spaces are matched.</span></span>
>
><span data-ttu-id="fd97a-145">Sem o quarto padrão, somente a primeira palavra da cadeia de caracteres entre aspas duplas é correspondida.</span><span class="sxs-lookup"><span data-stu-id="fd97a-145">Without the fourth pattern, only the first word of the string enclosed in double quotes is matched.</span></span>

## <span data-ttu-id="fd97a-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd97a-146">PARAMETERS</span></span>

### <span data-ttu-id="fd97a-147">-Exemplo</span><span class="sxs-lookup"><span data-stu-id="fd97a-147">-Example</span></span>

<span data-ttu-id="fd97a-148">Especifica uma lista de exemplos do formato de destino.</span><span class="sxs-lookup"><span data-stu-id="fd97a-148">Specifies a list of examples of the target format.</span></span>
<span data-ttu-id="fd97a-149">Especifique os pares separados pelo sinal de igual (=), com o padrão de origem à esquerda e o padrão de destino à direita, como nos exemplos a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd97a-149">Specify pairs separated by the equal (=) sign, with the source pattern on the left and the target pattern on the right, as in the following examples:</span></span>

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

><span data-ttu-id="fd97a-150">**Observação** O segundo exemplo usa uma lista de padrões</span><span class="sxs-lookup"><span data-stu-id="fd97a-150">**Note** The second example uses a list of patterns</span></span>

<span data-ttu-id="fd97a-151">Como alternativa, especifique uma lista de tabelas de hash que contenham as propriedades **before** e **After** .</span><span class="sxs-lookup"><span data-stu-id="fd97a-151">Alternatively, specify a list of hash tables that contain **Before** and **After** properties.</span></span>

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

><span data-ttu-id="fd97a-152">**Cuidado** Evite usar espaços em volta do sinal de igual, pois eles são tratados como parte do padrão.</span><span class="sxs-lookup"><span data-stu-id="fd97a-152">**Caution** Avoid using spaces around the equal sign, as they are treated as part of the pattern.</span></span>

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd97a-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd97a-153">-InputObject</span></span>

<span data-ttu-id="fd97a-154">Especifica uma cadeia de caracteres a ser formatada.</span><span class="sxs-lookup"><span data-stu-id="fd97a-154">Specifies a string to format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd97a-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd97a-155">CommonParameters</span></span>

<span data-ttu-id="fd97a-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd97a-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd97a-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd97a-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd97a-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fd97a-158">INPUTS</span></span>

### <span data-ttu-id="fd97a-159">String</span><span class="sxs-lookup"><span data-stu-id="fd97a-159">String</span></span>

<span data-ttu-id="fd97a-160">Você pode canalizar cadeias de caracteres para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd97a-160">You can pipe strings to this cmdlet.</span></span>

## <span data-ttu-id="fd97a-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fd97a-161">OUTPUTS</span></span>

### <span data-ttu-id="fd97a-162">String</span><span class="sxs-lookup"><span data-stu-id="fd97a-162">String</span></span>

<span data-ttu-id="fd97a-163">Esse cmdlet retorna uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fd97a-163">This cmdlet returns a string.</span></span>

## <span data-ttu-id="fd97a-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fd97a-164">NOTES</span></span>

## <span data-ttu-id="fd97a-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fd97a-165">RELATED LINKS</span></span>

[<span data-ttu-id="fd97a-166">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="fd97a-166">ConvertFrom-String</span></span>](ConvertFrom-String.md)

[<span data-ttu-id="fd97a-167">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="fd97a-167">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="fd97a-168">Get-Process</span><span class="sxs-lookup"><span data-stu-id="fd97a-168">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="fd97a-169">Out-String</span><span class="sxs-lookup"><span data-stu-id="fd97a-169">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="fd97a-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="fd97a-170">Select-Object</span></span>](Select-Object.md)
