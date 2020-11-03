---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 7c614314eb13ea484f5a0a5ade36aabdd6afdf58
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195243"
---
# <span data-ttu-id="25120-103">Select-String</span><span class="sxs-lookup"><span data-stu-id="25120-103">Select-String</span></span>

## <span data-ttu-id="25120-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="25120-104">SYNOPSIS</span></span>
<span data-ttu-id="25120-105">Localiza texto em arquivos e cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="25120-105">Finds text in strings and files.</span></span>

## <span data-ttu-id="25120-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25120-106">SYNTAX</span></span>

### <span data-ttu-id="25120-107">Arquivo (padrão)</span><span class="sxs-lookup"><span data-stu-id="25120-107">File (Default)</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="25120-108">ObjectRaw</span><span class="sxs-lookup"><span data-stu-id="25120-108">ObjectRaw</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="25120-109">Objeto</span><span class="sxs-lookup"><span data-stu-id="25120-109">Object</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="25120-110">FileRaw</span><span class="sxs-lookup"><span data-stu-id="25120-110">FileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="25120-111">LiteralFileRaw</span><span class="sxs-lookup"><span data-stu-id="25120-111">LiteralFileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="25120-112">Valor literal</span><span class="sxs-lookup"><span data-stu-id="25120-112">LiteralFile</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="25120-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25120-113">DESCRIPTION</span></span>

<span data-ttu-id="25120-114">O `Select-String` cmdlet procura padrões de texto e texto em cadeias de caracteres de entrada e arquivos.</span><span class="sxs-lookup"><span data-stu-id="25120-114">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="25120-115">Você pode usar `Select-String` semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.</span><span class="sxs-lookup"><span data-stu-id="25120-115">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="25120-116">`Select-String` baseia-se em linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="25120-116">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="25120-117">Por padrão, `Select-String` o localiza a primeira correspondência em cada linha e, para cada correspondência, exibe o nome do arquivo, o número da linha e todo o texto na linha que contém a correspondência.</span><span class="sxs-lookup"><span data-stu-id="25120-117">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="25120-118">Você pode direcionar `Select-String` para localizar várias correspondências por linha, exibir texto antes e depois da correspondência, ou exibir um valor booliano (true ou false) que indica se uma correspondência é encontrada.</span><span class="sxs-lookup"><span data-stu-id="25120-118">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="25120-119">`Select-String` usa correspondência de expressão regular, mas também pode executar uma correspondência que pesquisa a entrada para o texto que você especificar.</span><span class="sxs-lookup"><span data-stu-id="25120-119">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="25120-120">`Select-String` pode exibir todas as correspondências de texto ou parar após a primeira correspondência em cada arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="25120-120">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="25120-121">`Select-String` pode ser usado para exibir todo o texto que não corresponde ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="25120-121">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="25120-122">Você também pode especificar que `Select-String` deve esperar uma codificação de caractere específica, como quando você está pesquisando arquivos de texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="25120-122">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="25120-123">`Select-String` usa a BOM (marca de ordem de byte) para detectar o formato de codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="25120-123">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="25120-124">Se o arquivo não tiver uma BOM, ele assumirá que a codificação é UTF8.</span><span class="sxs-lookup"><span data-stu-id="25120-124">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="25120-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="25120-125">EXAMPLES</span></span>

### <span data-ttu-id="25120-126">Exemplo 1: Localizar uma correspondência que diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="25120-126">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="25120-127">Este exemplo faz uma correspondência que diferencia maiúsculas de minúsculas do texto que foi enviado pelo pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-127">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="25120-128">As cadeias de texto **Olá** e **Olá** são enviadas ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-128">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="25120-129">`Select-String` usa o parâmetro **Pattern** para especificar **Hello** .</span><span class="sxs-lookup"><span data-stu-id="25120-129">`Select-String` uses the **Pattern** parameter to specify **HELLO** .</span></span> <span data-ttu-id="25120-130">O parâmetro **CaseSensitive** especifica que o caso deve corresponder apenas ao padrão em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="25120-130">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="25120-131">**SimpleMatch** é um parâmetro opcional e especifica que a cadeia de caracteres no padrão não é interpretada como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-131">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="25120-132">`Select-String` exibe **Olá** no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-132">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="25120-133">Exemplo 2: localizar correspondências em arquivos de texto</span><span class="sxs-lookup"><span data-stu-id="25120-133">Example 2: Find matches in text files</span></span>

<span data-ttu-id="25120-134">Esse comando pesquisa todos os arquivos com a `.txt` extensão de nome de arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="25120-134">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="25120-135">A saída exibe as linhas nesses arquivos que incluem a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="25120-135">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="25120-136">Neste exemplo, `Get-Alias` e `Get-Command` são usados com o `Out-File` cmdlet para criar dois arquivos de texto no diretório atual, **Alias.txt** e **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="25120-136">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt** .</span></span>

<span data-ttu-id="25120-137">`Select-String` usa o parâmetro **path** com o curinga asterisco ( `*` ) para pesquisar todos os arquivos no diretório atual com a extensão de nome de arquivo `.txt` .</span><span class="sxs-lookup"><span data-stu-id="25120-137">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="25120-138">O parâmetro **Pattern** especifica o texto para corresponder a **Get-** .</span><span class="sxs-lookup"><span data-stu-id="25120-138">The **Pattern** parameter specifies the text to match **Get-** .</span></span> <span data-ttu-id="25120-139">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-139">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="25120-140">O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-140">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="25120-141">Exemplo 3: Localizar uma correspondência de padrão</span><span class="sxs-lookup"><span data-stu-id="25120-141">Example 3: Find a pattern match</span></span>

<span data-ttu-id="25120-142">Neste exemplo, vários arquivos são pesquisados para localizar correspondências para o padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="25120-142">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="25120-143">O padrão usa um quantificador de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-143">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="25120-144">Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25120-144">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="25120-145">O `Select-String` cmdlet usa dois parâmetros, **Path** e **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-145">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern** .</span></span> <span data-ttu-id="25120-146">O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-146">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="25120-147">O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="25120-147">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="25120-148">O parâmetro **Pattern** especifica a correspondência de um ponto de interrogação ( `?` ) em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="25120-148">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="25120-149">Uma barra invertida ( `\` ) é usada como um caractere de escape e é necessária porque o ponto de interrogação ( `?` ) é um quantificador de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-149">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="25120-150">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-150">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="25120-151">O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-151">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="25120-152">Exemplo 4: usar Select-String em uma função</span><span class="sxs-lookup"><span data-stu-id="25120-152">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="25120-153">Este exemplo cria uma função para procurar por um padrão nos arquivos de ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-153">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="25120-154">Para este exemplo, a função existe somente na sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-154">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="25120-155">Quando a sessão do PowerShell é fechada, a função é excluída.</span><span class="sxs-lookup"><span data-stu-id="25120-155">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="25120-156">Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="25120-156">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

<span data-ttu-id="25120-157">A função é criada na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-157">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="25120-158">O `Function` comando usa o nome **Search-Help** .</span><span class="sxs-lookup"><span data-stu-id="25120-158">The `Function` command uses the name **Search-Help** .</span></span> <span data-ttu-id="25120-159">Pressione **Enter** para começar a adicionar instruções à função.</span><span class="sxs-lookup"><span data-stu-id="25120-159">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="25120-160">No `>>` prompt, adicione cada instrução e pressione **Enter** , conforme mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="25120-160">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="25120-161">Depois que o colchete de fechamento for adicionado, você será retornado para um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-161">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="25120-162">A função contém dois comandos.</span><span class="sxs-lookup"><span data-stu-id="25120-162">The function contains two commands.</span></span> <span data-ttu-id="25120-163">A `$PSHelp` variável armazena o caminho para os arquivos de ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-163">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="25120-164">`$PSHOME` é o diretório de instalação do PowerShell com o subdiretório **en-US** que especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="25120-164">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="25120-165">O `Select-String` comando na função usa os parâmetros **Path** e **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-165">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="25120-166">O parâmetro **path** usa a `$PSHelp` variável para obter o caminho.</span><span class="sxs-lookup"><span data-stu-id="25120-166">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="25120-167">O parâmetro **Pattern** usa a cadeia de caracteres **About_** como os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="25120-167">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="25120-168">Para executar a função, digite `Search-Help` .</span><span class="sxs-lookup"><span data-stu-id="25120-168">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="25120-169">O comando da função `Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-169">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="25120-170">Exemplo 5: Pesquisar uma cadeia de caracteres em um log de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="25120-170">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="25120-171">Este exemplo pesquisa uma cadeia de caracteres em um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="25120-171">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="25120-172">A variável `$_` representa o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="25120-172">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="25120-173">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="25120-173">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="25120-174">O `Get-WinEvent` cmdlet usa o parâmetro **LogName** para especificar o log do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="25120-174">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="25120-175">O parâmetro **MaxEvents** obtém os 50 eventos mais recentes do log.</span><span class="sxs-lookup"><span data-stu-id="25120-175">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="25120-176">O conteúdo do log é armazenado na variável chamada `$Events` .</span><span class="sxs-lookup"><span data-stu-id="25120-176">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="25120-177">A `$Events` variável é enviada ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-177">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="25120-178">`Select-String` usa o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="25120-178">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="25120-179">A `$_` variável representa o objeto atual e `message` é uma propriedade do evento.</span><span class="sxs-lookup"><span data-stu-id="25120-179">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="25120-180">O parâmetro **Pattern** especifica a cadeia de caracteres que **falhou** e procura por correspondências `$_.message` .</span><span class="sxs-lookup"><span data-stu-id="25120-180">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="25120-181">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-181">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="25120-182">Exemplo 6: Localizar uma cadeia de caracteres em subdiretórios</span><span class="sxs-lookup"><span data-stu-id="25120-182">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="25120-183">Este exemplo pesquisa um diretório e todos os seus subdiretórios para uma cadeia de texto específica.</span><span class="sxs-lookup"><span data-stu-id="25120-183">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="25120-184">`Get-ChildItem` usa o parâmetro **path** para especificar **C:\Windows\System32 \* . txt** .</span><span class="sxs-lookup"><span data-stu-id="25120-184">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt** .</span></span> <span data-ttu-id="25120-185">O parâmetro **recurse** inclui os subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="25120-185">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="25120-186">Os objetos são enviados ao pipeline para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-186">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="25120-187">`Select-String` usa o parâmetro **Pattern** e especifica a cadeia de caracteres **Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="25120-187">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft** .</span></span> <span data-ttu-id="25120-188">O parâmetro **CaseSensitive** é usado para corresponder ao caso exato da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="25120-188">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="25120-189">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-189">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="25120-190">Dependendo de suas permissões, você poderá ver as mensagens de **acesso negado** na saída.</span><span class="sxs-lookup"><span data-stu-id="25120-190">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="25120-191">Exemplo 7: localizar cadeias de caracteres que não correspondem a um padrão</span><span class="sxs-lookup"><span data-stu-id="25120-191">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="25120-192">Este exemplo mostra como excluir linhas de dados que não correspondem a um padrão.</span><span class="sxs-lookup"><span data-stu-id="25120-192">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="25120-193">O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="25120-193">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="25120-194">`Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="25120-194">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="25120-195">O parâmetro **Pattern** especifica **Get** e **set** como o padrão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="25120-195">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="25120-196">O parâmetro não **Match** exclui **Get** e **set** dos resultados.</span><span class="sxs-lookup"><span data-stu-id="25120-196">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="25120-197">`Select-String` exibe a saída no console do PowerShell que não inclui **Get** ou **set** .</span><span class="sxs-lookup"><span data-stu-id="25120-197">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set** .</span></span>

### <span data-ttu-id="25120-198">Exemplo 8: localizar linhas antes e depois de uma correspondência</span><span class="sxs-lookup"><span data-stu-id="25120-198">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="25120-199">Este exemplo mostra como obter as linhas antes e depois do padrão correspondente.</span><span class="sxs-lookup"><span data-stu-id="25120-199">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

<span data-ttu-id="25120-200">O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="25120-200">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="25120-201">`Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="25120-201">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="25120-202">O parâmetro **Pattern** especifica **Get-Computer** como o padrão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="25120-202">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="25120-203">O parâmetro de **contexto** usa dois valores, antes e depois, e marca as correspondências de padrão na saída com um colchete angular ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="25120-203">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="25120-204">O parâmetro **Context** gera as duas linhas antes do primeiro padrão corresponder e três linhas após a última correspondência de padrão.</span><span class="sxs-lookup"><span data-stu-id="25120-204">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="25120-205">Exemplo 9: localizar todas as correspondências de padrão</span><span class="sxs-lookup"><span data-stu-id="25120-205">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="25120-206">Este exemplo mostra como o parâmetro **Mymatchs** encontra cada correspondência de padrão em uma linha de texto.</span><span class="sxs-lookup"><span data-stu-id="25120-206">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="25120-207">Por padrão, `Select-String` o localiza apenas a primeira ocorrência de um padrão em uma linha de texto.</span><span class="sxs-lookup"><span data-stu-id="25120-207">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="25120-208">Este exemplo usa propriedades de objeto que são encontradas com o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-208">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

<span data-ttu-id="25120-209">O `Get-ChildItem` cmdlet usa o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="25120-209">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="25120-210">O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-210">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="25120-211">O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="25120-211">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="25120-212">Os `Get-ChildItem` objetos são armazenados na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="25120-212">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="25120-213">A `$A` variável é enviada ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-213">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="25120-214">`Select-String` usa o parâmetro **Pattern** para pesquisar cada arquivo para a cadeia de caracteres **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="25120-214">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell** .</span></span>

<span data-ttu-id="25120-215">Na linha de comando do PowerShell, o `$A` conteúdo da variável é exibido.</span><span class="sxs-lookup"><span data-stu-id="25120-215">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="25120-216">Há uma linha que contém duas ocorrências da cadeia de caracteres do **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="25120-216">There's a line that contains two occurrences of the string **PowerShell** .</span></span>

<span data-ttu-id="25120-217">A `$A.Matches` propriedade lista a primeira ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="25120-217">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="25120-218">A `$A.Matches.Length` Propriedade conta a primeira ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="25120-218">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="25120-219">A `$B` variável usa os mesmos `Get-ChildItem` `Select-String` cmdlets e, mas adiciona o parâmetro de todas as **correspondências** .</span><span class="sxs-lookup"><span data-stu-id="25120-219">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="25120-220">Os **Permatchs** localiza cada ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="25120-220">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="25120-221">Os objetos armazenados nas `$A` variáveis e `$B` são idênticos.</span><span class="sxs-lookup"><span data-stu-id="25120-221">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="25120-222">A `$B.Matches.Length` Propriedade aumenta porque, para cada linha, todas as ocorrências do padrão do **PowerShell** são contadas.</span><span class="sxs-lookup"><span data-stu-id="25120-222">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="25120-223">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25120-223">PARAMETERS</span></span>

### <span data-ttu-id="25120-224">-Todas as correspondências</span><span class="sxs-lookup"><span data-stu-id="25120-224">-AllMatches</span></span>

<span data-ttu-id="25120-225">Indica que o cmdlet pesquisa mais de uma correspondência em cada linha de texto.</span><span class="sxs-lookup"><span data-stu-id="25120-225">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="25120-226">Sem esse parâmetro, `Select-String` o localiza apenas a primeira correspondência em cada linha de texto.</span><span class="sxs-lookup"><span data-stu-id="25120-226">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="25120-227">Quando `Select-String` o encontra mais de uma correspondência em uma linha de texto, ele ainda emite apenas um objeto **MatchInfo** para a linha, mas a propriedade **corresponde** do objeto contém todas as correspondências.</span><span class="sxs-lookup"><span data-stu-id="25120-227">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="25120-228">Esse parâmetro é ignorado quando usado em combinação com o parâmetro **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="25120-228">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="25120-229">Se você deseja retornar todas as correspondências e o padrão que você está procurando contém caracteres de expressão regular, você deve escapar esses caracteres em vez de usar **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="25120-229">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch** .</span></span> <span data-ttu-id="25120-230">Consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) para obter mais informações sobre a saída de expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="25120-230">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-231">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="25120-231">-CaseSensitive</span></span>

<span data-ttu-id="25120-232">Indica que as correspondências de cmdlet diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="25120-232">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="25120-233">Por padrão, as correspondências não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="25120-233">By default, matches aren't case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-234">-Context</span><span class="sxs-lookup"><span data-stu-id="25120-234">-Context</span></span>

<span data-ttu-id="25120-235">Captura o número especificado de linhas antes e depois da linha que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="25120-235">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="25120-236">Se você inserir um número como o valor desse parâmetro, esse número determina o número de linhas capturadas antes e após a correspondência.</span><span class="sxs-lookup"><span data-stu-id="25120-236">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="25120-237">Se você inserir dois números como valor, o primeiro número determina o número de linhas antes da correspondência e o segundo determina o número de linhas após a correspondência.</span><span class="sxs-lookup"><span data-stu-id="25120-237">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="25120-238">Por exemplo, `-Context 2,3`.</span><span class="sxs-lookup"><span data-stu-id="25120-238">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="25120-239">Na exibição padrão, as linhas com uma correspondência são indicadas por um colchete angular direito ( `>` ) (ASCII 62) na primeira coluna da exibição.</span><span class="sxs-lookup"><span data-stu-id="25120-239">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="25120-240">Linhas desmarcadas são o contexto.</span><span class="sxs-lookup"><span data-stu-id="25120-240">Unmarked lines are the context.</span></span>

<span data-ttu-id="25120-241">O parâmetro de **contexto** não altera o número de objetos gerados pelo `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-241">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="25120-242">`Select-String` gera um objeto [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) para cada correspondência.</span><span class="sxs-lookup"><span data-stu-id="25120-242">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="25120-243">O contexto é armazenado como uma matriz de cadeias de caracteres na propriedade **Context** do objeto.</span><span class="sxs-lookup"><span data-stu-id="25120-243">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="25120-244">Quando a saída de um `Select-String` comando é enviada para o pipeline para outro `Select-String` comando, o comando de recebimento pesquisa apenas o texto na linha correspondente.</span><span class="sxs-lookup"><span data-stu-id="25120-244">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="25120-245">A linha correspondente é o valor da propriedade **line** do objeto **MatchInfo** , não o texto nas linhas de contexto.</span><span class="sxs-lookup"><span data-stu-id="25120-245">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="25120-246">Como resultado, o parâmetro de **contexto** não é válido no comando de recebimento `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-246">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="25120-247">Quando o contexto inclui uma correspondência, o objeto **MatchInfo** de cada correspondência inclui todas as linhas de contexto, mas as linhas sobrepostas aparecem apenas uma vez na exibição.</span><span class="sxs-lookup"><span data-stu-id="25120-247">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-248">-Culture</span><span class="sxs-lookup"><span data-stu-id="25120-248">-Culture</span></span>

<span data-ttu-id="25120-249">Especifica um nome de cultura para corresponder ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="25120-249">Specifies a culture name to match the specified pattern.</span></span> <span data-ttu-id="25120-250">O parâmetro **Culture** deve ser usado com o parâmetro **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="25120-250">The **Culture** parameter must be used with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="25120-251">O comportamento padrão usa a cultura do runspace do PowerShell atual (sessão).</span><span class="sxs-lookup"><span data-stu-id="25120-251">The default behavior uses the culture of the current PowerShell runspace (session).</span></span>

<span data-ttu-id="25120-252">Para obter uma lista de todas as culturas com suporte, use o `Get-Culture -ListAvailable` comando.</span><span class="sxs-lookup"><span data-stu-id="25120-252">To get a list of all supported cultures, use `Get-Culture -ListAvailable` command.</span></span>

<span data-ttu-id="25120-253">Além disso, esse parâmetro aceita os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="25120-253">In addition, this parameter accepts the following arguments:</span></span>

- <span data-ttu-id="25120-254">CurrentCulture, que é padrão;</span><span class="sxs-lookup"><span data-stu-id="25120-254">CurrentCulture, that is default;</span></span>
- <span data-ttu-id="25120-255">Ordinal, que é uma comparação binária não lingüística;</span><span class="sxs-lookup"><span data-stu-id="25120-255">Ordinal, that is non-linguistic binary comparison;</span></span>
- <span data-ttu-id="25120-256">Invariável, que é a comparação independente de cultura.</span><span class="sxs-lookup"><span data-stu-id="25120-256">Invariant, that is culture independent comparison.</span></span>

<span data-ttu-id="25120-257">Com o `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` comando, você obtém uma comparação binária mais rápida.</span><span class="sxs-lookup"><span data-stu-id="25120-257">With `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` command you gets fastest binary comparison.</span></span>

<span data-ttu-id="25120-258">O parâmetro **Culture** usa a conclusão de Tab para percorrer a lista de argumentos que especificam as culturas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25120-258">The **Culture** parameter uses tab completion to scroll through the list of arguments that specify the available cultures.</span></span> <span data-ttu-id="25120-259">Para listar todos os argumentos disponíveis, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="25120-259">To list all available arguments, use the following command:</span></span>

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

<span data-ttu-id="25120-260">Para obter mais informações sobre a propriedade CultureInfo.Name do .NET, consulte [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span><span class="sxs-lookup"><span data-stu-id="25120-260">For more information about .NET CultureInfo.Name property, see [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span></span>

<span data-ttu-id="25120-261">O parâmetro **Culture** foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="25120-261">The **Culture** parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-262">-Codificação</span><span class="sxs-lookup"><span data-stu-id="25120-262">-Encoding</span></span>

<span data-ttu-id="25120-263">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="25120-263">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="25120-264">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="25120-264">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="25120-265">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="25120-265">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="25120-266">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="25120-266">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="25120-267">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="25120-267">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="25120-268">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="25120-268">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="25120-269">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="25120-269">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="25120-270">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="25120-270">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="25120-271">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="25120-271">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="25120-272">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="25120-272">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="25120-273">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="25120-273">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="25120-274">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="25120-274">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="25120-275">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="25120-275">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="25120-276">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="25120-276">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-277">-Excluir</span><span class="sxs-lookup"><span data-stu-id="25120-277">-Exclude</span></span>

<span data-ttu-id="25120-278">Exclui os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="25120-278">Exclude the specified items.</span></span> <span data-ttu-id="25120-279">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="25120-279">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="25120-280">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="25120-280">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="25120-281">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="25120-281">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="25120-282">-Incluir</span><span class="sxs-lookup"><span data-stu-id="25120-282">-Include</span></span>

<span data-ttu-id="25120-283">Inclui os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="25120-283">Includes the specified items.</span></span> <span data-ttu-id="25120-284">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="25120-284">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="25120-285">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="25120-285">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="25120-286">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="25120-286">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="25120-287">-InputObject</span><span class="sxs-lookup"><span data-stu-id="25120-287">-InputObject</span></span>

<span data-ttu-id="25120-288">Especifica o texto a ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="25120-288">Specifies the text to be searched.</span></span> <span data-ttu-id="25120-289">Insira uma variável que contém o texto ou digite um comando ou uma expressão que obtenha o texto.</span><span class="sxs-lookup"><span data-stu-id="25120-289">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="25120-290">Usar o parâmetro **InputObject** não é o mesmo que enviar cadeias de caracteres para baixo do pipeline para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-290">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="25120-291">Quando você canaliza mais de uma cadeia de caracteres para o `Select-String` cmdlet, ele pesquisa o texto especificado em cada cadeia de caracteres e retorna cada cadeia de caracteres que contém o texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="25120-291">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="25120-292">Quando você usa o parâmetro **InputObject** para enviar uma coleção de cadeias de caracteres, `Select-String` o trata a coleção como uma única cadeia de caracteres combinada.</span><span class="sxs-lookup"><span data-stu-id="25120-292">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="25120-293">`Select-String` Retorna as cadeias de caracteres como uma unidade se encontrar o texto de pesquisa em qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="25120-293">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ObjectRaw, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25120-294">-Lista</span><span class="sxs-lookup"><span data-stu-id="25120-294">-List</span></span>

<span data-ttu-id="25120-295">Somente a primeira instância de texto correspondente é retornada de cada arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="25120-295">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="25120-296">Essa é a maneira mais eficiente de recuperar uma lista de arquivos que têm conteúdo correspondente à expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-296">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="25120-297">Por padrão, `Select-String` retorna um objeto **MatchInfo** para cada correspondência que ele encontra.</span><span class="sxs-lookup"><span data-stu-id="25120-297">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-298">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="25120-298">-LiteralPath</span></span>

<span data-ttu-id="25120-299">Especifica o caminho para os arquivos a serem pesquisados.</span><span class="sxs-lookup"><span data-stu-id="25120-299">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="25120-300">O valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="25120-300">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="25120-301">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="25120-301">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="25120-302">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="25120-302">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="25120-303">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="25120-303">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="25120-304">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="25120-304">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="25120-305">-Noênfase</span><span class="sxs-lookup"><span data-stu-id="25120-305">-NoEmphasis</span></span>

<span data-ttu-id="25120-306">Por padrão, `Select-String` o realça a cadeia de caracteres que corresponde ao padrão que você pesquisou com o parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-306">By default, `Select-String` highlights the string that matches the pattern you searched for with the **Pattern** parameter.</span></span> <span data-ttu-id="25120-307">O parâmetro **noênfase** desabilita o realce.</span><span class="sxs-lookup"><span data-stu-id="25120-307">The **NoEmphasis** parameter disables the highlighting.</span></span>

<span data-ttu-id="25120-308">A ênfase usa cores negativas com base nas cores de texto e de fundo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25120-308">The emphasis uses negative colors based on your PowerShell background and text colors.</span></span> <span data-ttu-id="25120-309">Por exemplo, se suas cores do PowerShell forem um plano de fundo preto com texto em branco.</span><span class="sxs-lookup"><span data-stu-id="25120-309">For example, if your PowerShell colors are a black background with white text.</span></span> <span data-ttu-id="25120-310">A ênfase é um plano de fundo branco com texto em preto.</span><span class="sxs-lookup"><span data-stu-id="25120-310">The emphasis is a white background with black text.</span></span>

<span data-ttu-id="25120-311">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="25120-311">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-312">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="25120-312">-NotMatch</span></span>

<span data-ttu-id="25120-313">O parâmetro não **Match** localiza texto que não corresponde ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="25120-313">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-314">-Path</span><span class="sxs-lookup"><span data-stu-id="25120-314">-Path</span></span>

<span data-ttu-id="25120-315">Especifica o caminho para os arquivos a serem pesquisados.</span><span class="sxs-lookup"><span data-stu-id="25120-315">Specifies the path to the files to search.</span></span> <span data-ttu-id="25120-316">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="25120-316">Wildcards are permitted.</span></span> <span data-ttu-id="25120-317">O local padrão é o diretório local.</span><span class="sxs-lookup"><span data-stu-id="25120-317">The default location is the local directory.</span></span>

<span data-ttu-id="25120-318">Especifique os arquivos no diretório, como `log1.txt` , `*.doc` ou `*.*` .</span><span class="sxs-lookup"><span data-stu-id="25120-318">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="25120-319">Se você especificar apenas um diretório, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="25120-319">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="25120-320">-Padrão</span><span class="sxs-lookup"><span data-stu-id="25120-320">-Pattern</span></span>

<span data-ttu-id="25120-321">Especifica o texto a ser localizado em cada linha.</span><span class="sxs-lookup"><span data-stu-id="25120-321">Specifies the text to find on each line.</span></span> <span data-ttu-id="25120-322">O valor padrão é tratado como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-322">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="25120-323">Para saber mais sobre expressões regulares, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25120-323">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-324">-Quiet</span><span class="sxs-lookup"><span data-stu-id="25120-324">-Quiet</span></span>

<span data-ttu-id="25120-325">Indica que o cmdlet retorna um valor booliano (true ou false), em vez de um objeto **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="25120-325">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="25120-326">O valor será true se o padrão for encontrado; caso contrário, o valor será false.</span><span class="sxs-lookup"><span data-stu-id="25120-326">The value is True if the pattern is found; otherwise the value is False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-327">-RAW</span><span class="sxs-lookup"><span data-stu-id="25120-327">-Raw</span></span>

<span data-ttu-id="25120-328">Faz com que o cmdlet gere somente as cadeias de caracteres correspondentes, em vez de objetos **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="25120-328">Causes the cmdlet to output only the matching strings, rather than **MatchInfo** objects.</span></span> <span data-ttu-id="25120-329">Esses são os resultados em comportamento que é o mais semelhante aos comandos UNIX **grep** ou Windows **findstr.exe** .</span><span class="sxs-lookup"><span data-stu-id="25120-329">This is the results in behavior that's the most similar to the Unix **grep** or Windows **findstr.exe** commands.</span></span>

<span data-ttu-id="25120-330">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="25120-330">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-331">-SimpleMatch</span><span class="sxs-lookup"><span data-stu-id="25120-331">-SimpleMatch</span></span>

<span data-ttu-id="25120-332">Indica que o cmdlet usa uma correspondência simples em vez de uma correspondência de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-332">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="25120-333">Em uma correspondência simples, `Select-String` o pesquisa a entrada para o texto no parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-333">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="25120-334">Ele não interpreta o valor do parâmetro **Pattern** como uma instrução de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-334">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="25120-335">Além disso, quando **SimpleMatch** é usado, a propriedade **corresponde** do objeto **MatchInfo** retornado está vazia.</span><span class="sxs-lookup"><span data-stu-id="25120-335">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="25120-336">Quando esse parâmetro é usado com o parâmetro **Mymatchs** , os **correspondentes** são ignorados.</span><span class="sxs-lookup"><span data-stu-id="25120-336">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25120-337">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="25120-337">CommonParameters</span></span>

<span data-ttu-id="25120-338">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="25120-338">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25120-339">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="25120-339">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25120-340">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="25120-340">INPUTS</span></span>

### <span data-ttu-id="25120-341">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="25120-341">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="25120-342">É possível canalizar qualquer objeto que tenha um método **ToString** para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-342">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="25120-343">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="25120-343">OUTPUTS</span></span>

### <span data-ttu-id="25120-344">Microsoft. PowerShell. Commands. MatchInfo, System. booliano, System. String</span><span class="sxs-lookup"><span data-stu-id="25120-344">Microsoft.PowerShell.Commands.MatchInfo, System.Boolean, System.String</span></span>

<span data-ttu-id="25120-345">Por padrão, a saída é um conjunto de objetos **MatchInfo** com um para cada correspondência encontrada.</span><span class="sxs-lookup"><span data-stu-id="25120-345">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="25120-346">Se você usar o parâmetro **Quiet** , a saída será um valor **booliano** indicando se o padrão foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="25120-346">If you use the **Quiet** parameter, the output is a **Boolean** value indicating whether the pattern was found.</span></span>
<span data-ttu-id="25120-347">Se você usar o parâmetro **RAW** , a saída será um conjunto de objetos **String** que correspondem ao padrão.</span><span class="sxs-lookup"><span data-stu-id="25120-347">If you use the **Raw** parameter, the output is a set of **String** objects that match the pattern.</span></span>

## <span data-ttu-id="25120-348">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="25120-348">NOTES</span></span>

<span data-ttu-id="25120-349">`Select-String` é semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.</span><span class="sxs-lookup"><span data-stu-id="25120-349">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="25120-350">O alias de **SLS** para o `Select-String` cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="25120-350">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="25120-351">De acordo com [verbos aprovados para comandos do PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), o prefixo de alias oficial para `Select-*` cmdlets é `sc` , não `sl` .</span><span class="sxs-lookup"><span data-stu-id="25120-351">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="25120-352">Portanto, o alias apropriado para `Select-String` deveria ser `scs` , não `sls` .</span><span class="sxs-lookup"><span data-stu-id="25120-352">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="25120-353">Esta é uma exceção a essa regra.</span><span class="sxs-lookup"><span data-stu-id="25120-353">This is an exception to this rule.</span></span>

<span data-ttu-id="25120-354">Para usar `Select-String` , digite o texto que você deseja localizar como o valor do parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="25120-354">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="25120-355">Para especificar o texto a ser pesquisado, use os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="25120-355">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="25120-356">Digite o texto em uma cadeia de caracteres entre aspas e, em seguida, redirecione-o para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="25120-356">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="25120-357">Armazene uma cadeia de texto em uma variável e, em seguida, especifique a variável como o valor do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="25120-357">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="25120-358">Se o texto estiver armazenado em arquivos, use o parâmetro **path** para especificar o caminho para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="25120-358">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="25120-359">Por padrão, `Select-String` o interpreta o valor do parâmetro **Pattern** como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-359">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="25120-360">Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="25120-360">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="25120-361">Você pode usar o parâmetro **SimpleMatch** para substituir a correspondência de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="25120-361">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="25120-362">O parâmetro **SimpleMatch** localiza instâncias do valor do parâmetro **Pattern** na entrada.</span><span class="sxs-lookup"><span data-stu-id="25120-362">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="25120-363">A saída padrão de `Select-String` é um objeto **MatchInfo** , que inclui informações detalhadas sobre as correspondências.</span><span class="sxs-lookup"><span data-stu-id="25120-363">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="25120-364">As informações no objeto são úteis quando você está pesquisando texto em arquivos, porque os objetos **MatchInfo** têm propriedades como **filename** e **line** .</span><span class="sxs-lookup"><span data-stu-id="25120-364">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line** .</span></span> <span data-ttu-id="25120-365">Quando a entrada não estiver no arquivo, o valor desses parâmetros será **InputStream** .</span><span class="sxs-lookup"><span data-stu-id="25120-365">When the input isn't from the file, the value of these parameters is **InputStream** .</span></span>

<span data-ttu-id="25120-366">Se você não precisar das informações no objeto **MatchInfo** , use o parâmetro **Quiet** .</span><span class="sxs-lookup"><span data-stu-id="25120-366">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="25120-367">O parâmetro **Quiet** retorna um valor booliano (true ou false) para indicar se ele encontrou uma correspondência, em vez de um objeto **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="25120-367">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="25120-368">Quando as frases correspondentes, `Select-String` o usa a cultura atual definida para o sistema.</span><span class="sxs-lookup"><span data-stu-id="25120-368">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="25120-369">Para localizar a cultura atual, use o `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25120-369">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="25120-370">Para localizar as propriedades de um objeto **MatchInfo** , digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="25120-370">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="25120-371">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="25120-371">RELATED LINKS</span></span>

[<span data-ttu-id="25120-372">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="25120-372">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="25120-373">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="25120-373">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="25120-374">about_Functions</span><span class="sxs-lookup"><span data-stu-id="25120-374">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="25120-375">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="25120-375">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="25120-376">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="25120-376">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="25120-377">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="25120-377">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="25120-378">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="25120-378">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="25120-379">Get-Command</span><span class="sxs-lookup"><span data-stu-id="25120-379">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="25120-380">Get-Member</span><span class="sxs-lookup"><span data-stu-id="25120-380">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="25120-381">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="25120-381">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="25120-382">Out-File</span><span class="sxs-lookup"><span data-stu-id="25120-382">Out-File</span></span>](Out-File.md)
